# CArray<CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Insert(int,CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem const &)

- ea: `0x18000405c`
- end: `0x1800041c1`
- name: `?Insert@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHAEBUCTypeInfoItem@?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@@Z`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003020`

## callees

- `0x1800032a0`
- `0x180003318`
- `0x180003520`
- `0x18000405c`
- `0x180004288`
- `0x180004520`
- `0x18003c51e`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CArray<CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Insert(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v4; // rbp
  __int64 v5; // rcx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // edi
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // r8d
  __int64 v17; // rbx
  __int64 v18; // rdi
  __int64 v19; // rbp
  __int64 v20; // rcx
  int v22; // [rsp+40h] [rbp+8h] BYREF
  int v23; // [rsp+58h] [rbp+20h] BYREF

  v4 = (int)a2;
  v5 = *(unsigned int *)(a1 + 4);
  v23 = 0;
  if ( (int)v5 < 0 )
  {
    v7 = -2147418113;
    v8 = 2147549183LL;
LABEL_5:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_29;
  }
  v9 = SafeAdd<int>(v5, a2, &v23);
  v7 = v9;
  if ( v9 < 0 )
  {
    v8 = (unsigned int)v9;
    goto LABEL_5;
  }
  v11 = *(_DWORD *)a1;
  if ( *(int *)a1 >= 0 )
  {
    if ( v23 <= v11 )
    {
      v12 = 0;
      goto LABEL_22;
    }
    v22 = *(_DWORD *)a1;
    do
    {
      if ( v11 )
      {
        v14 = SafeMul<int>((unsigned int)v11, v10, &v22);
        v12 = v14;
        if ( v14 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
        v11 = v22;
      }
      else
      {
        v11 = 32;
        v12 = 0;
        v22 = 32;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
      if ( v12 < 0 )
      {
        v13 = (unsigned int)v12;
        goto LABEL_21;
      }
    }
    while ( v11 < v23 );
    v15 = CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::SetSize(
            a1,
            v11);
    v12 = v15;
    if ( v15 >= 0 )
      goto LABEL_22;
    v13 = (unsigned int)v15;
  }
  else
  {
    v12 = -2147418113;
    v13 = 2147549183LL;
  }
LABEL_21:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
  if ( v12 < 0 )
  {
    v7 = v12;
    v8 = (unsigned int)v12;
    goto LABEL_5;
  }
  v16 = *(_DWORD *)(a1 + 4);
  if ( (int)v4 < v16 )
    memmove_0(
      (void *)(*(_QWORD *)(a1 + 8) + 16 * v4 + 16),
      (const void *)(*(_QWORD *)(a1 + 8) + 16 * v4),
      16LL * (v16 - (int)v4));
  v17 = 2 * v4;
  *(_OWORD *)(*(_QWORD *)(a1 + 8) + 8 * v17) = 0;
  v18 = *(_QWORD *)(a1 + 8);
  v19 = *a3;
  *a3 = 0;
  v20 = *(_QWORD *)(v18 + 8 * v17);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  *(_QWORD *)(v18 + 8 * v17) = v19;
  *(_DWORD *)(v18 + 8 * v17 + 8) = *((_DWORD *)a3 + 2);
  ++*(_DWORD *)(a1 + 4);
  v7 = 0;
LABEL_29:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x18000405c  mov     [rsp+arg_8], rbx
0x180004061  mov     [rsp+arg_10], rbp
0x180004066  push    rsi
0x180004067  push    rdi
0x180004068  push    r14
0x18000406a  sub     rsp, 20h
0x18000406e  mov     rsi, rcx
0x180004071  movsxd  rbp, edx
0x180004074  mov     ecx, [rcx+4]
0x180004077  mov     r14, r8
0x18000407a  mov     [rsp+38h+arg_18], 0
0x180004082  test    ecx, ecx
0x180004084  jns     short loc_18000408F
0x180004086  mov     edi, 8000FFFFh
0x18000408b  mov     ecx, edi
0x18000408d  jmp     short loc_1800040A1
0x18000408f  lea     r8, [rsp+38h+arg_18]
0x180004094  call    ??$SafeAdd@H@@YAJHHPEAH@Z; SafeAdd<int>(int,int,int *)
0x180004099  mov     edi, eax
0x18000409b  test    eax, eax
0x18000409d  jns     short loc_1800040AB
0x18000409f  mov     ecx, eax
0x1800040a1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800040a6  jmp     loc_1800041A4
0x1800040ab  mov     edi, [rsi]
0x1800040ad  test    edi, edi
0x1800040af  jns     short loc_1800040BC
0x1800040b1  mov     edi, 8000FFFFh
0x1800040b6  mov     ebx, edi
0x1800040b8  mov     ecx, edi
0x1800040ba  jmp     short loc_18000411F
0x1800040bc  cmp     [rsp+38h+arg_18], edi
0x1800040c0  jg      short loc_1800040C6
0x1800040c2  xor     ebx, ebx
0x1800040c4  jmp     short loc_180004124
0x1800040c6  mov     [rsp+38h+arg_0], edi
0x1800040ca  test    edi, edi
0x1800040cc  jnz     short loc_1800040DB
0x1800040ce  mov     edi, 20h ; ' '
0x1800040d3  xor     ebx, ebx
0x1800040d5  mov     [rsp+38h+arg_0], edi
0x1800040d9  jmp     short loc_1800040F8
0x1800040db  lea     r8, [rsp+38h+arg_0]
0x1800040e0  mov     ecx, edi
0x1800040e2  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x1800040e7  mov     ebx, eax
0x1800040e9  test    eax, eax
0x1800040eb  jns     short loc_1800040F4
0x1800040ed  mov     ecx, eax
0x1800040ef  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800040f4  mov     edi, [rsp+38h+arg_0]
0x1800040f8  mov     ecx, ebx
0x1800040fa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800040ff  test    ebx, ebx
0x180004101  js      short loc_18000411D
0x180004103  cmp     edi, [rsp+38h+arg_18]
0x180004107  jl      short loc_1800040CA
0x180004109  mov     edx, edi
0x18000410b  mov     rcx, rsi
0x18000410e  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180004113  mov     ebx, eax
0x180004115  test    eax, eax
0x180004117  jns     short loc_180004124
0x180004119  mov     ecx, eax
0x18000411b  jmp     short loc_18000411F
0x18000411d  mov     ecx, ebx
0x18000411f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180004124  mov     ecx, ebx
0x180004126  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000412b  test    ebx, ebx
0x18000412d  jns     short loc_180004138
0x18000412f  mov     edi, ebx
0x180004131  mov     ecx, ebx
0x180004133  jmp     loc_1800040A1
0x180004138  mov     r8d, [rsi+4]
0x18000413c  mov     rbx, rbp
0x18000413f  cmp     ebp, r8d
0x180004142  jge     short loc_180004162
0x180004144  sub     r8d, ebp
0x180004147  mov     rdx, rbp
0x18000414a  shl     rdx, 4
0x18000414e  add     rdx, [rsi+8]; Src
0x180004152  movsxd  r8, r8d
0x180004155  shl     r8, 4; Size
0x180004159  lea     rcx, [rdx+10h]; void *
0x18000415d  call    memmove_0
0x180004162  mov     rax, [rsi+8]
0x180004166  add     rbx, rbx
0x180004169  xorps   xmm0, xmm0
0x18000416c  movups  xmmword ptr [rax+rbx*8], xmm0
0x180004170  mov     rdi, [rsi+8]
0x180004174  mov     rbp, [r14]
0x180004177  mov     qword ptr [r14], 0
0x18000417e  mov     rcx, [rdi+rbx*8]
0x180004182  test    rcx, rcx
0x180004185  jz      short loc_180004193
0x180004187  mov     rax, [rcx]
0x18000418a  mov     rax, [rax+10h]
0x18000418e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004193  mov     [rdi+rbx*8], rbp
0x180004197  mov     eax, [r14+8]
0x18000419b  mov     [rdi+rbx*8+8], eax
0x18000419f  inc     dword ptr [rsi+4]
0x1800041a2  xor     edi, edi
0x1800041a4  mov     ecx, edi
0x1800041a6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800041ab  mov     rbx, [rsp+38h+arg_8]
0x1800041b0  mov     eax, edi
0x1800041b2  mov     rbp, [rsp+38h+arg_10]
0x1800041b7  add     rsp, 20h
0x1800041bb  pop     r14
0x1800041bd  pop     rdi
0x1800041be  pop     rsi
0x1800041bf  retn
```
