# CopyVDirTree(void *,IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *,ushort const *,ushort const *,ushort const *,int,int *,ulong)

- ea: `0x18001b368`
- end: `0x18001b4d5`
- name: `?CopyVDirTree@@YAJPEAXPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG444HPEAHK@Z`
- size: `365`
- prototype: `__int64 __fastcall(void *, struct IVDirOperationHelper *, struct IIS_VDIR_CONFIG *, struct IBaseFileSystem *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800031b0`

## callees

- `0x180019d58`
- `0x18001b368`
- `0x18001b764`
- `0x18001f128`
- `0x180022520`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b40c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001b40c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001b3d7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001b3d7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4ad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001b4ad`

## pseudocode

```c
__int64 __fastcall CopyVDirTree(
        void *a1,
        struct IVDirOperationHelper *a2,
        struct IIS_VDIR_CONFIG *a3,
        struct IBaseFileSystem *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        int a9,
        int *a10)
{
  int IsSlashTerminated; // eax
  __int64 v15; // rax
  int v16; // ebx
  unsigned int v18; // [rsp+40h] [rbp-B1h]
  void **v19; // [rsp+60h] [rbp-91h] BYREF
  int v20; // [rsp+68h] [rbp-89h]
  struct IVDirOperationHelper *v21; // [rsp+70h] [rbp-81h]
  struct IIS_VDIR_CONFIG *v22; // [rsp+78h] [rbp-79h]
  struct IBaseFileSystem *v23; // [rsp+80h] [rbp-71h]
  void *v24; // [rsp+88h] [rbp-69h]
  _BYTE v25[48]; // [rsp+90h] [rbp-61h] BYREF
  int v26; // [rsp+C0h] [rbp-31h]
  int v27; // [rsp+C8h] [rbp-29h]
  int v28; // [rsp+CCh] [rbp-25h]
  int v29; // [rsp+D0h] [rbp-21h]
  int v30; // [rsp+D4h] [rbp-1Dh]

  v20 = 0;
  STRU::STRU((STRU *)v25);
  v21 = a2;
  v30 = 1;
  v29 = 1;
  v19 = &COPY_URI_ENUMERATOR::`vftable';
  v22 = a3;
  v23 = a4;
  v24 = a1;
  IsSlashTerminated = STRU::Copy((STRU *)v25, a7);
  if ( IsSlashTerminated < 0
    || (IsSlashTerminated = EnsureUriPathIsSlashTerminated((struct STRU *)v25), IsSlashTerminated < 0) )
  {
LABEL_8:
    v16 = IsSlashTerminated;
    goto LABEL_9;
  }
  v28 = v26;
  v15 = -1;
  do
    ++v15;
  while ( a5[v15] );
  v27 = v15;
  v16 = COPY_MOVE_BASE_ENUMERATOR::HandleOverwrite((COPY_MOVE_BASE_ENUMERATOR *)&v19, a2, a3, a4, a7, a8, a9, a10, v18);
  if ( v16 >= 0 )
  {
    IsSlashTerminated = EnumUri(a1, a3, a4, (struct IUriEnumerator *)&v19, a5, a6, 0x8019u);
    if ( IsSlashTerminated >= 0 )
      IsSlashTerminated = v20;
    goto LABEL_8;
  }
LABEL_9:
  STRU::~STRU((STRU *)v25);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001b368  push    rbp
0x18001b36a  push    rbx
0x18001b36b  push    rsi
0x18001b36c  push    rdi
0x18001b36d  push    r12
0x18001b36f  push    r13
0x18001b371  push    r14
0x18001b373  push    r15
0x18001b375  lea     rbp, [rsp-7]
0x18001b37a  sub     rsp, 0F8h
0x18001b381  mov     rax, cs:__security_cookie
0x18001b388  xor     rax, rsp
0x18001b38b  mov     [rbp+3Fh+var_50], rax
0x18001b38f  mov     rax, [rbp+3Fh+arg_38]
0x18001b396  mov     r15, rcx
0x18001b399  mov     rdi, [rbp+3Fh+arg_20]
0x18001b39d  lea     rcx, [rbp+3Fh+var_A0]
0x18001b3a1  mov     r13, [rbp+3Fh+arg_28]
0x18001b3a5  mov     r14, r9
0x18001b3a8  mov     r12, [rbp+3Fh+arg_30]
0x18001b3ac  mov     rsi, r8
0x18001b3af  mov     [rsp+130h+var_D8], rax
0x18001b3b4  mov     rbx, rdx
0x18001b3b7  mov     rax, [rbp+3Fh+arg_48]
0x18001b3be  mov     [rsp+130h+var_E0], rax
0x18001b3c3  lea     rax, ??_7COPY_MOVE_BASE_ENUMERATOR@@6B@; const COPY_MOVE_BASE_ENUMERATOR::`vftable'
0x18001b3ca  mov     [rsp+130h+var_D0], rax
0x18001b3cf  mov     [rsp+130h+var_C8], 0
0x18001b3d7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001b3dd  mov     ecx, 1
0x18001b3e2  mov     [rsp+130h+var_C0], rbx
0x18001b3e7  mov     [rbp+3Fh+var_5C], ecx
0x18001b3ea  lea     rax, ??_7COPY_URI_ENUMERATOR@@6B@; const COPY_URI_ENUMERATOR::`vftable'
0x18001b3f1  mov     [rbp+3Fh+var_60], ecx
0x18001b3f4  mov     rdx, r12
0x18001b3f7  lea     rcx, [rbp+3Fh+var_A0]
0x18001b3fb  mov     [rsp+130h+var_D0], rax
0x18001b400  mov     [rbp+3Fh+var_B8], rsi
0x18001b404  mov     [rbp+3Fh+var_B0], r14
0x18001b408  mov     [rbp+3Fh+var_A8], r15
0x18001b40c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b412  test    eax, eax
0x18001b414  js      loc_18001B4A7
0x18001b41a  lea     rcx, [rbp+3Fh+var_A0]; struct STRU *
0x18001b41e  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x18001b423  xor     ecx, ecx
0x18001b425  test    eax, eax
0x18001b427  js      short loc_18001B4A7
0x18001b429  mov     eax, [rbp+3Fh+var_70]
0x18001b42c  mov     [rbp+3Fh+var_64], eax
0x18001b42f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b433  inc     rax
0x18001b436  cmp     [rdi+rax*2], cx
0x18001b43a  jnz     short loc_18001B433
0x18001b43c  mov     [rbp+3Fh+var_68], eax
0x18001b43f  lea     rcx, [rsp+130h+var_D0]; this
0x18001b444  mov     rax, [rsp+130h+var_E0]
0x18001b449  mov     r9, r14; struct IBaseFileSystem *
0x18001b44c  mov     [rsp+130h+var_F8], rax; int *
0x18001b451  mov     r8, rsi; struct IIS_VDIR_CONFIG *
0x18001b454  mov     eax, [rbp+3Fh+arg_40]
0x18001b45a  mov     rdx, rbx; struct IVDirOperationHelper *
0x18001b45d  mov     [rsp+130h+var_100], eax; int
0x18001b461  mov     rax, [rsp+130h+var_D8]
0x18001b466  mov     [rsp+130h+var_108], rax; unsigned __int16 *
0x18001b46b  mov     [rsp+130h+var_110], r12; unsigned __int16 *
0x18001b470  call    ?HandleOverwrite@COPY_MOVE_BASE_ENUMERATOR@@QEAAJPEAVIVDirOperationHelper@@PEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEBG3HPEAHK@Z; COPY_MOVE_BASE_ENUMERATOR::HandleOverwrite(IVDirOperationHelper *,IIS_VDIR_CONFIG *,IBaseFileSystem *,ushort const *,ushort const *,int,int *,ulong)
0x18001b475  mov     ebx, eax
0x18001b477  test    eax, eax
0x18001b479  js      short loc_18001B4A9
0x18001b47b  mov     [rsp+130h+var_100], 8019h; unsigned int
0x18001b483  lea     r9, [rsp+130h+var_D0]; struct IUriEnumerator *
0x18001b488  mov     [rsp+130h+var_108], r13; unsigned __int16 *
0x18001b48d  mov     r8, r14; struct IBaseFileSystem *
0x18001b490  mov     rdx, rsi; struct IIS_VDIR_CONFIG *
0x18001b493  mov     [rsp+130h+var_110], rdi; unsigned __int16 *
0x18001b498  mov     rcx, r15; void *
0x18001b49b  call    ?EnumUri@@YAJPEAXPEAVIIS_VDIR_CONFIG@@PEAVIBaseFileSystem@@PEAVIUriEnumerator@@PEBG4K@Z; EnumUri(void *,IIS_VDIR_CONFIG *,IBaseFileSystem *,IUriEnumerator *,ushort const *,ushort const *,ulong)
0x18001b4a0  test    eax, eax
0x18001b4a2  cmovns  eax, [rsp+130h+var_C8]
0x18001b4a7  mov     ebx, eax
0x18001b4a9  lea     rcx, [rbp+3Fh+var_A0]
0x18001b4ad  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001b4b3  mov     eax, ebx
0x18001b4b5  mov     rcx, [rbp+3Fh+var_50]
0x18001b4b9  xor     rcx, rsp; StackCookie
0x18001b4bc  call    __security_check_cookie
0x18001b4c1  add     rsp, 0F8h
0x18001b4c8  pop     r15
0x18001b4ca  pop     r14
0x18001b4cc  pop     r13
0x18001b4ce  pop     r12
0x18001b4d0  pop     rdi
0x18001b4d1  pop     rsi
0x18001b4d2  pop     rbx
0x18001b4d3  pop     rbp
0x18001b4d4  retn
```
