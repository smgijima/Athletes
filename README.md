# Athletes
This is a athletes System


To Dump Database Tables for Athletes Database
-----------------------------------------------



-- phpMyAdmin SQL Dump
-- version 4.6.4
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Generation Time: Aug 15, 2017 at 02:28 PM
-- Server version: 5.7.14
-- PHP Version: 5.6.25

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `athletes`
--

-- --------------------------------------------------------

--
-- Table structure for table `athlete_register`
--

CREATE TABLE `athlete_register` (
  `Athlete_ID` int(11) NOT NULL,
  `Student_ID` int(11) NOT NULL,
  `Employee_ID` int(11) NOT NULL,
  `Date_Register` text NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `athlete_scores`
--

CREATE TABLE `athlete_scores` (
  `ID` int(11) NOT NULL,
  `Student_ID` int(11) NOT NULL,
  `Score_ID` int(11) NOT NULL,
  `Sport_ID` int(11) NOT NULL,
  `Score_Date` text
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `employee`
--

CREATE TABLE `employee` (
  `Employee_ID` int(11) NOT NULL,
  `ID_Number` text,
  `First_Name` text,
  `Last_Name` text,
  `Date_Of_Birth` text,
  `Gender` text,
  `Email_Adress` text,
  `Passwrd` text
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

--
-- Dumping data for table `employee`
--

INSERT INTO `employee` (`Employee_ID`, `ID_Number`, `First_Name`, `Last_Name`, `Date_Of_Birth`, `Gender`, `Email_Adress`, `Passwrd`) VALUES
(100, '9212065508089', 'Siphiwo', 'Mgijima', '06-12-1992', 'M', 'mgijimas@gmail.com', '1234567'),
(101, '9212065508089', 'Siphiwo', 'Mgijima', '17/12/2015', 'M', 'mgijimas@gmail.com', '1234567'),
(102, '9212065508089', 'Siphiwo', 'Mgijima', '06-12-1992', 'M', 'mgijimas@gmail.com', '1234567');

-- --------------------------------------------------------

--
-- Table structure for table `eventz`
--

CREATE TABLE `eventz` (
  `Event_ID` int(11) NOT NULL,
  `Event_Name` text NOT NULL,
  `Event_Date` text NOT NULL,
  `Event_Venue` text NOT NULL,
  `Event_Duration` text NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `event_venue`
--

CREATE TABLE `event_venue` (
  `ID` int(11) NOT NULL,
  `Event_ID` int(11) NOT NULL,
  `Venue_ID` int(11) NOT NULL,
  `Student_ID` int(11) NOT NULL,
  `Employee_ID` int(11) NOT NULL,
  `Sport_ID` int(11) NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `gender`
--

CREATE TABLE `gender` (
  `Gender_ID` int(11) NOT NULL,
  `Desciption` text
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `grade`
--

CREATE TABLE `grade` (
  `Grade_ID` int(11) NOT NULL,
  `Desciption` text
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `scores`
--

CREATE TABLE `scores` (
  `Scores_ID` int(11) NOT NULL,
  `Score_Points` int(11) NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `sport_activity`
--

CREATE TABLE `sport_activity` (
  `Sport_ID` int(11) NOT NULL,
  `Sport_Type` text NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `sport_athlete`
--

CREATE TABLE `sport_athlete` (
  `ID` int(11) NOT NULL,
  `Student_ID` int(11) NOT NULL,
  `Sport_ID` int(11) NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `student`
--

CREATE TABLE `student` (
  `Student_ID` int(11) NOT NULL,
  `ID_Number` int(11) NOT NULL,
  `First_Name` text NOT NULL,
  `Last_Name` text NOT NULL,
  `Date_Of_Birth` text NOT NULL,
  `Gender_ID` int(11) NOT NULL,
  `Grade_ID` int(11) NOT NULL,
  `Class_Group` text NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `system_user`
--

CREATE TABLE `system_user` (
  `ID` int(11) NOT NULL,
  `User_ID` text,
  `Employee_ID` int(11) DEFAULT NULL,
  `Date_Registered` text
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `users`
--

CREATE TABLE `users` (
  `User_ID` int(11) NOT NULL,
  `ID_Number` int(11) NOT NULL,
  `First_Name` text NOT NULL,
  `Last_Name` text NOT NULL,
  `Email_Adress` text NOT NULL,
  `Cell_No` text NOT NULL,
  `passwords` text NOT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Table structure for table `venue`
--

CREATE TABLE `venue` (
  `Venue_ID` int(11) NOT NULL,
  `Venue_Name` text NOT NULL,
  `Venue_Adress` text
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

--
-- Indexes for dumped tables
--

--
-- Indexes for table `athlete_register`
--
ALTER TABLE `athlete_register`
  ADD PRIMARY KEY (`Athlete_ID`),
  ADD KEY `Student_ID` (`Student_ID`),
  ADD KEY `Employee_ID` (`Employee_ID`);

--
-- Indexes for table `athlete_scores`
--
ALTER TABLE `athlete_scores`
  ADD PRIMARY KEY (`ID`),
  ADD KEY `Student_ID` (`Student_ID`),
  ADD KEY `Score_ID` (`Score_ID`),
  ADD KEY `Sport_ID` (`Sport_ID`);

--
-- Indexes for table `employee`
--
ALTER TABLE `employee`
  ADD PRIMARY KEY (`Employee_ID`);

--
-- Indexes for table `eventz`
--
ALTER TABLE `eventz`
  ADD PRIMARY KEY (`Event_ID`);

--
-- Indexes for table `event_venue`
--
ALTER TABLE `event_venue`
  ADD PRIMARY KEY (`ID`),
  ADD KEY `Event_ID` (`Event_ID`),
  ADD KEY `Venue_ID` (`Venue_ID`),
  ADD KEY `Student_ID` (`Student_ID`),
  ADD KEY `Employee_ID` (`Employee_ID`),
  ADD KEY `Sport_ID` (`Sport_ID`);

--
-- Indexes for table `gender`
--
ALTER TABLE `gender`
  ADD PRIMARY KEY (`Gender_ID`);

--
-- Indexes for table `grade`
--
ALTER TABLE `grade`
  ADD PRIMARY KEY (`Grade_ID`);

--
-- Indexes for table `scores`
--
ALTER TABLE `scores`
  ADD PRIMARY KEY (`Scores_ID`);

--
-- Indexes for table `sport_activity`
--
ALTER TABLE `sport_activity`
  ADD PRIMARY KEY (`Sport_ID`);

--
-- Indexes for table `sport_athlete`
--
ALTER TABLE `sport_athlete`
  ADD PRIMARY KEY (`ID`),
  ADD KEY `Student_ID` (`Student_ID`),
  ADD KEY `Sport_ID` (`Sport_ID`);

--
-- Indexes for table `student`
--
ALTER TABLE `student`
  ADD PRIMARY KEY (`Student_ID`),
  ADD KEY `Grade_ID` (`Grade_ID`),
  ADD KEY `Gender_ID` (`Gender_ID`);

--
-- Indexes for table `system_user`
--
ALTER TABLE `system_user`
  ADD PRIMARY KEY (`ID`),
  ADD KEY `Employee_ID` (`Employee_ID`);

--
-- Indexes for table `users`
--
ALTER TABLE `users`
  ADD PRIMARY KEY (`User_ID`),
  ADD KEY `ID_Number` (`ID_Number`);

--
-- Indexes for table `venue`
--
ALTER TABLE `venue`
  ADD PRIMARY KEY (`Venue_ID`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `athlete_register`
--
ALTER TABLE `athlete_register`
  MODIFY `Athlete_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `athlete_scores`
--
ALTER TABLE `athlete_scores`
  MODIFY `ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `employee`
--
ALTER TABLE `employee`
  MODIFY `Employee_ID` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=103;
--
-- AUTO_INCREMENT for table `eventz`
--
ALTER TABLE `eventz`
  MODIFY `Event_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `event_venue`
--
ALTER TABLE `event_venue`
  MODIFY `ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `gender`
--
ALTER TABLE `gender`
  MODIFY `Gender_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `grade`
--
ALTER TABLE `grade`
  MODIFY `Grade_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `scores`
--
ALTER TABLE `scores`
  MODIFY `Scores_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `sport_activity`
--
ALTER TABLE `sport_activity`
  MODIFY `Sport_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `sport_athlete`
--
ALTER TABLE `sport_athlete`
  MODIFY `ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `student`
--
ALTER TABLE `student`
  MODIFY `Student_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `system_user`
--
ALTER TABLE `system_user`
  MODIFY `ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `users`
--
ALTER TABLE `users`
  MODIFY `User_ID` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT for table `venue`
--
ALTER TABLE `venue`
  MODIFY `Venue_ID` int(11) NOT NULL AUTO_INCREMENT;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
