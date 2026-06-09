# CSsdpCacheEntry::FIsSearchMatchHash(char const *,ulong,_GUID,ulong)

- ea: `0x180018fe0`
- end: `0x180019120`
- name: `?FIsSearchMatchHash@CSsdpCacheEntry@@QEAAHPEBDKU_GUID@@K@Z`
- size: `320`
- prototype: `__int64 __fastcall(CSsdpCacheEntry *this, const char *Str1, int, struct _GUID *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180014868`
- `0x180015ac8`

## callees

- `0x180018fe0`
- `0x180019128`
- `0x180035274`
- `0x18003528c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019041`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019000`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019000`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntry::FIsSearchMatchHash(
        CSsdpCacheEntry *this,
        const char *Str1,
        int a3,
        struct _GUID *a4,
        unsigned int a5)
{
  __int64 v9; // rdx
  unsigned int v10; // edi
  const char *v11; // rax
  const char *v12; // rax
  const char *v14; // r9
  int v15; // ecx
  int v16; // r8d
  unsigned int CachedAddressFamily; // eax
  unsigned int i; // edx
  _QWORD *v19; // r8
  __int64 v20; // rax
  const char *v21; // rbp
  int v22; // edx
  int v23; // ecx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  if ( !strcmp_0(Str1, "ssdp:all") )
    goto LABEL_30;
  v9 = *((_QWORD *)this + 11);
  v10 = 0;
  if ( v9 )
  {
    v11 = *(const char **)(v9 + 8);
    if ( v11 && a5 == *((_DWORD *)this + 65) )
    {
      v14 = (const char *)(Str1 - v11);
      do
      {
        v15 = (unsigned __int8)v14[(_QWORD)v11];
        v16 = *(unsigned __int8 *)v11 - v15;
        if ( v16 )
          break;
        ++v11;
      }
      while ( v15 );
      if ( !v16 )
        goto LABEL_30;
    }
    v12 = *(const char **)(v9 + 24);
    if ( v12 )
    {
      v21 = (const char *)(Str1 - v12);
      do
      {
        v22 = (unsigned __int8)v21[(_QWORD)v12];
        v23 = *(unsigned __int8 *)v12 - v22;
        if ( v23 )
          break;
        ++v12;
      }
      while ( v22 );
      if ( !v23 )
      {
LABEL_30:
        if ( !memcmp_0(a4, &GUID_NULL, 0x10u) )
        {
          CachedAddressFamily = CSsdpCacheEntry::GetCachedAddressFamily(this);
          v10 = 0;
LABEL_13:
          LOBYTE(v10) = (CachedAddressFamily & a3) != 0;
        }
        else
        {
          v10 = 0;
          for ( i = 0; i < *((_DWORD *)this + 26); ++i )
          {
            v19 = (_QWORD *)(*((_QWORD *)this + 12) + ((unsigned __int64)i << 6));
            v20 = *(_QWORD *)&a4->Data1 - v19[6];
            if ( *(_QWORD *)&a4->Data1 == v19[6] )
              v20 = *(_QWORD *)a4->Data4 - v19[7];
            if ( !v20 )
            {
              CachedAddressFamily = (*v19 != 0) | 2;
              if ( !v19[1] )
                CachedAddressFamily = *v19 != 0;
              goto LABEL_13;
            }
          }
        }
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  return v10;
}

```

## disassembly

```asm
0x180018fe0  push    rbx
0x180018fe2  push    rbp
0x180018fe3  push    rsi
0x180018fe4  push    rdi
0x180018fe5  push    r14
0x180018fe7  push    r15
0x180018fe9  sub     rsp, 28h
0x180018fed  mov     rsi, rcx
0x180018ff0  mov     r15, r9
0x180018ff3  add     rcx, 0D8h; lpCriticalSection
0x180018ffa  mov     r14d, r8d
0x180018ffd  mov     rbp, rdx
0x180019000  call    cs:__imp_EnterCriticalSection
0x180019006  lea     rdx, Str2; "ssdp:all"
0x18001900d  mov     rcx, rbp; Str1
0x180019010  call    strcmp_0
0x180019015  test    eax, eax
0x180019017  jz      short loc_18001908A
0x180019019  mov     rdx, [rsi+58h]
0x18001901d  xor     edi, edi
0x18001901f  test    rdx, rdx
0x180019022  jz      short loc_18001903A
0x180019024  mov     rax, [rdx+8]
0x180019028  test    rax, rax
0x18001902b  jnz     short loc_180019056
0x18001902d  mov     rax, [rdx+18h]
0x180019031  test    rax, rax
0x180019034  jnz     loc_1800190EB
0x18001903a  lea     rcx, [rsi+0D8h]; lpCriticalSection
0x180019041  call    cs:__imp_LeaveCriticalSection
0x180019047  mov     eax, edi
0x180019049  add     rsp, 28h
0x18001904d  pop     r15
0x18001904f  pop     r14
0x180019051  pop     rdi
0x180019052  pop     rsi
0x180019053  pop     rbp
0x180019054  pop     rbx
0x180019055  retn
0x180019056  mov     ecx, [rsi+104h]
0x18001905c  cmp     [rsp+58h+arg_20], ecx
0x180019063  jnz     short loc_18001902D
0x180019065  mov     r9, rbp
0x180019068  sub     r9, rax
0x18001906b  nop     dword ptr [rax+rax+00h]
0x180019070  movzx   r8d, byte ptr [rax]
0x180019074  movzx   ecx, byte ptr [rax+r9]
0x180019079  sub     r8d, ecx
0x18001907c  jnz     short loc_180019085
0x18001907e  inc     rax
0x180019081  test    ecx, ecx
0x180019083  jnz     short loc_180019070
0x180019085  test    r8d, r8d
0x180019088  jnz     short loc_18001902D
0x18001908a  mov     r8d, 10h; Size
0x180019090  lea     rdx, GUID_NULL; Buf2
0x180019097  mov     rcx, r15; Buf1
0x18001909a  call    memcmp_0
0x18001909f  test    eax, eax
0x1800190a1  jnz     short loc_1800190B9
0x1800190a3  mov     rcx, rsi; this
0x1800190a6  call    ?GetCachedAddressFamily@CSsdpCacheEntry@@AEAAKXZ; CSsdpCacheEntry::GetCachedAddressFamily(void)
0x1800190ab  mov     edi, 0
0x1800190b0  test    r14d, eax
0x1800190b3  setnz   dil
0x1800190b7  jmp     short loc_18001903A
0x1800190b9  xor     edi, edi
0x1800190bb  xor     edx, edx
0x1800190bd  cmp     edx, [rsi+68h]
0x1800190c0  jnb     loc_18001903A
0x1800190c6  mov     rax, [r15]
0x1800190c9  mov     r8d, edx
0x1800190cc  shl     r8, 6
0x1800190d0  add     r8, [rsi+60h]
0x1800190d4  sub     rax, [r8+30h]
0x1800190d8  jnz     short loc_1800190E2
0x1800190da  mov     rax, [r15+8]
0x1800190de  sub     rax, [r8+38h]
0x1800190e2  test    rax, rax
0x1800190e5  jz      short loc_18001910A
0x1800190e7  inc     edx
0x1800190e9  jmp     short loc_1800190BD
0x1800190eb  sub     rbp, rax
0x1800190ee  movzx   ecx, byte ptr [rax]
0x1800190f1  movzx   edx, byte ptr [rax+rbp]
0x1800190f5  sub     ecx, edx
0x1800190f7  jnz     short loc_180019100
0x1800190f9  inc     rax
0x1800190fc  test    edx, edx
0x1800190fe  jnz     short loc_1800190EE
0x180019100  test    ecx, ecx
0x180019102  jnz     loc_18001903A
0x180019108  jmp     short loc_18001908A
0x18001910a  xor     ecx, ecx
0x18001910c  cmp     [r8], rcx
0x18001910f  setnz   cl
0x180019112  mov     eax, ecx
0x180019114  or      eax, 2
0x180019117  cmp     [r8+8], rdi
0x18001911b  cmovz   eax, ecx
0x18001911e  jmp     short loc_1800190B0
```
