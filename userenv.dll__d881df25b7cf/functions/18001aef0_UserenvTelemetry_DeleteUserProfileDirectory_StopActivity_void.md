# UserenvTelemetry::DeleteUserProfileDirectory::StopActivity(void)

- ea: `0x18001aef0`
- end: `0x18001b175`
- name: `?StopActivity@DeleteUserProfileDirectory@UserenvTelemetry@@MEAAXXZ`
- size: `645`
- prototype: `void __fastcall(UserenvTelemetry::DeleteUserProfileDirectory *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001d68`
- `0x180001ee8`
- `0x18000219c`
- `0x18000d8ec`
- `0x18000e640`
- `0x180013d08`
- `0x180014c30`
- `0x18001aef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b0ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b0ce`

## pseudocode

```c
void __fastcall UserenvTelemetry::DeleteUserProfileDirectory::StopActivity(
        UserenvTelemetry::DeleteUserProfileDirectory *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-80h] BYREF
  DWORD v16; // [rsp+A4h] [rbp-7Ch] BYREF
  int v17; // [rsp+A8h] [rbp-78h] BYREF
  int v18; // [rsp+ACh] [rbp-74h] BYREF
  int v19; // [rsp+B0h] [rbp-70h] BYREF
  int v20; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v21; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v30; // [rsp+100h] [rbp-20h] BYREF
  char v31[32]; // [rsp+110h] [rbp-10h] BYREF
  __int64 *v32; // [rsp+130h] [rbp+10h]
  __int64 v33; // [rsp+138h] [rbp+18h]
  int *v34; // [rsp+140h] [rbp+20h]
  __int64 v35; // [rsp+148h] [rbp+28h]
  DWORD *v36; // [rsp+150h] [rbp+30h]
  __int64 v37; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = ProfileAPILogging::Provider();
    v8 = v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v23 = *((_QWORD *)v4 + 14);
      v17 = v4[26];
      v24 = *((_QWORD *)v4 + 12);
      v25 = *((_QWORD *)v4 + 11);
      v18 = v4[20];
      v26 = *((_QWORD *)v4 + 9);
      v19 = v4[8];
      v27 = *((_QWORD *)v4 + 3);
      v20 = *v4;
      v28 = *((_QWORD *)v4 + 16);
      v15 = v4[16];
      v29 = *((_QWORD *)v4 + 7);
      v16 = v4[2];
      v30 = 0x1000000;
      v21 = 0x1000000;
      v22 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)byte_180022505,
        v10 + 8,
        (_DWORD)v8,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v16,
        (__int64)&v29,
        (__int64)&v15,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v26,
        (__int64)&v18,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v17,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  else
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = ProfileAPILogging::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v16 = CurrentThreadId;
      v37 = 4;
      v35 = 4;
      v15 = *(_DWORD *)(v14 + 72);
      v21 = 0x1000000;
      v36 = &v16;
      v34 = &v15;
      v32 = &v21;
      v33 = 8;
      tlgWriteTransfer_EventWriteTransfer(v12, word_1800224AA, v14 + 8, 0, 5, v31);
    }
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18001aef0  mov     [rsp-8+arg_8], rbx
0x18001aef5  mov     [rsp-8+arg_10], rdi
0x18001aefa  push    rbp
0x18001aefb  lea     rbp, [rsp-50h]
0x18001af00  sub     rsp, 170h
0x18001af07  mov     rax, cs:__security_cookie
0x18001af0e  xor     rax, rsp
0x18001af11  mov     [rbp+50h+var_10], rax
0x18001af15  mov     rdi, [rcx+110h]
0x18001af1c  mov     rbx, rcx
0x18001af1f  mov     eax, [rdi+48h]
0x18001af22  test    eax, eax
0x18001af24  jns     loc_18001B0A0
0x18001af2a  add     rdi, 50h ; 'P'
0x18001af2e  cmp     eax, [rdi+8]
0x18001af31  jnz     loc_18001B0A0
0x18001af37  test    rdi, rdi
0x18001af3a  jz      loc_18001B0A0
0x18001af40  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001af45  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x18001af4a  mov     r9, rax
0x18001af4d  mov     ecx, [rax]
0x18001af4f  cmp     ecx, 5
0x18001af52  jbe     loc_18001B14B
0x18001af58  mov     rdx, 400000000000h
0x18001af62  mov     rcx, rax
0x18001af65  call    _tlgKeywordOn
0x18001af6a  test    al, al
0x18001af6c  jz      loc_18001B14B
0x18001af72  mov     rax, [rdi+70h]
0x18001af76  lea     rdx, byte_180022505
0x18001af7d  mov     rcx, [rdi+78h]
0x18001af81  mov     r8, [rbx+110h]
0x18001af88  mov     [rbp+50h+var_A8], rax
0x18001af8c  add     r8, 8
0x18001af90  mov     eax, [rdi+68h]
0x18001af93  mov     [rbp+50h+var_C8], eax
0x18001af96  mov     rax, [rdi+60h]
0x18001af9a  mov     [rbp+50h+var_A0], rax
0x18001af9e  mov     rax, [rdi+58h]
0x18001afa2  mov     [rbp+50h+var_98], rax
0x18001afa6  mov     eax, [rdi+50h]
0x18001afa9  mov     [rbp+50h+var_C4], eax
0x18001afac  mov     rax, [rdi+48h]
0x18001afb0  mov     [rbp+50h+var_90], rax
0x18001afb4  mov     eax, [rdi+20h]
0x18001afb7  mov     [rbp+50h+var_C0], eax
0x18001afba  mov     rax, [rdi+18h]
0x18001afbe  mov     [rbp+50h+var_88], rax
0x18001afc2  mov     eax, [rdi]
0x18001afc4  mov     [rbp+50h+var_BC], eax
0x18001afc7  mov     rax, [rdi+80h]
0x18001afce  mov     [rbp+50h+var_80], rax
0x18001afd2  mov     eax, [rdi+40h]
0x18001afd5  mov     [rbp+50h+var_D0], eax
0x18001afd8  mov     rax, [rdi+38h]
0x18001afdc  mov     [rbp+50h+var_78], rax
0x18001afe0  mov     eax, [rdi+8]
0x18001afe3  mov     [rbp+50h+var_CC], eax
0x18001afe6  mov     eax, 1000000h
0x18001afeb  mov     [rbp+50h+var_70], rax
0x18001afef  mov     [rbp+50h+var_B8], rax
0x18001aff3  lea     rax, [rbp+50h+var_B0]
0x18001aff7  mov     [rsp+170h+var_D8], rax
0x18001afff  lea     rax, [rbp+50h+var_A8]
0x18001b003  mov     [rsp+170h+var_E0], rax
0x18001b00b  lea     rax, [rbp+50h+var_C8]
0x18001b00f  mov     [rsp+170h+var_E8], rax
0x18001b017  lea     rax, [rbp+50h+var_A0]
0x18001b01b  mov     [rsp+170h+var_F0], rax
0x18001b023  lea     rax, [rbp+50h+var_98]
0x18001b027  mov     [rsp+170h+var_F8], rax
0x18001b02c  lea     rax, [rbp+50h+var_C4]
0x18001b030  mov     [rsp+170h+var_100], rax
0x18001b035  lea     rax, [rbp+50h+var_90]
0x18001b039  mov     [rsp+170h+var_108], rax
0x18001b03e  lea     rax, [rbp+50h+var_C0]
0x18001b042  mov     [rsp+170h+var_110], rax
0x18001b047  lea     rax, [rbp+50h+var_88]
0x18001b04b  mov     [rsp+170h+var_118], rax
0x18001b050  lea     rax, [rbp+50h+var_BC]
0x18001b054  mov     [rsp+170h+var_120], rax
0x18001b059  lea     rax, [rbp+50h+var_80]
0x18001b05d  mov     [rsp+170h+var_128], rax
0x18001b062  lea     rax, [rbp+50h+var_D0]
0x18001b066  mov     [rsp+170h+var_130], rax
0x18001b06b  lea     rax, [rbp+50h+var_78]
0x18001b06f  mov     [rsp+170h+var_138], rax
0x18001b074  lea     rax, [rbp+50h+var_CC]
0x18001b078  mov     [rsp+170h+var_140], rax
0x18001b07d  lea     rax, [rbp+50h+var_70]
0x18001b081  mov     [rsp+170h+var_148], rax
0x18001b086  lea     rax, [rbp+50h+var_B8]
0x18001b08a  mov     [rbp+50h+var_B0], rcx
0x18001b08e  mov     rcx, r9
0x18001b091  mov     [rsp+170h+var_150], rax
0x18001b096  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001b09b  jmp     loc_18001B14B
0x18001b0a0  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001b0a5  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x18001b0aa  mov     rdi, rax
0x18001b0ad  mov     ecx, [rax]
0x18001b0af  cmp     ecx, 5
0x18001b0b2  jbe     loc_18001B14B
0x18001b0b8  mov     rdx, 400000000000h
0x18001b0c2  mov     rcx, rax
0x18001b0c5  call    _tlgKeywordOn
0x18001b0ca  test    al, al
0x18001b0cc  jz      short loc_18001B14B
0x18001b0ce  call    cs:__imp_GetCurrentThreadId
0x18001b0d5  nop     dword ptr [rax+rax+00h]
0x18001b0da  mov     r8, [rbx+110h]
0x18001b0e1  lea     rdx, word_1800224AA
0x18001b0e8  mov     [rbp+50h+var_CC], eax
0x18001b0eb  xor     r9d, r9d
0x18001b0ee  mov     rcx, rdi
0x18001b0f1  mov     [rbp+50h+var_18], 4
0x18001b0f9  mov     [rbp+50h+var_28], 4
0x18001b101  mov     eax, [r8+48h]
0x18001b105  add     r8, 8
0x18001b109  mov     [rbp+50h+var_D0], eax
0x18001b10c  mov     eax, 1000000h
0x18001b111  mov     [rbp+50h+var_B8], rax
0x18001b115  lea     rax, [rbp+50h+var_CC]
0x18001b119  mov     [rbp+50h+var_20], rax
0x18001b11d  lea     rax, [rbp+50h+var_D0]
0x18001b121  mov     [rbp+50h+var_30], rax
0x18001b125  lea     rax, [rbp+50h+var_B8]
0x18001b129  mov     [rbp+50h+var_40], rax
0x18001b12d  lea     rax, [rbp+50h+var_60]
0x18001b131  mov     [rsp+170h+var_148], rax
0x18001b136  mov     dword ptr [rsp+170h+var_150], 5
0x18001b13e  mov     [rbp+50h+var_38], 8
0x18001b146  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b14b  mov     rcx, rbx
0x18001b14e  call    ?IgnoreCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001b153  mov     rcx, [rbp+50h+var_10]
0x18001b157  xor     rcx, rsp; StackCookie
0x18001b15a  call    __security_check_cookie
0x18001b15f  lea     r11, [rsp+170h+var_s0]
0x18001b167  mov     rbx, [r11+18h]
0x18001b16b  mov     rdi, [r11+20h]
0x18001b16f  mov     rsp, r11
0x18001b172  pop     rbp
0x18001b173  retn
```
