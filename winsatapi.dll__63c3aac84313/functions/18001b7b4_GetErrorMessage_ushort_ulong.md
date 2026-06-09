# GetErrorMessage<ushort>(ulong)

- ea: `0x18001b7b4`
- end: `0x18001b8f0`
- name: `??$GetErrorMessage@G@@YAPEAGK@Z`
- size: `316`
- prototype: `WCHAR *__fastcall(DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001c414`

## callees

- `0x18000a380`
- `0x18000e6ac`
- `0x180013370`
- `0x18001b7b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b7ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b81a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b7ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001b81a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b8d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b8d1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b86a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b86a`

## string_xrefs

- `0x18001b7e6`: `netmsg.dll`
- `0x18001b813`: `Wininet.dll`
- `0x18001b883`: `base\winsat\api-dll\logging.cpp`

## pseudocode

```c
WCHAR *__fastcall GetErrorMessage<unsigned short>(DWORD dwMessageId)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  WCHAR *lpBuffer; // rsi
  signed int v5; // eax
  WCHAR *i; // r14
  HMODULE v8; // [rsp+78h] [rbp+10h]

  if ( dwMessageId - 2100 > 0x383 )
  {
    v3 = 0;
    v8 = 0;
    if ( dwMessageId - 12000 > 0xC0 )
      goto LABEL_18;
    Library = LoadLibraryExA("Wininet.dll", 0, 2u);
  }
  else
  {
    Library = LoadLibraryExA("netmsg.dll", 0, 2u);
  }
  v8 = Library;
  v3 = Library;
LABEL_18:
  try
  {
    lpBuffer = (WCHAR *)operator new[](0x400u);
    v5 = FormatMessageW(v3 != 0 ? 6144 : 4096, v3, dwMessageId, 0x400u, lpBuffer, 0x200u, 0);
    if ( v5 )
    {
      for ( i = &lpBuffer[v5 - 1]; i >= lpBuffer && (unsigned __int8)mlib::m_traits<unsigned short>::isSpace(*i); --i )
        *i = 0;
    }
    else
    {
      Log_Text_F("base\\winsat\\api-dll\\logging.cpp", 196, "INFO: cannot find message for Win32 error %u", dwMessageId);
      *lpBuffer = 0;
    }
  }
  catch ( std::bad_alloc )
  {
    Log_Text_F("base\\winsat\\api-dll\\logging.cpp", 206, "INFO: cannot allocate memory for error string");
    v3 = v8;
    lpBuffer = (WCHAR *)&String2;
  }
  lpBuffer = (WCHAR *)operator new[](0x400u);
  v5 = FormatMessageW(v3 != 0 ? 6144 : 4096, v3, dwMessageId, 0x400u, lpBuffer, 0x200u, 0);
}

```

## disassembly

```asm
0x18001b7b4  mov     rax, rsp
0x18001b7b7  push    rdi
0x18001b7b8  push    r14
0x18001b7ba  push    r15
0x18001b7bc  sub     rsp, 50h
0x18001b7c0  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18001b7c8  mov     [rax+8], rbx
0x18001b7cc  mov     [rax+20h], rsi
0x18001b7d0  mov     r14d, ecx
0x18001b7d3  lea     eax, [rcx-834h]
0x18001b7d9  cmp     eax, 383h
0x18001b7de  ja      short loc_18001B7F7
0x18001b7e0  xor     edx, edx; hFile
0x18001b7e2  lea     r8d, [rdx+2]; dwFlags
0x18001b7e6  lea     rcx, aNetmsgDll; "netmsg.dll"
0x18001b7ed  call    cs:__imp_LoadLibraryExA
0x18001b7f3  xor     edi, edi
0x18001b7f5  jmp     short loc_18001B820
0x18001b7f7  xor     edi, edi
0x18001b7f9  mov     ebx, edi
0x18001b7fb  mov     [rsp+68h+arg_8], rbx
0x18001b800  lea     eax, [rcx-2EE0h]
0x18001b806  cmp     eax, 0C0h
0x18001b80b  ja      short loc_18001B828
0x18001b80d  xor     edx, edx; hFile
0x18001b80f  lea     r8d, [rdi+2]; dwFlags
0x18001b813  lea     rcx, aWininetDll; "Wininet.dll"
0x18001b81a  call    cs:__imp_LoadLibraryExA
0x18001b820  mov     [rsp+68h+arg_8], rax
0x18001b825  mov     rbx, rax
0x18001b828  mov     rax, rbx
0x18001b82b  neg     rax
0x18001b82e  sbb     r15d, r15d
0x18001b831  and     r15d, 800h
0x18001b838  mov     ecx, 400h; unsigned __int64
0x18001b83d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001b842  mov     rsi, rax
0x18001b845  mov     [rsp+68h+Arguments], rdi; Arguments
0x18001b84a  mov     [rsp+68h+nSize], 200h; nSize
0x18001b852  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x18001b857  mov     r9d, 400h; dwLanguageId
0x18001b85d  mov     r8d, r14d; dwMessageId
0x18001b860  mov     rdx, rbx; lpSource
0x18001b863  lea     ecx, [r15+1000h]; dwFlags
0x18001b86a  call    cs:__imp_FormatMessageW
0x18001b870  test    eax, eax
0x18001b872  jnz     short loc_18001B894
0x18001b874  mov     r9d, r14d
0x18001b877  lea     r8, aInfoCannotFind; "INFO: cannot find message for Win32 err"...
0x18001b87e  mov     edx, 0C4h
0x18001b883  lea     rcx, aBaseWinsatApiD_0; "base\\winsat\\api-dll\\logging.cpp"
0x18001b88a  call    Log_Text_F
0x18001b88f  mov     [rsi], di
0x18001b892  jmp     short loc_18001B8BA
0x18001b894  movsxd  r14, eax
0x18001b897  dec     r14
0x18001b89a  lea     r14, [rsi+r14*2]
0x18001b89e  jmp     short loc_18001B8B5
0x18001b8a0  movzx   ecx, word ptr [r14]
0x18001b8a4  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x18001b8a9  test    al, al
0x18001b8ab  jz      short loc_18001B8BA
0x18001b8ad  mov     [r14], di
0x18001b8b1  sub     r14, 2
0x18001b8b5  cmp     r14, rsi
0x18001b8b8  jnb     short loc_18001B8A0
0x18001b8ba  jmp     short loc_18001B8C9
0x18001b8bc  mov     rbx, [rsp+68h+arg_8]
0x18001b8c1  mov     rsi, [rsp+68h+arg_10]
0x18001b8c9  test    rbx, rbx
0x18001b8cc  jz      short loc_18001B8D7
0x18001b8ce  mov     rcx, rbx; hLibModule
0x18001b8d1  call    cs:__imp_FreeLibrary
0x18001b8d7  mov     rax, rsi
0x18001b8da  lea     r11, [rsp+68h+var_18]
0x18001b8df  mov     rbx, [r11+20h]
0x18001b8e3  mov     rsi, [r11+38h]
0x18001b8e7  mov     rsp, r11
0x18001b8ea  pop     r15
0x18001b8ec  pop     r14
0x18001b8ee  pop     rdi
0x18001b8ef  retn
```
