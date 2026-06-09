# CFmtConv::LoadCodecs(void)

- ea: `0x1800a64c8`
- end: `0x1800a66bf`
- name: `?LoadCodecs@CFmtConv@@QEAAXXZ`
- size: `503`
- prototype: `void __fastcall(CFmtConv *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a60ac`

## callees

- `0x180013ec0`
- `0x180079e30`
- `0x1800a64c8`
- `0x1800a72a4`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800a652a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800a652a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800a6513`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800a6513`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800a65e8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800a65e8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRelativePathToW` at `0x1800a660f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRelativePathToW` at `0x1800a660f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800a661f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800a661f`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverAddW` at `0x1800a664e`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverAddW` at `0x1800a664e`

## pseudocode

```c
void __fastcall CFmtConv::LoadCodecs(CFmtConv *this)
{
  __int64 i; // rbx
  __int64 v3; // rcx
  char *v4; // r14
  HMODULE LibraryW; // rax
  MMRESULT v6; // eax
  LPCWSTR pszTo; // [rsp+30h] [rbp-D0h] BYREF
  struct IEnumSpObjectTokens *v8; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v10[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Buffer[264]; // [rsp+470h] [rbp+370h] BYREF

  v8 = 0;
  _o_wcscpy_s(v10, 260, L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Speech_OneCore");
  _o_wcscat_s(v10, 260, L"\\Codecs");
  *((_DWORD *)this + 264) = 0;
  if ( (int)SpEnumTokens(v10, 0, 0, &v8) >= 0 )
  {
    for ( i = 0; (unsigned int)i < 0x14; i = (unsigned int)(i + 1) )
    {
      v9 = 0;
      if ( ((unsigned int (__fastcall *)(struct IEnumSpObjectTokens *, _QWORD, __int64 *))v8->lpVtbl->Item)(
             v8,
             (unsigned int)i,
             &v9) )
      {
        break;
      }
      v3 = v9;
      v4 = (char *)this + 8 * i;
      *((_QWORD *)v4 + 112) = 0;
      *((_QWORD *)v4 + 92) = 0;
      if ( v3 )
      {
        pszTo = 0;
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPCWSTR *))(*(_QWORD *)v3 + 48LL))(v3, L"file", &pszTo) >= 0 )
        {
          GetCurrentDirectoryW(0x104u, Buffer);
          if ( PathRelativePathToW(pszPath, Buffer, 0x10u, pszTo, 0x80u) )
          {
            LibraryW = LoadLibraryW(pszTo);
            *((_QWORD *)this + i + 92) = LibraryW;
            if ( LibraryW )
            {
              v6 = acmDriverAddW((LPHACMDRIVERID)v4 + 112, LibraryW, (LPARAM)pszPath, 0, 9u);
              if ( v6 )
                DoTraceMessage(2, "Failure adding ACM Driver for %S (%d)", pszPath, v6);
            }
            else
            {
              DoTraceMessage(2, "Error loading codec %S", pszTo);
            }
          }
        }
      }
    }
    *((_DWORD *)this + 264) = i;
  }
}

```

## disassembly

```asm
0x1800a64c8  mov     [rsp-8+arg_8], rbx
0x1800a64cd  mov     [rsp-8+arg_10], rsi
0x1800a64d2  push    rbp
0x1800a64d3  push    rdi
0x1800a64d4  push    r14
0x1800a64d6  lea     rbp, [rsp-590h]
0x1800a64de  sub     rsp, 690h
0x1800a64e5  mov     rax, cs:__security_cookie
0x1800a64ec  xor     rax, rsp
0x1800a64ef  mov     [rbp+5A0h+var_20], rax
0x1800a64f6  mov     rdi, rcx
0x1800a64f9  mov     [rsp+6A0h+var_668], 0
0x1800a6502  lea     rcx, [rsp+6A0h+var_650]
0x1800a6507  mov     edx, 104h
0x1800a650c  lea     r8, aHkeyLocalMachi_10; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800a6513  call    cs:__imp__o_wcscpy_s
0x1800a6519  lea     r8, aCodecs; "\\Codecs"
0x1800a6520  mov     edx, 104h
0x1800a6525  lea     rcx, [rsp+6A0h+var_650]
0x1800a652a  call    cs:__imp__o_wcscat_s
0x1800a6530  lea     r9, [rsp+6A0h+var_668]; struct IEnumSpObjectTokens **
0x1800a6535  mov     dword ptr [rdi+420h], 0
0x1800a653f  xor     r8d, r8d; unsigned __int16 *
0x1800a6542  lea     rcx, [rsp+6A0h+var_650]; unsigned __int16 *
0x1800a6547  xor     edx, edx; unsigned __int16 *
0x1800a6549  call    ?SpEnumTokens@@YAJPEBG00PEAPEAUIEnumSpObjectTokens@@@Z; SpEnumTokens(ushort const *,ushort const *,ushort const *,IEnumSpObjectTokens * *)
0x1800a654e  test    eax, eax
0x1800a6550  js      loc_1800A6698
0x1800a6556  xor     ebx, ebx
0x1800a6558  cmp     ebx, 14h
0x1800a655b  jnb     loc_1800A6692
0x1800a6561  mov     rcx, [rsp+6A0h+var_668]
0x1800a6566  lea     r8, [rsp+6A0h+var_660]
0x1800a656b  mov     [rsp+6A0h+var_660], 0
0x1800a6574  mov     edx, ebx
0x1800a6576  mov     rax, [rcx]
0x1800a6579  mov     rax, [rax+38h]
0x1800a657d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6582  test    eax, eax
0x1800a6584  jnz     loc_1800A6692
0x1800a658a  mov     rcx, [rsp+6A0h+var_660]
0x1800a658f  lea     r14, [rdi+rbx*8]
0x1800a6593  mov     qword ptr [r14+380h], 0
0x1800a659e  mov     qword ptr [rdi+rbx*8+2E0h], 0
0x1800a65aa  test    rcx, rcx
0x1800a65ad  jz      loc_1800A668B
0x1800a65b3  mov     [rsp+6A0h+pszTo], 0
0x1800a65bc  lea     r8, [rsp+6A0h+pszTo]
0x1800a65c1  mov     rax, [rcx]
0x1800a65c4  lea     rdx, aFile; "file"
0x1800a65cb  mov     rax, [rax+30h]
0x1800a65cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a65d4  test    eax, eax
0x1800a65d6  js      loc_1800A668B
0x1800a65dc  lea     rdx, [rbp+5A0h+Buffer]; lpBuffer
0x1800a65e3  mov     ecx, 104h; nBufferLength
0x1800a65e8  call    cs:__imp_GetCurrentDirectoryW
0x1800a65ee  mov     r9, [rsp+6A0h+pszTo]; pszTo
0x1800a65f3  lea     rdx, [rbp+5A0h+Buffer]; pszFrom
0x1800a65fa  mov     r8d, 10h; dwAttrFrom
0x1800a6600  mov     [rsp+6A0h+dwAttrTo], 80h; dwAttrTo
0x1800a6608  lea     rcx, [rbp+5A0h+pszPath]; pszPath
0x1800a660f  call    cs:__imp_PathRelativePathToW
0x1800a6615  cmp     eax, 1
0x1800a6618  jnz     short loc_1800A668B
0x1800a661a  mov     rcx, [rsp+6A0h+pszTo]; lpLibFileName
0x1800a661f  call    cs:__imp_LoadLibraryW
0x1800a6625  mov     [rdi+rbx*8+2E0h], rax
0x1800a662d  test    rax, rax
0x1800a6630  jz      short loc_1800A6675
0x1800a6632  xor     r9d, r9d; dwPriority
0x1800a6635  mov     [rsp+6A0h+dwAttrTo], 9; fdwAdd
0x1800a663d  lea     r8, [rbp+5A0h+pszPath]; lParam
0x1800a6644  mov     rdx, rax; hinstModule
0x1800a6647  lea     rcx, [r14+380h]; phadid
0x1800a664e  call    cs:__imp_acmDriverAddW
0x1800a6654  test    eax, eax
0x1800a6656  jz      short loc_1800A668B
0x1800a6658  mov     r9d, eax
0x1800a665b  lea     r8, [rbp+5A0h+pszPath]
0x1800a6662  lea     rdx, aFailureAddingA; "Failure adding ACM Driver for %S (%d)"
0x1800a6669  mov     ecx, 2; int
0x1800a666e  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800a6673  jmp     short loc_1800A668B
0x1800a6675  mov     r8, [rsp+6A0h+pszTo]
0x1800a667a  lea     rdx, aErrorLoadingCo; "Error loading codec %S"
0x1800a6681  mov     ecx, 2; int
0x1800a6686  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1800a668b  inc     ebx
0x1800a668d  jmp     loc_1800A6558
0x1800a6692  mov     [rdi+420h], ebx
0x1800a6698  mov     rcx, [rbp+5A0h+var_20]
0x1800a669f  xor     rcx, rsp; StackCookie
0x1800a66a2  call    __security_check_cookie
0x1800a66a7  lea     r11, [rsp+6A0h+var_10]
0x1800a66af  mov     rbx, [r11+28h]
0x1800a66b3  mov     rsi, [r11+30h]
0x1800a66b7  mov     rsp, r11
0x1800a66ba  pop     r14
0x1800a66bc  pop     rdi
0x1800a66bd  pop     rbp
0x1800a66be  retn
```
