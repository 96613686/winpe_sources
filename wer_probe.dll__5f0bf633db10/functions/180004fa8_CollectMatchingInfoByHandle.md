# CollectMatchingInfoByHandle

- ea: `0x180004fa8`
- end: `0x1800052c7`
- name: `CollectMatchingInfoByHandle`
- size: `799`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180066710`

## callees

- `0x180004ed0`
- `0x180004fa8`
- `0x1800052d0`
- `0x1800136f0`
- `0x180033948`
- `0x180047b64`
- `0x18004c940`
- `0x180050db0`
- `0x1800517cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005093`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005286`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005093`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005286`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005294`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800050a5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005265`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005265`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800050ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800050ca`
- `ntdll!wcsrchr` at `0x18000515d`
- `ntdll!wcsrchr` at `0x18000515d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180005186`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180005186`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180005219`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180005219`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800050ea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800050ea`

## string_xrefs

- `0x1800051f4`: `[CollectMatchingInfoByHandle] CMI_FILTER_THISFILEONLY specified with a directory (path=%S).\n`
- `0x1800050fb`: `[CollectMatchingInfoByHandle] GetFileAttributes failed (path=%S).\n`

## pseudocode

```c
__int64 __fastcall CollectMatchingInfoByHandle(unsigned __int16 *a1, int a2, void *a3)
{
  WCHAR *v4; // rbx
  unsigned int v5; // r12d
  __int64 v8; // rsi
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  char v11; // r10
  __int64 v12; // rax
  wchar_t *v13; // rax
  const unsigned __int16 *v14; // rax
  _WORD *v15; // r10
  HANDLE v16; // rax
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  HMODULE hLibModule[2]; // [rsp+70h] [rbp-90h]
  unsigned __int16 v22; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+82h] [rbp-7Eh]
  __int128 v24; // [rsp+92h] [rbp-6Eh]
  wchar_t v25; // [rsp+A2h] [rbp-5Eh]
  _BYTE v26[492]; // [rsp+A4h] [rbp-5Ch] BYREF

  v4 = 0;
  v5 = 0;
  v22 = 69;
  v25 = aExeNotSpecifie[17];
  v23 = *(_OWORD *)L"xe Not Specified";
  v24 = *(_OWORD *)L"pecified";
  memset_0(v26, 0, 0x1E4u);
  v8 = -1;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  *(_OWORD *)hLibModule = 0;
  if ( a3 == (void *)-1LL )
    goto LABEL_31;
  if ( (unsigned __int16)a2 > 5u )
    goto LABEL_31;
  if ( (int)_CmiLoadFunctions((struct tagCMIPFN *)&v20) < 0 )
    goto LABEL_31;
  v18 = 0u;
  DWORD2(v19) = 1;
  *(_QWORD *)&v19 = (a2 & 0x40000000) != 0 ? 0x64uLL : 0;
  ProcessHeap = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x2000u);
  v4 = v10;
  if ( !v10 )
    goto LABEL_31;
  *v10 = 0;
  if ( (unsigned __int16)a2 == 4 )
  {
    if ( GetSystemDirectoryW(v10, 0x104u) - 1 > 0x103 )
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
    v12 = -1;
    do
      ++v12;
    while ( v4[v12] );
    if ( (v11 & 0x10) != 0 )
    {
      if ( (int)v12 <= 0 || v4[(int)v12 - 1] == 92 )
      {
        do
LABEL_24:
          ++v8;
        while ( v4[v8] );
        if ( (unsigned __int16)a2 != 5 || v22 )
        {
          if ( (a2 & 0x20000000) != 0 )
          {
            SetFilePointer(a3, 0, 0, 2u);
            DWORD2(v19) = 0;
          }
          LOBYTE(v5) = (unsigned int)_CmiCollectMatchingInfoDir(a3, &v18, a2, v4, &v22, &v4[v8], 0, (__int64)&v20) == 1;
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
      v13 = wcsrchr(v4, 0x5Cu);
      if ( v13 )
      {
        v14 = CharNext(v13);
        if ( (int)StringCchCopyW(&v22, 0x104u, v14) < 0 )
          goto LABEL_31;
        *v15 = 0;
        goto LABEL_24;
      }
      if ( (int)StringCchCopyW(&v22, 0x104u, v4) < 0 || !GetCurrentDirectoryW(0x1000u, v4) )
        goto LABEL_31;
    }
LABEL_20:
    if ( (int)StringCchCatW(v4, 0x1000u, L"\\") < 0 )
      goto LABEL_31;
    goto LABEL_24;
  }
LABEL_31:
  if ( hLibModule[1] )
    FreeLibrary(hLibModule[1]);
  hLibModule[1] = 0;
  v20 = 0u;
  hLibModule[0] = 0;
  if ( v4 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v4);
  }
  return v5;
}

```

## disassembly

```asm
0x180004fa8  mov     [rsp-8+arg_18], rbx
0x180004fad  push    rbp
0x180004fae  push    rsi
0x180004faf  push    rdi
0x180004fb0  push    r12
0x180004fb2  push    r13
0x180004fb4  push    r14
0x180004fb6  push    r15
0x180004fb8  lea     rbp, [rsp-1A0h]
0x180004fc0  sub     rsp, 2A0h
0x180004fc7  mov     rax, cs:__security_cookie
0x180004fce  xor     rax, rsp
0x180004fd1  mov     [rbp+1D0h+var_40], rax
0x180004fd8  movups  xmm0, xmmword ptr cs:aExeNotSpecifie+2; "xe Not Specified"
0x180004fdf  xor     eax, eax
0x180004fe1  mov     r13, r8
0x180004fe4  movups  xmm1, xmmword ptr cs:aExeNotSpecifie+12h; "pecified"
0x180004feb  mov     ebx, eax
0x180004fed  mov     r12d, eax
0x180004ff0  mov     r15d, edx
0x180004ff3  mov     rdi, rcx
0x180004ff6  xor     edx, edx; Val
0x180004ff8  lea     rcx, [rbp+1D0h+var_22C]; void *
0x180004ffc  mov     r8d, 1E4h; Size
0x180005002  lea     eax, [rbx+45h]
0x180005005  mov     [rbp+1D0h+var_250], ax
0x180005009  movzx   eax, word ptr cs:aExeNotSpecifie+22h; ""
0x180005010  mov     [rbp+1D0h+var_22E], ax
0x180005014  movups  [rbp+1D0h+var_24E], xmm0
0x180005018  movups  [rbp+1D0h+var_23E], xmm1
0x18000501c  call    memset_0
0x180005021  xorps   xmm0, xmm0
0x180005024  xorps   xmm1, xmm1
0x180005027  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000502b  movups  [rsp+2D0h+var_290], xmm0
0x180005030  movups  [rsp+2D0h+var_280], xmm0
0x180005035  movups  [rsp+2D0h+var_270], xmm1
0x18000503a  movups  xmmword ptr [rsp+2D0h+hLibModule], xmm1
0x18000503f  cmp     r13, rsi
0x180005042  jz      loc_18000525B
0x180005048  movzx   r14d, r15w
0x18000504c  cmp     r14d, 5
0x180005050  ja      loc_18000525B
0x180005056  lea     rcx, [rsp+2D0h+var_270]; struct tagCMIPFN *
0x18000505b  call    ?_CmiLoadFunctions@@YAJPEAUtagCMIPFN@@@Z; _CmiLoadFunctions(tagCMIPFN *)
0x180005060  xor     ecx, ecx
0x180005062  test    eax, eax
0x180005064  js      loc_18000525B
0x18000506a  mov     eax, r15d
0x18000506d  mov     qword ptr [rsp+2D0h+var_290+8], rcx
0x180005072  and     eax, 40000000h
0x180005077  mov     qword ptr [rsp+2D0h+var_290], rcx
0x18000507c  neg     eax
0x18000507e  mov     dword ptr [rsp+2D0h+var_280+4], ecx
0x180005082  mov     dword ptr [rsp+2D0h+var_280+8], 1
0x18000508a  sbb     eax, eax
0x18000508c  and     eax, 64h
0x18000508f  mov     dword ptr [rsp+2D0h+var_280], eax
0x180005093  call    cs:__imp_GetProcessHeap
0x180005099  lea     edx, [rbx+8]; dwFlags
0x18000509c  mov     r8d, 2000h; dwBytes
0x1800050a2  mov     rcx, rax; hHeap
0x1800050a5  call    cs:__imp_HeapAlloc
0x1800050ab  xor     ecx, ecx
0x1800050ad  mov     rbx, rax
0x1800050b0  test    rax, rax
0x1800050b3  jz      loc_18000525B
0x1800050b9  mov     [rax], cx
0x1800050bc  cmp     r14d, 4
0x1800050c0  jnz     short loc_1800050E7
0x1800050c2  mov     edx, 104h; uSize
0x1800050c7  mov     rcx, rax; lpBuffer
0x1800050ca  call    cs:__imp_GetSystemDirectoryW
0x1800050d0  dec     eax
0x1800050d2  cmp     eax, 103h
0x1800050d7  ja      loc_18000525B
0x1800050dd  mov     edx, 1000h
0x1800050e2  jmp     loc_180005197
0x1800050e7  mov     rcx, rdi; lpFileName
0x1800050ea  call    cs:__imp_GetFileAttributesW
0x1800050f0  mov     r10d, eax
0x1800050f3  cmp     eax, 0FFFFFFFFh
0x1800050f6  jnz     short loc_18000510C
0x1800050f8  mov     rdx, rdi
0x1800050fb  lea     rcx, aCollectmatchin; "[CollectMatchingInfoByHandle] GetFileAt"...
0x180005102  call    ?_CmiDebugPrintA@@YAXPEBDZZ; _CmiDebugPrintA(char const *,...)
0x180005107  jmp     loc_18000525B
0x18000510c  mov     r8, rdi; unsigned __int16 *
0x18000510f  mov     rcx, rbx; unsigned __int16 *
0x180005112  mov     edi, 1000h
0x180005117  mov     edx, edi; unsigned __int64
0x180005119  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000511e  xor     ecx, ecx
0x180005120  test    eax, eax
0x180005122  js      loc_18000525B
0x180005128  mov     rax, rsi
0x18000512b  inc     rax
0x18000512e  cmp     [rbx+rax*2], cx
0x180005132  jnz     short loc_18000512B
0x180005134  test    r10b, 10h
0x180005138  jz      short loc_180005155
0x18000513a  test    eax, eax
0x18000513c  jle     loc_1800051DC
0x180005142  cdqe
0x180005144  mov     edx, 5Ch ; '\'
0x180005149  cmp     [rbx+rax*2-2], dx
0x18000514e  jnz     short loc_180005194
0x180005150  jmp     loc_1800051DC
0x180005155  mov     edx, 5Ch ; '\'; Ch
0x18000515a  mov     rcx, rbx; Str
0x18000515d  call    cs:__imp_wcsrchr
0x180005163  test    rax, rax
0x180005166  jnz     short loc_1800051B2
0x180005168  mov     r8, rbx; unsigned __int16 *
0x18000516b  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x18000516f  mov     edx, 104h; unsigned __int64
0x180005174  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005179  test    eax, eax
0x18000517b  js      loc_18000525B
0x180005181  mov     rdx, rbx; lpBuffer
0x180005184  mov     ecx, edi; nBufferLength
0x180005186  call    cs:__imp_GetCurrentDirectoryW
0x18000518c  test    eax, eax
0x18000518e  jz      loc_18000525B
0x180005194  mov     rdx, rdi; unsigned __int64
0x180005197  lea     r8, SubBlock; "\\"
0x18000519e  mov     rcx, rbx; unsigned __int16 *
0x1800051a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800051a6  xor     ecx, ecx
0x1800051a8  test    eax, eax
0x1800051aa  js      loc_18000525B
0x1800051b0  jmp     short loc_1800051DC
0x1800051b2  mov     rcx, rax; unsigned __int16 *
0x1800051b5  call    ?CharNext@@YAPEAGPEBG@Z; CharNext(ushort const *)
0x1800051ba  mov     r8, rax; unsigned __int16 *
0x1800051bd  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x1800051c1  mov     edx, 104h; unsigned __int64
0x1800051c6  mov     r10, rax
0x1800051c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800051ce  xor     ecx, ecx
0x1800051d0  test    eax, eax
0x1800051d2  js      loc_18000525B
0x1800051d8  mov     [r10], cx
0x1800051dc  inc     rsi
0x1800051df  cmp     [rbx+rsi*2], cx
0x1800051e3  jnz     short loc_1800051DC
0x1800051e5  cmp     r14d, 5
0x1800051e9  jnz     short loc_180005200
0x1800051eb  cmp     [rbp+1D0h+var_250], cx
0x1800051ef  jnz     short loc_180005200
0x1800051f1  mov     rdx, rbx
0x1800051f4  lea     rcx, aCollectmatchin_0; "[CollectMatchingInfoByHandle] CMI_FILTE"...
0x1800051fb  jmp     loc_180005102
0x180005200  lea     rdi, [rbx+rsi*2]
0x180005204  bt      r15d, 1Dh
0x180005209  jnb     short loc_180005225
0x18000520b  mov     r9d, 2; dwMoveMethod
0x180005211  xor     r8d, r8d; lpDistanceToMoveHigh
0x180005214  xor     edx, edx; lDistanceToMove
0x180005216  mov     rcx, r13; hFile
0x180005219  call    cs:__imp_SetFilePointer
0x18000521f  xor     ecx, ecx
0x180005221  mov     dword ptr [rsp+2D0h+var_280+8], ecx
0x180005225  lea     rax, [rsp+2D0h+var_270]
0x18000522a  mov     r9, rbx
0x18000522d  mov     [rsp+2D0h+var_298], rax
0x180005232  lea     rdx, [rsp+2D0h+var_290]
0x180005237  mov     [rsp+2D0h+var_2A0], ecx
0x18000523b  lea     rax, [rbp+1D0h+var_250]
0x18000523f  mov     [rsp+2D0h+var_2A8], rdi
0x180005244  mov     rcx, r13
0x180005247  mov     r8d, r15d
0x18000524a  mov     [rsp+2D0h+var_2B0], rax
0x18000524f  call    ?_CmiCollectMatchingInfoDir@@YA?AW4CMI_RESULT@@PEAXPEAUtagRECINFO@@KPEBGPEAG3HPEAUtagCMIPFN@@@Z; _CmiCollectMatchingInfoDir(void *,tagRECINFO *,ulong,ushort const *,ushort *,ushort *,int,tagCMIPFN *)
0x180005254  cmp     eax, 1
0x180005257  setz    r12b
0x18000525b  mov     rcx, [rsp+2D0h+hLibModule+8]; hLibModule
0x180005260  test    rcx, rcx
0x180005263  jz      short loc_18000526B
0x180005265  call    cs:__imp_FreeLibrary
0x18000526b  xor     ecx, ecx
0x18000526d  mov     [rsp+2D0h+hLibModule+8], rcx
0x180005272  mov     qword ptr [rsp+2D0h+var_270], rcx
0x180005277  mov     qword ptr [rsp+2D0h+var_270+8], rcx
0x18000527c  mov     [rsp+2D0h+hLibModule], rcx
0x180005281  test    rbx, rbx
0x180005284  jz      short loc_18000529A
0x180005286  call    cs:__imp_GetProcessHeap
0x18000528c  mov     r8, rbx; lpMem
0x18000528f  xor     edx, edx; dwFlags
0x180005291  mov     rcx, rax; hHeap
0x180005294  call    cs:__imp_HeapFree
0x18000529a  mov     eax, r12d
0x18000529d  mov     rcx, [rbp+1D0h+var_40]
0x1800052a4  xor     rcx, rsp; StackCookie
0x1800052a7  call    __security_check_cookie
0x1800052ac  mov     rbx, [rsp+2D0h+arg_18]
0x1800052b4  add     rsp, 2A0h
0x1800052bb  pop     r15
0x1800052bd  pop     r14
0x1800052bf  pop     r13
0x1800052c1  pop     r12
0x1800052c3  pop     rdi
0x1800052c4  pop     rsi
0x1800052c5  pop     rbp
0x1800052c6  retn
```
