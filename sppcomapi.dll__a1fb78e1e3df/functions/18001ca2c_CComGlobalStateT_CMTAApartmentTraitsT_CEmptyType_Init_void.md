# CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(void)

- ea: `0x18001ca2c`
- end: `0x18001cc42`
- name: `?Init@?$CComGlobalStateT@V?$CMTAApartmentTraitsT@VCEmptyType@@@@@@AEAAJXZ`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001bd4c`

## callees

- `0x1800032a0`
- `0x180003318`
- `0x180003520`
- `0x180004288`
- `0x18001c1f8`
- `0x18001ca2c`
- `0x18001cc48`
- `0x18001d750`
- `0x18003c51e`

## pseudocode

```c
__int64 __fastcall CComGlobalStateT<CMTAApartmentTraitsT<CEmptyType>>::Init(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  int v3; // r12d
  unsigned int v4; // ebx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // r15
  unsigned __int8 v10; // al
  int v11; // edi
  int v12; // eax
  __int64 v13; // r15
  __int64 v14; // r13
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // edi
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  int v22; // r8d
  unsigned int v24; // [rsp+60h] [rbp+8h] BYREF
  int v25; // [rsp+68h] [rbp+10h] BYREF

  v2 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  v3 = 0;
  v4 = 0;
  *(_DWORD *)(a1 + 56) = 0;
  while ( v2 )
  {
    v6 = *(_DWORD *)(v2 + 8);
    if ( !v6 )
    {
      *(_QWORD *)(a1 + 40) = *(_QWORD *)(v2 + 16);
      goto LABEL_43;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      *(_QWORD *)(a1 + 48) = *(_QWORD *)(v2 + 16);
      goto LABEL_43;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      v13 = *(int *)(a1 + 12);
      v25 = 0;
      if ( (int)v13 < 0 )
      {
        v4 = -2147418113;
        goto LABEL_35;
      }
      v14 = *(_QWORD *)(v2 + 16);
      v15 = SafeAdd<int>((unsigned int)v13, a2, &v25);
      v4 = v15;
      if ( v15 < 0 )
      {
        v17 = (unsigned int)v15;
        goto LABEL_17;
      }
      v18 = *(_DWORD *)(a1 + 8);
      if ( v18 < 0 )
      {
        v19 = 2147549183LL;
        v4 = -2147418113;
        goto LABEL_33;
      }
      if ( v25 > v18 )
      {
        v24 = *(_DWORD *)(a1 + 8);
        do
        {
          if ( v18 )
          {
            v20 = SafeMul<int>((unsigned int)v18, v16, &v24);
            v4 = v20;
            if ( v20 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v20);
            v18 = v24;
          }
          else
          {
            v18 = 32;
            v4 = 0;
            v24 = 32;
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
          if ( (v4 & 0x80000000) != 0 )
          {
            v19 = v4;
            goto LABEL_33;
          }
        }
        while ( v18 < v25 );
        v21 = CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(
                a1 + 8,
                (unsigned int)v18);
        v4 = v21;
        if ( v21 >= 0 )
          goto LABEL_34;
        v19 = (unsigned int)v21;
LABEL_33:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v19);
      }
      else
      {
        v4 = 0;
      }
LABEL_34:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
      if ( (v4 & 0x80000000) == 0 )
      {
        v22 = *(_DWORD *)(a1 + 12);
        if ( (int)v13 < v22 )
          memmove_0(
            (void *)(*(_QWORD *)(a1 + 16) + 8 * v13 + 8),
            (const void *)(*(_QWORD *)(a1 + 16) + 8 * v13),
            8LL * (v22 - (int)v13));
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v13) = 0;
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8 * v13) = v14;
        ++*(_DWORD *)(a1 + 12);
        v4 = 0;
      }
      else
      {
LABEL_35:
        v17 = v4;
LABEL_17:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
      if ( (v4 & 0x80000000) != 0 )
        goto LABEL_47;
      goto LABEL_43;
    }
    if ( v8 == 1 )
    {
      v9 = *(_QWORD *)(v2 + 16);
      v24 = 0;
      v4 = 0;
      v10 = CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(
              a1 + 24,
              v9 + 4,
              &v24);
      v11 = v10;
      if ( v10
        || (v12 = CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(
                    a1 + 24,
                    v24,
                    v9),
            v4 = v12,
            v12 >= 0) )
      {
        v3 = v11 ^ 1;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
      if ( (v4 & 0x80000000) != 0 )
        goto LABEL_47;
      if ( !v3 )
      {
        v4 = -2147418113;
LABEL_47:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
        break;
      }
      ++*(_DWORD *)(a1 + 56);
    }
LABEL_43:
    v2 = *(_QWORD *)v2;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x18001ca2c  mov     [rsp+arg_10], rbx
0x18001ca31  push    rbp
0x18001ca32  push    rsi
0x18001ca33  push    rdi
0x18001ca34  push    r12
0x18001ca36  push    r13
0x18001ca38  push    r14
0x18001ca3a  push    r15
0x18001ca3c  sub     rsp, 20h
0x18001ca40  mov     rsi, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18001ca47  xor     r12d, r12d
0x18001ca4a  xor     ebx, ebx
0x18001ca4c  mov     rbp, rcx
0x18001ca4f  mov     [rcx+38h], ebx
0x18001ca52  jmp     loc_18001CC0C
0x18001ca57  mov     ecx, [rsi+8]
0x18001ca5a  test    ecx, ecx
0x18001ca5c  jz      loc_18001CC01
0x18001ca62  sub     ecx, 1
0x18001ca65  jz      loc_18001CBF7
0x18001ca6b  sub     ecx, 1
0x18001ca6e  jz      short loc_18001CAE6
0x18001ca70  cmp     ecx, 1
0x18001ca73  jnz     loc_18001CC09
0x18001ca79  mov     r15, [rsi+10h]
0x18001ca7d  lea     r8, [rsp+58h+arg_0]
0x18001ca82  lea     rcx, [rbp+18h]
0x18001ca86  mov     [rsp+58h+arg_0], 0
0x18001ca8e  xor     ebx, ebx
0x18001ca90  lea     rdx, [r15+4]
0x18001ca94  call    ?Find@?$CSortedArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NAEBU_GUID@@PEAH@Z; CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(_GUID const &,int *)
0x18001ca99  movzx   edi, al
0x18001ca9c  test    al, al
0x18001ca9e  jnz     short loc_18001CABF
0x18001caa0  mov     edx, [rsp+58h+arg_0]
0x18001caa4  lea     rcx, [rbp+18h]
0x18001caa8  mov     r8, r15
0x18001caab  call    ?Insert@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHPEAU?$CComObjectActivationT@VCEmptyType@@@@@Z; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(int,CComObjectActivationT<CEmptyType> *)
0x18001cab0  mov     ebx, eax
0x18001cab2  test    eax, eax
0x18001cab4  jns     short loc_18001CABF
0x18001cab6  mov     ecx, eax
0x18001cab8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cabd  jmp     short loc_18001CAC6
0x18001cabf  mov     r12d, edi
0x18001cac2  xor     r12d, 1
0x18001cac6  mov     ecx, ebx
0x18001cac8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cacd  test    ebx, ebx
0x18001cacf  js      loc_18001CC1C
0x18001cad5  test    r12d, r12d
0x18001cad8  jz      loc_18001CC17
0x18001cade  inc     dword ptr [rbp+38h]
0x18001cae1  jmp     loc_18001CC09
0x18001cae6  movsxd  r15, dword ptr [rbp+0Ch]
0x18001caea  mov     [rsp+58h+arg_8], 0
0x18001caf2  test    r15d, r15d
0x18001caf5  jns     short loc_18001CB01
0x18001caf7  mov     ebx, 8000FFFFh
0x18001cafc  jmp     loc_18001CBA8
0x18001cb01  mov     r13, [rsi+10h]
0x18001cb05  lea     r8, [rsp+58h+arg_8]
0x18001cb0a  mov     ecx, r15d
0x18001cb0d  call    ??$SafeAdd@H@@YAJHHPEAH@Z; SafeAdd<int>(int,int,int *)
0x18001cb12  mov     ebx, eax
0x18001cb14  test    eax, eax
0x18001cb16  jns     short loc_18001CB24
0x18001cb18  mov     ecx, eax
0x18001cb1a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cb1f  jmp     loc_18001CBEA
0x18001cb24  mov     edi, [rbp+8]
0x18001cb27  test    edi, edi
0x18001cb29  jns     short loc_18001CB34
0x18001cb2b  mov     ecx, 8000FFFFh
0x18001cb30  mov     ebx, ecx
0x18001cb32  jmp     short loc_18001CB98
0x18001cb34  cmp     [rsp+58h+arg_8], edi
0x18001cb38  jg      short loc_18001CB3E
0x18001cb3a  xor     ebx, ebx
0x18001cb3c  jmp     short loc_18001CB9D
0x18001cb3e  mov     [rsp+58h+arg_0], edi
0x18001cb42  test    edi, edi
0x18001cb44  jnz     short loc_18001CB53
0x18001cb46  mov     edi, 20h ; ' '
0x18001cb4b  xor     ebx, ebx
0x18001cb4d  mov     [rsp+58h+arg_0], edi
0x18001cb51  jmp     short loc_18001CB70
0x18001cb53  lea     r8, [rsp+58h+arg_0]
0x18001cb58  mov     ecx, edi
0x18001cb5a  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x18001cb5f  mov     ebx, eax
0x18001cb61  test    eax, eax
0x18001cb63  jns     short loc_18001CB6C
0x18001cb65  mov     ecx, eax
0x18001cb67  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cb6c  mov     edi, [rsp+58h+arg_0]
0x18001cb70  mov     ecx, ebx
0x18001cb72  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cb77  test    ebx, ebx
0x18001cb79  js      short loc_18001CB96
0x18001cb7b  cmp     edi, [rsp+58h+arg_8]
0x18001cb7f  jl      short loc_18001CB42
0x18001cb81  mov     edx, edi
0x18001cb83  lea     rcx, [rbp+8]
0x18001cb87  call    ?SetSize@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001cb8c  mov     ebx, eax
0x18001cb8e  test    eax, eax
0x18001cb90  jns     short loc_18001CB9D
0x18001cb92  mov     ecx, eax
0x18001cb94  jmp     short loc_18001CB98
0x18001cb96  mov     ecx, ebx
0x18001cb98  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cb9d  mov     ecx, ebx
0x18001cb9f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cba4  test    ebx, ebx
0x18001cba6  jns     short loc_18001CBAF
0x18001cba8  mov     ecx, ebx
0x18001cbaa  jmp     loc_18001CB1A
0x18001cbaf  mov     r8d, [rbp+0Ch]
0x18001cbb3  cmp     r15d, r8d
0x18001cbb6  jge     short loc_18001CBD3
0x18001cbb8  mov     rcx, [rbp+10h]
0x18001cbbc  sub     r8d, r15d
0x18001cbbf  movsxd  r8, r8d
0x18001cbc2  shl     r8, 3; Size
0x18001cbc6  lea     rdx, [rcx+r15*8]; Src
0x18001cbca  lea     rcx, [rdx+8]; void *
0x18001cbce  call    memmove_0
0x18001cbd3  mov     rax, [rbp+10h]
0x18001cbd7  xor     edx, edx
0x18001cbd9  mov     [rax+r15*8], rdx
0x18001cbdd  mov     rax, [rbp+10h]
0x18001cbe1  mov     [rax+r15*8], r13
0x18001cbe5  inc     dword ptr [rbp+0Ch]
0x18001cbe8  xor     ebx, ebx
0x18001cbea  mov     ecx, ebx
0x18001cbec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cbf1  test    ebx, ebx
0x18001cbf3  js      short loc_18001CC1C
0x18001cbf5  jmp     short loc_18001CC09
0x18001cbf7  mov     rax, [rsi+10h]
0x18001cbfb  mov     [rbp+30h], rax
0x18001cbff  jmp     short loc_18001CC09
0x18001cc01  mov     rax, [rsi+10h]
0x18001cc05  mov     [rbp+28h], rax
0x18001cc09  mov     rsi, [rsi]
0x18001cc0c  test    rsi, rsi
0x18001cc0f  jnz     loc_18001CA57
0x18001cc15  jmp     short loc_18001CC23
0x18001cc17  mov     ebx, 8000FFFFh
0x18001cc1c  mov     ecx, ebx
0x18001cc1e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cc23  mov     ecx, ebx
0x18001cc25  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cc2a  mov     eax, ebx
0x18001cc2c  mov     rbx, [rsp+58h+arg_10]
0x18001cc31  add     rsp, 20h
0x18001cc35  pop     r15
0x18001cc37  pop     r14
0x18001cc39  pop     r13
0x18001cc3b  pop     r12
0x18001cc3d  pop     rdi
0x18001cc3e  pop     rsi
0x18001cc3f  pop     rbp
0x18001cc40  retn
```
