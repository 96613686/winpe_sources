# SpAcquireResourceExclusive(_ERESOURCE *)

- ea: `0x140021df0`
- end: `0x14002216b`
- name: `?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z`
- size: `891`
- prototype: `void __fastcall(PERESOURCE Resource)`
- caller_count: `62`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400338f0`
- `0x1400393c8`
- `0x14003b9c0`
- `0x14003c260`
- `0x14008d55c`
- `0x14008dd50`
- `0x140091470`
- `0x1400917e0`
- `0x1400918a4`
- `0x1400927e0`
- `0x140092fbc`
- `0x14009365c`
- `0x140093b94`
- `0x140093f68`
- `0x140094274`
- `0x1400944b8`
- `0x1400949b8`
- `0x14009665c`
- `0x1400967bc`
- `0x14009697c`
- `0x140096b90`
- `0x140096e90`
- `0x140097280`
- `0x140097518`
- `0x140097bdc`
- `0x140097d58`
- `0x1400985a0`
- `0x140098760`
- `0x14009882c`
- `0x140098cd8`
- `0x14009905c`
- `0x1400991dc`
- `0x140099414`
- `0x1400997a8`
- `0x140099dc8`
- `0x14009a4d4`
- `0x14009aa74`
- `0x14009b578`
- `0x14009b648`
- `0x14009b874`
- `0x14009ba5c`
- `0x14009bbbc`
- `0x14009be10`
- `0x14009bf7c`
- `0x1400a22cc`
- `0x1400a63b8`
- `0x1400a84f0`
- `0x1400a86e0`
- `0x1400a8890`
- `0x1400a8b30`

## callees

- `0x140021df0`
- `0x14002c3ec`
- `0x140035ca0`
- `0x140068110`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140021e47`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140021e47`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021e58`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140021e58`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140021f1d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140021f1d`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002202b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002202b`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021e38`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021e80`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021e38`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021e80`
- `ntoskrnl!EtwWriteTransfer` at `0x140022136`
- `ntoskrnl!EtwWriteTransfer` at `0x140022136`

## pseudocode

```c
void __fastcall SpAcquireResourceExclusive(PERESOURCE Resource)
{
  ULONGLONG UnbiasedInterruptTime; // rdi
  ULONGLONG v3; // rax
  unsigned __int64 v4; // rsi
  __int64 v5; // rcx
  char *v6; // rdi
  __int64 v7; // rbx
  char *v8; // r10
  char v9; // r9
  char *v10; // rdx
  int v11; // r8d
  __int64 v12; // rcx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+44h] [rbp-BCh] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v16[3]; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  PVOID BackTrace[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v21; // [rsp+88h] [rbp-78h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  void *v23; // [rsp+B0h] [rbp-50h]
  int v24; // [rsp+B8h] [rbp-48h]
  int v25; // [rsp+BCh] [rbp-44h]
  __int64 *v26; // [rsp+C0h] [rbp-40h]
  __int64 v27; // [rsp+C8h] [rbp-38h]
  __int64 ActivityIdThread; // [rsp+D0h] [rbp-30h]
  __int64 v29; // [rsp+D8h] [rbp-28h]
  unsigned __int64 *v30; // [rsp+E0h] [rbp-20h]
  __int64 v31; // [rsp+E8h] [rbp-18h]
  _DWORD *v32; // [rsp+F0h] [rbp-10h]
  __int64 v33; // [rsp+F8h] [rbp-8h]
  int *v34; // [rsp+100h] [rbp+0h]
  __int64 v35; // [rsp+108h] [rbp+8h]
  int *v36; // [rsp+110h] [rbp+10h]
  __int64 v37; // [rsp+118h] [rbp+18h]
  int *v38; // [rsp+120h] [rbp+20h]
  __int64 v39; // [rsp+128h] [rbp+28h]

  UnbiasedInterruptTime = 0;
  *(_OWORD *)BackTrace = 0;
  v21 = 0;
  if ( Resource == (PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96) )
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(Resource, 1u);
  if ( Resource == (PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96) )
  {
    v3 = KeQueryUnbiasedInterruptTime();
    *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 25) = v3;
    v4 = (v3 - UnbiasedInterruptTime) / 0x2710;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids, v4);
    }
    if ( v4 > 0x7530 )
    {
      v5 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
      v6 = *(char **)(v5 + 24);
      v7 = *(unsigned int *)(v5 + 32);
      RtlCaptureStackBackTrace(1u, 4u, BackTrace, 0);
      v8 = &v6[v7];
      if ( BackTrace[0] < v6 || BackTrace[0] >= v8 )
      {
        v9 = 0;
        BackTrace[0] = 0;
      }
      else
      {
        v9 = LOBYTE(BackTrace[0]) - (_BYTE)v6;
        BackTrace[0] = (PVOID)((char *)BackTrace[0] - v6);
      }
      if ( BackTrace[1] < v6 || BackTrace[1] >= v8 )
        v10 = 0;
      else
        v10 = (char *)((char *)BackTrace[1] - (char *)v6);
      BackTrace[1] = v10;
      if ( (unsigned __int64)v21 < (unsigned __int64)v6 || (unsigned __int64)v21 >= (unsigned __int64)v8 )
      {
        v11 = 0;
        *(_QWORD *)&v21 = 0;
      }
      else
      {
        v11 = v21 - (_DWORD)v6;
        *(_QWORD *)&v21 = v21 - (_QWORD)v6;
      }
      if ( *((_QWORD *)&v21 + 1) < (unsigned __int64)v6 || *((_QWORD *)&v21 + 1) >= (unsigned __int64)v8 )
        v12 = 0;
      else
        v12 = *((_QWORD *)&v21 + 1) - (_QWORD)v6;
      *((_QWORD *)&v21 + 1) = v12;
      if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
        McTemplateK0xdddd_EtwWriteTransfer(v12, (unsigned int)ResourceWait, v11, v4, v9, (char)v10, v11, v12);
      if ( (unsigned int)dword_14007F050 > 5
        && (qword_14007F060 & 0x400000000000LL) != 0
        && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
      {
        v13 = DWORD2(v21);
        v14 = v21;
        v15 = (int)BackTrace[1];
        v16[0] = BackTrace[0];
        v17 = v4;
        v18 = 0x1000000;
        ActivityIdThread = IoGetActivityIdThread(qword_14007F068);
        v38 = &v13;
        v26 = &v18;
        *(_DWORD *)&EventDescriptor.Level = 5;
        v36 = &v14;
        UserData.Ptr = (ULONGLONG)off_14007F058;
        v34 = &v15;
        v32 = v16;
        v30 = &v17;
        v39 = 4;
        v37 = 4;
        v35 = 4;
        v33 = 4;
        v31 = 8;
        v29 = 16;
        v27 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x400000000000LL;
        UserData.Size = *(unsigned __int16 *)off_14007F058;
        v23 = &unk_140075998;
        UserData.Reserved = 2;
        v24 = 112;
        v25 = 1;
        v16[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &UserData);
      }
    }
  }
}

```

## disassembly

```asm
0x140021df0  mov     [rsp-8+arg_10], rbx
0x140021df5  push    rbp
0x140021df6  push    rdi
0x140021df7  push    r14
0x140021df9  lea     rbp, [rsp-40h]
0x140021dfe  sub     rsp, 140h
0x140021e05  mov     rax, cs:__security_cookie
0x140021e0c  xor     rax, rsp
0x140021e0f  mov     [rbp+50h+var_20], rax
0x140021e13  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140021e1a  xor     r14d, r14d
0x140021e1d  xorps   xmm0, xmm0
0x140021e20  add     rax, 60h ; '`'
0x140021e24  mov     rbx, rcx
0x140021e27  mov     edi, r14d
0x140021e2a  movups  xmmword ptr [rsp+150h+BackTrace], xmm0
0x140021e2f  movups  [rbp+50h+var_C8], xmm0
0x140021e33  cmp     rcx, rax
0x140021e36  jnz     short loc_140021E47
0x140021e38  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140021e3f  nop     dword ptr [rax+rax+00h]
0x140021e44  mov     rdi, rax
0x140021e47  call    cs:__imp_KeEnterCriticalRegion
0x140021e4e  nop     dword ptr [rax+rax+00h]
0x140021e53  mov     dl, 1; Wait
0x140021e55  mov     rcx, rbx; Resource
0x140021e58  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140021e5f  nop     dword ptr [rax+rax+00h]
0x140021e64  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140021e6b  add     rcx, 60h ; '`'
0x140021e6f  cmp     rbx, rcx
0x140021e72  jnz     loc_14002214A
0x140021e78  mov     [rsp+150h+arg_8], rsi
0x140021e80  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140021e87  nop     dword ptr [rax+rax+00h]
0x140021e8c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x140021e93  mov     rdx, rax
0x140021e96  sub     rdx, rdi
0x140021e99  mov     [rcx+0C8h], rax
0x140021ea0  mov     rax, 346DC5D63886594Bh
0x140021eaa  mul     rdx
0x140021ead  mov     rsi, rdx
0x140021eb0  shr     rsi, 0Bh
0x140021eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140021ebb  lea     rax, WPP_GLOBAL_Control
0x140021ec2  cmp     rcx, rax
0x140021ec5  jz      short loc_140021EEC
0x140021ec7  mov     eax, [rcx+2Ch]
0x140021eca  test    al, 1
0x140021ecc  jz      short loc_140021EEC
0x140021ece  cmp     byte ptr [rcx+29h], 3
0x140021ed2  jb      short loc_140021EEC
0x140021ed4  mov     rcx, [rcx+18h]
0x140021ed8  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140021edf  mov     edx, 23h ; '#'
0x140021ee4  mov     r9, rsi
0x140021ee7  call    WPP_SF_i
0x140021eec  cmp     rsi, 7530h
0x140021ef3  jbe     loc_140022142
0x140021ef9  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140021f00  lea     r8, [rsp+150h+BackTrace]; BackTrace
0x140021f05  xor     r9d, r9d; BackTraceHash
0x140021f08  mov     edx, 4; FramesToCapture
0x140021f0d  mov     rcx, [rax+8]
0x140021f11  mov     rdi, [rcx+18h]
0x140021f15  mov     ebx, [rcx+20h]
0x140021f18  mov     ecx, 1; FramesToSkip
0x140021f1d  call    cs:__imp_RtlCaptureStackBackTrace
0x140021f24  nop     dword ptr [rax+rax+00h]
0x140021f29  mov     r9, [rsp+150h+BackTrace]
0x140021f2e  lea     r10, [rdi+rbx]
0x140021f32  cmp     r9, rdi
0x140021f35  jb      short loc_140021F46
0x140021f37  cmp     r9, r10
0x140021f3a  jnb     short loc_140021F46
0x140021f3c  sub     r9, rdi
0x140021f3f  mov     [rsp+150h+BackTrace], r9
0x140021f44  jmp     short loc_140021F4E
0x140021f46  mov     r9, r14
0x140021f49  mov     [rsp+150h+BackTrace], r14
0x140021f4e  mov     rdx, [rbp+50h+BackTrace+8]
0x140021f52  cmp     rdx, rdi
0x140021f55  jb      short loc_140021F61
0x140021f57  cmp     rdx, r10
0x140021f5a  jnb     short loc_140021F61
0x140021f5c  sub     rdx, rdi
0x140021f5f  jmp     short loc_140021F64
0x140021f61  mov     rdx, r14
0x140021f64  mov     r8, qword ptr [rbp+50h+var_C8]
0x140021f68  mov     [rbp+50h+BackTrace+8], rdx
0x140021f6c  cmp     r8, rdi
0x140021f6f  jb      short loc_140021F7F
0x140021f71  cmp     r8, r10
0x140021f74  jnb     short loc_140021F7F
0x140021f76  sub     r8, rdi
0x140021f79  mov     qword ptr [rbp+50h+var_C8], r8
0x140021f7d  jmp     short loc_140021F86
0x140021f7f  mov     r8, r14
0x140021f82  mov     qword ptr [rbp+50h+var_C8], r14
0x140021f86  mov     rcx, qword ptr [rbp+50h+var_C8+8]
0x140021f8a  cmp     rcx, rdi
0x140021f8d  jb      short loc_140021F99
0x140021f8f  cmp     rcx, r10
0x140021f92  jnb     short loc_140021F99
0x140021f94  sub     rcx, rdi
0x140021f97  jmp     short loc_140021F9C
0x140021f99  mov     rcx, r14
0x140021f9c  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x140021fa3  mov     qword ptr [rbp+50h+var_C8+8], rcx
0x140021fa7  jz      short loc_140021FCA
0x140021fa9  mov     [rsp+150h+var_118], ecx
0x140021fad  mov     [rsp+150h+var_120], r8d
0x140021fb2  mov     dword ptr [rsp+150h+UserData], edx
0x140021fb6  lea     rdx, ResourceWait
0x140021fbd  mov     [rsp+150h+UserDataCount], r9d
0x140021fc2  mov     r9, rsi
0x140021fc5  call    McTemplateK0xdddd_EtwWriteTransfer
0x140021fca  mov     eax, cs:dword_14007F050
0x140021fd0  cmp     eax, 5
0x140021fd3  jbe     loc_140022142
0x140021fd9  mov     rcx, cs:qword_14007F068
0x140021fe0  mov     rbx, 400000000000h
0x140021fea  mov     rax, cs:qword_14007F060
0x140021ff1  test    rbx, rax
0x140021ff4  jz      loc_140022142
0x140021ffa  mov     rax, rcx
0x140021ffd  and     rax, rbx
0x140022000  cmp     rax, rcx
0x140022003  jnz     loc_140022142
0x140022009  mov     eax, dword ptr [rbp+50h+var_C8+8]
0x14002200c  mov     [rsp+150h+var_110], eax
0x140022010  mov     eax, dword ptr [rbp+50h+var_C8]
0x140022013  mov     [rsp+150h+var_10C], eax
0x140022017  mov     eax, dword ptr [rbp+50h+BackTrace+8]
0x14002201a  mov     [rsp+150h+var_108], eax
0x14002201e  mov     eax, dword ptr [rsp+150h+BackTrace]
0x140022022  mov     [rsp+150h+var_104], eax
0x140022026  mov     [rsp+150h+var_F8], rsi
0x14002202b  call    cs:__imp_IoGetActivityIdThread
0x140022032  nop     dword ptr [rax+rax+00h]
0x140022037  mov     [rsp+150h+var_F0], 1000000h
0x140022040  lea     rcx, [rsp+150h+var_110]
0x140022045  mov     [rbp+50h+var_80], rax
0x140022049  lea     rdx, [rsp+150h+EventDescriptor]; EventDescriptor
0x14002204e  mov     [rbp+50h+var_30], rcx
0x140022052  lea     rax, [rsp+150h+var_F0]
0x140022057  mov     [rbp+50h+var_90], rax
0x14002205b  lea     rcx, [rsp+150h+var_10C]
0x140022060  movzx   eax, cs:word_14007598E
0x140022067  xor     r9d, r9d; RelatedActivityId
0x14002206a  mov     dword ptr [rsp+150h+EventDescriptor.Level], eax
0x14002206e  xor     r8d, r8d; ActivityId
0x140022071  mov     rax, cs:off_14007F058
0x140022078  mov     [rbp+50h+var_40], rcx
0x14002207c  lea     rcx, [rsp+150h+var_108]
0x140022081  mov     [rbp+50h+var_B0.Ptr], rax
0x140022085  mov     [rbp+50h+var_50], rcx
0x140022089  lea     rcx, [rsp+150h+var_104]
0x14002208e  mov     [rbp+50h+var_60], rcx
0x140022092  lea     rcx, [rsp+150h+var_F8]
0x140022097  mov     [rbp+50h+var_70], rcx
0x14002209b  lea     rcx, _TraceLoggingMetadata
0x1400220a2  mov     [rbp+50h+var_28], 4
0x1400220aa  mov     [rbp+50h+var_38], 4
0x1400220b2  mov     [rbp+50h+var_48], 4
0x1400220ba  mov     [rbp+50h+var_58], 4
0x1400220c2  mov     [rbp+50h+var_68], 8
0x1400220ca  mov     [rbp+50h+var_78], 10h
0x1400220d2  mov     [rbp+50h+var_88], 8
0x1400220da  mov     dword ptr [rsp+150h+EventDescriptor.Id], 0B000000h
0x1400220e2  mov     [rsp+150h+EventDescriptor.Keyword], rbx
0x1400220e7  movzx   eax, word ptr [rax]
0x1400220ea  mov     [rbp+50h+var_B0.Size], eax
0x1400220ed  lea     rax, unk_140075998
0x1400220f4  mov     [rbp+50h+var_A0], rax
0x1400220f8  lea     rax, _TraceLoggingMetadataEnd
0x1400220ff  sub     eax, ecx
0x140022101  mov     dword ptr [rbp+50h+var_B0.0Ch], 2
0x140022108  mov     [rbp+50h+var_98], 70h ; 'p'
0x14002210f  mov     [rbp+50h+var_94], 1
0x140022116  mov     [rsp+150h+var_100], eax
0x14002211a  mov     eax, [rsp+150h+var_100]
0x14002211e  mov     rcx, cs:RegHandle; RegHandle
0x140022125  lea     rax, [rbp+50h+var_B0]
0x140022129  mov     [rsp+150h+UserData], rax; UserData
0x14002212e  mov     [rsp+150h+UserDataCount], 9; UserDataCount
0x140022136  call    cs:__imp_EtwWriteTransfer
0x14002213d  nop     dword ptr [rax+rax+00h]
0x140022142  mov     rsi, [rsp+150h+arg_8]
0x14002214a  mov     rcx, [rbp+50h+var_20]
0x14002214e  xor     rcx, rsp; StackCookie
0x140022151  call    __security_check_cookie
0x140022156  mov     rbx, [rsp+150h+arg_10]
0x14002215e  add     rsp, 140h
0x140022165  pop     r14
0x140022167  pop     rdi
0x140022168  pop     rbp
0x140022169  retn
```
