# InitLocStrings(void)

- ea: `0x18002e7b8`
- end: `0x18002e9c0`
- name: `?InitLocStrings@@YAJXZ`
- size: `520`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180039100`

## callees

- `0x180003ac0`
- `0x180018138`
- `0x18001d9a0`
- `0x18002e7b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8d5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e86a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002e86a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e81a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002e81a`

## string_xrefs

- `0x18002e927`: `InitLocStrings: Failed to load configuration strings. Using default hardcoded strings. Error:0x%08X\n`
- `0x1800678c9`: `InitLocStrings: Failed to load configuration strings. Using default hardcoded strings. Error:0x%08X\n`

## pseudocode

```c
__int64 InitLocStrings(void)
{
  unsigned int v0; // ebx
  __int64 i; // rdx
  HMODULE v2; // rcx
  UINT v3; // r14d
  unsigned int j; // edi
  unsigned int StringW; // eax
  signed int LastError; // eax
  signed int v7; // eax
  HMODULE phModule; // [rsp+70h] [rbp+8h] BYREF

  v0 = 0;
  phModule = 0;
  for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
    (&g_wszConfigFlagPtr)[i] = (unsigned __int16 * near *)(&g_wszLocalizedStrings
                                                         + 128 * (unsigned __int64)(unsigned int)i);
  g_pwszSuccessMsg = (__int64)&qword_1800A5130;
  if ( GetModuleHandleExW(2u, L"w32time", &phModule) && (v2 = phModule) != 0 )
  {
    v3 = 251;
    for ( j = 0; j < 6; ++j )
    {
      StringW = LoadStringW(v2, v3, &g_wszLocalizedStrings + 128 * (unsigned __int64)j, 128);
      if ( !StringW )
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError > 0 )
          v0 = (unsigned __int16)LastError | 0x80070000;
        if ( (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(L"LoadStringW %d failed with error 0x%08x\n", j, v0);
        break;
      }
      if ( StringW >= 0x80 )
      {
        v0 = -2147418113;
        break;
      }
      ++v3;
      v2 = phModule;
    }
  }
  else
  {
    v7 = GetLastError();
    v0 = v7;
    if ( v7 > 0 )
      v0 = (unsigned __int16)v7 | 0x80070000;
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"GetModuleHandleExW 0x%08x\n", v0);
  }
  if ( v0 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(
        L"InitLocStrings: Failed to load configuration strings. Using default hardcoded strings. Error:0x%08X\n",
        v0);
    StringCchPrintfW(&g_wszLocalizedStrings, 0x80u, L"Undefined or not used");
    StringCchPrintfW(&qword_1800A4D30, 0x80u, L"Default");
    StringCchPrintfW(&qword_1800A4E30, 0x80u, L"Local");
    StringCchPrintfW(&qword_1800A4F30, 0x80u, L"Policy");
    StringCchPrintfW(&qword_1800A5030, 0x80u, L"Reserved");
    StringCchPrintfW(&qword_1800A5130, 0x80u, L"Success");
  }
  return v0;
}

```

## disassembly

```asm
0x18002e7b8  push    rbx
0x18002e7ba  push    rsi
0x18002e7bb  push    rdi
0x18002e7bc  push    r12
0x18002e7be  push    r14
0x18002e7c0  push    r15
0x18002e7c2  sub     rsp, 38h
0x18002e7c6  xor     ebx, ebx
0x18002e7c8  mov     [rsp+68h+var_48], ebx
0x18002e7cc  mov     [rsp+68h+phModule], rbx
0x18002e7d1  xor     edx, edx
0x18002e7d3  lea     r15, ?g_wszLocalizedStrings@@3PAY0IA@GA; ushort (near * g_wszLocalizedStrings)[128]
0x18002e7da  mov     [rsp+68h+var_44], edx
0x18002e7de  cmp     edx, 5
0x18002e7e1  jnb     short loc_18002E7FB
0x18002e7e3  mov     eax, edx
0x18002e7e5  shl     rax, 8
0x18002e7e9  add     rax, r15
0x18002e7ec  lea     r8, ?g_wszConfigFlagPtr@@3PAPEAGA; ushort * near * g_wszConfigFlagPtr
0x18002e7f3  mov     [r8+rdx*8], rax
0x18002e7f7  inc     edx
0x18002e7f9  jmp     short loc_18002E7DA
0x18002e7fb  lea     r12, qword_1800A5130
0x18002e802  mov     cs:g_pwszSuccessMsg, r12
0x18002e809  lea     r8, [rsp+68h+phModule]; phModule
0x18002e80e  lea     rdx, ModuleName; "w32time"
0x18002e815  mov     ecx, 2; dwFlags
0x18002e81a  call    cs:__imp_GetModuleHandleExW
0x18002e821  nop     dword ptr [rax+rax+00h]
0x18002e826  test    eax, eax
0x18002e828  jz      loc_18002E8D5
0x18002e82e  mov     rcx, [rsp+68h+phModule]; hInstance
0x18002e833  test    rcx, rcx
0x18002e836  jz      loc_18002E8D5
0x18002e83c  mov     r14d, 0FBh
0x18002e842  xor     edi, edi
0x18002e844  lea     esi, [r14-7Bh]
0x18002e848  mov     [rsp+68h+var_3C], edi
0x18002e84c  mov     [rsp+68h+var_40], r14d
0x18002e851  cmp     edi, 6
0x18002e854  jnb     loc_18002E912
0x18002e85a  mov     r8d, edi
0x18002e85d  shl     r8, 8
0x18002e861  add     r8, r15; lpBuffer
0x18002e864  mov     r9d, esi; cchBufferMax
0x18002e867  mov     edx, r14d; uID
0x18002e86a  call    cs:__imp_LoadStringW
0x18002e871  nop     dword ptr [rax+rax+00h]
0x18002e876  test    eax, eax
0x18002e878  jnz     short loc_18002E8B7
0x18002e87a  call    cs:__imp_GetLastError
0x18002e881  nop     dword ptr [rax+rax+00h]
0x18002e886  mov     ebx, eax
0x18002e888  test    eax, eax
0x18002e88a  jle     short loc_18002E895
0x18002e88c  movzx   ebx, ax
0x18002e88f  or      ebx, 80070000h
0x18002e895  mov     [rsp+68h+var_48], ebx
0x18002e899  xor     ecx, ecx
0x18002e89b  call    FileLogAllowEntry
0x18002e8a0  test    al, al
0x18002e8a2  jz      short loc_18002E912
0x18002e8a4  mov     r8d, ebx
0x18002e8a7  mov     edx, edi
0x18002e8a9  lea     rcx, aLoadstringwDFa; "LoadStringW %d failed with error 0x%08x"...
0x18002e8b0  call    FileLogAdd
0x18002e8b5  jmp     short loc_18002E912
0x18002e8b7  cmp     eax, esi
0x18002e8b9  jb      short loc_18002E8C6
0x18002e8bb  mov     ebx, 8000FFFFh
0x18002e8c0  mov     [rsp+68h+var_48], ebx
0x18002e8c4  jmp     short loc_18002E912
0x18002e8c6  inc     r14d
0x18002e8c9  inc     edi
0x18002e8cb  mov     rcx, [rsp+68h+phModule]
0x18002e8d0  jmp     loc_18002E848
0x18002e8d5  call    cs:__imp_GetLastError
0x18002e8dc  nop     dword ptr [rax+rax+00h]
0x18002e8e1  mov     ebx, eax
0x18002e8e3  test    eax, eax
0x18002e8e5  jle     short loc_18002E8F0
0x18002e8e7  movzx   ebx, ax
0x18002e8ea  or      ebx, 80070000h
0x18002e8f0  mov     [rsp+68h+var_48], ebx
0x18002e8f4  xor     ecx, ecx
0x18002e8f6  call    FileLogAllowEntry
0x18002e8fb  test    al, al
0x18002e8fd  jz      short loc_18002E90D
0x18002e8ff  mov     edx, ebx
0x18002e901  lea     rcx, aGetmodulehandl; "GetModuleHandleExW 0x%08x\n"
0x18002e908  call    FileLogAdd
0x18002e90d  mov     esi, 80h
0x18002e912  test    ebx, ebx
0x18002e914  jz      loc_18002E9AF
0x18002e91a  xor     ecx, ecx
0x18002e91c  call    FileLogAllowEntry
0x18002e921  test    al, al
0x18002e923  jz      short loc_18002E933
0x18002e925  mov     edx, ebx
0x18002e927  lea     rcx, aInitlocstrings; "InitLocStrings: Failed to load configur"...
0x18002e92e  call    FileLogAdd
0x18002e933  lea     r8, aUndefinedOrNot; "Undefined or not used"
0x18002e93a  mov     rdx, rsi; unsigned __int64
0x18002e93d  mov     rcx, r15; unsigned __int16 *
0x18002e940  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e945  lea     r8, aDefault; "Default"
0x18002e94c  mov     rdx, rsi; unsigned __int64
0x18002e94f  lea     rcx, qword_1800A4D30; unsigned __int16 *
0x18002e956  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e95b  lea     r8, aLocal; "Local"
0x18002e962  mov     rdx, rsi; unsigned __int64
0x18002e965  lea     rcx, qword_1800A4E30; unsigned __int16 *
0x18002e96c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e971  lea     r8, aPolicy; "Policy"
0x18002e978  mov     rdx, rsi; unsigned __int64
0x18002e97b  lea     rcx, qword_1800A4F30; unsigned __int16 *
0x18002e982  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e987  lea     r8, aReserved_0; "Reserved"
0x18002e98e  mov     rdx, rsi; unsigned __int64
0x18002e991  lea     rcx, qword_1800A5030; unsigned __int16 *
0x18002e998  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e99d  lea     r8, aSuccess; "Success"
0x18002e9a4  mov     rdx, rsi; unsigned __int64
0x18002e9a7  mov     rcx, r12; unsigned __int16 *
0x18002e9aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e9af  mov     eax, ebx
0x18002e9b1  add     rsp, 38h
0x18002e9b5  pop     r15
0x18002e9b7  pop     r14
0x18002e9b9  pop     r12
0x18002e9bb  pop     rdi
0x18002e9bc  pop     rsi
0x18002e9bd  pop     rbx
0x18002e9be  retn
0x1800678a7  push    rbx
0x1800678a9  push    rbp
0x1800678aa  sub     rsp, 28h
0x1800678ae  mov     rbp, rdx
0x1800678b1  mov     ebx, [rbp+20h]
0x1800678b4  test    ebx, ebx
0x1800678b6  jz      loc_180067967
0x1800678bc  xor     ecx, ecx
0x1800678be  call    FileLogAllowEntry
0x1800678c3  test    al, al
0x1800678c5  jz      short loc_1800678D6
0x1800678c7  mov     edx, ebx
0x1800678c9  lea     rcx, aInitlocstrings; "InitLocStrings: Failed to load configur"...
0x1800678d0  call    FileLogAdd
0x1800678d5  nop
0x1800678d6  lea     r8, aUndefinedOrNot; "Undefined or not used"
0x1800678dd  mov     edx, 80h; unsigned __int64
0x1800678e2  lea     rcx, ?g_wszLocalizedStrings@@3PAY0IA@GA; unsigned __int16 *
0x1800678e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800678ee  lea     r8, aDefault; "Default"
0x1800678f5  mov     edx, 80h; unsigned __int64
0x1800678fa  lea     rcx, qword_1800A4D30; unsigned __int16 *
0x180067901  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067906  lea     r8, aLocal; "Local"
0x18006790d  mov     edx, 80h; unsigned __int64
0x180067912  lea     rcx, qword_1800A4E30; unsigned __int16 *
0x180067919  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006791e  lea     r8, aPolicy; "Policy"
0x180067925  mov     edx, 80h; unsigned __int64
0x18006792a  lea     rcx, qword_1800A4F30; unsigned __int16 *
0x180067931  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067936  lea     r8, aReserved_0; "Reserved"
0x18006793d  mov     edx, 80h; unsigned __int64
0x180067942  lea     rcx, qword_1800A5030; unsigned __int16 *
0x180067949  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006794e  lea     r8, aSuccess; "Success"
0x180067955  mov     edx, 80h; unsigned __int64
0x18006795a  lea     rcx, qword_1800A5130; unsigned __int16 *
0x180067961  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067966  nop
0x180067967  add     rsp, 28h
0x18006796b  pop     rbp
0x18006796c  pop     rbx
0x18006796d  retn
```
