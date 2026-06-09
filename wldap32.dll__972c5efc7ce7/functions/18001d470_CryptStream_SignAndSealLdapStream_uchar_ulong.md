# CryptStream::SignAndSealLdapStream(uchar *,ulong)

- ea: `0x18001d470`
- end: `0x18001da36`
- name: `?SignAndSealLdapStream@CryptStream@@AEAAKPEAEK@Z`
- size: `1478`
- prototype: `unsigned int(CryptStream *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001ef6c`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000b440`
- `0x18001d470`
- `0x18001da40`
- `0x18001ef10`
- `0x180032bd8`
- `0x180034510`
- `0x18004c76c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d531`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001d531`
- `WS2_32!__imp_htonl` at `0x18001d6bd`
- `WS2_32!__imp_htonl` at `0x18001d6bd`

## string_xrefs

- `0x18001d9e2`: `EncryptMessage failed with 0x%x, security context is 0x%x\n`

## pseudocode

```c
__int64 __fastcall CryptStream::SignAndSealLdapStream(CryptStream *this, unsigned __int8 *a2, unsigned int a3)
{
  int v4; // ecx
  unsigned int v5; // esi
  unsigned int v7; // eax
  unsigned int v8; // edx
  unsigned int v9; // r8d
  unsigned int v11; // edx
  unsigned int v12; // edi
  unsigned int v13; // r15d
  LPVOID v14; // rax
  __int64 v15; // r14
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // edi
  bool v21; // r15
  unsigned int v22; // eax
  unsigned int v23; // r13d
  __int64 v24; // rax
  __int64 v25; // r10
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // eax
  int v29; // r11d
  unsigned int v30; // r10d
  u_long v31; // r9d
  int v32; // eax
  unsigned int v33; // ecx
  unsigned int v34; // edi
  unsigned int v35; // eax
  u_long v36; // [rsp+30h] [rbp-39h]
  int v37; // [rsp+34h] [rbp-35h]
  int v38; // [rsp+38h] [rbp-31h]
  __int128 v39; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v40[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v41; // [rsp+58h] [rbp-11h]
  unsigned int v42; // [rsp+60h] [rbp-9h]
  int v43; // [rsp+64h] [rbp-5h]
  __int64 v44; // [rsp+68h] [rbp-1h]
  int v45; // [rsp+70h] [rbp+7h]
  int v46; // [rsp+74h] [rbp+Bh]
  unsigned __int64 v47; // [rsp+78h] [rbp+Fh]

  v4 = g_fTracingOn;
  v5 = a3;
  v39 = 0;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
  {
    LDAPClientPrint(32, "Signing/Sealing %d bytes of cleartext.\n", a3);
    v4 = g_fTracingOn;
  }
  v7 = *((_DWORD *)this + 47);
  if ( v7 == -1 )
    v7 = v5;
  v8 = v7 + 4;
  if ( v7 >= 0xFFFFFFFC
    || (v9 = v8 + *((_DWORD *)this + 32), v9 < v8)
    || (v11 = v9 + *((_DWORD *)this + 33), v11 < v9)
    || (v12 = v11 + *((_DWORD *)this + 34), v12 < v11) )
  {
    if ( v4 && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientTraceEvent(0x10000000, (__int64)"Integer overflow while calculating size of encrypted packet\n");
    return 82;
  }
  else
  {
    v13 = v12 + 8;
    if ( v12 + 8 < v12 )
    {
      v15 = 0;
      v13 = -1;
    }
    else
    {
      v14 = HeapAlloc(LdapHeap, 8u, v13);
      v4 = g_fTracingOn;
      v15 = (__int64)v14;
    }
    if ( v4 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
    {
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", v13, v15, 1667593036);
      v4 = g_fTracingOn;
    }
    v16 = LdapAllocatedHeap;
    if ( v15 )
    {
      *(_DWORD *)v15 = 1667593036;
      *(_DWORD *)(v15 + 4) = v12;
      v15 += 8;
      v16 += v12;
      LdapAllocatedHeap = v16;
    }
    if ( v4 && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n", v12, v15, 1667593036, v16);
    if ( v15 )
    {
      v17 = *((_QWORD *)this + 2);
      v18 = v15 + 4;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      v38 = 0;
      if ( *(_BYTE *)(v17 + 194) )
        v21 = *(_BYTE *)(v17 + 195) == 0;
      while ( 1 )
      {
        if ( !v5 )
        {
LABEL_30:
          ldapFree(v15, 1667593036);
          return v20;
        }
        v22 = *((_DWORD *)this + 47);
        v23 = v5;
        if ( v22 != -1 && v5 > v22 )
          v23 = *((_DWORD *)this + 47);
        v24 = *((unsigned int *)this + 34);
        v41 = v18;
        v43 = 1;
        v44 = v24 + v18;
        v40[0] = v24;
        v40[1] = 2;
        v42 = v23;
        memcpy_0((void *)(v24 + v18), &a2[v19], v23);
        v25 = *((_QWORD *)this + 3);
        v26 = v23 + (unsigned __int64)*((unsigned int *)this + 34);
        v46 = 9;
        v27 = *((_QWORD *)this + 2);
        v47 = v15 + 4 + v26;
        v45 = *((_DWORD *)this + 32) + *((_DWORD *)this + 33);
        *((_QWORD *)&v39 + 1) = v40;
        *(_QWORD *)&v39 = 0x300000000LL;
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, _QWORD))(v25 + 200))(
                v27 + 216,
                v21 ? 0x80000001 : 0,
                &v39,
                0);
        v29 = v28;
        v30 = v40[0];
        v31 = v40[0] + v42 + v45;
        v37 = v28;
        v36 = v31;
        if ( v28 )
        {
          if ( v28 > -2146893052 )
          {
            if ( v28 <= -2146893043 )
            {
              if ( v28 == -2146893043 || v28 == -2146893051 )
              {
                v20 = 86;
                goto LABEL_23;
              }
              if ( v28 != -2146893050 && v28 != -2146893044 )
                goto LABEL_61;
LABEL_55:
              v20 = 49;
              goto LABEL_23;
            }
            if ( v28 == -2146893042 )
              goto LABEL_55;
            if ( v28 == 58 )
            {
              v20 = 81;
              goto LABEL_23;
            }
            if ( v28 != 1460 )
            {
LABEL_61:
              SetConnectionError(*((_QWORD *)this + 2), (unsigned int)v28);
              v30 = v40[0];
              v20 = 82;
              v31 = v36;
              v29 = v37;
              goto LABEL_23;
            }
            v20 = 85;
          }
          else
          {
            if ( v28 != -2146893056 )
              goto LABEL_61;
            v20 = 90;
          }
        }
        else
        {
          v20 = 0;
        }
LABEL_23:
        v32 = g_fTracingOn;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
        {
          LDAPClientPrint(32, "EncryptMessage returned 0x%x\n", v29);
          v30 = v40[0];
          v32 = g_fTracingOn;
          v31 = v36;
          v29 = v37;
        }
        if ( v20 )
        {
          if ( v32 && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
            LDAPClientPrint(
              32,
              "EncryptMessage failed with 0x%x, security context is 0x%x\n",
              v29,
              *((_QWORD *)this + 2) + 216);
          goto LABEL_30;
        }
        v33 = *((_DWORD *)this + 34);
        v34 = v31 + 4;
        if ( v30 < v33 )
        {
          if ( v32 && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
          {
            LDAPClientPrint(32, "Shifting encryptbuffers by %d\n", v30 - v33);
            v30 = v40[0];
          }
          ldap_MoveMemory(v41 + v30, v44, v42 + v45);
        }
        *(_DWORD *)v15 = htonl(v31);
        v35 = LdapSendRaw(*((struct ldap_connection **)this + 2), (char *)v15, v34, 0, 0);
        v20 = v35;
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
          LDAPClientPrint(
            32,
            "Sending %d signed/sealed bytes with retval 0x%x, %d bytes of cleartext to go\n",
            v36 + 4,
            v35,
            v5 - v23);
        if ( v20 )
          goto LABEL_30;
        v18 = v15 + 4;
        v5 -= v23;
        v19 = v23 + v38;
        v38 += v23;
      }
    }
    return 90;
  }
}

```

## disassembly

```asm
0x18001d470  push    rbp
0x18001d472  push    rbx
0x18001d473  push    rsi
0x18001d474  push    r12
0x18001d476  lea     rbp, [rsp-3Fh]
0x18001d47b  sub     rsp, 0A8h
0x18001d482  mov     rax, cs:__security_cookie
0x18001d489  xor     rax, rsp
0x18001d48c  mov     [rbp+57h+var_40], rax
0x18001d490  mov     rbx, rcx
0x18001d493  xorps   xmm0, xmm0
0x18001d496  mov     ecx, cs:g_fTracingOn
0x18001d49c  mov     esi, r8d
0x18001d49f  mov     r12, rdx
0x18001d4a2  movups  [rbp+57h+var_80], xmm0
0x18001d4a6  test    ecx, ecx
0x18001d4a8  jnz     loc_18001D7DC
0x18001d4ae  mov     eax, [rbx+0BCh]
0x18001d4b4  cmp     eax, 0FFFFFFFFh
0x18001d4b7  mov     [rsp+0C0h+arg_18], rdi
0x18001d4bf  cmovz   eax, esi
0x18001d4c2  lea     edx, [rax+4]
0x18001d4c5  cmp     edx, 4
0x18001d4c8  jb      short loc_18001D4D9
0x18001d4ca  mov     r8d, [rbx+80h]
0x18001d4d1  add     r8d, edx
0x18001d4d4  cmp     r8d, edx
0x18001d4d7  jnb     short loc_18001D4EB
0x18001d4d9  test    ecx, ecx
0x18001d4db  jnz     loc_18001DA02
0x18001d4e1  mov     eax, 52h ; 'R'
0x18001d4e6  jmp     loc_18001D743
0x18001d4eb  mov     edx, [rbx+84h]
0x18001d4f1  add     edx, r8d
0x18001d4f4  cmp     edx, r8d
0x18001d4f7  jb      short loc_18001D4D9
0x18001d4f9  mov     edi, [rbx+88h]
0x18001d4ff  add     edi, edx
0x18001d501  cmp     edi, edx
0x18001d503  jb      short loc_18001D4D9
0x18001d505  mov     [rsp+0C0h+var_28], r14
0x18001d50d  mov     [rsp+0C0h+var_30], r15
0x18001d515  lea     r15d, [rdi+8]
0x18001d519  cmp     r15d, edi
0x18001d51c  jb      loc_18001D765
0x18001d522  mov     rcx, cs:LdapHeap; hHeap
0x18001d529  mov     edx, 8; dwFlags
0x18001d52e  mov     r8d, r15d; dwBytes
0x18001d531  call    cs:__imp_HeapAlloc
0x18001d538  nop     dword ptr [rax+rax+00h]
0x18001d53d  mov     ecx, cs:g_fTracingOn
0x18001d543  mov     r14, rax
0x18001d546  test    ecx, ecx
0x18001d548  jnz     loc_18001D798
0x18001d54e  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001d554  test    r14, r14
0x18001d557  jz      short loc_18001D570
0x18001d559  mov     dword ptr [r14], 6365734Ch
0x18001d560  mov     [r14+4], edi
0x18001d564  add     r14, 8
0x18001d568  add     eax, edi
0x18001d56a  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x18001d570  test    ecx, ecx
0x18001d572  jnz     loc_18001D812
0x18001d578  test    r14, r14
0x18001d57b  jz      loc_18001D854
0x18001d581  mov     rax, [rbx+10h]
0x18001d585  lea     rcx, [r14+4]
0x18001d589  xor     edx, edx
0x18001d58b  xor     edi, edi
0x18001d58d  xor     r15b, r15b
0x18001d590  mov     [rbp+57h+var_88], edx
0x18001d593  mov     r8d, 1
0x18001d599  cmp     [rax+0C2h], dl
0x18001d59f  jz      short loc_18001D5AF
0x18001d5a1  cmp     [rax+0C3h], dl
0x18001d5a7  movzx   r15d, r15b
0x18001d5ab  cmovz   r15d, r8d
0x18001d5af  mov     [rsp+0C0h+var_20], r13
0x18001d5b7  test    esi, esi
0x18001d5b9  jz      loc_18001D71C
0x18001d5bf  mov     eax, [rbx+0BCh]
0x18001d5c5  mov     r13d, esi
0x18001d5c8  cmp     eax, 0FFFFFFFFh
0x18001d5cb  jnz     loc_18001D85E
0x18001d5d1  mov     eax, [rbx+88h]
0x18001d5d7  add     rdx, r12; Src
0x18001d5da  mov     [rbp+57h+var_68], rcx
0x18001d5de  add     rcx, rax; void *
0x18001d5e1  mov     [rbp+57h+var_5C], r8d
0x18001d5e5  mov     r8d, r13d; Size
0x18001d5e8  mov     [rbp+57h+var_58], rcx
0x18001d5ec  mov     [rbp+57h+var_70], eax
0x18001d5ef  mov     [rbp+57h+var_6C], 2
0x18001d5f6  mov     [rbp+57h+var_60], r13d
0x18001d5fa  mov     edi, r13d
0x18001d5fd  call    memcpy_0
0x18001d602  mov     eax, [rbx+88h]
0x18001d608  lea     rcx, [r14+4]
0x18001d60c  mov     r10, [rbx+18h]
0x18001d610  lea     r8, [rbp+57h+var_80]
0x18001d614  add     rax, rdi
0x18001d617  mov     [rbp+57h+var_4C], 9
0x18001d61e  add     rax, rcx
0x18001d621  mov     dword ptr [rbp+57h+var_80+4], 3
0x18001d628  mov     rcx, [rbx+10h]
0x18001d62c  mov     [rbp+57h+var_48], rax
0x18001d630  mov     eax, [rbx+84h]
0x18001d636  add     eax, [rbx+80h]
0x18001d63c  mov     [rbp+57h+var_50], eax
0x18001d63f  lea     rax, [rbp+57h+var_70]
0x18001d643  mov     qword ptr [rbp+57h+var_80+8], rax
0x18001d647  movzx   eax, r15b
0x18001d64b  neg     al
0x18001d64d  mov     dword ptr [rbp+57h+var_80], 0
0x18001d654  mov     rax, [r10+0C8h]
0x18001d65b  sbb     edx, edx
0x18001d65d  add     rcx, 0D8h
0x18001d664  and     edx, 80000001h
0x18001d66a  xor     r9d, r9d
0x18001d66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d672  mov     r9d, [rbp+57h+var_50]
0x18001d676  mov     r11d, eax
0x18001d679  add     r9d, [rbp+57h+var_60]
0x18001d67d  mov     r10d, [rbp+57h+var_70]
0x18001d681  add     r9d, r10d
0x18001d684  mov     [rbp+57h+var_8C], eax
0x18001d687  mov     [rbp+57h+var_90], r9d
0x18001d68b  test    eax, eax
0x18001d68d  jnz     loc_18001D869
0x18001d693  xor     edi, edi
0x18001d695  mov     eax, cs:g_fTracingOn
0x18001d69b  test    eax, eax
0x18001d69d  jnz     loc_18001D8FD
0x18001d6a3  test    edi, edi
0x18001d6a5  jnz     short loc_18001D714
0x18001d6a7  mov     ecx, [rbx+88h]
0x18001d6ad  lea     edi, [r9+4]
0x18001d6b1  cmp     r10d, ecx
0x18001d6b4  jb      loc_18001D773
0x18001d6ba  mov     ecx, r9d; hostlong
0x18001d6bd  call    cs:__imp_htonl
0x18001d6c4  nop     dword ptr [rax+rax+00h]
0x18001d6c9  xor     r9d, r9d; char *
0x18001d6cc  mov     [rsp+0C0h+var_A0], 0; unsigned int
0x18001d6d4  mov     [r14], eax
0x18001d6d7  mov     r8d, edi; len
0x18001d6da  mov     rcx, [rbx+10h]; struct ldap_connection *
0x18001d6de  mov     rdx, r14; buf
0x18001d6e1  call    ?LdapSendRaw@@YAKPEAUldap_connection@@PEADK1K@Z; LdapSendRaw(ldap_connection *,char *,ulong,char *,ulong)
0x18001d6e6  cmp     cs:g_fTracingOn, 0
0x18001d6ed  mov     edi, eax
0x18001d6ef  jnz     loc_18001D980
0x18001d6f5  test    edi, edi
0x18001d6f7  jnz     short loc_18001D71C
0x18001d6f9  mov     edx, [rbp+57h+var_88]
0x18001d6fc  lea     rcx, [r14+4]
0x18001d700  sub     esi, r13d
0x18001d703  mov     r8d, 1
0x18001d709  add     edx, r13d
0x18001d70c  mov     [rbp+57h+var_88], edx
0x18001d70f  jmp     loc_18001D5B7
0x18001d714  test    eax, eax
0x18001d716  jnz     loc_18001D9C4
0x18001d71c  mov     edx, 6365734Ch
0x18001d721  mov     rcx, r14
0x18001d724  call    ldapFree
0x18001d729  mov     r13, [rsp+0C0h+var_20]
0x18001d731  mov     eax, edi
0x18001d733  mov     r14, [rsp+0C0h+var_28]
0x18001d73b  mov     r15, [rsp+0C0h+var_30]
0x18001d743  mov     rdi, [rsp+0C0h+arg_18]
0x18001d74b  mov     rcx, [rbp+57h+var_40]
0x18001d74f  xor     rcx, rsp; StackCookie
0x18001d752  call    __security_check_cookie
0x18001d757  add     rsp, 0A8h
0x18001d75e  pop     r12
0x18001d760  pop     rsi
0x18001d761  pop     rbx
0x18001d762  pop     rbp
0x18001d763  retn
0x18001d765  xor     r14d, r14d
0x18001d768  mov     r15d, 0FFFFFFFFh
0x18001d76e  jmp     loc_18001D546
0x18001d773  test    eax, eax
0x18001d775  jnz     loc_18001D942
0x18001d77b  mov     r8d, [rbp+57h+var_50]
0x18001d77f  add     r8d, [rbp+57h+var_60]
0x18001d783  mov     rdx, [rbp+57h+var_58]
0x18001d787  mov     ecx, r10d
0x18001d78a  add     rcx, [rbp+57h+var_68]
0x18001d78e  call    ldap_MoveMemory
0x18001d793  jmp     loc_18001D6BA
0x18001d798  cmp     cs:g_fProviderEnabled, 0
0x18001d79f  jz      loc_18001D54E
0x18001d7a5  test    byte ptr cs:g_ulTraceFlags, 8
0x18001d7ac  jz      loc_18001D54E
0x18001d7b2  mov     r9, r14
0x18001d7b5  mov     [rsp+0C0h+var_A0], 6365734Ch
0x18001d7bd  mov     r8d, r15d
0x18001d7c0  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18001d7c7  mov     ecx, 8
0x18001d7cc  call    LDAPClientPrint
0x18001d7d1  mov     ecx, cs:g_fTracingOn
0x18001d7d7  jmp     loc_18001D54E
0x18001d7dc  cmp     cs:g_fProviderEnabled, 0
0x18001d7e3  jz      loc_18001D4AE
0x18001d7e9  test    byte ptr cs:g_ulTraceFlags, 20h
0x18001d7f0  jz      loc_18001D4AE
0x18001d7f6  lea     rdx, aSigningSealing; "Signing/Sealing %d bytes of cleartext."...
0x18001d7fd  mov     ecx, 20h ; ' '
0x18001d802  call    LDAPClientPrint
0x18001d807  mov     ecx, cs:g_fTracingOn
0x18001d80d  jmp     loc_18001D4AE
0x18001d812  cmp     cs:g_fProviderEnabled, 0
0x18001d819  jz      loc_18001D578
0x18001d81f  test    byte ptr cs:g_ulTraceFlags, 8
0x18001d826  jz      loc_18001D578
0x18001d82c  mov     [rsp+0C0h+var_98], eax
0x18001d830  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x18001d837  mov     r9, r14
0x18001d83a  mov     [rsp+0C0h+var_A0], 6365734Ch
0x18001d842  mov     r8d, edi
0x18001d845  mov     ecx, 8
0x18001d84a  call    LDAPClientPrint
0x18001d84f  jmp     loc_18001D578
0x18001d854  mov     eax, 5Ah ; 'Z'
0x18001d859  jmp     loc_18001D733
0x18001d85e  cmp     esi, eax
0x18001d860  cmova   r13d, eax
0x18001d864  jmp     loc_18001D5D1
0x18001d869  cmp     eax, 80090304h
0x18001d86e  jg      short loc_18001D883
0x18001d870  jz      short loc_18001D8D2
0x18001d872  cmp     eax, 80090300h
0x18001d877  jnz     short loc_18001D8D2
0x18001d879  mov     edi, 5Ah ; 'Z'
0x18001d87e  jmp     loc_18001D695
0x18001d883  cmp     eax, 8009030Dh
0x18001d888  jg      short loc_18001D8B5
0x18001d88a  jz      short loc_18001D8AB
0x18001d88c  cmp     eax, 80090305h
0x18001d891  jz      short loc_18001D8AB
0x18001d893  cmp     eax, 80090306h
0x18001d898  jz      short loc_18001D8A1
0x18001d89a  cmp     eax, 8009030Ch
0x18001d89f  jnz     short loc_18001D8D2
0x18001d8a1  mov     edi, 31h ; '1'
0x18001d8a6  jmp     loc_18001D695
0x18001d8ab  mov     edi, 56h ; 'V'
0x18001d8b0  jmp     loc_18001D695
0x18001d8b5  cmp     eax, 8009030Eh
0x18001d8ba  jz      short loc_18001D8A1
0x18001d8bc  cmp     eax, 3Ah ; ':'
0x18001d8bf  jz      short loc_18001D8F3
0x18001d8c1  cmp     eax, 5B4h
0x18001d8c6  jnz     short loc_18001D8D2
0x18001d8c8  mov     edi, 55h ; 'U'
0x18001d8cd  jmp     loc_18001D695
0x18001d8d2  mov     rcx, [rbx+10h]
0x18001d8d6  mov     edx, eax
0x18001d8d8  call    SetConnectionError
0x18001d8dd  mov     r10d, [rbp+57h+var_70]
0x18001d8e1  mov     edi, 52h ; 'R'
0x18001d8e6  mov     r9d, [rbp+57h+var_90]
0x18001d8ea  mov     r11d, [rbp+57h+var_8C]
0x18001d8ee  jmp     loc_18001D695
0x18001d8f3  mov     edi, 51h ; 'Q'
0x18001d8f8  jmp     loc_18001D695
0x18001d8fd  cmp     cs:g_fProviderEnabled, 0
0x18001d904  jz      loc_18001D6A3
0x18001d90a  test    byte ptr cs:g_ulTraceFlags, 20h
0x18001d911  jz      loc_18001D6A3
0x18001d917  mov     r8d, r11d
0x18001d91a  lea     rdx, aEncryptmessage_0; "EncryptMessage returned 0x%x\n"
0x18001d921  mov     ecx, 20h ; ' '
0x18001d926  call    LDAPClientPrint
0x18001d92b  mov     r10d, [rbp+57h+var_70]
0x18001d92f  mov     eax, cs:g_fTracingOn
0x18001d935  mov     r9d, [rbp+57h+var_90]
0x18001d939  mov     r11d, [rbp+57h+var_8C]
0x18001d93d  jmp     loc_18001D6A3
0x18001d942  cmp     cs:g_fProviderEnabled, 0
0x18001d949  jz      loc_18001D77B
0x18001d94f  test    byte ptr cs:g_ulTraceFlags, 20h
0x18001d956  jz      loc_18001D77B
0x18001d95c  sub     r10d, ecx
0x18001d95f  lea     rdx, aShiftingEncryp; "Shifting encryptbuffers by %d\n"
0x18001d966  mov     r8d, r10d
0x18001d969  mov     ecx, 20h ; ' '
0x18001d96e  call    LDAPClientPrint
0x18001d973  mov     r10d, [rbp+57h+var_70]
0x18001d977  mov     r9d, [rbp+57h+var_90]
0x18001d97b  jmp     loc_18001D77B
0x18001d980  cmp     cs:g_fProviderEnabled, 0
0x18001d987  jz      loc_18001D6F5
0x18001d98d  test    byte ptr cs:g_ulTraceFlags, 20h
0x18001d994  jz      loc_18001D6F5
0x18001d99a  mov     r8d, [rbp+57h+var_90]
0x18001d99e  lea     rdx, aSendingDSigned; "Sending %d signed/sealed bytes with ret"...
  ... truncated ...
```
