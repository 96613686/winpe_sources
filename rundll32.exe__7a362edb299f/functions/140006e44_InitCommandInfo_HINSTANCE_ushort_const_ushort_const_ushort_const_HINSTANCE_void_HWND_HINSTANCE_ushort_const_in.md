# _InitCommandInfo(HINSTANCE__ *,ushort const *,ushort const *,ushort const *,HINSTANCE__ * *,void (**)(HWND__ *,HINSTANCE__ *,ushort const *,int),char * *)

- ea: `0x140006e44`
- end: `0x140007090`
- name: `?_InitCommandInfo@@YAHPEAUHINSTANCE__@@PEBG11PEAPEAU1@PEAP6AXPEAUHWND__@@01H@ZPEAPEAD@Z`
- size: `588`
- prototype: `__int64 __fastcall(HINSTANCE, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HINSTANCE *, void (**)(HWND, HINSTANCE, const unsigned __int16 *, int), char **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007798`

## callees

- `0x1400015a0`
- `0x140006a7c`
- `0x140006d14`
- `0x140006e44`
- `0x14000737c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006eb4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006eb4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000705b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000705b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ec8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140006fde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140006fde`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006f38`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006f38`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140006fcf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140007015`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140006fcf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140007015`

## pseudocode

```c
__int64 __fastcall _InitCommandInfo(
        HINSTANCE a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HINSTANCE *a5,
        void (**a6)(HWND, HINSTANCE, const unsigned __int16 *, int),
        char **a7)
{
  HINSTANCE v9; // rbp
  HMODULE Library; // rax
  HMODULE v12; // r15
  unsigned int v13; // ebx
  DWORD LastError; // eax
  DWORD v15; // eax
  void (*CommandFunction)(HWND, HINSTANCE, const unsigned __int16 *, int); // r12
  __int64 v17; // rax
  int v18; // r14d
  CHAR *v19; // rdi
  void (**v20)(HWND, HINSTANCE, const unsigned __int16 *, int); // rax
  unsigned int v21; // esi
  int cbMultiByte[2]; // [rsp+40h] [rbp-278h] BYREF
  char **v24; // [rsp+48h] [rbp-270h]
  void (**v25)(HWND, HINSTANCE, const unsigned __int16 *, int); // [rsp+50h] [rbp-268h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-258h] BYREF

  v9 = g_hInstance;
  v24 = a7;
  v25 = a6;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  Library = LoadLibraryExW(a2, 0, 8u);
  v12 = Library;
  if ( Library )
  {
    cbMultiByte[0] = 0;
    CommandFunction = _FindCommandFunction(Library, a3, cbMultiByte);
    if ( CommandFunction )
    {
      if ( !cbMultiByte[0] || !a4 || !*a4 )
        goto LABEL_16;
      v17 = -1;
      do
        ++v17;
      while ( a4[v17] );
      v18 = v17 + 1;
      cbMultiByte[0] = WideCharToMultiByte(0, 0x400u, a4, v17 + 1, 0, 0, 0, 0);
      v19 = (CHAR *)LocalAlloc(0, cbMultiByte[0]);
      if ( v19 )
      {
        WideCharToMultiByte(0, 0x400u, a4, v18, v19, cbMultiByte[0], 0, 0);
        *v24 = v19;
LABEL_16:
        v20 = v25;
        v13 = 1;
        *a5 = v12;
        *v20 = CommandFunction;
        return v13;
      }
      v21 = 768;
      a3 = 0;
    }
    else
    {
      v21 = 1024;
      a4 = a2;
    }
    _DisplayErrorMessage(v9, v21, a4, a3);
    FreeLibrary(v12);
    return 0;
  }
  v13 = 0;
  LastError = GetLastError();
  if ( LastError == 193 )
  {
    if ( (unsigned int)_TryWow64Scenario(a2) )
      return v13;
    *(_QWORD *)cbMultiByte = a2;
    v15 = FormatMessageW(0x3000u, 0, 0xC1u, 0, Buffer, 0x104u, (va_list *)cbMultiByte);
  }
  else
  {
    v15 = FormatMessageW(0x1200u, 0, LastError, 0, Buffer, 0x104u, 0);
  }
  if ( v15 )
    _DisplayErrorMessage(v9, 0x401u, a2, Buffer);
  return v13;
}

```

## disassembly

```asm
0x140006e44  mov     [rsp+arg_0], rbx
0x140006e49  push    rbp
0x140006e4a  push    rsi
0x140006e4b  push    rdi
0x140006e4c  push    r12
0x140006e4e  push    r13
0x140006e50  push    r14
0x140006e52  push    r15
0x140006e54  sub     rsp, 280h
0x140006e5b  mov     rax, cs:__security_cookie
0x140006e62  xor     rax, rsp
0x140006e65  mov     [rsp+2B8h+var_48], rax
0x140006e6d  mov     rax, [rsp+2B8h+arg_28]
0x140006e75  xor     esi, esi
0x140006e77  mov     rcx, [rsp+2B8h+arg_30]
0x140006e7f  mov     rdi, rdx
0x140006e82  mov     r13, [rsp+2B8h+arg_20]
0x140006e8a  mov     r14, r8
0x140006e8d  mov     rbp, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x140006e94  xor     edx, edx; hFile
0x140006e96  mov     [rsp+2B8h+var_270], rcx
0x140006e9b  lea     r8d, [rsi+8]; dwFlags
0x140006e9f  mov     rbx, r9
0x140006ea2  mov     [rsp+2B8h+var_268], rax
0x140006ea7  mov     [r13+0], rsi
0x140006eab  mov     [rax], rsi
0x140006eae  mov     [rcx], rsi
0x140006eb1  mov     rcx, rdi; lpLibFileName
0x140006eb4  call    cs:__imp_LoadLibraryExW
0x140006eba  mov     r15, rax
0x140006ebd  test    rax, rax
0x140006ec0  jnz     loc_140006F60
0x140006ec6  mov     ebx, esi
0x140006ec8  call    cs:__imp_GetLastError
0x140006ece  mov     r14d, 0C1h
0x140006ed4  cmp     eax, r14d
0x140006ed7  jnz     short loc_140006F14
0x140006ed9  mov     rcx, rdi; unsigned __int16 *
0x140006edc  call    ?_TryWow64Scenario@@YAHPEBG@Z; _TryWow64Scenario(ushort const *)
0x140006ee1  test    eax, eax
0x140006ee3  jnz     loc_140007063
0x140006ee9  lea     rax, [rsp+2B8h+cbMultiByte]
0x140006eee  mov     qword ptr [rsp+2B8h+cbMultiByte], rdi
0x140006ef3  mov     [rsp+2B8h+Arguments], rax
0x140006ef8  mov     r8d, r14d
0x140006efb  lea     rax, [rsp+2B8h+Buffer]
0x140006f00  mov     [rsp+2B8h+nSize], 104h
0x140006f08  mov     [rsp+2B8h+lpBuffer], rax
0x140006f0d  mov     ecx, 3000h
0x140006f12  jmp     short loc_140006F33
0x140006f14  mov     [rsp+2B8h+Arguments], rsi; Arguments
0x140006f19  lea     rcx, [rsp+2B8h+Buffer]
0x140006f1e  mov     [rsp+2B8h+nSize], 104h; nSize
0x140006f26  mov     r8d, eax; dwMessageId
0x140006f29  mov     [rsp+2B8h+lpBuffer], rcx; lpBuffer
0x140006f2e  mov     ecx, 1200h; dwFlags
0x140006f33  xor     r9d, r9d; dwLanguageId
0x140006f36  xor     edx, edx; lpSource
0x140006f38  call    cs:__imp_FormatMessageW
0x140006f3e  test    eax, eax
0x140006f40  jz      loc_140007063
0x140006f46  lea     r9, [rsp+2B8h+Buffer]; unsigned __int16 *
0x140006f4b  mov     r8, rdi; unsigned __int16 *
0x140006f4e  mov     edx, 401h; unsigned int
0x140006f53  mov     rcx, rbp; hInstance
0x140006f56  call    ?_DisplayErrorMessage@@YAXPEAUHINSTANCE__@@IPEBG1@Z; _DisplayErrorMessage(HINSTANCE__ *,uint,ushort const *,ushort const *)
0x140006f5b  jmp     loc_140007063
0x140006f60  lea     r8, [rsp+2B8h+cbMultiByte]; int *
0x140006f65  mov     [rsp+2B8h+cbMultiByte], esi
0x140006f69  mov     rdx, r14; lpWideCharStr
0x140006f6c  mov     rcx, r15; hModule
0x140006f6f  call    ?_FindCommandFunction@@YAP6AXPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z12PEAH@Z; _FindCommandFunction(HINSTANCE__ *,ushort const *,int *)
0x140006f74  mov     r12, rax
0x140006f77  test    rax, rax
0x140006f7a  jz      loc_140007040
0x140006f80  cmp     [rsp+2B8h+cbMultiByte], esi
0x140006f84  jz      loc_140007023
0x140006f8a  test    rbx, rbx
0x140006f8d  jz      loc_140007023
0x140006f93  cmp     [rbx], si
0x140006f96  jz      loc_140007023
0x140006f9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006fa0  inc     rax
0x140006fa3  cmp     [rbx+rax*2], si
0x140006fa7  jnz     short loc_140006FA0
0x140006fa9  mov     [rsp+2B8h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x140006fae  lea     r14d, [rax+1]
0x140006fb2  mov     [rsp+2B8h+Arguments], rsi; lpDefaultChar
0x140006fb7  mov     r9d, r14d; cchWideChar
0x140006fba  mov     [rsp+2B8h+nSize], esi; cbMultiByte
0x140006fbe  mov     r8, rbx; lpWideCharStr
0x140006fc1  mov     [rsp+2B8h+lpBuffer], rsi; lpMultiByteStr
0x140006fc6  xor     ecx, ecx; CodePage
0x140006fc8  mov     esi, 400h
0x140006fcd  mov     edx, esi; dwFlags
0x140006fcf  call    cs:__imp_WideCharToMultiByte
0x140006fd5  movsxd  rdx, eax; uBytes
0x140006fd8  xor     ecx, ecx; uFlags
0x140006fda  mov     [rsp+2B8h+cbMultiByte], eax
0x140006fde  call    cs:__imp_LocalAlloc
0x140006fe4  mov     rdi, rax
0x140006fe7  test    rax, rax
0x140006fea  jz      short loc_140007036
0x140006fec  mov     eax, [rsp+2B8h+cbMultiByte]
0x140006ff0  mov     r9d, r14d; cchWideChar
0x140006ff3  mov     [rsp+2B8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140006ffc  mov     r8, rbx; lpWideCharStr
0x140006fff  mov     [rsp+2B8h+Arguments], 0; lpDefaultChar
0x140007008  mov     edx, esi; dwFlags
0x14000700a  mov     [rsp+2B8h+nSize], eax; cbMultiByte
0x14000700e  xor     ecx, ecx; CodePage
0x140007010  mov     [rsp+2B8h+lpBuffer], rdi; lpMultiByteStr
0x140007015  call    cs:__imp_WideCharToMultiByte
0x14000701b  mov     rax, [rsp+2B8h+var_270]
0x140007020  mov     [rax], rdi
0x140007023  mov     rax, [rsp+2B8h+var_268]
0x140007028  mov     ebx, 1
0x14000702d  mov     [r13+0], r15
0x140007031  mov     [rax], r12
0x140007034  jmp     short loc_140007063
0x140007036  mov     esi, 300h
0x14000703b  xor     r14d, r14d
0x14000703e  jmp     short loc_140007048
0x140007040  mov     esi, 400h
0x140007045  mov     rbx, rdi
0x140007048  mov     r9, r14; unsigned __int16 *
0x14000704b  mov     r8, rbx; unsigned __int16 *
0x14000704e  mov     edx, esi; unsigned int
0x140007050  mov     rcx, rbp; hInstance
0x140007053  call    ?_DisplayErrorMessage@@YAXPEAUHINSTANCE__@@IPEBG1@Z; _DisplayErrorMessage(HINSTANCE__ *,uint,ushort const *,ushort const *)
0x140007058  mov     rcx, r15; hLibModule
0x14000705b  call    cs:__imp_FreeLibrary
0x140007061  xor     ebx, ebx
0x140007063  mov     eax, ebx
0x140007065  mov     rcx, [rsp+2B8h+var_48]
0x14000706d  xor     rcx, rsp; StackCookie
0x140007070  call    __security_check_cookie
0x140007075  mov     rbx, [rsp+2B8h+arg_0]
0x14000707d  add     rsp, 280h
0x140007084  pop     r15
0x140007086  pop     r14
0x140007088  pop     r13
0x14000708a  pop     r12
0x14000708c  pop     rdi
0x14000708d  pop     rsi
0x14000708e  pop     rbp
0x14000708f  retn
```
