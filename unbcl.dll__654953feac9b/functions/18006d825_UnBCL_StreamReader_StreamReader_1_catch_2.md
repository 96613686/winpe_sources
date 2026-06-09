# _UnBCL::StreamReader::_StreamReader_::_1_::catch$2

- ea: `0x18006d825`
- end: `0x18006d8af`
- name: `_UnBCL::StreamReader::_StreamReader_::_1_::catch$2`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180059cf0`
- `0x18006d825`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006d846`
- `KERNEL32!GetLastError` at `0x18006d846`

## string_xrefs

- `0x18006d850`: `UnBCL::StreamReader::~StreamReader`
- `0x18006d86e`: `StreamReader::Close throw an Win32Exception`
- `0x18006d85c`: `base\ntsetup\unbcl\src\streamreader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall UnBCL::StreamReader::_StreamReader_::_1_::catch_2(__int64 a1, __int64 a2)
{
  struct ILogHandler *v3; // rdi
  void (__fastcall *v4)(struct ILogHandler *, __int64, const char *, __int64, const wchar_t *, const wchar_t *, DWORD); // rbx
  DWORD LastError; // eax
  void (__fastcall ***v6)(_QWORD, __int64); // rcx

  v3 = UnBCL::Logging::s_Handler;
  if ( UnBCL::Logging::s_Handler )
  {
    v4 = **(void (__fastcall ***)(struct ILogHandler *, __int64, const char *, __int64, const wchar_t *, const wchar_t *, DWORD))UnBCL::Logging::s_Handler;
    LastError = GetLastError();
    v4(
      v3,
      50331648,
      "StreamReader::Close throw an Win32Exception",
      57,
      L"base\\ntsetup\\unbcl\\src\\streamreader.cpp",
      L"UnBCL::StreamReader::~StreamReader",
      LastError);
  }
  v6 = *(void (__fastcall ****)(_QWORD, __int64))(a2 + 72);
  if ( v6 )
    (**v6)(v6, 1);
  return &loc_180059D79;
}

```

## disassembly

```asm
0x18006d825  mov     [rsp+arg_8], rdx
0x18006d82a  push    rbx
0x18006d82b  push    rbp
0x18006d82c  push    rdi
0x18006d82d  sub     rsp, 40h
0x18006d831  mov     rbp, rdx
0x18006d834  mov     rdi, cs:?s_Handler@Logging@UnBCL@@0PEAUILogHandler@@EA; ILogHandler * UnBCL::Logging::s_Handler
0x18006d83b  test    rdi, rdi
0x18006d83e  jz      short loc_18006D885
0x18006d840  mov     rax, [rdi]
0x18006d843  mov     rbx, [rax]
0x18006d846  call    cs:__imp_GetLastError
0x18006d84c  mov     [rsp+58h+var_28], eax
0x18006d850  lea     rax, aUnbclStreamrea; "UnBCL::StreamReader::~StreamReader"
0x18006d857  mov     [rsp+58h+var_30], rax
0x18006d85c  lea     rax, aBaseNtsetupUnb_10; "base\\ntsetup\\unbcl\\src\\streamreader"...
0x18006d863  mov     [rsp+58h+var_38], rax
0x18006d868  mov     r9d, 39h ; '9'
0x18006d86e  lea     r8, aStreamreaderCl; "StreamReader::Close throw an Win32Excep"...
0x18006d875  mov     edx, 3000000h
0x18006d87a  mov     rcx, rdi
0x18006d87d  mov     rax, rbx
0x18006d880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d885  mov     rcx, [rbp+48h]
0x18006d889  test    rcx, rcx
0x18006d88c  jz      short loc_18006D89F
0x18006d88e  mov     rax, [rcx]
0x18006d891  mov     edx, 1
0x18006d896  mov     rax, [rax]
0x18006d899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d89e  nop
0x18006d89f  lea     rax, loc_180059D79
0x18006d8a6  add     rsp, 40h
0x18006d8aa  pop     rdi
0x18006d8ab  pop     rbp
0x18006d8ac  pop     rbx
0x18006d8ad  retn
```
