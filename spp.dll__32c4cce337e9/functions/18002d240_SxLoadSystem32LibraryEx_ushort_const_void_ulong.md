# SxLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x18002d240`
- end: `0x18002d3ff`
- name: `?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `447`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180035818`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x180027d5c`
- `0x18002d240`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18002d2ce`
- `KERNEL32!LocalAlloc` at `0x18002d2ce`
- `KERNEL32!LoadLibraryExW` at `0x18002d39b`
- `KERNEL32!LoadLibraryExW` at `0x18002d39b`
- `KERNEL32!LocalFree` at `0x18002d3cc`
- `KERNEL32!LocalFree` at `0x18002d3cc`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d27d`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d2f6`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d27d`
- `KERNEL32!GetSystemDirectoryW` at `0x18002d2f6`
- `KERNEL32!SetLastError` at `0x18002d3dc`
- `KERNEL32!SetLastError` at `0x18002d3dc`

## string_xrefs

- `0x18002d257`: `SxLoadSystem32LibraryEx`

## pseudocode

```c
HINSTANCE __fastcall SxLoadSystem32LibraryEx(const unsigned __int16 *a1, void *a2)
{
  HMODULE Library; // rsi
  UINT SystemDirectoryW; // eax
  __int64 v5; // rcx
  UINT v6; // r14d
  DWORD LastFailureAsHRESULT; // eax
  __int16 v8; // cx
  __int64 v9; // rdi
  __int64 v10; // rdx
  unsigned __int64 v11; // r15
  WCHAR *v12; // rax
  unsigned __int16 *v13; // rbx
  UINT v14; // ecx
  __int16 v15; // ax
  int v17; // [rsp+20h] [rbp-48h] BYREF
  __int16 v18; // [rsp+24h] [rbp-44h]
  __int16 v19; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "SxLoadSystem32LibraryEx", 0x714u, 1u);
  Library = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v6 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5);
    v8 = 1823;
LABEL_3:
    v17 = LastFailureAsHRESULT;
    v19 = v8;
LABEL_24:
    SetLastError(LastFailureAsHRESULT);
    goto LABEL_25;
  }
  v17 = 0;
  v9 = -1;
  v18 = 1823;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  v11 = v10 + SystemDirectoryW + 1 + 1LL;
  v12 = (WCHAR *)LocalAlloc(0, 2 * v11);
  v13 = v12;
  v8 = 1829;
  if ( !v12 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_3;
  }
  v18 = 1829;
  v17 = 0;
  v14 = GetSystemDirectoryW(v12, v6);
  if ( !v14 )
  {
    v17 = GetLastFailureAsHRESULT(0);
    v15 = 1832;
LABEL_10:
    v19 = v15;
    goto LABEL_22;
  }
  v18 = 1832;
  v15 = 1833;
  if ( v14 >= v6 )
  {
    v17 = -2147024785;
    goto LABEL_10;
  }
  v17 = 0;
  v18 = 1833;
  do
    ++v9;
  while ( v13[v9] );
  if ( v13[v9 - 1] != 92 )
  {
    v17 = StringCchCatW(v13, v11, L"\\");
    v15 = 1837;
    if ( v17 < 0 )
      goto LABEL_10;
    v18 = 1837;
  }
  v17 = StringCchCatW(v13, v11, a1);
  v15 = 1840;
  if ( v17 < 0 )
    goto LABEL_10;
  v18 = 1840;
  Library = LoadLibraryExW(v13, 0, 2u);
  if ( Library )
  {
    v17 = 0;
    v18 = 1843;
  }
  else
  {
    v17 = ((__int64 (*)(void))GetLastFailureAsHRESULT)();
    v19 = 1843;
  }
LABEL_22:
  LocalFree(v13);
  if ( !Library )
  {
    LastFailureAsHRESULT = v17;
    goto LABEL_24;
  }
LABEL_25:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return Library;
}

```

## disassembly

```asm
0x18002d240  push    rbp
0x18002d242  push    rbx
0x18002d243  push    rsi
0x18002d244  push    rdi
0x18002d245  push    r12
0x18002d247  push    r13
0x18002d249  push    r14
0x18002d24b  push    r15
0x18002d24d  mov     rbp, rsp
0x18002d250  sub     rsp, 68h
0x18002d254  mov     r12, rcx
0x18002d257  lea     rdx, aSxloadsystem32; "SxLoadSystem32LibraryEx"
0x18002d25e  lea     rcx, [rbp+var_48]; this
0x18002d262  mov     r9d, 1; unsigned __int16
0x18002d268  mov     r8d, 714h; unsigned __int16
0x18002d26e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002d273  xor     r13d, r13d
0x18002d276  xor     edx, edx; uSize
0x18002d278  xor     ecx, ecx; lpBuffer
0x18002d27a  mov     esi, r13d
0x18002d27d  call    cs:__imp_GetSystemDirectoryW
0x18002d283  mov     r14d, eax
0x18002d286  test    eax, eax
0x18002d288  jnz     short loc_18002D2A0
0x18002d28a  call    GetLastFailureAsHRESULT
0x18002d28f  mov     ecx, 71Fh
0x18002d294  mov     [rbp+var_48], eax
0x18002d297  mov     [rbp+var_42], cx
0x18002d29b  jmp     loc_18002D3DA
0x18002d2a0  mov     ecx, 71Fh
0x18002d2a5  mov     [rbp+var_48], r13d
0x18002d2a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002d2ad  mov     [rbp+var_44], cx
0x18002d2b1  mov     rdx, rdi
0x18002d2b4  inc     rdx
0x18002d2b7  cmp     [r12+rdx*2], r13w
0x18002d2bc  jnz     short loc_18002D2B4
0x18002d2be  lea     r15d, [rax+1]
0x18002d2c2  xor     ecx, ecx; uFlags
0x18002d2c4  inc     r15
0x18002d2c7  add     r15, rdx
0x18002d2ca  lea     rdx, [r15+r15]; uBytes
0x18002d2ce  call    cs:__imp_LocalAlloc
0x18002d2d4  mov     rbx, rax
0x18002d2d7  mov     ecx, 725h
0x18002d2dc  test    rax, rax
0x18002d2df  jnz     short loc_18002D2E8
0x18002d2e1  mov     eax, 8007000Eh
0x18002d2e6  jmp     short loc_18002D294
0x18002d2e8  mov     [rbp+var_44], cx
0x18002d2ec  mov     edx, r14d; uSize
0x18002d2ef  mov     rcx, rbx; lpBuffer
0x18002d2f2  mov     [rbp+var_48], r13d
0x18002d2f6  call    cs:__imp_GetSystemDirectoryW
0x18002d2fc  mov     ecx, eax
0x18002d2fe  test    eax, eax
0x18002d300  jnz     short loc_18002D318
0x18002d302  call    GetLastFailureAsHRESULT
0x18002d307  mov     [rbp+var_48], eax
0x18002d30a  mov     eax, 728h
0x18002d30f  mov     [rbp+var_42], ax
0x18002d313  jmp     loc_18002D3C9
0x18002d318  mov     eax, 728h
0x18002d31d  mov     [rbp+var_44], ax
0x18002d321  mov     eax, 729h
0x18002d326  cmp     ecx, r14d
0x18002d329  jb      short loc_18002D334
0x18002d32b  mov     [rbp+var_48], 8007006Fh
0x18002d332  jmp     short loc_18002D30F
0x18002d334  mov     [rbp+var_48], r13d
0x18002d338  mov     [rbp+var_44], ax
0x18002d33c  inc     rdi
0x18002d33f  cmp     [rbx+rdi*2], r13w
0x18002d344  jnz     short loc_18002D33C
0x18002d346  mov     eax, 5Ch ; '\'
0x18002d34b  cmp     ax, [rbx+rdi*2-2]
0x18002d350  jz      short loc_18002D374
0x18002d352  lea     r8, asc_18003A0A0; "\\"
0x18002d359  mov     rdx, r15; unsigned __int64
0x18002d35c  mov     rcx, rbx; unsigned __int16 *
0x18002d35f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d364  mov     [rbp+var_48], eax
0x18002d367  test    eax, eax
0x18002d369  mov     eax, 72Dh
0x18002d36e  js      short loc_18002D30F
0x18002d370  mov     [rbp+var_44], ax
0x18002d374  mov     r8, r12; unsigned __int16 *
0x18002d377  mov     rdx, r15; unsigned __int64
0x18002d37a  mov     rcx, rbx; unsigned __int16 *
0x18002d37d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d382  mov     [rbp+var_48], eax
0x18002d385  test    eax, eax
0x18002d387  mov     eax, 730h
0x18002d38c  js      short loc_18002D30F
0x18002d38e  xor     edx, edx; hFile
0x18002d390  mov     [rbp+var_44], ax
0x18002d394  mov     rcx, rbx; lpLibFileName
0x18002d397  lea     r8d, [rdx+2]; dwFlags
0x18002d39b  call    cs:__imp_LoadLibraryExW
0x18002d3a1  mov     rsi, rax
0x18002d3a4  test    rax, rax
0x18002d3a7  jnz     short loc_18002D3BC
0x18002d3a9  call    GetLastFailureAsHRESULT
0x18002d3ae  mov     ecx, 733h
0x18002d3b3  mov     [rbp+var_48], eax
0x18002d3b6  mov     [rbp+var_42], cx
0x18002d3ba  jmp     short loc_18002D3C9
0x18002d3bc  mov     ecx, 733h
0x18002d3c1  mov     [rbp+var_48], r13d
0x18002d3c5  mov     [rbp+var_44], cx
0x18002d3c9  mov     rcx, rbx; hMem
0x18002d3cc  call    cs:__imp_LocalFree
0x18002d3d2  test    rsi, rsi
0x18002d3d5  jnz     short loc_18002D3E2
0x18002d3d7  mov     eax, [rbp+var_48]
0x18002d3da  mov     ecx, eax; dwErrCode
0x18002d3dc  call    cs:__imp_SetLastError
0x18002d3e2  lea     rcx, [rbp+var_48]; this
0x18002d3e6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002d3eb  mov     rax, rsi
0x18002d3ee  add     rsp, 68h
0x18002d3f2  pop     r15
0x18002d3f4  pop     r14
0x18002d3f6  pop     r13
0x18002d3f8  pop     r12
0x18002d3fa  pop     rdi
0x18002d3fb  pop     rsi
0x18002d3fc  pop     rbx
0x18002d3fd  pop     rbp
0x18002d3fe  retn
```
