# Nguyen Van Minh - CV LaTeX (Modular)

Hệ thống CV LaTeX theo kiến trúc module: một nguồn nội dung chung, nhiều CV theo từng công ty.

## Mục tiêu

- Không copy/paste nhiều file CV.
- Dễ tùy biến theo từng job/company.
- Dễ bảo trì khi cập nhật nội dung.

## Cấu trúc chính

- base/: nội dung và style dùng chung
- base/preamble.tex: package, layout, font
- base/commands.tex: macro và biến cấu hình
- base/sections/: từng phần của CV (header, experience, projects, education, skills)
- companies/<company-name>/: CV riêng cho từng công ty
- companies/<company-name>/main.tex: chọn thứ tự section
- companies/<company-name>/overrides.tex: override skill/biến riêng
- main.tex: entry root để compile trên Overleaf

## Cách dùng trên Overleaf

1. Upload toàn bộ project.
2. Vào Menu > Main document và chọn:
   - main.tex (khuyến nghị), hoặc
   - companies/<company-name>/main.tex nếu chỉ muốn compile 1 CV cụ thể.
3. Recompile.

Lưu ý: không compile trực tiếp các file include như preamble.tex hoặc sections/*.tex.

## Tạo CV cho công ty mới

1. Tạo thư mục companies/<new-company>/.
2. Copy từ companies/example/:
   - main.tex
   - overrides.tex
3. Chỉnh main.tex để đổi thứ tự/ẩn hiện section.
4. Chỉnh overrides.tex để thay skill theo JD.

## Tùy biến skills theo công ty

Hiện tại hỗ trợ 2 macro:

- \SkillLanguages
- \SkillTools

Ví dụ trong overrides.tex:

\renewcommand{\SkillLanguages}{Java, Python, SQL}
\renewcommand{\SkillTools}{Spring Boot, Kafka, Redis, Docker}

## Ví dụ đã có sẵn

- companies/google-swe/
- companies/shopee-backend/

## License

MIT
