# CThumbnailCacheDataFile::_GetThumbnailStreamAtOffset(ulong,ulong,unsigned __int64,int,_GUID const &,void * *)

- ea: `0x180023bd4`
- end: `0x180023e38`
- name: `?_GetThumbnailStreamAtOffset@CThumbnailCacheDataFile@@AEAAJKK_KHAEBU_GUID@@PEAPEAX@Z`
- size: `612`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned int, unsigned int, __int64, int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000cc10`
- `0x18002f0e8`

## callees

- `0x18000e624`
- `0x180012f3c`
- `0x180013008`
- `0x180023bd4`
- `0x180023e40`
- `0x180023e68`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180023c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180023c8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023c2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023c2e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023e01`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023e01`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180023cb7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180023cb7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180023ccc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180023ccc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180023cf1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180023cf1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023d13`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023d13`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThumbnailCacheDataFile::_GetThumbnailStreamAtOffset(
        RTL_SRWLOCK *this,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        const struct _GUID *a6,
        void **a7)
{
  SIZE_T v7; // r13
  CMappingManager *v9; // rsi
  HRESULT v10; // edi
  char *v11; // r15
  unsigned int v12; // r14d
  RTL_SRWLOCK *v13; // rbx
  unsigned int i; // r8d
  __int64 v15; // rdx
  unsigned int v16; // ecx
  HGLOBAL v17; // rax
  void *v18; // rbx
  void *v19; // rax
  int v21; // [rsp+30h] [rbp-40h]
  int v22; // [rsp+30h] [rbp-40h]
  _OWORD v23[2]; // [rsp+40h] [rbp-30h] BYREF
  LPSTREAM ppstm; // [rsp+60h] [rbp-10h] BYREF

  v7 = a3;
  *a7 = 0;
  v9 = (CMappingManager *)&this[9];
  v10 = -2147467259;
  v21 = -2147467259;
  v11 = 0;
  v12 = 0;
  LODWORD(ppstm) = 0;
  v13 = this + 51;
  AcquireSRWLockShared(this + 51);
  for ( i = 0; i < 0xA; ++i )
  {
    v15 = 32LL * i;
    if ( *(_QWORD *)((char *)v9 + v15 + 24) )
    {
      v16 = *(_DWORD *)((char *)v9 + v15 + 32);
      if ( a2 >= v16 && a2 + (unsigned int)v7 < *(_DWORD *)((char *)v9 + v15 + 36) + v16 )
      {
        v21 = 0;
        _InterlockedIncrement((volatile signed __int32 *)((char *)v9 + v15 + 16));
        v11 = *(char **)((char *)v9 + v15 + 24);
        v12 = a2 - *(_DWORD *)((char *)v9 + v15 + 32);
        LODWORD(ppstm) = v12;
        break;
      }
    }
  }
  if ( v13 )
    ReleaseSRWLockShared(v13);
  if ( v21 < 0 )
  {
    memset(v23, 0, sizeof(v23));
    if ( (int)CMappingManager::_CreateView(v9, 0, a2, v7, (unsigned int *)&ppstm, (struct MAPPED_VIEW *)v23) < 0 )
      return (unsigned int)-2147287038;
    v11 = (char *)*((_QWORD *)&v23[0] + 1);
    v22 = CMappingManager::_CacheView(v9, (struct MAPPED_VIEW *)v23);
    v12 = (unsigned int)ppstm;
  }
  else
  {
    v22 = 1;
  }
  if ( !a5 || (unsigned int)IsBufferPagedIn(v11, v7) )
  {
    v17 = GlobalAlloc(2u, v7);
    v18 = v17;
    if ( v17 )
    {
      v19 = GlobalLock(v17);
      if ( !v19 )
        goto LABEL_25;
      v10 = CopyMemoryFromMemMappedFile(v19, &v11[v12], v7);
      GlobalUnlock(v18);
      if ( v10 < 0 )
        goto LABEL_25;
      ppstm = 0;
      v10 = CreateStreamOnHGlobal(v18, 1, &ppstm);
      if ( v10 >= 0 )
      {
        (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
        v18 = 0;
        v10 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, void **))ppstm)(
                ppstm,
                &GUID_0000000c_0000_0000_c000_000000000046,
                a7);
      }
      if ( ppstm )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      if ( v18 )
LABEL_25:
        GlobalFree(v18);
    }
    else
    {
      v10 = -2147024882;
    }
  }
  CMappingManager::ReleaseView(v9, v11, v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180023bd4  mov     [rsp-38h+arg_18], rbx
0x180023bd9  push    rbp
0x180023bda  push    rsi
0x180023bdb  push    rdi
0x180023bdc  push    r12
0x180023bde  push    r13
0x180023be0  push    r14
0x180023be2  push    r15
0x180023be4  mov     rbp, rsp
0x180023be7  sub     rsp, 70h
0x180023beb  mov     rax, cs:__security_cookie
0x180023bf2  xor     rax, rsp
0x180023bf5  mov     [rbp+var_8], rax
0x180023bf9  mov     r13d, r8d
0x180023bfc  mov     r12d, edx
0x180023bff  mov     rax, [rbp+arg_30]
0x180023c03  mov     [rbp+var_38], rax
0x180023c07  mov     qword ptr [rax], 0
0x180023c0e  lea     rsi, [rcx+48h]
0x180023c12  mov     edi, 80004005h
0x180023c17  mov     [rbp+var_40], edi
0x180023c1a  xor     r15d, r15d
0x180023c1d  xor     r14d, r14d
0x180023c20  mov     dword ptr [rbp+ppstm], r14d
0x180023c24  lea     rbx, [rsi+150h]
0x180023c2b  mov     rcx, rbx; SRWLock
0x180023c2e  call    cs:__imp_AcquireSRWLockShared
0x180023c34  xor     r8d, r8d
0x180023c37  cmp     r8d, 0Ah
0x180023c3b  jnb     short loc_180023C86
0x180023c3d  mov     edx, r8d
0x180023c40  shl     rdx, 5
0x180023c44  cmp     [rdx+rsi+18h], r14
0x180023c49  jz      loc_180023DA9
0x180023c4f  mov     ecx, [rdx+rsi+20h]
0x180023c53  cmp     r12d, ecx
0x180023c56  jb      loc_180023DA9
0x180023c5c  add     ecx, [rdx+rsi+24h]
0x180023c60  lea     eax, [r12+r13]
0x180023c64  cmp     eax, ecx
0x180023c66  jnb     loc_180023DA9
0x180023c6c  mov     [rbp+var_40], r14d
0x180023c70  lock inc dword ptr [rdx+rsi+10h]
0x180023c75  mov     r15, [rdx+rsi+18h]
0x180023c7a  mov     r14d, r12d
0x180023c7d  sub     r14d, [rdx+rsi+20h]
0x180023c82  mov     dword ptr [rbp+ppstm], r14d
0x180023c86  test    rbx, rbx
0x180023c89  jz      short loc_180023C94
0x180023c8b  mov     rcx, rbx; SRWLock
0x180023c8e  call    cs:__imp_ReleaseSRWLockShared
0x180023c94  cmp     [rbp+var_40], 0
0x180023c98  jl      loc_180023DB1
0x180023c9e  mov     [rbp+var_40], 1
0x180023ca5  cmp     [rbp+arg_20], 0
0x180023ca9  jnz     loc_180023E0C
0x180023caf  mov     rdx, r13; dwBytes
0x180023cb2  mov     ecx, 2; uFlags
0x180023cb7  call    cs:__imp_GlobalAlloc
0x180023cbd  mov     rbx, rax
0x180023cc0  test    rax, rax
0x180023cc3  jz      loc_180023E2E
0x180023cc9  mov     rcx, rax; hMem
0x180023ccc  call    cs:__imp_GlobalLock
0x180023cd2  test    rax, rax
0x180023cd5  jz      loc_180023DFE
0x180023cdb  mov     edx, r14d
0x180023cde  add     rdx, r15; void *
0x180023ce1  mov     r8, r13; unsigned __int64
0x180023ce4  mov     rcx, rax; void *
0x180023ce7  call    ?CopyMemoryFromMemMappedFile@@YAJPEAX0_K@Z; CopyMemoryFromMemMappedFile(void *,void *,unsigned __int64)
0x180023cec  mov     edi, eax
0x180023cee  mov     rcx, rbx; hMem
0x180023cf1  call    cs:__imp_GlobalUnlock
0x180023cf7  test    edi, edi
0x180023cf9  js      loc_180023DFE
0x180023cff  mov     [rbp+ppstm], 0
0x180023d07  lea     r8, [rbp+ppstm]; ppstm
0x180023d0b  mov     edx, 1; fDeleteOnRelease
0x180023d10  mov     rcx, rbx; hGlobal
0x180023d13  call    cs:__imp_CreateStreamOnHGlobal
0x180023d19  mov     edi, eax
0x180023d1b  test    eax, eax
0x180023d1d  js      short loc_180023D55
0x180023d1f  mov     rcx, [rbp+ppstm]
0x180023d23  xor     edx, edx
0x180023d25  mov     rax, [rcx]
0x180023d28  xor     r9d, r9d
0x180023d2b  xor     r8d, r8d
0x180023d2e  mov     rax, [rax+28h]
0x180023d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d37  xor     ebx, ebx
0x180023d39  mov     rcx, [rbp+ppstm]
0x180023d3d  mov     rax, [rcx]
0x180023d40  mov     r8, [rbp+var_38]
0x180023d44  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180023d4b  mov     rax, [rax]
0x180023d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d53  mov     edi, eax
0x180023d55  mov     rcx, [rbp+ppstm]
0x180023d59  test    rcx, rcx
0x180023d5c  jz      short loc_180023D6B
0x180023d5e  mov     rax, [rcx]
0x180023d61  mov     rax, [rax+10h]
0x180023d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d6a  nop
0x180023d6b  test    rbx, rbx
0x180023d6e  jnz     loc_180023DFE
0x180023d74  mov     r8d, [rbp+var_40]; int
0x180023d78  mov     rdx, r15; void *
0x180023d7b  mov     rcx, rsi; this
0x180023d7e  call    ?ReleaseView@CMappingManager@@QEAAJPEAXH@Z; CMappingManager::ReleaseView(void *,int)
0x180023d83  mov     eax, edi
0x180023d85  mov     rcx, [rbp+var_8]
0x180023d89  xor     rcx, rsp; StackCookie
0x180023d8c  call    __security_check_cookie
0x180023d91  mov     rbx, [rsp+70h+arg_18]
0x180023d99  add     rsp, 70h
0x180023d9d  pop     r15
0x180023d9f  pop     r14
0x180023da1  pop     r13
0x180023da3  pop     r12
0x180023da5  pop     rdi
0x180023da6  pop     rsi
0x180023da7  pop     rbp
0x180023da8  retn
0x180023da9  inc     r8d
0x180023dac  jmp     loc_180023C37
0x180023db1  xorps   xmm0, xmm0
0x180023db4  movups  [rbp+var_30], xmm0
0x180023db8  movups  [rbp+var_20], xmm0
0x180023dbc  lea     rax, [rbp+var_30]
0x180023dc0  mov     [rsp+70h+var_48], rax; struct MAPPED_VIEW *
0x180023dc5  lea     rax, [rbp+ppstm]
0x180023dc9  mov     [rsp+70h+var_50], rax; unsigned int *
0x180023dce  mov     r9d, r13d; unsigned int
0x180023dd1  mov     r8d, r12d; unsigned int
0x180023dd4  xor     edx, edx; int
0x180023dd6  mov     rcx, rsi; this
0x180023dd9  call    ?_CreateView@CMappingManager@@AEAAJHKKPEAKPEAUMAPPED_VIEW@@@Z; CMappingManager::_CreateView(int,ulong,ulong,ulong *,MAPPED_VIEW *)
0x180023dde  test    eax, eax
0x180023de0  js      short loc_180023E24
0x180023de2  mov     r15, qword ptr [rbp+var_30+8]
0x180023de6  lea     rdx, [rbp+var_30]; struct MAPPED_VIEW *
0x180023dea  mov     rcx, rsi; this
0x180023ded  call    ?_CacheView@CMappingManager@@AEAAHPEAUMAPPED_VIEW@@@Z; CMappingManager::_CacheView(MAPPED_VIEW *)
0x180023df2  mov     [rbp+var_40], eax
0x180023df5  mov     r14d, dword ptr [rbp+ppstm]
0x180023df9  jmp     loc_180023CA5
0x180023dfe  mov     rcx, rbx; hMem
0x180023e01  call    cs:__imp_GlobalFree
0x180023e07  jmp     loc_180023D74
0x180023e0c  mov     edx, r13d; unsigned int
0x180023e0f  mov     rcx, r15; void *
0x180023e12  call    ?IsBufferPagedIn@@YAHPEBXI@Z; IsBufferPagedIn(void const *,uint)
0x180023e17  test    eax, eax
0x180023e19  jz      loc_180023D74
0x180023e1f  jmp     loc_180023CAF
0x180023e24  mov     edi, 80030002h
0x180023e29  jmp     loc_180023D83
0x180023e2e  mov     edi, 8007000Eh
0x180023e33  jmp     loc_180023D74
```
