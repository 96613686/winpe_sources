# AnimationClockLoggingTelemetry::GetCommitHandle::StopActivity(void)

- ea: `0x18009d8d0`
- end: `0x18009dafb`
- name: `?StopActivity@GetCommitHandle@AnimationClockLoggingTelemetry@@MEAAXXZ`
- size: `555`
- prototype: `void __fastcall(AnimationClockLoggingTelemetry::GetCommitHandle *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001b88`
- `0x18005d528`
- `0x18006125c`
- `0x1800615e0`
- `0x18006cadc`
- `0x18009d8d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009da9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009da9c`

## pseudocode

```c
void __fastcall AnimationClockLoggingTelemetry::GetCommitHandle::StopActivity(
        AnimationClockLoggingTelemetry::GetCommitHandle *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // r9d
  __int64 v7; // r8
  _DWORD *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C4h] [rbp-7Ch] BYREF
  int v14; // [rsp+C8h] [rbp-78h] BYREF
  int v15; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v16; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v17; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v18; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v20; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v21; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v22; // [rsp+100h] [rbp-40h] BYREF
  __int64 v23; // [rsp+108h] [rbp-38h] BYREF
  __int64 v24; // [rsp+110h] [rbp-30h] BYREF
  __int64 v25; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v26[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v27; // [rsp+150h] [rbp+10h] BYREF
  int v28; // [rsp+158h] [rbp+18h] BYREF
  __int64 v29; // [rsp+160h] [rbp+20h] BYREF
  int v30; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = *(_DWORD **)(wil::details::static_lazy<AnimationClockLogging>::get() + 8);
    if ( *v5 > 4u )
    {
      v16 = *((_QWORD *)v4 + 6);
      v27 = v4[17];
      v28 = v4[4];
      v17 = *((_QWORD *)v4 + 15);
      v18 = *((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v29) = v4[26];
      v19 = *((_QWORD *)v4 + 12);
      v20 = *((_QWORD *)v4 + 11);
      v30 = v4[20];
      v21 = *((_QWORD *)v4 + 9);
      v12 = v4[8];
      v22 = *((_QWORD *)v4 + 3);
      v13 = *v4;
      v23 = *((_QWORD *)v4 + 16);
      v14 = v4[16];
      v24 = *((_QWORD *)v4 + 7);
      v15 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)byte_1800FF9D5,
        v7 + 8,
        v6,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v12,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v16);
    }
  }
  else
  {
    wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = *(_DWORD **)(wil::details::static_lazy<AnimationClockLogging>::get() + 8);
    if ( *v8 > 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v10 + 72);
      v29 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (unsigned __int8 *)&byte_1800FFB1F,
        v10 + 8,
        v11,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18009d8d0  push    rbp
0x18009d8d2  push    rbx
0x18009d8d3  push    rdi
0x18009d8d4  lea     rbp, [rsp+10h]
0x18009d8d9  sub     rsp, 130h
0x18009d8e0  mov     rdi, [rcx+110h]
0x18009d8e7  mov     rbx, rcx
0x18009d8ea  mov     eax, [rdi+48h]
0x18009d8ed  test    eax, eax
0x18009d8ef  jns     loc_18009DA87
0x18009d8f5  add     rdi, 50h ; 'P'
0x18009d8f9  cmp     eax, [rdi+8]
0x18009d8fc  jnz     loc_18009DA87
0x18009d902  test    rdi, rdi
0x18009d905  jz      loc_18009DA87
0x18009d90b  call    ?zInternalStop@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18009d910  call    ?get@?$static_lazy@VAnimationClockLogging@@@details@wil@@QEAAPEAVAnimationClockLogging@@P6AXXZ@Z; wil::details::static_lazy<AnimationClockLogging>::get(void (*)(void))
0x18009d915  mov     rcx, [rax+8]
0x18009d919  mov     eax, [rcx]
0x18009d91b  cmp     eax, 4
0x18009d91e  jbe     loc_18009DAE9
0x18009d924  mov     rax, [rdi+30h]
0x18009d928  lea     rdx, byte_1800FF9D5
0x18009d92f  mov     [rbp+var_70], rax
0x18009d933  mov     eax, [rdi+44h]
0x18009d936  mov     [rbp+arg_0], eax
0x18009d939  mov     eax, [rdi+10h]
0x18009d93c  mov     [rbp+arg_8], eax
0x18009d93f  mov     rax, [rdi+78h]
0x18009d943  mov     [rbp+var_68], rax
0x18009d947  mov     rax, [rdi+70h]
0x18009d94b  mov     [rbp+var_60], rax
0x18009d94f  mov     eax, [rdi+68h]
0x18009d952  mov     r8, [rbx+110h]
0x18009d959  mov     dword ptr [rbp+arg_10], eax
0x18009d95c  add     r8, 8
0x18009d960  mov     rax, [rdi+60h]
0x18009d964  mov     [rbp+var_58], rax
0x18009d968  mov     rax, [rdi+58h]
0x18009d96c  mov     [rbp+var_50], rax
0x18009d970  mov     eax, [rdi+50h]
0x18009d973  mov     [rbp+arg_18], eax
0x18009d976  mov     rax, [rdi+48h]
0x18009d97a  mov     [rbp+var_48], rax
0x18009d97e  mov     eax, [rdi+20h]
0x18009d981  mov     [rbp+var_80], eax
0x18009d984  mov     rax, [rdi+18h]
0x18009d988  mov     [rbp+var_40], rax
0x18009d98c  mov     eax, [rdi]
0x18009d98e  mov     [rbp+var_7C], eax
0x18009d991  mov     rax, [rdi+80h]
0x18009d998  mov     [rbp+var_38], rax
0x18009d99c  mov     eax, [rdi+40h]
0x18009d99f  mov     [rbp+var_78], eax
0x18009d9a2  mov     rax, [rdi+38h]
0x18009d9a6  mov     [rbp+var_30], rax
0x18009d9aa  mov     eax, [rdi+8]
0x18009d9ad  mov     [rbp+var_74], eax
0x18009d9b0  lea     rax, [rbp+var_70]
0x18009d9b4  mov     [rsp+140h+var_90], rax
0x18009d9bc  lea     rax, [rbp+arg_0]
0x18009d9c0  mov     [rsp+140h+var_98], rax
0x18009d9c8  lea     rax, [rbp+arg_8]
0x18009d9cc  mov     [rsp+140h+var_A0], rax
0x18009d9d4  lea     rax, [rbp+var_68]
0x18009d9d8  mov     [rsp+140h+var_A8], rax
0x18009d9e0  lea     rax, [rbp+var_60]
0x18009d9e4  mov     [rsp+140h+var_B0], rax
0x18009d9ec  lea     rax, [rbp+arg_10]
0x18009d9f0  mov     [rsp+140h+var_B8], rax
0x18009d9f8  lea     rax, [rbp+var_58]
0x18009d9fc  mov     [rsp+140h+var_C0], rax
0x18009da04  lea     rax, [rbp+var_50]
0x18009da08  mov     [rsp+140h+var_C8], rax
0x18009da0d  lea     rax, [rbp+arg_18]
0x18009da11  mov     [rsp+140h+var_D0], rax
0x18009da16  lea     rax, [rbp+var_48]
0x18009da1a  mov     [rsp+140h+var_D8], rax
0x18009da1f  lea     rax, [rbp+var_80]
0x18009da23  mov     [rsp+140h+var_E0], rax
0x18009da28  lea     rax, [rbp+var_40]
0x18009da2c  mov     [rsp+140h+var_E8], rax
0x18009da31  lea     rax, [rbp+var_7C]
0x18009da35  mov     [rsp+140h+var_F0], rax
0x18009da3a  lea     rax, [rbp+var_38]
0x18009da3e  mov     [rsp+140h+var_F8], rax
0x18009da43  lea     rax, [rbp+var_78]
0x18009da47  mov     [rsp+140h+var_100], rax
0x18009da4c  lea     rax, [rbp+var_30]
0x18009da50  mov     [rsp+140h+var_108], rax
0x18009da55  lea     rax, [rbp+var_74]
0x18009da59  mov     [rsp+140h+var_110], rax
0x18009da5e  lea     rax, [rbp+var_28]
0x18009da62  mov     [rsp+140h+var_118], rax
0x18009da67  lea     rax, [rbp+var_20]
0x18009da6b  mov     [rsp+140h+var_120], rax
0x18009da70  mov     [rbp+var_28], 1000000h
0x18009da78  mov     [rbp+var_20], 0
0x18009da80  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18009da85  jmp     short loc_18009DAE9
0x18009da87  call    ?zInternalStop@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18009da8c  call    ?get@?$static_lazy@VAnimationClockLogging@@@details@wil@@QEAAPEAVAnimationClockLogging@@P6AXXZ@Z; wil::details::static_lazy<AnimationClockLogging>::get(void (*)(void))
0x18009da91  mov     rdi, [rax+8]
0x18009da95  mov     eax, [rdi]
0x18009da97  cmp     eax, 4
0x18009da9a  jbe     short loc_18009DAE9
0x18009da9c  call    cs:__imp_GetCurrentThreadId
0x18009daa2  mov     r8, [rbx+110h]
0x18009daa9  lea     rdx, byte_1800FFB1F
0x18009dab0  mov     [rbp+arg_0], eax
0x18009dab3  mov     rcx, rdi
0x18009dab6  mov     eax, [r8+48h]
0x18009daba  add     r8, 8
0x18009dabe  mov     [rbp+arg_8], eax
0x18009dac1  lea     rax, [rbp+arg_0]
0x18009dac5  mov     [rsp+140h+var_110], rax
0x18009daca  lea     rax, [rbp+arg_8]
0x18009dace  mov     [rsp+140h+var_118], rax
0x18009dad3  lea     rax, [rbp+arg_10]
0x18009dad7  mov     [rsp+140h+var_120], rax
0x18009dadc  mov     [rbp+arg_10], 0
0x18009dae4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009dae9  mov     rcx, rbx
0x18009daec  add     rsp, 130h
0x18009daf3  pop     rdi
0x18009daf4  pop     rbx
0x18009daf5  pop     rbp
0x18009daf6  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWindowFrameLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
