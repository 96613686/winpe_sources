# RetrieveFromCache(ldap_connection *,ushort *,uchar,int *,ushort * * *)

- ea: `0x18001de00`
- end: `0x18001e2b3`
- name: `?RetrieveFromCache@@YAEPEAUldap_connection@@PEAGEPEAHPEAPEAPEAG@Z`
- size: `1203`
- prototype: `unsigned __int8(struct ldap_connection *, unsigned __int16 *, unsigned __int8, int *, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800112b0`

## callees

- `0x1800037a8`
- `0x180006510`
- `0x18000b440`
- `0x18001ce90`
- `0x18001de00`
- `0x18001e7b0`
- `0x18001ffa0`
- `0x180032bd8`
- `0x18004c76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001de49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001de49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e203`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e203`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e03f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001e03f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ded9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e15b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001ded9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e15b`

## string_xrefs

- `0x18001e1b6`: `RetrieveFromCache: CachePage missing in late stage\n`
- `0x18001e240`: `Found cache match for attribute '%S'\n`

## pseudocode

```c
unsigned __int8 __fastcall RetrieveFromCache(
        struct ldap_connection *a1,
        const CHAR *a2,
        char a3,
        int *a4,
        unsigned __int16 ***a5)
{
  unsigned __int8 result; // al
  __int64 v10; // rbx
  struct _CACHEHOLDER * near **v11; // r14
  unsigned __int16 **v12; // rsi
  unsigned int v13; // ebx
  int v14; // ebp
  const WCHAR *lpString2; // rdx
  bool v16; // zf
  int v17; // r15d
  __int64 v18; // rbx
  __int64 v19; // rcx
  int v20; // r12d
  __int64 v21; // rcx
  __int64 v22; // rbx
  const void *v23; // r13
  _WORD *v24; // rdx
  unsigned int v25; // ecx
  size_t v26; // rbp
  unsigned int v27; // r14d
  _DWORD *v28; // rdi
  int i; // esi
  struct _CACHEHOLDER * near **v30; // r14
  const WCHAR *v31; // r8
  const WCHAR *v32; // rcx
  bool v33; // zf
  __int64 v34; // rdx
  unsigned int v35; // eax
  __int64 v36; // [rsp+30h] [rbp-38h]

  result = (unsigned __int8)a5;
  if ( !a5 )
    return result;
  *a5 = 0;
  EnterCriticalSection(&CacheLock);
  if ( *a4 == -1 )
  {
    for ( i = 0; i < 5; ++i )
    {
      v30 = &(&CacheArray)[i];
      if ( *v30 )
      {
        v31 = (const WCHAR *)*((_QWORD *)a1 + 52);
        v32 = (const WCHAR *)(*v30)[1];
        if ( v31 )
        {
          if ( !v32 )
            continue;
          v33 = CompareStringW(0x400u, 1u, v31, -1, v32, -1) == 2;
        }
        else
        {
          v33 = v32 == 0;
        }
        if ( v33 && *((_WORD *)*v30 + 8) == *((_WORD *)a1 + 253) )
        {
          *a4 = i;
          break;
        }
      }
    }
  }
  v10 = *a4;
  if ( (_DWORD)v10 == -1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x10000000) != 0 )
      LDAPClientTraceEvent(0x10000000, "RetrieveFromCache: CachePage missing in late stage\n");
    v34 = 82;
    goto LABEL_64;
  }
  v11 = &(&CacheArray)[v10];
  (*v11)[4] = (struct _CACHEHOLDER *)LdapGetTickCount();
  if ( !a3 )
  {
    v35 = ToUnicodeWithAlloc(a2, 1);
    if ( v35 )
    {
      v34 = v35;
LABEL_64:
      SetConnectionError(a1, v34);
      LeaveCriticalSection(&CacheLock);
      return 0;
    }
  }
  v12 = 0;
  v13 = 0;
  v14 = -1;
  do
  {
    lpString2 = (const WCHAR *)(*v11)[(int)v13 + 5];
    if ( a2 )
    {
      if ( !lpString2 )
        goto LABEL_10;
      v16 = CompareStringW(0x400u, 1u, (PCNZWCH)a2, -1, lpString2, -1) == 2;
    }
    else
    {
      v16 = lpString2 == 0;
    }
    if ( v16 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "Found cache match for attribute '%S'\n", (const wchar_t *)a2);
      v14 = v13;
    }
LABEL_10:
    ++v13;
  }
  while ( v13 < 0xF );
  if ( !a3 )
    ldapFree(a2, 1768838476);
  if ( v14 == -1 )
    goto LABEL_19;
  v17 = 0;
  v18 = 8LL * v14 + 160;
  v19 = *(__int64 *)((char *)*v11 + v18);
  if ( v19 )
  {
    while ( *(_QWORD *)(v19 + 8LL * v17) )
      ++v17;
  }
  v12 = (unsigned __int16 **)ldapMalloc((unsigned int)(8 * v17 + 8), 1819039308);
  if ( v12 )
  {
    v20 = 0;
    v21 = *(__int64 *)((char *)*v11 + v18);
    v36 = v21;
    while ( v20 < v17 )
    {
      v22 = 8LL * v20;
      v23 = *(const void **)(v22 + v21);
      if ( !v23 )
        goto LABEL_20;
      v24 = *(_WORD **)(v22 + v21);
      v25 = 1;
      while ( *v24 )
      {
        if ( v25 + 1 < v25 )
          goto LABEL_20;
        ++v25;
        ++v24;
      }
      v26 = 2LL * v25;
      if ( v26 > 0xFFFFFFFF )
        goto LABEL_20;
      v27 = v26 + 8;
      if ( (int)v26 + 8 < (unsigned int)v26 )
      {
        v28 = 0;
        v27 = -1;
      }
      else
      {
        v28 = HeapAlloc(LdapHeap, 8u, v27);
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapMalloc allocated 0x%x bytes at address 0x%x of tag 0x%x.\n",
          v27,
          (_DWORD)v28,
          1818318412);
      if ( v28 )
      {
        *v28 = 1818318412;
        v28[1] = v26;
        v28 += 2;
        LdapAllocatedHeap += v26;
      }
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 8) != 0 )
        LDAPClientPrint(
          8,
          "ldapMalloc 0x%08x bytes at address 0x%x of tag %x, tot=%d.\n",
          v26,
          (_DWORD)v28,
          1818318412,
          LdapAllocatedHeap);
      if ( !v28 )
      {
LABEL_20:
        v12[v20] = 0;
        goto LABEL_21;
      }
      memcpy_0(v28, v23, v26);
      v21 = v36;
      ++v20;
      v12[(unsigned __int64)v22 / 8] = (unsigned __int16 *)v28;
    }
LABEL_19:
    LeaveCriticalSection(&CacheLock);
    *a5 = v12;
    return 1;
  }
  else
  {
    SetConnectionError(a1, 90);
LABEL_21:
    LeaveCriticalSection(&CacheLock);
    return 0;
  }
}

```

## disassembly

```asm
0x18001de00  push    rbx
0x18001de02  push    rdi
0x18001de03  push    r13
0x18001de05  push    r15
0x18001de07  sub     rsp, 48h
0x18001de0b  mov     rax, [rsp+68h+arg_20]
0x18001de13  mov     rbx, r9
0x18001de16  movzx   r15d, r8b
0x18001de1a  mov     rdi, rdx
0x18001de1d  mov     r13, rcx
0x18001de20  test    rax, rax
0x18001de23  jz      loc_18001E17A
0x18001de29  mov     [rsp+68h+arg_8], rsi
0x18001de2e  lea     rcx, CacheLock; lpCriticalSection
0x18001de35  mov     [rsp+68h+arg_10], r12
0x18001de3d  mov     [rsp+68h+var_28], r14
0x18001de42  mov     qword ptr [rax], 0
0x18001de49  call    cs:__imp_EnterCriticalSection
0x18001de50  nop     dword ptr [rax+rax+00h]
0x18001de55  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18001de58  lea     r12, ?CacheArray@@3PAPEAU_CACHEHOLDER@@A; _CACHEHOLDER * near * CacheArray
0x18001de5f  jz      loc_18001E109
0x18001de65  movsxd  rbx, dword ptr [rbx]
0x18001de68  cmp     ebx, 0FFFFFFFFh
0x18001de6b  jz      loc_18001E197
0x18001de71  call    LdapGetTickCount
0x18001de76  mov     rcx, [r12+rbx*8]
0x18001de7a  lea     r14, [r12+rbx*8]
0x18001de7e  mov     [rsp+68h+var_38], rdi
0x18001de83  mov     [rcx+20h], rax
0x18001de87  test    r15b, r15b
0x18001de8a  jz      loc_18001E1CE
0x18001de90  xor     esi, esi
0x18001de92  mov     [rsp+68h+arg_0], rbp
0x18001de97  xor     ebx, ebx
0x18001de99  mov     ebp, 0FFFFFFFFh
0x18001de9e  xchg    ax, ax
0x18001dea0  mov     rax, [r14]
0x18001dea3  movsxd  rcx, ebx
0x18001dea6  mov     rdx, [rax+rcx*8+28h]
0x18001deab  test    rdi, rdi
0x18001deae  jz      loc_18001E0C4
0x18001deb4  test    rdx, rdx
0x18001deb7  jz      short loc_18001DEEF
0x18001deb9  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001dec1  mov     r9d, 0FFFFFFFFh; cchCount1
0x18001dec7  mov     [rsp+68h+lpString2], rdx; lpString2
0x18001decc  mov     r8, rdi; lpString1
0x18001decf  mov     edx, 1; dwCmpFlags
0x18001ded4  mov     ecx, 400h; Locale
0x18001ded9  call    cs:__imp_CompareStringW
0x18001dee0  nop     dword ptr [rax+rax+00h]
0x18001dee5  cmp     eax, 2
0x18001dee8  setz    al
0x18001deeb  test    al, al
0x18001deed  jnz     short loc_18001DF2E
0x18001deef  inc     ebx
0x18001def1  cmp     ebx, 0Fh
0x18001def4  jb      short loc_18001DEA0
0x18001def6  test    r15b, r15b
0x18001def9  jz      loc_18001E256
0x18001deff  cmp     ebp, 0FFFFFFFFh
0x18001df02  jz      short loc_18001DF3E
0x18001df04  movsxd  rax, ebp
0x18001df07  xor     r15d, r15d
0x18001df0a  lea     rbx, ds:0A0h[rax*8]
0x18001df12  mov     rax, [r14]
0x18001df15  mov     rcx, [rbx+rax]
0x18001df19  test    rcx, rcx
0x18001df1c  jz      short loc_18001DF9C
0x18001df1e  xchg    ax, ax
0x18001df20  movsxd  rax, r15d
0x18001df23  cmp     [rcx+rax*8], rsi
0x18001df27  jz      short loc_18001DF9C
0x18001df29  inc     r15d
0x18001df2c  jmp     short loc_18001DF20
0x18001df2e  cmp     cs:g_fTracingOn, esi
0x18001df34  jnz     loc_18001E220
0x18001df3a  mov     ebp, ebx
0x18001df3c  jmp     short loc_18001DEEF
0x18001df3e  lea     rcx, CacheLock; lpCriticalSection
0x18001df45  call    cs:__imp_LeaveCriticalSection
0x18001df4c  nop     dword ptr [rax+rax+00h]
0x18001df51  mov     rax, [rsp+68h+arg_20]
0x18001df59  mov     [rax], rsi
0x18001df5c  mov     al, 1
0x18001df5e  jmp     short loc_18001DF79
0x18001df60  mov     [rsi+rbx], r8
0x18001df64  lea     rcx, CacheLock; lpCriticalSection
0x18001df6b  call    cs:__imp_LeaveCriticalSection
0x18001df72  nop     dword ptr [rax+rax+00h]
0x18001df77  xor     al, al
0x18001df79  mov     rbp, [rsp+68h+arg_0]
0x18001df7e  mov     rsi, [rsp+68h+arg_8]
0x18001df83  mov     r12, [rsp+68h+arg_10]
0x18001df8b  mov     r14, [rsp+68h+var_28]
0x18001df90  add     rsp, 48h
0x18001df94  pop     r15
0x18001df96  pop     r13
0x18001df98  pop     rdi
0x18001df99  pop     rbx
0x18001df9a  retn
0x18001df9c  lea     ecx, ds:8[r15*8]
0x18001dfa4  mov     edx, 6C6C564Ch
0x18001dfa9  call    ldapMalloc
0x18001dfae  mov     rsi, rax
0x18001dfb1  test    rax, rax
0x18001dfb4  jz      loc_18001E0B2
0x18001dfba  mov     rax, [r14]
0x18001dfbd  xor     r8d, r8d
0x18001dfc0  mov     r12d, r8d
0x18001dfc3  mov     rcx, [rbx+rax]
0x18001dfc7  mov     [rsp+68h+var_38], rcx
0x18001dfcc  mov     r9d, 0FFFFFFFFh
0x18001dfd2  cmp     r12d, r15d
0x18001dfd5  jge     loc_18001DF3E
0x18001dfdb  movsxd  rax, r12d
0x18001dfde  lea     rbx, ds:0[rax*8]
0x18001dfe6  mov     r13, [rbx+rcx]
0x18001dfea  test    r13, r13
0x18001dfed  jz      loc_18001DF60
0x18001dff3  mov     rdx, r13
0x18001dff6  mov     ecx, 1
0x18001dffb  nop     dword ptr [rax+rax+00h]
0x18001e000  cmp     word ptr [rdx], 0
0x18001e004  jz      short loc_18001E019
0x18001e006  lea     eax, [rcx+1]
0x18001e009  cmp     eax, ecx
0x18001e00b  jb      loc_18001DF60
0x18001e011  mov     ecx, eax
0x18001e013  add     rdx, 2
0x18001e017  jmp     short loc_18001E000
0x18001e019  mov     ebp, ecx
0x18001e01b  add     rbp, rbp
0x18001e01e  cmp     rbp, r9
0x18001e021  ja      loc_18001DF60
0x18001e027  lea     r14d, [rbp+8]
0x18001e02b  cmp     r14d, ebp
0x18001e02e  jb      short loc_18001E0AA
0x18001e030  mov     rcx, cs:LdapHeap; hHeap
0x18001e037  mov     edx, 8; dwFlags
0x18001e03c  mov     r8d, r14d; dwBytes
0x18001e03f  call    cs:__imp_HeapAlloc
0x18001e046  nop     dword ptr [rax+rax+00h]
0x18001e04b  mov     rdi, rax
0x18001e04e  xor     r8d, r8d
0x18001e051  cmp     cs:g_fTracingOn, 0
0x18001e058  jnz     short loc_18001E0CC
0x18001e05a  test    rdi, rdi
0x18001e05d  jz      short loc_18001E072
0x18001e05f  mov     dword ptr [rdi], 6C61564Ch
0x18001e065  mov     [rdi+4], ebp
0x18001e068  add     rdi, 8
0x18001e06c  add     cs:?LdapAllocatedHeap@@3KA, ebp; ulong LdapAllocatedHeap
0x18001e072  cmp     cs:g_fTracingOn, 0
0x18001e079  jnz     loc_18001E268
0x18001e07f  test    rdi, rdi
0x18001e082  jz      loc_18001DF60
0x18001e088  mov     r8, rbp; Size
0x18001e08b  mov     rdx, r13; Src
0x18001e08e  mov     rcx, rdi; void *
0x18001e091  call    memcpy_0
0x18001e096  mov     rcx, [rsp+68h+var_38]
0x18001e09b  inc     r12d
0x18001e09e  xor     r8d, r8d
0x18001e0a1  mov     [rsi+rbx], rdi
0x18001e0a5  jmp     loc_18001DFCC
0x18001e0aa  mov     rdi, r8
0x18001e0ad  mov     r14d, r9d
0x18001e0b0  jmp     short loc_18001E051
0x18001e0b2  mov     edx, 5Ah ; 'Z'
0x18001e0b7  mov     rcx, r13
0x18001e0ba  call    SetConnectionError
0x18001e0bf  jmp     loc_18001DF64
0x18001e0c4  test    rdx, rdx
0x18001e0c7  jmp     loc_18001DEE8
0x18001e0cc  cmp     cs:g_fProviderEnabled, 0
0x18001e0d3  jz      short loc_18001E05A
0x18001e0d5  test    byte ptr cs:g_ulTraceFlags, 8
0x18001e0dc  jz      loc_18001E05A
0x18001e0e2  mov     r9, rdi
0x18001e0e5  mov     dword ptr [rsp+68h+lpString2], 6C61564Ch
0x18001e0ed  mov     r8d, r14d
0x18001e0f0  lea     rdx, aLdapmallocAllo; "ldapMalloc allocated 0x%x bytes at addr"...
0x18001e0f7  mov     ecx, 8
0x18001e0fc  call    LDAPClientPrint
0x18001e101  xor     r8d, r8d
0x18001e104  jmp     loc_18001E05A
0x18001e109  xor     esi, esi
0x18001e10b  nop     dword ptr [rax+rax+00h]
0x18001e110  cmp     esi, 5
0x18001e113  jge     loc_18001DE65
0x18001e119  movsxd  rax, esi
0x18001e11c  lea     r14, [r12+rax*8]
0x18001e120  mov     rax, [r12+rax*8]
0x18001e124  test    rax, rax
0x18001e127  jz      short loc_18001E171
0x18001e129  mov     r8, [r13+1A0h]; lpString1
0x18001e130  mov     rcx, [rax+8]
0x18001e134  test    r8, r8
0x18001e137  jz      short loc_18001E175
0x18001e139  test    rcx, rcx
0x18001e13c  jz      short loc_18001E171
0x18001e13e  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001e146  mov     edx, 1; dwCmpFlags
0x18001e14b  mov     [rsp+68h+lpString2], rcx; lpString2
0x18001e150  mov     r9d, 0FFFFFFFFh; cchCount1
0x18001e156  mov     ecx, 400h; Locale
0x18001e15b  call    cs:__imp_CompareStringW
0x18001e162  nop     dword ptr [rax+rax+00h]
0x18001e167  cmp     eax, 2
0x18001e16a  setz    al
0x18001e16d  test    al, al
0x18001e16f  jnz     short loc_18001E17F
0x18001e171  inc     esi
0x18001e173  jmp     short loc_18001E110
0x18001e175  test    rcx, rcx
0x18001e178  jmp     short loc_18001E16A
0x18001e17a  jmp     loc_18001DF90
0x18001e17f  mov     rcx, [r14]
0x18001e182  movzx   eax, word ptr [r13+1FAh]
0x18001e18a  cmp     [rcx+10h], ax
0x18001e18e  jnz     short loc_18001E171
0x18001e190  mov     [rbx], esi
0x18001e192  jmp     loc_18001DE65
0x18001e197  cmp     cs:g_fTracingOn, 0
0x18001e19e  jz      short loc_18001E1C7
0x18001e1a0  cmp     cs:g_fProviderEnabled, 0
0x18001e1a7  jz      short loc_18001E1C7
0x18001e1a9  test    cs:g_ulTraceFlags, 10000000h
0x18001e1b4  jz      short loc_18001E1C7
0x18001e1b6  lea     rdx, aRetrievefromca; "RetrieveFromCache: CachePage missing in"...
0x18001e1bd  mov     ecx, 10000000h
0x18001e1c2  call    LDAPClientTraceEvent
0x18001e1c7  mov     edx, 52h ; 'R'
0x18001e1cc  jmp     short loc_18001E1F4
0x18001e1ce  mov     r9d, 696E554Ch
0x18001e1d4  mov     dword ptr [rsp+68h+lpString2], 1; int
0x18001e1dc  lea     r8, [rsp+68h+var_38]
0x18001e1e1  mov     edx, 0FFFFFFFFh
0x18001e1e6  mov     rcx, rdi; lpMultiByteStr
0x18001e1e9  call    ToUnicodeWithAlloc
0x18001e1ee  test    eax, eax
0x18001e1f0  jz      short loc_18001E216
0x18001e1f2  mov     edx, eax
0x18001e1f4  mov     rcx, r13
0x18001e1f7  call    SetConnectionError
0x18001e1fc  lea     rcx, CacheLock; lpCriticalSection
0x18001e203  call    cs:__imp_LeaveCriticalSection
0x18001e20a  nop     dword ptr [rax+rax+00h]
0x18001e20f  xor     al, al
0x18001e211  jmp     loc_18001DF7E
0x18001e216  mov     rdi, [rsp+68h+var_38]
0x18001e21b  jmp     loc_18001DE90
0x18001e220  cmp     cs:g_fProviderEnabled, esi
0x18001e226  jz      loc_18001DF3A
0x18001e22c  test    cs:g_ulTraceFlags, 400000h
0x18001e237  jz      loc_18001DF3A
0x18001e23d  mov     r8, rdi
0x18001e240  lea     rdx, aFoundCacheMatc; "Found cache match for attribute '%S'\n"
0x18001e247  mov     ecx, 400000h
0x18001e24c  call    LDAPClientPrint
0x18001e251  jmp     loc_18001DF3A
0x18001e256  mov     edx, 696E554Ch
0x18001e25b  mov     rcx, rdi
0x18001e25e  call    ldapFree
0x18001e263  jmp     loc_18001DEFF
0x18001e268  cmp     cs:g_fProviderEnabled, 0
0x18001e26f  jz      loc_18001E07F
0x18001e275  test    byte ptr cs:g_ulTraceFlags, 8
0x18001e27c  jz      loc_18001E07F
0x18001e282  mov     eax, cs:?LdapAllocatedHeap@@3KA; ulong LdapAllocatedHeap
0x18001e288  lea     rdx, aLdapmalloc0x08; "ldapMalloc 0x%08x bytes at address 0x%x"...
0x18001e28f  mov     [rsp+68h+cchCount2], eax
0x18001e293  mov     r9, rdi
0x18001e296  mov     r8d, ebp
0x18001e299  mov     dword ptr [rsp+68h+lpString2], 6C61564Ch
0x18001e2a1  mov     ecx, 8
0x18001e2a6  call    LDAPClientPrint
0x18001e2ab  xor     r8d, r8d
0x18001e2ae  jmp     loc_18001E07F
```
