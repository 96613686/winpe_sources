# WofpNormalizeFilePath

- ea: `0x180036e98`
- end: `0x18003704e`
- name: `WofpNormalizeFilePath`
- size: `438`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1800366b0`

## callees

- `0x18000fd58`
- `0x1800105a0`
- `0x180036a00`
- `0x180036e98`
- `0x1800607b0`
- `0x1800607d4`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180036f38`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180036f38`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180036f5d`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180036f5d`
- `KERNEL32!HeapAlloc` at `0x180036fe6`
- `KERNEL32!HeapAlloc` at `0x180036fe6`
- `KERNEL32!GetProcessHeap` at `0x180036fd2`
- `KERNEL32!GetProcessHeap` at `0x180036fd2`

## pseudocode

```c
__int64 __fastcall WofpNormalizeFilePath(STRSAFE_PCNZWCH pszSrc, wchar_t **a2)
{
  unsigned int v2; // ebx
  STRSAFE_PCNZWCH v5; // rsi
  unsigned int i; // edi
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  size_t v9; // rdx
  WCHAR *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  SIZE_T v14; // r14
  HANDLE ProcessHeap; // rax
  wchar_t *v16; // rax
  wchar_t *v17; // rbp
  DWORD cchReturnLength[4]; // [rsp+30h] [rbp-4D8h] BYREF
  WCHAR szVolumeName[56]; // [rsp+40h] [rbp-4C8h] BYREF
  wchar_t pszDest[264]; // [rsp+B0h] [rbp-458h] BYREF
  WCHAR szVolumePathNames[264]; // [rsp+2C0h] [rbp-248h] BYREF

  v2 = 0;
  v5 = pszSrc;
  for ( i = 0; i < 2; ++i )
  {
    v7 = wcschr_0(v5 + 1, 0x5Cu);
    v5 = v7;
    if ( !v7 )
      return 2147942487LL;
  }
  v8 = v7 + 1;
  StringCchCopyW(pszDest, 0x104u, L"\\\\?\\GlobalRoot");
  StringCchCatNW(pszDest, v9, pszSrc, v8 - pszSrc);
  if ( GetVolumeNameForVolumeMountPointW(pszDest, szVolumeName, 0x32u) )
  {
    if ( GetVolumePathNamesForVolumeNameW(szVolumeName, szVolumePathNames, 0x104u, cchReturnLength)
      && szVolumePathNames[0] )
    {
      v10 = szVolumePathNames;
    }
    else
    {
      v10 = szVolumeName;
    }
  }
  else
  {
    v10 = pszDest;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( v10[v12] );
  if ( v12 && v10[v12 - 1] == 92 )
    v10[v12 - 1] = 0;
  v13 = -1;
  do
    ++v13;
  while ( v10[v13] );
  do
    ++v11;
  while ( v8[v11] );
  v14 = 2 * (v11 + v13) + 4;
  ProcessHeap = GetProcessHeap();
  v16 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v14);
  v17 = v16;
  if ( v16 )
  {
    StringCbPrintfW(v16, v14, L"%ws\\%ws", v10, v8);
    *a2 = v17;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v2;
}

```

## disassembly

```asm
0x180036e98  mov     [rsp+arg_10], rbx
0x180036e9d  push    rbp
0x180036e9e  push    rsi
0x180036e9f  push    rdi
0x180036ea0  push    r14
0x180036ea2  push    r15
0x180036ea4  sub     rsp, 4E0h
0x180036eab  mov     rax, cs:__security_cookie
0x180036eb2  xor     rax, rsp
0x180036eb5  mov     [rsp+508h+var_38], rax
0x180036ebd  xor     ebx, ebx
0x180036ebf  mov     r15, rdx
0x180036ec2  mov     rbp, rcx
0x180036ec5  mov     rsi, rcx
0x180036ec8  mov     edi, ebx
0x180036eca  lea     r14d, [rbx+5Ch]
0x180036ece  mov     edx, r14d; Ch
0x180036ed1  lea     rcx, [rsi+2]; Str
0x180036ed5  call    wcschr_0
0x180036eda  mov     rsi, rax
0x180036edd  test    rax, rax
0x180036ee0  jz      loc_180037022
0x180036ee6  inc     edi
0x180036ee8  cmp     edi, 2
0x180036eeb  jb      short loc_180036ECE
0x180036eed  mov     edi, 104h
0x180036ef2  lea     r8, aGlobalroot; "\\\\?\\GlobalRoot"
0x180036ef9  mov     edx, edi; unsigned __int64
0x180036efb  lea     rcx, [rsp+508h+pszDest]; unsigned __int16 *
0x180036f03  add     rsi, 2
0x180036f07  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036f0c  mov     r9, rsi
0x180036f0f  lea     rcx, [rsp+508h+pszDest]; pszDest
0x180036f17  sub     r9, rbp
0x180036f1a  mov     r8, rbp; pszSrc
0x180036f1d  sar     r9, 1; cchToAppend
0x180036f20  call    StringCchCatNW
0x180036f25  mov     r8d, 32h ; '2'; cchBufferLength
0x180036f2b  lea     rdx, [rsp+508h+szVolumeName]; lpszVolumeName
0x180036f30  lea     rcx, [rsp+508h+pszDest]; lpszVolumeMountPoint
0x180036f38  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180036f3f  nop     dword ptr [rax+rax+00h]
0x180036f44  test    eax, eax
0x180036f46  jz      short loc_180036F88
0x180036f48  lea     r9, [rsp+508h+cchReturnLength]; lpcchReturnLength
0x180036f4d  mov     r8d, edi; cchBufferLength
0x180036f50  lea     rdx, [rsp+508h+szVolumePathNames]; lpszVolumePathNames
0x180036f58  lea     rcx, [rsp+508h+szVolumeName]; lpszVolumeName
0x180036f5d  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180036f64  nop     dword ptr [rax+rax+00h]
0x180036f69  test    eax, eax
0x180036f6b  jz      short loc_180036F81
0x180036f6d  cmp     [rsp+508h+szVolumePathNames], bx
0x180036f75  jz      short loc_180036F81
0x180036f77  lea     rdi, [rsp+508h+szVolumePathNames]
0x180036f7f  jmp     short loc_180036F90
0x180036f81  lea     rdi, [rsp+508h+szVolumeName]
0x180036f86  jmp     short loc_180036F90
0x180036f88  lea     rdi, [rsp+508h+pszDest]
0x180036f90  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180036f94  mov     rax, rcx
0x180036f97  inc     rax
0x180036f9a  cmp     [rdi+rax*2], bx
0x180036f9e  jnz     short loc_180036F97
0x180036fa0  test    rax, rax
0x180036fa3  jz      short loc_180036FB2
0x180036fa5  cmp     [rdi+rax*2-2], r14w
0x180036fab  jnz     short loc_180036FB2
0x180036fad  mov     [rdi+rax*2-2], bx
0x180036fb2  mov     rax, rcx
0x180036fb5  inc     rax
0x180036fb8  cmp     [rdi+rax*2], bx
0x180036fbc  jnz     short loc_180036FB5
0x180036fbe  inc     rcx
0x180036fc1  cmp     [rsi+rcx*2], bx
0x180036fc5  jnz     short loc_180036FBE
0x180036fc7  add     rax, rcx
0x180036fca  lea     r14, ds:4[rax*2]
0x180036fd2  call    cs:__imp_GetProcessHeap
0x180036fd9  nop     dword ptr [rax+rax+00h]
0x180036fde  mov     r8, r14; dwBytes
0x180036fe1  xor     edx, edx; dwFlags
0x180036fe3  mov     rcx, rax; hHeap
0x180036fe6  call    cs:__imp_HeapAlloc
0x180036fed  nop     dword ptr [rax+rax+00h]
0x180036ff2  mov     rbp, rax
0x180036ff5  test    rax, rax
0x180036ff8  jnz     short loc_180037001
0x180036ffa  mov     ebx, 8007000Eh
0x180036fff  jmp     short loc_18003701E
0x180037001  mov     r9, rdi
0x180037004  mov     [rsp+508h+var_4E8], rsi
0x180037009  lea     r8, aWsWs; "%ws\\%ws"
0x180037010  mov     rdx, r14; cbDest
0x180037013  mov     rcx, rbp; pszDest
0x180037016  call    StringCbPrintfW
0x18003701b  mov     [r15], rbp
0x18003701e  mov     eax, ebx
0x180037020  jmp     short loc_180037027
0x180037022  mov     eax, 80070057h
0x180037027  mov     rcx, [rsp+508h+var_38]
0x18003702f  xor     rcx, rsp; StackCookie
0x180037032  call    __security_check_cookie
0x180037037  mov     rbx, [rsp+508h+arg_10]
0x18003703f  add     rsp, 4E0h
0x180037046  pop     r15
0x180037048  pop     r14
0x18003704a  pop     rdi
0x18003704b  pop     rsi
0x18003704c  pop     rbp
0x18003704d  retn
```
