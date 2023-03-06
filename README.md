# Hello
# La-Net releted info

Please treat this email as an application for leave. I would like to inform you that I require a day of absence on /04/02/2023 Saturday. I will be back in the office on the following 06/02/2023 Monday.

https://forms.gle/BcomJDEkrgGbKnX4A

//////////////////////////////////////////////////////////////////////

import React, { useState } from "react";
import style from "./TTT.module.css";
let val = 0;
const xMove: number[] = [];
const oMove: number[] = [];
const reset = {
  td1: "",
  td2: "",
  td3: "",
  td4: "",
  td5: "",
  td6: "",
  td7: "",
  td8: "",
  td9: "",
};
const TTT = () => {
  const OX = ["O", "X"];
  const win = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9],
    [1, 4, 7],
    [2, 5, 8],
    [3, 6, 9],
    [1, 5, 9],
    [3, 5, 7],
  ];
  const [ShowArr, setShowArr] = useState(reset);
  //   chance.forEach(element => {

  //   });
  const onClickHandler = (event: any) => {
    // console.log(event.target.id);
    if (val === 0) {
      setShowArr({ ...ShowArr, [`td${event.target.id}`]: OX[0] });
      oMove.push(+event.target.id);
      console.log("o");

      val = 1;
    } else {
      setShowArr({ ...ShowArr, [`td${event.target.id}`]: OX[1] });
      xMove.push(+event.target.id);
      // console.log("x", win.includes(xMove.sort((a, b) => a - b).join("")));
      val = 0;
    }
  };
  //   console.log(xMove, oMove);

  return (
    <>
      <table cellSpacing={0} className={style.ticTacToe}>
        <tr>
          <td id='1' onClick={onClickHandler}>
            {ShowArr.td1}
          </td>
          <td id='2' onClick={onClickHandler}>
            {ShowArr.td2}
          </td>
          <td id='3' onClick={onClickHandler}>
            {ShowArr.td3}
          </td>
        </tr>
        <tr>
          <td id='4' onClick={onClickHandler}>
            {ShowArr.td4}
          </td>
          <td id='5' onClick={onClickHandler}>
            {ShowArr.td5}
          </td>
          <td id='6' onClick={onClickHandler}>
            {ShowArr.td6}
          </td>
        </tr>
        <tr>
          <td id='7' onClick={onClickHandler}>
            {ShowArr.td7}
          </td>
          <td id='8' onClick={onClickHandler}>
            {ShowArr.td8}
          </td>
          <td id='9' onClick={onClickHandler}>
            {ShowArr.td9}
          </td>
        </tr>
      </table>
      <button onClick={() => setShowArr(reset)}>reset</button>
    </>
  );
};

export default TTT;
/*
win.map((val) =>val.map((val) => {
                  if (oMove.includes(val)) {
                    return "0";
                  }
                  return "1";
                }).join("") === "000"
          ).filter((val) => val)[0]

.ticTacToe{
    display: block;
    width: 30%;
    height: 30%;
    border-collapse: collapse;
    margin: 10% auto;
}
.ticTacToe td{
    border: 3px solid black;
    width: 100px;
    height: 100px;
    text-align: center;
    font-size: 80px;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
}
.ticTacToe tr:first-child td {
  border-top: none;
}

.ticTacToe tr:last-child td {
  border-bottom: none;
}

.ticTacToe tr td:first-child {
  border-left: none;
}

.ticTacToe tr td:last-child {
  border-right: none;
}
*/

