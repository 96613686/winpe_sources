# CollectMatchingInfoByHandle

- ea: `0x180004fec`
- end: `0x180005326`
- name: `CollectMatchingInfoByHandle`
- size: `826`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800697d0`

## callees

- `0x180004790`
- `0x180004fec`
- `0x180005330`
- `0x180016f70`
- `0x1800353c0`
- `0x180049cc4`
- `0x18004b408`
- `0x18004ed08`
- `0x180053300`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000511a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000511a`
- `ntdll!wcsrchr` at `0x1800051b9`
- `ntdll!wcsrchr` at `0x1800051b9`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800051e8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800051e8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180005281`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180005281`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005140`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005140`

## string_xrefs

- `0x18000525c`: `[CollectMatchingInfoByHandle] CMI_FILTER_THISFILEONLY specified with a directory (path=%S).\n`
- `0x180005157`: `[CollectMatchingInfoByHandle] GetFileAttributes failed (path=%S).\n`

## pseudocode

```c
__int64 __fastcall CollectMatchingInfoByHandle(unsigned __int16 *a1, int a2, void *a3)
{
  WCHAR *v4; // rbx
  unsigned int v5; // r12d
  __int64 v8; // rsi
  HANDLE ProcessHeap; // rax
  char v10; // r10
  __int64 v11; // rax
  wchar_t *v12; // rax
  const unsigned __int16 *v13; // rax
  _WORD *v14; // r10
  HANDLE v15; // rax
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h]
  _OWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20; // [rsp+80h] [rbp-80h] BYREF
  __int128 v21; // [rsp+82h] [rbp-7Eh]
  __int128 v22; // [rsp+92h] [rbp-6Eh]
  wchar_t v23; // [rsp+A2h] [rbp-5Eh]
  _BYTE v24[492]; // [rsp+A4h] [rbp-5Ch] BYREF

  v4 = 0;
  v5 = 0;
  v20 = 69;
  v23 = aExeNotSpecifie[17];
  v21 = *(_OWORD *)L"xe Not Specified";
  v22 = *(_OWORD *)L"pecified";
  memset_0(v24, 0, 0x1E4u);
  v8 = -1;
  v17 = 0;
  v18 = 0;
  memset(v19, 0, sizeof(v19));
  if ( a3 == (void *)-1LL )
    goto LABEL_31;
  if ( (unsigned __int16)a2 > 5u )
    goto LABEL_31;
  if ( (int)_CmiLoadFunctions((struct tagCMIPFN *)v19) < 0 )
    goto LABEL_31;
  v17 = 0u;
  DWORD2(v18) = 1;
  *(_QWORD *)&v18 = (a2 & 0x40000000) != 0 ? 0x64uLL : 0;
  ProcessHeap = GetProcessHeap();
  v4 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x2000u);
  if ( !v4 )
    goto LABEL_31;
  *v4 = 0;
  if ( (unsigned __int16)a2 == 4 )
  {
    if ( GetSystemDirectoryW(v4, 0x104u) - 1 > 0x103 )
      goto LABEL_31;
    goto LABEL_20;
  }
  if ( GetFileAttributesW(a1) == -1 )
  {
    _CmiDebugPrintA("[CollectMatchingInfoByHandle] GetFileAttributes failed (path=%S).\n", a1);
    goto LABEL_31;
  }
  if ( (int)StringCchCopyW(v4, 0x1000u, a1) >= 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v4[v11] );
    if ( (v10 & 0x10) != 0 )
    {
      if ( (int)v11 <= 0 || v4[(int)v11 - 1] == 92 )
      {
        do
LABEL_24:
          ++v8;
        while ( v4[v8] );
        if ( (unsigned __int16)a2 != 5 || v20 )
        {
          if ( (a2 & 0x20000000) != 0 )
          {
            SetFilePointer(a3, 0, 0, 2u);
            DWORD2(v18) = 0;
          }
          LOBYTE(v5) = (unsigned int)_CmiCollectMatchingInfoDir(a3, &v17, a2, v4, &v20, &v4[v8], 0, (__int64)v19) == 1;
        }
        else
        {
          _CmiDebugPrintA(
            "[CollectMatchingInfoByHandle] CMI_FILTER_THISFILEONLY specified with a directory (path=%S).\n",
            v4);
        }
        goto LABEL_31;
      }
    }
    else
    {
      v12 = wcsrchr(v4, 0x5Cu);
      if ( v12 )
      {
        v13 = CharNext(v12);
        if ( (int)StringCchCopyW(&v20, 0x104u, v13) < 0 )
          goto LABEL_31;
        *v14 = 0;
        goto LABEL_24;
      }
      if ( (int)StringCchCopyW(&v20, 0x104u, v4) < 0 || !GetCurrentDirectoryW(0x1000u, v4) )
        goto LABEL_31;
    }
LABEL_20:
    if ( (int)StringCchCatW(v4, 0x1000u, L"\\") < 0 )
      goto LABEL_31;
    goto LABEL_24;
  }
LABEL_31:
  _CmiFreeFunctions((struct tagCMIPFN *)v19);
  if ( v4 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v4);
  }
  return v5;
}

```

## disassembly

```asm
0x180004fec  mov     [rsp-8+arg_18], rbx
0x180004ff1  push    rbp
0x180004ff2  push    rsi
0x180004ff3  push    rdi
0x180004ff4  push    r12
0x180004ff6  push    r13
0x180004ff8  push    r14
0x180004ffa  push    r15
0x180004ffc  lea     rbp, [rsp-1A0h]
0x180005004  sub     rsp, 2A0h
0x18000500b  mov     rax, cs:__security_cookie
0x180005012  xor     rax, rsp
0x180005015  mov     [rbp+1D0h+var_40], rax
0x18000501c  movups  xmm0, xmmword ptr cs:aExeNotSpecifie+2; "xe Not Specified"
0x180005023  xor     eax, eax
0x180005025  mov     r13, r8
0x180005028  movups  xmm1, xmmword ptr cs:aExeNotSpecifie+12h; "pecified"
0x18000502f  mov     ebx, eax
0x180005031  mov     r12d, eax
0x180005034  mov     r15d, edx
0x180005037  mov     rdi, rcx
0x18000503a  xor     edx, edx; Val
0x18000503c  lea     rcx, [rbp+1D0h+var_22C]; void *
0x180005040  mov     r8d, 1E4h; Size
0x180005046  lea     eax, [rbx+45h]
0x180005049  mov     [rbp+1D0h+var_250], ax
0x18000504d  movzx   eax, word ptr cs:aExeNotSpecifie+22h; ""
0x180005054  mov     [rbp+1D0h+var_22E], ax
0x180005058  movups  [rbp+1D0h+var_24E], xmm0
0x18000505c  movups  [rbp+1D0h+var_23E], xmm1
0x180005060  call    memset_0
0x180005065  xorps   xmm0, xmm0
0x180005068  xorps   xmm1, xmm1
0x18000506b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000506f  movups  [rsp+2D0h+var_290], xmm0
0x180005074  movups  [rsp+2D0h+var_280], xmm0
0x180005079  movups  [rsp+2D0h+var_270], xmm1
0x18000507e  movups  [rsp+2D0h+var_260], xmm1
0x180005083  cmp     r13, rsi
0x180005086  jz      loc_1800052C9
0x18000508c  movzx   r14d, r15w
0x180005090  cmp     r14d, 5
0x180005094  ja      loc_1800052C9
0x18000509a  lea     rcx, [rsp+2D0h+var_270]; struct tagCMIPFN *
0x18000509f  call    ?_CmiLoadFunctions@@YAJPEAUtagCMIPFN@@@Z; _CmiLoadFunctions(tagCMIPFN *)
0x1800050a4  xor     ecx, ecx
0x1800050a6  test    eax, eax
0x1800050a8  js      loc_1800052C9
0x1800050ae  mov     eax, r15d
0x1800050b1  mov     qword ptr [rsp+2D0h+var_290+8], rcx
0x1800050b6  and     eax, 40000000h
0x1800050bb  mov     qword ptr [rsp+2D0h+var_290], rcx
0x1800050c0  neg     eax
0x1800050c2  mov     dword ptr [rsp+2D0h+var_280+4], ecx
0x1800050c6  mov     dword ptr [rsp+2D0h+var_280+8], 1
0x1800050ce  sbb     eax, eax
0x1800050d0  and     eax, 64h
0x1800050d3  mov     dword ptr [rsp+2D0h+var_280], eax
0x1800050d7  call    cs:__imp_GetProcessHeap
0x1800050de  nop     dword ptr [rax+rax+00h]
0x1800050e3  lea     edx, [rbx+8]; dwFlags
0x1800050e6  mov     r8d, 2000h; dwBytes
0x1800050ec  mov     rcx, rax; hHeap
0x1800050ef  call    cs:__imp_HeapAlloc
0x1800050f6  nop     dword ptr [rax+rax+00h]
0x1800050fb  mov     rbx, rax
0x1800050fe  xor     eax, eax
0x180005100  test    rbx, rbx
0x180005103  jz      loc_1800052C9
0x180005109  mov     [rbx], ax
0x18000510c  cmp     r14d, 4
0x180005110  jnz     short loc_18000513D
0x180005112  mov     edx, 104h; uSize
0x180005117  mov     rcx, rbx; lpBuffer
0x18000511a  call    cs:__imp_GetSystemDirectoryW
0x180005121  nop     dword ptr [rax+rax+00h]
0x180005126  dec     eax
0x180005128  cmp     eax, 103h
0x18000512d  ja      loc_1800052C9
0x180005133  mov     edx, 1000h
0x180005138  jmp     loc_1800051FF
0x18000513d  mov     rcx, rdi; lpFileName
0x180005140  call    cs:__imp_GetFileAttributesW
0x180005147  nop     dword ptr [rax+rax+00h]
0x18000514c  mov     r10d, eax
0x18000514f  cmp     eax, 0FFFFFFFFh
0x180005152  jnz     short loc_180005168
0x180005154  mov     rdx, rdi
0x180005157  lea     rcx, aCollectmatchin; "[CollectMatchingInfoByHandle] GetFileAt"...
0x18000515e  call    ?_CmiDebugPrintA@@YAXPEBDZZ; _CmiDebugPrintA(char const *,...)
0x180005163  jmp     loc_1800052C9
0x180005168  mov     r8, rdi; unsigned __int16 *
0x18000516b  mov     rcx, rbx; unsigned __int16 *
0x18000516e  mov     edi, 1000h
0x180005173  mov     edx, edi; unsigned __int64
0x180005175  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000517a  xor     ecx, ecx
0x18000517c  test    eax, eax
0x18000517e  js      loc_1800052C9
0x180005184  mov     rax, rsi
0x180005187  inc     rax
0x18000518a  cmp     [rbx+rax*2], cx
0x18000518e  jnz     short loc_180005187
0x180005190  test    r10b, 10h
0x180005194  jz      short loc_1800051B1
0x180005196  test    eax, eax
0x180005198  jle     loc_180005244
0x18000519e  cdqe
0x1800051a0  mov     edx, 5Ch ; '\'
0x1800051a5  cmp     [rbx+rax*2-2], dx
0x1800051aa  jnz     short loc_1800051FC
0x1800051ac  jmp     loc_180005244
0x1800051b1  mov     edx, 5Ch ; '\'; Ch
0x1800051b6  mov     rcx, rbx; Str
0x1800051b9  call    cs:__imp_wcsrchr
0x1800051c0  nop     dword ptr [rax+rax+00h]
0x1800051c5  test    rax, rax
0x1800051c8  jnz     short loc_18000521A
0x1800051ca  mov     r8, rbx; unsigned __int16 *
0x1800051cd  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x1800051d1  mov     edx, 104h; unsigned __int64
0x1800051d6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800051db  test    eax, eax
0x1800051dd  js      loc_1800052C9
0x1800051e3  mov     rdx, rbx; lpBuffer
0x1800051e6  mov     ecx, edi; nBufferLength
0x1800051e8  call    cs:__imp_GetCurrentDirectoryW
0x1800051ef  nop     dword ptr [rax+rax+00h]
0x1800051f4  test    eax, eax
0x1800051f6  jz      loc_1800052C9
0x1800051fc  mov     rdx, rdi; unsigned __int64
0x1800051ff  lea     r8, SubBlock; "\\"
0x180005206  mov     rcx, rbx; unsigned __int16 *
0x180005209  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000520e  xor     ecx, ecx
0x180005210  test    eax, eax
0x180005212  js      loc_1800052C9
0x180005218  jmp     short loc_180005244
0x18000521a  mov     rcx, rax; unsigned __int16 *
0x18000521d  call    ?CharNext@@YAPEAGPEBG@Z; CharNext(ushort const *)
0x180005222  mov     r8, rax; unsigned __int16 *
0x180005225  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x180005229  mov     edx, 104h; unsigned __int64
0x18000522e  mov     r10, rax
0x180005231  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005236  xor     ecx, ecx
0x180005238  test    eax, eax
0x18000523a  js      loc_1800052C9
0x180005240  mov     [r10], cx
0x180005244  inc     rsi
0x180005247  cmp     [rbx+rsi*2], cx
0x18000524b  jnz     short loc_180005244
0x18000524d  cmp     r14d, 5
0x180005251  jnz     short loc_180005268
0x180005253  cmp     [rbp+1D0h+var_250], cx
0x180005257  jnz     short loc_180005268
0x180005259  mov     rdx, rbx
0x18000525c  lea     rcx, aCollectmatchin_0; "[CollectMatchingInfoByHandle] CMI_FILTE"...
0x180005263  jmp     loc_18000515E
0x180005268  lea     rdi, [rbx+rsi*2]
0x18000526c  bt      r15d, 1Dh
0x180005271  jnb     short loc_180005293
0x180005273  mov     r9d, 2; dwMoveMethod
0x180005279  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000527c  xor     edx, edx; lDistanceToMove
0x18000527e  mov     rcx, r13; hFile
0x180005281  call    cs:__imp_SetFilePointer
0x180005288  nop     dword ptr [rax+rax+00h]
0x18000528d  xor     ecx, ecx
0x18000528f  mov     dword ptr [rsp+2D0h+var_280+8], ecx
0x180005293  lea     rax, [rsp+2D0h+var_270]
0x180005298  mov     r9, rbx
0x18000529b  mov     [rsp+2D0h+var_298], rax
0x1800052a0  lea     rdx, [rsp+2D0h+var_290]
0x1800052a5  mov     [rsp+2D0h+var_2A0], ecx
0x1800052a9  lea     rax, [rbp+1D0h+var_250]
0x1800052ad  mov     [rsp+2D0h+var_2A8], rdi
0x1800052b2  mov     rcx, r13
0x1800052b5  mov     r8d, r15d
0x1800052b8  mov     [rsp+2D0h+var_2B0], rax
0x1800052bd  call    ?_CmiCollectMatchingInfoDir@@YA?AW4CMI_RESULT@@PEAXPEAUtagRECINFO@@KPEBGPEAG3HPEAUtagCMIPFN@@@Z; _CmiCollectMatchingInfoDir(void *,tagRECINFO *,ulong,ushort const *,ushort *,ushort *,int,tagCMIPFN *)
0x1800052c2  cmp     eax, 1
0x1800052c5  setz    r12b
0x1800052c9  lea     rcx, [rsp+2D0h+var_270]; struct tagCMIPFN *
0x1800052ce  call    ?_CmiFreeFunctions@@YAXPEAUtagCMIPFN@@@Z; _CmiFreeFunctions(tagCMIPFN *)
0x1800052d3  test    rbx, rbx
0x1800052d6  jz      short loc_1800052F8
0x1800052d8  call    cs:__imp_GetProcessHeap
0x1800052df  nop     dword ptr [rax+rax+00h]
0x1800052e4  mov     r8, rbx; lpMem
0x1800052e7  xor     edx, edx; dwFlags
0x1800052e9  mov     rcx, rax; hHeap
0x1800052ec  call    cs:__imp_HeapFree
0x1800052f3  nop     dword ptr [rax+rax+00h]
0x1800052f8  mov     eax, r12d
0x1800052fb  mov     rcx, [rbp+1D0h+var_40]
0x180005302  xor     rcx, rsp; StackCookie
0x180005305  call    __security_check_cookie
0x18000530a  mov     rbx, [rsp+2D0h+arg_18]
0x180005312  add     rsp, 2A0h
0x180005319  pop     r15
0x18000531b  pop     r14
0x18000531d  pop     r13
0x18000531f  pop     r12
0x180005321  pop     rdi
0x180005322  pop     rsi
0x180005323  pop     rbp
0x180005324  retn
```
