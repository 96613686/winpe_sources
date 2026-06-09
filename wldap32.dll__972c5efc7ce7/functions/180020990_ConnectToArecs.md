# ConnectToArecs

- ea: `0x180020990`
- end: `0x18002144e`
- name: `ConnectToArecs`
- size: `2750`
- prototype: `__int64 __usercall@<rax>(struct ldap_connection *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002376c`

## callees

- `0x1800037a8`
- `0x18000b440`
- `0x18001ce90`
- `0x18001f13c`
- `0x180020228`
- `0x180020990`
- `0x180021454`
- `0x180022e80`
- `0x180034510`
- `0x180034e6c`
- `0x180042484`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020b81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020c77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020ce2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020b81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020c77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020ce2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020c54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020c54`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020ec0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020ec0`
- `WS2_32!__imp_htons` at `0x180020da6`
- `WS2_32!__imp_htons` at `0x180020da6`

## string_xrefs

- `0x1800212fa`: `Freeing memory at 0x%x which is already freed\n`
- `0x1800213b9`: `Freeing memory at 0x%x which is already freed\n`

## pseudocode

```c
__int64 __fastcall ConnectToArecs(struct ldap_connection *a1, const WCHAR **a2, char a3, unsigned __int16 a4, int *a5)
{
  __int64 v8; // rsi
  __int64 i; // r15
  bool v10; // zf
  int v11; // eax
  unsigned int SocketAddressesByNameW; // ebp
  __int64 v13; // rbx
  __int64 **v14; // rax
  __int64 **v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // r15
  __int64 *v18; // rdi
  int v20; // eax
  int v21; // r9d
  int v22; // r8d
  int v23; // eax
  HANDLE v24; // rcx
  _DWORD *v25; // rax
  _DWORD *v26; // rbx
  __int64 **v27; // rdi
  int v28; // eax
  int v29; // r9d
  int v30; // r8d
  int v31; // eax
  HANDLE v32; // rcx
  _DWORD *v33; // rax
  _DWORD *v34; // rbx
  _DWORD *v35; // rax
  _DWORD *v36; // rbx
  __int64 v37; // rcx
  _WORD *v38; // rbx
  int v39; // r8d
  WCHAR *v40; // rcx
  __int64 v41; // rax
  const WCHAR *v42; // rcx
  __int64 v43; // rax
  const wchar_t *v44; // r8
  const WCHAR *v45; // r8
  __int64 *v46; // r15
  _DWORD *v47; // r12
  __int64 v48; // rax
  __int64 v49; // rdx
  _QWORD **v50; // r9
  _QWORD *v51; // rax
  int v53; // [rsp+38h] [rbp-370h] BYREF
  int v54; // [rsp+3Ch] [rbp-36Ch]
  _QWORD v55[100]; // [rsp+40h] [rbp-368h] BYREF

  memset_0(v55, 0, sizeof(v55));
  v8 = 0;
  for ( i = *(_QWORD *)a2[3]; ; i = *(_QWORD *)&a2[3][4 * (unsigned int)v8] )
  {
    if ( !i || (unsigned int)v8 >= 0x63 )
    {
      v10 = *((_WORD *)a1 + 253) == 0;
      v55[v8] = 0;
      if ( v10 )
        *((_WORD *)a1 + 253) = 389;
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        LDAPClientPrint(0x2000000, "gethostbyname collected %d records for '%S'\n", v8, *a2);
      if ( a5 )
      {
        if ( a3 )
          v53 = 1;
        else
          v53 = *a5;
        v54 = a5[1];
      }
      else
      {
        v54 = 0;
        v11 = 45;
        if ( a3 )
          v11 = 1;
        v53 = v11;
      }
      SocketAddressesByNameW = LdapParallelConnect(a1, (__int64)&v53);
      if ( SocketAddressesByNameW )
        goto LABEL_11;
      v40 = (WCHAR *)a2[1];
      if ( !v40 )
        v40 = (WCHAR *)*a2;
      v41 = ldap_dup_stringW(v40);
      *((_QWORD *)a1 + 52) = v41;
      if ( (a2[1] || *a2) && !v41 )
        goto LABEL_32;
      ldapFree(*((_QWORD *)a1 + 124), 1953712204);
      *((_QWORD *)a1 + 124) = 0;
      v42 = a2[1];
      if ( !v42 )
        v42 = *a2;
      SocketAddressesByNameW = FromUnicodeWithAlloc(v42);
      if ( SocketAddressesByNameW )
        goto LABEL_11;
      v43 = ldap_dup_stringW(*((void **)a1 + 52));
      v44 = (const wchar_t *)*((_QWORD *)a1 + 52);
      *((_QWORD *)a1 + 54) = v43;
      if ( v44 )
      {
        if ( !v43 )
          goto LABEL_32;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000000) != 0 )
        LDAPClientPrint(0x2000000, "Successfully connected to host '%S'\n", v44);
      v45 = (const WCHAR *)*((_QWORD *)a1 + 48);
      v46 = (__int64 *)((char *)a1 + 376);
      v47 = (_DWORD *)((char *)a1 + 372);
      if ( v45 && CompareStringW(0x400u, 1u, v45, -1, L"localhost", -1) == 2 )
      {
        SocketAddressesByNameW = GetSocketAddressesByNameW(
                                   *((PCWSTR *)a1 + 54),
                                   a4,
                                   (unsigned int *)a1 + 93,
                                   (struct _SOCKET_ADDRESS ***)a1 + 47);
        goto LABEL_11;
      }
      FreeSocketAddressArr((unsigned int *)a1 + 93, (struct _SOCKET_ADDRESS ***)a1 + 47);
      v48 = ldapMalloc((unsigned int)(8 * v8), 1919177548);
      *v46 = v48;
      if ( !v48 )
      {
LABEL_32:
        SocketAddressesByNameW = 90;
        goto LABEL_11;
      }
      v49 = 0;
      if ( !(_DWORD)v8 )
        goto LABEL_11;
      do
      {
        v50 = (_QWORD **)&v55[v49];
        *(_QWORD *)(*v46 + 8LL * (unsigned int)*v47) = 0;
        v51 = *v50;
        if ( *v50 && *v51 )
        {
          *(_QWORD *)(*v46 + 8LL * (unsigned int)*v47) = *v51;
          **v50 = 0;
          ++*v47;
        }
        v49 = (unsigned int)(v49 + 1);
      }
      while ( (unsigned int)v49 < (unsigned int)v8 );
      v13 = 0;
      while ( 1 )
      {
LABEL_12:
        v14 = (__int64 **)v55[v13];
        v15 = (__int64 **)&v55[v13];
        if ( !v14 )
          goto LABEL_18;
        if ( *v14 )
        {
          v16 = **v14;
          if ( v16 )
            ldapFree(v16, 1919177548);
          v17 = **v15;
          if ( v17 )
          {
            v28 = *(_DWORD *)(v17 - 8);
            if ( v28 != 1684095564 )
              break;
          }
        }
LABEL_17:
        v18 = *v15;
        if ( v18 )
        {
          v20 = *((_DWORD *)v18 - 2);
          if ( v20 != 1684095564 )
          {
            if ( v20 != 1701987916 )
              goto LABEL_22;
            if ( g_fTracingOn )
            {
              if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", (_DWORD)v18);
LABEL_22:
              if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                LDAPClientPrint(
                  8,
                  "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
                  *((_DWORD *)v18 - 1),
                  (_DWORD)v18 - 8,
                  1919177548);
            }
            v21 = *((_DWORD *)v18 - 2);
            if ( v21 != 1919177548 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
              LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1919177548, v21);
            v22 = *((_DWORD *)v18 - 1);
            v23 = LdapAllocatedHeap - v22;
            LdapAllocatedHeap -= v22;
            if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
              LDAPClientPrint(
                8,
                "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                v22,
                (_DWORD)v18,
                1919177548,
                v23);
            v24 = LdapHeap;
            *((_DWORD *)v18 - 2) = 1701987916;
            HeapFree(v24, 0, v18 - 1);
          }
        }
LABEL_18:
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= (unsigned int)v8 )
          return SocketAddressesByNameW;
      }
      if ( v28 == 1701987916 )
      {
        if ( !g_fTracingOn )
        {
LABEL_36:
          v29 = *(_DWORD *)(v17 - 8);
          if ( v29 != 1919177548 && g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(8, "Expected tag 0x%x but found tag 0x%x\n", 1919177548, v29);
          v30 = *(_DWORD *)(v17 - 4);
          v31 = LdapAllocatedHeap - v30;
          LdapAllocatedHeap -= v30;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(
              8,
              "ldapFree   0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
              v30,
              v17,
              1919177548,
              v31);
          v32 = LdapHeap;
          *(_DWORD *)(v17 - 8) = 1701987916;
          HeapFree(v32, 0, (LPVOID)(v17 - 8));
          goto LABEL_17;
        }
        if ( g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(8, "Freeing memory at 0x%x which is already freed\n", **v15);
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapfree freed       0x%x bytes at address 0x%x of tag 0x%x.\n",
          *(_DWORD *)(v17 - 4),
          v17 - 8,
          1919177548);
      goto LABEL_36;
    }
    v25 = HeapAlloc(LdapHeap, 8u, 0x18u);
    v26 = v25;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 24, (_DWORD)v25, 1919177548);
    if ( v26 )
    {
      *v26 = 1919177548;
      v26[1] = 16;
      v26 += 2;
      LdapAllocatedHeap += 16;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        16,
        (_DWORD)v26,
        1919177548,
        LdapAllocatedHeap);
    v55[v8] = v26;
    v27 = (__int64 **)&v55[v8];
    if ( !v26 )
      goto LABEL_32;
    v33 = HeapAlloc(LdapHeap, 8u, 0x18u);
    v34 = v33;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 24, (_DWORD)v33, 1919177548);
    if ( v34 )
    {
      *v34 = 1919177548;
      v34[1] = 16;
      v34 += 2;
      LdapAllocatedHeap += 16;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        16,
        (_DWORD)v34,
        1919177548,
        LdapAllocatedHeap);
    **v27 = (__int64)v34;
    if ( !**v27 )
      goto LABEL_32;
    v35 = HeapAlloc(LdapHeap, 8u, 0x88u);
    v36 = v35;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(8, "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n", 136, (_DWORD)v35, 1919177548);
    if ( v36 )
    {
      *v36 = 1919177548;
      v36[1] = 128;
      v36 += 2;
      LdapAllocatedHeap += 128;
    }
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
      LDAPClientPrint(
        8,
        "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
        128,
        (_DWORD)v36,
        1919177548,
        LdapAllocatedHeap);
    *(_QWORD *)**v27 = v36;
    v37 = **v27;
    v38 = *(_WORD **)v37;
    if ( !*(_QWORD *)v37 )
      goto LABEL_104;
    *(_DWORD *)(v37 + 8) = 128;
    v39 = *(__int16 *)(i + 2);
    if ( v39 > *(_DWORD *)(**v27 + 8) )
      break;
    if ( *(_WORD *)i == 2 )
    {
      memcpy_0(v38 + 2, *(const void **)(i + 8), *(__int16 *)(i + 2));
      *(_DWORD *)(**v27 + 8) = 16;
    }
    else if ( *(_WORD *)i == 23 )
    {
      memcpy_0(v38 + 4, *(const void **)(i + 8), *(__int16 *)(i + 2));
      *(_DWORD *)(**v27 + 8) = 28;
    }
    *v38 = *(_WORD *)i;
    v38[1] = htons(a4);
    v8 = (unsigned int)(v8 + 1);
    (*v27)[1] = 0;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
    LDAPClientPrint(0x10000000, "Length is too big (%d)\n", v39);
LABEL_104:
  SocketAddressesByNameW = 82;
LABEL_11:
  v13 = 0;
  if ( (_DWORD)v8 )
    goto LABEL_12;
  return SocketAddressesByNameW;
}

```

## disassembly

```asm
0x180020990  push    rbp
0x180020992  push    rsi
0x180020993  push    r12
0x180020995  push    r13
0x180020997  push    r14
0x180020999  push    r15
0x18002099b  sub     rsp, 378h
0x1800209a2  mov     rax, cs:__security_cookie
0x1800209a9  xor     rax, rsp
0x1800209ac  mov     [rsp+3A8h+var_48], rax
0x1800209b4  mov     rbp, [rsp+3A8h+arg_20]
0x1800209bc  movzx   r12d, r8b
0x1800209c0  mov     r13, rdx
0x1800209c3  mov     [rsp+3A8h+var_378], r9w
0x1800209c9  mov     r14, rcx
0x1800209cc  xor     edx, edx; Val
0x1800209ce  mov     r8d, 320h; Size
0x1800209d4  lea     rcx, [rsp+3A8h+var_368]; void *
0x1800209d9  call    memset_0
0x1800209de  mov     rax, [r13+18h]
0x1800209e2  xor     esi, esi
0x1800209e4  mov     [rsp+3A8h+arg_10], rbx
0x1800209ec  mov     [rsp+3A8h+var_38], rdi
0x1800209f4  mov     r15, [rax]
0x1800209f7  test    r15, r15
0x1800209fa  jnz     loc_180020B66
0x180020a00  cmp     word ptr [r14+1FAh], 0
0x180020a09  mov     [rsp+rsi*8+3A8h+var_368], 0
0x180020a12  jz      loc_1800211CD
0x180020a18  cmp     cs:g_fTracingOn, 0
0x180020a1f  jnz     loc_1800211DC
0x180020a25  mov     ebx, 1
0x180020a2a  test    rbp, rbp
0x180020a2d  jnz     loc_180021217
0x180020a33  test    r12b, r12b
0x180020a36  mov     dword ptr [rsp+3A8h+var_370+4], ebp
0x180020a3a  mov     eax, 2Dh ; '-'
0x180020a3f  cmovnz  eax, ebx
0x180020a42  mov     dword ptr [rsp+3A8h+var_370], eax
0x180020a46  movzx   r8d, [rsp+3A8h+var_378]
0x180020a4c  lea     rax, [rsp+3A8h+var_370]
0x180020a51  mov     r9d, esi
0x180020a54  mov     [rsp+3A8h+lpString2], rax; __int64
0x180020a59  lea     rdx, [rsp+3A8h+var_368]
0x180020a5e  mov     rcx, r14; struct ldap_connection *
0x180020a61  call    LdapParallelConnect
0x180020a66  mov     ebp, eax
0x180020a68  test    eax, eax
0x180020a6a  jz      loc_180020DD0
0x180020a70  xor     ebx, ebx
0x180020a72  test    esi, esi
0x180020a74  jz      short loc_180020AB9
0x180020a76  lea     rdi, [rsp+3A8h+var_368]
0x180020a7b  mov     rax, [rdi+rbx*8]
0x180020a7f  lea     rdi, [rdi+rbx*8]
0x180020a83  test    rax, rax
0x180020a86  jz      short loc_180020AB3
0x180020a88  mov     rcx, [rax]
0x180020a8b  test    rcx, rcx
0x180020a8e  jz      short loc_180020AAB
0x180020a90  mov     rcx, [rcx]
0x180020a93  test    rcx, rcx
0x180020a96  jnz     loc_1800212C1
0x180020a9c  mov     rax, [rdi]
0x180020a9f  mov     r15, [rax]
0x180020aa2  test    r15, r15
0x180020aa5  jnz     loc_180020BE7
0x180020aab  mov     rdi, [rdi]
0x180020aae  test    rdi, rdi
0x180020ab1  jnz     short loc_180020AEE
0x180020ab3  inc     ebx
0x180020ab5  cmp     ebx, esi
0x180020ab7  jb      short loc_180020A76
0x180020ab9  mov     rdi, [rsp+3A8h+var_38]
0x180020ac1  mov     eax, ebp
0x180020ac3  mov     rbx, [rsp+3A8h+arg_10]
0x180020acb  mov     rcx, [rsp+3A8h+var_48]
0x180020ad3  xor     rcx, rsp; StackCookie
0x180020ad6  call    __security_check_cookie
0x180020adb  add     rsp, 378h
0x180020ae2  pop     r15
0x180020ae4  pop     r14
0x180020ae6  pop     r13
0x180020ae8  pop     r12
0x180020aea  pop     rsi
0x180020aeb  pop     rbp
0x180020aec  retn
0x180020aee  mov     eax, [rdi-8]
0x180020af1  cmp     eax, 6461424Ch
0x180020af6  jz      short loc_180020AB3
0x180020af8  cmp     eax, 6572464Ch
0x180020afd  jz      loc_18002138F
0x180020b03  cmp     cs:g_fTracingOn, 0
0x180020b0a  jnz     loc_1800213CF
0x180020b10  mov     r9d, [rdi-8]
0x180020b14  cmp     r9d, 7264534Ch
0x180020b1b  jnz     loc_180020F69
0x180020b21  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180020b27  mov     r8d, [rdi-4]
0x180020b2b  sub     eax, r8d
0x180020b2e  cmp     cs:g_fTracingOn, 0
0x180020b35  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180020b3b  jnz     loc_18002140F
0x180020b41  mov     rcx, cs:LdapHeap; hHeap
0x180020b48  lea     r8, [rdi-8]; lpMem
0x180020b4c  xor     edx, edx; dwFlags
0x180020b4e  mov     dword ptr [rdi-8], 6572464Ch
0x180020b55  call    cs:__imp_HeapFree
0x180020b5c  nop     dword ptr [rax+rax+00h]
0x180020b61  jmp     loc_180020AB3
0x180020b66  cmp     esi, 63h ; 'c'
0x180020b69  jnb     loc_180020A00
0x180020b6f  mov     rcx, cs:LdapHeap; hHeap
0x180020b76  mov     edx, 8; dwFlags
0x180020b7b  mov     r8d, 18h; dwBytes
0x180020b81  call    cs:__imp_HeapAlloc
0x180020b88  nop     dword ptr [rax+rax+00h]
0x180020b8d  cmp     cs:g_fTracingOn, 0
0x180020b94  mov     rbx, rax
0x180020b97  jnz     loc_180020FEF
0x180020b9d  test    rbx, rbx
0x180020ba0  jz      short loc_180020BBA
0x180020ba2  mov     dword ptr [rbx], 7264534Ch
0x180020ba8  mov     dword ptr [rbx+4], 10h
0x180020baf  add     rbx, 8
0x180020bb3  add     cs:?LdapAllocatedHeap@@3KA, 10h; ulong LdapAllocatedHeap
0x180020bba  cmp     cs:g_fTracingOn, 0
0x180020bc1  jnz     loc_1800210B2
0x180020bc7  lea     rdi, [rsp+3A8h+var_368]
0x180020bcc  mov     [rdi+rsi*8], rbx
0x180020bd0  lea     rdi, [rdi+rsi*8]
0x180020bd4  test    rbx, rbx
0x180020bd7  jnz     loc_180020C65
0x180020bdd  mov     ebp, 5Ah ; 'Z'
0x180020be2  jmp     loc_180020A70
0x180020be7  mov     eax, [r15-8]
0x180020beb  cmp     eax, 6461424Ch
0x180020bf0  jz      loc_180020AAB
0x180020bf6  cmp     eax, 6572464Ch
0x180020bfb  jz      loc_1800212D0
0x180020c01  cmp     cs:g_fTracingOn, 0
0x180020c08  jnz     loc_180021310
0x180020c0e  mov     r9d, [r15-8]
0x180020c12  cmp     r9d, 7264534Ch
0x180020c19  jnz     loc_180020FAC
0x180020c1f  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x180020c25  mov     r8d, [r15-4]
0x180020c29  sub     eax, r8d
0x180020c2c  cmp     cs:g_fTracingOn, 0
0x180020c33  mov     cs:?LdapAllocatedHeap@@3KA, eax; ulong LdapAllocatedHeap
0x180020c39  jnz     loc_180021350
0x180020c3f  mov     rcx, cs:LdapHeap; hHeap
0x180020c46  lea     r8, [r15-8]; lpMem
0x180020c4a  xor     edx, edx; dwFlags
0x180020c4c  mov     dword ptr [r15-8], 6572464Ch
0x180020c54  call    cs:__imp_HeapFree
0x180020c5b  nop     dword ptr [rax+rax+00h]
0x180020c60  jmp     loc_180020AAB
0x180020c65  mov     rcx, cs:LdapHeap; hHeap
0x180020c6c  mov     edx, 8; dwFlags
0x180020c71  mov     r8d, 18h; dwBytes
0x180020c77  call    cs:__imp_HeapAlloc
0x180020c7e  nop     dword ptr [rax+rax+00h]
0x180020c83  cmp     cs:g_fTracingOn, 0
0x180020c8a  mov     rbx, rax
0x180020c8d  jnz     loc_180021030
0x180020c93  test    rbx, rbx
0x180020c96  jz      short loc_180020CB0
0x180020c98  mov     dword ptr [rbx], 7264534Ch
0x180020c9e  mov     dword ptr [rbx+4], 10h
0x180020ca5  add     rbx, 8
0x180020ca9  add     cs:?LdapAllocatedHeap@@3KA, 10h; ulong LdapAllocatedHeap
0x180020cb0  cmp     cs:g_fTracingOn, 0
0x180020cb7  jnz     loc_1800210FD
0x180020cbd  mov     rax, [rdi]
0x180020cc0  mov     [rax], rbx
0x180020cc3  mov     rax, [rdi]
0x180020cc6  cmp     qword ptr [rax], 0
0x180020cca  jz      loc_180020BDD
0x180020cd0  mov     rcx, cs:LdapHeap; hHeap
0x180020cd7  mov     edx, 8; dwFlags
0x180020cdc  mov     r8d, 88h; dwBytes
0x180020ce2  call    cs:__imp_HeapAlloc
0x180020ce9  nop     dword ptr [rax+rax+00h]
0x180020cee  cmp     cs:g_fTracingOn, 0
0x180020cf5  mov     rbx, rax
0x180020cf8  jnz     loc_180021071
0x180020cfe  test    rbx, rbx
0x180020d01  jz      short loc_180020D1B
0x180020d03  mov     dword ptr [rbx], 7264534Ch
0x180020d09  mov     dword ptr [rbx+4], 80h
0x180020d10  add     rbx, 8
0x180020d14  sub     cs:?LdapAllocatedHeap@@3KA, 0FFFFFF80h; ulong LdapAllocatedHeap
0x180020d1b  cmp     cs:g_fTracingOn, 0
0x180020d22  jnz     loc_180021148
0x180020d28  mov     rax, [rdi]
0x180020d2b  mov     rcx, [rax]
0x180020d2e  mov     [rcx], rbx
0x180020d31  mov     rax, [rdi]
0x180020d34  mov     rcx, [rax]
0x180020d37  mov     rbx, [rcx]
0x180020d3a  test    rbx, rbx
0x180020d3d  jz      loc_1800211C3
0x180020d43  mov     dword ptr [rcx+8], 80h
0x180020d4a  movsx   rdx, word ptr [r15+2]
0x180020d4f  mov     rax, [rdi]
0x180020d52  mov     r8d, edx
0x180020d55  mov     rcx, [rax]
0x180020d58  cmp     edx, [rcx+8]
0x180020d5b  jg      loc_180021193
0x180020d61  movzx   eax, word ptr [r15]
0x180020d65  mov     ecx, 2
0x180020d6a  cmp     cx, ax
0x180020d6d  jz      loc_180020F47
0x180020d73  mov     ecx, 17h
0x180020d78  cmp     cx, ax
0x180020d7b  jnz     short loc_180020D9A
0x180020d7d  mov     r8, rdx; Size
0x180020d80  lea     rcx, [rbx+8]; void *
0x180020d84  mov     rdx, [r15+8]; Src
0x180020d88  call    memcpy_0
0x180020d8d  mov     rax, [rdi]
0x180020d90  mov     rcx, [rax]
0x180020d93  mov     dword ptr [rcx+8], 1Ch
0x180020d9a  movzx   eax, word ptr [r15]
0x180020d9e  movzx   ecx, [rsp+3A8h+var_378]; hostshort
0x180020da3  mov     [rbx], ax
0x180020da6  call    cs:__imp_htons
0x180020dad  nop     dword ptr [rax+rax+00h]
0x180020db2  mov     [rbx+2], ax
0x180020db6  inc     esi
0x180020db8  mov     rax, [rdi]
0x180020dbb  mov     qword ptr [rax+8], 0
0x180020dc3  mov     rax, [r13+18h]
0x180020dc7  mov     r15, [rax+rsi*8]
0x180020dcb  jmp     loc_1800209F7
0x180020dd0  mov     rcx, [r13+8]; Src
0x180020dd4  test    rcx, rcx
0x180020dd7  jz      loc_180021235
0x180020ddd  xor     edx, edx
0x180020ddf  mov     r8d, 7473484Ch
0x180020de5  call    ldap_dup_stringW
0x180020dea  mov     [r14+1A0h], rax
0x180020df1  cmp     qword ptr [r13+8], 0
0x180020df6  jnz     short loc_180020DFF
0x180020df8  cmp     qword ptr [r13+0], 0
0x180020dfd  jz      short loc_180020E08
0x180020dff  test    rax, rax
0x180020e02  jz      loc_180020BDD
0x180020e08  mov     rcx, [r14+3E0h]
0x180020e0f  mov     edx, 7473484Ch
0x180020e14  call    ldapFree
0x180020e19  mov     qword ptr [r14+3E0h], 0
0x180020e24  mov     rcx, [r13+8]; lpWideCharStr
0x180020e28  test    rcx, rcx
0x180020e2b  jz      loc_18002123E
0x180020e31  mov     r8d, 7473484Ch
0x180020e37  lea     rdx, [r14+3E0h]
0x180020e3e  call    FromUnicodeWithAlloc
0x180020e43  mov     ebp, eax
0x180020e45  test    eax, eax
0x180020e47  jnz     loc_180020A70
0x180020e4d  mov     rcx, [r14+1A0h]; Src
0x180020e54  xor     edx, edx
0x180020e56  mov     r8d, 7473484Ch
0x180020e5c  call    ldap_dup_stringW
0x180020e61  mov     r8, [r14+1A0h]
0x180020e68  mov     [r14+1B0h], rax
0x180020e6f  test    r8, r8
0x180020e72  jnz     loc_180021247
0x180020e78  cmp     cs:g_fTracingOn, 0
0x180020e7f  jnz     loc_180021255
0x180020e85  mov     r8, [r14+180h]; lpString1
0x180020e8c  lea     r15, [r14+178h]
0x180020e93  lea     r12, [r14+174h]
0x180020e9a  test    r8, r8
0x180020e9d  jz      short loc_180020ED5
0x180020e9f  lea     rax, aLocalhost; "localhost"
0x180020ea6  mov     [rsp+3A8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180020eae  mov     r9d, 0FFFFFFFFh; cchCount1
0x180020eb4  mov     [rsp+3A8h+lpString2], rax; lpString2
0x180020eb9  mov     edx, ebx; dwCmpFlags
0x180020ebb  mov     ecx, 400h; Locale
0x180020ec0  call    cs:__imp_CompareStringW
0x180020ec7  nop     dword ptr [rax+rax+00h]
0x180020ecc  cmp     eax, 2
0x180020ecf  jz      loc_180021289
0x180020ed5  mov     rdx, r15; struct _SOCKET_ADDRESS ***
0x180020ed8  mov     rcx, r12; unsigned int *
0x180020edb  mov     rbx, r15
0x180020ede  mov     rdi, r12
0x180020ee1  call    ?FreeSocketAddressArr@@YAXPEAKPEAPEAPEAU_SOCKET_ADDRESS@@@Z; FreeSocketAddressArr(ulong *,_SOCKET_ADDRESS * * *)
0x180020ee6  lea     ecx, ds:0[rsi*8]
0x180020eed  mov     edx, 7264534Ch
0x180020ef2  call    ldapMalloc
0x180020ef7  mov     [rbx], rax
0x180020efa  test    rax, rax
0x180020efd  jz      loc_180020BDD
0x180020f03  xor     edx, edx
0x180020f05  test    esi, esi
  ... truncated ...
```
