# SxLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x1800933b4`
- end: `0x18009359d`
- name: `?SxLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `489`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, void *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180096e8c`
- `0x18009f22c`

## callees

- `0x18001393c`
- `0x180072e08`
- `0x180072f14`
- `0x1800933b4`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180093526`
- `KERNEL32!LoadLibraryExW` at `0x180093526`
- `KERNEL32!GetSystemDirectoryW` at `0x1800933f2`
- `KERNEL32!GetSystemDirectoryW` at `0x180093475`
- `KERNEL32!GetSystemDirectoryW` at `0x1800933f2`
- `KERNEL32!GetSystemDirectoryW` at `0x180093475`
- `KERNEL32!LocalFree` at `0x18009355d`
- `KERNEL32!LocalFree` at `0x18009355d`
- `KERNEL32!SetLastError` at `0x180093573`
- `KERNEL32!SetLastError` at `0x180093573`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093448`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093448`

## string_xrefs

- `0x1800933cb`: `SxLoadSystem32LibraryEx`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "SxLoadSystem32LibraryEx", 0x714u, 1u);
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
0x1800933b4  push    rbp
0x1800933b6  push    rbx
0x1800933b7  push    rsi
0x1800933b8  push    rdi
0x1800933b9  push    r12
0x1800933bb  push    r13
0x1800933bd  push    r14
0x1800933bf  push    r15
0x1800933c1  mov     rbp, rsp
0x1800933c4  sub     rsp, 68h
0x1800933c8  mov     r13d, r8d
0x1800933cb  lea     rdx, aSxloadsystem32; "SxLoadSystem32LibraryEx"
0x1800933d2  mov     r12, rcx
0x1800933d5  mov     r8d, 714h; unsigned __int16
0x1800933db  lea     rcx, [rbp+var_48]; this
0x1800933df  mov     r9d, 1; unsigned __int16
0x1800933e5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800933ea  xor     ebx, ebx
0x1800933ec  xor     edx, edx; uSize
0x1800933ee  xor     ecx, ecx; lpBuffer
0x1800933f0  mov     esi, ebx
0x1800933f2  call    cs:__imp_GetSystemDirectoryW
0x1800933f9  nop     dword ptr [rax+rax+00h]
0x1800933fe  mov     r14d, eax
0x180093401  test    eax, eax
0x180093403  jnz     short loc_18009341B
0x180093405  call    GetLastFailureAsHRESULT
0x18009340a  mov     ecx, 71Fh
0x18009340f  mov     [rbp+var_48], eax
0x180093412  mov     [rbp+var_42], cx
0x180093416  jmp     loc_180093571
0x18009341b  mov     ecx, 71Fh
0x180093420  mov     [rbp+var_48], ebx
0x180093423  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180093427  mov     [rbp+var_44], cx
0x18009342b  mov     rdx, rdi
0x18009342e  inc     rdx
0x180093431  cmp     [r12+rdx*2], bx
0x180093436  jnz     short loc_18009342E
0x180093438  lea     r15d, [rax+1]
0x18009343c  xor     ecx, ecx; uFlags
0x18009343e  inc     r15
0x180093441  add     r15, rdx
0x180093444  lea     rdx, [r15+r15]; uBytes
0x180093448  call    cs:__imp_LocalAlloc
0x18009344f  nop     dword ptr [rax+rax+00h]
0x180093454  mov     rbx, rax
0x180093457  mov     ecx, 725h
0x18009345c  test    rax, rax
0x18009345f  jnz     short loc_180093468
0x180093461  mov     eax, 8007000Eh
0x180093466  jmp     short loc_18009340F
0x180093468  mov     [rbp+var_44], cx
0x18009346c  mov     edx, r14d; uSize
0x18009346f  mov     rcx, rbx; lpBuffer
0x180093472  mov     [rbp+var_48], esi
0x180093475  call    cs:__imp_GetSystemDirectoryW
0x18009347c  nop     dword ptr [rax+rax+00h]
0x180093481  mov     ecx, eax
0x180093483  test    eax, eax
0x180093485  jnz     short loc_18009349D
0x180093487  call    GetLastFailureAsHRESULT
0x18009348c  mov     [rbp+var_48], eax
0x18009348f  mov     eax, 728h
0x180093494  mov     [rbp+var_42], ax
0x180093498  jmp     loc_18009355A
0x18009349d  mov     eax, 728h
0x1800934a2  mov     [rbp+var_44], ax
0x1800934a6  mov     eax, 729h
0x1800934ab  cmp     ecx, r14d
0x1800934ae  jb      short loc_1800934B9
0x1800934b0  mov     [rbp+var_48], 8007006Fh
0x1800934b7  jmp     short loc_180093494
0x1800934b9  xor     r14d, r14d
0x1800934bc  mov     [rbp+var_44], ax
0x1800934c0  mov     [rbp+var_48], r14d
0x1800934c4  inc     rdi
0x1800934c7  cmp     [rbx+rdi*2], r14w
0x1800934cc  jnz     short loc_1800934C4
0x1800934ce  mov     eax, 5Ch ; '\'
0x1800934d3  cmp     ax, [rbx+rdi*2-2]
0x1800934d8  jz      short loc_1800934FC
0x1800934da  lea     r8, Str; "\\"
0x1800934e1  mov     rdx, r15; unsigned __int64
0x1800934e4  mov     rcx, rbx; unsigned __int16 *
0x1800934e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800934ec  mov     [rbp+var_48], eax
0x1800934ef  test    eax, eax
0x1800934f1  mov     eax, 72Dh
0x1800934f6  js      short loc_180093494
0x1800934f8  mov     [rbp+var_44], ax
0x1800934fc  mov     r8, r12; unsigned __int16 *
0x1800934ff  mov     rdx, r15; unsigned __int64
0x180093502  mov     rcx, rbx; unsigned __int16 *
0x180093505  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009350a  mov     [rbp+var_48], eax
0x18009350d  test    eax, eax
0x18009350f  mov     eax, 730h
0x180093514  js      loc_180093494
0x18009351a  mov     r8d, r13d; dwFlags
0x18009351d  mov     [rbp+var_44], ax
0x180093521  xor     edx, edx; hFile
0x180093523  mov     rcx, rbx; lpLibFileName
0x180093526  call    cs:__imp_LoadLibraryExW
0x18009352d  nop     dword ptr [rax+rax+00h]
0x180093532  mov     rsi, rax
0x180093535  test    rax, rax
0x180093538  jnz     short loc_18009354D
0x18009353a  call    GetLastFailureAsHRESULT
0x18009353f  mov     ecx, 733h
0x180093544  mov     [rbp+var_48], eax
0x180093547  mov     [rbp+var_42], cx
0x18009354b  jmp     short loc_18009355A
0x18009354d  mov     ecx, 733h
0x180093552  mov     [rbp+var_48], r14d
0x180093556  mov     [rbp+var_44], cx
0x18009355a  mov     rcx, rbx; hMem
0x18009355d  call    cs:__imp_LocalFree
0x180093564  nop     dword ptr [rax+rax+00h]
0x180093569  test    rsi, rsi
0x18009356c  jnz     short loc_18009357F
0x18009356e  mov     eax, [rbp+var_48]
0x180093571  mov     ecx, eax; dwErrCode
0x180093573  call    cs:__imp_SetLastError
0x18009357a  nop     dword ptr [rax+rax+00h]
0x18009357f  lea     rcx, [rbp+var_48]; this
0x180093583  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180093588  mov     rax, rsi
0x18009358b  add     rsp, 68h
0x18009358f  pop     r15
0x180093591  pop     r14
0x180093593  pop     r13
0x180093595  pop     r12
0x180093597  pop     rdi
0x180093598  pop     rsi
0x180093599  pop     rbx
0x18009359a  pop     rbp
0x18009359b  retn
```
