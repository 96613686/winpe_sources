# CryptStream::UnSignAndSealLdapStream(ldap_recvbuffer *)

- ea: `0x18001c2d0`
- end: `0x18001ce7e`
- name: `?UnSignAndSealLdapStream@CryptStream@@AEAAKPEAUldap_recvbuffer@@@Z`
- size: `2990`
- prototype: `unsigned int __fastcall(CryptStream *__hidden this, struct ldap_recvbuffer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800191d0`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x180018cc0`
- `0x18001ad5c`
- `0x18001c2d0`
- `0x18001ce90`
- `0x18001e800`
- `0x180032bd8`
- `0x18004c76c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c407`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c5ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c407`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c5ef`
- `WS2_32!__imp_ntohl` at `0x18001c653`
- `WS2_32!__imp_ntohl` at `0x18001c6ed`
- `WS2_32!__imp_ntohl` at `0x18001cab0`
- `WS2_32!__imp_ntohl` at `0x18001c653`
- `WS2_32!__imp_ntohl` at `0x18001c6ed`
- `WS2_32!__imp_ntohl` at `0x18001cab0`

## string_xrefs

- `0x18001cae5`: `Overflow when computing encrypted packet size.\n`
- `0x18001cbef`: `Overflow when computing encrypted packet size.\n`
- `0x18001cc22`: `Adding a new entry to the lookaside list (size = %li)\n`
- `0x18001cd5b`: `cbInboundCryptoBytesInLookasideList should be 0: it's actually %d bytes\n`
- `0x18001cb3c`: `Freeing memory at 0x%x which is already freed\n`
- `0x18001cc9f`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
__int64 __fastcall CryptStream::UnSignAndSealLdapStream(CryptStream *this, struct ldap_recvbuffer *a2)
{
  __int64 v2; // r14
  struct ldap_recvbuffer *v3; // rsi
  CryptStream *v4; // rdi
  _QWORD *v5; // r15
  _DWORD *v6; // r12
  unsigned int v7; // r8d
  unsigned int *v8; // r13
  unsigned int v9; // eax
  unsigned int *v10; // rcx
  const void **v11; // rbp
  char *v12; // rdx
  _BYTE *v13; // rax
  int v14; // r8d
  _QWORD *v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  int v18; // r9d
  int v19; // r8d
  int v20; // eax
  HANDLE v21; // rcx
  u_long *v22; // rsi
  _QWORD *v24; // rax
  __int64 v25; // rcx
  _QWORD *v26; // rdx
  _QWORD *v27; // rax
  unsigned int v28; // eax
  unsigned int v29; // r9d
  _BYTE *v30; // rax
  char *v31; // rdx
  char v32; // cl
  u_long *v33; // r12
  unsigned int v34; // r8d
  _QWORD *v35; // r9
  u_long v36; // eax
  __int64 v37; // r8
  unsigned int v38; // ecx
  _QWORD *v39; // rdi
  char *v40; // rdx
  char *v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rcx
  int v44; // eax
  int v45; // r9d
  int v46; // r8d
  int v47; // eax
  HANDLE v48; // rcx
  char *v49; // rcx
  char *i; // rdx
  char v51; // al
  _QWORD *v52; // rax
  __int64 v53; // rcx
  u_long v54; // eax
  u_long *v55; // r15
  _DWORD *v56; // r14
  u_long *v57; // rcx
  u_long v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rax
  int v61; // eax
  unsigned int v62; // ebx
  size_t v63; // rdi
  unsigned int v64; // ebx
  bool v65; // cc
  void *v66; // rsi
  __int64 v67; // rax
  __int64 v68; // rbx
  _QWORD *v69; // rax
  __int64 v70; // rcx
  unsigned int v71; // eax
  __int64 v72; // rcx
  _QWORD *v73; // rax
  __int64 v74; // rdx
  bool v75; // zf
  _QWORD *v76; // rax
  __int64 v77; // rax
  unsigned int v78; // edx
  _BYTE *v79; // r8
  int v80; // edx
  char *v81; // rcx
  char v82; // al
  _BYTE *v83; // r8
  char *j; // rcx
  char v85; // al
  char v86; // al
  char v87; // cl
  char v88; // al
  unsigned int v89; // ebx
  void *v90; // rdi
  u_long v91; // eax
  __int128 v92; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v93[2]; // [rsp+40h] [rbp-58h] BYREF
  u_long *v94; // [rsp+48h] [rbp-50h]
  size_t Size; // [rsp+50h] [rbp-48h]
  void *Src; // [rsp+58h] [rbp-40h]
  u_long *v98; // [rsp+A8h] [rbp+10h]

  v2 = *((unsigned int *)a2 + 6);
  v3 = a2;
  v4 = this;
  v92 = 0;
  if ( !(_DWORD)v2 )
  {
    v72 = *((_QWORD *)a2 + 1);
    v73 = (_QWORD *)*((_QWORD *)a2 + 2);
    LOBYTE(a2) = 1;
    *v73 = v72;
    *(_QWORD *)(v72 + 8) = v73;
    LdapFreeReceiveStructure(v3, a2);
    return 0;
  }
  if ( *((_BYTE *)this + 272) )
  {
    v8 = (unsigned int *)((char *)this + 264);
    if ( (int)v2 + *((_DWORD *)this + 66) >= (unsigned int)v2 )
    {
      v24 = (_QWORD *)*((_QWORD *)a2 + 2);
      v5 = (_QWORD *)((char *)this + 232);
      v25 = *((_QWORD *)a2 + 1);
      v26 = (_QWORD *)((char *)a2 + 8);
      *v24 = v25;
      *(_QWORD *)(v25 + 8) = v24;
      v27 = (_QWORD *)*((_QWORD *)v4 + 30);
      *v26 = (char *)v4 + 232;
      *((_QWORD *)v3 + 2) = v27;
      *v27 = v26;
      *((_QWORD *)v4 + 30) = v26;
      *v8 += v2;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
        LDAPClientPrint(32, "Adding a new entry to the lookaside list (size = %li)\n", v2);
      goto LABEL_20;
    }
    return 82;
  }
  v5 = (_QWORD *)((char *)this + 232);
  if ( (_QWORD *)*v5 != v5 )
    return 82;
  v6 = (_DWORD *)((char *)this + 260);
  v7 = *((_DWORD *)this + 65);
  v8 = (unsigned int *)((char *)this + 264);
  v9 = *((_DWORD *)this + 64) - v7;
  *((_DWORD *)this + 66) = 0;
  v10 = (unsigned int *)((char *)this + 260);
  if ( v9 < (unsigned int)v2 )
  {
    v71 = v7 + v2;
    if ( v7 + (unsigned int)v2 < v7 || (v89 = v71 + 0x2000, v71 + 0x2000 < v71) )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
        LDAPClientPrint(
          0x10000000,
          "CryptStream::CheckInboundSpace: integer overflow. InboundCryptoBytes 0x%x, BytesNeeded 0x%x\n",
          v7,
          v2);
      return 90;
    }
    v90 = (void *)ldapMalloc(v89, 1667593036);
    if ( !v90 )
      return 90;
    v11 = (const void **)((char *)this + 248);
    if ( *v6 )
      memcpy_0(v90, *v11, (unsigned int)*v6);
    ldapFree(*v11, 1667593036);
    *v11 = v90;
    v4 = this;
    *((_DWORD *)this + 64) = v89;
    v10 = (unsigned int *)((char *)this + 260);
  }
  else
  {
    v11 = (const void **)((char *)v4 + 248);
  }
  v12 = (char *)v3 + 36;
  v13 = (char *)*v11 + *v10;
  v14 = v2;
  if ( v13 > (_BYTE *)v3 + 36 )
  {
    v30 = &v13[v2];
    v31 = &v12[v2];
    do
    {
      v32 = *--v31;
      *--v30 = v32;
      --v14;
    }
    while ( v14 );
  }
  else if ( v13 != (char *)v3 + 36 )
  {
    do
    {
      v87 = *v12++;
      *v13++ = v87;
      --v14;
    }
    while ( v14 );
  }
  *v6 += v2;
  v15 = (_QWORD *)*((_QWORD *)v3 + 2);
  v16 = *((_QWORD *)v3 + 1);
  *v15 = v16;
  *(_QWORD *)(v16 + 8) = v15;
  if ( _InterlockedExchange64((volatile __int64 *)v3, 0) )
  {
    v69 = (_QWORD *)*((_QWORD *)v3 + 2);
    v70 = *((_QWORD *)v3 + 1);
    *v69 = v70;
    *(_QWORD *)(v70 + 8) = v69;
  }
  v17 = *((_DWORD *)v3 - 2);
  if ( v17 == 1684095564 )
    goto LABEL_16;
  if ( v17 != 1701987916 )
    goto LABEL_12;
  if ( g_fTracingOn )
  {
    if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)v3);
LABEL_12:
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
        *((_DWORD *)v3 - 1),
        (_DWORD)v3 - 8,
        1667584588);
  }
  v18 = *((_DWORD *)v3 - 2);
  if ( v18 != 1667584588 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1667584588, v18);
  v19 = *((_DWORD *)v3 - 1);
  v20 = LdapAllocatedHeap - v19;
  LdapAllocatedHeap -= v19;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    LDAPClientPrint(8, "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", v19, (_DWORD)v3, 1667584588, v20);
  v21 = LdapHeap;
  *((_DWORD *)v3 - 2) = 1701987916;
  HeapFree(v21, 0, (char *)v3 - 8);
LABEL_16:
  v22 = (u_long *)((char *)v4 + 260);
  if ( *((_DWORD *)v4 + 65) < 4u )
    return 0;
  v54 = ntohl(*(_DWORD *)*v11) + 4;
  if ( v54 < 4 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientTraceEvent(0x10000000, "Overflow when computing encrypted packet size.\n");
    v64 = 82;
    v33 = (u_long *)((char *)v4 + 268);
    v56 = (_DWORD *)((char *)v4 + 296);
    v55 = (u_long *)((char *)v4 + 300);
    goto LABEL_58;
  }
  *((_DWORD *)v4 + 67) = v54;
  *((_BYTE *)v4 + 272) = 1;
LABEL_20:
  v22 = (u_long *)((char *)v4 + 260);
  v28 = *((_DWORD *)v4 + 65);
  v98 = (u_long *)((char *)v4 + 260);
  v29 = *v8 + v28;
  if ( v29 < v28 )
    return 82;
  v33 = (u_long *)((char *)v4 + 268);
  v34 = *((_DWORD *)v4 + 67);
  if ( v34 > v29 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
      LDAPClientPrint(
        32,
        "Don't have enough data to start decrypting. Waiting for %#010x bytes, currently have %#010x bytes.\n",
        v34,
        v29);
    return 0;
  }
  if ( !CryptStream::CheckInboundSpace(v4, *v8) )
    return 90;
  while ( 1 )
  {
    v35 = (_QWORD *)*v5;
    if ( (_QWORD *)*v5 == v5 )
      break;
    v36 = *v22;
    v37 = *((unsigned int *)v35 + 4);
    v38 = v37 + *v22;
    if ( *((_DWORD *)v4 + 64) < v38 || v38 < v36 )
      return 82;
    v39 = v35 - 1;
    v40 = (char *)v35 + 28;
    v41 = (char *)(*((_QWORD *)this + 31) + v36);
    if ( v41 > v40 )
    {
      v49 = &v41[v37];
      for ( i = &v40[v37]; (_DWORD)v37; LODWORD(v37) = v37 - 1 )
      {
        v51 = *--i;
        *--v49 = v51;
      }
    }
    else if ( v41 != v40 && (_DWORD)v37 )
    {
      do
      {
        v86 = *v40++;
        *v41++ = v86;
        LODWORD(v37) = v37 - 1;
      }
      while ( (_DWORD)v37 );
    }
    *v22 += *((_DWORD *)v39 + 6);
    *v8 -= *((_DWORD *)v39 + 6);
    v42 = (_QWORD *)v35[1];
    v43 = *v35;
    *v42 = *v35;
    *(_QWORD *)(v43 + 8) = v42;
    if ( _InterlockedExchange64(v39, 0) )
    {
      v52 = (_QWORD *)v35[1];
      v53 = *v35;
      *v52 = *v35;
      *(_QWORD *)(v53 + 8) = v52;
    }
    v44 = *((_DWORD *)v35 - 4);
    if ( v44 != 1684095564 )
    {
      if ( v44 != 1701987916 )
        goto LABEL_36;
      if ( g_fTracingOn )
      {
        if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)v35 - 8);
LABEL_36:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
            *((_DWORD *)v39 - 1),
            (_DWORD)v39 - 8,
            1667584588);
      }
      v45 = *((_DWORD *)v39 - 2);
      if ( v45 != 1667584588 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1667584588, v45);
      v46 = *((_DWORD *)v39 - 1);
      v47 = LdapAllocatedHeap - v46;
      LdapAllocatedHeap -= v46;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
          v46,
          (_DWORD)v39,
          1667584588,
          v47);
      v48 = LdapHeap;
      *((_DWORD *)v39 - 2) = 1701987916;
      HeapFree(v48, 0, v39 - 1);
    }
    v4 = this;
  }
  if ( *v8 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
      LDAPClientPrint(32, "cbInboundCryptoBytesInLookasideList should be 0: it's actually %d bytes\n", *v8);
    return 82;
  }
  v55 = (u_long *)((char *)v4 + 300);
  if ( *v22 > *((_DWORD *)v4 + 75) )
    *v55 = *v22;
  v56 = (_DWORD *)((char *)v4 + 296);
  ++*((_DWORD *)v4 + 74);
  while ( 1 )
  {
    if ( !*((_BYTE *)v4 + 272) || !*v22 || *v33 > *v22 )
      return 0;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
    {
      LDAPClientPrint(32, "CurrentMessageSize is  %d bytes\n", *v33);
      LDAPClientPrint(32, "Total size of inbound buffer is  %d bytes\n", *v22);
    }
    v11 = (const void **)((char *)v4 + 248);
    v57 = (u_long *)*((_QWORD *)v4 + 31);
    v94 = v57 + 1;
    v58 = ntohl(*v57);
    v59 = *((_QWORD *)v4 + 2);
    v93[0] = v58;
    v93[1] = 10;
    *((_QWORD *)&v92 + 1) = v93;
    v60 = *((_QWORD *)v4 + 3);
    Src = 0;
    Size = 0x100000000LL;
    *(_QWORD *)&v92 = 0x200000000LL;
    v61 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(v60 + 208))(v59 + 216, &v92, 0, 0);
    v62 = v61;
    if ( v61 )
      break;
    v63 = (unsigned int)Size;
    if ( (unsigned int)Size >= 0xFFFFFFD8 )
    {
      v64 = 82;
LABEL_57:
      v4 = this;
      goto LABEL_58;
    }
    v66 = Src;
    v67 = ldapMalloc((unsigned int)(Size + 40), 1667584588);
    v68 = v67;
    if ( !v67 )
    {
      v22 = v98;
      v64 = 90;
      goto LABEL_57;
    }
    *(_QWORD *)v67 = *((_QWORD *)this + 2);
    *(_DWORD *)(v67 + 32) = v63;
    *(_DWORD *)(v67 + 24) = v63;
    memcpy_0((void *)(v67 + 36), v66, v63);
    v4 = this;
    v74 = *((_QWORD *)this + 2) + 40LL;
    v75 = g_fTracingOn == 0;
    v76 = *(_QWORD **)(*((_QWORD *)this + 2) + 48LL);
    *(_QWORD *)(v68 + 8) = v74;
    *(_QWORD *)(v68 + 16) = v76;
    *v76 = v68 + 8;
    *(_QWORD *)(v74 + 8) = v68 + 8;
    if ( !v75 && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
      LDAPClientPrint(32, "Actual number of decrypted bytes is %d\n", v93[0]);
    v77 = *v33;
    v22 = (u_long *)((char *)this + 260);
    v78 = *((_DWORD *)this + 65);
    v64 = 0;
    if ( v78 <= (unsigned int)v77 )
      goto LABEL_58;
    v79 = *v11;
    v80 = v78 - v77;
    v81 = (char *)*v11 + v77;
    if ( *v11 > v81 )
    {
      v83 = &v79[v80];
      for ( j = &v81[v80]; v80; --v80 )
      {
        v85 = *--j;
        *--v83 = v85;
      }
    }
    else if ( *v11 != v81 && v80 )
    {
      do
      {
        v88 = *v81++;
        *v79++ = v88;
        --v80;
      }
      while ( v80 );
    }
    *v22 -= *v33;
    if ( *v22 >= 4 )
    {
      v91 = ntohl(*(_DWORD *)*v11) + 4;
      if ( v91 < 4 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
          LDAPClientTraceEvent(0x10000000, "Overflow when computing encrypted packet size.\n");
        v64 = 82;
        goto LABEL_58;
      }
      *v33 = v91;
      v82 = 1;
    }
    else
    {
      v82 = 0;
    }
    *((_BYTE *)this + 272) = v82;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
    LDAPClientPrint(32, "wldap32: DecryptMessage couldn't decrypt.  sErr = 0x%x\n.", v61);
  v64 = LdapConvertSecurityError(*((_QWORD *)v4 + 2), v62);
LABEL_58:
  v65 = *v56 <= 0xC8u;
  *v33 = 0;
  *((_BYTE *)v4 + 272) = 0;
  *v22 = 0;
  if ( !v65 )
  {
    if ( *v55 < *((_DWORD *)v4 + 64) >> 1 )
    {
      ldapFree(*v11, 1667593036);
      *((_DWORD *)v4 + 64) = 0;
      *v11 = 0;
    }
    *v56 = 0;
    *v55 = 0;
  }
  return v64;
}

```

## disassembly

```asm
0x18001c2d0  mov     rax, rsp
0x18001c2d3  mov     [rax+8], rcx
0x18001c2d7  push    rsi
0x18001c2d8  push    rdi
0x18001c2d9  push    r14
0x18001c2db  sub     rsp, 80h
0x18001c2e2  mov     r14d, [rdx+18h]
0x18001c2e6  xorps   xmm0, xmm0
0x18001c2e9  mov     rsi, rdx
0x18001c2ec  mov     rdi, rcx
0x18001c2ef  movups  xmmword ptr [rax-68h], xmm0
0x18001c2f3  test    r14d, r14d
0x18001c2f6  jz      loc_18001C808
0x18001c2fc  cmp     byte ptr [rcx+110h], 0
0x18001c303  mov     [rax+18h], rbx
0x18001c307  mov     [rax-20h], rbp
0x18001c30b  mov     [rax-28h], r12
0x18001c30f  mov     [rax-30h], r13
0x18001c313  mov     [rax-38h], r15
0x18001c317  jnz     loc_18001C427
0x18001c31d  lea     r15, [rcx+0E8h]
0x18001c324  cmp     [r15], r15
0x18001c327  jnz     loc_18001C495
0x18001c32d  mov     eax, [rdi+100h]
0x18001c333  lea     r12, [rcx+104h]
0x18001c33a  mov     r8d, [r12]
0x18001c33e  lea     r13, [rcx+108h]
0x18001c345  sub     eax, r8d
0x18001c348  mov     dword ptr [r13+0], 0
0x18001c350  mov     rcx, r12
0x18001c353  cmp     eax, r14d
0x18001c356  jb      loc_18001C7E4
0x18001c35c  lea     rbp, [rdi+0F8h]
0x18001c363  mov     eax, [rcx]
0x18001c365  lea     rdx, [rsi+24h]
0x18001c369  add     rax, [rbp+0]
0x18001c36d  mov     r8d, r14d
0x18001c370  cmp     rax, rdx
0x18001c373  ja      loc_18001C4C3
0x18001c379  jnz     loc_18001C9D0
0x18001c37f  add     [r12], r14d
0x18001c383  mov     rax, [rsi+10h]
0x18001c387  mov     rcx, [rsi+8]
0x18001c38b  mov     [rax], rcx
0x18001c38e  mov     [rcx+8], rax
0x18001c392  xor     eax, eax
0x18001c394  xchg    rax, [rsi]
0x18001c397  test    rax, rax
0x18001c39a  jnz     loc_18001C7D0
0x18001c3a0  mov     eax, [rsi-8]
0x18001c3a3  cmp     eax, 6461424Ch
0x18001c3a8  jz      short loc_18001C413
0x18001c3aa  cmp     eax, 6572464Ch
0x18001c3af  jz      loc_18001CB12
0x18001c3b5  cmp     cs:g_fTracingOn, 0
0x18001c3bc  jnz     loc_18001CB52
0x18001c3c2  mov     r9d, [rsi-8]
0x18001c3c6  cmp     r9d, 6365524Ch
0x18001c3cd  jnz     loc_18001C966
0x18001c3d3  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001c3d9  mov     r8d, [rsi-4]
0x18001c3dd  sub     eax, r8d
0x18001c3e0  cmp     cs:g_fTracingOn, 0
0x18001c3e7  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001c3ed  jnz     loc_18001CB92
0x18001c3f3  mov     rcx, cs:LdapHeap; hHeap
0x18001c3fa  lea     r8, [rsi-8]; lpMem
0x18001c3fe  xor     edx, edx; dwFlags
0x18001c400  mov     dword ptr [rsi-8], 6572464Ch
0x18001c407  call    cs:__imp_HeapFree
0x18001c40e  nop     dword ptr [rax+rax+00h]
0x18001c413  lea     rsi, [rdi+104h]
0x18001c41a  cmp     dword ptr [rsi], 4
0x18001c41d  jnb     loc_18001C64D
0x18001c423  xor     eax, eax
0x18001c425  jmp     short loc_18001C49A
0x18001c427  lea     r13, [rcx+108h]
0x18001c42e  mov     ecx, [r13+0]
0x18001c432  add     ecx, r14d
0x18001c435  cmp     ecx, r14d
0x18001c438  jb      short loc_18001C495
0x18001c43a  mov     rax, [rsi+10h]
0x18001c43e  lea     r15, [rdi+0E8h]
0x18001c445  mov     rcx, [rdx+8]
0x18001c449  add     rdx, 8
0x18001c44d  mov     [rax], rcx
0x18001c450  mov     [rcx+8], rax
0x18001c454  mov     rax, [r15+8]
0x18001c458  mov     [rdx], r15
0x18001c45b  mov     [rsi+10h], rax
0x18001c45f  mov     [rax], rdx
0x18001c462  mov     [r15+8], rdx
0x18001c466  add     [r13+0], r14d
0x18001c46a  cmp     cs:g_fTracingOn, 0
0x18001c471  jnz     loc_18001CC05
0x18001c477  mov     edx, [r13+0]; unsigned int
0x18001c47b  lea     rsi, [rdi+104h]
0x18001c482  mov     eax, [rsi]
0x18001c484  mov     [rsp+98h+arg_8], rsi
0x18001c48c  lea     r9d, [rdx+rax]
0x18001c490  cmp     r9d, eax
0x18001c493  jnb     short loc_18001C4EA
0x18001c495  mov     eax, 52h ; 'R'
0x18001c49a  mov     r13, [rsp+98h+var_30]
0x18001c49f  mov     r12, [rsp+98h+var_28]
0x18001c4a4  mov     rbp, [rsp+98h+var_20]
0x18001c4a9  mov     rbx, [rsp+98h+arg_10]
0x18001c4b1  mov     r15, [rsp+98h+var_38]
0x18001c4b6  add     rsp, 80h
0x18001c4bd  pop     r14
0x18001c4bf  pop     rdi
0x18001c4c0  pop     rsi
0x18001c4c1  retn
0x18001c4c3  add     rax, r14
0x18001c4c6  add     rdx, r14
0x18001c4c9  nop     dword ptr [rax+00000000h]
0x18001c4d0  movzx   ecx, byte ptr [rdx-1]
0x18001c4d4  lea     rdx, [rdx-1]
0x18001c4d8  mov     [rax-1], cl
0x18001c4db  lea     rax, [rax-1]
0x18001c4df  add     r8d, 0FFFFFFFFh
0x18001c4e3  jnz     short loc_18001C4D0
0x18001c4e5  jmp     loc_18001C37F
0x18001c4ea  lea     r12, [rdi+10Ch]
0x18001c4f1  mov     r8d, [r12]
0x18001c4f5  cmp     r8d, r9d
0x18001c4f8  ja      loc_18001CC38
0x18001c4fe  mov     rcx, rdi; this
0x18001c501  call    ?CheckInboundSpace@CryptStream@@AEAAEK@Z; CryptStream::CheckInboundSpace(ulong)
0x18001c506  test    al, al
0x18001c508  jz      loc_18001C7FE
0x18001c50e  mov     r9, [r15]
0x18001c511  cmp     r9, r15
0x18001c514  jz      loc_18001C67D
0x18001c51a  mov     eax, [rsi]
0x18001c51c  mov     r8d, [r9+10h]
0x18001c520  lea     ecx, [r8+rax]
0x18001c524  cmp     [rdi+100h], ecx
0x18001c52a  jb      loc_18001C495
0x18001c530  cmp     ecx, eax
0x18001c532  jb      loc_18001C495
0x18001c538  mov     r10, [rsp+98h+arg_0]
0x18001c540  lea     rdi, [r9-8]
0x18001c544  mov     ecx, eax
0x18001c546  lea     rdx, [rdi+24h]
0x18001c54a  add     rcx, [r10+0F8h]
0x18001c551  cmp     rcx, rdx
0x18001c554  ja      loc_18001C608
0x18001c55a  jnz     loc_18001C9A9
0x18001c560  mov     eax, [rdi+18h]
0x18001c563  add     [rsi], eax
0x18001c565  mov     eax, [rdi+18h]
0x18001c568  sub     [r13+0], eax
0x18001c56c  mov     rax, [r9+8]
0x18001c570  mov     rcx, [r9]
0x18001c573  mov     [rax], rcx
0x18001c576  mov     [rcx+8], rax
0x18001c57a  xor     eax, eax
0x18001c57c  xchg    rax, [rdi]
0x18001c57f  test    rax, rax
0x18001c582  jnz     loc_18001C63A
0x18001c588  mov     eax, [rdi-8]
0x18001c58b  cmp     eax, 6461424Ch
0x18001c590  jz      short loc_18001C5FB
0x18001c592  cmp     eax, 6572464Ch
0x18001c597  jz      loc_18001CC75
0x18001c59d  cmp     cs:g_fTracingOn, 0
0x18001c5a4  jnz     loc_18001CCB5
0x18001c5aa  mov     r9d, [rdi-8]
0x18001c5ae  cmp     r9d, 6365524Ch
0x18001c5b5  jnz     loc_18001C923
0x18001c5bb  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001c5c1  mov     r8d, [rdi-4]
0x18001c5c5  sub     eax, r8d
0x18001c5c8  cmp     cs:g_fTracingOn, 0
0x18001c5cf  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001c5d5  jnz     loc_18001CCF5
0x18001c5db  mov     rcx, cs:LdapHeap; hHeap
0x18001c5e2  lea     r8, [rdi-8]; lpMem
0x18001c5e6  xor     edx, edx; dwFlags
0x18001c5e8  mov     dword ptr [rdi-8], 6572464Ch
0x18001c5ef  call    cs:__imp_HeapFree
0x18001c5f6  nop     dword ptr [rax+rax+00h]
0x18001c5fb  mov     rdi, [rsp+98h+arg_0]
0x18001c603  jmp     loc_18001C50E
0x18001c608  add     rcx, r8
0x18001c60b  add     rdx, r8
0x18001c60e  test    r8d, r8d
0x18001c611  jz      loc_18001C560
0x18001c617  nop     word ptr [rax+rax+00000000h]
0x18001c620  movzx   eax, byte ptr [rdx-1]
0x18001c624  lea     rdx, [rdx-1]
0x18001c628  mov     [rcx-1], al
0x18001c62b  lea     rcx, [rcx-1]
0x18001c62f  add     r8d, 0FFFFFFFFh
0x18001c633  jnz     short loc_18001C620
0x18001c635  jmp     loc_18001C560
0x18001c63a  mov     rax, [r9+8]
0x18001c63e  mov     rcx, [r9]
0x18001c641  mov     [rax], rcx
0x18001c644  mov     [rcx+8], rax
0x18001c648  jmp     loc_18001C588
0x18001c64d  mov     rcx, [rbp+0]
0x18001c651  mov     ecx, [rcx]; netlong
0x18001c653  call    cs:__imp_ntohl
0x18001c65a  nop     dword ptr [rax+rax+00h]
0x18001c65f  add     eax, 4
0x18001c662  cmp     eax, 4
0x18001c665  jb      loc_18001C8F7
0x18001c66b  mov     [rdi+10Ch], eax
0x18001c671  mov     byte ptr [rdi+110h], 1
0x18001c678  jmp     loc_18001C477
0x18001c67d  mov     r8d, [r13+0]
0x18001c681  test    r8d, r8d
0x18001c684  jnz     loc_18001CD34
0x18001c68a  mov     eax, [rsi]
0x18001c68c  lea     r15, [rdi+12Ch]
0x18001c693  cmp     eax, [r15]
0x18001c696  ja      loc_18001CD71
0x18001c69c  lea     r14, [rdi+128h]
0x18001c6a3  inc     dword ptr [r14]
0x18001c6a6  cmp     byte ptr [rdi+110h], 0
0x18001c6ad  jz      loc_18001C423
0x18001c6b3  mov     eax, [rsi]
0x18001c6b5  test    eax, eax
0x18001c6b7  jz      loc_18001C423
0x18001c6bd  mov     r8d, [r12]
0x18001c6c1  cmp     r8d, eax
0x18001c6c4  ja      loc_18001C423
0x18001c6ca  cmp     cs:g_fTracingOn, 0
0x18001c6d1  jnz     loc_18001CD79
0x18001c6d7  lea     rbp, [rdi+0F8h]
0x18001c6de  mov     rcx, [rbp+0]
0x18001c6e2  lea     rax, [rcx+4]
0x18001c6e6  mov     [rsp+98h+var_50], rax
0x18001c6eb  mov     ecx, [rcx]; netlong
0x18001c6ed  call    cs:__imp_ntohl
0x18001c6f4  nop     dword ptr [rax+rax+00h]
0x18001c6f9  mov     rcx, [rdi+10h]
0x18001c6fd  lea     rdx, [rsp+98h+var_68]
0x18001c702  mov     [rsp+98h+var_58], eax
0x18001c706  add     rcx, 0D8h
0x18001c70d  lea     rax, [rsp+98h+var_58]
0x18001c712  mov     [rsp+98h+var_54], 0Ah
0x18001c71a  mov     [rsp+98h+var_60], rax
0x18001c71f  xor     r9d, r9d
0x18001c722  mov     rax, [rdi+18h]
0x18001c726  xor     r8d, r8d
0x18001c729  mov     [rsp+98h+Src], 0
0x18001c732  mov     dword ptr [rsp+98h+Size], 0
0x18001c73a  mov     dword ptr [rsp+98h+Size+4], 1
0x18001c742  mov     [rsp+98h+var_64], 2
0x18001c74a  mov     [rsp+98h+var_68], 0
0x18001c752  mov     rax, [rax+0D0h]
0x18001c759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c75e  mov     ebx, eax
0x18001c760  test    eax, eax
0x18001c762  jnz     loc_18001CDFD
0x18001c768  mov     edi, dword ptr [rsp+98h+Size]
0x18001c76c  lea     ecx, [rdi+28h]
0x18001c76f  cmp     ecx, 28h ; '('
0x18001c772  jnb     short loc_18001C7AA
0x18001c774  mov     ebx, 52h ; 'R'
0x18001c779  mov     rdi, [rsp+98h+arg_0]
0x18001c781  cmp     dword ptr [r14], 0C8h
0x18001c788  mov     dword ptr [r12], 0
0x18001c790  mov     byte ptr [rdi+110h], 0
0x18001c797  mov     dword ptr [rsi], 0
0x18001c79d  ja      loc_18001CE3E
0x18001c7a3  mov     eax, ebx
0x18001c7a5  jmp     loc_18001C49A
0x18001c7aa  mov     rsi, [rsp+98h+Src]
0x18001c7af  mov     edx, 6365524Ch
0x18001c7b4  call    ldapMalloc
0x18001c7b9  mov     rbx, rax
0x18001c7bc  test    rax, rax
0x18001c7bf  jnz     short loc_18001C830
0x18001c7c1  mov     rsi, [rsp+98h+arg_8]
0x18001c7c9  mov     ebx, 5Ah ; 'Z'
0x18001c7ce  jmp     short loc_18001C779
0x18001c7d0  mov     rax, [rsi+10h]
0x18001c7d4  mov     rcx, [rsi+8]
0x18001c7d8  mov     [rax], rcx
0x18001c7db  mov     [rcx+8], rax
0x18001c7df  jmp     loc_18001C3A0
0x18001c7e4  lea     eax, [r8+r14]
0x18001c7e8  cmp     eax, r8d
0x18001c7eb  jnb     loc_18001CA32
0x18001c7f1  cmp     cs:g_fTracingOn, 0
0x18001c7f8  jnz     loc_18001CB00
0x18001c7fe  mov     eax, 5Ah ; 'Z'
0x18001c803  jmp     loc_18001C49A
0x18001c808  mov     rcx, [rdx+8]
0x18001c80c  mov     rax, [rdx+10h]
0x18001c810  mov     dl, 1
0x18001c812  mov     [rax], rcx
0x18001c815  mov     [rcx+8], rax
0x18001c819  mov     rcx, rsi
0x18001c81c  call    LdapFreeReceiveStructure
0x18001c821  xor     eax, eax
  ... truncated ...
```
