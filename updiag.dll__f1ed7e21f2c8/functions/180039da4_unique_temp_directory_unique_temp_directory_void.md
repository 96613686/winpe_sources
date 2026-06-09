# unique_temp_directory::~unique_temp_directory(void)

- ea: `0x180039da4`
- end: `0x180039e5c`
- name: `??1unique_temp_directory@@QEAA@XZ`
- size: `184`
- prototype: `void __fastcall(unique_temp_directory *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180039e64`
- `0x18003a460`

## callees

- `0x180018eec`
- `0x180039da4`
- `0x1800641c4`
- `0x1800670a4`
- `0x18007a150`

## string_xrefs

- `0x180039e32`: `Failed to remove temporary directory: %ls`
- `0x180039e3e`: `C:\__w\1\s\src\Calliope\libs\inc\unique_temp_directory.hpp`

## pseudocode

```c
void __fastcall unique_temp_directory::~unique_temp_directory(unique_temp_directory *this)
{
  unique_temp_directory *v1; // rbx
  __int64 v2; // rax
  unsigned __int64 *v3; // r9
  const char *v4; // rax
  char *v5[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v6[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = this;
  if ( *((_BYTE *)this + 32) && *((_QWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 3) > 7u )
      this = *(unique_temp_directory **)this;
    v2 = _std_fs_remove(this);
    v6[0] = (unsigned __int8)v2;
    LODWORD(v5[0]) = HIDWORD(v2);
    v5[1] = (char *)&`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    if ( HIDWORD(v2) == 145 )
      std::filesystem::_Remove_all_dir(v1, (const struct std::filesystem::path *)v5, (struct std::error_code *)v6, v3);
    if ( LODWORD(v5[0]) )
    {
      v4 = (const char *)v1;
      if ( *((_QWORD *)v1 + 3) > 7u )
        v4 = *(const char **)v1;
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x2F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\libs\\inc\\unique_temp_directory.hpp",
        (const char *)LODWORD(v5[0]),
        (unsigned int)"Failed to remove temporary directory: %ls",
        v4);
    }
  }
  std::wstring::~wstring(v1);
}

```

## disassembly

```asm
0x180039da4  push    rbx
0x180039da6  sub     rsp, 50h
0x180039daa  mov     rbx, rcx
0x180039dad  cmp     byte ptr [rcx+20h], 0
0x180039db1  jz      loc_180039E4F
0x180039db7  cmp     qword ptr [rcx+10h], 0
0x180039dbc  jz      loc_180039E4F
0x180039dc2  cmp     qword ptr [rcx+18h], 7
0x180039dc7  jbe     short loc_180039DCC
0x180039dc9  mov     rcx, [rcx]
0x180039dcc  call    __std_fs_remove
0x180039dd1  movzx   ecx, al
0x180039dd4  mov     [rsp+58h+var_18], rcx
0x180039dd9  shr     rax, 20h
0x180039ddd  mov     dword ptr [rsp+58h+var_28], eax
0x180039de1  lea     rcx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180039de8  mov     [rsp+58h+var_28+8], rcx
0x180039ded  movaps  xmm0, xmmword ptr [rsp+58h+var_28]
0x180039df2  movdqa  xmmword ptr [rsp+58h+var_28], xmm0
0x180039df8  cmp     eax, 91h
0x180039dfd  jnz     short loc_180039E11
0x180039dff  lea     r8, [rsp+58h+var_18]; struct std::error_code *
0x180039e04  lea     rdx, [rsp+58h+var_28]; struct std::filesystem::path *
0x180039e09  mov     rcx, rbx; this
0x180039e0c  call    ?_Remove_all_dir@filesystem@std@@YAXAEBVpath@12@AEAVerror_code@2@AEA_K@Z; std::filesystem::_Remove_all_dir(std::filesystem::path const &,std::error_code &,unsigned __int64 &)
0x180039e11  mov     r9d, dword ptr [rsp+58h+var_28]; char *
0x180039e16  test    r9d, r9d
0x180039e19  jz      short loc_180039E4F
0x180039e1b  mov     rax, rbx
0x180039e1e  cmp     qword ptr [rbx+18h], 7
0x180039e23  jbe     short loc_180039E28
0x180039e25  mov     rax, [rbx]
0x180039e28  mov     rcx, [rsp+58h]; this
0x180039e2d  mov     [rsp+58h+var_30], rax; char *
0x180039e32  lea     rax, aFailedToRemove; "Failed to remove temporary directory: %"...
0x180039e39  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180039e3e  lea     r8, aCW1SSrcCalliop_21; "C:\\__w\\1\\s\\src\\Calliope\\libs\\inc"...
0x180039e45  mov     edx, 2Fh ; '/'; void *
0x180039e4a  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180039e4f  mov     rcx, rbx
0x180039e52  add     rsp, 50h
0x180039e56  pop     rbx
0x180039e57  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
