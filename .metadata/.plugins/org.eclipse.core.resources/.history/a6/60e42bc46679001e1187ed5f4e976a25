package dao;


import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.ArrayList;
import connectDB.ConnectDB;
import java.sql.Statement;

import entity.LoaiPhong;
import entity.PhongHat;
public class Phong_DAO {
	public ArrayList<PhongHat> getAllPhong() {
		ArrayList<PhongHat> dsPhong = new ArrayList<PhongHat>();
		
		try {
			ConnectDB.getInstance();
			Connection con = ConnectDB.getConnection();
			String sql = "SELECT MaPhongHat, TenPhongHat, GiaPhong, TinhTrang, SucChua, p.MaLoaiPhong, l.TenLoaiPhong FROM tbl_PhongHat p join tbl_LoaiPhong l on p.MaLoaiPhong = l.MaLoaiPhong";
			Statement statement = con.createStatement();
			ResultSet rs = statement.executeQuery(sql);
			while(rs.next()) {
				String ma = rs.getString(1);
				String ten = rs.getString(2);
				double donGia = rs.getDouble(3);
				String tinhTrang = rs.getString(4);
				int sucChua = rs.getInt(5);
				LoaiPhong lp = new LoaiPhong(rs.getString(6), rs.getString(7));
				
				PhongHat p = new PhongHat(ma, ten, lp, donGia, tinhTrang, sucChua);
				dsPhong.add(p);
			}
		
		} catch (SQLException e) {
			// TODO: handle exception
			e.printStackTrace();
		}
		return dsPhong;
	}

}
