# URL_AUTHZ_RULE_ENTRY::CheckAuthorizationRule(ushort const *,IHttpUser *,char const *,AUTHORIZATION_ACCESS_TYPE *)

- ea: `0x180002b88`
- end: `0x180002ed0`
- name: `?CheckAuthorizationRule@URL_AUTHZ_RULE_ENTRY@@QEAAJPEBGPEAVIHttpUser@@PEBDPEAW4AUTHORIZATION_ACCESS_TYPE@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(URL_AUTHZ_RULE_ENTRY *this, wchar_t *, struct IHttpUser *, const char *, enum AUTHORIZATION_ACCESS_TYPE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003158`

## callees

- `0x180002b88`
- `0x180002ed8`
- `0x180003438`
- `0x180003910`
- `0x180003ba6`
- `0x180003be0`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002e10`
- `msvcrt!_wcsicmp` at `0x180002e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d53`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002d49`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002d49`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002cc5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002cc5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002d27`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002d79`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002da1`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002d27`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002d79`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002da1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002d31`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002d70`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002dab`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002d31`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002d70`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002dab`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::CheckAuthorizationRule(
        URL_AUTHZ_RULE_ENTRY *this,
        wchar_t *a2,
        struct IHttpUser *a3,
        const char *a4,
        enum AUTHORIZATION_ACCESS_TYPE *a5)
{
  unsigned int v5; // r10d
  unsigned int v6; // r14d
  wchar_t *v9; // rax
  __int64 v11; // r11
  unsigned int v12; // ecx
  __int64 v13; // rax
  const char *v14; // rax
  const char *v15; // r9
  int v16; // r8d
  int v17; // edx
  int v18; // r15d
  signed int v19; // edi
  unsigned int i; // r12d
  __int64 v21; // r14
  __int64 v22; // rax
  __int64 v23; // rdi
  signed int LastError; // eax
  int matched; // eax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  signed __int32 v30[8]; // [rsp+0h] [rbp-70h] BYREF
  int v31; // [rsp+20h] [rbp-50h] BYREF
  int v32; // [rsp+24h] [rbp-4Ch]
  wchar_t *String2; // [rsp+28h] [rbp-48h]
  _QWORD v34[4]; // [rsp+30h] [rbp-40h] BYREF
  void *Src; // [rsp+50h] [rbp-20h]
  unsigned int Size; // [rsp+58h] [rbp-18h]
  __int16 Size_4; // [rsp+5Ch] [rbp-14h]

  v5 = *((_DWORD *)this + 20);
  v6 = 0;
  String2 = a2;
  v9 = a2;
  if ( v5 )
  {
    v11 = *((_QWORD *)this + 9);
    v12 = 0;
    while ( 1 )
    {
      v13 = 56LL * v12;
      if ( !*(_DWORD *)(v13 + v11 + 48) )
        break;
      v14 = *(const char **)(v13 + v11 + 32);
      v15 = (const char *)(a4 - v14);
      do
      {
        v16 = (unsigned __int8)v15[(_QWORD)v14];
        v17 = *(unsigned __int8 *)v14 - v16;
        if ( v17 )
          break;
        ++v14;
      }
      while ( v16 );
      if ( !v17 )
        break;
      if ( ++v12 >= v5 )
        goto LABEL_9;
    }
    v9 = String2;
  }
  if ( *((_DWORD *)this + 21) || *((_DWORD *)this + 22) && (!*v9 || !*((_DWORD *)this + 4)) )
  {
LABEL_33:
    *(_DWORD *)a5 = *((_DWORD *)this + 4);
    return 0;
  }
  v18 = (*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a3 + 64LL))(a3);
  v32 = v18;
  if ( !(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a3 + 32LL))(a3) && !v18 )
  {
LABEL_9:
    *(_DWORD *)a5 = 2;
    return 0;
  }
  v19 = 0;
  for ( i = 0; i < *((_DWORD *)this + 8); ++i )
  {
    v21 = 56LL * i;
    if ( v18 )
    {
      v27 = _wcsicmp(*(const wchar_t **)(*((_QWORD *)this + 3) + v21 + 32), String2);
      v6 = 0;
      if ( !v27 )
        goto LABEL_33;
      goto LABEL_37;
    }
    v22 = *((_QWORD *)this + 5);
    v31 = 0;
    if ( !*(_DWORD *)(v22 + v21 + 48) )
    {
      v34[0] = 0;
      Src = v34;
      Size = 32;
      Size_4 = 256;
      CReaderWriterLock3::WriteLock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
      if ( !*(_DWORD *)(*((_QWORD *)this + 5) + v21 + 48) )
      {
        (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
        v19 = URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal(
                (struct STRU *)(v21 + *((_QWORD *)this + 3)),
                (struct BUFFER *)v34);
        (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
        if ( v19 < 0 )
        {
          v6 = 0;
          if ( *((_DWORD *)this + 4) )
            goto LABEL_28;
          v19 = 0;
          CReaderWriterLock3::WriteUnlock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
          BUFFER::~BUFFER((BUFFER *)v34);
          goto LABEL_37;
        }
        v23 = v21 + *((_QWORD *)this + 5);
        if ( BUFFER::Resize((BUFFER *)v23, Size) )
        {
          memcpy_0(*(void **)(v23 + 32), Src, Size);
          _InterlockedOr(v30, 0);
          *(_DWORD *)(v23 + 48) = 1;
        }
        else
        {
          LastError = GetLastError();
          v19 = LastError;
          if ( LastError > 0 )
            v19 = (unsigned __int16)LastError | 0x80070000;
          if ( v19 < 0 )
          {
LABEL_28:
            BUFFER::~BUFFER((BUFFER *)v34);
            CReaderWriterLock3::WriteUnlock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
            return (unsigned int)v19;
          }
        }
      }
      CReaderWriterLock3::WriteUnlock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
      BUFFER::~BUFFER((BUFFER *)v34);
    }
    matched = URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(
                a3,
                *(void **)(*((_QWORD *)this + 5) + v21 + 32),
                &v31);
    v6 = 0;
    v19 = matched;
    if ( matched < 0 )
      return (unsigned int)v19;
    if ( v31 )
      goto LABEL_33;
LABEL_37:
    v18 = v32;
  }
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
  if ( !*((_DWORD *)this + 16) )
  {
LABEL_46:
    *(_DWORD *)a5 = 2;
    goto LABEL_47;
  }
  while ( 1 )
  {
    v28 = *((_QWORD *)this + 7);
    v29 = 56LL * v6;
    v31 = 0;
    if ( v18 )
    {
      v19 = (*(__int64 (__fastcall **)(struct IHttpUser *, _QWORD, int *))(*(_QWORD *)a3 + 72LL))(
              a3,
              *(_QWORD *)(v29 + v28 + 32),
              &v31);
      if ( v19 < 0 )
        goto LABEL_47;
    }
    else
    {
      v19 = URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(a3, (struct STRU *)(v29 + v28), &v31);
      if ( v19 < 0 )
      {
        if ( *((_DWORD *)this + 4) )
          goto LABEL_47;
        v19 = 0;
        goto LABEL_45;
      }
    }
    if ( v31 )
      break;
LABEL_45:
    if ( ++v6 >= *((_DWORD *)this + 16) )
      goto LABEL_46;
  }
  v19 = 0;
  *(_DWORD *)a5 = *((_DWORD *)this + 4);
LABEL_47:
  (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180002b88  mov     [rsp-38h+arg_18], rbx
0x180002b8d  push    rbp
0x180002b8e  push    rsi
0x180002b8f  push    rdi
0x180002b90  push    r12
0x180002b92  push    r13
0x180002b94  push    r14
0x180002b96  push    r15
0x180002b98  mov     rbp, rsp
0x180002b9b  sub     rsp, 70h
0x180002b9f  mov     rax, cs:__security_cookie
0x180002ba6  xor     rax, rsp
0x180002ba9  mov     [rbp+var_10], rax
0x180002bad  mov     r10d, [rcx+50h]
0x180002bb1  xor     r14d, r14d
0x180002bb4  mov     rsi, [rbp+arg_20]
0x180002bb8  mov     rdi, r9
0x180002bbb  mov     [rbp+String2], rdx
0x180002bbf  mov     r13, r8
0x180002bc2  mov     rax, rdx
0x180002bc5  mov     rbx, rcx
0x180002bc8  test    r10d, r10d
0x180002bcb  jz      short loc_180002C1B
0x180002bcd  mov     r11, [rbx+48h]
0x180002bd1  mov     ecx, r14d
0x180002bd4  mov     eax, ecx
0x180002bd6  imul    rax, 38h ; '8'
0x180002bda  cmp     [rax+r11+30h], r14d
0x180002bdf  jz      short loc_180002C17
0x180002be1  mov     rax, [rax+r11+20h]
0x180002be6  mov     r9, rdi
0x180002be9  sub     r9, rax
0x180002bec  movzx   edx, byte ptr [rax]
0x180002bef  movzx   r8d, byte ptr [rax+r9]
0x180002bf4  sub     edx, r8d
0x180002bf7  jnz     short loc_180002C01
0x180002bf9  inc     rax
0x180002bfc  test    r8d, r8d
0x180002bff  jnz     short loc_180002BEC
0x180002c01  test    edx, edx
0x180002c03  jz      short loc_180002C17
0x180002c05  inc     ecx
0x180002c07  cmp     ecx, r10d
0x180002c0a  jb      short loc_180002BD4
0x180002c0c  mov     dword ptr [rsi], 2
0x180002c12  jmp     loc_180002DDA
0x180002c17  mov     rax, [rbp+String2]
0x180002c1b  cmp     [rbx+54h], r14d
0x180002c1f  jnz     loc_180002DD5
0x180002c25  cmp     [rbx+58h], r14d
0x180002c29  jz      short loc_180002C3F
0x180002c2b  cmp     [rax], r14w
0x180002c2f  jz      loc_180002DD5
0x180002c35  cmp     [rbx+10h], r14d
0x180002c39  jz      loc_180002DD5
0x180002c3f  mov     rax, [r13+0]
0x180002c43  mov     rcx, r13
0x180002c46  mov     rax, [rax+40h]
0x180002c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4f  mov     r15d, eax
0x180002c52  mov     [rbp+var_4C], eax
0x180002c55  mov     rax, [r13+0]
0x180002c59  mov     rcx, r13
0x180002c5c  mov     rax, [rax+20h]
0x180002c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c65  test    rax, rax
0x180002c68  jnz     short loc_180002C6F
0x180002c6a  test    r15d, r15d
0x180002c6d  jz      short loc_180002C0C
0x180002c6f  mov     edi, r14d
0x180002c72  mov     r12d, r14d
0x180002c75  cmp     [rbx+20h], r14d
0x180002c79  jbe     loc_180002E2E
0x180002c7f  mov     eax, r12d
0x180002c82  xor     edx, edx
0x180002c84  imul    r14, rax, 38h ; '8'
0x180002c88  test    r15d, r15d
0x180002c8b  jnz     loc_180002E03
0x180002c91  mov     rax, [rbx+28h]
0x180002c95  mov     [rbp+var_50], edx
0x180002c98  mov     ecx, [rax+r14+30h]
0x180002c9d  test    ecx, ecx
0x180002c9f  jnz     loc_180002DB1
0x180002ca5  lea     rax, [rbp+var_40]
0x180002ca9  mov     [rbp+var_40], rdx
0x180002cad  lea     r15, [rbx+30h]
0x180002cb1  mov     [rbp+Src], rax
0x180002cb5  mov     rcx, r15
0x180002cb8  mov     dword ptr [rbp+Size], 20h ; ' '
0x180002cbf  mov     word ptr [rbp+Size+4], 100h
0x180002cc5  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180002ccb  mov     rax, [rbx+28h]
0x180002ccf  mov     ecx, [rax+r14+30h]
0x180002cd4  test    ecx, ecx
0x180002cd6  jnz     loc_180002D9E
0x180002cdc  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002ce3  mov     rax, [rcx]
0x180002ce6  mov     rax, [rax+18h]
0x180002cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cef  mov     rcx, [rbx+18h]
0x180002cf3  lea     rdx, [rbp+var_40]; struct BUFFER *
0x180002cf7  add     rcx, r14; struct STRU *
0x180002cfa  call    ?ResolveUserNameToSidForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVSTRU@@PEAVBUFFER@@@Z; URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal(STRU *,BUFFER *)
0x180002cff  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002d06  mov     edi, eax
0x180002d08  mov     rdx, [rcx]
0x180002d0b  mov     rax, [rdx+20h]
0x180002d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d14  test    edi, edi
0x180002d16  jns     short loc_180002D3C
0x180002d18  xor     r14d, r14d
0x180002d1b  cmp     [rbx+10h], r14d
0x180002d1f  jnz     short loc_180002D6C
0x180002d21  mov     rcx, r15
0x180002d24  mov     edi, r14d
0x180002d27  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002d2d  lea     rcx, [rbp+var_40]
0x180002d31  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002d37  jmp     loc_180002E1D
0x180002d3c  mov     rdi, [rbx+28h]
0x180002d40  mov     edx, dword ptr [rbp+Size]
0x180002d43  add     rdi, r14
0x180002d46  mov     rcx, rdi
0x180002d49  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180002d4f  test    al, al
0x180002d51  jnz     short loc_180002D81
0x180002d53  call    cs:__imp_GetLastError
0x180002d59  mov     edi, eax
0x180002d5b  test    eax, eax
0x180002d5d  jle     short loc_180002D68
0x180002d5f  movzx   edi, ax
0x180002d62  or      edi, 80070000h
0x180002d68  test    edi, edi
0x180002d6a  jns     short loc_180002D9E
0x180002d6c  lea     rcx, [rbp+var_40]
0x180002d70  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002d76  mov     rcx, r15
0x180002d79  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002d7f  jmp     short loc_180002DDD
0x180002d81  mov     r8d, dword ptr [rbp+Size]; Size
0x180002d85  mov     rdx, [rbp+Src]; Src
0x180002d89  mov     rcx, [rdi+20h]; void *
0x180002d8d  call    memcpy_0
0x180002d92  lock or [rsp+70h+var_70], 0
0x180002d97  mov     dword ptr [rdi+30h], 1
0x180002d9e  mov     rcx, r15
0x180002da1  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002da7  lea     rcx, [rbp+var_40]
0x180002dab  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002db1  mov     rdx, [rbx+28h]
0x180002db5  lea     r8, [rbp+var_50]; int *
0x180002db9  mov     rcx, r13; struct IHttpUser *
0x180002dbc  mov     rdx, [rdx+r14+20h]; void *
0x180002dc1  call    ?MatchUserNameForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVIHttpUser@@PEAXPEAH@Z; URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(IHttpUser *,void *,int *)
0x180002dc6  xor     r14d, r14d
0x180002dc9  mov     edi, eax
0x180002dcb  test    eax, eax
0x180002dcd  js      short loc_180002DDD
0x180002dcf  cmp     [rbp+var_50], r14d
0x180002dd3  jz      short loc_180002E1D
0x180002dd5  mov     eax, [rbx+10h]
0x180002dd8  mov     [rsi], eax
0x180002dda  mov     edi, r14d
0x180002ddd  mov     eax, edi
0x180002ddf  mov     rcx, [rbp+var_10]
0x180002de3  xor     rcx, rsp; StackCookie
0x180002de6  call    __security_check_cookie
0x180002deb  mov     rbx, [rsp+70h+arg_18]
0x180002df3  add     rsp, 70h
0x180002df7  pop     r15
0x180002df9  pop     r14
0x180002dfb  pop     r13
0x180002dfd  pop     r12
0x180002dff  pop     rdi
0x180002e00  pop     rsi
0x180002e01  pop     rbp
0x180002e02  retn
0x180002e03  mov     rcx, [rbx+18h]
0x180002e07  mov     rdx, [rbp+String2]; String2
0x180002e0b  mov     rcx, [rcx+r14+20h]; String1
0x180002e10  call    cs:__imp__wcsicmp
0x180002e16  xor     r14d, r14d
0x180002e19  test    eax, eax
0x180002e1b  jz      short loc_180002DD5
0x180002e1d  mov     r15d, [rbp+var_4C]
0x180002e21  inc     r12d
0x180002e24  cmp     r12d, [rbx+20h]
0x180002e28  jb      loc_180002C7F
0x180002e2e  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002e35  mov     rax, [rcx]
0x180002e38  mov     rax, [rax+18h]
0x180002e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e41  xor     r12d, r12d
0x180002e44  cmp     [rbx+40h], r12d
0x180002e48  jbe     short loc_180002EA8
0x180002e4a  mov     rdx, [rbx+38h]
0x180002e4e  lea     r8, [rbp+var_50]; int *
0x180002e52  mov     eax, r14d
0x180002e55  imul    rcx, rax, 38h ; '8'
0x180002e59  mov     [rbp+var_50], r12d
0x180002e5d  test    r15d, r15d
0x180002e60  jnz     short loc_180002E7E
0x180002e62  add     rdx, rcx; struct STRU *
0x180002e65  mov     rcx, r13; struct IHttpUser *
0x180002e68  call    ?CheckTokenMembershipForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVIHttpUser@@PEAVSTRU@@PEAH@Z; URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(IHttpUser *,STRU *,int *)
0x180002e6d  mov     edi, eax
0x180002e6f  test    eax, eax
0x180002e71  jns     short loc_180002E99
0x180002e73  cmp     [rbx+10h], r12d
0x180002e77  jnz     short loc_180002EAE
0x180002e79  mov     edi, r12d
0x180002e7c  jmp     short loc_180002E9F
0x180002e7e  mov     rax, [r13+0]
0x180002e82  mov     rdx, [rcx+rdx+20h]
0x180002e87  mov     rcx, r13
0x180002e8a  mov     rax, [rax+48h]
0x180002e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e93  mov     edi, eax
0x180002e95  test    eax, eax
0x180002e97  js      short loc_180002EAE
0x180002e99  cmp     [rbp+var_50], r12d
0x180002e9d  jnz     short loc_180002EC6
0x180002e9f  inc     r14d
0x180002ea2  cmp     r14d, [rbx+40h]
0x180002ea6  jb      short loc_180002E4A
0x180002ea8  mov     dword ptr [rsi], 2
0x180002eae  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002eb5  mov     rax, [rcx]
0x180002eb8  mov     rax, [rax+20h]
0x180002ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec1  jmp     loc_180002DDD
0x180002ec6  mov     eax, [rbx+10h]
0x180002ec9  mov     edi, r12d
0x180002ecc  mov     [rsi], eax
0x180002ece  jmp     short loc_180002EAE
```
