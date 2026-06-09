# CUWFCspCurrentSessionNode::SetValue(tagVARIANT)

- ea: `0x18000e300`
- end: `0x18000e507`
- name: `?SetValue@CUWFCspCurrentSessionNode@@UEAAJUtagVARIANT@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(CUWFCspCurrentSessionNode *this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b90`
- `0x180007fc4`
- `0x18000b4dc`
- `0x18000b61c`
- `0x18000c1ec`
- `0x18000c5b4`
- `0x18000c8d8`
- `0x18000cbfc`
- `0x18000e300`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000e373`
- `OLEAUT32!__imp_VariantInit` at `0x18000e373`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000e3e1`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000e407`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000e3e1`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000e407`
- `uwfcfgmgmt!UwfCfgSetCriticalThreshold` at `0x18000e417`
- `uwfcfgmgmt!UwfCfgSetCriticalThreshold` at `0x18000e417`
- `uwfcfgmgmt!UwfCfgSetWarningThreshold` at `0x18000e3f1`
- `uwfcfgmgmt!UwfCfgSetWarningThreshold` at `0x18000e3f1`
- `uwfcfgmgmt!UwfCfgSetOverlayCommitState` at `0x18000e3cb`
- `uwfcfgmgmt!UwfCfgSetOverlayCommitState` at `0x18000e3cb`

## pseudocode

```c
__int64 __fastcall CUWFCspCurrentSessionNode::SetValue(CUWFCspCurrentSessionNode *this, struct tagVARIANT *a2)
{
  int *v4; // rbx
  HRESULT v5; // edi
  HRESULT v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rdx
  RTL_SRWLOCK *v9; // r8
  int *v10; // rsi
  int v11; // r8d
  LONG lVal; // edx
  int *v14; // [rsp+20h] [rbp-E0h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v16[42]; // [rsp+40h] [rbp-C0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v16);
  v16[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v16, L"UWFCSPCurrentSessionNodeSet");
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (int *)((char *)this + 44);
  if ( !a2->vt )
    goto LABEL_2;
  if ( *v4 == 6 )
  {
    v5 = VariantChangeType(&pvarg, a2, 0, 0x13u);
    if ( v5 < 0 )
      goto LABEL_14;
    v6 = UwfCfgSetCriticalThreshold(pvarg.cyVal.Lo);
    goto LABEL_13;
  }
  if ( *v4 == 7 )
  {
    v5 = VariantChangeType(&pvarg, a2, 0, 0x13u);
    if ( v5 < 0 )
      goto LABEL_14;
    v6 = UwfCfgSetWarningThreshold(pvarg.cyVal.Lo);
LABEL_13:
    v5 = v6;
    goto LABEL_14;
  }
  if ( *v4 != 16 )
  {
    v5 = (*((_DWORD *)this + 13) & 2) != 0 ? -2147467263 : -2046820335;
    goto LABEL_14;
  }
  if ( a2->vt == 11 )
  {
    v6 = UwfCfgSetOverlayCommitState(a2->iVal != 0);
    goto LABEL_13;
  }
LABEL_2:
  v5 = -2147024809;
LABEL_14:
  v7 = *((_QWORD *)this + 3);
  v8 = *((unsigned int *)this + 10);
  v14 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, int **))(*(_QWORD *)v7 + 88LL))(v7, v8, &v14) < 0 || (v10 = v14) == 0 )
  {
    v10 = &dword_18001F7A4;
    v14 = &dword_18001F7A4;
  }
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    (__int64)v16,
    v5,
    v9);
  if ( !a2 )
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
      (__int64)v16,
      -1,
      *v4,
      (__int64)v10);
  v11 = *v4;
  if ( a2->vt == 3 )
  {
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<long,unsigned long,unsigned short const *>(
      (__int64)v16,
      a2->lVal,
      v11,
      (__int64)v10);
  }
  else if ( a2->vt == 8 )
  {
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned short *,unsigned long,unsigned short const *>(
      (__int64)v16,
      a2->plVal,
      v11,
      v10);
  }
  else if ( a2->vt == 11 )
  {
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<short,unsigned long,unsigned short const *>(
      (__int64)v16,
      a2->iVal,
      v11,
      v10);
  }
  else
  {
    if ( a2->vt == 19 )
      lVal = a2->lVal;
    else
      lVal = -1;
    UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned long,unsigned short const *>(
      (__int64)v16,
      lVal,
      v11,
      (__int64)v10);
  }
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e300  mov     [rsp-8+arg_10], rbx
0x18000e305  mov     [rsp-8+arg_18], rsi
0x18000e30a  push    rbp
0x18000e30b  push    rdi
0x18000e30c  push    r13
0x18000e30e  push    r14
0x18000e310  push    r15
0x18000e312  lea     rbp, [rsp-0A0h]
0x18000e31a  sub     rsp, 1A0h
0x18000e321  mov     rax, cs:__security_cookie
0x18000e328  xor     rax, rsp
0x18000e32b  mov     [rbp+0C0h+var_30], rax
0x18000e332  mov     rsi, rcx
0x18000e335  mov     r14, rdx
0x18000e338  lea     rcx, [rsp+1C0h+var_180]
0x18000e33d  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000e342  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000e349  lea     rdx, aUwfcspcurrents_0; "UWFCSPCurrentSessionNodeSet"
0x18000e350  mov     [rsp+1C0h+var_180], rax
0x18000e355  lea     rcx, [rsp+1C0h+var_180]
0x18000e35a  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000e35f  xorps   xmm0, xmm0
0x18000e362  lea     rcx, [rsp+1C0h+pvarg]; pvarg
0x18000e367  xor     eax, eax
0x18000e369  movups  xmmword ptr [rsp+1C0h+pvarg], xmm0
0x18000e36e  mov     qword ptr [rsp+1C0h+pvarg+10h], rax
0x18000e373  call    cs:__imp_VariantInit
0x18000e379  xor     r15d, r15d
0x18000e37c  lea     rbx, [rsi+2Ch]
0x18000e380  lea     r13d, [r15+13h]
0x18000e384  cmp     r15w, [r14]
0x18000e388  jnz     short loc_18000E394
0x18000e38a  mov     edi, 80070057h
0x18000e38f  jmp     loc_18000E41F
0x18000e394  mov     ecx, [rbx]
0x18000e396  sub     ecx, 6
0x18000e399  jz      short loc_18000E3F9
0x18000e39b  sub     ecx, 1
0x18000e39e  jz      short loc_18000E3D3
0x18000e3a0  cmp     ecx, 9
0x18000e3a3  jz      short loc_18000E3BC
0x18000e3a5  mov     eax, [rsi+34h]
0x18000e3a8  and     al, 2
0x18000e3aa  neg     al
0x18000e3ac  sbb     edi, edi
0x18000e3ae  and     edi, 0FA003FF0h
0x18000e3b4  add     edi, 86000011h
0x18000e3ba  jmp     short loc_18000E41F
0x18000e3bc  cmp     word ptr [r14], 0Bh
0x18000e3c1  jnz     short loc_18000E38A
0x18000e3c3  cmp     [r14+8], r15w
0x18000e3c8  setnz   cl
0x18000e3cb  call    cs:__imp_?UwfCfgSetOverlayCommitState@@YAJ_N@Z; UwfCfgSetOverlayCommitState(bool)
0x18000e3d1  jmp     short loc_18000E41D
0x18000e3d3  mov     r9d, r13d; vt
0x18000e3d6  lea     rcx, [rsp+1C0h+pvarg]; pvargDest
0x18000e3db  xor     r8d, r8d; wFlags
0x18000e3de  mov     rdx, r14; pvarSrc
0x18000e3e1  call    cs:__imp_VariantChangeType
0x18000e3e7  mov     edi, eax
0x18000e3e9  test    eax, eax
0x18000e3eb  js      short loc_18000E41F
0x18000e3ed  mov     ecx, dword ptr [rsp+1C0h+pvarg+8]
0x18000e3f1  call    cs:__imp_?UwfCfgSetWarningThreshold@@YAJK@Z; UwfCfgSetWarningThreshold(ulong)
0x18000e3f7  jmp     short loc_18000E41D
0x18000e3f9  mov     r9d, r13d; vt
0x18000e3fc  lea     rcx, [rsp+1C0h+pvarg]; pvargDest
0x18000e401  xor     r8d, r8d; wFlags
0x18000e404  mov     rdx, r14; pvarSrc
0x18000e407  call    cs:__imp_VariantChangeType
0x18000e40d  mov     edi, eax
0x18000e40f  test    eax, eax
0x18000e411  js      short loc_18000E41F
0x18000e413  mov     ecx, dword ptr [rsp+1C0h+pvarg+8]
0x18000e417  call    cs:__imp_?UwfCfgSetCriticalThreshold@@YAJK@Z; UwfCfgSetCriticalThreshold(ulong)
0x18000e41d  mov     edi, eax
0x18000e41f  mov     rcx, [rsi+18h]
0x18000e423  lea     r8, [rsp+1C0h+var_1A0]
0x18000e428  mov     edx, [rsi+28h]
0x18000e42b  mov     [rsp+1C0h+var_1A0], r15
0x18000e430  mov     rax, [rcx]
0x18000e433  mov     rax, [rax+58h]
0x18000e437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43c  test    eax, eax
0x18000e43e  js      short loc_18000E44A
0x18000e440  mov     rsi, [rsp+1C0h+var_1A0]
0x18000e445  test    rsi, rsi
0x18000e448  jnz     short loc_18000E456
0x18000e44a  lea     rsi, dword_18001F7A4
0x18000e451  mov     [rsp+1C0h+var_1A0], rsi
0x18000e456  mov     edx, edi
0x18000e458  lea     rcx, [rsp+1C0h+var_180]
0x18000e45d  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000e462  test    r14, r14
0x18000e465  jnz     short loc_18000E47A
0x18000e467  mov     r8d, [rbx]
0x18000e46a  lea     rcx, [rsp+1C0h+var_180]
0x18000e46f  mov     r9, rsi
0x18000e472  or      edx, 0FFFFFFFFh
0x18000e475  call    ??$Stop@KKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ulong,ushort const *>(ulong,ulong,ushort const *)
0x18000e47a  cmp     word ptr [r14], 3
0x18000e47f  lea     rcx, [rsp+1C0h+var_180]
0x18000e484  mov     r8d, [rbx]
0x18000e487  mov     r9, rsi
0x18000e48a  jz      short loc_18000E4C7
0x18000e48c  cmp     word ptr [r14], 8
0x18000e491  jz      short loc_18000E4BC
0x18000e493  cmp     word ptr [r14], 0Bh
0x18000e498  jz      short loc_18000E4B0
0x18000e49a  cmp     [r14], r13w
0x18000e49e  jz      short loc_18000E4A5
0x18000e4a0  or      edx, 0FFFFFFFFh
0x18000e4a3  jmp     short loc_18000E4A9
0x18000e4a5  mov     edx, [r14+8]
0x18000e4a9  call    ??$Stop@KKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ulong,ushort const *>(ulong,ulong,ushort const *)
0x18000e4ae  jmp     short loc_18000E4D0
0x18000e4b0  movzx   edx, word ptr [r14+8]
0x18000e4b5  call    ??$Stop@FKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXFKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<short,ulong,ushort const *>(short,ulong,ushort const *)
0x18000e4ba  jmp     short loc_18000E4D0
0x18000e4bc  mov     rdx, [r14+8]
0x18000e4c0  call    ??$Stop@PEAGKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEAGKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ushort *,ulong,ushort const *>(ushort *,ulong,ushort const *)
0x18000e4c5  jmp     short loc_18000E4D0
0x18000e4c7  mov     edx, [r14+8]
0x18000e4cb  call    ??$Stop@JKPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXJKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<long,ulong,ushort const *>(long,ulong,ushort const *)
0x18000e4d0  lea     rcx, [rsp+1C0h+var_180]
0x18000e4d5  call    ??1ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAA@XZ; UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(void)
0x18000e4da  mov     eax, edi
0x18000e4dc  mov     rcx, [rbp+0C0h+var_30]
0x18000e4e3  xor     rcx, rsp; StackCookie
0x18000e4e6  call    __security_check_cookie
0x18000e4eb  lea     r11, [rsp+1C0h+var_20]
0x18000e4f3  mov     rbx, [r11+40h]
0x18000e4f7  mov     rsi, [r11+48h]
0x18000e4fb  mov     rsp, r11
0x18000e4fe  pop     r15
0x18000e500  pop     r14
0x18000e502  pop     r13
0x18000e504  pop     rdi
0x18000e505  pop     rbp
0x18000e506  retn
```
