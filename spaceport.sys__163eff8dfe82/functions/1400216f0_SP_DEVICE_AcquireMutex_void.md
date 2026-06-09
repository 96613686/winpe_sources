# SP_DEVICE::AcquireMutex(void)

- ea: `0x1400216f0`
- end: `0x140021a7e`
- name: `?AcquireMutex@SP_DEVICE@@QEAAXXZ`
- size: `910`
- prototype: `void __fastcall(SP_DEVICE *__hidden this)`
- caller_count: `13`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002b094`
- `0x14003b080`
- `0x14003c778`
- `0x14008c2f0`
- `0x14009d930`
- `0x14009ee34`
- `0x14009f82c`
- `0x1400a0b40`
- `0x1400a54d0`
- `0x1400a7294`
- `0x1400adc34`
- `0x1400afca4`
- `0x1400b61d0`

## callees

- `0x1400216f0`
- `0x14002c32c`
- `0x14002c3ec`
- `0x140068110`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002174d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002174d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400217f6`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400217f6`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002191b`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002191b`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021727`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021759`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021727`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140021759`
- `ntoskrnl!EtwWriteTransfer` at `0x140021a44`
- `ntoskrnl!EtwWriteTransfer` at `0x140021a44`

## pseudocode

```c
void __fastcall SP_DEVICE::AcquireMutex(SP_DEVICE *this)
{
  ULONGLONG UnbiasedInterruptTime; // rbx
  ULONGLONG v3; // rax
  unsigned __int64 v4; // rsi
  __int64 v5; // rcx
  char *v6; // rdi
  __int64 v7; // rbx
  char *v8; // rcx
  char v9; // r10
  int v10; // r8d
  char v11; // r9
  __int64 v12; // rdx
  __int64 ActivityIdThread; // rax
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh] BYREF
  int v16; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v17[3]; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-88h] BYREF
  PVOID BackTrace[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v22; // [rsp+98h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  int *v24; // [rsp+C0h] [rbp-40h]
  int v25; // [rsp+C8h] [rbp-38h]
  int v26; // [rsp+CCh] [rbp-34h]
  __int64 *v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  __int64 v29; // [rsp+E0h] [rbp-20h]
  __int64 v30; // [rsp+E8h] [rbp-18h]
  unsigned __int64 *v31; // [rsp+F0h] [rbp-10h]
  __int64 v32; // [rsp+F8h] [rbp-8h]
  char *v33; // [rsp+100h] [rbp+0h]
  __int64 v34; // [rsp+108h] [rbp+8h]
  char *v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  _DWORD *v37; // [rsp+120h] [rbp+20h]
  __int64 v38; // [rsp+128h] [rbp+28h]
  int *v39; // [rsp+130h] [rbp+30h]
  __int64 v40; // [rsp+138h] [rbp+38h]
  int *v41; // [rsp+140h] [rbp+40h]
  __int64 v42; // [rsp+148h] [rbp+48h]
  int *v43; // [rsp+150h] [rbp+50h]
  __int64 v44; // [rsp+158h] [rbp+58h]

  *(_OWORD *)BackTrace = 0;
  v22 = 0;
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  KeWaitForSingleObject((char *)this + 176, Executive, 0, 0, 0);
  v3 = KeQueryUnbiasedInterruptTime();
  *((_QWORD *)this + 29) = v3;
  v4 = (v3 - UnbiasedInterruptTime) / 0x2710;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids, v4);
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
    {
      v10 = 0;
      BackTrace[1] = 0;
    }
    else
    {
      v10 = LODWORD(BackTrace[1]) - (_DWORD)v6;
      BackTrace[1] = (PVOID)((char *)BackTrace[1] - v6);
    }
    if ( (unsigned __int64)v22 < (unsigned __int64)v6 || (unsigned __int64)v22 >= (unsigned __int64)v8 )
    {
      v11 = 0;
      *(_QWORD *)&v22 = 0;
    }
    else
    {
      v11 = v22 - (_BYTE)v6;
      *(_QWORD *)&v22 = v22 - (_QWORD)v6;
    }
    if ( *((_QWORD *)&v22 + 1) < (unsigned __int64)v6 || *((_QWORD *)&v22 + 1) >= (unsigned __int64)v8 )
      v12 = 0;
    else
      v12 = *((_QWORD *)&v22 + 1) - (_QWORD)v6;
    *((_QWORD *)&v22 + 1) = v12;
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
      McTemplateK0xjjdddd_EtwWriteTransfer(
        (_DWORD)this + 24,
        (unsigned int)MutexWait,
        v10,
        v4,
        (__int64)this + 24,
        (__int64)this + 40,
        v9,
        v10,
        v11,
        v12);
    if ( (unsigned int)dword_14007F050 > 5
      && (qword_14007F060 & 0x400000000000LL) != 0
      && (qword_14007F068 & 0x400000000000LL) == qword_14007F068 )
    {
      v14 = DWORD2(v22);
      v15 = v22;
      v16 = (int)BackTrace[1];
      v17[0] = BackTrace[0];
      v18 = v4;
      ActivityIdThread = IoGetActivityIdThread(qword_14007F068);
      v19 = 0x1000000;
      v44 = 4;
      v29 = ActivityIdThread;
      v43 = &v14;
      v42 = 4;
      v41 = &v15;
      v40 = 4;
      v39 = &v16;
      v38 = 4;
      v37 = v17;
      v35 = (char *)this + 40;
      v31 = &v18;
      v27 = &v19;
      *(_DWORD *)&EventDescriptor.Level = 5;
      UserData.Ptr = (ULONGLONG)off_14007F058;
      v36 = 16;
      v33 = (char *)this + 24;
      v34 = 16;
      v32 = 8;
      v30 = 16;
      v28 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Size = *(unsigned __int16 *)off_14007F058;
      v24 = &dword_140074B64;
      UserData.Reserved = 2;
      v25 = 128;
      v26 = 1;
      v17[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
    }
  }
}

```

## disassembly

```asm
0x1400216f0  mov     [rsp-8+arg_10], rbx
0x1400216f5  mov     [rsp-8+arg_18], rsi
0x1400216fa  push    rbp
0x1400216fb  push    r14
0x1400216fd  push    r15
0x1400216ff  lea     rbp, [rsp-70h]
0x140021704  sub     rsp, 170h
0x14002170b  mov     rax, cs:__security_cookie
0x140021712  xor     rax, rsp
0x140021715  mov     [rbp+80h+var_20], rax
0x140021719  xorps   xmm0, xmm0
0x14002171c  mov     r14, rcx
0x14002171f  movups  xmmword ptr [rbp+80h+BackTrace], xmm0
0x140021723  movups  [rbp+80h+var_E8], xmm0
0x140021727  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002172e  nop     dword ptr [rax+rax+00h]
0x140021733  xor     r15d, r15d
0x140021736  lea     rcx, [r14+0B0h]; Object
0x14002173d  xor     r9d, r9d; Alertable
0x140021740  mov     [rsp+180h+Timeout], r15; Timeout
0x140021745  xor     r8d, r8d; WaitMode
0x140021748  xor     edx, edx; WaitReason
0x14002174a  mov     rbx, rax
0x14002174d  call    cs:__imp_KeWaitForSingleObject
0x140021754  nop     dword ptr [rax+rax+00h]
0x140021759  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140021760  nop     dword ptr [rax+rax+00h]
0x140021765  mov     rcx, rax
0x140021768  mov     [r14+0E8h], rax
0x14002176f  sub     rcx, rbx
0x140021772  mov     rax, 346DC5D63886594Bh
0x14002177c  mul     rcx
0x14002177f  mov     rsi, rdx
0x140021782  shr     rsi, 0Bh
0x140021786  mov     rcx, cs:WPP_GLOBAL_Control
0x14002178d  lea     rax, WPP_GLOBAL_Control
0x140021794  cmp     rcx, rax
0x140021797  jz      short loc_1400217BE
0x140021799  mov     eax, [rcx+2Ch]
0x14002179c  test    al, 1
0x14002179e  jz      short loc_1400217BE
0x1400217a0  cmp     byte ptr [rcx+29h], 3
0x1400217a4  jb      short loc_1400217BE
0x1400217a6  mov     rcx, [rcx+18h]
0x1400217aa  lea     r8, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids
0x1400217b1  mov     edx, 0Ah
0x1400217b6  mov     r9, rsi
0x1400217b9  call    WPP_SF_i
0x1400217be  cmp     rsi, 7530h
0x1400217c5  jbe     loc_140021A58
0x1400217cb  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400217d2  lea     r8, [rbp+80h+BackTrace]; BackTrace
0x1400217d6  mov     [rsp+180h+arg_8], rdi
0x1400217de  xor     r9d, r9d; BackTraceHash
0x1400217e1  mov     edx, 4; FramesToCapture
0x1400217e6  mov     rcx, [rax+8]
0x1400217ea  mov     rdi, [rcx+18h]
0x1400217ee  mov     ebx, [rcx+20h]
0x1400217f1  mov     ecx, 1; FramesToSkip
0x1400217f6  call    cs:__imp_RtlCaptureStackBackTrace
0x1400217fd  nop     dword ptr [rax+rax+00h]
0x140021802  mov     r10, [rbp+80h+BackTrace]
0x140021806  lea     rcx, [rdi+rbx]
0x14002180a  cmp     r10, rdi
0x14002180d  jb      short loc_14002181D
0x14002180f  cmp     r10, rcx
0x140021812  jnb     short loc_14002181D
0x140021814  sub     r10, rdi
0x140021817  mov     [rbp+80h+BackTrace], r10
0x14002181b  jmp     short loc_140021824
0x14002181d  mov     r10, r15
0x140021820  mov     [rbp+80h+BackTrace], r15
0x140021824  mov     r8, [rbp+80h+BackTrace+8]
0x140021828  cmp     r8, rdi
0x14002182b  jb      short loc_14002183B
0x14002182d  cmp     r8, rcx
0x140021830  jnb     short loc_14002183B
0x140021832  sub     r8, rdi
0x140021835  mov     [rbp+80h+BackTrace+8], r8
0x140021839  jmp     short loc_140021842
0x14002183b  mov     r8, r15
0x14002183e  mov     [rbp+80h+BackTrace+8], r15
0x140021842  mov     r9, qword ptr [rbp+80h+var_E8]
0x140021846  cmp     r9, rdi
0x140021849  jb      short loc_140021859
0x14002184b  cmp     r9, rcx
0x14002184e  jnb     short loc_140021859
0x140021850  sub     r9, rdi
0x140021853  mov     qword ptr [rbp+80h+var_E8], r9
0x140021857  jmp     short loc_140021860
0x140021859  mov     r9, r15
0x14002185c  mov     qword ptr [rbp+80h+var_E8], r15
0x140021860  mov     rdx, qword ptr [rbp+80h+var_E8+8]
0x140021864  cmp     rdx, rdi
0x140021867  jb      short loc_140021873
0x140021869  cmp     rdx, rcx
0x14002186c  jnb     short loc_140021873
0x14002186e  sub     rdx, rdi
0x140021871  jmp     short loc_140021876
0x140021873  mov     rdx, r15
0x140021876  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14002187d  mov     qword ptr [rbp+80h+var_E8+8], rdx
0x140021881  jz      short loc_1400218B7
0x140021883  mov     [rsp+180h+var_138], edx
0x140021887  lea     rcx, [r14+18h]
0x14002188b  mov     [rsp+180h+var_140], r9d
0x140021890  lea     rax, [rcx+10h]
0x140021894  mov     [rsp+180h+var_148], r8d
0x140021899  lea     rdx, MutexWait
0x1400218a0  mov     [rsp+180h+var_150], r10d
0x1400218a5  mov     r9, rsi
0x1400218a8  mov     [rsp+180h+UserData], rax
0x1400218ad  mov     [rsp+180h+Timeout], rcx
0x1400218b2  call    McTemplateK0xjjdddd_EtwWriteTransfer
0x1400218b7  mov     eax, cs:dword_14007F050
0x1400218bd  cmp     eax, 5
0x1400218c0  jbe     loc_140021A50
0x1400218c6  mov     rcx, cs:qword_14007F068
0x1400218cd  mov     rdi, 400000000000h
0x1400218d7  mov     rax, cs:qword_14007F060
0x1400218de  test    rdi, rax
0x1400218e1  jz      loc_140021A50
0x1400218e7  mov     rax, rcx
0x1400218ea  and     rax, rdi
0x1400218ed  cmp     rax, rcx
0x1400218f0  jnz     loc_140021A50
0x1400218f6  mov     eax, dword ptr [rbp+80h+var_E8+8]
0x1400218f9  lea     rbx, [r14+18h]
0x1400218fd  mov     [rsp+180h+var_130], eax
0x140021901  mov     eax, dword ptr [rbp+80h+var_E8]
0x140021904  mov     [rsp+180h+var_12C], eax
0x140021908  mov     eax, dword ptr [rbp+80h+BackTrace+8]
0x14002190b  mov     [rsp+180h+var_128], eax
0x14002190f  mov     eax, dword ptr [rbp+80h+BackTrace]
0x140021912  mov     [rsp+180h+var_124], eax
0x140021916  mov     [rsp+180h+var_118], rsi
0x14002191b  call    cs:__imp_IoGetActivityIdThread
0x140021922  nop     dword ptr [rax+rax+00h]
0x140021927  mov     [rsp+180h+var_110], 1000000h
0x140021930  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x140021935  mov     rcx, rax
0x140021938  mov     [rbp+80h+var_28], 4
0x140021940  mov     [rbp+80h+var_A0], rcx
0x140021944  lea     rax, [rsp+180h+var_130]
0x140021949  mov     [rbp+80h+var_30], rax
0x14002194d  lea     rcx, _TraceLoggingMetadata
0x140021954  mov     [rbp+80h+var_38], 4
0x14002195c  lea     rax, [rsp+180h+var_12C]
0x140021961  mov     [rbp+80h+var_40], rax
0x140021965  xor     r9d, r9d; RelatedActivityId
0x140021968  mov     [rbp+80h+var_48], 4
0x140021970  lea     rax, [rsp+180h+var_128]
0x140021975  mov     [rbp+80h+var_50], rax
0x140021979  xor     r8d, r8d; ActivityId
0x14002197c  mov     [rbp+80h+var_58], 4
0x140021984  lea     rax, [rsp+180h+var_124]
0x140021989  mov     [rbp+80h+var_60], rax
0x14002198d  lea     rax, [rbx+10h]
0x140021991  mov     [rbp+80h+var_70], rax
0x140021995  lea     rax, [rsp+180h+var_118]
0x14002199a  mov     [rbp+80h+var_90], rax
0x14002199e  lea     rax, [rsp+180h+var_110]
0x1400219a3  mov     [rbp+80h+var_B0], rax
0x1400219a7  movzx   eax, cs:word_140074B5A
0x1400219ae  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x1400219b2  mov     rax, cs:off_14007F058
0x1400219b9  mov     [rbp+80h+var_D0.Ptr], rax
0x1400219bd  mov     [rbp+80h+var_68], 10h
0x1400219c5  mov     [rbp+80h+var_80], rbx
0x1400219c9  mov     [rbp+80h+var_78], 10h
0x1400219d1  mov     [rbp+80h+var_88], 8
0x1400219d9  mov     [rbp+80h+var_98], 10h
0x1400219e1  mov     [rbp+80h+var_A8], 8
0x1400219e9  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x1400219f1  mov     [rbp+80h+EventDescriptor.Keyword], rdi
0x1400219f5  movzx   eax, word ptr [rax]
0x1400219f8  mov     [rbp+80h+var_D0.Size], eax
0x1400219fb  lea     rax, dword_140074B64
0x140021a02  mov     [rbp+80h+var_C0], rax
0x140021a06  lea     rax, _TraceLoggingMetadataEnd
0x140021a0d  sub     eax, ecx
0x140021a0f  mov     dword ptr [rbp+80h+var_D0.0Ch], 2
0x140021a16  mov     [rbp+80h+var_B8], 80h
0x140021a1d  mov     [rbp+80h+var_B4], 1
0x140021a24  mov     [rsp+180h+var_120], eax
0x140021a28  mov     eax, [rsp+180h+var_120]
0x140021a2c  mov     rcx, cs:RegHandle; RegHandle
0x140021a33  lea     rax, [rbp+80h+var_D0]
0x140021a37  mov     [rsp+180h+UserData], rax; UserData
0x140021a3c  mov     dword ptr [rsp+180h+Timeout], 0Bh; UserDataCount
0x140021a44  call    cs:__imp_EtwWriteTransfer
0x140021a4b  nop     dword ptr [rax+rax+00h]
0x140021a50  mov     rdi, [rsp+180h+arg_8]
0x140021a58  mov     rcx, [rbp+80h+var_20]
0x140021a5c  xor     rcx, rsp; StackCookie
0x140021a5f  call    __security_check_cookie
0x140021a64  lea     r11, [rsp+180h+var_10]
0x140021a6c  mov     rbx, [r11+30h]
0x140021a70  mov     rsi, [r11+38h]
0x140021a74  mov     rsp, r11
0x140021a77  pop     r15
0x140021a79  pop     r14
0x140021a7b  pop     rbp
0x140021a7c  retn
```
