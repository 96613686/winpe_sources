# CopyResultToCache(ldap_connection *,ldapmsg *)

- ea: `0x1800057a0`
- end: `0x180006196`
- name: `?CopyResultToCache@@YAEPEAUldap_connection@@PEAUldapmsg@@@Z`
- size: `2550`
- prototype: `unsigned __int8 __fastcall(struct ldap_connection *, struct ldapmsg *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180006d80`
- `0x180045b90`

## callees

- `0x1800037a8`
- `0x18000461c`
- `0x180004740`
- `0x180005170`
- `0x1800057a0`
- `0x1800061a0`
- `0x180006510`
- `0x180006b20`
- `0x18000b440`
- `0x18001ba9c`
- `0x18001ce90`
- `0x18001e7b0`
- `0x180022e80`
- `0x180032bd8`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800058a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800058a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005806`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006033`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005806`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005dd2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006033`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ba5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005ba5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005c90`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000595b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000595b`

## string_xrefs

- `0x180005f5e`: `Copying RootDSE of '%S' to cache...\n`
- `0x180005fc8`: `No space to cache new server RootDSE, increase MAX_CACHE_SIZE\n`
- `0x1800058f9`: `Found empty slot %d, creating new cache page\n`
- `0x180006063`: `CopyResultToCache: refcount is %d, CacheIndex is %d\n`

## pseudocode

```c
unsigned __int8 __fastcall CopyResultToCache(const wchar_t **a1, struct ldapmsg *a2)
{
  PCHAR *v5; // rcx
  __int64 v6; // rdx
  int v7; // esi
  struct _CACHEHOLDER *v8; // r14
  int v9; // ebp
  int i; // ebx
  struct _CACHEHOLDER * near **v11; // rdi
  const WCHAR *v12; // r8
  const WCHAR *lpString2; // rcx
  bool v14; // zf
  struct _CACHEHOLDER * near *v15; // rax
  struct _CACHEHOLDER **v16; // rbx
  __int64 TickCount; // rax
  struct _CACHEHOLDER *v18; // rcx
  __int64 v19; // rbp
  _DWORD *v20; // rsi
  const WCHAR *Attribute; // rax
  int v22; // edi
  const WCHAR *v23; // r14
  __int64 v24; // r12
  __int64 v25; // r15
  __int64 v26; // rcx
  const WCHAR *v27; // rdx
  unsigned int v28; // ecx
  size_t v29; // rdi
  unsigned int v30; // ebp
  struct _CACHEHOLDER *v31; // rax
  _QWORD *v32; // rdi
  unsigned __int64 v33; // rdi
  unsigned int v34; // esi
  char *v35; // r14
  unsigned int v36; // r14d
  char *v37; // r15
  _WORD *v38; // rdx
  unsigned int v39; // ecx
  _DWORD *v40; // rdi
  size_t v41; // rsi
  unsigned int v42; // ebp
  __int64 v43; // rax
  int v44; // esi
  struct _CACHEHOLDER **v45; // rax
  struct _CACHEHOLDER * near **v46; // rdi
  __int64 v47; // rax
  struct _CACHEHOLDER * near *v48; // rcx
  char *Src; // [rsp+30h] [rbp-58h]
  PCHAR Srca; // [rsp+30h] [rbp-58h]
  unsigned int *v51; // [rsp+38h] [rbp-50h] BYREF
  __int64 v52; // [rsp+40h] [rbp-48h]
  struct ldapmsg *v53; // [rsp+98h] [rbp+10h]
  int v54; // [rsp+A0h] [rbp+18h]
  PCHAR *vals; // [rsp+A8h] [rbp+20h] BYREF

  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
    LDAPClientPrint(16, "Copying RootDSE of '%S' to cache...\n", a1[52]);
  if ( !a2 )
    return 0;
  SetConnectionError(a1, 0);
  if ( a2 == (struct ldapmsg *)-1LL )
    return 0;
  do
  {
    if ( a2->lm_msgtype == 100 )
      break;
    a2 = a2->lm_chain;
  }
  while ( a2 );
  v53 = a2;
  if ( !a2 || !ValidateServerReturnedAttrList((struct ldap_connection *)a1, a2) )
    return 0;
  EnterCriticalSection(&CacheLock);
  if ( GlobalLdapShuttingDown == 1 )
    goto LABEL_129;
  v7 = -1;
  v8 = 0;
  v9 = -1;
  for ( i = 0; ; ++i )
  {
    while ( 1 )
    {
      if ( i >= 5 )
        goto LABEL_15;
      v11 = &(&CacheArray)[i];
      if ( *v11 )
        break;
      if ( v9 != -1 )
        goto LABEL_30;
      v9 = i++;
    }
    v12 = a1[52];
    lpString2 = (const WCHAR *)(*v11)[1];
    if ( !v12 )
      break;
    if ( lpString2 )
    {
      v14 = CompareStringW(0x400u, 1u, v12, -1, lpString2, -1) == 2;
      goto LABEL_25;
    }
LABEL_26:
    v15 = *v11;
    if ( v7 == -1 )
    {
      if ( *(_DWORD *)v15 )
        continue;
      v8 = v15[4];
      goto LABEL_29;
    }
    if ( v8 > v15[4] && !*(_DWORD *)v15 )
    {
      v8 = v15[4];
LABEL_29:
      v7 = i;
      continue;
    }
LABEL_30:
    ;
  }
  v14 = lpString2 == 0;
LABEL_25:
  if ( !v14 || *((_WORD *)*v11 + 8) != *((_WORD *)a1 + 253) )
    goto LABEL_26;
  if ( i != -1 )
    goto LABEL_33;
LABEL_15:
  if ( v9 != -1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
      LDAPClientPrint(16, "Found empty slot %d, creating new cache page\n", v9);
    i = v9;
    goto LABEL_108;
  }
  if ( v7 != -1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
      LDAPClientPrint(16, "Deleting existing page %d for lack of space\n", v7);
    FreeCachePage((struct _CACHEHOLDER *)(&CacheArray)[v7]);
    (&CacheArray)[v7] = 0;
    i = v7;
LABEL_108:
    v45 = (struct _CACHEHOLDER **)ldapMalloc(280, 1818318412);
    (&CacheArray)[i] = v45;
    v46 = &(&CacheArray)[i];
    if ( v45 )
    {
      v47 = ldap_dup_stringW((void *)a1[52]);
      v48 = *v46;
      (*v46)[1] = (struct _CACHEHOLDER *)v47;
      if ( v47 )
      {
        *((_WORD *)v48 + 8) = *((_WORD *)a1 + 253);
LABEL_33:
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
          LDAPClientPrint(16, "CopyResultToCache: refcount is %d, CacheIndex is %d\n", *(_DWORD *)(&CacheArray)[i], i);
        v16 = (struct _CACHEHOLDER **)&(&CacheArray)[i];
        *((_QWORD *)*v16 + 3) = LdapGetTickCount();
        TickCount = LdapGetTickCount();
        v18 = *v16;
        v19 = (__int64)v53;
        v20 = 0;
        v51 = 0;
        *((_QWORD *)v18 + 4) = TickCount;
        Attribute = (const WCHAR *)LdapFirstAttribute((struct ldap_connection *)a1, (__int64)v53, &v51, 1);
        v22 = 0;
        v54 = 0;
LABEL_35:
        v23 = Attribute;
        if ( !Attribute )
        {
          ++*(_DWORD *)*v16;
          LeaveCriticalSection(&CacheLock);
          return 1;
        }
        vals = 0;
        LdapGetValues((struct ldap_connection *)a1, v19, Attribute, 0, 1, &vals);
        LODWORD(v24) = 0;
        if ( vals && *vals )
        {
          do
            v24 = (unsigned int)(v24 + 1);
          while ( vals[v24] );
        }
        v25 = v22;
        v26 = *((_QWORD *)*v16 + v22 + 5);
        if ( v26 )
          ldapFree(v26, 1818318412);
        v27 = v23;
        v28 = 1;
        while ( *v27 )
        {
          if ( v28 + 1 < v28 )
            goto LABEL_5;
          ++v28;
          ++v27;
        }
        v29 = 2LL * v28;
        if ( v29 > 0xFFFFFFFF )
          goto LABEL_5;
        v30 = v29 + 8;
        if ( (int)v29 + 8 < (unsigned int)v29 )
          v30 = -1;
        else
          v20 = HeapAlloc(LdapHeap, 8u, v30);
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
            v30,
            (_DWORD)v20,
            1818318412);
        if ( v20 )
        {
          *v20 = 1818318412;
          v20[1] = v29;
          v20 += 2;
          LdapAllocatedHeap += v29;
        }
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
          LDAPClientPrint(
            8,
            "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
            v29,
            (_DWORD)v20,
            1818318412,
            LdapAllocatedHeap);
        if ( v20 )
        {
          memcpy_0(v20, v23, v29);
          v31 = *v16;
          *((_QWORD *)v31 + v25 + 5) = v20;
          v32 = (_QWORD *)*((_QWORD *)v31 + v25 + 20);
          if ( v32 )
          {
            v44 = 0;
            if ( *v32 )
            {
              do
                ldapFree(v32[v44++], 1818318412);
              while ( v32[v44] );
            }
            ldapFree(v32, 1819039308);
            *((_QWORD *)*v16 + v25 + 20) = 0;
          }
          if ( (int)v24 + 1 < (unsigned int)v24 || (v33 = 8LL * (unsigned int)(v24 + 1), v33 > 0xFFFFFFFF) )
          {
            ldap_value_free(vals);
            FreeCachePage(*v16);
            *v16 = 0;
            LeaveCriticalSection(&CacheLock);
            v6 = 82;
            goto LABEL_8;
          }
          v34 = v33 + 8;
          if ( (int)v33 + 8 < (unsigned int)v33 )
          {
            v35 = 0;
            v34 = -1;
          }
          else
          {
            v35 = (char *)HeapAlloc(LdapHeap, 8u, v34);
          }
          Src = v35;
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(
              8,
              "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
              v34,
              (_DWORD)v35,
              1819039308);
          if ( v35 )
          {
            *(_DWORD *)v35 = 1819039308;
            *((_DWORD *)v35 + 1) = v33;
            v35 += 8;
            LdapAllocatedHeap += v33;
            Src = v35;
          }
          if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
            LDAPClientPrint(
              8,
              "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
              v33,
              (_DWORD)v35,
              1819039308,
              LdapAllocatedHeap);
          if ( v35 )
          {
            v20 = 0;
            *((_QWORD *)*v16 + v25 + 20) = v35;
            v36 = 0;
            v5 = vals;
            v37 = Src;
            while ( 1 )
            {
              if ( v36 >= (unsigned int)v24 )
              {
                ldap_value_free(v5);
                v19 = (__int64)v53;
                v22 = ++v54;
                Attribute = (const WCHAR *)LdapNextAttribute((__int64)a1, (__int64)v53, v51, 1);
                goto LABEL_35;
              }
              v52 = 8LL * v36;
              Srca = v5[(unsigned __int64)v52 / 8];
              if ( Srca )
              {
                v38 = v5[(unsigned __int64)v52 / 8];
                v39 = 1;
                while ( *v38 )
                {
                  if ( v39 + 1 < v39 )
                    goto LABEL_70;
                  ++v39;
                  ++v38;
                }
                v41 = 2LL * v39;
                if ( v41 <= 0xFFFFFFFF )
                {
                  v42 = v41 + 8;
                  if ( (int)v41 + 8 < (unsigned int)v41 )
                  {
                    v40 = 0;
                    v42 = -1;
                  }
                  else
                  {
                    v40 = HeapAlloc(LdapHeap, 8u, v42);
                  }
                  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                    LDAPClientPrint(
                      8,
                      "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
                      v42,
                      (_DWORD)v40,
                      1818318412);
                  if ( v40 )
                  {
                    *v40 = 1818318412;
                    v40[1] = v41;
                    v40 += 2;
                    LdapAllocatedHeap += v41;
                  }
                  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
                    LDAPClientPrint(
                      8,
                      "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
                      v41,
                      (_DWORD)v40,
                      1818318412,
                      LdapAllocatedHeap);
                  if ( v40 )
                  {
                    memcpy_0(v40, Srca, v41);
                    v20 = 0;
                    goto LABEL_80;
                  }
                }
                v20 = 0;
              }
LABEL_70:
              v40 = 0;
LABEL_80:
              v43 = v52;
              *(_QWORD *)&v37[v52] = v40;
              v5 = vals;
              if ( *(PCHAR *)((char *)vals + v43) && !v40 )
                goto LABEL_6;
              ++v36;
            }
          }
          ldap_value_free(vals);
          FreeCachePage(*v16);
          *v16 = 0;
        }
        else
        {
LABEL_5:
          *((_QWORD *)*v16 + v25 + 5) = 0;
          v5 = vals;
LABEL_6:
          ldap_value_free(v5);
          FreeCachePage(*v16);
          *v16 = 0;
        }
        LeaveCriticalSection(&CacheLock);
        v6 = 90;
LABEL_8:
        SetConnectionError(a1, v6);
        return 0;
      }
      ldapFree(v48, 1818318412);
      *v46 = 0;
    }
    SetConnectionError(a1, 90);
    goto LABEL_129;
  }
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10) != 0 )
    LDAPClientTraceEvent(16, "No space to cache new server RootDSE, increase MAX_CACHE_SIZE\n");
LABEL_129:
  LeaveCriticalSection(&CacheLock);
  return 0;
}

```

## disassembly

```asm
0x1800057a0  mov     [rsp+arg_8], rdx
0x1800057a5  push    rbp
0x1800057a6  push    r13
0x1800057a8  sub     rsp, 78h
0x1800057ac  cmp     cs:g_fTracingOn, 0
0x1800057b3  mov     rbp, rdx
0x1800057b6  mov     r13, rcx
0x1800057b9  jnz     loc_180005F3D
0x1800057bf  test    rbp, rbp
0x1800057c2  jz      short loc_1800057D4
0x1800057c4  xor     edx, edx
0x1800057c6  mov     rcx, r13
0x1800057c9  call    SetConnectionError
0x1800057ce  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800057d2  jnz     short loc_180005850
0x1800057d4  xor     al, al
0x1800057d6  add     rsp, 78h
0x1800057da  pop     r13
0x1800057dc  pop     rbp
0x1800057dd  retn
0x1800057df  mov     rax, [rbx]
0x1800057e2  mov     [rax+r15*8+28h], rsi
0x1800057e7  mov     rcx, [rsp+88h+vals]; vals
0x1800057ef  call    ldap_value_free
0x1800057f4  mov     rcx, [rbx]; struct _CACHEHOLDER *
0x1800057f7  call    ?FreeCachePage@@YAXPEAU_CACHEHOLDER@@@Z; FreeCachePage(_CACHEHOLDER *)
0x1800057fc  mov     [rbx], rsi
0x1800057ff  lea     rcx, CacheLock; lpCriticalSection
0x180005806  call    cs:__imp_LeaveCriticalSection
0x18000580d  nop     dword ptr [rax+rax+00h]
0x180005812  mov     edx, 5Ah ; 'Z'
0x180005817  mov     rcx, r13
0x18000581a  call    SetConnectionError
0x18000581f  xor     al, al
0x180005821  mov     r12, [rsp+88h+var_28]
0x180005826  mov     r14, [rsp+88h+var_30]
0x18000582b  mov     rdi, [rsp+88h+var_20]
0x180005830  mov     rsi, [rsp+88h+var_18]
0x180005835  mov     rbx, [rsp+88h+arg_0]
0x18000583d  mov     r15, [rsp+88h+var_38]
0x180005842  add     rsp, 78h
0x180005846  pop     r13
0x180005848  pop     rbp
0x180005849  retn
0x180005850  cmp     dword ptr [rbp+4], 64h ; 'd'
0x180005854  jnz     loc_180005F74
0x18000585a  mov     [rsp+88h+arg_8], rbp
0x180005862  test    rbp, rbp
0x180005865  jz      loc_1800057D4
0x18000586b  mov     rdx, rbp; struct ldapmsg *
0x18000586e  mov     rcx, r13; struct ldap_connection *
0x180005871  call    ?ValidateServerReturnedAttrList@@YAEPEAUldap_connection@@PEAUldapmsg@@@Z; ValidateServerReturnedAttrList(ldap_connection *,ldapmsg *)
0x180005876  test    al, al
0x180005878  jz      loc_1800057D4
0x18000587e  mov     [rsp+88h+arg_0], rbx
0x180005886  lea     rcx, CacheLock; lpCriticalSection
0x18000588d  mov     [rsp+88h+var_18], rsi
0x180005892  mov     [rsp+88h+var_20], rdi
0x180005897  mov     [rsp+88h+var_30], r14
0x18000589c  mov     [rsp+88h+var_38], r15
0x1800058a1  call    cs:__imp_EnterCriticalSection
0x1800058a8  nop     dword ptr [rax+rax+00h]
0x1800058ad  cmp     cs:GlobalLdapShuttingDown, 1
0x1800058b4  jz      loc_18000602C
0x1800058ba  mov     esi, 0FFFFFFFFh
0x1800058bf  lea     r15, ?CacheArray@@3PAPEAU_CACHEHOLDER@@A; _CACHEHOLDER * near * CacheArray
0x1800058c6  xor     r14d, r14d
0x1800058c9  mov     ebp, esi
0x1800058cb  xor     ebx, ebx
0x1800058cd  cmp     ebx, 5
0x1800058d0  jl      short loc_180005911
0x1800058d2  cmp     ebp, 0FFFFFFFFh
0x1800058d5  jz      loc_180005FA4
0x1800058db  cmp     cs:g_fTracingOn, 0
0x1800058e2  jz      short loc_18000590A
0x1800058e4  cmp     cs:g_fProviderEnabled, 0
0x1800058eb  jz      short loc_18000590A
0x1800058ed  test    byte ptr cs:g_ulTraceFlags, 10h
0x1800058f4  jz      short loc_18000590A
0x1800058f6  mov     r8d, ebp
0x1800058f9  lea     rdx, aFoundEmptySlot; "Found empty slot %d, creating new cache"...
0x180005900  mov     ecx, 10h
0x180005905  call    LDAPClientPrint
0x18000590a  mov     ebx, ebp
0x18000590c  jmp     loc_180005EE5
0x180005911  movsxd  rax, ebx
0x180005914  lea     rdi, [r15+rax*8]
0x180005918  mov     rax, [r15+rax*8]
0x18000591c  test    rax, rax
0x18000591f  jz      loc_180005DE5
0x180005925  mov     r8, [r13+1A0h]; lpString1
0x18000592c  mov     rcx, [rax+8]
0x180005930  test    r8, r8
0x180005933  jz      loc_180005EB7
0x180005939  test    rcx, rcx
0x18000593c  jz      short loc_180005971
0x18000593e  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x180005946  mov     edx, 1; dwCmpFlags
0x18000594b  mov     [rsp+88h+lpString2], rcx; lpString2
0x180005950  mov     r9d, 0FFFFFFFFh; cchCount1
0x180005956  mov     ecx, 400h; Locale
0x18000595b  call    cs:__imp_CompareStringW
0x180005962  nop     dword ptr [rax+rax+00h]
0x180005967  cmp     eax, 2
0x18000596a  setz    al
0x18000596d  test    al, al
0x18000596f  jnz     short loc_18000598F
0x180005971  mov     rax, [rdi]
0x180005974  cmp     esi, 0FFFFFFFFh
0x180005977  jnz     loc_180005F86
0x18000597d  cmp     dword ptr [rax], 0
0x180005980  jnz     short loc_180005988
0x180005982  mov     r14, [rax+20h]
0x180005986  mov     esi, ebx
0x180005988  inc     ebx
0x18000598a  jmp     loc_1800058CD
0x18000598f  mov     rcx, [rdi]
0x180005992  movzx   eax, word ptr [r13+1FAh]
0x18000599a  cmp     [rcx+10h], ax
0x18000599e  jnz     short loc_180005971
0x1800059a0  cmp     ebx, 0FFFFFFFFh
0x1800059a3  jz      loc_1800058D2
0x1800059a9  cmp     cs:g_fTracingOn, 0
0x1800059b0  mov     [rsp+88h+var_28], r12
0x1800059b5  jnz     loc_180006046
0x1800059bb  call    LdapGetTickCount
0x1800059c0  movsxd  rcx, ebx
0x1800059c3  lea     rbx, [r15+rcx*8]
0x1800059c7  mov     rcx, [r15+rcx*8]
0x1800059cb  mov     [rcx+18h], rax
0x1800059cf  call    LdapGetTickCount
0x1800059d4  mov     rcx, [rbx]
0x1800059d7  lea     r8, [rsp+88h+var_50]
0x1800059dc  mov     rbp, [rsp+88h+arg_8]
0x1800059e4  xor     esi, esi
0x1800059e6  mov     r9b, 1
0x1800059e9  mov     [rsp+88h+var_50], rsi
0x1800059ee  mov     rdx, rbp
0x1800059f1  mov     [rcx+20h], rax
0x1800059f5  mov     rcx, r13; struct ldap_connection *
0x1800059f8  call    LdapFirstAttribute
0x1800059fd  mov     edi, esi
0x1800059ff  mov     [rsp+88h+arg_10], esi
0x180005a06  mov     r14, rax
0x180005a09  test    rax, rax
0x180005a0c  jz      loc_180005DC6
0x180005a12  lea     rax, [rsp+88h+vals]
0x180005a1a  mov     [rsp+88h+vals], rsi
0x180005a22  mov     qword ptr [rsp+88h+cchCount2], rax; __int64
0x180005a27  xor     r9d, r9d
0x180005a2a  mov     r8, r14
0x180005a2d  mov     byte ptr [rsp+88h+lpString2], 1; char
0x180005a32  mov     rdx, rbp
0x180005a35  mov     rcx, r13; struct ldap_connection *
0x180005a38  call    LdapGetValues
0x180005a3d  mov     rcx, [rsp+88h+vals]
0x180005a45  mov     r12d, esi
0x180005a48  test    rcx, rcx
0x180005a4b  jnz     loc_180005D68
0x180005a51  mov     rax, [rbx]
0x180005a54  movsxd  r15, edi
0x180005a57  mov     rcx, [rax+r15*8+28h]
0x180005a5c  test    rcx, rcx
0x180005a5f  jnz     loc_180006083
0x180005a65  mov     rdx, r14
0x180005a68  mov     ecx, 1
0x180005a6d  nop     dword ptr [rax]
0x180005a70  cmp     word ptr [rdx], 0
0x180005a74  jz      short loc_180005A89
0x180005a76  lea     eax, [rcx+1]
0x180005a79  cmp     eax, ecx
0x180005a7b  jb      loc_1800057DF
0x180005a81  mov     ecx, eax
0x180005a83  add     rdx, 2
0x180005a87  jmp     short loc_180005A70
0x180005a89  mov     edi, ecx
0x180005a8b  mov     eax, 0FFFFFFFFh
0x180005a90  add     rdi, rdi
0x180005a93  cmp     rdi, rax
0x180005a96  ja      loc_1800057DF
0x180005a9c  lea     ebp, [rdi+8]
0x180005a9f  cmp     ebp, edi
0x180005aa1  jb      loc_180005D61
0x180005aa7  mov     rcx, cs:LdapHeap; hHeap
0x180005aae  mov     edx, 8; dwFlags
0x180005ab3  mov     r8d, ebp; dwBytes
0x180005ab6  call    cs:__imp_HeapAlloc
0x180005abd  nop     dword ptr [rax+rax+00h]
0x180005ac2  mov     rsi, rax
0x180005ac5  cmp     cs:g_fTracingOn, 0
0x180005acc  jnz     loc_180005E35
0x180005ad2  test    rsi, rsi
0x180005ad5  jz      short loc_180005AEA
0x180005ad7  mov     dword ptr [rsi], 6C61564Ch
0x180005add  mov     [rsi+4], edi
0x180005ae0  add     rsi, 8
0x180005ae4  add     cs:?LdapAllocatedHeap@@3KA, edi; ulong LdapAllocatedHeap
0x180005aea  cmp     cs:g_fTracingOn, 0
0x180005af1  jnz     loc_180006092
0x180005af7  test    rsi, rsi
0x180005afa  jz      loc_180006191
0x180005b00  mov     r8, rdi; Size
0x180005b03  mov     rdx, r14; Src
0x180005b06  mov     rcx, rsi; void *
0x180005b09  call    memcpy_0
0x180005b0e  mov     rax, [rbx]
0x180005b11  mov     rbp, [rsp+88h+arg_8]
0x180005b19  mov     [rsp+88h+arg_8], rbp
0x180005b21  mov     [rax+r15*8+28h], rsi
0x180005b26  mov     rdi, [rax+r15*8+0A0h]
0x180005b2e  test    rdi, rdi
0x180005b31  jnz     loc_180005D81
0x180005b37  lea     eax, [r12+1]
0x180005b3c  cmp     eax, r12d
0x180005b3f  jb      short loc_180005B52
0x180005b41  mov     edi, eax
0x180005b43  mov     r8d, 0FFFFFFFFh
0x180005b49  shl     rdi, 3
0x180005b4d  cmp     rdi, r8
0x180005b50  jbe     short loc_180005B8B
0x180005b52  mov     rcx, [rsp+88h+vals]; vals
0x180005b5a  call    ldap_value_free
0x180005b5f  mov     rcx, [rbx]; struct _CACHEHOLDER *
0x180005b62  call    ?FreeCachePage@@YAXPEAU_CACHEHOLDER@@@Z; FreeCachePage(_CACHEHOLDER *)
0x180005b67  lea     rcx, CacheLock; lpCriticalSection
0x180005b6e  mov     qword ptr [rbx], 0
0x180005b75  call    cs:__imp_LeaveCriticalSection
0x180005b7c  nop     dword ptr [rax+rax+00h]
0x180005b81  mov     edx, 52h ; 'R'
0x180005b86  jmp     loc_180005817
0x180005b8b  lea     esi, [rdi+8]
0x180005b8e  cmp     esi, edi
0x180005b90  jb      loc_180005D56
0x180005b96  mov     rcx, cs:LdapHeap; hHeap
0x180005b9d  mov     edx, 8; dwFlags
0x180005ba2  mov     r8d, esi; dwBytes
0x180005ba5  call    cs:__imp_HeapAlloc
0x180005bac  nop     dword ptr [rax+rax+00h]
0x180005bb1  mov     r14, rax
0x180005bb4  mov     r8d, 0FFFFFFFFh
0x180005bba  cmp     cs:g_fTracingOn, 0
0x180005bc1  mov     [rsp+88h+Src], r14
0x180005bc6  jnz     loc_180005E73
0x180005bcc  test    r14, r14
0x180005bcf  jz      short loc_180005BEB
0x180005bd1  mov     dword ptr [r14], 6C6C564Ch
0x180005bd8  mov     [r14+4], edi
0x180005bdc  add     r14, 8
0x180005be0  add     cs:?LdapAllocatedHeap@@3KA, edi; ulong LdapAllocatedHeap
0x180005be6  mov     [rsp+88h+Src], r14
0x180005beb  cmp     cs:g_fTracingOn, 0
0x180005bf2  jnz     loc_1800060DA
0x180005bf8  test    r14, r14
0x180005bfb  jz      loc_180006170
0x180005c01  mov     rax, [rbx]
0x180005c04  xor     esi, esi
0x180005c06  mov     [rax+r15*8+0A0h], r14
0x180005c0e  mov     r14d, esi
0x180005c11  mov     rcx, [rsp+88h+vals]; vals
0x180005c19  mov     r15, [rsp+88h+Src]
0x180005c1e  cmp     r14d, r12d
0x180005c21  jnb     loc_180005D17
0x180005c27  mov     eax, r14d
0x180005c2a  lea     rax, ds:0[rax*8]
0x180005c32  mov     [rsp+88h+var_48], rax
0x180005c37  mov     rax, [rax+rcx]
0x180005c3b  mov     [rsp+88h+Src], rax
0x180005c40  test    rax, rax
0x180005c43  jz      short loc_180005C67
0x180005c45  mov     rdx, rax
0x180005c48  mov     ecx, 1
0x180005c4d  nop     dword ptr [rax]
0x180005c50  cmp     word ptr [rdx], 0
0x180005c54  jz      short loc_180005C6C
0x180005c56  lea     eax, [rcx+1]
0x180005c59  cmp     eax, ecx
0x180005c5b  jb      short loc_180005C67
0x180005c5d  mov     ecx, eax
0x180005c5f  add     rdx, 2
0x180005c63  jmp     short loc_180005C50
0x180005c65  xor     esi, esi
0x180005c67  mov     rdi, rsi
0x180005c6a  jmp     short loc_180005CE8
0x180005c6c  mov     esi, ecx
0x180005c6e  add     rsi, rsi
0x180005c71  cmp     rsi, r8
0x180005c74  ja      short loc_180005C65
0x180005c76  lea     ebp, [rsi+8]
0x180005c79  cmp     ebp, esi
0x180005c7b  jb      loc_180005D4C
0x180005c81  mov     rcx, cs:LdapHeap; hHeap
0x180005c88  mov     edx, 8; dwFlags
0x180005c8d  mov     r8d, ebp; dwBytes
0x180005c90  call    cs:__imp_HeapAlloc
0x180005c97  nop     dword ptr [rax+rax+00h]
0x180005c9c  mov     rdi, rax
0x180005c9f  cmp     cs:g_fTracingOn, 0
0x180005ca6  jnz     loc_180005DF7
0x180005cac  test    rdi, rdi
0x180005caf  jz      short loc_180005CC4
  ... truncated ...
```
