# SxLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x18008f3b0`
- end: `0x18008f574`
- name: `?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `452`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, void *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180092c54`
- `0x18009ab28`

## callees

- `0x1800130bc`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f3b0`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18008f510`
- `KERNEL32!LoadLibraryExW` at `0x18008f510`
- `KERNEL32!GetSystemDirectoryW` at `0x18008f3ee`
- `KERNEL32!GetSystemDirectoryW` at `0x18008f465`
- `KERNEL32!GetSystemDirectoryW` at `0x18008f3ee`
- `KERNEL32!GetSystemDirectoryW` at `0x18008f465`
- `KERNEL32!LocalFree` at `0x18008f541`
- `KERNEL32!LocalFree` at `0x18008f541`
- `KERNEL32!SetLastError` at `0x18008f551`
- `KERNEL32!SetLastError` at `0x18008f551`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f43e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008f43e`

## string_xrefs

- `0x18008f3c7`: `SxLoadSystem32LibraryEx`

## pseudocode

```c
HINSTANCE __fastcall SxLoadSystem32LibraryEx(const unsigned __int16 *a1, void *a2, DWORD a3)
{
  HMODULE Library; // rsi
  UINT SystemDirectoryW; // eax
  __int64 v7; // rcx
  UINT v8; // r14d
  DWORD LastFailureAsHRESULT; // eax
  __int16 v10; // cx
  __int64 v11; // rdi
  __int64 v12; // rdx
  unsigned __int64 v13; // r15
  WCHAR *v14; // rax
  unsigned __int16 *v15; // rbx
  UINT v16; // ecx
  __int16 v17; // ax
  __int64 v18; // rcx
  int v20; // [rsp+20h] [rbp-48h] BYREF
  __int16 v21; // [rsp+24h] [rbp-44h]
  __int16 v22; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "SxLoadSystem32LibraryEx", 1812, 1);
  Library = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v8 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v10 = 1823;
LABEL_3:
    v20 = LastFailureAsHRESULT;
    v22 = v10;
LABEL_24:
    SetLastError(LastFailureAsHRESULT);
    goto LABEL_25;
  }
  v20 = 0;
  v11 = -1;
  v21 = 1823;
  v12 = -1;
  do
    ++v12;
  while ( a1[v12] );
  v13 = v12 + SystemDirectoryW + 1 + 1LL;
  v14 = (WCHAR *)LocalAlloc(0, 2 * v13);
  v15 = v14;
  v10 = 1829;
  if ( !v14 )
  {
    LastFailureAsHRESULT = -2147024882;
    goto LABEL_3;
  }
  v21 = 1829;
  v20 = 0;
  v16 = GetSystemDirectoryW(v14, v8);
  if ( !v16 )
  {
    v20 = GetLastFailureAsHRESULT(0);
    v17 = 1832;
LABEL_10:
    v22 = v17;
    goto LABEL_22;
  }
  v21 = 1832;
  v17 = 1833;
  if ( v16 >= v8 )
  {
    v20 = -2147024785;
    goto LABEL_10;
  }
  v21 = 1833;
  v20 = 0;
  do
    ++v11;
  while ( v15[v11] );
  if ( v15[v11 - 1] != 92 )
  {
    v20 = StringCchCatW(v15, v13, L"\\");
    v17 = 1837;
    if ( v20 < 0 )
      goto LABEL_10;
    v21 = 1837;
  }
  v20 = StringCchCatW(v15, v13, a1);
  v17 = 1840;
  if ( v20 < 0 )
    goto LABEL_10;
  v21 = 1840;
  Library = LoadLibraryExW(v15, 0, a3);
  if ( Library )
  {
    v20 = 0;
    v21 = 1843;
  }
  else
  {
    v20 = GetLastFailureAsHRESULT(v18);
    v22 = 1843;
  }
LABEL_22:
  LocalFree(v15);
  if ( !Library )
  {
    LastFailureAsHRESULT = v20;
    goto LABEL_24;
  }
LABEL_25:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return Library;
}

```

## disassembly

```asm
0x18008f3b0  push    rbp
0x18008f3b2  push    rbx
0x18008f3b3  push    rsi
0x18008f3b4  push    rdi
0x18008f3b5  push    r12
0x18008f3b7  push    r13
0x18008f3b9  push    r14
0x18008f3bb  push    r15
0x18008f3bd  mov     rbp, rsp
0x18008f3c0  sub     rsp, 68h
0x18008f3c4  mov     r13d, r8d
0x18008f3c7  lea     rdx, aSxloadsystem32; "SxLoadSystem32LibraryEx"
0x18008f3ce  mov     r12, rcx
0x18008f3d1  mov     r8d, 714h; unsigned __int16
0x18008f3d7  lea     rcx, [rbp+var_48]; this
0x18008f3db  mov     r9d, 1; unsigned __int16
0x18008f3e1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008f3e6  xor     ebx, ebx
0x18008f3e8  xor     edx, edx; uSize
0x18008f3ea  xor     ecx, ecx; lpBuffer
0x18008f3ec  mov     esi, ebx
0x18008f3ee  call    cs:__imp_GetSystemDirectoryW
0x18008f3f4  mov     r14d, eax
0x18008f3f7  test    eax, eax
0x18008f3f9  jnz     short loc_18008F411
0x18008f3fb  call    GetLastFailureAsHRESULT
0x18008f400  mov     ecx, 71Fh
0x18008f405  mov     [rbp+var_48], eax
0x18008f408  mov     [rbp+var_42], cx
0x18008f40c  jmp     loc_18008F54F
0x18008f411  mov     ecx, 71Fh
0x18008f416  mov     [rbp+var_48], ebx
0x18008f419  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008f41d  mov     [rbp+var_44], cx
0x18008f421  mov     rdx, rdi
0x18008f424  inc     rdx
0x18008f427  cmp     [r12+rdx*2], bx
0x18008f42c  jnz     short loc_18008F424
0x18008f42e  lea     r15d, [rax+1]
0x18008f432  xor     ecx, ecx; uFlags
0x18008f434  inc     r15
0x18008f437  add     r15, rdx
0x18008f43a  lea     rdx, [r15+r15]; uBytes
0x18008f43e  call    cs:__imp_LocalAlloc
0x18008f444  mov     rbx, rax
0x18008f447  mov     ecx, 725h
0x18008f44c  test    rax, rax
0x18008f44f  jnz     short loc_18008F458
0x18008f451  mov     eax, 8007000Eh
0x18008f456  jmp     short loc_18008F405
0x18008f458  mov     [rbp+var_44], cx
0x18008f45c  mov     edx, r14d; uSize
0x18008f45f  mov     rcx, rbx; lpBuffer
0x18008f462  mov     [rbp+var_48], esi
0x18008f465  call    cs:__imp_GetSystemDirectoryW
0x18008f46b  mov     ecx, eax
0x18008f46d  test    eax, eax
0x18008f46f  jnz     short loc_18008F487
0x18008f471  call    GetLastFailureAsHRESULT
0x18008f476  mov     [rbp+var_48], eax
0x18008f479  mov     eax, 728h
0x18008f47e  mov     [rbp+var_42], ax
0x18008f482  jmp     loc_18008F53E
0x18008f487  mov     eax, 728h
0x18008f48c  mov     [rbp+var_44], ax
0x18008f490  mov     eax, 729h
0x18008f495  cmp     ecx, r14d
0x18008f498  jb      short loc_18008F4A3
0x18008f49a  mov     [rbp+var_48], 8007006Fh
0x18008f4a1  jmp     short loc_18008F47E
0x18008f4a3  xor     r14d, r14d
0x18008f4a6  mov     [rbp+var_44], ax
0x18008f4aa  mov     [rbp+var_48], r14d
0x18008f4ae  inc     rdi
0x18008f4b1  cmp     [rbx+rdi*2], r14w
0x18008f4b6  jnz     short loc_18008F4AE
0x18008f4b8  mov     eax, 5Ch ; '\'
0x18008f4bd  cmp     ax, [rbx+rdi*2-2]
0x18008f4c2  jz      short loc_18008F4E6
0x18008f4c4  lea     r8, Str; "\\"
0x18008f4cb  mov     rdx, r15; unsigned __int64
0x18008f4ce  mov     rcx, rbx; unsigned __int16 *
0x18008f4d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008f4d6  mov     [rbp+var_48], eax
0x18008f4d9  test    eax, eax
0x18008f4db  mov     eax, 72Dh
0x18008f4e0  js      short loc_18008F47E
0x18008f4e2  mov     [rbp+var_44], ax
0x18008f4e6  mov     r8, r12; unsigned __int16 *
0x18008f4e9  mov     rdx, r15; unsigned __int64
0x18008f4ec  mov     rcx, rbx; unsigned __int16 *
0x18008f4ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008f4f4  mov     [rbp+var_48], eax
0x18008f4f7  test    eax, eax
0x18008f4f9  mov     eax, 730h
0x18008f4fe  js      loc_18008F47E
0x18008f504  mov     r8d, r13d; dwFlags
0x18008f507  mov     [rbp+var_44], ax
0x18008f50b  xor     edx, edx; hFile
0x18008f50d  mov     rcx, rbx; lpLibFileName
0x18008f510  call    cs:__imp_LoadLibraryExW
0x18008f516  mov     rsi, rax
0x18008f519  test    rax, rax
0x18008f51c  jnz     short loc_18008F531
0x18008f51e  call    GetLastFailureAsHRESULT
0x18008f523  mov     ecx, 733h
0x18008f528  mov     [rbp+var_48], eax
0x18008f52b  mov     [rbp+var_42], cx
0x18008f52f  jmp     short loc_18008F53E
0x18008f531  mov     ecx, 733h
0x18008f536  mov     [rbp+var_48], r14d
0x18008f53a  mov     [rbp+var_44], cx
0x18008f53e  mov     rcx, rbx; hMem
0x18008f541  call    cs:__imp_LocalFree
0x18008f547  test    rsi, rsi
0x18008f54a  jnz     short loc_18008F557
0x18008f54c  mov     eax, [rbp+var_48]
0x18008f54f  mov     ecx, eax; dwErrCode
0x18008f551  call    cs:__imp_SetLastError
0x18008f557  lea     rcx, [rbp+var_48]; this
0x18008f55b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008f560  mov     rax, rsi
0x18008f563  add     rsp, 68h
0x18008f567  pop     r15
0x18008f569  pop     r14
0x18008f56b  pop     r13
0x18008f56d  pop     r12
0x18008f56f  pop     rdi
0x18008f570  pop     rsi
0x18008f571  pop     rbx
0x18008f572  pop     rbp
0x18008f573  retn
```
