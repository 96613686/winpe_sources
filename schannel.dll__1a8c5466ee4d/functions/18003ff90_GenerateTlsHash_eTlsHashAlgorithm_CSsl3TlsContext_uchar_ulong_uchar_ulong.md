# GenerateTlsHash(_eTlsHashAlgorithm,CSsl3TlsContext *,uchar *,ulong,uchar *,ulong *)

- ea: `0x18003ff90`
- end: `0x180040279`
- name: `?GenerateTlsHash@@YAKW4_eTlsHashAlgorithm@@PEAVCSsl3TlsContext@@PEAEK2PEAK@Z`
- size: `745`
- prototype: `unsigned int(enum _eTlsHashAlgorithm, struct CSsl3TlsContext *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003fc90`
- `0x180085dc0`

## callees

- `0x18001db60`
- `0x18003ff90`
- `0x1800597b0`
- `0x1800889d0`
- `0x180091010`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x18004009d`
- `bcrypt!BCryptGetProperty` at `0x18004009d`
- `bcrypt!BCryptCreateHash` at `0x18004014d`
- `bcrypt!BCryptCreateHash` at `0x18004014d`
- `bcrypt!BCryptHashData` at `0x18004016d`
- `bcrypt!BCryptHashData` at `0x180040186`
- `bcrypt!BCryptHashData` at `0x18004016d`
- `bcrypt!BCryptHashData` at `0x180040186`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008fc34`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008fc34`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008fbfb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008fbfb`
- `bcrypt!BCryptFinishHash` at `0x1800401a3`
- `bcrypt!BCryptFinishHash` at `0x1800401a3`
- `bcrypt!BCryptDestroyHash` at `0x1800401b4`
- `bcrypt!BCryptDestroyHash` at `0x1800401b4`

## pseudocode

```c
NTSTATUS __fastcall GenerateTlsHash(
        enum _eTlsHashAlgorithm a1,
        UCHAR *a2,
        unsigned __int8 *a3,
        ULONG a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  unsigned int v7; // eax
  int v10; // ebx
  __int64 v11; // rdx
  BCRYPT_ALG_HANDLE v12; // rax
  __int64 v13; // rcx
  BCRYPT_HANDLE v14; // rsi
  ULONG v15; // r14d
  NTSTATUS Property; // edi
  unsigned __int64 v17; // rdi
  UCHAR *p_hObject; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  NTSTATUS result; // eax
  _DWORD *v25; // rax
  __int64 v26; // [rsp+0h] [rbp-40h] BYREF
  ULONG *pcbResult; // [rsp+20h] [rbp-20h]
  ULONG dwFlags; // [rsp+28h] [rbp-18h]
  BCRYPT_HANDLE hObject; // [rsp+40h] [rbp+0h] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp+8h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp+10h] BYREF
  ULONG v32; // [rsp+58h] [rbp+18h] BYREF

  hObject = 0;
  v7 = 0;
  v10 = g_dwHashInfoTotalCount;
  while ( v7 < g_dwHashInfoTotalCount )
  {
    v11 = g_pHashInfo[v7];
    if ( v11 && *(_DWORD *)(v11 + 20) == a1 )
    {
      v10 = v7;
      break;
    }
    ++v7;
  }
  if ( v10 < 0 || v10 >= g_dwHashInfoTotalCount )
  {
    v10 = 0;
  }
  else
  {
    if ( v10 == 1 )
    {
      v12 = g_hMD5Provider;
      goto LABEL_12;
    }
    if ( v10 == 2 )
    {
      v12 = g_hSHAProvider;
      goto LABEL_12;
    }
  }
  v12 = (BCRYPT_ALG_HANDLE)qword_1800AE610[v10];
LABEL_12:
  hObject = v12;
  if ( v10 < (unsigned int)g_dwHashInfoTotalCount && (_mm_lfence(), (v13 = g_pHashInfo[v10]) != 0) )
  {
    v14 = hObject;
    v15 = *(_DWORD *)(v13 + 8);
    if ( hObject )
      goto LABEL_15;
    if ( *(_QWORD *)v13 )
    {
      result = BCryptOpenAlgorithmProvider(&hObject, *(LPCWSTR *)v13, 0, 0);
      if ( !result )
      {
        v14 = (BCRYPT_HANDLE)_InterlockedCompareExchange64(&qword_1800AE610[v10], (signed __int64)hObject, 0);
        if ( v14 )
        {
          BCryptCloseAlgorithmProvider(hObject, 0);
          hObject = v14;
        }
        else
        {
          v14 = hObject;
        }
LABEL_15:
        dwFlags = 0;
        *(_DWORD *)pbOutput = 0;
        v32 = 0;
        phHash = 0;
        pcbResult = &v32;
        *a6 = v15;
        Property = BCryptGetProperty(v14, L"ObjectLength", pbOutput, 4u, pcbResult, dwFlags);
        if ( Property )
          return Property;
        v17 = *(unsigned int *)pbOutput;
        p_hObject = 0;
        if ( *(_DWORD *)pbOutput )
        {
          if ( *(unsigned int *)pbOutput <= (unsigned __int64)g_ulMaxStackAllocSize )
          {
            v19 = *(unsigned int *)pbOutput + g_ulAdditionalProbeSize + 8;
            if ( v19 >= *(unsigned int *)pbOutput )
            {
              if ( (unsigned int)VerifyStackAvailable(v19) )
              {
                v20 = v17 + 23;
                if ( v17 + 23 <= v17 + 8 )
                  v20 = 0xFFFFFFFFFFFFFF0LL;
                v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
                v22 = alloca(v21);
                v23 = alloca(v21);
                p_hObject = (UCHAR *)&hObject;
                if ( &v26 != (__int64 *)-64LL )
                {
                  LODWORD(hObject) = 1801679955;
                  p_hObject = pbOutput;
                  if ( pbOutput )
                    goto LABEL_24;
                }
              }
            }
          }
        }
        if ( v17 + 8 >= v17 )
        {
          v25 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          if ( !v25 )
            return 14;
          *v25 = 1885431112;
          p_hObject = (UCHAR *)(v25 + 2);
        }
        if ( p_hObject )
        {
LABEL_24:
          Property = BCryptCreateHash(v14, &phHash, p_hObject, *(ULONG *)pbOutput, 0, 0, 0);
          if ( !Property )
          {
            Property = BCryptHashData(phHash, a2 + 1992, 0x40u, 0);
            if ( !Property )
            {
              Property = BCryptHashData(phHash, a3, a4, 0);
              if ( !Property )
                Property = BCryptFinishHash(phHash, a5, v15, 0);
            }
          }
          if ( phHash )
            BCryptDestroyHash(phHash);
          if ( p_hObject )
          {
            if ( *((_DWORD *)p_hObject - 2) == 1885431112 )
              ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_hObject - 8);
          }
          return Property;
        }
        return 14;
      }
    }
    else
    {
      result = 1359;
    }
  }
  else
  {
    result = 1168;
    v15 = 0;
  }
  *a6 = v15;
  return result;
}

```

## disassembly

```asm
0x18003ff90  push    rbp
0x18003ff92  push    rbx
0x18003ff93  push    rsi
0x18003ff94  push    rdi
0x18003ff95  push    r12
0x18003ff97  push    r13
0x18003ff99  push    r14
0x18003ff9b  push    r15
0x18003ff9d  sub     rsp, 78h
0x18003ffa1  lea     rbp, [rsp+40h]
0x18003ffa6  mov     rax, cs:__security_cookie
0x18003ffad  xor     rax, rbp
0x18003ffb0  mov     [rbp+70h+var_48], rax
0x18003ffb4  mov     r10d, cs:g_dwHashInfoTotalCount
0x18003ffbb  mov     r12, r8
0x18003ffbe  mov     rdi, [rbp+70h+arg_28]
0x18003ffc5  xor     r8d, r8d; pszImplementation
0x18003ffc8  mov     [rbp+70h+hObject], r8
0x18003ffcc  mov     eax, r8d
0x18003ffcf  mov     r15d, r9d
0x18003ffd2  mov     r13, rdx
0x18003ffd5  mov     r11d, ecx
0x18003ffd8  mov     ebx, r10d
0x18003ffdb  lea     rdx, __ImageBase
0x18003ffe2  cmp     eax, r10d
0x18003ffe5  jnb     short loc_180040009
0x18003ffe7  mov     ecx, eax
0x18003ffe9  mov     rdx, rva g_pHashInfo[rdx+rcx*8]
0x18003fff1  test    rdx, rdx
0x18003fff4  jz      short loc_18003FFFC
0x18003fff6  cmp     [rdx+14h], r11d
0x18003fffa  jz      short loc_180040000
0x18003fffc  inc     eax
0x18003fffe  jmp     short loc_18003FFDB
0x180040000  mov     ebx, eax
0x180040002  lea     rdx, __ImageBase
0x180040009  test    ebx, ebx
0x18004000b  js      loc_180040224
0x180040011  cmp     ebx, r10d
0x180040014  jge     loc_180040224
0x18004001a  mov     ecx, ebx
0x18004001c  sub     ecx, 1
0x18004001f  jz      loc_1800401EF
0x180040025  cmp     ecx, 1
0x180040028  jz      loc_180040218
0x18004002e  mov     eax, ebx
0x180040030  mov     rax, rva qword_1800AE610[rdx+rax*8]
0x180040038  mov     [rbp+70h+hObject], rax
0x18004003c  cmp     ebx, r10d
0x18004003f  jnb     loc_1800401FB
0x180040045  lfence
0x180040048  mov     eax, ebx
0x18004004a  mov     rcx, rva g_pHashInfo[rdx+rax*8]
0x180040052  test    rcx, rcx
0x180040055  jz      loc_1800401FB
0x18004005b  mov     rsi, [rbp+70h+hObject]
0x18004005f  mov     r14d, [rcx+8]
0x180040063  test    rsi, rsi
0x180040066  jz      loc_18004022C
0x18004006c  mov     [rsp+0B0h+dwFlags], r8d; dwFlags
0x180040071  lea     rax, [rbp+70h+var_58]
0x180040075  mov     dword ptr [rbp+70h+pbOutput], r8d
0x180040079  lea     rdx, pszProperty; "ObjectLength"
0x180040080  mov     [rbp+70h+var_58], r8d
0x180040084  mov     r9d, 4; cbOutput
0x18004008a  mov     [rbp+70h+phHash], r8
0x18004008e  mov     rcx, rsi; hObject
0x180040091  lea     r8, [rbp+70h+pbOutput]; pbOutput
0x180040095  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18004009a  mov     [rdi], r14d
0x18004009d  call    cs:__imp_BCryptGetProperty
0x1800400a3  mov     edi, eax
0x1800400a5  test    eax, eax
0x1800400a7  jnz     loc_1800401D0
0x1800400ad  mov     edi, dword ptr [rbp+70h+pbOutput]
0x1800400b0  xor     ebx, ebx
0x1800400b2  test    rdi, rdi
0x1800400b5  jz      loc_18004023F
0x1800400bb  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800400c2  ja      loc_18004023F
0x1800400c8  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800400cf  add     rcx, 8
0x1800400d3  add     rcx, rdi
0x1800400d6  cmp     rcx, rdi
0x1800400d9  jb      loc_18004023F
0x1800400df  call    VerifyStackAvailable
0x1800400e4  test    eax, eax
0x1800400e6  jz      loc_18004023F
0x1800400ec  lea     rax, [rdi+8]
0x1800400f0  lea     rcx, [rax+0Fh]
0x1800400f4  cmp     rcx, rax
0x1800400f7  ja      short loc_180040103
0x1800400f9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180040103  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180040107  mov     rax, rcx
0x18004010a  call    _alloca_probe
0x18004010f  sub     rsp, rcx
0x180040112  lea     rbx, [rsp+0B0h+hObject]
0x180040117  test    rbx, rbx
0x18004011a  jz      loc_18004023F
0x180040120  mov     dword ptr [rbx], 6B637453h
0x180040126  add     rbx, 8
0x18004012a  jz      loc_18004023F
0x180040130  mov     r9d, dword ptr [rbp+70h+pbOutput]; cbHashObject
0x180040134  lea     rdx, [rbp+70h+phHash]; phHash
0x180040138  xor     eax, eax
0x18004013a  mov     r8, rbx; pbHashObject
0x18004013d  mov     [rsp+0B0h+var_80], eax; dwFlags
0x180040141  mov     rcx, rsi; hAlgorithm
0x180040144  mov     [rsp+0B0h+dwFlags], eax; cbSecret
0x180040148  mov     [rsp+0B0h+pcbResult], rax; pbSecret
0x18004014d  call    cs:__imp_BCryptCreateHash
0x180040153  mov     edi, eax
0x180040155  test    eax, eax
0x180040157  jnz     short loc_1800401AB
0x180040159  mov     rcx, [rbp+70h+phHash]; hHash
0x18004015d  lea     rdx, [r13+7C8h]; pbInput
0x180040164  xor     r9d, r9d; dwFlags
0x180040167  mov     r8d, 40h ; '@'; cbInput
0x18004016d  call    cs:__imp_BCryptHashData
0x180040173  mov     edi, eax
0x180040175  test    eax, eax
0x180040177  jnz     short loc_1800401AB
0x180040179  mov     rcx, [rbp+70h+phHash]; hHash
0x18004017d  xor     r9d, r9d; dwFlags
0x180040180  mov     r8d, r15d; cbInput
0x180040183  mov     rdx, r12; pbInput
0x180040186  call    cs:__imp_BCryptHashData
0x18004018c  mov     edi, eax
0x18004018e  test    eax, eax
0x180040190  jnz     short loc_1800401AB
0x180040192  mov     rdx, [rbp+70h+arg_20]; pbOutput
0x180040199  xor     r9d, r9d; dwFlags
0x18004019c  mov     rcx, [rbp+70h+phHash]; hHash
0x1800401a0  mov     r8d, r14d; cbOutput
0x1800401a3  call    cs:__imp_BCryptFinishHash
0x1800401a9  mov     edi, eax
0x1800401ab  mov     rcx, [rbp+70h+phHash]; hHash
0x1800401af  test    rcx, rcx
0x1800401b2  jz      short loc_1800401BA
0x1800401b4  call    cs:__imp_BCryptDestroyHash
0x1800401ba  test    rbx, rbx
0x1800401bd  jz      short loc_1800401D0
0x1800401bf  cmp     dword ptr [rbx-8], 70616548h
0x1800401c6  lea     rcx, [rbx-8]
0x1800401ca  jz      loc_180040268
0x1800401d0  mov     eax, edi
0x1800401d2  mov     rcx, [rbp+70h+var_48]
0x1800401d6  xor     rcx, rbp; StackCookie
0x1800401d9  call    __security_check_cookie
0x1800401de  lea     rsp, [rbp+38h]
0x1800401e2  pop     r15
0x1800401e4  pop     r14
0x1800401e6  pop     r13
0x1800401e8  pop     r12
0x1800401ea  pop     rdi
0x1800401eb  pop     rsi
0x1800401ec  pop     rbx
0x1800401ed  pop     rbp
0x1800401ee  retn
0x1800401ef  mov     rax, cs:?g_hMD5Provider@@3PEAXEA; void * g_hMD5Provider
0x1800401f6  jmp     loc_180040038
0x1800401fb  mov     eax, 490h
0x180040200  mov     r14d, r8d
0x180040203  mov     [rdi], r14d
0x180040206  jmp     short loc_1800401D2
0x180040208  test    rbx, rbx
0x18004020b  jnz     loc_180040130
0x180040211  mov     edi, 0Eh
0x180040216  jmp     short loc_1800401D0
0x180040218  mov     rax, cs:?g_hSHAProvider@@3PEAXEA; void * g_hSHAProvider
0x18004021f  jmp     loc_180040038
0x180040224  mov     ebx, r8d
0x180040227  jmp     loc_18004002E
0x18004022c  mov     rdx, [rcx]; pszAlgId
0x18004022f  test    rdx, rdx
0x180040232  jnz     loc_18008FBF4
0x180040238  mov     eax, 54Fh
0x18004023d  jmp     short loc_180040203
0x18004023f  lea     rcx, [rdi+8]
0x180040243  cmp     rcx, rdi
0x180040246  jb      short loc_180040208
0x180040248  mov     rax, cs:g_pfnAllocate
0x18004024f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040254  mov     rbx, rax
0x180040257  test    rax, rax
0x18004025a  jz      short loc_180040211
0x18004025c  mov     dword ptr [rax], 70616548h
0x180040262  add     rbx, 8
0x180040266  jmp     short loc_180040208
0x180040268  mov     rax, cs:g_pfnFree
0x18004026f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040274  jmp     loc_1800401D0
0x18008fbf4  xor     r9d, r9d; dwFlags
0x18008fbf7  lea     rcx, [rbp+70h+hObject]; phAlgorithm
0x18008fbfb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008fc01  test    eax, eax
0x18008fc03  jnz     loc_180040203
0x18008fc09  movsxd  rax, ebx
0x18008fc0c  lea     rcx, __ImageBase
0x18008fc13  lea     rdx, rva qword_1800AE610[rcx]
0x18008fc1a  mov     rcx, [rbp+70h+hObject]
0x18008fc1e  lea     rdx, [rdx+rax*8]
0x18008fc22  xor     eax, eax
0x18008fc24  lock cmpxchg [rdx], rcx
0x18008fc29  mov     rsi, rax
0x18008fc2c  jz      short loc_18008FC40
0x18008fc2e  mov     rcx, [rbp+70h+hObject]; hAlgorithm
0x18008fc32  xor     edx, edx; dwFlags
0x18008fc34  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18008fc3a  mov     [rbp+70h+hObject], rsi
0x18008fc3e  jmp     short loc_18008FC44
0x18008fc40  mov     rsi, [rbp+70h+hObject]
0x18008fc44  xor     r8d, r8d
0x18008fc47  jmp     loc_18004006C
```
