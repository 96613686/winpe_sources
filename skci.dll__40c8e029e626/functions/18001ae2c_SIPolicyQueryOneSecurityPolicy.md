# SIPolicyQueryOneSecurityPolicy

- ea: `0x18001ae2c`
- end: `0x18001b0a1`
- name: `SIPolicyQueryOneSecurityPolicy`
- size: `629`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001912c`
- `0x18001919c`
- `0x18001ab6c`
- `0x18001b550`
- `0x18001bfc0`
- `0x18001d95c`
- `0x18001e674`
- `0x1800214ac`
- `0x18004e3cc`

## callees

- `0x18001ae2c`
- `0x18003392c`

## import_xrefs

- `securekernel!bsearch` at `0x18001aee1`
- `securekernel!bsearch` at `0x18001af1e`
- `securekernel!bsearch` at `0x18001af54`
- `securekernel!bsearch` at `0x18001aee1`
- `securekernel!bsearch` at `0x18001af1e`
- `securekernel!bsearch` at `0x18001af54`
- `securekernel!RtlEqualUnicodeString` at `0x18001ae77`
- `securekernel!RtlEqualUnicodeString` at `0x18001ae94`
- `securekernel!RtlEqualUnicodeString` at `0x18001ae77`
- `securekernel!RtlEqualUnicodeString` at `0x18001ae94`

## pseudocode

```c
__int64 __fastcall SIPolicyQueryOneSecurityPolicy(
        __int64 a1,
        const UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _BYTE *a6,
        unsigned int *a7)
{
  int v8; // eax
  __int128 v9; // rdi
  unsigned int v11; // ebx
  size_t v12; // r8
  const void *v13; // rdx
  size_t v14; // r8
  const void *v15; // rdx
  size_t v16; // r8
  const void *v17; // rdx
  int v18; // edx
  __int64 v19; // rdx
  int v20; // eax
  size_t v21; // rdx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  __int128 Key; // [rsp+30h] [rbp-28h] BYREF
  __int128 v27; // [rsp+40h] [rbp-18h]

  v8 = *(_DWORD *)(a1 + 768) & 1;
  *((_QWORD *)&v9 + 1) = a3;
  *(_QWORD *)&v9 = a2;
  Key = 0;
  v27 = 0;
  if ( !(_BYTE)v8
    && RtlEqualUnicodeString(a2, &stru_180036600, 1u)
    && RtlEqualUnicodeString(*((PCUNICODE_STRING *)&v9 + 1), &stru_180036650, 1u) )
  {
    return (unsigned int)-1073741275;
  }
  v12 = *(unsigned int *)(a1 + 688);
  v13 = *(const void **)(a1 + 696);
  Key = v9;
  *(_QWORD *)&v27 = a4;
  *(_QWORD *)&v9 = bsearch(
                     &Key,
                     v13,
                     v12,
                     0x48u,
                     (int (__cdecl *)(const void *, const void *))SIPolicySecureSettingSearchCompare);
  if ( !(_QWORD)v9 )
  {
    v14 = *(unsigned int *)(a1 + 688);
    v15 = *(const void **)(a1 + 696);
    *(_QWORD *)&v27 = a4;
    *((_QWORD *)&Key + 1) = &g_AnyFileWildCardString;
    *(_QWORD *)&v9 = bsearch(
                       &Key,
                       v15,
                       v14,
                       0x48u,
                       (int (__cdecl *)(const void *, const void *))SIPolicySecureSettingSearchCompare);
    if ( !(_QWORD)v9 )
    {
      v16 = *(unsigned int *)(a1 + 688);
      v17 = *(const void **)(a1 + 696);
      *((_QWORD *)&Key + 1) = *((_QWORD *)&v9 + 1);
      *(_QWORD *)&v27 = &g_AnyFileWildCardString;
      *(_QWORD *)&v9 = bsearch(
                         &Key,
                         v17,
                         v16,
                         0x48u,
                         (int (__cdecl *)(const void *, const void *))SIPolicySecureSettingSearchCompare);
      if ( !(_QWORD)v9 )
        return (unsigned int)-1073741275;
    }
  }
  v18 = *(_DWORD *)v9;
  v11 = 0;
  switch ( *(_DWORD *)v9 )
  {
    case 0:
      *a5 = 0;
      if ( !a6 )
      {
        *a7 = 1;
        return v11;
      }
      v24 = *a7;
      *a7 = 1;
      if ( v24 )
      {
        *a6 = *(_BYTE *)(v9 + 56);
        return v11;
      }
      return (unsigned int)-1073741789;
    case 1:
      *a5 = v18;
      if ( !a6 )
      {
        *a7 = 4;
        return v11;
      }
      v23 = *a7;
      *a7 = 4;
      if ( v23 >= 4 )
      {
        *(_DWORD *)a6 = *(_DWORD *)(v9 + 56);
        return v11;
      }
      return (unsigned int)-1073741789;
    case 2:
      *a5 = v18;
      v21 = *(unsigned int *)(v9 + 56);
      if ( !a6 )
      {
        *a7 = v21;
        return v11;
      }
      v22 = *a7;
      *a7 = v21;
      if ( v22 >= (unsigned int)v21 )
      {
        memcpy_0(a6, *(const void **)(v9 + 64), v21);
        return v11;
      }
      return (unsigned int)-1073741789;
    case 3:
      *a5 = v18;
      v19 = *(unsigned __int16 *)(v9 + 56);
      if ( a6 )
      {
        *((_QWORD *)&v9 + 1) = *(unsigned __int16 *)(v9 + 56);
        if ( *a7 >= (unsigned __int64)(v19 + 2) )
        {
          memcpy_0(a6, *(const void **)(v9 + 64), *((size_t *)&v9 + 1));
          *(_WORD *)&a6[2 * (*((_QWORD *)&v9 + 1) >> 1)] = 0;
          v20 = *(unsigned __int16 *)(v9 + 56) + 2;
        }
        else
        {
          v11 = -1073741789;
          v20 = v19 + 2;
        }
        *a7 = v20;
      }
      else
      {
        *a7 = v19 + 2;
      }
      break;
    default:
      return (unsigned int)-1058471933;
  }
  return v11;
}

```

## disassembly

```asm
0x18001ae2c  push    rbp
0x18001ae2e  push    rbx
0x18001ae2f  push    rsi
0x18001ae30  push    rdi
0x18001ae31  push    r12
0x18001ae33  push    r13
0x18001ae35  push    r14
0x18001ae37  push    r15
0x18001ae39  mov     rbp, rsp
0x18001ae3c  sub     rsp, 58h
0x18001ae40  mov     eax, [rcx+300h]
0x18001ae46  xorps   xmm0, xmm0
0x18001ae49  mov     r15d, 1
0x18001ae4f  mov     r14, r9
0x18001ae52  and     eax, r15d
0x18001ae55  mov     rsi, r8
0x18001ae58  mov     rdi, rdx
0x18001ae5b  mov     rbx, rcx
0x18001ae5e  movups  [rbp+Key], xmm0
0x18001ae62  movups  [rbp+var_18], xmm0
0x18001ae66  test    al, al
0x18001ae68  jnz     short loc_18001AEAE
0x18001ae6a  mov     r8b, r15b; CaseInSensitive
0x18001ae6d  lea     rdx, stru_180036600; String2
0x18001ae74  mov     rcx, rdi; String1
0x18001ae77  call    cs:__imp_RtlEqualUnicodeString
0x18001ae7e  nop     dword ptr [rax+rax+00h]
0x18001ae83  test    al, al
0x18001ae85  jz      short loc_18001AEAE
0x18001ae87  mov     r8b, r15b; CaseInSensitive
0x18001ae8a  lea     rdx, stru_180036650; String2
0x18001ae91  mov     rcx, rsi; String1
0x18001ae94  call    cs:__imp_RtlEqualUnicodeString
0x18001ae9b  nop     dword ptr [rax+rax+00h]
0x18001aea0  test    al, al
0x18001aea2  jz      short loc_18001AEAE
0x18001aea4  mov     ebx, 0C0000225h
0x18001aea9  jmp     loc_18001B08D
0x18001aeae  mov     r8d, [rbx+2B0h]; NumOfElements
0x18001aeb5  lea     r13, SIPolicySecureSettingSearchCompare
0x18001aebc  mov     rdx, [rbx+2B8h]; Base
0x18001aec3  lea     rcx, [rbp+Key]; Key
0x18001aec7  mov     r12d, 48h ; 'H'
0x18001aecd  mov     qword ptr [rbp+Key], rdi
0x18001aed1  mov     r9d, r12d; SizeOfElements
0x18001aed4  mov     qword ptr [rbp+Key+8], rsi
0x18001aed8  mov     qword ptr [rbp+var_18], r14
0x18001aedc  mov     [rsp+58h+PtFuncCompare], r13; PtFuncCompare
0x18001aee1  call    cs:__imp_bsearch
0x18001aee8  nop     dword ptr [rax+rax+00h]
0x18001aeed  mov     rdi, rax
0x18001aef0  test    rax, rax
0x18001aef3  jnz     short loc_18001AF6C
0x18001aef5  mov     r8d, [rbx+2B0h]; NumOfElements
0x18001aefc  lea     rcx, [rbp+Key]; Key
0x18001af00  mov     rdx, [rbx+2B8h]; Base
0x18001af07  mov     r9d, r12d; SizeOfElements
0x18001af0a  mov     qword ptr [rbp+var_18], r14
0x18001af0e  lea     r14, g_AnyFileWildCardString
0x18001af15  mov     qword ptr [rbp+Key+8], r14
0x18001af19  mov     [rsp+58h+PtFuncCompare], r13; PtFuncCompare
0x18001af1e  call    cs:__imp_bsearch
0x18001af25  nop     dword ptr [rax+rax+00h]
0x18001af2a  mov     rdi, rax
0x18001af2d  test    rax, rax
0x18001af30  jnz     short loc_18001AF6C
0x18001af32  mov     r8d, [rbx+2B0h]; NumOfElements
0x18001af39  lea     rcx, [rbp+Key]; Key
0x18001af3d  mov     rdx, [rbx+2B8h]; Base
0x18001af44  mov     r9d, r12d; SizeOfElements
0x18001af47  mov     qword ptr [rbp+Key+8], rsi
0x18001af4b  mov     qword ptr [rbp+var_18], r14
0x18001af4f  mov     [rsp+58h+PtFuncCompare], r13; PtFuncCompare
0x18001af54  call    cs:__imp_bsearch
0x18001af5b  nop     dword ptr [rax+rax+00h]
0x18001af60  mov     rdi, rax
0x18001af63  test    rax, rax
0x18001af66  jz      loc_18001AEA4
0x18001af6c  mov     edx, [rdi]
0x18001af6e  xor     ebx, ebx
0x18001af70  mov     ecx, edx
0x18001af72  test    edx, edx
0x18001af74  jz      loc_18001B05F
0x18001af7a  sub     ecx, r15d
0x18001af7d  jz      loc_18001B030
0x18001af83  sub     ecx, r15d
0x18001af86  jz      short loc_18001AFFD
0x18001af88  cmp     ecx, r15d
0x18001af8b  jz      short loc_18001AF97
0x18001af8d  mov     ebx, 0C0E90003h
0x18001af92  jmp     loc_18001B08D
0x18001af97  mov     rax, [rbp+arg_20]
0x18001af9b  mov     r15, [rbp+arg_28]
0x18001af9f  mov     [rax], edx
0x18001afa1  movzx   edx, word ptr [rdi+38h]
0x18001afa5  test    r15, r15
0x18001afa8  jnz     short loc_18001AFB8
0x18001afaa  mov     rax, [rbp+arg_30]
0x18001afae  lea     ecx, [rdx+2]
0x18001afb1  mov     [rax], ecx
0x18001afb3  jmp     loc_18001B08D
0x18001afb8  mov     r14, [rbp+arg_30]
0x18001afbc  lea     rcx, [rdx+2]
0x18001afc0  mov     rsi, rdx
0x18001afc3  mov     eax, [r14]
0x18001afc6  cmp     rax, rcx
0x18001afc9  jnb     short loc_18001AFDB
0x18001afcb  mov     ebx, 0C0000023h
0x18001afd0  lea     eax, [rdx+2]
0x18001afd3  mov     [r14], eax
0x18001afd6  jmp     loc_18001B08D
0x18001afdb  mov     rdx, [rdi+40h]; Src
0x18001afdf  mov     r8, rsi; MaxCount
0x18001afe2  mov     rcx, r15; void *
0x18001afe5  call    memcpy_0
0x18001afea  xor     eax, eax
0x18001afec  shr     rsi, 1
0x18001afef  mov     [r15+rsi*2], ax
0x18001aff4  movzx   eax, word ptr [rdi+38h]
0x18001aff8  add     eax, 2
0x18001affb  jmp     short loc_18001AFD3
0x18001affd  mov     rax, [rbp+arg_20]
0x18001b001  mov     r9, [rbp+arg_28]
0x18001b005  mov     [rax], edx
0x18001b007  mov     edx, [rdi+38h]
0x18001b00a  mov     rax, [rbp+arg_30]
0x18001b00e  test    r9, r9
0x18001b011  jnz     short loc_18001B017
0x18001b013  mov     [rax], edx
0x18001b015  jmp     short loc_18001B08D
0x18001b017  mov     ecx, [rax]
0x18001b019  mov     [rax], edx
0x18001b01b  cmp     ecx, edx
0x18001b01d  jb      short loc_18001B081
0x18001b01f  mov     r8, rdx; MaxCount
0x18001b022  mov     rcx, r9; void *
0x18001b025  mov     rdx, [rdi+40h]; Src
0x18001b029  call    memcpy_0
0x18001b02e  jmp     short loc_18001B08D
0x18001b030  mov     rax, [rbp+arg_20]
0x18001b034  mov     [rax], edx
0x18001b036  mov     rdx, [rbp+arg_28]
0x18001b03a  mov     rax, [rbp+arg_30]
0x18001b03e  test    rdx, rdx
0x18001b041  jnz     short loc_18001B04B
0x18001b043  mov     dword ptr [rax], 4
0x18001b049  jmp     short loc_18001B08D
0x18001b04b  mov     ecx, [rax]
0x18001b04d  mov     dword ptr [rax], 4
0x18001b053  cmp     ecx, 4
0x18001b056  jb      short loc_18001B081
0x18001b058  mov     eax, [rdi+38h]
0x18001b05b  mov     [rdx], eax
0x18001b05d  jmp     short loc_18001B08D
0x18001b05f  mov     rax, [rbp+arg_20]
0x18001b063  mov     [rax], edx
0x18001b065  mov     rdx, [rbp+arg_28]
0x18001b069  mov     rax, [rbp+arg_30]
0x18001b06d  test    rdx, rdx
0x18001b070  jnz     short loc_18001B077
0x18001b072  mov     [rax], r15d
0x18001b075  jmp     short loc_18001B08D
0x18001b077  mov     ecx, [rax]
0x18001b079  mov     [rax], r15d
0x18001b07c  cmp     ecx, r15d
0x18001b07f  jnb     short loc_18001B088
0x18001b081  mov     ebx, 0C0000023h
0x18001b086  jmp     short loc_18001B08D
0x18001b088  mov     cl, [rdi+38h]
0x18001b08b  mov     [rdx], cl
0x18001b08d  mov     eax, ebx
0x18001b08f  add     rsp, 58h
0x18001b093  pop     r15
0x18001b095  pop     r14
0x18001b097  pop     r13
0x18001b099  pop     r12
0x18001b09b  pop     rdi
0x18001b09c  pop     rsi
0x18001b09d  pop     rbx
0x18001b09e  pop     rbp
0x18001b09f  retn
```
