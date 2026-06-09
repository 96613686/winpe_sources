# SxLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x18001c28c`
- end: `0x18001c44b`
- name: `?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `447`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180020184`

## callees

- `0x180007620`
- `0x18001586c`
- `0x180015974`
- `0x18001c28c`
- `0x18001c58c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c3e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c3e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c428`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c428`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c31a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c31a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c418`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c418`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c2c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c342`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c2c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c342`

## string_xrefs

- `0x18001c2a3`: `SxLoadSystem32LibraryEx`

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
  __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-48h] BYREF
  __int16 v19; // [rsp+24h] [rbp-44h]
  __int16 v20; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "SxLoadSystem32LibraryEx", 1812, 1);
  Library = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v6 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v5);
    v8 = 1823;
LABEL_3:
    v18 = LastFailureAsHRESULT;
    v20 = v8;
LABEL_24:
    SetLastError(LastFailureAsHRESULT);
    goto LABEL_25;
  }
  v18 = 0;
  v9 = -1;
  v19 = 1823;
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
  v19 = 1829;
  v18 = 0;
  v14 = GetSystemDirectoryW(v12, v6);
  if ( !v14 )
  {
    v18 = GetLastFailureAsHRESULT(0);
    v15 = 1832;
LABEL_10:
    v20 = v15;
    goto LABEL_22;
  }
  v19 = 1832;
  v15 = 1833;
  if ( v14 >= v6 )
  {
    v18 = -2147024785;
    goto LABEL_10;
  }
  v18 = 0;
  v19 = 1833;
  do
    ++v9;
  while ( v13[v9] );
  if ( v13[v9 - 1] != 92 )
  {
    v18 = StringCchCatW(v13, v11, L"\\");
    v15 = 1837;
    if ( v18 < 0 )
      goto LABEL_10;
    v19 = 1837;
  }
  v18 = StringCchCatW(v13, v11, a1);
  v15 = 1840;
  if ( v18 < 0 )
    goto LABEL_10;
  v19 = 1840;
  Library = LoadLibraryExW(v13, 0, 2u);
  if ( Library )
  {
    v18 = 0;
    v19 = 1843;
  }
  else
  {
    v18 = GetLastFailureAsHRESULT(v16);
    v20 = 1843;
  }
LABEL_22:
  LocalFree(v13);
  if ( !Library )
  {
    LastFailureAsHRESULT = v18;
    goto LABEL_24;
  }
LABEL_25:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return Library;
}

```

## disassembly

```asm
0x18001c28c  push    rbp
0x18001c28e  push    rbx
0x18001c28f  push    rsi
0x18001c290  push    rdi
0x18001c291  push    r12
0x18001c293  push    r13
0x18001c295  push    r14
0x18001c297  push    r15
0x18001c299  mov     rbp, rsp
0x18001c29c  sub     rsp, 68h
0x18001c2a0  mov     r12, rcx
0x18001c2a3  lea     rdx, aSxloadsystem32; "SxLoadSystem32LibraryEx"
0x18001c2aa  lea     rcx, [rbp+var_48]; this
0x18001c2ae  mov     r9d, 1; unsigned __int16
0x18001c2b4  mov     r8d, 714h; unsigned __int16
0x18001c2ba  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c2bf  xor     r13d, r13d
0x18001c2c2  xor     edx, edx; uSize
0x18001c2c4  xor     ecx, ecx; lpBuffer
0x18001c2c6  mov     esi, r13d
0x18001c2c9  call    cs:__imp_GetSystemDirectoryW
0x18001c2cf  mov     r14d, eax
0x18001c2d2  test    eax, eax
0x18001c2d4  jnz     short loc_18001C2EC
0x18001c2d6  call    GetLastFailureAsHRESULT
0x18001c2db  mov     ecx, 71Fh
0x18001c2e0  mov     [rbp+var_48], eax
0x18001c2e3  mov     [rbp+var_42], cx
0x18001c2e7  jmp     loc_18001C426
0x18001c2ec  mov     ecx, 71Fh
0x18001c2f1  mov     [rbp+var_48], r13d
0x18001c2f5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c2f9  mov     [rbp+var_44], cx
0x18001c2fd  mov     rdx, rdi
0x18001c300  inc     rdx
0x18001c303  cmp     [r12+rdx*2], r13w
0x18001c308  jnz     short loc_18001C300
0x18001c30a  lea     r15d, [rax+1]
0x18001c30e  xor     ecx, ecx; uFlags
0x18001c310  inc     r15
0x18001c313  add     r15, rdx
0x18001c316  lea     rdx, [r15+r15]; uBytes
0x18001c31a  call    cs:__imp_LocalAlloc
0x18001c320  mov     rbx, rax
0x18001c323  mov     ecx, 725h
0x18001c328  test    rax, rax
0x18001c32b  jnz     short loc_18001C334
0x18001c32d  mov     eax, 8007000Eh
0x18001c332  jmp     short loc_18001C2E0
0x18001c334  mov     [rbp+var_44], cx
0x18001c338  mov     edx, r14d; uSize
0x18001c33b  mov     rcx, rbx; lpBuffer
0x18001c33e  mov     [rbp+var_48], r13d
0x18001c342  call    cs:__imp_GetSystemDirectoryW
0x18001c348  mov     ecx, eax
0x18001c34a  test    eax, eax
0x18001c34c  jnz     short loc_18001C364
0x18001c34e  call    GetLastFailureAsHRESULT
0x18001c353  mov     [rbp+var_48], eax
0x18001c356  mov     eax, 728h
0x18001c35b  mov     [rbp+var_42], ax
0x18001c35f  jmp     loc_18001C415
0x18001c364  mov     eax, 728h
0x18001c369  mov     [rbp+var_44], ax
0x18001c36d  mov     eax, 729h
0x18001c372  cmp     ecx, r14d
0x18001c375  jb      short loc_18001C380
0x18001c377  mov     [rbp+var_48], 8007006Fh
0x18001c37e  jmp     short loc_18001C35B
0x18001c380  mov     [rbp+var_48], r13d
0x18001c384  mov     [rbp+var_44], ax
0x18001c388  inc     rdi
0x18001c38b  cmp     [rbx+rdi*2], r13w
0x18001c390  jnz     short loc_18001C388
0x18001c392  mov     eax, 5Ch ; '\'
0x18001c397  cmp     ax, [rbx+rdi*2-2]
0x18001c39c  jz      short loc_18001C3C0
0x18001c39e  lea     r8, asc_180024680; "\\"
0x18001c3a5  mov     rdx, r15; unsigned __int64
0x18001c3a8  mov     rcx, rbx; unsigned __int16 *
0x18001c3ab  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c3b0  mov     [rbp+var_48], eax
0x18001c3b3  test    eax, eax
0x18001c3b5  mov     eax, 72Dh
0x18001c3ba  js      short loc_18001C35B
0x18001c3bc  mov     [rbp+var_44], ax
0x18001c3c0  mov     r8, r12; unsigned __int16 *
0x18001c3c3  mov     rdx, r15; unsigned __int64
0x18001c3c6  mov     rcx, rbx; unsigned __int16 *
0x18001c3c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c3ce  mov     [rbp+var_48], eax
0x18001c3d1  test    eax, eax
0x18001c3d3  mov     eax, 730h
0x18001c3d8  js      short loc_18001C35B
0x18001c3da  xor     edx, edx; hFile
0x18001c3dc  mov     [rbp+var_44], ax
0x18001c3e0  mov     rcx, rbx; lpLibFileName
0x18001c3e3  lea     r8d, [rdx+2]; dwFlags
0x18001c3e7  call    cs:__imp_LoadLibraryExW
0x18001c3ed  mov     rsi, rax
0x18001c3f0  test    rax, rax
0x18001c3f3  jnz     short loc_18001C408
0x18001c3f5  call    GetLastFailureAsHRESULT
0x18001c3fa  mov     ecx, 733h
0x18001c3ff  mov     [rbp+var_48], eax
0x18001c402  mov     [rbp+var_42], cx
0x18001c406  jmp     short loc_18001C415
0x18001c408  mov     ecx, 733h
0x18001c40d  mov     [rbp+var_48], r13d
0x18001c411  mov     [rbp+var_44], cx
0x18001c415  mov     rcx, rbx; hMem
0x18001c418  call    cs:__imp_LocalFree
0x18001c41e  test    rsi, rsi
0x18001c421  jnz     short loc_18001C42E
0x18001c423  mov     eax, [rbp+var_48]
0x18001c426  mov     ecx, eax; dwErrCode
0x18001c428  call    cs:__imp_SetLastError
0x18001c42e  lea     rcx, [rbp+var_48]; this
0x18001c432  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001c437  mov     rax, rsi
0x18001c43a  add     rsp, 68h
0x18001c43e  pop     r15
0x18001c440  pop     r14
0x18001c442  pop     r13
0x18001c444  pop     r12
0x18001c446  pop     rdi
0x18001c447  pop     rsi
0x18001c448  pop     rbx
0x18001c449  pop     rbp
0x18001c44a  retn
```
