# DAV_IF_HELPER::TestLockToken(ushort const *,ushort const *)

- ea: `0x180006940`
- end: `0x180006b99`
- name: `?TestLockToken@DAV_IF_HELPER@@UEAAHPEBG0@Z`
- size: `601`
- prototype: `__int64 __fastcall(DAV_IF_HELPER *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800043b0`
- `0x180006940`
- `0x180019d58`
- `0x180019ea0`
- `0x18001a914`
- `0x180020614`
- `0x1800206ec`
- `0x180022520`
- `0x1800225b0`
- `0x180023010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180006b55`
- `msvcrt!_wcsnicmp` at `0x180006b55`
- `msvcrt!_wcsicmp` at `0x180006b17`
- `msvcrt!_wcsicmp` at `0x180006b17`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006a5d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180006a5d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800069e6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800069f6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800069e6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800069f6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006a35`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006aef`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006a35`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006aef`

## pseudocode

```c
_BOOL8 __fastcall DAV_IF_HELPER::TestLockToken(
        DAV_IF_HELPER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rsi
  BOOL v7; // edi
  __int64 v8; // rcx
  int CachedFileInfo; // r15d
  int v10; // r8d
  __int64 Key; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  const wchar_t *v14; // rsi
  unsigned __int64 v15; // rax
  size_t v16; // r8
  struct IHttpFileInfo *v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v20; // [rsp+58h] [rbp-A8h]
  _BYTE v21[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v22; // [rsp+90h] [rbp-70h]
  char v23[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v24[492]; // [rsp+B8h] [rbp-48h] BYREF
  char v25[1064]; // [rsp+1018h] [rbp+F18h] BYREF

  LOCK_SET::LOCK_SET((LOCK_SET *)v23);
  v6 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)this + 3) + 104LL))(
         *((_QWORD *)this + 3),
         a3);
  v7 = 1;
  if ( v6 )
    goto LABEL_20;
  v8 = *((_QWORD *)this + 4);
  if ( v8 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v8 + 104LL))(v8, a3);
    if ( v6 )
      goto LABEL_20;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 2) + 28LL) )
  {
    STRU::STRU((STRU *)v19);
    v18 = 0;
    STRU::STRU((STRU *)v21);
    CachedFileInfo = MapUriPathToPhysicalPath(*((struct IHttpContext **)this + 1), a2, (struct STRU *)v21);
    if ( CachedFileInfo >= 0 )
      CachedFileInfo = GetCachedFileInfo(g_pGlobalInfo, *((struct IHttpContext **)this + 1), v22, &v18);
    STRU::~STRU((STRU *)v21);
    if ( CachedFileInfo >= 0 )
    {
      if ( ((*(__int64 (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v18 + 56LL))(v18) & 0x10) != 0
        && (int)STRU::Copy((STRU *)v19, a2) >= 0
        && (int)EnsureUriPathIsSlashTerminated((struct STRU *)v19) >= 0 )
      {
        a2 = v20;
      }
      (*(void (__fastcall **)(struct IHttpFileInfo *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    if ( (*(int (__fastcall **)(__int64 *, const unsigned __int16 *))(v24[0] + 8))(v24, a2) >= 0
      && (*(int (__fastcall **)(_QWORD, const unsigned __int16 *, char *, __int64))(**(_QWORD **)(*((_QWORD *)this + 2)
                                                                                                + 16LL)
                                                                                  + 88LL))(
           *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
           a2,
           v23,
           1) >= 0 )
    {
      Key = (__int64)STATIC_WSTRING_HASH::FindKey((STATIC_WSTRING_HASH *)v25, a3, v10);
      v12 = Key - 16;
      v13 = -Key;
      if ( (v12 & -(__int64)(v13 != 0)) != 0 )
        v6 = *(_QWORD *)(v12 & -(__int64)(v13 != 0));
      else
        v6 = 0;
    }
    STRU::~STRU((STRU *)v19);
    if ( v6 )
    {
LABEL_20:
      v14 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6);
      if ( !_wcsicmp(a2, v14) )
        goto LABEL_28;
      v15 = -1;
      v16 = -1;
      do
        ++v16;
      while ( v14[v16] );
      do
        ++v15;
      while ( a2[v15] );
      if ( v15 > v16 && (!v16 || v14[v16 - 1] == 47) )
      {
        v7 = _wcsnicmp(v14, a2, v16) == 0;
        goto LABEL_28;
      }
    }
  }
  v7 = 0;
LABEL_28:
  LOCK_SET::~LOCK_SET((LOCK_SET *)v23);
  return v7;
}

```

## disassembly

```asm
0x180006940  mov     [rsp-8+arg_18], rbx
0x180006945  push    rbp
0x180006946  push    rsi
0x180006947  push    rdi
0x180006948  push    r12
0x18000694a  push    r13
0x18000694c  push    r14
0x18000694e  push    r15
0x180006950  lea     rbp, [rsp-1350h]
0x180006958  mov     eax, 1450h
0x18000695d  call    _alloca_probe
0x180006962  sub     rsp, rax
0x180006965  mov     rax, cs:__security_cookie
0x18000696c  xor     rax, rsp
0x18000696f  mov     [rbp+1380h+var_40], rax
0x180006976  mov     r14, rcx
0x180006979  mov     r12, r8
0x18000697c  lea     rcx, [rbp+1380h+var_13D0]; this
0x180006980  mov     rbx, rdx
0x180006983  call    ??0LOCK_SET@@QEAA@XZ; LOCK_SET::LOCK_SET(void)
0x180006988  mov     rcx, [r14+18h]
0x18000698c  mov     rdx, r12
0x18000698f  mov     rax, [rcx]
0x180006992  mov     rax, [rax+68h]
0x180006996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699b  xor     r13d, r13d
0x18000699e  mov     rsi, rax
0x1800069a1  mov     edi, 1
0x1800069a6  test    rax, rax
0x1800069a9  jnz     loc_180006AFF
0x1800069af  mov     rcx, [r14+20h]
0x1800069b3  test    rcx, rcx
0x1800069b6  jz      short loc_1800069D3
0x1800069b8  mov     rax, [rcx]
0x1800069bb  mov     rdx, r12
0x1800069be  mov     rax, [rax+68h]
0x1800069c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c7  mov     rsi, rax
0x1800069ca  test    rax, rax
0x1800069cd  jnz     loc_180006AFF
0x1800069d3  mov     rax, [r14+10h]
0x1800069d7  cmp     [rax+1Ch], r13d
0x1800069db  jz      loc_180006AFA
0x1800069e1  lea     rcx, [rsp+1480h+var_1448]
0x1800069e6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800069ec  lea     rcx, [rsp+1480h+var_1410]
0x1800069f1  mov     [rsp+1480h+var_1450], r13
0x1800069f6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800069fc  mov     rcx, [r14+8]; struct IHttpContext *
0x180006a00  lea     r8, [rsp+1480h+var_1410]; struct STRU *
0x180006a05  mov     rdx, rbx; unsigned __int16 *
0x180006a08  call    ?MapUriPathToPhysicalPath@@YAJPEAVIHttpContext@@PEBGPEAVSTRU@@@Z; MapUriPathToPhysicalPath(IHttpContext *,ushort const *,STRU *)
0x180006a0d  mov     r15d, eax
0x180006a10  test    eax, eax
0x180006a12  js      short loc_180006A30
0x180006a14  mov     r8, [rbp+1380h+var_13F0]; unsigned __int16 *
0x180006a18  lea     r9, [rsp+1480h+var_1450]; struct IHttpFileInfo **
0x180006a1d  mov     rdx, [r14+8]; struct IHttpContext *
0x180006a21  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; struct IHttpServer *
0x180006a28  call    ?GetCachedFileInfo@@YAJPEAVIHttpServer@@PEAVIHttpContext@@PEBGPEAPEAVIHttpFileInfo@@@Z; GetCachedFileInfo(IHttpServer *,IHttpContext *,ushort const *,IHttpFileInfo * *)
0x180006a2d  mov     r15d, eax
0x180006a30  lea     rcx, [rsp+1480h+var_1410]
0x180006a35  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006a3b  test    r15d, r15d
0x180006a3e  js      short loc_180006A8A
0x180006a40  mov     rcx, [rsp+1480h+var_1450]
0x180006a45  mov     rax, [rcx]
0x180006a48  mov     rax, [rax+38h]
0x180006a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a51  test    al, 10h
0x180006a53  jz      short loc_180006A79
0x180006a55  mov     rdx, rbx
0x180006a58  lea     rcx, [rsp+1480h+var_1448]
0x180006a5d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180006a63  test    eax, eax
0x180006a65  js      short loc_180006A79
0x180006a67  lea     rcx, [rsp+1480h+var_1448]; struct STRU *
0x180006a6c  call    ?EnsureUriPathIsSlashTerminated@@YAJPEAVSTRU@@@Z; EnsureUriPathIsSlashTerminated(STRU *)
0x180006a71  test    eax, eax
0x180006a73  cmovns  rbx, [rsp+1480h+var_1428]
0x180006a79  mov     rcx, [rsp+1480h+var_1450]
0x180006a7e  mov     rax, [rcx]
0x180006a81  mov     rax, [rax+10h]
0x180006a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a8a  mov     rax, [rbp+1380h+var_13C8]
0x180006a8e  lea     rcx, [rbp+1380h+var_13C8]
0x180006a92  mov     rdx, rbx
0x180006a95  mov     rax, [rax+8]
0x180006a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9e  test    eax, eax
0x180006aa0  js      short loc_180006AEA
0x180006aa2  mov     rax, [r14+10h]
0x180006aa6  lea     r8, [rbp+1380h+var_13D0]
0x180006aaa  mov     r9d, edi
0x180006aad  mov     rdx, rbx
0x180006ab0  mov     rcx, [rax+10h]
0x180006ab4  mov     rax, [rcx]
0x180006ab7  mov     rax, [rax+58h]
0x180006abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac0  test    eax, eax
0x180006ac2  js      short loc_180006AEA
0x180006ac4  mov     rdx, r12; unsigned __int16 *
0x180006ac7  lea     rcx, [rbp+1380h+var_468]; this
0x180006ace  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180006ad3  lea     rcx, [rax-10h]
0x180006ad7  neg     rax
0x180006ada  sbb     rsi, rsi
0x180006add  and     rsi, rcx
0x180006ae0  jnz     short loc_180006AE7
0x180006ae2  mov     rsi, r13
0x180006ae5  jmp     short loc_180006AEA
0x180006ae7  mov     rsi, [rsi]
0x180006aea  lea     rcx, [rsp+1480h+var_1448]
0x180006aef  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006af5  test    rsi, rsi
0x180006af8  jnz     short loc_180006AFF
0x180006afa  mov     edi, r13d
0x180006afd  jmp     short loc_180006B64
0x180006aff  mov     rax, [rsi]
0x180006b02  mov     rcx, rsi
0x180006b05  mov     rax, [rax+20h]
0x180006b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0e  mov     rdx, rax; String2
0x180006b11  mov     rcx, rbx; String1
0x180006b14  mov     rsi, rax
0x180006b17  call    cs:__imp__wcsicmp
0x180006b1d  test    eax, eax
0x180006b1f  jz      short loc_180006B64
0x180006b21  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006b25  mov     r8, rax
0x180006b28  inc     r8; MaxCount
0x180006b2b  cmp     [rsi+r8*2], r13w
0x180006b30  jnz     short loc_180006B28
0x180006b32  inc     rax
0x180006b35  cmp     [rbx+rax*2], r13w
0x180006b3a  jnz     short loc_180006B32
0x180006b3c  cmp     rax, r8
0x180006b3f  jbe     short loc_180006AFA
0x180006b41  test    r8, r8
0x180006b44  jz      short loc_180006B4F
0x180006b46  cmp     word ptr [rsi+r8*2-2], 2Fh ; '/'
0x180006b4d  jnz     short loc_180006AFA
0x180006b4f  mov     rdx, rbx; String2
0x180006b52  mov     rcx, rsi; String1
0x180006b55  call    cs:__imp__wcsnicmp
0x180006b5b  test    eax, eax
0x180006b5d  mov     edi, r13d
0x180006b60  setz    dil
0x180006b64  lea     rcx, [rbp+1380h+var_13D0]; this
0x180006b68  call    ??1LOCK_SET@@UEAA@XZ; LOCK_SET::~LOCK_SET(void)
0x180006b6d  mov     eax, edi
0x180006b6f  mov     rcx, [rbp+1380h+var_40]
0x180006b76  xor     rcx, rsp; StackCookie
0x180006b79  call    __security_check_cookie
0x180006b7e  mov     rbx, [rsp+1480h+arg_18]
0x180006b86  add     rsp, 1450h
0x180006b8d  pop     r15
0x180006b8f  pop     r14
0x180006b91  pop     r13
0x180006b93  pop     r12
0x180006b95  pop     rdi
0x180006b96  pop     rsi
0x180006b97  pop     rbp
0x180006b98  retn
```
