# Tpm20Scheduler::SchedulerThreadFunction(void)

- ea: `0x1400179c4`
- end: `0x140017e91`
- name: `?SchedulerThreadFunction@Tpm20Scheduler@@AEAAXXZ`
- size: `1229`
- prototype: `void __fastcall(Tpm20Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001c080`

## callees

- `0x1400010a4`
- `0x140001214`
- `0x14000660c`
- `0x1400078b8`
- `0x140007b5c`
- `0x140008bfc`
- `0x14000a4f0`
- `0x14000f490`
- `0x14000f4b4`
- `0x140013210`
- `0x140016ac4`
- `0x1400171d0`
- `0x1400179c4`
- `0x14001a770`
- `0x14001b1ac`
- `0x14001c0e8`
- `0x14001c290`
- `0x140039740`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140017a42`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017a42`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140017d06`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140017d58`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140017d06`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140017d58`
- `ntoskrnl!KeResetEvent` at `0x140017a51`
- `ntoskrnl!KeResetEvent` at `0x140017a51`

## pseudocode

```c
void __fastcall Tpm20Scheduler::SchedulerThreadFunction(Tpm20Scheduler *this)
{
  unsigned int v1; // r14d
  unsigned int v2; // r15d
  int v3; // r13d
  int v5; // r12d
  int v6; // esi
  unsigned int v7; // eax
  __int64 v8; // rdx
  union _LARGE_INTEGER *v9; // rcx
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rcx
  Tpm20Scheduler *v13; // rcx
  int v14; // eax
  int v15; // r8d
  char v16; // di
  int v17; // ecx
  __int64 v18; // rdx
  int ResetRestartCount; // edi
  __int64 v20; // r8
  int v21; // r9d
  unsigned int v22; // esi
  unsigned int v23; // edi
  int v24; // ecx
  int v25; // ecx
  Tpm20Scheduler *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  bool v29; // zf
  int v30; // eax
  int v31; // eax
  int v32; // r8d
  char v33; // di
  int v34; // ecx
  Tpm20Scheduler *v35; // rcx
  int Timeout; // [rsp+20h] [rbp-99h]
  unsigned int v37; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-65h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v40; // [rsp+5Ch] [rbp-5Dh] BYREF
  __int64 v41; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v42[11]; // [rsp+68h] [rbp-51h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v5 = 0;
  v6 = -1073741823;
LABEL_2:
  v7 = *((_DWORD *)this + 44);
  if ( v7 <= 1 )
  {
    v8 = 1;
  }
  else
  {
    v8 = -5000000;
    *((_DWORD *)this + 44) = v7 - 1;
  }
  v42[0] = v8;
  v9 = (union _LARGE_INTEGER *)v42;
  if ( v8 == 1 )
    v9 = 0;
  KeWaitForSingleObject(this, Executive, 0, 0, v9);
  KeResetEvent((PRKEVENT)this);
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v10 = *((_DWORD *)this + 47);
            if ( !(unsigned int)Tpm20Scheduler::FetchEvent(this, v10, 4) )
              break;
            v5 = 1;
          }
          if ( !(unsigned int)Tpm20Scheduler::FetchEvent(v12, v11, 8) )
            break;
          v38 = 0;
          v37 = 0;
          v14 = Tpm20Scheduler::DoS4S5Start(v13);
          v16 = v14;
          if ( v14 < 0 )
          {
            v17 = (int)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids);
            }
            if ( (TPMEnableBits & 1) != 0 )
              McTemplateK0dqq_EtwWriteTransfer(v17, (unsigned int)TPM_HW_PROTOCOL_ERROR, v15, 28, 52, v16);
          }
          ResetRestartCount = Tpm20GetResetRestartCount(*((struct TpmTransport **)this + 18), &v38, &v37);
          if ( ResetRestartCount < 0 || v6 < 0 )
          {
            if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)tlgKeywordOn() )
            {
              v40 = v6;
              v42[9] = &v40;
              v39 = ResetRestartCount;
              v42[7] = &v39;
              v41 = 0x1000000;
              v42[5] = &v41;
              v42[10] = 4;
              Timeout = 5;
              v42[8] = 4;
              v42[6] = 8;
              tlgWriteTransfer_EtwWriteTransfer(&dword_1400470A0, &dword_140041B14, 0, 0);
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              Timeout = v6;
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                18,
                WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids,
                (unsigned int)ResetRestartCount);
            }
          }
          else
          {
            v22 = v38;
            v23 = v37;
            if ( v38 != v1 || v37 != v2 + 1 )
            {
              if ( (unsigned int)dword_1400470A0 > 5 && (unsigned __int8)tlgKeywordOn() )
              {
                v38 = v23;
                v37 = v22;
                v39 = v2;
                v40 = v1;
                v41 = 0x1000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v24,
                  (unsigned int)&dword_140041B64,
                  v20,
                  v21,
                  (__int64)&v41,
                  (__int64)&v40,
                  (__int64)&v39,
                  (__int64)&v37,
                  (__int64)&v38);
              }
              v25 = (int)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                Timeout = v2;
                WPP_SF_dddd(WPP_GLOBAL_Control->AttachedDevice, v18, v20, v1);
              }
              if ( (v22 != v1 || v23 <= v2) && (TPMEnableBits & 4) != 0 )
                McTemplateK0dqqqqq_EtwWriteTransfer(v25, v18, v20, v21, Timeout, v1, v2, v22, v23);
            }
          }
          v6 = -1073741823;
        }
        if ( *((_DWORD *)this + 44) )
        {
          if ( (int)TpmArchiveLog() >= 0 )
          {
            ZwUpdateWnfStateData(&WNF_TPM_PREATT_HC_TRIGGER, 0, 0, 0, 0, 0, 0);
            *((_DWORD *)this + 44) = 0;
          }
          if ( *((_DWORD *)this + 44) == 1 && !v3 )
          {
            v3 = 1;
            ZwUpdateWnfStateData(&WNF_TPM_PREATT_HC_TRIGGER, 0, 0, 0, 0, 0, 0);
          }
        }
        if ( !v5 || !(unsigned int)Tpm20Scheduler::FetchEvent(this, v10, 16) )
          break;
        Tpm20Scheduler::DoContextCleanup(v26);
      }
      if ( !(unsigned int)Tpm20Scheduler::FetchEvent(this, v10, 2) )
        break;
      v1 = 0;
      v2 = 0;
      v29 = *((_DWORD *)this + 12) == 3;
      v38 = 0;
      v37 = 0;
      if ( v29 )
      {
        v30 = Tpm20GetResetRestartCount(*((struct TpmTransport **)this + 18), &v38, &v37);
        v1 = v38;
        v6 = v30;
        v2 = v37;
      }
      v31 = Tpm20Scheduler::DoSaveTpmStateAndSignalSuspended(this);
      v33 = v31;
      if ( v31 < 0 )
      {
        v34 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids);
        if ( (TPMEnableBits & 1) != 0 )
          McTemplateK0dqq_EtwWriteTransfer(v34, (unsigned int)TPM_SAVE_STATE_FAILED_EX, v32, 28, 180, v33);
      }
      v5 = 0;
    }
    if ( (unsigned int)Tpm20Scheduler::FetchEvent(v28, v27, 1) )
      break;
    if ( !v5 || !(unsigned int)Tpm20Scheduler::FetchNextUserRequest(v35) )
      goto LABEL_2;
    Tpm20Scheduler::DoUserRequest(this);
  }
}

```

## disassembly

```asm
0x1400179c4  push    rbp
0x1400179c6  push    rbx
0x1400179c7  push    rsi
0x1400179c8  push    rdi
0x1400179c9  push    r12
0x1400179cb  push    r13
0x1400179cd  push    r14
0x1400179cf  push    r15
0x1400179d1  lea     rbp, [rsp-1Fh]
0x1400179d6  sub     rsp, 0D8h
0x1400179dd  mov     rax, cs:__security_cookie
0x1400179e4  xor     rax, rsp
0x1400179e7  mov     [rbp+57h+var_50], rax
0x1400179eb  xor     r14d, r14d
0x1400179ee  xor     r15d, r15d
0x1400179f1  xor     r13d, r13d
0x1400179f4  mov     rbx, rcx
0x1400179f7  xor     r12d, r12d
0x1400179fa  mov     esi, 0C0000001h
0x1400179ff  mov     eax, [rbx+0B0h]
0x140017a05  cmp     eax, 1
0x140017a08  jbe     short loc_140017A1B
0x140017a0a  dec     eax
0x140017a0c  mov     rdx, 0FFFFFFFFFFB3B4C0h
0x140017a13  mov     [rbx+0B0h], eax
0x140017a19  jmp     short loc_140017A20
0x140017a1b  mov     edx, 1
0x140017a20  xor     eax, eax
0x140017a22  mov     [rbp+57h+var_A8], rdx
0x140017a26  cmp     rdx, 1
0x140017a2a  lea     rcx, [rbp+57h+var_A8]
0x140017a2e  cmovz   rcx, rax
0x140017a32  xor     r9d, r9d; Alertable
0x140017a35  mov     [rsp+110h+Timeout], rcx; Timeout
0x140017a3a  xor     r8d, r8d; WaitMode
0x140017a3d  mov     rcx, rbx; Object
0x140017a40  xor     edx, edx; WaitReason
0x140017a42  call    cs:__imp_KeWaitForSingleObject
0x140017a49  nop     dword ptr [rax+rax+00h]
0x140017a4e  mov     rcx, rbx; Event
0x140017a51  call    cs:__imp_KeResetEvent
0x140017a58  nop     dword ptr [rax+rax+00h]
0x140017a5d  mov     edi, [rbx+0BCh]
0x140017a63  mov     r8d, 4
0x140017a69  mov     edx, edi
0x140017a6b  mov     rcx, rbx
0x140017a6e  call    ?FetchEvent@Tpm20Scheduler@@AEAAHJW4_SCHED20_EVENT@1@@Z; Tpm20Scheduler::FetchEvent(long,Tpm20Scheduler::_SCHED20_EVENT)
0x140017a73  test    eax, eax
0x140017a75  jz      short loc_140017A7F
0x140017a77  mov     r12d, 1
0x140017a7d  jmp     short loc_140017A5D
0x140017a7f  mov     r8d, 8
0x140017a85  call    ?FetchEvent@Tpm20Scheduler@@AEAAHJW4_SCHED20_EVENT@1@@Z; Tpm20Scheduler::FetchEvent(long,Tpm20Scheduler::_SCHED20_EVENT)
0x140017a8a  test    eax, eax
0x140017a8c  jz      loc_140017CC8
0x140017a92  mov     [rbp+57h+var_BC], 0
0x140017a99  mov     [rbp+57h+var_C0], 0
0x140017aa0  call    ?DoS4S5Start@Tpm20Scheduler@@AEAAJXZ; Tpm20Scheduler::DoS4S5Start(void)
0x140017aa5  mov     edi, eax
0x140017aa7  test    eax, eax
0x140017aa9  jns     short loc_140017B02
0x140017aab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017ab2  lea     rax, WPP_GLOBAL_Control
0x140017ab9  cmp     rcx, rax
0x140017abc  jz      short loc_140017ADB
0x140017abe  mov     edx, [rcx+2Ch]
0x140017ac1  test    dl, 1
0x140017ac4  jz      short loc_140017ADB
0x140017ac6  mov     rcx, [rcx+18h]
0x140017aca  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x140017ad1  mov     edx, 10h
0x140017ad6  call    WPP_SF_
0x140017adb  test    cs:TPMEnableBits, 1
0x140017ae2  jz      short loc_140017B02
0x140017ae4  mov     dword ptr [rsp+110h+var_E8], edi
0x140017ae8  lea     rdx, TPM_HW_PROTOCOL_ERROR
0x140017aef  mov     r9d, 1Ch
0x140017af5  mov     dword ptr [rsp+110h+Timeout], 534h
0x140017afd  call    McTemplateK0dqq_EtwWriteTransfer
0x140017b02  mov     rcx, [rbx+90h]; struct TpmTransport *
0x140017b09  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x140017b0d  lea     rdx, [rbp+57h+var_BC]; unsigned int *
0x140017b11  call    ?Tpm20GetResetRestartCount@@YAJPEAVTpmTransport@@PEAI1@Z; Tpm20GetResetRestartCount(TpmTransport *,uint *,uint *)
0x140017b16  mov     edi, eax
0x140017b18  test    eax, eax
0x140017b1a  js      loc_140017C0C
0x140017b20  test    esi, esi
0x140017b22  js      loc_140017C0C
0x140017b28  mov     esi, [rbp+57h+var_BC]
0x140017b2b  mov     edi, [rbp+57h+var_C0]
0x140017b2e  cmp     esi, r14d
0x140017b31  jnz     short loc_140017B3F
0x140017b33  lea     eax, [r15+1]
0x140017b37  cmp     edi, eax
0x140017b39  jz      loc_140017CBE
0x140017b3f  mov     eax, cs:dword_1400470A0
0x140017b45  cmp     eax, 5
0x140017b48  jbe     short loc_140017BA2
0x140017b4a  call    _tlgKeywordOn
0x140017b4f  test    al, al
0x140017b51  jz      short loc_140017BA2
0x140017b53  lea     rax, [rbp+57h+var_BC]
0x140017b57  mov     [rbp+57h+var_BC], edi
0x140017b5a  mov     [rsp+110h+var_D0], rax
0x140017b5f  lea     rdx, dword_140041B64
0x140017b66  lea     rax, [rbp+57h+var_C0]
0x140017b6a  mov     [rbp+57h+var_C0], esi
0x140017b6d  mov     [rsp+110h+var_D8], rax
0x140017b72  lea     rax, [rbp+57h+var_B8]
0x140017b76  mov     [rsp+110h+var_E0], rax
0x140017b7b  lea     rax, [rbp+57h+var_B4]
0x140017b7f  mov     [rsp+110h+var_E8], rax
0x140017b84  lea     rax, [rbp+57h+var_B0]
0x140017b88  mov     [rsp+110h+Timeout], rax
0x140017b8d  mov     [rbp+57h+var_B8], r15d
0x140017b91  mov     [rbp+57h+var_B4], r14d
0x140017b95  mov     [rbp+57h+var_B0], 1000000h
0x140017b9d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140017ba2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017ba9  lea     rax, WPP_GLOBAL_Control
0x140017bb0  cmp     rcx, rax
0x140017bb3  jz      short loc_140017BD5
0x140017bb5  mov     eax, [rcx+2Ch]
0x140017bb8  test    al, 2
0x140017bba  jz      short loc_140017BD5
0x140017bbc  mov     rcx, [rcx+18h]
0x140017bc0  mov     r9d, r14d
0x140017bc3  mov     dword ptr [rsp+110h+var_E0], edi
0x140017bc7  mov     dword ptr [rsp+110h+var_E8], esi
0x140017bcb  mov     dword ptr [rsp+110h+Timeout], r15d
0x140017bd0  call    WPP_SF_dddd
0x140017bd5  cmp     esi, r14d
0x140017bd8  jnz     short loc_140017BE3
0x140017bda  cmp     edi, r15d
0x140017bdd  ja      loc_140017CBE
0x140017be3  test    cs:TPMEnableBits, 4
0x140017bea  jz      loc_140017CBE
0x140017bf0  mov     dword ptr [rsp+110h+var_D0], edi
0x140017bf4  mov     dword ptr [rsp+110h+var_D8], esi
0x140017bf8  mov     dword ptr [rsp+110h+var_E0], r15d
0x140017bfd  mov     dword ptr [rsp+110h+var_E8], r14d
0x140017c02  call    McTemplateK0dqqqqq_EtwWriteTransfer
0x140017c07  jmp     loc_140017CBE
0x140017c0c  mov     eax, cs:dword_1400470A0
0x140017c12  cmp     eax, 5
0x140017c15  jbe     short loc_140017C88
0x140017c17  call    _tlgKeywordOn
0x140017c1c  test    al, al
0x140017c1e  jz      short loc_140017C88
0x140017c20  lea     rax, [rbp+57h+var_B4]
0x140017c24  mov     [rbp+57h+var_B4], esi
0x140017c27  mov     [rbp+57h+var_60], rax
0x140017c2b  lea     rdx, dword_140041B14
0x140017c32  lea     rax, [rbp+57h+var_B8]
0x140017c36  mov     [rbp+57h+var_B8], edi
0x140017c39  mov     [rbp+57h+var_70], rax
0x140017c3d  lea     rcx, dword_1400470A0
0x140017c44  lea     rax, [rbp+57h+var_B0]
0x140017c48  mov     [rbp+57h+var_B0], 1000000h
0x140017c50  mov     [rbp+57h+var_80], rax
0x140017c54  xor     r9d, r9d
0x140017c57  lea     rax, [rbp+57h+var_A0]
0x140017c5b  mov     [rbp+57h+var_58], 4
0x140017c63  mov     [rsp+110h+var_E8], rax
0x140017c68  xor     r8d, r8d
0x140017c6b  mov     dword ptr [rsp+110h+Timeout], 5
0x140017c73  mov     [rbp+57h+var_68], 4
0x140017c7b  mov     [rbp+57h+var_78], 8
0x140017c83  call    _tlgWriteTransfer_EtwWriteTransfer
0x140017c88  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017c8f  lea     rax, WPP_GLOBAL_Control
0x140017c96  cmp     rcx, rax
0x140017c99  jz      short loc_140017CBE
0x140017c9b  mov     eax, [rcx+2Ch]
0x140017c9e  test    al, 2
0x140017ca0  jz      short loc_140017CBE
0x140017ca2  mov     rcx, [rcx+18h]
0x140017ca6  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x140017cad  mov     edx, 12h
0x140017cb2  mov     dword ptr [rsp+110h+Timeout], esi
0x140017cb6  mov     r9d, edi
0x140017cb9  call    WPP_SF_Dd
0x140017cbe  mov     esi, 0C0000001h
0x140017cc3  jmp     loc_140017A5D
0x140017cc8  cmp     dword ptr [rbx+0B0h], 0
0x140017ccf  jz      loc_140017D64
0x140017cd5  call    TpmArchiveLog
0x140017cda  test    eax, eax
0x140017cdc  js      short loc_140017D1C
0x140017cde  mov     dword ptr [rsp+110h+var_E0], 0
0x140017ce6  lea     rcx, WNF_TPM_PREATT_HC_TRIGGER
0x140017ced  mov     dword ptr [rsp+110h+var_E8], 0
0x140017cf5  xor     r9d, r9d
0x140017cf8  xor     r8d, r8d
0x140017cfb  mov     [rsp+110h+Timeout], 0
0x140017d04  xor     edx, edx
0x140017d06  call    cs:__imp_ZwUpdateWnfStateData
0x140017d0d  nop     dword ptr [rax+rax+00h]
0x140017d12  mov     dword ptr [rbx+0B0h], 0
0x140017d1c  cmp     dword ptr [rbx+0B0h], 1
0x140017d23  jnz     short loc_140017D64
0x140017d25  test    r13d, r13d
0x140017d28  jnz     short loc_140017D64
0x140017d2a  mov     dword ptr [rsp+110h+var_E0], 0
0x140017d32  lea     rcx, WNF_TPM_PREATT_HC_TRIGGER
0x140017d39  mov     dword ptr [rsp+110h+var_E8], 0
0x140017d41  xor     r9d, r9d
0x140017d44  xor     r8d, r8d
0x140017d47  mov     [rsp+110h+Timeout], 0
0x140017d50  xor     edx, edx
0x140017d52  mov     r13d, 1
0x140017d58  call    cs:__imp_ZwUpdateWnfStateData
0x140017d5f  nop     dword ptr [rax+rax+00h]
0x140017d64  test    r12d, r12d
0x140017d67  jz      short loc_140017D87
0x140017d69  mov     r8d, 10h
0x140017d6f  mov     edx, edi
0x140017d71  mov     rcx, rbx
0x140017d74  call    ?FetchEvent@Tpm20Scheduler@@AEAAHJW4_SCHED20_EVENT@1@@Z; Tpm20Scheduler::FetchEvent(long,Tpm20Scheduler::_SCHED20_EVENT)
0x140017d79  test    eax, eax
0x140017d7b  jz      short loc_140017D87
0x140017d7d  call    ?DoContextCleanup@Tpm20Scheduler@@AEAAXXZ; Tpm20Scheduler::DoContextCleanup(void)
0x140017d82  jmp     loc_140017A5D
0x140017d87  mov     r8d, 2
0x140017d8d  mov     edx, edi
0x140017d8f  mov     rcx, rbx
0x140017d92  call    ?FetchEvent@Tpm20Scheduler@@AEAAHJW4_SCHED20_EVENT@1@@Z; Tpm20Scheduler::FetchEvent(long,Tpm20Scheduler::_SCHED20_EVENT)
0x140017d97  test    eax, eax
0x140017d99  jz      loc_140017E3E
0x140017d9f  xor     r14d, r14d
0x140017da2  xor     r15d, r15d
0x140017da5  cmp     dword ptr [rbx+30h], 3
0x140017da9  mov     [rbp+57h+var_BC], r14d
0x140017dad  mov     [rbp+57h+var_C0], r15d
0x140017db1  jnz     short loc_140017DD1
0x140017db3  mov     rcx, [rbx+90h]; struct TpmTransport *
0x140017dba  lea     r8, [rbp+57h+var_C0]; unsigned int *
0x140017dbe  lea     rdx, [rbp+57h+var_BC]; unsigned int *
0x140017dc2  call    ?Tpm20GetResetRestartCount@@YAJPEAVTpmTransport@@PEAI1@Z; Tpm20GetResetRestartCount(TpmTransport *,uint *,uint *)
0x140017dc7  mov     r14d, [rbp+57h+var_BC]
0x140017dcb  mov     esi, eax
0x140017dcd  mov     r15d, [rbp+57h+var_C0]
0x140017dd1  mov     rcx, rbx; this
0x140017dd4  call    ?DoSaveTpmStateAndSignalSuspended@Tpm20Scheduler@@AEAAJXZ; Tpm20Scheduler::DoSaveTpmStateAndSignalSuspended(void)
0x140017dd9  mov     edi, eax
0x140017ddb  test    eax, eax
0x140017ddd  jns     short loc_140017E36
0x140017ddf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017de6  lea     rax, WPP_GLOBAL_Control
0x140017ded  cmp     rcx, rax
0x140017df0  jz      short loc_140017E0F
0x140017df2  mov     edx, [rcx+2Ch]
0x140017df5  test    dl, 1
0x140017df8  jz      short loc_140017E0F
0x140017dfa  mov     rcx, [rcx+18h]
0x140017dfe  lea     r8, WPP_2f941e6db7ef36bb85742d5aa01850b9_Traceguids
0x140017e05  mov     edx, 13h
0x140017e0a  call    WPP_SF_
0x140017e0f  test    cs:TPMEnableBits, 1
0x140017e16  jz      short loc_140017E36
0x140017e18  mov     dword ptr [rsp+110h+var_E8], edi
0x140017e1c  lea     rdx, TPM_SAVE_STATE_FAILED_EX
0x140017e23  mov     r9d, 1Ch
0x140017e29  mov     dword ptr [rsp+110h+Timeout], 5B4h
0x140017e31  call    McTemplateK0dqq_EtwWriteTransfer
0x140017e36  xor     r12d, r12d
0x140017e39  jmp     loc_140017A5D
0x140017e3e  mov     r8d, 1
0x140017e44  call    ?FetchEvent@Tpm20Scheduler@@AEAAHJW4_SCHED20_EVENT@1@@Z; Tpm20Scheduler::FetchEvent(long,Tpm20Scheduler::_SCHED20_EVENT)
0x140017e49  test    eax, eax
0x140017e4b  jnz     short loc_140017E70
0x140017e4d  test    r12d, r12d
0x140017e50  jz      loc_1400179FF
0x140017e56  call    ?FetchNextUserRequest@Tpm20Scheduler@@AEAAHXZ; Tpm20Scheduler::FetchNextUserRequest(void)
0x140017e5b  test    eax, eax
0x140017e5d  jz      loc_1400179FF
0x140017e63  mov     rcx, rbx; this
0x140017e66  call    ?DoUserRequest@Tpm20Scheduler@@AEAAXXZ; Tpm20Scheduler::DoUserRequest(void)
0x140017e6b  jmp     loc_140017A5D
0x140017e70  mov     rcx, [rbp+57h+var_50]
0x140017e74  xor     rcx, rsp; StackCookie
0x140017e77  call    __security_check_cookie
0x140017e7c  add     rsp, 0D8h
0x140017e83  pop     r15
0x140017e85  pop     r14
0x140017e87  pop     r13
0x140017e89  pop     r12
0x140017e8b  pop     rdi
0x140017e8c  pop     rsi
0x140017e8d  pop     rbx
0x140017e8e  pop     rbp
0x140017e8f  retn
```
