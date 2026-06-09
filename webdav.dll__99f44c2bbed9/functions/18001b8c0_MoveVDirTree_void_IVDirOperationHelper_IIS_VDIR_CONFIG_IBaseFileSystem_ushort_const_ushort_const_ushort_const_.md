# MoveVDirTree(void *,IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *,ushort const *,ushort const *,ushort const *,int,int *,ulong)

- ea: `0x18001b8c0`
- end: `0x18001ba54`
- name: `?MoveVDirTree@@YAJPEAXPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG444HPEAHK@Z`
- size: `404`
- prototype: `__int64 __fastcall(void *, struct IVDirOperationHelper *, struct IIS_VDIR_CONFIG *, struct IBaseFileSystem *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000e1b0`

## callees

- `0x180019d58`
- `0x18001b4dc`
- `0x18001b764`
- `0x18001b8c0`
- `0x18001f128`
- `0x180022520`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b967`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b967`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001b92f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001b92f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ba2c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ba2c`

## pseudocode

```c
__int64 __fastcall MoveVDirTree(
        void *a1,
        struct IVDirOperationHelper *a2,
        struct IIS_VDIR_CONFIG *a3,
        struct IBaseFileSystem *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        const unsigned __int16 *a8,
        int a9,
        int *a10)
{
  int IsSlashTerminated; // eax
  __int64 v15; // rax
  int v16; // ebx
  unsigned int v18; // [rsp+30h] [rbp-C1h]
  unsigned int v19; // [rsp+40h] [rbp-B1h]
  void **v20; // [rsp+60h] [rbp-91h] BYREF
  int v21; // [rsp+68h] [rbp-89h]
  struct IVDirOperationHelper *v22; // [rsp+70h] [rbp-81h]
  struct IIS_VDIR_CONFIG *v23; // [rsp+78h] [rbp-79h]
  struct IBaseFileSystem *v24; // [rsp+80h] [rbp-71h]
  void *v25; // [rsp+88h] [rbp-69h]
  _BYTE v26[48]; // [rsp+90h] [rbp-61h] BYREF
  int v27; // [rsp+C0h] [rbp-31h]
  int v28; // [rsp+C8h] [rbp-29h]
  int v29; // [rsp+CCh] [rbp-25h]
  int v30; // [rsp+D0h] [rbp-21h]
  int v31; // [rsp+D4h] [rbp-1Dh]

  v21 = 0;
  STRU::STRU((STRU *)v26);
  v31 = 1;
  v20 = &MOVE_URI_ENUMERATOR::`vftable';
  v22 = a2;
  v23 = a3;
  v24 = a4;
  v30 = 3;
  v25 = a1;
  IsSlashTerminated = STRU::Copy((STRU *)v26, a7);
  if ( IsSlashTerminated < 0
    || (IsSlashTerminated = EnsureUriPathIsSlashTerminated((struct STRU *)v26), IsSlashTerminated < 0) )
  {
LABEL_9:
    v16 = IsSlashTerminated;
    goto LABEL_10;
  }
  v29 = v27;
  v15 = -1;
  do
    ++v15;
  while ( a5[v15] );
  v28 = v15;
  v16 = COPY_MOVE_BASE_ENUMERATOR::HandleOverwrite((COPY_MOVE_BASE_ENUMERATOR *)&v20, a2, a3, a4, a7, a8, a9, a10, v19);
  if ( v16 >= 0 )
  {
    IsSlashTerminated = EnumUri(a1, a3, a4, (struct IUriEnumerator *)&v20, a5, a6, 0x8019u);
    if ( IsSlashTerminated >= 0 )
    {
      IsSlashTerminated = v21;
      if ( v21 >= 0 )
        IsSlashTerminated = DeleteVDirTree(a1, a2, a3, a4, a5, a6, v18);
    }
    goto LABEL_9;
  }
LABEL_10:
  STRU::~STRU((STRU *)v26);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001b8c0  push    rbp
0x18001b8c2  push    rbx
0x18001b8c3  push    rsi
0x18001b8c4  push    rdi
0x18001b8c5  push    r12
0x18001b8c7  push    r13
0x18001b8c9  push    r14
0x18001b8cb  push    r15
0x18001b8cd  lea     rbp, [rsp-7]
0x18001b8d2  sub     rsp, 0F8h
0x18001b8d9  mov     rax, cs:__security_cookie
0x18001b8e0  xor     rax, rsp
0x18001b8e3  mov     [rbp+3Fh+var_50], rax
0x18001b8e7  mov     rax, [rbp+3Fh+arg_38]
0x18001b8ee  mov     r15, rcx
0x18001b8f1  mov     rdi, [rbp+3Fh+arg_20]
0x18001b8f5  lea     rcx, [rbp+3Fh+var_A0]
0x18001b8f9  mov     r12, [rbp+3Fh+arg_28]
0x18001b8fd  mov     r14, r9
0x18001b900  mov     rbx, [rbp+3Fh+arg_30]
0x18001b904  mov     rsi, r8
0x18001b907  mov     [rsp+130h+var_D8], rax
0x18001b90c  mov     r13, rdx
0x18001b90f  mov     rax, [rbp+3Fh+arg_48]
0x18001b916  mov     [rsp+130h+var_E0], rax
0x18001b91b  lea     rax, ??_7COPY_MOVE_BASE_ENUMERATOR@@6B@; const COPY_MOVE_BASE_ENUMERATOR::`vftable'
0x18001b922  mov     [rsp+130h+var_D0], rax
0x18001b927  mov     [rsp+130h+var_C8], 0
0x18001b92f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001b935  lea     rax, ??_7MOVE_URI_ENUMERATOR@@6B@; const MOVE_URI_ENUMERATOR::`vftable'
0x18001b93c  mov     [rbp+3Fh+var_5C], 1
0x18001b943  mov     rdx, rbx
0x18001b946  mov     [rsp+130h+var_D0], rax
0x18001b94b  lea     rcx, [rbp+3Fh+var_A0]
0x18001b94f  mov     [rsp+130h+var_C0], r13
0x18001b954  mov     [rbp+3Fh+var_B8], rsi
0x18001b958  mov     [rbp+3Fh+var_B0], r14
0x18001b95c  mov     [rbp+3Fh+var_60], 3
0x18001b963  mov     [rbp+3Fh+var_A8], r15
0x18001b967  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b96d  test    eax, eax
0x18001b96f  js      loc_18001BA26
0x18001b975  lea     rcx, [rbp+3Fh+var_A0]; struct STRU *
0x18001b979  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x18001b97e  xor     ecx, ecx
0x18001b980  test    eax, eax
0x18001b982  js      loc_18001BA26
0x18001b988  mov     eax, [rbp+3Fh+var_70]
0x18001b98b  mov     [rbp+3Fh+var_64], eax
0x18001b98e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b992  inc     rax
0x18001b995  cmp     [rdi+rax*2], cx
0x18001b999  jnz     short loc_18001B992
0x18001b99b  mov     [rbp+3Fh+var_68], eax
0x18001b99e  lea     rcx, [rsp+130h+var_D0]; this
0x18001b9a3  mov     rax, [rsp+130h+var_E0]
0x18001b9a8  mov     r9, r14; struct IBaseFileSystem *
0x18001b9ab  mov     [rsp+130h+var_F8], rax; int *
0x18001b9b0  mov     r8, rsi; struct IIS_VDIR_CONFIG *
0x18001b9b3  mov     eax, [rbp+3Fh+arg_40]
0x18001b9b9  mov     rdx, r13; struct IVDirOperationHelper *
0x18001b9bc  mov     [rsp+130h+var_100], eax; int
0x18001b9c0  mov     rax, [rsp+130h+var_D8]
0x18001b9c5  mov     [rsp+130h+var_108], rax; unsigned __int16 *
0x18001b9ca  mov     [rsp+130h+var_110], rbx; unsigned __int16 *
0x18001b9cf  call    ?HandleOverwrite@COPY_MOVE_BASE_ENUMERATOR@@QEAAJPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG3HPEAHK@Z; COPY_MOVE_BASE_ENUMERATOR::HandleOverwrite(IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *,ushort const *,int,int *,ulong)
0x18001b9d4  mov     ebx, eax
0x18001b9d6  test    eax, eax
0x18001b9d8  js      short loc_18001BA28
0x18001b9da  mov     [rsp+130h+var_100], 8019h; unsigned int
0x18001b9e2  lea     r9, [rsp+130h+var_D0]; struct IUriEnumerator *
0x18001b9e7  mov     [rsp+130h+var_108], r12; unsigned __int16 *
0x18001b9ec  mov     r8, r14; struct IBaseFileSystem *
0x18001b9ef  mov     rdx, rsi; struct IIS_VDIR_CONFIG *
0x18001b9f2  mov     [rsp+130h+var_110], rdi; unsigned __int16 *
0x18001b9f7  mov     rcx, r15; void *
0x18001b9fa  call    ?EnumUri@@YAJPEAXPEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEAVIUriEnumerator@@PEBG4K@Z; EnumUri(void *,IIS_VDIR_CONFIG *,IBaseFileSystem *,IUriEnumerator *,ushort const *,ushort const *,ulong)
0x18001b9ff  test    eax, eax
0x18001ba01  js      short loc_18001BA26
0x18001ba03  mov     eax, [rsp+130h+var_C8]
0x18001ba07  test    eax, eax
0x18001ba09  js      short loc_18001BA26
0x18001ba0b  mov     [rsp+130h+var_108], r12; unsigned __int16 *
0x18001ba10  mov     r9, r14; struct IBaseFileSystem *
0x18001ba13  mov     r8, rsi; struct IIS_VDIR_CONFIG *
0x18001ba16  mov     [rsp+130h+var_110], rdi; unsigned __int16 *
0x18001ba1b  mov     rdx, r13; struct IVDirOperationHelper *
0x18001ba1e  mov     rcx, r15; void *
0x18001ba21  call    ?DeleteVDirTree@@YAJPEAXPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG4K@Z; DeleteVDirTree(void *,IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *,ushort const *,ulong)
0x18001ba26  mov     ebx, eax
0x18001ba28  lea     rcx, [rbp+3Fh+var_A0]
0x18001ba2c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ba32  mov     eax, ebx
0x18001ba34  mov     rcx, [rbp+3Fh+var_50]
0x18001ba38  xor     rcx, rsp; StackCookie
0x18001ba3b  call    __security_check_cookie
0x18001ba40  add     rsp, 0F8h
0x18001ba47  pop     r15
0x18001ba49  pop     r14
0x18001ba4b  pop     r13
0x18001ba4d  pop     r12
0x18001ba4f  pop     rdi
0x18001ba50  pop     rsi
0x18001ba51  pop     rbx
0x18001ba52  pop     rbp
0x18001ba53  retn
```
