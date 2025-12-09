"use client";
import { useEffect, useState } from "react";

export default function Home() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch("YOUR_WEB_APP_URL")
      .then(res => res.json())
      .then(setData);
  }, []);

  return (
    <div style={{ padding: "20px" }}>
      <h1>YouTube Trending</h1>

      <table border="1" cellPadding="6">
        <thead>
          <tr>
            <th>Title</th>
            <th>Channel</th>
            <th>Views</th>
          </tr>
        </thead>
        <tbody>
          {data.map((item, i) => (
            <tr key={i}>
              <td>{item.title}</td>
              <td>{item.channel}</td>
              <td>{item.views}</td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}
