# SP_DEVICE::ReleaseMutex(void)

- ea: `0x140021a90`
- end: `0x140021de1`
- name: `?ReleaseMutex@SP_DEVICE@@QEAAXXZ`
- size: `849`
- prototype: `void __fastcall(SP_DEVICE *__hidden this)`
- caller_count: `15`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002bc90`
- `0x14003afc0`
- `0x14003c6b8`
- `0x14008c2f0`
- `0x14008dad4`
- `0x14009d910`
- `0x14009ee20`
- `0x1400a0a10`
- `0x1400a53a0`
- `0x1400a7164`
- `0x1400ada94`
- `0x1400afb04`
- `0x1400b46f0`
- `0x1400b6030`
- `0x1400b6ac0`

## callees

- `0x140021a90`
- `0x14002c32c`
- `0x14002c3ec`
- `0x140067fc0`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140021b74`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140021b74`
- `ntoskrnl!KeReleaseMutex` at `0x140021af0`
- `ntoskrnl!KeReleaseMutex` at `0x140021af0`
- `ntoskrnl!IoGetActivityIdThread` at `0x140021d10`
- `ntoskrnl!IoGetActivityIdThread` at `0x140021d10`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021abd`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021abd`
- `ntoskrnl!EtwWriteTransfer` at `0x140021dac`
- `ntoskrnl!EtwWriteTransfer` at `0x140021dac`

## pseudocode

```c
void __fastcall SP_DEVICE::ReleaseMutex(SP_DEVICE *this)
{
  ULONGLONG v2; // rsi
  __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  PVOID v6; // rcx
  char v7; // r10
  int v8; // r8d
  char v9; // r9
  char v10; // dl
  __int64 ActivityIdThread; // rax
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+54h] [rbp-ACh] BYREF
  int v14; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v15[3]; // [rsp+5Ch] [rbp-A4h] BYREF
  ULONGLONG v16; // [rsp+68h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-90h] BYREF
  PVOID BackTrace[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v19; // [rsp+90h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  void *v21; // [rsp+B0h] [rbp-50h]
  int v22; // [rsp+B8h] [rbp-48h]
  int v23; // [rsp+BCh] [rbp-44h]
  __int64 v24; // [rsp+C0h] [rbp-40h]
  __int64 v25; // [rsp+C8h] [rbp-38h]
  ULONGLONG *v26; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  char *v28; // [rsp+E0h] [rbp-20h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  char *v30; // [rsp+F0h] [rbp-10h]
  __int64 v31; // [rsp+F8h] [rbp-8h]
  _DWORD *v32; // [rsp+100h] [rbp+0h]
  __int64 v33; // [rsp+108h] [rbp+8h]
  int *v34; // [rsp+110h] [rbp+10h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  int *v36; // [rsp+120h] [rbp+20h]
  __int64 v37; // [rsp+128h] [rbp+28h]
  int *v38; // [rsp+130h] [rbp+30h]
  __int64 v39; // [rsp+138h] [rbp+38h]

  *(_OWORD *)BackTrace = 0;
  v19 = 0;
  v2 = (KeQueryUnbiasedInterruptTime() - *((_QWORD *)this + 29)) / 0x2710;
  KeReleaseMutex((PRKMUTEX)((char *)this + 176), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids, v2);
  }
  if ( v2 > 0x7530 )
  {
    v3 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
    v4 = *(_QWORD *)(v3 + 24);
    v5 = *(unsigned int *)(v3 + 32);
    RtlCaptureStackBackTrace(1u, 4u, BackTrace, 0);
    v6 = (PVOID)(v4 + v5);
    if ( BackTrace[0] < (PVOID)v4 || BackTrace[0] >= v6 )
    {
      v7 = 0;
      BackTrace[0] = 0;
    }
    else
    {
      v7 = LOBYTE(BackTrace[0]) - v4;
      BackTrace[0] = (char *)BackTrace[0] - v4;
    }
    if ( BackTrace[1] < (PVOID)v4 || BackTrace[1] >= v6 )
    {
      v8 = 0;
      BackTrace[1] = 0;
    }
    else
    {
      v8 = LODWORD(BackTrace[1]) - v4;
      BackTrace[1] = (char *)BackTrace[1] - v4;
    }
    if ( (unsigned __int64)v19 < v4 || (unsigned __int64)v19 >= (unsigned __int64)v6 )
    {
      v9 = 0;
      *(_QWORD *)&v19 = 0;
    }
    else
    {
      v9 = v19 - v4;
      *(_QWORD *)&v19 = v19 - v4;
    }
    if ( *((_QWORD *)&v19 + 1) < v4 || *((_QWORD *)&v19 + 1) >= (unsigned __int64)v6 )
    {
      v10 = 0;
      *((_QWORD *)&v19 + 1) = 0;
    }
    else
    {
      v10 = BYTE8(v19) - v4;
      *((_QWORD *)&v19 + 1) -= v4;
    }
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
      McTemplateK0xjjdddd_EtwWriteTransfer(
        (_DWORD)this + 24,
        (unsigned int)MutexHold,
        v8,
        v2,
        (__int64)this + 24,
        (__int64)this + 40,
        v7,
        v8,
        v9,
        v10);
    if ( (unsigned int)dword_14007F050 > 5
      && (qword_14007F060 & 0x400000000000LL) != 0
      && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
    {
      v12 = DWORD2(v19);
      v13 = v19;
      v14 = (int)BackTrace[1];
      v15[0] = BackTrace[0];
      v38 = &v12;
      v36 = &v13;
      v34 = &v14;
      v32 = v15;
      v30 = (char *)this + 40;
      v26 = &v16;
      v16 = v2;
      v39 = 4;
      v37 = 4;
      v35 = 4;
      v33 = 4;
      v31 = 16;
      v28 = (char *)this + 24;
      v29 = 16;
      v27 = 8;
      ActivityIdThread = IoGetActivityIdThread((char *)this + 24);
      v25 = 16;
      v24 = ActivityIdThread;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14007F058;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Size = *(unsigned __int16 *)off_14007F058;
      v21 = &unk_140074F00;
      UserData.Reserved = 2;
      v22 = 112;
      v23 = 1;
      v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xAu, &UserData);
    }
  }
}

```

## disassembly

```asm
0x140021a90  push    rbp
0x140021a92  push    rsi
0x140021a93  push    r14
0x140021a95  lea     rbp, [rsp-50h]
0x140021a9a  sub     rsp, 150h
0x140021aa1  mov     rax, cs:__security_cookie
0x140021aa8  xor     rax, rsp
0x140021aab  mov     [rbp+60h+var_20], rax
0x140021aaf  xorps   xmm0, xmm0
0x140021ab2  mov     r14, rcx
0x140021ab5  movups  xmmword ptr [rbp+60h+BackTrace], xmm0
0x140021ab9  movups  [rbp+60h+var_D0], xmm0
0x140021abd  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140021ac4  nop     dword ptr [rax+rax+00h]
0x140021ac9  mov     rdx, rax
0x140021acc  lea     rcx, [r14+0B0h]; Mutex
0x140021ad3  sub     rdx, [r14+0E8h]
0x140021ada  mov     rax, 346DC5D63886594Bh
0x140021ae4  mul     rdx
0x140021ae7  mov     rsi, rdx
0x140021aea  xor     edx, edx; Wait
0x140021aec  shr     rsi, 0Bh
0x140021af0  call    cs:__imp_KeReleaseMutex
0x140021af7  nop     dword ptr [rax+rax+00h]
0x140021afc  mov     rcx, cs:WPP_GLOBAL_Control
0x140021b03  lea     rax, WPP_GLOBAL_Control
0x140021b0a  cmp     rcx, rax
0x140021b0d  jz      short loc_140021B34
0x140021b0f  mov     eax, [rcx+2Ch]
0x140021b12  test    al, 1
0x140021b14  jz      short loc_140021B34
0x140021b16  cmp     byte ptr [rcx+29h], 3
0x140021b1a  jb      short loc_140021B34
0x140021b1c  mov     rcx, [rcx+18h]
0x140021b20  lea     r8, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids
0x140021b27  mov     edx, 0Bh
0x140021b2c  mov     r9, rsi
0x140021b2f  call    WPP_SF_i
0x140021b34  cmp     rsi, 7530h
0x140021b3b  jbe     loc_140021DC8
0x140021b41  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140021b48  lea     r8, [rbp+60h+BackTrace]; BackTrace
0x140021b4c  mov     [rsp+160h+arg_8], rbx
0x140021b54  xor     r9d, r9d; BackTraceHash
0x140021b57  mov     [rsp+160h+arg_10], rdi
0x140021b5f  mov     edx, 4; FramesToCapture
0x140021b64  mov     rcx, [rax+8]
0x140021b68  mov     rdi, [rcx+18h]
0x140021b6c  mov     ebx, [rcx+20h]
0x140021b6f  mov     ecx, 1; FramesToSkip
0x140021b74  call    cs:__imp_RtlCaptureStackBackTrace
0x140021b7b  nop     dword ptr [rax+rax+00h]
0x140021b80  mov     r10, [rbp+60h+BackTrace]
0x140021b84  lea     rcx, [rdi+rbx]
0x140021b88  xor     ebx, ebx
0x140021b8a  cmp     r10, rdi
0x140021b8d  jb      short loc_140021B9D
0x140021b8f  cmp     r10, rcx
0x140021b92  jnb     short loc_140021B9D
0x140021b94  sub     r10, rdi
0x140021b97  mov     [rbp+60h+BackTrace], r10
0x140021b9b  jmp     short loc_140021BA4
0x140021b9d  mov     r10, rbx
0x140021ba0  mov     [rbp+60h+BackTrace], rbx
0x140021ba4  mov     r8, [rbp+60h+BackTrace+8]
0x140021ba8  cmp     r8, rdi
0x140021bab  jb      short loc_140021BBB
0x140021bad  cmp     r8, rcx
0x140021bb0  jnb     short loc_140021BBB
0x140021bb2  sub     r8, rdi
0x140021bb5  mov     [rbp+60h+BackTrace+8], r8
0x140021bb9  jmp     short loc_140021BC2
0x140021bbb  mov     r8, rbx
0x140021bbe  mov     [rbp+60h+BackTrace+8], rbx
0x140021bc2  mov     r9, qword ptr [rbp+60h+var_D0]
0x140021bc6  cmp     r9, rdi
0x140021bc9  jb      short loc_140021BD9
0x140021bcb  cmp     r9, rcx
0x140021bce  jnb     short loc_140021BD9
0x140021bd0  sub     r9, rdi
0x140021bd3  mov     qword ptr [rbp+60h+var_D0], r9
0x140021bd7  jmp     short loc_140021BE0
0x140021bd9  mov     r9, rbx
0x140021bdc  mov     qword ptr [rbp+60h+var_D0], rbx
0x140021be0  mov     rdx, qword ptr [rbp+60h+var_D0+8]
0x140021be4  cmp     rdx, rdi
0x140021be7  jb      short loc_140021BF7
0x140021be9  cmp     rdx, rcx
0x140021bec  jnb     short loc_140021BF7
0x140021bee  sub     rdx, rdi
0x140021bf1  mov     qword ptr [rbp+60h+var_D0+8], rdx
0x140021bf5  jmp     short loc_140021BFE
0x140021bf7  mov     rdx, rbx
0x140021bfa  mov     qword ptr [rbp+60h+var_D0+8], rbx
0x140021bfe  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x140021c05  jz      short loc_140021C3B
0x140021c07  mov     [rsp+160h+var_118], edx
0x140021c0b  lea     rcx, [r14+18h]
0x140021c0f  mov     [rsp+160h+var_120], r9d
0x140021c14  lea     rax, [rcx+10h]
0x140021c18  mov     [rsp+160h+var_128], r8d
0x140021c1d  lea     rdx, MutexHold
0x140021c24  mov     [rsp+160h+var_130], r10d
0x140021c29  mov     r9, rsi
0x140021c2c  mov     [rsp+160h+UserData], rax
0x140021c31  mov     qword ptr [rsp+160h+UserDataCount], rcx
0x140021c36  call    McTemplateK0xjjdddd_EtwWriteTransfer
0x140021c3b  mov     eax, cs:dword_14007F050
0x140021c41  cmp     eax, 5
0x140021c44  jbe     loc_140021DB8
0x140021c4a  mov     rcx, cs:qword_14007F068
0x140021c51  mov     rdi, 400000000000h
0x140021c5b  mov     rax, cs:qword_14007F060
0x140021c62  test    rdi, rax
0x140021c65  jz      loc_140021DB8
0x140021c6b  mov     rax, rcx
0x140021c6e  and     rax, rdi
0x140021c71  cmp     rax, rcx
0x140021c74  jnz     loc_140021DB8
0x140021c7a  mov     eax, dword ptr [rbp+60h+var_D0+8]
0x140021c7d  lea     rcx, [r14+18h]
0x140021c81  mov     [rsp+160h+var_110], eax
0x140021c85  mov     eax, dword ptr [rbp+60h+var_D0]
0x140021c88  mov     [rsp+160h+var_10C], eax
0x140021c8c  mov     eax, dword ptr [rbp+60h+BackTrace+8]
0x140021c8f  mov     [rsp+160h+var_108], eax
0x140021c93  mov     eax, dword ptr [rbp+60h+BackTrace]
0x140021c96  mov     [rsp+160h+var_104], eax
0x140021c9a  lea     rax, [rsp+160h+var_110]
0x140021c9f  mov     [rbp+60h+var_30], rax
0x140021ca3  lea     rax, [rsp+160h+var_10C]
0x140021ca8  mov     [rbp+60h+var_40], rax
0x140021cac  lea     rax, [rsp+160h+var_108]
0x140021cb1  mov     [rbp+60h+var_50], rax
0x140021cb5  lea     rax, [rsp+160h+var_104]
0x140021cba  mov     [rbp+60h+var_60], rax
0x140021cbe  lea     rax, [rcx+10h]
0x140021cc2  mov     [rbp+60h+var_70], rax
0x140021cc6  lea     rax, [rsp+160h+var_F8]
0x140021ccb  mov     [rbp+60h+var_90], rax
0x140021ccf  mov     [rsp+160h+var_F8], rsi
0x140021cd4  mov     [rbp+60h+var_28], 4
0x140021cdc  mov     [rbp+60h+var_38], 4
0x140021ce4  mov     [rbp+60h+var_48], 4
0x140021cec  mov     [rbp+60h+var_58], 4
0x140021cf4  mov     [rbp+60h+var_68], 10h
0x140021cfc  mov     [rbp+60h+var_80], rcx
0x140021d00  mov     [rbp+60h+var_78], 10h
0x140021d08  mov     [rbp+60h+var_88], 8
0x140021d10  call    cs:__imp_IoGetActivityIdThread
0x140021d17  nop     dword ptr [rax+rax+00h]
0x140021d1c  mov     [rbp+60h+var_98], 10h
0x140021d24  lea     rcx, _TraceLoggingMetadata
0x140021d2b  mov     [rbp+60h+var_A0], rax
0x140021d2f  lea     rdx, [rsp+160h+EventDescriptor]; EventDescriptor
0x140021d34  movzx   eax, cs:word_140074EF6
0x140021d3b  xor     r9d, r9d; RelatedActivityId
0x140021d3e  mov     dword ptr [rsp+160h+EventDescriptor.Level], eax
0x140021d42  xor     r8d, r8d; ActivityId
0x140021d45  mov     rax, cs:off_14007F058
0x140021d4c  mov     [rbp+60h+var_C0.Ptr], rax
0x140021d50  mov     dword ptr [rsp+160h+EventDescriptor.Id], 0B000000h
0x140021d58  mov     [rsp+160h+EventDescriptor.Keyword], rdi
0x140021d5d  movzx   eax, word ptr [rax]
0x140021d60  mov     [rbp+60h+var_C0.Size], eax
0x140021d63  lea     rax, unk_140074F00
0x140021d6a  mov     [rbp+60h+var_B0], rax
0x140021d6e  lea     rax, _TraceLoggingMetadataEnd
0x140021d75  sub     eax, ecx
0x140021d77  mov     dword ptr [rbp+60h+var_C0.0Ch], 2
0x140021d7e  mov     [rbp+60h+var_A8], 70h ; 'p'
0x140021d85  mov     [rbp+60h+var_A4], 1
0x140021d8c  mov     [rsp+160h+var_100], eax
0x140021d90  mov     eax, [rsp+160h+var_100]
0x140021d94  mov     rcx, cs:RegHandle; RegHandle
0x140021d9b  lea     rax, [rbp+60h+var_C0]
0x140021d9f  mov     [rsp+160h+UserData], rax; UserData
0x140021da4  mov     [rsp+160h+UserDataCount], 0Ah; UserDataCount
0x140021dac  call    cs:__imp_EtwWriteTransfer
0x140021db3  nop     dword ptr [rax+rax+00h]
0x140021db8  mov     rdi, [rsp+160h+arg_10]
0x140021dc0  mov     rbx, [rsp+160h+arg_8]
0x140021dc8  mov     rcx, [rbp+60h+var_20]
0x140021dcc  xor     rcx, rsp; StackCookie
0x140021dcf  call    __security_check_cookie
0x140021dd4  add     rsp, 150h
0x140021ddb  pop     r14
0x140021ddd  pop     rsi
0x140021dde  pop     rbp
0x140021ddf  retn
```
