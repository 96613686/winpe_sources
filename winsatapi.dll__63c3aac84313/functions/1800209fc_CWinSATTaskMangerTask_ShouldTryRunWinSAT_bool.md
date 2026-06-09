# CWinSATTaskMangerTask::ShouldTryRunWinSAT(bool &)

- ea: `0x1800209fc`
- end: `0x180020abe`
- name: `?ShouldTryRunWinSAT@CWinSATTaskMangerTask@@AEAAJAEA_N@Z`
- size: `194`
- prototype: `__int64 __fastcall(CWinSATTaskMangerTask *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180020dcc`

## callees

- `0x18000e6ac`
- `0x180011124`
- `0x1800209fc`
- `0x18002d328`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a2d`

## string_xrefs

- `0x180020a69`: `base\winsat\api-dll\winsattaskmangertask.cpp`
- `0x180020a8f`: `base\winsat\api-dll\winsattaskmangertask.cpp`

## pseudocode

```c
__int64 __fastcall CWinSATTaskMangerTask::ShouldTryRunWinSAT(CWinSATTaskMangerTask *this, bool *a2)
{
  DWORD LastError; // eax
  bool v5; // [rsp+20h] [rbp-138h] BYREF
  CHAR Buffer[256]; // [rsp+30h] [rbp-128h] BYREF
  DWORD v7; // [rsp+130h] [rbp-28h]
  char v8; // [rsp+134h] [rbp-24h]
  __int64 v9; // [rsp+138h] [rbp-20h]

  v5 = 0;
  if ( HasActiveConsoleWindow(&v5) )
  {
    LastError = GetLastError();
    v8 = 1;
    v7 = LastError;
    v9 = 0;
    mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
    Log_Text_F(
      (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
      172,
      "Cannot determine who has the active console Window: %s",
      Buffer);
    return 2147500037LL;
  }
  else
  {
    if ( v5 )
    {
      *a2 = 1;
    }
    else
    {
      Log_Text_F(
        (__int64)"base\\winsat\\api-dll\\winsattaskmangertask.cpp",
        176,
        "The Active Console Window is not available, cannot run WinSAT");
      *a2 = 0;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800209fc  push    rbx
0x1800209fe  sub     rsp, 150h
0x180020a05  mov     rax, cs:__security_cookie
0x180020a0c  xor     rax, rsp
0x180020a0f  mov     [rsp+158h+var_18], rax
0x180020a17  lea     rcx, [rsp+158h+var_138]; bool *
0x180020a1c  mov     [rsp+158h+var_138], 0
0x180020a21  mov     rbx, rdx
0x180020a24  call    ?HasActiveConsoleWindow@@YAKAEA_N@Z; HasActiveConsoleWindow(bool &)
0x180020a29  test    eax, eax
0x180020a2b  jz      short loc_180020A7C
0x180020a2d  call    cs:__imp_GetLastError
0x180020a33  lea     rcx, [rsp+158h+Buffer]; lpBuffer
0x180020a38  mov     [rsp+158h+var_24], 1
0x180020a40  mov     [rsp+158h+var_28], eax
0x180020a47  mov     [rsp+158h+var_20], 0
0x180020a53  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x180020a58  lea     r9, [rsp+158h+Buffer]
0x180020a5d  mov     edx, 0ACh
0x180020a62  lea     r8, aCannotDetermin_0; "Cannot determine who has the active con"...
0x180020a69  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020a70  call    Log_Text_F
0x180020a75  mov     eax, 80004005h
0x180020a7a  jmp     short loc_180020AA5
0x180020a7c  cmp     [rsp+158h+var_138], 0
0x180020a81  jnz     short loc_180020AA0
0x180020a83  lea     r8, aTheActiveConso; "The Active Console Window is not availa"...
0x180020a8a  mov     edx, 0B0h
0x180020a8f  lea     rcx, aBaseWinsatApiD_1; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180020a96  call    Log_Text_F
0x180020a9b  mov     byte ptr [rbx], 0
0x180020a9e  jmp     short loc_180020AA3
0x180020aa0  mov     byte ptr [rbx], 1
0x180020aa3  xor     eax, eax
0x180020aa5  mov     rcx, [rsp+158h+var_18]
0x180020aad  xor     rcx, rsp; StackCookie
0x180020ab0  call    __security_check_cookie
0x180020ab5  add     rsp, 150h
0x180020abc  pop     rbx
0x180020abd  retn
```
