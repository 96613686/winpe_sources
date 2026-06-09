# GetErrorMessage<char>(ulong)

- ea: `0x14003d044`
- end: `0x14003d156`
- name: `??$GetErrorMessage@D@@YAPEADK@Z`
- size: `274`
- prototype: `CHAR *__fastcall(DWORD dwMessageId)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14003dbb4`
- `0x14003dcf8`
- `0x14003e1b8`

## callees

- `0x140001ac8`
- `0x140039f10`
- `0x14003d044`
- `0x14003ec14`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14003d13f`
- `KERNEL32!FreeLibrary` at `0x14003d13f`
- `KERNEL32!LoadLibraryExA` at `0x14003d08c`
- `KERNEL32!LoadLibraryExA` at `0x14003d08c`
- `KERNEL32!FormatMessageA` at `0x14003d0e0`
- `KERNEL32!FormatMessageA` at `0x14003d0e0`

## string_xrefs

- `0x14003d060`: `netmsg.dll`
- `0x14003d07d`: `Wininet.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CHAR *__fastcall GetErrorMessage<char>(DWORD dwMessageId)
{
  const CHAR *v2; // rcx
  HMODULE v3; // rbx
  CHAR *lpBuffer; // rsi
  signed int v5; // eax
  __int64 v6; // rcx
  CHAR *i; // rdi
  HMODULE Library; // [rsp+68h] [rbp+10h]

  if ( dwMessageId - 2100 > 0x383 )
  {
    v3 = 0;
    Library = 0;
    if ( dwMessageId - 12000 > 0xC0 )
      goto LABEL_18;
    v2 = "Wininet.dll";
  }
  else
  {
    v2 = "netmsg.dll";
  }
  Library = LoadLibraryExA(v2, 0, 2u);
  v3 = Library;
LABEL_18:
  try
  {
    lpBuffer = (CHAR *)operator new[](0x200u);
    v5 = FormatMessageA(v3 != 0 ? 6144 : 4096, v3, dwMessageId, 0x400u, lpBuffer, 0x200u, 0);
    if ( v5 )
    {
      for ( i = &lpBuffer[v5 - 1]; i >= lpBuffer; --i )
      {
        LOBYTE(v6) = *i;
        if ( !(unsigned __int8)mlib::m_traits<char>::isSpace(v6) )
          break;
        *i = 0;
      }
    }
    else
    {
      Log_Text_F("base\\winsat\\exe\\logging.cpp", 299, "INFO: cannot find message for Win32 error %u", dwMessageId);
      *lpBuffer = 0;
    }
  }
  catch ( std::bad_alloc )
  {
    Log_Text_F("base\\winsat\\exe\\logging.cpp", 309, "INFO: cannot allocate memory for error string");
    v3 = Library;
    lpBuffer = 0;
  }
  lpBuffer = (CHAR *)operator new[](0x200u);
  v5 = FormatMessageA(v3 != 0 ? 6144 : 4096, v3, dwMessageId, 0x400u, lpBuffer, 0x200u, 0);
}

```

## disassembly

```asm
0x14003d044  mov     [rsp+arg_0], rbx
0x14003d049  push    rsi
0x14003d04a  push    rdi
0x14003d04b  push    r14
0x14003d04d  sub     rsp, 40h
0x14003d051  mov     edi, ecx
0x14003d053  lea     eax, [rcx-834h]
0x14003d059  cmp     eax, 383h
0x14003d05e  ja      short loc_14003D069
0x14003d060  lea     rcx, aNetmsgDll; "netmsg.dll"
0x14003d067  jmp     short loc_14003D084
0x14003d069  xor     ebx, ebx
0x14003d06b  mov     [rsp+58h+arg_8], rbx
0x14003d070  lea     eax, [rcx-2EE0h]
0x14003d076  cmp     eax, 0C0h
0x14003d07b  ja      short loc_14003D09A
0x14003d07d  lea     rcx, aWininetDll_0; "Wininet.dll"
0x14003d084  mov     r8d, 2; dwFlags
0x14003d08a  xor     edx, edx; hFile
0x14003d08c  call    cs:__imp_LoadLibraryExA
0x14003d092  mov     [rsp+58h+arg_8], rax
0x14003d097  mov     rbx, rax
0x14003d09a  mov     rax, rbx
0x14003d09d  neg     rax
0x14003d0a0  sbb     r14d, r14d
0x14003d0a3  and     r14d, 800h
0x14003d0aa  mov     ecx, 200h; unsigned __int64
0x14003d0af  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14003d0b4  mov     rsi, rax
0x14003d0b7  mov     [rsp+58h+Arguments], 0; Arguments
0x14003d0c0  mov     [rsp+58h+nSize], 200h; nSize
0x14003d0c8  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x14003d0cd  mov     r9d, 400h; dwLanguageId
0x14003d0d3  mov     r8d, edi; dwMessageId
0x14003d0d6  mov     rdx, rbx; lpSource
0x14003d0d9  lea     ecx, [r14+1000h]; dwFlags
0x14003d0e0  call    cs:__imp_FormatMessageA
0x14003d0e6  test    eax, eax
0x14003d0e8  jnz     short loc_14003D10A
0x14003d0ea  mov     r9d, edi
0x14003d0ed  lea     r8, aInfoCannotFind; "INFO: cannot find message for Win32 err"...
0x14003d0f4  mov     edx, 12Bh
0x14003d0f9  lea     rcx, aBaseWinsatExeL; "base\\winsat\\exe\\logging.cpp"
0x14003d100  call    Log_Text_F
0x14003d105  mov     byte ptr [rsi], 0
0x14003d108  jmp     short loc_14003D12B
0x14003d10a  movsxd  rdi, eax
0x14003d10d  dec     rdi
0x14003d110  add     rdi, rsi
0x14003d113  jmp     short loc_14003D126
0x14003d115  mov     cl, [rdi]
0x14003d117  call    ?isSpace@?$m_traits@D@mlib@@SA_ND@Z; mlib::m_traits<char>::isSpace(char)
0x14003d11c  test    al, al
0x14003d11e  jz      short loc_14003D12B
0x14003d120  mov     byte ptr [rdi], 0
0x14003d123  dec     rdi
0x14003d126  cmp     rdi, rsi
0x14003d129  jnb     short loc_14003D115
0x14003d12b  jmp     short loc_14003D137
0x14003d12d  mov     rbx, [rsp+58h+arg_8]
0x14003d132  mov     rsi, [rsp+58h+arg_10]
0x14003d137  test    rbx, rbx
0x14003d13a  jz      short loc_14003D145
0x14003d13c  mov     rcx, rbx; hLibModule
0x14003d13f  call    cs:__imp_FreeLibrary
0x14003d145  mov     rax, rsi
0x14003d148  mov     rbx, [rsp+58h+arg_0]
0x14003d14d  add     rsp, 40h
0x14003d151  pop     r14
0x14003d153  pop     rdi
0x14003d154  pop     rsi
0x14003d155  retn
```
