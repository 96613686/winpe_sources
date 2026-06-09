# SampHandleDuplicateAccountNamesHelper(ulong,ulong,_SAMP_OBJECT_TYPE,ulong)

- ea: `0x180096d88`
- end: `0x1800973ba`
- name: `?SampHandleDuplicateAccountNamesHelper@@YAJKKW4_SAMP_OBJECT_TYPE@@K@Z`
- size: `1586`
- prototype: `int __high(unsigned int, unsigned int, enum _SAMP_OBJECT_TYPE, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800968b4`

## callees

- `0x180004fa0`
- `0x1800066f0`
- `0x180011810`
- `0x1800198a0`
- `0x1800213d0`
- `0x180022440`
- `0x1800270e0`
- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x18004e2d4`
- `0x180065b60`
- `0x1800792ac`
- `0x180096d88`
- `0x1800973c0`
- `0x1800974d4`
- `0x180097b14`
- `0x180097ff8`
- `0x1800993a4`
- `0x1800bb788`
- `0x1800bb794`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort_s` at `0x1800971ed`
- `api-ms-win-crt-private-l1-1-0!_o_qsort_s` at `0x1800971ed`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800970b6`
- `ntdll!RtlCompareUnicodeStrings` at `0x1800970b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009703a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009703a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009712a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009713e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009712a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009713e`

## pseudocode

```c
__int64 __fastcall SampHandleDuplicateAccountNamesHelper(int a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rcx
  _QWORD *v6; // r13
  int v7; // eax
  int v8; // ebx
  PUNICODE_STRING v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  PUNICODE_STRING v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  PUNICODE_STRING v18; // rcx
  __int64 v19; // rdx
  int AccountContext; // eax
  PVOID **v21; // r15
  int UnicodeStringAttribute; // eax
  _QWORD *v23; // rax
  unsigned int v24; // esi
  int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rcx
  HLOCAL *v28; // rax
  __int64 i; // rsi
  SIZE_T *v31; // rcx
  unsigned __int16 *v32; // r12
  unsigned int v33; // esi
  __int64 v34; // rcx
  int v35; // eax
  int v36; // edx
  int v37; // r8d
  unsigned int v38; // r12d
  PUNICODE_STRING v39; // r10
  SIZE_T v40; // r15
  int v41; // eax
  void *Context; // [rsp+20h] [rbp-60h]
  int Contexta; // [rsp+20h] [rbp-60h]
  void *Src; // [rsp+40h] [rbp-40h] BYREF
  PVOID HandleId; // [rsp+48h] [rbp-38h] BYREF
  SIZE_T uBytes; // [rsp+50h] [rbp-30h] BYREF
  __int128 v47; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING v48; // [rsp+68h] [rbp-18h] BYREF
  int v50; // [rsp+C8h] [rbp+48h]
  unsigned int v51; // [rsp+D0h] [rbp+50h] BYREF

  v51 = 0;
  Src = 0;
  v48 = 0;
  v5 = *((_QWORD *)SampDefinedDomains + 170);
  v6 = 0;
  uBytes = 0;
  HandleId = 0;
  v47 = 0;
  v7 = SampAcquireWriteLock(v5);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v10 = 72;
LABEL_5:
      WPP_SF_d(v9[3].Buffer, v10, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (unsigned int)v7);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  SampSetTransactionDomain(1);
  v11 = SampBuildAccountKeyName(4, &v48, 0);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_48;
    v13 = 73;
    v14 = (unsigned int)v11;
    goto LABEL_47;
  }
  v15 = SampQueryRegistryAccountsByMatchingRid((HKEY)SampKey, &v48, a4, &v51, (unsigned __int16 ***)&Src);
  v8 = v15;
  if ( v15 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_48;
    v19 = 74;
    goto LABEL_14;
  }
  if ( v51 <= 1 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 75, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, a4, v51);
    v8 = 0;
    goto LABEL_48;
  }
  v50 = 1;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 76, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, a4, v51);
  AccountContext = SampCreateAccountContext(4, a4, v16, v17, (__int64)Context, (__int64)&HandleId);
  v8 = AccountContext;
  if ( AccountContext < 0 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 77, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, a4, AccountContext);
LABEL_85:
    v21 = (PVOID **)HandleId;
LABEL_86:
    if ( v21 )
      SampDeleteContext(v21);
LABEL_92:
    if ( !v50 )
      goto LABEL_49;
LABEL_48:
    SampReleaseWriteLock(0);
    goto LABEL_49;
  }
  v21 = (PVOID **)HandleId;
  UnicodeStringAttribute = SampGetUnicodeStringAttribute((struct _SAMP_OBJECT *)HandleId);
  v8 = UnicodeStringAttribute;
  if ( UnicodeStringAttribute < 0 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        78,
        WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids,
        a4,
        UnicodeStringAttribute);
    goto LABEL_86;
  }
  SampDeleteContext(v21);
  HandleId = 0;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_Z(WPP_GLOBAL_Control[3].Buffer, 79, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, &v47);
  v8 = RtlULongLongMult(v51, 8u, &uBytes);
  if ( v8 < 0 )
    goto LABEL_48;
  v23 = LocalAlloc(0x40u, uBytes);
  v6 = v23;
  if ( !v23 )
  {
    v8 = -1073741670;
    v12 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_48;
    v13 = 80;
    v14 = 3221225626LL;
    goto LABEL_47;
  }
  memcpy_0(v23, Src, uBytes);
  v24 = v51;
  v25 = 0;
  if ( !v51 )
  {
LABEL_44:
    v8 = -1073741595;
    v12 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_48;
    v13 = 81;
    v14 = 3221225701LL;
    goto LABEL_47;
  }
  while ( 1 )
  {
    v26 = -1;
    v27 = v6[v25];
    do
      ++v26;
    while ( *(_WORD *)(v27 + 2 * v26) );
    LOBYTE(Contexta) = 1;
    if ( !(unsigned int)RtlCompareUnicodeStrings(
                          v27,
                          v26,
                          *((_QWORD *)&v47 + 1),
                          (unsigned __int64)(unsigned __int16)v47 >> 1,
                          Contexta) )
      break;
    if ( ++v25 >= v24 )
      goto LABEL_44;
  }
  v31 = &v6[v25];
  v32 = (unsigned __int16 *)*v31;
  uBytes = *v31;
  if ( v24 - v25 != 1 )
    memmove_0(v31, &v6[v25 + 1], 8LL * (v24 - v25 - 1));
  v33 = v24 - 1;
  if ( v33 > 1 )
    qsort_s(v6, v33, 8u, (_CoreCrtSecureSearchSortCompareFunction)CompareLPCWSTR, 0);
  if ( a1 != 2 )
  {
    v41 = SampLogDuplicateAccountNameDetected(a4, v32, (unsigned __int16 **)v6, v33);
    v38 = 0;
    v8 = v41;
    if ( v41 >= 0 )
      goto LABEL_78;
    v12 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_48;
    v13 = 86;
    v14 = (unsigned int)v41;
LABEL_47:
    WPP_SF_d(v12[3].Buffer, v13, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, v14);
    goto LABEL_48;
  }
  v15 = SampQueueAccountNameDeletions(&v48, (unsigned __int16 **)v6, v33);
  v8 = v15;
  if ( v15 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) == 0 || HIBYTE(WPP_GLOBAL_Control[4].Length) < 2u )
      goto LABEL_48;
    v19 = 82;
LABEL_14:
    WPP_SF_Dd(v18[3].Buffer, v19, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, a4, v15);
    goto LABEL_48;
  }
  LOBYTE(v34) = 1;
  v7 = SampReleaseWriteLock(v34);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v50 = 0;
    v35 = SampLogDuplicateAccountNameDeletions(a4, v32, (unsigned __int16 **)v6, v33);
    v38 = 0;
    v8 = v35;
    if ( v35 >= 0 )
    {
      v39 = WPP_GLOBAL_Control;
    }
    else
    {
      v39 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 84, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (unsigned int)v35);
        v39 = WPP_GLOBAL_Control;
      }
      v8 = 0;
    }
    if ( (*(_BYTE *)(&v39[4].MaximumLength + 1) & 1) == 0 || HIBYTE(v39[4].Length) < 4u )
      goto LABEL_79;
    WPP_SF_(v39[3].Buffer, 85, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids);
LABEL_78:
    v39 = WPP_GLOBAL_Control;
LABEL_79:
    if ( !v33 )
      goto LABEL_92;
    v40 = uBytes;
    do
    {
      if ( (*(_BYTE *)(&v39[4].MaximumLength + 1) & 1) != 0 && HIBYTE(v39[4].Length) >= 4u )
      {
        WPP_SF_DdSS(v39[3].Buffer, v36, v37, a4, a4, v40, v6[v38]);
        v39 = WPP_GLOBAL_Control;
      }
      ++v38;
    }
    while ( v38 < v33 );
    goto LABEL_85;
  }
  v9 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    v10 = 83;
    goto LABEL_5;
  }
LABEL_49:
  SampFreeUnicodeString(&v47);
  LocalFree(v6);
  v28 = (HLOCAL *)Src;
  if ( Src )
  {
    for ( i = 0; (unsigned int)i < v51; i = (unsigned int)(i + 1) )
    {
      LocalFree(v28[i]);
      v28 = (HLOCAL *)Src;
    }
    LocalFree(v28);
  }
  SampFreeUnicodeString(&v48);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 88, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids, (unsigned int)v8, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180096d88  mov     rax, rsp
0x180096d8b  mov     [rax+20h], rbx
0x180096d8f  mov     [rax+18h], r8d
0x180096d93  mov     [rax+10h], edx
0x180096d96  mov     [rax+8], ecx
0x180096d99  push    rbp
0x180096d9a  push    rsi
0x180096d9b  push    rdi
0x180096d9c  push    r12
0x180096d9e  push    r13
0x180096da0  push    r14
0x180096da2  push    r15
0x180096da4  mov     rbp, rsp
0x180096da7  sub     rsp, 80h
0x180096dae  mov     rcx, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180096db5  xor     r12d, r12d
0x180096db8  xorps   xmm0, xmm0
0x180096dbb  mov     [rbp+arg_10], r12d
0x180096dbf  mov     r14d, r9d
0x180096dc2  mov     [rbp+Src], r12
0x180096dc6  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x180096dca  mov     rcx, [rcx+550h]
0x180096dd1  mov     r13d, r12d
0x180096dd4  mov     [rbp+uBytes], r12
0x180096dd8  mov     [rbp+HandleId], r12
0x180096ddc  movups  [rbp+var_28], xmm0
0x180096de0  call    SampAcquireWriteLock
0x180096de5  lea     rsi, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180096dec  mov     ebx, eax
0x180096dee  test    eax, eax
0x180096df0  jns     short loc_180096E29
0x180096df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180096df9  lea     edi, [r12+1]
0x180096dfe  test    [rcx+44h], dil
0x180096e02  jz      loc_180097104
0x180096e08  cmp     byte ptr [rcx+41h], 2
0x180096e0c  jb      loc_180097104
0x180096e12  lea     edx, [rdi+47h]
0x180096e15  mov     r8, rsi
0x180096e18  mov     rcx, [rcx+38h]
0x180096e1c  mov     r9d, eax
0x180096e1f  call    WPP_SF_d
0x180096e24  jmp     loc_180097104
0x180096e29  mov     edi, 1
0x180096e2e  mov     ecx, edi
0x180096e30  call    SampSetTransactionDomain
0x180096e35  lea     r15d, [rdi+3]
0x180096e39  xor     r8d, r8d
0x180096e3c  mov     ecx, r15d
0x180096e3f  lea     rdx, [rbp+var_18]
0x180096e43  call    ?SampBuildAccountKeyName@@YAJW4_SAMP_OBJECT_TYPE@@PEAU_UNICODE_STRING@@1@Z; SampBuildAccountKeyName(_SAMP_OBJECT_TYPE,_UNICODE_STRING *,_UNICODE_STRING *)
0x180096e48  mov     ebx, eax
0x180096e4a  test    eax, eax
0x180096e4c  jns     short loc_180096E77
0x180096e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180096e55  test    [rcx+44h], dil
0x180096e59  jz      loc_1800970FD
0x180096e5f  cmp     byte ptr [rcx+41h], 2
0x180096e63  jb      loc_1800970FD
0x180096e69  lea     edx, [rdi+48h]
0x180096e6c  mov     r9d, eax
0x180096e6f  mov     r8, rsi
0x180096e72  jmp     loc_1800970F4
0x180096e77  mov     rcx, cs:SampKey; HKEY
0x180096e7e  lea     rax, [rbp+Src]
0x180096e82  lea     r9, [rbp+arg_10]; unsigned int *
0x180096e86  mov     [rsp+80h+Context], rax; unsigned __int16 ***
0x180096e8b  mov     r8d, r14d; unsigned int
0x180096e8e  lea     rdx, [rbp+var_18]; struct _UNICODE_STRING *
0x180096e92  call    ?SampQueryRegistryAccountsByMatchingRid@@YAJPEAUHKEY__@@PEAU_UNICODE_STRING@@KPEAKPEAPEAPEAG@Z; SampQueryRegistryAccountsByMatchingRid(HKEY__ *,_UNICODE_STRING *,ulong,ulong *,ushort * * *)
0x180096e97  mov     ebx, eax
0x180096e99  test    eax, eax
0x180096e9b  jns     short loc_180096ED5
0x180096e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180096ea4  test    [rcx+44h], dil
0x180096ea8  jz      loc_1800970FD
0x180096eae  cmp     byte ptr [rcx+41h], 2
0x180096eb2  jb      loc_1800970FD
0x180096eb8  mov     edx, 4Ah ; 'J'
0x180096ebd  mov     r8, rsi
0x180096ec0  mov     rcx, [rcx+38h]
0x180096ec4  mov     r9d, r14d
0x180096ec7  mov     dword ptr [rsp+80h+Context], eax
0x180096ecb  call    WPP_SF_Dd
0x180096ed0  jmp     loc_1800970FD
0x180096ed5  mov     eax, [rbp+arg_10]
0x180096ed8  cmp     eax, edi
0x180096eda  ja      short loc_180096F0F
0x180096edc  mov     rcx, cs:WPP_GLOBAL_Control
0x180096ee3  test    [rcx+44h], dil
0x180096ee7  jz      short loc_180096F07
0x180096ee9  cmp     [rcx+41h], r15b
0x180096eed  jb      short loc_180096F07
0x180096eef  mov     rcx, [rcx+38h]
0x180096ef3  mov     edx, 4Bh ; 'K'
0x180096ef8  mov     r9d, r14d
0x180096efb  mov     dword ptr [rsp+80h+Context], eax
0x180096eff  mov     r8, rsi
0x180096f02  call    WPP_SF_Dd
0x180096f07  mov     ebx, r12d
0x180096f0a  jmp     loc_1800970FD
0x180096f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180096f16  mov     [rbp+arg_8], edi
0x180096f19  test    [rcx+44h], dil
0x180096f1d  jz      short loc_180096F3D
0x180096f1f  cmp     [rcx+41h], r15b
0x180096f23  jb      short loc_180096F3D
0x180096f25  mov     rcx, [rcx+38h]
0x180096f29  mov     edx, 4Ch ; 'L'
0x180096f2e  mov     r9d, r14d
0x180096f31  mov     dword ptr [rsp+80h+Context], eax
0x180096f35  mov     r8, rsi
0x180096f38  call    WPP_SF_Dd
0x180096f3d  lea     rax, [rbp+HandleId]
0x180096f41  mov     edx, r14d
0x180096f44  mov     ecx, r15d
0x180096f47  mov     [rsp+80h+var_58], rax
0x180096f4c  call    ?SampCreateAccountContext@@YAJW4_SAMP_OBJECT_TYPE@@KEEEPEAPEAU_SAMP_OBJECT@@@Z; SampCreateAccountContext(_SAMP_OBJECT_TYPE,ulong,uchar,uchar,uchar,_SAMP_OBJECT * *)
0x180096f51  mov     ebx, eax
0x180096f53  test    eax, eax
0x180096f55  jns     short loc_180096F8F
0x180096f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180096f5e  test    [rcx+44h], dil
0x180096f62  jz      loc_18009734F
0x180096f68  cmp     byte ptr [rcx+41h], 2
0x180096f6c  jb      loc_18009734F
0x180096f72  mov     rcx, [rcx+38h]
0x180096f76  mov     edx, 4Dh ; 'M'
0x180096f7b  mov     r9d, r14d
0x180096f7e  mov     dword ptr [rsp+80h+Context], eax
0x180096f82  mov     r8, rsi
0x180096f85  call    WPP_SF_Dd
0x180096f8a  jmp     loc_18009734F
0x180096f8f  mov     r15, [rbp+HandleId]
0x180096f93  lea     r9, [rbp+var_28]
0x180096f97  mov     rcx, r15; struct _SAMP_OBJECT *
0x180096f9a  mov     r8b, dil
0x180096f9d  mov     edx, edi
0x180096f9f  call    SampGetUnicodeStringAttribute
0x180096fa4  mov     ebx, eax
0x180096fa6  test    eax, eax
0x180096fa8  jns     short loc_180096FE2
0x180096faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180096fb1  test    [rcx+44h], dil
0x180096fb5  jz      loc_180097353
0x180096fbb  cmp     byte ptr [rcx+41h], 2
0x180096fbf  jb      loc_180097353
0x180096fc5  mov     rcx, [rcx+38h]
0x180096fc9  mov     edx, 4Eh ; 'N'
0x180096fce  mov     r9d, r14d
0x180096fd1  mov     dword ptr [rsp+80h+Context], eax
0x180096fd5  mov     r8, rsi
0x180096fd8  call    WPP_SF_Dd
0x180096fdd  jmp     loc_180097353
0x180096fe2  mov     rcx, r15; HandleId
0x180096fe5  call    SampDeleteContext
0x180096fea  mov     [rbp+HandleId], r12
0x180096fee  mov     rcx, cs:WPP_GLOBAL_Control
0x180096ff5  test    [rcx+44h], dil
0x180096ff9  jz      short loc_180097016
0x180096ffb  cmp     byte ptr [rcx+41h], 4
0x180096fff  jb      short loc_180097016
0x180097001  mov     rcx, [rcx+38h]
0x180097005  lea     r9, [rbp+var_28]
0x180097009  mov     edx, 4Fh ; 'O'
0x18009700e  mov     r8, rsi
0x180097011  call    WPP_SF_Z
0x180097016  mov     ecx, [rbp+arg_10]; unsigned __int64
0x180097019  lea     r8, [rbp+uBytes]; unsigned __int64 *
0x18009701d  mov     edx, 8; unsigned __int64
0x180097022  call    ?RtlULongLongMult@@YAJ_K0PEA_K@Z; RtlULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180097027  mov     ebx, eax
0x180097029  test    eax, eax
0x18009702b  js      loc_1800970FD
0x180097031  mov     rdx, [rbp+uBytes]; uBytes
0x180097035  mov     ecx, 40h ; '@'; uFlags
0x18009703a  call    cs:__imp_LocalAlloc
0x180097040  mov     r13, rax
0x180097043  test    rax, rax
0x180097046  jnz     short loc_180097076
0x180097048  mov     ebx, 0C000009Ah
0x18009704d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097054  test    [rcx+44h], dil
0x180097058  jz      loc_1800970FD
0x18009705e  cmp     byte ptr [rcx+41h], 2
0x180097062  jb      loc_1800970FD
0x180097068  lea     edx, [rax+50h]
0x18009706b  mov     r9d, 0C000009Ah
0x180097071  jmp     loc_180096E6F
0x180097076  mov     r8, [rbp+uBytes]; Size
0x18009707a  mov     rcx, r13; void *
0x18009707d  mov     rdx, [rbp+Src]; Src
0x180097081  call    memcpy_0
0x180097086  mov     esi, [rbp+arg_10]
0x180097089  mov     ebx, r12d
0x18009708c  test    esi, esi
0x18009708e  jz      short loc_1800970CA
0x180097090  mov     eax, ebx
0x180097092  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180097096  mov     rcx, [r13+rax*8+0]
0x18009709b  inc     rdx
0x18009709e  cmp     [rcx+rdx*2], r12w
0x1800970a3  jnz     short loc_18009709B
0x1800970a5  movzx   r9d, word ptr [rbp+var_28]
0x1800970aa  mov     r8, qword ptr [rbp+var_28+8]
0x1800970ae  shr     r9, 1
0x1800970b1  mov     byte ptr [rsp+80h+Context], dil
0x1800970b6  call    cs:__imp_RtlCompareUnicodeStrings
0x1800970bc  test    eax, eax
0x1800970be  jz      loc_180097196
0x1800970c4  add     ebx, edi
0x1800970c6  cmp     ebx, esi
0x1800970c8  jb      short loc_180097090
0x1800970ca  mov     ebx, 0C00000E5h
0x1800970cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800970d6  test    [rcx+44h], dil
0x1800970da  jz      short loc_1800970FD
0x1800970dc  cmp     byte ptr [rcx+41h], 2
0x1800970e0  jb      short loc_1800970FD
0x1800970e2  mov     edx, 51h ; 'Q'
0x1800970e7  mov     r9d, 0C00000E5h
0x1800970ed  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x1800970f4  mov     rcx, [rcx+38h]
0x1800970f8  call    WPP_SF_d
0x1800970fd  xor     ecx, ecx
0x1800970ff  call    SampReleaseWriteLock
0x180097104  lea     rcx, [rbp+var_28]
0x180097108  call    SampFreeUnicodeString
0x18009710d  mov     rcx, r13; hMem
0x180097110  call    cs:__imp_LocalFree
0x180097116  mov     rax, [rbp+Src]
0x18009711a  test    rax, rax
0x18009711d  jz      short loc_180097144
0x18009711f  xor     esi, esi
0x180097121  cmp     [rbp+arg_10], esi
0x180097124  jbe     short loc_18009713B
0x180097126  mov     rcx, [rax+rsi*8]; hMem
0x18009712a  call    cs:__imp_LocalFree
0x180097130  mov     rax, [rbp+Src]
0x180097134  add     esi, edi
0x180097136  cmp     esi, [rbp+arg_10]
0x180097139  jb      short loc_180097126
0x18009713b  mov     rcx, rax; hMem
0x18009713e  call    cs:__imp_LocalFree
0x180097144  lea     rcx, [rbp+var_18]
0x180097148  call    SampFreeUnicodeString
0x18009714d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097154  test    dword ptr [rcx+44h], 20000h
0x18009715b  jz      short loc_180097179
0x18009715d  mov     rcx, [rcx+38h]
0x180097161  lea     r8, WPP_e294cfc5e5043c283e392179ed50e6b7_Traceguids
0x180097168  mov     edx, 58h ; 'X'
0x18009716d  mov     dword ptr [rsp+80h+Context], ebx
0x180097171  mov     r9d, ebx
0x180097174  call    WPP_SF_Dd
0x180097179  mov     eax, ebx
0x18009717b  mov     rbx, [rsp+80h+arg_18]
0x180097183  add     rsp, 80h
0x18009718a  pop     r15
0x18009718c  pop     r14
0x18009718e  pop     r13
0x180097190  pop     r12
0x180097192  pop     rdi
0x180097193  pop     rsi
0x180097194  pop     rbp
0x180097195  retn
0x180097196  mov     eax, ebx
0x180097198  lea     rcx, ds:0[rax*8]
0x1800971a0  mov     eax, esi
0x1800971a2  add     rcx, r13; void *
0x1800971a5  sub     eax, ebx
0x1800971a7  mov     r12, [rcx]
0x1800971aa  mov     [rbp+uBytes], r12
0x1800971ae  sub     eax, edi
0x1800971b0  jz      short loc_1800971CC
0x1800971b2  mov     r8d, eax
0x1800971b5  lea     eax, [rbx+1]
0x1800971b8  lea     rdx, ds:0[rax*8]
0x1800971c0  shl     r8, 3; Size
0x1800971c4  add     rdx, r13; Src
0x1800971c7  call    memmove_0
0x1800971cc  dec     esi
0x1800971ce  cmp     esi, edi
0x1800971d0  jbe     short loc_1800971F3
0x1800971d2  mov     edx, esi; NumOfElements
0x1800971d4  lea     r9, ?CompareLPCWSTR@@YAHPEAXPEBX1@Z; CompareFunction
0x1800971db  mov     r8d, 8; SizeOfElements
0x1800971e1  mov     [rsp+80h+Context], 0; Context
0x1800971ea  mov     rcx, r13; Base
0x1800971ed  call    cs:__imp_qsort_s
0x1800971f3  cmp     [rbp+arg_0], 2
0x1800971f7  jnz     loc_180097362
0x1800971fd  mov     r8d, esi; unsigned int
0x180097200  lea     rcx, [rbp+var_18]; struct _UNICODE_STRING *
0x180097204  mov     rdx, r13; unsigned __int16 **
0x180097207  call    ?SampQueueAccountNameDeletions@@YAJPEAU_UNICODE_STRING@@PEAPEAGK@Z; SampQueueAccountNameDeletions(_UNICODE_STRING *,ushort * *,ulong)
0x18009720c  mov     ebx, eax
0x18009720e  test    eax, eax
0x180097210  jns     short loc_18009723E
0x180097212  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
