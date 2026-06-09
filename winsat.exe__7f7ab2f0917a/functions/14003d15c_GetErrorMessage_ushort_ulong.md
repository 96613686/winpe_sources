# GetErrorMessage<ushort>(ulong)

- ea: `0x14003d15c`
- end: `0x14003d289`
- name: `??$GetErrorMessage@G@@YAPEAGK@Z`
- size: `301`
- prototype: `WCHAR *__fastcall(DWORD dwMessageId)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14003fa8c`
- `0x1400426ac`

## callees

- `0x140001ac8`
- `0x1400188d0`
- `0x14003d15c`
- `0x14003ec14`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14003d26c`
- `KERNEL32!FreeLibrary` at `0x14003d26c`
- `KERNEL32!LoadLibraryExA` at `0x14003d18c`
- `KERNEL32!LoadLibraryExA` at `0x14003d1b9`
- `KERNEL32!LoadLibraryExA` at `0x14003d18c`
- `KERNEL32!LoadLibraryExA` at `0x14003d1b9`
- `KERNEL32!FormatMessageW` at `0x14003d209`
- `KERNEL32!FormatMessageW` at `0x14003d209`

## string_xrefs

- `0x14003d185`: `netmsg.dll`
- `0x14003d1b2`: `Wininet.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WCHAR *__fastcall GetErrorMessage<unsigned short>(DWORD dwMessageId)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  WCHAR *lpBuffer; // rsi
  signed int v5; // eax
  WCHAR *i; // r14
  HMODULE v8; // [rsp+68h] [rbp+10h]

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
      Log_Text_F("base\\winsat\\exe\\logging.cpp", 366, "INFO: cannot find message for Win32 error %u", dwMessageId);
      *lpBuffer = 0;
    }
  }
  catch ( std::bad_alloc )
  {
    Log_Text_F("base\\winsat\\exe\\logging.cpp", 376, "INFO: cannot allocate memory for error string");
    v3 = v8;
    lpBuffer = 0;
  }
  lpBuffer = (WCHAR *)operator new[](0x400u);
  v5 = FormatMessageW(v3 != 0 ? 6144 : 4096, v3, dwMessageId, 0x400u, lpBuffer, 0x200u, 0);
}

```

## disassembly

```asm
0x14003d15c  mov     [rsp+arg_0], rbx
0x14003d161  mov     [rsp+arg_18], rsi
0x14003d166  push    rdi
0x14003d167  push    r14
0x14003d169  push    r15
0x14003d16b  sub     rsp, 40h
0x14003d16f  mov     r14d, ecx
0x14003d172  lea     eax, [rcx-834h]
0x14003d178  cmp     eax, 383h
0x14003d17d  ja      short loc_14003D196
0x14003d17f  xor     edx, edx; hFile
0x14003d181  lea     r8d, [rdx+2]; dwFlags
0x14003d185  lea     rcx, aNetmsgDll; "netmsg.dll"
0x14003d18c  call    cs:__imp_LoadLibraryExA
0x14003d192  xor     edi, edi
0x14003d194  jmp     short loc_14003D1BF
0x14003d196  xor     edi, edi
0x14003d198  mov     ebx, edi
0x14003d19a  mov     [rsp+58h+arg_8], rbx
0x14003d19f  lea     eax, [rcx-2EE0h]
0x14003d1a5  cmp     eax, 0C0h
0x14003d1aa  ja      short loc_14003D1C7
0x14003d1ac  xor     edx, edx; hFile
0x14003d1ae  lea     r8d, [rdi+2]; dwFlags
0x14003d1b2  lea     rcx, aWininetDll_0; "Wininet.dll"
0x14003d1b9  call    cs:__imp_LoadLibraryExA
0x14003d1bf  mov     [rsp+58h+arg_8], rax
0x14003d1c4  mov     rbx, rax
0x14003d1c7  mov     rax, rbx
0x14003d1ca  neg     rax
0x14003d1cd  sbb     r15d, r15d
0x14003d1d0  and     r15d, 800h
0x14003d1d7  mov     ecx, 400h; unsigned __int64
0x14003d1dc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14003d1e1  mov     rsi, rax
0x14003d1e4  mov     [rsp+58h+Arguments], rdi; Arguments
0x14003d1e9  mov     [rsp+58h+nSize], 200h; nSize
0x14003d1f1  mov     [rsp+58h+lpBuffer], rax; lpBuffer
0x14003d1f6  mov     r9d, 400h; dwLanguageId
0x14003d1fc  mov     r8d, r14d; dwMessageId
0x14003d1ff  mov     rdx, rbx; lpSource
0x14003d202  lea     ecx, [r15+1000h]; dwFlags
0x14003d209  call    cs:__imp_FormatMessageW
0x14003d20f  test    eax, eax
0x14003d211  jnz     short loc_14003D233
0x14003d213  mov     r9d, r14d
0x14003d216  lea     r8, aInfoCannotFind; "INFO: cannot find message for Win32 err"...
0x14003d21d  mov     edx, 16Eh
0x14003d222  lea     rcx, aBaseWinsatExeL; "base\\winsat\\exe\\logging.cpp"
0x14003d229  call    Log_Text_F
0x14003d22e  mov     [rsi], di
0x14003d231  jmp     short loc_14003D259
0x14003d233  movsxd  r14, eax
0x14003d236  dec     r14
0x14003d239  lea     r14, [rsi+r14*2]
0x14003d23d  jmp     short loc_14003D254
0x14003d23f  movzx   ecx, word ptr [r14]
0x14003d243  call    ?isSpace@?$m_traits@G@mlib@@SA_NG@Z; mlib::m_traits<ushort>::isSpace(ushort)
0x14003d248  test    al, al
0x14003d24a  jz      short loc_14003D259
0x14003d24c  mov     [r14], di
0x14003d250  sub     r14, 2
0x14003d254  cmp     r14, rsi
0x14003d257  jnb     short loc_14003D23F
0x14003d259  jmp     short loc_14003D264
0x14003d25b  xor     edi, edi
0x14003d25d  mov     rbx, [rsp+58h+arg_8]
0x14003d262  mov     esi, edi
0x14003d264  test    rbx, rbx
0x14003d267  jz      short loc_14003D272
0x14003d269  mov     rcx, rbx; hLibModule
0x14003d26c  call    cs:__imp_FreeLibrary
0x14003d272  mov     rax, rsi
0x14003d275  mov     rbx, [rsp+58h+arg_0]
0x14003d27a  mov     rsi, [rsp+58h+arg_18]
0x14003d27f  add     rsp, 40h
0x14003d283  pop     r15
0x14003d285  pop     r14
0x14003d287  pop     rdi
0x14003d288  retn
```
