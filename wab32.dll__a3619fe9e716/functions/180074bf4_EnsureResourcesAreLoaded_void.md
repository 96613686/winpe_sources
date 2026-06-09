# EnsureResourcesAreLoaded(void)

- ea: `0x180074bf4`
- end: `0x180074dec`
- name: `?EnsureResourcesAreLoaded@@YAJXZ`
- size: `504`
- prototype: `__int64(void)`
- caller_count: `13`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180007680`
- `0x180007740`
- `0x1800077d0`
- `0x180007890`
- `0x180007930`
- `0x180007a20`
- `0x18002e8a0`
- `0x18002f1c0`
- `0x18002f240`
- `0x18003bef0`
- `0x18003dcc4`
- `0x18003fec0`
- `0x180075960`

## callees

- `0x1800045e4`
- `0x180068538`
- `0x180074bf4`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x180074ce2`
- `SHLWAPI!PathAppendW` at `0x180074ce2`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180074cc8`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180074cc8`
- `SHLWAPI!StrStrW` at `0x180074d2d`
- `SHLWAPI!StrStrW` at `0x180074d67`
- `SHLWAPI!StrStrW` at `0x180074d2d`
- `SHLWAPI!StrStrW` at `0x180074d67`
- `KERNEL32!GetModuleFileNameW` at `0x180074cb5`
- `KERNEL32!GetModuleFileNameW` at `0x180074cb5`
- `KERNEL32!LoadLibraryW` at `0x180074cf5`
- `KERNEL32!LoadLibraryW` at `0x180074cf5`
- `KERNEL32!EnterCriticalSection` at `0x180074c88`
- `KERNEL32!EnterCriticalSection` at `0x180074c88`
- `KERNEL32!LeaveCriticalSection` at `0x180074dc0`
- `KERNEL32!LeaveCriticalSection` at `0x180074dc0`
- `USER32!LoadStringW` at `0x180074d1b`
- `USER32!LoadStringW` at `0x180074d55`
- `USER32!LoadStringW` at `0x180074d8b`
- `USER32!LoadStringW` at `0x180074d1b`
- `USER32!LoadStringW` at `0x180074d55`
- `USER32!LoadStringW` at `0x180074d8b`

## string_xrefs

- `0x180074cd6`: `wab32res.dll`

## pseudocode

```c
__int64 EnsureResourcesAreLoaded(void)
{
  unsigned int v0; // ebx
  HMODULE LibraryW; // rax
  unsigned int i; // ebx
  UINT uID[2]; // [rsp+20h] [rbp-E0h]
  LPWSTR lpBuffer; // [rsp+28h] [rbp-D8h]
  int cchBufferMax[2]; // [rsp+30h] [rbp-D0h]
  int v7; // [rsp+38h] [rbp-C8h]
  __int64 *v8; // [rsp+40h] [rbp-C0h]
  __int64 v9; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+50h] [rbp-B0h]
  __int64 *v11; // [rsp+58h] [rbp-A8h]
  __int64 v12; // [rsp+60h] [rbp-A0h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(Filename, 0, 0x208u);
  uID[0] = 4035;
  *(_QWORD *)cchBufferMax = 32;
  lpBuffer = &szResourceDNByLN;
  v8 = szResourceDNByCommaLN;
  v9 = 32;
  v12 = 32;
  v11 = szResourceDNByFN;
  v7 = 4037;
  v10 = 4036;
  EnterCriticalSection(&csLoadResourceLibrary);
  if ( hinstMapiX )
  {
LABEL_11:
    v0 = 0;
    goto LABEL_12;
  }
  v0 = -2147418113;
  if ( GetModuleFileNameW(hinstMapiXWAB, Filename, 0x104u) )
  {
    if ( PathRemoveFileSpecW(Filename) )
    {
      if ( PathAppendW(Filename, L"wab32res.dll") )
      {
        LibraryW = LoadLibraryW(Filename);
        if ( LibraryW )
        {
          hinstMapiX = LibraryW;
          LoadStringW(LibraryW, 0xFC2u, Filename, 260);
          bDNisByLN = StrStrW(Filename, L"1") != 0;
          LoadStringW(hinstMapiX, 0x10DCu, Filename, 260);
          StrStrW(Filename, L"1");
          for ( i = 0; i < 3; ++i )
          {
            if ( !LoadStringW(hinstMapiX, uID[6 * i], *(LPWSTR *)&cchBufferMax[6 * i - 2], cchBufferMax[6 * i]) )
              StringCchCopyW(
                *(unsigned __int16 **)&cchBufferMax[6 * i - 2],
                *(_QWORD *)&cchBufferMax[6 * i],
                L"%1% %2% %3");
          }
          InitCommonControlLib();
          goto LABEL_11;
        }
      }
    }
  }
LABEL_12:
  LeaveCriticalSection(&csLoadResourceLibrary);
  return v0;
}

```

## disassembly

```asm
0x180074bf4  mov     [rsp-8+arg_0], rbx
0x180074bf9  mov     [rsp-8+arg_8], rdi
0x180074bfe  push    rbp
0x180074bff  lea     rbp, [rsp-190h]
0x180074c07  sub     rsp, 290h
0x180074c0e  mov     rax, cs:__security_cookie
0x180074c15  xor     rax, rsp
0x180074c18  mov     [rbp+190h+var_10], rax
0x180074c1f  xor     edx, edx; Val
0x180074c21  lea     rcx, [rsp+290h+Filename]; void *
0x180074c26  mov     r8d, 208h; Size
0x180074c2c  call    memset_0
0x180074c31  mov     ecx, 20h ; ' '
0x180074c36  mov     [rsp+290h+uID], 0FC3h
0x180074c3e  lea     rax, szResourceDNByLN
0x180074c45  mov     qword ptr [rsp+290h+cchBufferMax], rcx
0x180074c4a  mov     [rsp+290h+lpBuffer], rax
0x180074c4f  lea     rax, szResourceDNByCommaLN
0x180074c56  mov     [rsp+290h+var_250], rax
0x180074c5b  lea     rax, szResourceDNByFN
0x180074c62  mov     [rsp+290h+var_248], rcx
0x180074c67  mov     [rsp+290h+var_230], rcx
0x180074c6c  lea     rcx, ?csLoadResourceLibrary@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180074c73  mov     [rsp+290h+var_238], rax
0x180074c78  mov     [rsp+290h+var_258], 0FC5h
0x180074c80  mov     [rsp+290h+var_240], 0FC4h
0x180074c88  call    cs:__imp_EnterCriticalSection
0x180074c8e  cmp     cs:hinstMapiX, 0
0x180074c96  jnz     loc_180074DB7
0x180074c9c  mov     rcx, cs:hinstMapiXWAB; hModule
0x180074ca3  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180074ca8  mov     edi, 104h
0x180074cad  mov     ebx, 8000FFFFh
0x180074cb2  mov     r8d, edi; nSize
0x180074cb5  call    cs:__imp_GetModuleFileNameW
0x180074cbb  test    eax, eax
0x180074cbd  jz      loc_180074DB9
0x180074cc3  lea     rcx, [rsp+290h+Filename]; pszPath
0x180074cc8  call    cs:__imp_PathRemoveFileSpecW
0x180074cce  test    eax, eax
0x180074cd0  jz      loc_180074DB9
0x180074cd6  lea     rdx, aWab32resDll; "wab32res.dll"
0x180074cdd  lea     rcx, [rsp+290h+Filename]; pszPath
0x180074ce2  call    cs:__imp_PathAppendW
0x180074ce8  test    eax, eax
0x180074cea  jz      loc_180074DB9
0x180074cf0  lea     rcx, [rsp+290h+Filename]; lpLibFileName
0x180074cf5  call    cs:__imp_LoadLibraryW
0x180074cfb  test    rax, rax
0x180074cfe  jz      loc_180074DB9
0x180074d04  mov     r9d, edi; cchBufferMax
0x180074d07  mov     cs:hinstMapiX, rax
0x180074d0e  lea     r8, [rsp+290h+Filename]; lpBuffer
0x180074d13  mov     edx, 0FC2h; uID
0x180074d18  mov     rcx, rax; hInstance
0x180074d1b  call    cs:__imp_LoadStringW
0x180074d21  lea     rdx, pszSrch; "1"
0x180074d28  lea     rcx, [rsp+290h+Filename]; pszFirst
0x180074d2d  call    cs:__imp_StrStrW
0x180074d33  xor     ecx, ecx
0x180074d35  lea     r8, [rsp+290h+Filename]; lpBuffer
0x180074d3a  test    rax, rax
0x180074d3d  mov     r9d, edi; cchBufferMax
0x180074d40  mov     edx, 10DCh; uID
0x180074d45  setnz   cl
0x180074d48  mov     cs:bDNisByLN, ecx
0x180074d4e  mov     rcx, cs:hinstMapiX; hInstance
0x180074d55  call    cs:__imp_LoadStringW
0x180074d5b  lea     rdx, pszSrch; "1"
0x180074d62  lea     rcx, [rsp+290h+Filename]; pszFirst
0x180074d67  call    cs:__imp_StrStrW
0x180074d6d  xor     ebx, ebx
0x180074d6f  mov     rcx, cs:hinstMapiX; hInstance
0x180074d76  movsxd  rax, ebx
0x180074d79  lea     rdi, [rax+rax*2]
0x180074d7d  mov     r9d, [rsp+rdi*8+290h+cchBufferMax]; cchBufferMax
0x180074d82  mov     r8, [rsp+rdi*8+290h+lpBuffer]; lpBuffer
0x180074d87  mov     edx, [rsp+rdi*8+290h+uID]; uID
0x180074d8b  call    cs:__imp_LoadStringW
0x180074d91  test    eax, eax
0x180074d93  jnz     short loc_180074DAB
0x180074d95  mov     rdx, qword ptr [rsp+rdi*8+290h+cchBufferMax]; unsigned __int64
0x180074d9a  lea     r8, a123; "%1% %2% %3"
0x180074da1  mov     rcx, [rsp+rdi*8+290h+lpBuffer]; unsigned __int16 *
0x180074da6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180074dab  inc     ebx
0x180074dad  cmp     ebx, 3
0x180074db0  jb      short loc_180074D6F
0x180074db2  call    ?InitCommonControlLib@@YAHXZ; InitCommonControlLib(void)
0x180074db7  xor     ebx, ebx
0x180074db9  lea     rcx, ?csLoadResourceLibrary@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180074dc0  call    cs:__imp_LeaveCriticalSection
0x180074dc6  mov     eax, ebx
0x180074dc8  mov     rcx, [rbp+190h+var_10]
0x180074dcf  xor     rcx, rsp; StackCookie
0x180074dd2  call    __security_check_cookie
0x180074dd7  lea     r11, [rsp+290h+var_s0]
0x180074ddf  mov     rbx, [r11+10h]
0x180074de3  mov     rdi, [r11+18h]
0x180074de7  mov     rsp, r11
0x180074dea  pop     rbp
0x180074deb  retn
```
