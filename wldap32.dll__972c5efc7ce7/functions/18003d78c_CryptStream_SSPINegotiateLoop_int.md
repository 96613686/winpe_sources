# CryptStream::SSPINegotiateLoop(int)

- ea: `0x18003d78c`
- end: `0x18003de08`
- name: `?SSPINegotiateLoop@CryptStream@@AEAAJH@Z`
- size: `1660`
- prototype: `__int64 __fastcall(CryptStream *__hidden this, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800191d0`
- `0x18003d43c`

## callees

- `0x1800037a8`
- `0x18001ce90`
- `0x18001da40`
- `0x18001ef10`
- `0x18002b5a4`
- `0x180031a10`
- `0x180032bd8`
- `0x180034510`
- `0x180034e6c`
- `0x18003d78c`
- `0x18003de10`
- `0x18004c76c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d87b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d87b`

## string_xrefs

- `0x18003ddc3`: `SSPINegotiateLoop: bailing out due to SEC_I_INCOMPLETE_CREDENTIALS\n`

## pseudocode

```c
__int64 __fastcall CryptStream::SSPINegotiateLoop(CryptStream *this)
{
  __int64 v1; // rax
  bool v3; // cf
  char *v4; // rcx
  unsigned int v5; // esi
  __int64 v6; // rax
  __int64 v8; // rax
  int v9; // r13d
  int v10; // r14d
  int v11; // r12d
  char *v12; // r15
  int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // r9
  bool v18; // zf
  unsigned __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  unsigned int (__fastcall *v23)(char *, _DWORD *, _QWORD, _QWORD); // rax
  __int64 v24; // rax
  _QWORD *v25; // r14
  __int64 v26; // rcx
  char v27; // al
  __int64 v28; // rcx
  char v29; // bl
  __int64 v30; // rax
  _DWORD *v31; // rcx
  __int64 v32; // rax
  unsigned int v33[2]; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+28h] [rbp-D8h]
  char *v35; // [rsp+38h] [rbp-C8h]
  int v36; // [rsp+70h] [rbp-90h]
  _DWORD v37[2]; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  unsigned int v41; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+9Ch] [rbp-64h] BYREF
  int v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A4h] [rbp-5Ch]
  unsigned int len[2]; // [rsp+A8h] [rbp-58h] BYREF
  char *buf; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v48; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v49; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v50; // [rsp+D8h] [rbp-28h] BYREF
  char *v51; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD v52[2]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD *v53; // [rsp+F8h] [rbp-8h]
  _DWORD v54[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 *v55; // [rsp+110h] [rbp+10h]
  int v56; // [rsp+134h] [rbp+34h]
  _DWORD v57[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 *v58; // [rsp+158h] [rbp+58h]
  int v59; // [rsp+198h] [rbp+98h]
  _DWORD v60[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v61[7]; // [rsp+1A8h] [rbp+A8h]

  v1 = *((_QWORD *)this + 2);
  v42 = 0;
  v41 = 0;
  v50 = 0;
  v49 = 0;
  v3 = *(_QWORD *)(v1 + 792) != 0;
  *((_QWORD *)&v49 + 1) = len;
  v4 = (char *)*((_QWORD *)this + 27);
  *(_QWORD *)&v49 = 0x100000000LL;
  v5 = v3 ? 49436 : 49438;
  *((_QWORD *)&v50 + 1) = v37;
  *(_QWORD *)&v50 = 0x200000000LL;
  if ( !v4 )
  {
    v6 = ldapMalloc(SspiMaxTokenSize, 1667593036);
    *((_QWORD *)this + 27) = v6;
    v4 = (char *)v6;
    if ( !v6 )
      return 8;
  }
  v8 = *((unsigned int *)this + 56);
  v9 = 0;
  v10 = 2;
  Src = v4;
  v11 = SspiMaxTokenSize - v8;
  v43 = 0;
  v12 = &v4[v8];
  v36 = 0;
  v37[0] = v8;
  v37[1] = 2;
  AcquireSRWLockExclusive((PSRWLOCK)this + 6);
  v51 = (char *)this + 48;
  v13 = 590610;
  while ( 1 )
  {
LABEL_5:
    if ( v13 != 590610 && v13 != -2146893032 && v13 != 590624 )
      goto LABEL_65;
    while ( 1 )
    {
      if ( !v37[0] && v13 != 590624 || v13 == -2146893032 )
      {
        if ( v9 )
        {
          if ( (unsigned int)CryptStream::SslBlockingReceive(this, v12, v11, &v41) )
            goto LABEL_59;
          v14 = v41;
          *((_DWORD *)this + 56) += v41;
          v12 += v14;
          v11 -= v14;
          v37[0] += v14;
        }
        else
        {
          v36 = 1;
        }
      }
      v15 = *((_QWORD *)this + 3);
      v40 = 0;
      buf = 0;
      LODWORD(v35) = 0;
      len[0] = 0;
      v39 = 0;
      len[1] = 2;
      LODWORD(v34) = 16;
      v33[0] = 0;
      v16 = (*(__int64 (__fastcall **)(char *, char *, _QWORD, _QWORD, unsigned int *, __int64, __int128 *, char *, _QWORD, __int128 *, int *, char *))(v15 + 48))(
              (char *)this + 56,
              (char *)this + 72,
              0,
              v5,
              *(unsigned int **)v33,
              v34,
              &v50,
              v35,
              0,
              &v49,
              &v42,
              (char *)this + 88);
      v13 = v16;
      if ( v16 && v16 != 590610 )
      {
        if ( v16 >= 0 )
          break;
        if ( (v42 & 0x4000) == 0 )
          goto LABEL_49;
      }
      if ( len[0] && buf )
      {
        if ( LdapSendRaw(*((struct ldap_connection **)this + 2), buf, len[0], 0, 0) )
          goto LABEL_59;
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 3) + 128LL))(buf);
        buf = 0;
        len[0] = 0;
      }
      if ( v13 )
        break;
      if ( HIDWORD(v39) != 5 )
      {
        v37[0] = 0;
        *((_DWORD *)this + 56) = 0;
        goto LABEL_56;
      }
      ldap_MoveMemory(Src, (char *)Src + (unsigned int)(v37[0] - v39), (unsigned int)v39);
      v18 = g_fTracingOn == (_DWORD)v17;
      v19 = (unsigned int)v39;
      v37[0] = v39;
      *((_DWORD *)this + 56) = v39;
      if ( !v18 && g_fProviderEnabled != (_DWORD)v17 && (g_ulTraceFlags & 0x20) != 0 )
      {
        LDAPClientPrint(32, "Received Extra Buffer After ISC Call, ExtraBufferDataSize: 0x%n", (_DWORD *)v19);
        v17 = 0;
      }
      v20 = *((_QWORD *)this + 24);
      if ( v20 )
      {
        memcpy_0(*(void **)(v20 + 8), Src, *((unsigned int *)this + 56));
        **((_DWORD **)this + 24) = v37[0];
        *(_DWORD *)(*((_QWORD *)this + 24) + 4LL) = 5;
LABEL_56:
        v32 = *((_QWORD *)this + 2);
        v48 = 0;
        if ( *(_QWORD *)(v32 + 792) )
        {
          v13 = (*(__int64 (__fastcall **)(char *, __int64, __int64 *, _QWORD))(*((_QWORD *)this + 3) + 88LL))(
                  (char *)this + 72,
                  83,
                  &v48,
                  0);
          if ( !v13
            && !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64 *))(*((_QWORD *)this + 2) + 792LL))(
                  *(_QWORD *)(*((_QWORD *)this + 2) + 448LL),
                  &v48) )
          {
LABEL_59:
            v13 = -2146893052;
          }
        }
        goto LABEL_65;
      }
      v60[0] = *((_DWORD *)this + 56);
      v21 = 1;
      v61[0] = Src;
      v22 = 4;
      v60[1] = 1;
      do
      {
        ++v21;
        v61[v22 / 2] = v17;
        *(_QWORD *)&v60[v22] = 0;
        v22 += 4LL;
      }
      while ( v21 != 4 );
      v52[1] = 4;
      v53 = v60;
      v23 = (unsigned int (__fastcall *)(char *, _DWORD *, _QWORD, _QWORD))*((_QWORD *)this + 1);
      v52[0] = v17;
      if ( v23((char *)this + 72, v52, 0, 0) != 590625 )
        goto LABEL_56;
      v13 = 590610;
LABEL_34:
      v9 = v36;
    }
    if ( v13 == 590624 )
      break;
    if ( v13 < 0 )
    {
LABEL_49:
      if ( v13 != -2146893032 )
        goto LABEL_65;
    }
    v9 = v36;
    if ( v13 != -2146893032 )
    {
      if ( HIDWORD(v39) == 5 )
      {
        ldap_MoveMemory(Src, (char *)Src + (unsigned int)(v37[0] - v39), (unsigned int)v39);
        v12 = (char *)(*((_QWORD *)this + 27) + (unsigned int)v39);
        v11 = SspiMaxTokenSize - v39;
        v37[0] = v39;
        *((_DWORD *)this + 56) = v39;
      }
      else
      {
        v12 = (char *)*((_QWORD *)this + 27);
        v11 = SspiMaxTokenSize;
        v37[0] = 0;
        *((_DWORD *)this + 56) = 0;
      }
    }
  }
  if ( !v10 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
      LDAPClientTraceEvent(32, (__int64)"SSPINegotiateLoop: bailing out due to SEC_I_INCOMPLETE_CREDENTIALS\n");
    v13 = -2146893042;
    goto LABEL_65;
  }
  v24 = *((_QWORD *)this + 2);
  v44 = --v10;
  if ( !*(_QWORD *)(v24 + 784) || v43 )
    goto LABEL_47;
  v25 = (_QWORD *)((char *)this + 144);
  v13 = (*(__int64 (__fastcall **)(char *, __int64, char *, _QWORD))(*((_QWORD *)this + 3) + 88LL))(
          (char *)this + 72,
          89,
          (char *)this + 144,
          0);
  if ( v13 )
    goto LABEL_65;
  v26 = *((_QWORD *)this + 2);
  v47 = 0;
  v27 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64 *))(v26 + 784))(
          *(_QWORD *)(v26 + 448),
          (char *)this + 144,
          &v47);
  v28 = *((_QWORD *)this + 3);
  v29 = v27;
  v43 = 1;
  (*(void (__fastcall **)(_QWORD))(v28 + 128))(*v25);
  *((_DWORD *)this + 38) = 0;
  *v25 = 0;
  if ( !v29 )
  {
    v10 = v44;
    v5 |= 0x80u;
    v13 = 590624;
    goto LABEL_34;
  }
  CryptStream::FreeCredentialIfNeeded(this);
  memset_0(v57, 0, 0x50u);
  memset_0(v54, 0, 0x48u);
  v30 = *((_QWORD *)this + 2);
  if ( GlobalDisableTLS13 )
  {
    v57[0] = 4;
    v31 = v57;
    v59 = *(_DWORD *)(v30 + 776);
    v58 = &v47;
    v57[1] = 1;
  }
  else
  {
    v54[0] = 5;
    v31 = v54;
    v56 = *(_DWORD *)(v30 + 776);
    v55 = &v47;
    v54[2] = 1;
  }
  v35 = (char *)this + 56;
  HIDWORD(v34) = 0;
  v33[1] = HIDWORD(v31);
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*((_QWORD *)this + 3) + 24LL))(
          0,
          *(_QWORD *)(SspiPackageSslPct + 16),
          2);
  if ( !v13 )
  {
    v10 = v44;
    v13 = 590624;
LABEL_47:
    v9 = v36;
    v5 |= 0x80u;
    goto LABEL_5;
  }
LABEL_65:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v51);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18003d78c  push    rbp
0x18003d78e  push    rbx
0x18003d78f  push    rsi
0x18003d790  push    rdi
0x18003d791  push    r12
0x18003d793  push    r13
0x18003d795  push    r14
0x18003d797  push    r15
0x18003d799  lea     rbp, [rsp-0F8h]
0x18003d7a1  sub     rsp, 1F8h
0x18003d7a8  mov     rax, cs:__security_cookie
0x18003d7af  xor     rax, rsp
0x18003d7b2  mov     [rbp+130h+var_50], rax
0x18003d7b9  mov     rax, [rcx+10h]
0x18003d7bd  xor     ebx, ebx
0x18003d7bf  mov     rdi, rcx
0x18003d7c2  mov     [rbp+130h+var_194], ebx
0x18003d7c5  xorps   xmm0, xmm0
0x18003d7c8  mov     [rbp+130h+var_198], ebx
0x18003d7cb  movups  [rbp+130h+var_158], xmm0
0x18003d7cf  xorps   xmm1, xmm1
0x18003d7d2  movups  [rbp+130h+var_168], xmm1
0x18003d7d6  mov     rcx, [rax+318h]
0x18003d7dd  lea     rax, [rbp+130h+len]
0x18003d7e1  neg     rcx
0x18003d7e4  mov     qword ptr [rbp+130h+var_168+8], rax
0x18003d7e8  mov     rcx, [rdi+0D8h]
0x18003d7ef  lea     rax, [rsp+230h+var_1B8]
0x18003d7f4  sbb     esi, esi
0x18003d7f6  mov     dword ptr [rbp+130h+var_168+4], 1
0x18003d7fd  and     esi, 0FFFFFFFEh
0x18003d800  mov     dword ptr [rbp+130h+var_168], ebx
0x18003d803  add     esi, 0C11Eh
0x18003d809  mov     dword ptr [rbp+130h+var_158+4], 2
0x18003d810  mov     qword ptr [rbp+130h+var_158+8], rax
0x18003d814  mov     dword ptr [rbp+130h+var_158], ebx
0x18003d817  test    rcx, rcx
0x18003d81a  jnz     short loc_18003D843
0x18003d81c  mov     ecx, cs:SspiMaxTokenSize
0x18003d822  mov     edx, 6365734Ch
0x18003d827  call    ldapMalloc
0x18003d82c  mov     [rdi+0D8h], rax
0x18003d833  mov     rcx, rax
0x18003d836  test    rax, rax
0x18003d839  jnz     short loc_18003D843
0x18003d83b  lea     eax, [rbx+8]
0x18003d83e  jmp     loc_18003DDE4
0x18003d843  mov     eax, [rdi+0E0h]
0x18003d849  mov     r13d, ebx
0x18003d84c  mov     r12d, cs:SspiMaxTokenSize
0x18003d853  mov     r14d, 2
0x18003d859  mov     [rbp+130h+Src], rcx
0x18003d85d  sub     r12d, eax
0x18003d860  mov     [rbp+130h+var_190], ebx
0x18003d863  lea     r15, [rcx+rax]
0x18003d867  mov     [rsp+230h+var_1C0], ebx
0x18003d86b  lea     rbx, [rdi+30h]
0x18003d86f  mov     [rsp+230h+var_1B8], eax
0x18003d873  mov     rcx, rbx; SRWLock
0x18003d876  mov     [rsp+230h+var_1B4], r14d
0x18003d87b  call    cs:__imp_AcquireSRWLockExclusive
0x18003d882  nop     dword ptr [rax+rax+00h]
0x18003d887  mov     [rbp+130h+var_148], rbx
0x18003d88b  mov     ebx, 90312h
0x18003d890  xor     r9d, r9d
0x18003d893  cmp     ebx, 90312h
0x18003d899  jz      short loc_18003D8AF
0x18003d89b  cmp     ebx, 80090318h
0x18003d8a1  jz      short loc_18003D8AF
0x18003d8a3  cmp     ebx, 90320h
0x18003d8a9  jnz     loc_18003DDD9
0x18003d8af  cmp     [rsp+230h+var_1B8], r9d
0x18003d8b4  jnz     short loc_18003D8BE
0x18003d8b6  cmp     ebx, 90320h
0x18003d8bc  jnz     short loc_18003D8C6
0x18003d8be  cmp     ebx, 80090318h
0x18003d8c4  jnz     short loc_18003D905
0x18003d8c6  test    r13d, r13d
0x18003d8c9  jz      short loc_18003D8FD
0x18003d8cb  lea     r9, [rbp+130h+var_198]; unsigned int *
0x18003d8cf  mov     r8d, r12d; unsigned int
0x18003d8d2  mov     rdx, r15; unsigned __int8 *
0x18003d8d5  mov     rcx, rdi; this
0x18003d8d8  call    ?SslBlockingReceive@CryptStream@@QEAAKPEAEKPEAK@Z; CryptStream::SslBlockingReceive(uchar *,ulong,ulong *)
0x18003d8dd  xor     r9d, r9d
0x18003d8e0  test    eax, eax
0x18003d8e2  jnz     loc_18003DDA1
0x18003d8e8  mov     ecx, [rbp+130h+var_198]
0x18003d8eb  add     [rdi+0E0h], ecx
0x18003d8f1  add     r15, rcx
0x18003d8f4  sub     r12d, ecx
0x18003d8f7  add     [rsp+230h+var_1B8], ecx
0x18003d8fb  jmp     short loc_18003D905
0x18003d8fd  mov     [rsp+230h+var_1C0], 1
0x18003d905  mov     rax, [rdi+18h]
0x18003d909  lea     rcx, [rdi+58h]
0x18003d90d  mov     [rsp+230h+var_1D8], rcx
0x18003d912  lea     r13, [rdi+48h]
0x18003d916  mov     [rbp+130h+var_1A0], r9
0x18003d91a  lea     rcx, [rbp+130h+var_194]
0x18003d91e  mov     [rsp+230h+var_1E0], rcx
0x18003d923  xor     r8d, r8d
0x18003d926  mov     [rbp+130h+buf], r9
0x18003d92a  lea     rcx, [rbp+130h+var_168]
0x18003d92e  mov     [rsp+230h+var_1E8], rcx
0x18003d933  mov     rdx, r13
0x18003d936  mov     [rsp+230h+var_1F0], r9
0x18003d93b  lea     rcx, [rbp+130h+var_158]
0x18003d93f  mov     dword ptr [rsp+230h+var_1F8], r9d
0x18003d944  mov     [rsp+230h+var_200], rcx
0x18003d949  lea     rcx, [rdi+38h]
0x18003d94d  mov     [rbp+130h+len], r9d
0x18003d951  mov     [rbp+130h+var_1A8], 0
0x18003d959  mov     [rbp+130h+var_184], 2
0x18003d960  mov     rax, [rax+30h]
0x18003d964  mov     dword ptr [rsp+230h+var_208], 10h
0x18003d96c  mov     [rsp+230h+var_210], r9d
0x18003d971  mov     r9d, esi
0x18003d974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d979  xor     r9d, r9d; char *
0x18003d97c  mov     ebx, eax
0x18003d97e  test    eax, eax
0x18003d980  jz      short loc_18003D99E
0x18003d982  cmp     eax, 90312h
0x18003d987  jz      short loc_18003D99E
0x18003d989  test    eax, eax
0x18003d98b  jns     loc_18003DAE4
0x18003d991  test    [rbp+130h+var_194], 4000h
0x18003d998  jz      loc_18003DC94
0x18003d99e  mov     r8d, [rbp+130h+len]; len
0x18003d9a2  test    r8d, r8d
0x18003d9a5  jz      short loc_18003D9E5
0x18003d9a7  mov     rdx, [rbp+130h+buf]; buf
0x18003d9ab  test    rdx, rdx
0x18003d9ae  jz      short loc_18003D9E5
0x18003d9b0  mov     rcx, [rdi+10h]; struct ldap_connection *
0x18003d9b4  mov     [rsp+230h+var_210], r9d; unsigned int
0x18003d9b9  call    ?LdapSendRaw@@YAKPEAUldap_connection@@PEADK1K@Z; LdapSendRaw(ldap_connection *,char *,ulong,char *,ulong)
0x18003d9be  test    eax, eax
0x18003d9c0  jnz     loc_18003DDA1
0x18003d9c6  mov     rax, [rdi+18h]
0x18003d9ca  mov     rcx, [rbp+130h+buf]
0x18003d9ce  mov     rax, [rax+80h]
0x18003d9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9da  xor     r9d, r9d
0x18003d9dd  mov     [rbp+130h+buf], r9
0x18003d9e1  mov     [rbp+130h+len], r9d
0x18003d9e5  test    ebx, ebx
0x18003d9e7  jnz     loc_18003DAE4
0x18003d9ed  cmp     dword ptr [rbp+130h+var_1A8+4], 5
0x18003d9f1  jnz     loc_18003DD46
0x18003d9f7  mov     edx, [rsp+230h+var_1B8]
0x18003d9fb  mov     r8d, dword ptr [rbp+130h+var_1A8]
0x18003d9ff  sub     edx, r8d
0x18003da02  mov     rcx, [rbp+130h+Src]
0x18003da06  add     rdx, rcx
0x18003da09  call    ldap_MoveMemory
0x18003da0e  cmp     cs:g_fTracingOn, r9d
0x18003da15  mov     r8d, dword ptr [rbp+130h+var_1A8]
0x18003da19  mov     [rsp+230h+var_1B8], r8d
0x18003da1e  mov     [rdi+0E0h], r8d
0x18003da25  jz      short loc_18003DA4B
0x18003da27  cmp     cs:g_fProviderEnabled, r9d
0x18003da2e  jz      short loc_18003DA4B
0x18003da30  test    byte ptr cs:g_ulTraceFlags, 20h
0x18003da37  jz      short loc_18003DA4B
0x18003da39  lea     rdx, aReceivedExtraB; "Received Extra Buffer After ISC Call, E"...
0x18003da40  lea     ecx, [rbx+20h]
0x18003da43  call    LDAPClientPrint
0x18003da48  xor     r9d, r9d
0x18003da4b  mov     rcx, [rdi+0C0h]
0x18003da52  mov     eax, [rdi+0E0h]
0x18003da58  test    rcx, rcx
0x18003da5b  jnz     loc_18003DD16
0x18003da61  lea     edx, [rcx+1]
0x18003da64  mov     dword ptr [rbp+130h+var_90], eax
0x18003da6a  mov     rax, [rbp+130h+Src]
0x18003da6e  mov     ecx, edx
0x18003da70  mov     [rbp+130h+var_88], rax
0x18003da77  lea     eax, [rdx+0Fh]
0x18003da7a  mov     dword ptr [rbp+130h+var_90+4], edx
0x18003da80  add     rcx, rdx
0x18003da83  mov     [rbp+rax+130h+var_88], r9
0x18003da8b  mov     [rbp+rax+130h+var_90], 0
0x18003da97  lea     rax, [rax+10h]
0x18003da9b  cmp     rcx, 4
0x18003da9f  jnz     short loc_18003DA80
0x18003daa1  lea     rax, [rbp+130h+var_90]
0x18003daa8  mov     [rbp+130h+var_13C], ecx
0x18003daab  mov     [rbp+130h+var_138], rax
0x18003daaf  lea     rdx, [rbp+130h+var_140]
0x18003dab3  mov     rax, [rdi+8]
0x18003dab7  xor     r8d, r8d
0x18003daba  mov     [rbp+130h+var_140], r9d
0x18003dabe  mov     rcx, r13
0x18003dac1  xor     r9d, r9d
0x18003dac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dac9  xor     r9d, r9d
0x18003dacc  cmp     eax, 90321h
0x18003dad1  jnz     loc_18003DD52
0x18003dad7  lea     ebx, [rax-0Fh]
0x18003dada  mov     r13d, [rsp+230h+var_1C0]
0x18003dadf  jmp     loc_18003D8AF
0x18003dae4  cmp     ebx, 90320h
0x18003daea  jnz     loc_18003DC90
0x18003daf0  test    r14d, r14d
0x18003daf3  jz      loc_18003DDA8
0x18003daf9  mov     rax, [rdi+10h]
0x18003dafd  dec     r14d
0x18003db00  mov     [rbp+130h+var_18C], r14d
0x18003db04  cmp     [rax+310h], r9
0x18003db0b  jz      loc_18003DC82
0x18003db11  cmp     [rbp+130h+var_190], r9d
0x18003db15  jnz     loc_18003DC82
0x18003db1b  mov     rax, [rdi+18h]
0x18003db1f  lea     r14, [rdi+90h]
0x18003db26  mov     r8, r14
0x18003db29  mov     edx, 59h ; 'Y'
0x18003db2e  mov     rcx, r13
0x18003db31  mov     rax, [rax+58h]
0x18003db35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db3a  mov     ebx, eax
0x18003db3c  test    eax, eax
0x18003db3e  jnz     loc_18003DDD9
0x18003db44  mov     rcx, [rdi+10h]
0x18003db48  lea     r8, [rbp+130h+var_178]
0x18003db4c  mov     [rbp+130h+var_178], 0
0x18003db54  mov     rdx, r14
0x18003db57  mov     rax, [rcx+310h]
0x18003db5e  mov     rcx, [rcx+1C0h]
0x18003db65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db6a  mov     rcx, [rdi+18h]
0x18003db6e  mov     bl, al
0x18003db70  mov     [rbp+130h+var_190], 1
0x18003db77  mov     rax, [rcx+80h]
0x18003db7e  mov     rcx, [r14]
0x18003db81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db86  xor     r9d, r9d
0x18003db89  mov     [rdi+98h], r9d
0x18003db90  mov     [r14], r9
0x18003db93  test    bl, bl
0x18003db95  jnz     short loc_18003DBA9
0x18003db97  mov     r14d, [rbp+130h+var_18C]
0x18003db9b  bts     esi, 7
0x18003db9f  mov     ebx, 90320h
0x18003dba4  jmp     loc_18003DADA
0x18003dba9  mov     rcx, rdi; this
0x18003dbac  call    ?FreeCredentialIfNeeded@CryptStream@@AEAAXXZ; CryptStream::FreeCredentialIfNeeded(void)
0x18003dbb1  xor     edx, edx; Val
0x18003dbb3  lea     rcx, [rbp+130h+var_E0]; void *
0x18003dbb7  lea     r8d, [rdx+50h]; Size
0x18003dbbb  call    memset_0
0x18003dbc0  xor     edx, edx; Val
0x18003dbc2  lea     rcx, [rbp+130h+var_130]; void *
0x18003dbc6  lea     r8d, [rdx+48h]; Size
0x18003dbca  call    memset_0
0x18003dbcf  mov     rax, [rdi+10h]
0x18003dbd3  xor     r8d, r8d
0x18003dbd6  cmp     cs:GlobalDisableTLS13, r8b
0x18003dbdd  jz      short loc_18003DC07
0x18003dbdf  mov     [rbp+130h+var_E0], 4
0x18003dbe6  lea     rcx, [rbp+130h+var_E0]
0x18003dbea  mov     eax, [rax+308h]
0x18003dbf0  mov     [rbp+130h+var_98], eax
0x18003dbf6  lea     rax, [rbp+130h+var_178]
0x18003dbfa  mov     [rbp+130h+var_D8], rax
0x18003dbfe  mov     [rbp+130h+var_DC], 1
0x18003dc05  jmp     short loc_18003DC2A
0x18003dc07  mov     [rbp+130h+var_130], 5
0x18003dc0e  lea     rcx, [rbp+130h+var_130]
0x18003dc12  mov     eax, [rax+308h]
0x18003dc18  mov     [rbp+130h+var_FC], eax
0x18003dc1b  lea     rax, [rbp+130h+var_178]
0x18003dc1f  mov     [rbp+130h+var_120], rax
0x18003dc23  mov     [rbp+130h+var_128], 1
0x18003dc2a  mov     rax, [rdi+18h]
0x18003dc2e  lea     rdx, [rdi+58h]
0x18003dc32  mov     [rsp+230h+var_1F0], rdx
0x18003dc37  xor     r9d, r9d
0x18003dc3a  lea     rdx, [rdi+38h]
0x18003dc3e  mov     [rsp+230h+var_1F8], rdx
0x18003dc43  mov     rdx, cs:SspiPackageSslPct
0x18003dc4a  mov     rax, [rax+18h]
0x18003dc4e  mov     [rsp+230h+var_200], r8
0x18003dc53  mov     [rsp+230h+var_208], r8
0x18003dc58  lea     r8d, [r9+2]
0x18003dc5c  mov     rdx, [rdx+10h]
0x18003dc60  mov     qword ptr [rsp+230h+var_210], rcx
0x18003dc65  xor     ecx, ecx
0x18003dc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc6c  xor     r9d, r9d
0x18003dc6f  mov     ebx, eax
0x18003dc71  test    eax, eax
0x18003dc73  jnz     loc_18003DDD9
0x18003dc79  mov     r14d, [rbp+130h+var_18C]
0x18003dc7d  mov     ebx, 90320h
0x18003dc82  mov     r13d, [rsp+230h+var_1C0]
0x18003dc87  bts     esi, 7
0x18003dc8b  jmp     loc_18003D893
0x18003dc90  test    ebx, ebx
  ... truncated ...
```
