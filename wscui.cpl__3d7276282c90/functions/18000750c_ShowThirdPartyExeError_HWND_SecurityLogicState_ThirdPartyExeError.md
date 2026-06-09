# ShowThirdPartyExeError(HWND__ *,SecurityLogicState *,ThirdPartyExeError)

- ea: `0x18000750c`
- end: `0x1800076b7`
- name: `?ShowThirdPartyExeError@@YA_NPEAUHWND__@@PEAVSecurityLogicState@@W4ThirdPartyExeError@@@Z`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007854`
- `0x180007938`

## callees

- `0x180001b90`
- `0x180004838`
- `0x180004c48`
- `0x180004f20`
- `0x1800052cc`
- `0x18000750c`
- `0x180007bc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall ShowThirdPartyExeError(__int64 a1, __int64 a2, int a3)
{
  int v6; // ebx
  char *v7; // rdx
  char *v8; // rbx
  int *v9; // rdi
  char *v10; // rdx
  __int64 v11; // rbx
  char *v12; // rdx
  bool v13; // di
  char *v15[2]; // [rsp+40h] [rbp-10h] BYREF
  char *v16; // [rsp+88h] [rbp+38h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v16);
  if ( !a3 )
  {
    v12 = *SecurityLogicControl::GetString(v15, 0x47Fu, *(unsigned __int16 **)(a2 + 64));
    v8 = v16;
    v9 = (int *)(v16 - 24);
    if ( v12 - 24 == v16 - 24 )
      goto LABEL_21;
    if ( v9[4] < 0 || *((_QWORD *)v12 - 3) != *(_QWORD *)v9 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v16, v12, *((_DWORD *)v12 - 4));
      v8 = v16;
      goto LABEL_21;
    }
LABEL_13:
    v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
    ATL::CStringData::Release((ATL::CStringData *)v9);
    v8 = (char *)(v11 + 24);
LABEL_21:
    ATL::CStringData::Release((ATL::CStringData *)(v15[0] - 24));
    goto LABEL_22;
  }
  v6 = a3 - 1;
  if ( !v6 )
  {
    v10 = *SecurityLogicControl::GetString(v15, 0x4A9u, *(unsigned __int16 **)(a2 + 64));
    v8 = v16;
    v9 = (int *)(v16 - 24);
    if ( v10 - 24 == v16 - 24 )
      goto LABEL_21;
    if ( v9[4] < 0 || *((_QWORD *)v10 - 3) != *(_QWORD *)v9 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v16, v10, *((_DWORD *)v10 - 4));
      v8 = v16;
      goto LABEL_21;
    }
    goto LABEL_13;
  }
  if ( v6 == 1 )
  {
    v7 = *SecurityLogicControl::GetString(v15, 0x490u, *(unsigned __int16 **)(a2 + 64));
    v8 = v16;
    v9 = (int *)(v16 - 24);
    if ( v7 - 24 == v16 - 24 )
      goto LABEL_21;
    if ( v9[4] < 0 || *((_QWORD *)v7 - 3) != *(_QWORD *)v9 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v16, v7, *((_DWORD *)v7 - 4));
      v8 = v16;
      goto LABEL_21;
    }
    goto LABEL_13;
  }
  v8 = v16;
LABEL_22:
  v13 = (int)IsolationAwareTaskDialog(a1, (__int64)hInstance) >= 0;
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
  return v13;
}

```

## disassembly

```asm
0x18000750c  mov     [rsp-18h+arg_0], rbx
0x180007511  push    rbp
0x180007512  push    rsi
0x180007513  push    rdi
0x180007514  mov     rbp, rsp
0x180007517  sub     rsp, 50h
0x18000751b  mov     ebx, r8d
0x18000751e  mov     rdi, rdx
0x180007521  mov     rsi, rcx
0x180007524  lea     rcx, [rbp+arg_18]
0x180007528  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000752d  nop
0x18000752e  mov     [rbp+arg_10], 0
0x180007535  test    ebx, ebx
0x180007537  jz      loc_18000760F
0x18000753d  sub     ebx, 1
0x180007540  jz      short loc_1800075B1
0x180007542  cmp     ebx, 1
0x180007545  jnz     short loc_1800075A8
0x180007547  mov     r8, [rdi+40h]
0x18000754b  mov     edx, 490h
0x180007550  lea     rcx, [rbp+var_10]
0x180007554  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x180007559  nop
0x18000755a  mov     rdx, [rax]
0x18000755d  lea     rcx, [rdx-18h]
0x180007561  mov     rbx, [rbp+arg_18]
0x180007565  lea     rdi, [rbx-18h]
0x180007569  cmp     rcx, rdi
0x18000756c  jz      short loc_1800075A3
0x18000756e  cmp     dword ptr [rdi+10h], 0
0x180007572  jl      short loc_180007592
0x180007574  mov     rax, [rdi]
0x180007577  cmp     [rcx], rax
0x18000757a  jnz     short loc_180007592
0x18000757c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180007581  mov     rbx, rax
0x180007584  mov     rcx, rdi; this
0x180007587  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000758c  add     rbx, 18h
0x180007590  jmp     short loc_1800075A3
0x180007592  mov     r8d, [rdx-10h]
0x180007596  lea     rcx, [rbp+arg_18]
0x18000759a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000759f  mov     rbx, [rbp+arg_18]
0x1800075a3  jmp     loc_18000766B
0x1800075a8  mov     rbx, [rbp+arg_18]
0x1800075ac  jmp     loc_180007678
0x1800075b1  mov     r8, [rdi+40h]
0x1800075b5  mov     edx, 4A9h
0x1800075ba  lea     rcx, [rbp+var_10]
0x1800075be  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x1800075c3  nop
0x1800075c4  mov     rdx, [rax]
0x1800075c7  lea     rcx, [rdx-18h]
0x1800075cb  mov     rbx, [rbp+arg_18]
0x1800075cf  lea     rdi, [rbx-18h]
0x1800075d3  cmp     rcx, rdi
0x1800075d6  jz      short loc_18000760D
0x1800075d8  cmp     dword ptr [rdi+10h], 0
0x1800075dc  jl      short loc_1800075FC
0x1800075de  mov     rax, [rdi]
0x1800075e1  cmp     [rcx], rax
0x1800075e4  jnz     short loc_1800075FC
0x1800075e6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800075eb  mov     rbx, rax
0x1800075ee  mov     rcx, rdi; this
0x1800075f1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800075f6  add     rbx, 18h
0x1800075fa  jmp     short loc_18000760D
0x1800075fc  mov     r8d, [rdx-10h]
0x180007600  lea     rcx, [rbp+arg_18]
0x180007604  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180007609  mov     rbx, [rbp+arg_18]
0x18000760d  jmp     short loc_18000766B
0x18000760f  mov     r8, [rdi+40h]
0x180007613  mov     edx, 47Fh
0x180007618  lea     rcx, [rbp+var_10]
0x18000761c  call    ?GetString@SecurityLogicControl@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEBG@Z; SecurityLogicControl::GetString(int,ushort const *)
0x180007621  nop
0x180007622  mov     rdx, [rax]
0x180007625  lea     rcx, [rdx-18h]
0x180007629  mov     rbx, [rbp+arg_18]
0x18000762d  lea     rdi, [rbx-18h]
0x180007631  cmp     rcx, rdi
0x180007634  jz      short loc_18000766B
0x180007636  cmp     dword ptr [rdi+10h], 0
0x18000763a  jl      short loc_18000765A
0x18000763c  mov     rax, [rdi]
0x18000763f  cmp     [rcx], rax
0x180007642  jnz     short loc_18000765A
0x180007644  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180007649  mov     rbx, rax
0x18000764c  mov     rcx, rdi; this
0x18000764f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007654  add     rbx, 18h
0x180007658  jmp     short loc_18000766B
0x18000765a  mov     r8d, [rdx-10h]
0x18000765e  lea     rcx, [rbp+arg_18]
0x180007662  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180007667  mov     rbx, [rbp+arg_18]
0x18000766b  mov     rcx, [rbp+var_10]
0x18000766f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007673  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007678  lea     rax, [rbp+arg_10]
0x18000767c  mov     [rsp+50h+var_18], rax
0x180007681  mov     [rsp+50h+var_30], rbx
0x180007686  mov     rdx, cs:hInstance
0x18000768d  mov     rcx, rsi
0x180007690  call    IsolationAwareTaskDialog
0x180007695  mov     edi, eax
0x180007697  shr     edi, 1Fh
0x18000769a  xor     dil, 1
0x18000769e  lea     rcx, [rbx-18h]; this
0x1800076a2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800076a7  mov     al, dil
0x1800076aa  mov     rbx, [rsp+50h+arg_0]
0x1800076af  add     rsp, 50h
0x1800076b3  pop     rdi
0x1800076b4  pop     rsi
0x1800076b5  pop     rbp
0x1800076b6  retn
```
