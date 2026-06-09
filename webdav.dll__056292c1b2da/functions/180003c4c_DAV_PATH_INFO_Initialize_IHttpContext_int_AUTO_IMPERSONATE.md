# DAV_PATH_INFO::Initialize(IHttpContext *,int,AUTO_IMPERSONATE *)

- ea: `0x180003c4c`
- end: `0x180003dd6`
- name: `?Initialize@DAV_PATH_INFO@@QEAAJPEAVIHttpContext@@HPEAVAUTO_IMPERSONATE@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(DAV_PATH_INFO *this, struct IHttpContext *, int, struct AUTO_IMPERSONATE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003480`

## callees

- `0x180003c4c`
- `0x180019d58`
- `0x180019ea0`
- `0x180019ff8`
- `0x18001a504`
- `0x18001b314`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003cb8`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003cb8`

## pseudocode

```c
__int64 __fastcall DAV_PATH_INFO::Initialize(
        DAV_PATH_INFO *this,
        struct IHttpContext *a2,
        int a3,
        struct AUTO_IMPERSONATE *a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int HRefHead; // ebx
  const unsigned __int16 *v14; // rax
  __int64 v15; // rax
  struct IHttpServer *v16; // rbx
  struct IHttpFileInfo *v17; // rax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  struct IHttpFileInfo *v21; // [rsp+50h] [rbp+8h] BYREF

  v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v10 = *(const unsigned __int16 **)(v9 + 96);
  v11 = *(const unsigned __int16 **)(v9 + 88);
  if ( !v10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v10 = &v11[v12];
  }
  HRefHead = STRU::Copy((DAV_PATH_INFO *)((char *)this + 8), v11, v10 - v11);
  if ( HRefHead < 0 )
    return (unsigned int)HRefHead;
  HRefHead = MakeHRefHead(a2, (DAV_PATH_INFO *)((char *)this + 64));
  if ( HRefHead < 0 )
    return (unsigned int)HRefHead;
  v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 168LL))(
                                    a2,
                                    0);
  HRefHead = GetCanonicalizationProofPhysicalPath(v14, 0, (DAV_PATH_INFO *)((char *)this + 120));
  if ( HRefHead < 0 )
    return (unsigned int)HRefHead;
  v15 = *(_QWORD *)a2;
  v16 = g_pGlobalInfo;
  v21 = 0;
  v17 = (struct IHttpFileInfo *)(*(__int64 (__fastcall **)(struct IHttpContext *))(v15 + 208))(a2);
  v21 = v17;
  if ( v17 )
  {
    (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v17 + 8LL))(v17);
    HRefHead = 0;
LABEL_11:
    *(_QWORD *)this = v21;
    goto LABEL_12;
  }
  v18 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpContext *, _QWORD))(*(_QWORD *)a2 + 168LL))(
                                    a2,
                                    0);
  HRefHead = GetCachedFileInfo(v16, a2, v18, &v21);
  if ( HRefHead >= 0 )
    goto LABEL_11;
LABEL_12:
  AUTO_IMPERSONATE::Reimpersonate(a4);
  if ( HRefHead < 0 )
  {
    if ( a3 )
      return (unsigned int)HRefHead;
    HRefHead = 0;
  }
  if ( *(_QWORD *)this )
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 56LL))(*(_QWORD *)this);
    *((_DWORD *)this + 44) = v19;
    if ( v19 != -1 && (v19 & 0x10) != 0 )
      return (unsigned int)EnsureUriPathIsSlashTerminated((DAV_PATH_INFO *)((char *)this + 8));
  }
  return (unsigned int)HRefHead;
}

```

## disassembly

```asm
0x180003c4c  mov     [rsp+arg_8], rbx
0x180003c51  mov     [rsp+arg_10], rbp
0x180003c56  push    rsi
0x180003c57  push    rdi
0x180003c58  push    r12
0x180003c5a  push    r14
0x180003c5c  push    r15
0x180003c5e  sub     rsp, 20h
0x180003c62  mov     rax, [rdx]
0x180003c65  mov     rdi, rcx
0x180003c68  mov     rcx, rdx
0x180003c6b  mov     r15, r9
0x180003c6e  mov     r14d, r8d
0x180003c71  mov     rsi, rdx
0x180003c74  mov     rax, [rax+18h]
0x180003c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c7d  mov     rcx, rax
0x180003c80  mov     r10, [rax]
0x180003c83  mov     rax, [r10+8]
0x180003c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c8c  xor     r12d, r12d
0x180003c8f  mov     r8, [rax+60h]
0x180003c93  mov     rdx, [rax+58h]
0x180003c97  test    r8, r8
0x180003c9a  jnz     short loc_180003CAE
0x180003c9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003ca0  inc     rax
0x180003ca3  cmp     [rdx+rax*2], r12w
0x180003ca8  jnz     short loc_180003CA0
0x180003caa  lea     r8, [rdx+rax*2]
0x180003cae  sub     r8, rdx
0x180003cb1  lea     rcx, [rdi+8]
0x180003cb5  sar     r8, 1
0x180003cb8  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180003cbe  mov     ebx, eax
0x180003cc0  test    eax, eax
0x180003cc2  js      loc_180003DBD
0x180003cc8  lea     rdx, [rdi+40h]; struct STRU *
0x180003ccc  mov     rcx, rsi; struct IHttpContext *
0x180003ccf  call    ?MakeHRefHead@@YAJPEAVIHttpContext@@PEAVSTRU@@@Z; MakeHRefHead(IHttpContext *,STRU *)
0x180003cd4  mov     ebx, eax
0x180003cd6  test    eax, eax
0x180003cd8  js      loc_180003DBD
0x180003cde  mov     rax, [rsi]
0x180003ce1  xor     edx, edx
0x180003ce3  mov     rcx, rsi
0x180003ce6  mov     rax, [rax+0A8h]
0x180003ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf2  lea     r8, [rdi+78h]; struct STRU *
0x180003cf6  xor     edx, edx; int
0x180003cf8  mov     rcx, rax; unsigned __int16 *
0x180003cfb  call    ?GetCanonicalizationProofPhysicalPath@@YAJPEBGHPEAVSTRU@@@Z; GetCanonicalizationProofPhysicalPath(ushort const *,int,STRU *)
0x180003d00  mov     ebx, eax
0x180003d02  test    eax, eax
0x180003d04  js      loc_180003DBD
0x180003d0a  mov     rax, [rsi]
0x180003d0d  mov     rcx, rsi
0x180003d10  mov     rbx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180003d17  mov     [rsp+48h+arg_0], r12
0x180003d1c  mov     rax, [rax+0D0h]
0x180003d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d28  mov     [rsp+48h+arg_0], rax
0x180003d2d  mov     rcx, rax
0x180003d30  test    rax, rax
0x180003d33  jz      short loc_180003D46
0x180003d35  mov     rax, [rax]
0x180003d38  mov     rax, [rax+8]
0x180003d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d41  mov     ebx, r12d
0x180003d44  jmp     short loc_180003D73
0x180003d46  mov     rax, [rsi]
0x180003d49  xor     edx, edx
0x180003d4b  mov     rcx, rsi
0x180003d4e  mov     rax, [rax+0A8h]
0x180003d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5a  mov     r8, rax; unsigned __int16 *
0x180003d5d  lea     r9, [rsp+48h+arg_0]; struct IHttpFileInfo **
0x180003d62  mov     rdx, rsi; struct IHttpContext *
0x180003d65  mov     rcx, rbx; struct IHttpServer *
0x180003d68  call    ?GetCachedFileInfo@@YAJPEAVIHttpServer@@PEAVIHttpContext@@PEBGPEAPEAVIHttpFileInfo@@@Z; GetCachedFileInfo(IHttpServer *,IHttpContext *,ushort const *,IHttpFileInfo * *)
0x180003d6d  mov     ebx, eax
0x180003d6f  test    eax, eax
0x180003d71  js      short loc_180003D7B
0x180003d73  mov     rax, [rsp+48h+arg_0]
0x180003d78  mov     [rdi], rax
0x180003d7b  mov     rcx, r15; this
0x180003d7e  call    ?Reimpersonate@AUTO_IMPERSONATE@@QEAAJXZ; AUTO_IMPERSONATE::Reimpersonate(void)
0x180003d83  test    ebx, ebx
0x180003d85  jns     short loc_180003D8F
0x180003d87  test    r14d, r14d
0x180003d8a  jnz     short loc_180003DBD
0x180003d8c  mov     ebx, r12d
0x180003d8f  mov     rcx, [rdi]
0x180003d92  test    rcx, rcx
0x180003d95  jz      short loc_180003DBD
0x180003d97  mov     rax, [rcx]
0x180003d9a  mov     rax, [rax+38h]
0x180003d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da3  mov     [rdi+0B0h], eax
0x180003da9  cmp     eax, 0FFFFFFFFh
0x180003dac  jz      short loc_180003DBD
0x180003dae  test    al, 10h
0x180003db0  jz      short loc_180003DBD
0x180003db2  lea     rcx, [rdi+8]; struct STRU *
0x180003db6  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x180003dbb  mov     ebx, eax
0x180003dbd  mov     rbp, [rsp+48h+arg_10]
0x180003dc2  mov     eax, ebx
0x180003dc4  mov     rbx, [rsp+48h+arg_8]
0x180003dc9  add     rsp, 20h
0x180003dcd  pop     r15
0x180003dcf  pop     r14
0x180003dd1  pop     r12
0x180003dd3  pop     rdi
0x180003dd4  pop     rsi
0x180003dd5  retn
```
