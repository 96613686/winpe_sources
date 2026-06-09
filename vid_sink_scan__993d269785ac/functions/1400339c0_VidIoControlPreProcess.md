# VidIoControlPreProcess

- ea: `0x1400339c0`
- end: `0x140033e6a`
- name: `VidIoControlPreProcess`
- size: `1194`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008160`

## callees

- `0x140010270`
- `0x140021650`
- `0x140023cb4`
- `0x1400339c0`
- `0x140035698`
- `0x1400377bc`
- `0x140037fd0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140033e3b`
- `ntoskrnl!IofCompleteRequest` at `0x140033e3b`
- `ntoskrnl!EtwWriteTransfer` at `0x140033c2c`
- `ntoskrnl!EtwWriteTransfer` at `0x140033c2c`
- `ntoskrnl!PsGetCurrentProcess` at `0x140033c44`
- `ntoskrnl!PsGetCurrentProcess` at `0x140033c44`
- `HAL!KeQueryPerformanceCounter` at `0x140033a4a`
- `HAL!KeQueryPerformanceCounter` at `0x140033d02`
- `HAL!KeQueryPerformanceCounter` at `0x140033dc7`
- `HAL!KeQueryPerformanceCounter` at `0x140033a4a`
- `HAL!KeQueryPerformanceCounter` at `0x140033d02`
- `HAL!KeQueryPerformanceCounter` at `0x140033dc7`

## pseudocode

```c
__int64 __fastcall VidIoControlPreProcess(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  wchar_t *v3; // rax
  unsigned int LowPart; // esi
  unsigned int v6; // ebx
  int Options; // r12d
  struct _IRP *MasterIrp; // r13
  int Length; // ebx
  __int64 v10; // rdi
  int v11; // edx
  int v12; // ecx
  unsigned __int16 v13; // r15
  unsigned __int64 v14; // rdi
  int v15; // edx
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned __int64 v18; // rax
  unsigned int v19; // eax
  unsigned __int64 v20; // rax
  unsigned int pullResult; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+54h] [rbp-ACh] BYREF
  NTSTRSAFE_PWSTR pszDest; // [rsp+58h] [rbp-A8h]
  int v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-88h] BYREF
  __int128 v29; // [rsp+88h] [rbp-78h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v32; // [rsp+B0h] [rbp-50h]
  int v33; // [rsp+B8h] [rbp-48h]
  int v34; // [rsp+BCh] [rbp-44h]
  const char *v35; // [rsp+C0h] [rbp-40h]
  __int64 v36; // [rsp+C8h] [rbp-38h]
  const char *v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  int *v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  int *v41; // [rsp+F0h] [rbp-10h]
  __int64 v42; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  _DWORD *v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  __int64 v47; // [rsp+120h] [rbp+20h]
  _DWORD v48[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  int *v51; // [rsp+140h] [rbp+40h]
  __int64 v52; // [rsp+148h] [rbp+48h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  pullResult = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( (LowPart & 3) != 0 )
  {
    v6 = -1073741808;
LABEL_36:
    a2->IoStatus.Information = pullResult;
    a2->IoStatus.Status = v6;
    IofCompleteRequest(a2, 0);
    return v6;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options )
    MasterIrp = a2->AssociatedIrp.MasterIrp;
  else
    LODWORD(MasterIrp) = 0;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v23 = Length;
  if ( Length )
    v3 = (wchar_t *)a2->AssociatedIrp.MasterIrp;
  pszDest = v3;
  *(_QWORD *)v25 = CurrentStackLocation->FileObject;
  v29 = 0;
  PerformanceFrequency.QuadPart = 0;
  v10 = *(_QWORD *)(*(_QWORD *)v25 + 24LL);
  *(LARGE_INTEGER *)&v29 = KeQueryPerformanceCounter(0);
  v13 = (LowPart >> 2) & 0x3FF;
  v14 = v10 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( !v14 )
  {
    v19 = VidIoControlDriver(
            (_DWORD)VidDeviceExtension,
            v25[0],
            (_DWORD)MasterIrp,
            Options,
            (__int64)pszDest,
            Length,
            LowPart,
            (__int64)&pullResult);
LABEL_33:
    v6 = v19;
    if ( v13 < 0x2Au )
    {
      *((LARGE_INTEGER *)&v29 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
      v20 = 1000000LL * (*((_QWORD *)&v29 + 1) - (_QWORD)v29) / PerformanceFrequency.QuadPart;
      _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45)
                                                        + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 47)));
      _InterlockedAdd64(
        (volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45) + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 48)),
        v20);
    }
    goto LABEL_35;
  }
  if ( *(_DWORD *)v14 == 544176197 )
  {
    v19 = VidExoIoControlDriver(
            v12,
            v11,
            (_DWORD)MasterIrp,
            Options,
            (__int64)pszDest,
            Length,
            LowPart,
            (__int64)&pullResult);
    goto LABEL_33;
  }
  if ( *(_DWORD *)v14 != 1853125200 )
  {
    v6 = -1073741816;
    goto LABEL_36;
  }
  v15 = *(_DWORD *)(v14 + 48);
  if ( v15 == 1 || LowPart == 2232784 )
  {
    v16 = *(_QWORD *)(v14 + 10240);
    if ( v16 == PsGetCurrentProcess() || LowPart == 2232419 || LowPart == 2232563 )
    {
      if ( (*(_DWORD *)(v14 + 16) & 0x8000LL) != 0 )
        v17 = VidExoIoControlPartition(
                v14,
                (int)a2,
                v25[0],
                (int)MasterIrp,
                Options,
                pszDest,
                v23,
                LowPart,
                (ULONGLONG)&pullResult);
      else
        v17 = VidIoControlPartition(v14, Options, pszDest, v23, LowPart, (ULONGLONG)&pullResult);
      v6 = v17;
      if ( v13 < 0xD4u )
      {
        *((LARGE_INTEGER *)&v29 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
        v18 = 1000000LL * (*((_QWORD *)&v29 + 1) - (_QWORD)v29) / PerformanceFrequency.QuadPart;
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v14 + 1528)
                                                          + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 292)));
        _InterlockedAdd64(
          (volatile signed __int64 *)(*(_QWORD *)(v14 + 1528) + 8LL * (2 * ((LowPart >> 2) & 0x3FF) + 293)),
          v18);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_d02e4ee7584e3e1b78981b48a2d50880_Traceguids);
      }
      v6 = -1073741790;
    }
  }
  else
  {
    v6 = -1073741811;
    if ( (unsigned int)dword_140064110 > 2
      && (qword_140064120 & 0x100) != 0
      && (qword_140064128 & 0x100) == qword_140064128 )
    {
      v36 = 31;
      v35 = "VidIoControlPartitionIsAllowed";
      v38 = 41;
      v37 = "onecore\\vm\\vid\\sys\\driver\\vidiocontrol.c";
      v48[1] = 0;
      v39 = &v23;
      v25[0] = v15;
      v41 = &v26;
      v23 = 8117;
      v43 = v14 + 656;
      v40 = 4;
      v45 = v48;
      v47 = *(_QWORD *)(v14 + 128);
      v48[0] = *(unsigned __int16 *)(v14 + 120);
      v27 = *(_QWORD *)(v14 + 648);
      v49 = &v27;
      v51 = v25;
      UserData.Ptr = (ULONGLONG)off_140064118;
      *(_DWORD *)&EventDescriptor.Level = 2;
      v26 = -1073741811;
      v42 = 4;
      v44 = 16;
      v46 = 2;
      v50 = 8;
      v52 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 256;
      UserData.Size = *(unsigned __int16 *)off_140064118;
      v32 = word_14005C0FA;
      UserData.Reserved = 2;
      v33 = 110;
      v34 = 1;
      LODWORD(pszDest) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
    }
  }
LABEL_35:
  if ( v6 != 259 )
    goto LABEL_36;
  return v6;
}

```

## disassembly

```asm
0x1400339c0  push    rbp
0x1400339c2  push    rbx
0x1400339c3  push    rsi
0x1400339c4  push    rdi
0x1400339c5  push    r12
0x1400339c7  push    r13
0x1400339c9  push    r14
0x1400339cb  push    r15
0x1400339cd  lea     rbp, [rsp-68h]
0x1400339d2  sub     rsp, 168h
0x1400339d9  mov     rax, cs:__security_cookie
0x1400339e0  xor     rax, rsp
0x1400339e3  mov     [rbp+0A0h+var_50], rax
0x1400339e7  mov     rcx, [rdx+0B8h]
0x1400339ee  xor     eax, eax
0x1400339f0  mov     dword ptr [rsp+1A0h+var_150], eax
0x1400339f4  mov     r14, rdx
0x1400339f7  mov     esi, [rcx+18h]
0x1400339fa  test    sil, 3
0x1400339fe  jz      short loc_140033A0A
0x140033a00  mov     ebx, 0C0000010h
0x140033a05  jmp     loc_140033E2A
0x140033a0a  mov     r12d, [rcx+10h]
0x140033a0e  test    r12d, r12d
0x140033a11  jz      short loc_140033A19
0x140033a13  mov     r13, [rdx+18h]
0x140033a17  jmp     short loc_140033A1C
0x140033a19  mov     r13, rax
0x140033a1c  mov     ebx, [rcx+8]
0x140033a1f  mov     dword ptr [rsp+1A0h+var_150+4], ebx
0x140033a23  test    ebx, ebx
0x140033a25  jz      short loc_140033A2B
0x140033a27  mov     rax, [rdx+18h]
0x140033a2b  mov     [rsp+1A0h+pszDest], rax
0x140033a30  xorps   xmm0, xmm0
0x140033a33  mov     rax, [rcx+30h]
0x140033a37  xor     ecx, ecx; PerformanceFrequency
0x140033a39  mov     qword ptr [rsp+1A0h+var_140], rax
0x140033a3e  movups  [rbp+0A0h+var_118], xmm0
0x140033a42  mov     qword ptr [rbp+0A0h+PerformanceFrequency], rcx
0x140033a46  mov     rdi, [rax+18h]
0x140033a4a  call    cs:__imp_KeQueryPerformanceCounter
0x140033a51  nop     dword ptr [rax+rax+00h]
0x140033a56  mov     r15d, esi
0x140033a59  mov     qword ptr [rbp+0A0h+var_118], rax
0x140033a5d  shr     r15d, 2
0x140033a61  mov     eax, 3FFh
0x140033a66  and     r15w, ax
0x140033a6a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x140033a6e  jz      loc_140033D87
0x140033a74  mov     eax, [rdi]
0x140033a76  cmp     eax, 206F7845h
0x140033a7b  jz      loc_140033D5E
0x140033a81  cmp     eax, 6E747250h
0x140033a86  jnz     loc_140033D54
0x140033a8c  mov     edx, [rdi+30h]
0x140033a8f  cmp     edx, 1
0x140033a92  jz      loc_140033C3D
0x140033a98  cmp     esi, 2211D0h
0x140033a9e  jz      loc_140033C3D
0x140033aa4  mov     eax, cs:dword_140064110
0x140033aaa  mov     ebx, 0C000000Dh
0x140033aaf  cmp     eax, 2
0x140033ab2  jbe     loc_140033E22
0x140033ab8  mov     rcx, cs:qword_140064128
0x140033abf  mov     rax, cs:qword_140064120
0x140033ac6  bt      rax, 8
0x140033acb  jnb     loc_140033E22
0x140033ad1  mov     rax, rcx
0x140033ad4  and     eax, 100h
0x140033ad9  cmp     rax, rcx
0x140033adc  jnz     loc_140033E22
0x140033ae2  lea     rax, aVidiocontrolpa; "VidIoControlPartitionIsAllowed"
0x140033ae9  mov     [rbp+0A0h+var_D8], 1Fh
0x140033af1  mov     [rbp+0A0h+var_E0], rax
0x140033af5  xor     ecx, ecx
0x140033af7  lea     rax, aOnecoreVmVidSy_31; "onecore\\vm\\vid\\sys\\driver\\vidiocon"...
0x140033afe  mov     [rbp+0A0h+var_C8], 29h ; ')'
0x140033b06  mov     [rbp+0A0h+var_D0], rax
0x140033b0a  mov     [rbp+0A0h+var_74], ecx
0x140033b0d  lea     rax, [rsp+1A0h+var_150+4]
0x140033b12  mov     [rbp+0A0h+var_C0], rax
0x140033b16  xor     r9d, r9d; RelatedActivityId
0x140033b19  mov     [rsp+1A0h+var_140], edx
0x140033b1d  lea     rax, [rsp+1A0h+var_138]
0x140033b22  mov     [rbp+0A0h+var_B0], rax
0x140033b26  lea     rdx, [rsp+1A0h+EventDescriptor]; EventDescriptor
0x140033b2b  mov     dword ptr [rsp+1A0h+var_150+4], 1FB5h
0x140033b33  lea     rax, [rdi+290h]
0x140033b3a  mov     [rbp+0A0h+var_A0], rax
0x140033b3e  xor     r8d, r8d; ActivityId
0x140033b41  mov     [rbp+0A0h+var_B8], 4
0x140033b49  lea     rax, [rbp+0A0h+var_78]
0x140033b4d  mov     [rbp+0A0h+var_90], rax
0x140033b51  mov     rax, [rdi+80h]
0x140033b58  mov     [rbp+0A0h+var_80], rax
0x140033b5c  movzx   eax, word ptr [rdi+78h]
0x140033b60  mov     [rbp+0A0h+var_78], eax
0x140033b63  mov     rax, [rdi+288h]
0x140033b6a  mov     [rsp+1A0h+var_130], rax
0x140033b6f  lea     rax, [rsp+1A0h+var_130]
0x140033b74  mov     [rbp+0A0h+var_70], rax
0x140033b78  lea     rax, [rsp+1A0h+var_140]
0x140033b7d  mov     [rbp+0A0h+var_60], rax
0x140033b81  mov     rax, cs:qword_14005C0F0
0x140033b88  movzx   ecx, ax
0x140033b8b  mov     rax, cs:off_140064118
0x140033b92  mov     [rbp+0A0h+var_100.Ptr], rax
0x140033b96  mov     dword ptr [rsp+1A0h+EventDescriptor.Level], ecx
0x140033b9a  lea     rcx, _TraceLoggingMetadata
0x140033ba1  mov     [rsp+1A0h+var_138], ebx
0x140033ba5  mov     [rbp+0A0h+var_A8], 4
0x140033bad  mov     [rbp+0A0h+var_98], 10h
0x140033bb5  mov     [rbp+0A0h+var_88], 2
0x140033bbd  mov     [rbp+0A0h+var_68], 8
0x140033bc5  mov     [rbp+0A0h+var_58], 4
0x140033bcd  mov     dword ptr [rsp+1A0h+EventDescriptor.Id], 0B000000h
0x140033bd5  mov     [rbp+0A0h+EventDescriptor.Keyword], 100h
0x140033bdd  movzx   eax, word ptr [rax]
0x140033be0  mov     [rbp+0A0h+var_100.Size], eax
0x140033be3  lea     rax, word_14005C0FA
0x140033bea  mov     [rbp+0A0h+var_F0], rax
0x140033bee  lea     rax, _TraceLoggingMetadataEnd
0x140033bf5  sub     eax, ecx
0x140033bf7  mov     dword ptr [rbp+0A0h+var_100.0Ch], 2
0x140033bfe  mov     [rbp+0A0h+var_E8], 6Eh ; 'n'
0x140033c05  mov     [rbp+0A0h+var_E4], 1
0x140033c0c  mov     dword ptr [rsp+1A0h+pszDest], eax
0x140033c10  mov     eax, dword ptr [rsp+1A0h+pszDest]
0x140033c14  mov     rcx, cs:RegHandle; RegHandle
0x140033c1b  lea     rax, [rbp+0A0h+var_100]
0x140033c1f  mov     [rsp+1A0h+UserData], rax; UserData
0x140033c24  mov     [rsp+1A0h+UserDataCount], 0Bh; UserDataCount
0x140033c2c  call    cs:__imp_EtwWriteTransfer
0x140033c33  nop     dword ptr [rax+rax+00h]
0x140033c38  jmp     loc_140033E22
0x140033c3d  mov     rbx, [rdi+2800h]
0x140033c44  call    cs:__imp_PsGetCurrentProcess
0x140033c4b  nop     dword ptr [rax+rax+00h]
0x140033c50  cmp     rbx, rax
0x140033c53  jz      short loc_140033CA4
0x140033c55  cmp     esi, 221063h
0x140033c5b  jz      short loc_140033CA4
0x140033c5d  cmp     esi, 2210F3h
0x140033c63  jz      short loc_140033CA4
0x140033c65  mov     rcx, cs:WPP_GLOBAL_Control
0x140033c6c  lea     rax, WPP_GLOBAL_Control
0x140033c73  cmp     rcx, rax
0x140033c76  jz      short loc_140033C9A
0x140033c78  mov     eax, [rcx+2Ch]
0x140033c7b  test    al, 2
0x140033c7d  jz      short loc_140033C9A
0x140033c7f  cmp     byte ptr [rcx+29h], 2
0x140033c83  jb      short loc_140033C9A
0x140033c85  mov     rcx, [rcx+18h]
0x140033c89  lea     r8, WPP_d02e4ee7584e3e1b78981b48a2d50880_Traceguids
0x140033c90  mov     edx, 0Dh
0x140033c95  call    WPP_SF_
0x140033c9a  mov     ebx, 0C0000022h
0x140033c9f  jmp     loc_140033E22
0x140033ca4  mov     eax, [rdi+10h]
0x140033ca7  mov     r9, r13; int
0x140033caa  mov     r8, qword ptr [rsp+1A0h+var_140]; int
0x140033caf  bt      rax, 0Fh
0x140033cb4  lea     rax, [rsp+1A0h+var_150]
0x140033cb9  mov     rdx, r14; int
0x140033cbc  mov     [rsp+1A0h+pullResult], rax; pullResult
0x140033cc1  mov     rcx, rdi; int
0x140033cc4  mov     eax, dword ptr [rsp+1A0h+var_150+4]
0x140033cc8  mov     [rsp+1A0h+var_168], esi; int
0x140033ccc  mov     [rsp+1A0h+var_170], eax; int
0x140033cd0  mov     rax, [rsp+1A0h+pszDest]
0x140033cd5  mov     [rsp+1A0h+UserData], rax; pszDest
0x140033cda  mov     [rsp+1A0h+UserDataCount], r12d; int
0x140033cdf  jnb     short loc_140033CE8
0x140033ce1  call    VidExoIoControlPartition
0x140033ce6  jmp     short loc_140033CED
0x140033ce8  call    VidIoControlPartition
0x140033ced  mov     ebx, eax
0x140033cef  mov     eax, 0D4h
0x140033cf4  cmp     r15w, ax
0x140033cf8  jnb     loc_140033E22
0x140033cfe  lea     rcx, [rbp+0A0h+PerformanceFrequency]; PerformanceFrequency
0x140033d02  call    cs:__imp_KeQueryPerformanceCounter
0x140033d09  nop     dword ptr [rax+rax+00h]
0x140033d0e  mov     qword ptr [rbp+0A0h+var_118+8], rax
0x140033d12  sub     rax, qword ptr [rbp+0A0h+var_118]
0x140033d16  mov     rcx, [rdi+5F8h]
0x140033d1d  imul    rax, 0F4240h
0x140033d24  movzx   r8d, r15w
0x140033d28  cqo
0x140033d2a  idiv    qword ptr [rbp+0A0h+PerformanceFrequency]
0x140033d2e  lea     edx, ds:124h[r8*2]
0x140033d36  lock inc qword ptr [rcx+rdx*8]
0x140033d3b  mov     rcx, [rdi+5F8h]
0x140033d42  lea     edx, ds:125h[r8*2]
0x140033d4a  lock add [rcx+rdx*8], rax
0x140033d4f  jmp     loc_140033E22
0x140033d54  mov     ebx, 0C0000008h
0x140033d59  jmp     loc_140033E2A
0x140033d5e  lea     rax, [rsp+1A0h+var_150]
0x140033d63  mov     r9d, r12d
0x140033d66  mov     qword ptr [rsp+1A0h+var_168], rax
0x140033d6b  mov     r8, r13
0x140033d6e  mov     rax, [rsp+1A0h+pszDest]
0x140033d73  mov     [rsp+1A0h+var_170], esi
0x140033d77  mov     dword ptr [rsp+1A0h+UserData], ebx
0x140033d7b  mov     qword ptr [rsp+1A0h+UserDataCount], rax
0x140033d80  call    VidExoIoControlDriver
0x140033d85  jmp     short loc_140033DBA
0x140033d87  mov     rdx, qword ptr [rsp+1A0h+var_140]
0x140033d8c  lea     rax, [rsp+1A0h+var_150]
0x140033d91  mov     rcx, cs:VidDeviceExtension
0x140033d98  mov     r9d, r12d
0x140033d9b  mov     qword ptr [rsp+1A0h+var_168], rax
0x140033da0  mov     r8, r13
0x140033da3  mov     rax, [rsp+1A0h+pszDest]
0x140033da8  mov     [rsp+1A0h+var_170], esi
0x140033dac  mov     dword ptr [rsp+1A0h+UserData], ebx
0x140033db0  mov     qword ptr [rsp+1A0h+UserDataCount], rax
0x140033db5  call    VidIoControlDriver
0x140033dba  mov     ebx, eax
0x140033dbc  cmp     r15w, 2Ah ; '*'
0x140033dc1  jnb     short loc_140033E22
0x140033dc3  lea     rcx, [rbp+0A0h+PerformanceFrequency]; PerformanceFrequency
0x140033dc7  call    cs:__imp_KeQueryPerformanceCounter
0x140033dce  nop     dword ptr [rax+rax+00h]
0x140033dd3  mov     rcx, cs:VidDeviceExtension
0x140033dda  mov     qword ptr [rbp+0A0h+var_118+8], rax
0x140033dde  sub     rax, qword ptr [rbp+0A0h+var_118]
0x140033de2  imul    rax, 0F4240h
0x140033de9  movzx   r9d, r15w
0x140033ded  cqo
0x140033def  idiv    qword ptr [rbp+0A0h+PerformanceFrequency]
0x140033df3  mov     rdx, [rcx+168h]
0x140033dfa  lea     r8d, ds:2Fh[r9*2]
0x140033e02  lock inc qword ptr [rdx+r8*8]
0x140033e07  mov     rcx, cs:VidDeviceExtension
0x140033e0e  lea     r8d, ds:30h[r9*2]
0x140033e16  mov     rdx, [rcx+168h]
0x140033e1d  lock add [rdx+r8*8], rax
0x140033e22  cmp     ebx, 103h
0x140033e28  jz      short loc_140033E47
0x140033e2a  mov     edx, dword ptr [rsp+1A0h+var_150]
0x140033e2e  mov     rcx, r14; Irp
0x140033e31  mov     [r14+38h], rdx
0x140033e35  xor     edx, edx; PriorityBoost
0x140033e37  mov     [r14+30h], ebx
0x140033e3b  call    cs:__imp_IofCompleteRequest
0x140033e42  nop     dword ptr [rax+rax+00h]
0x140033e47  mov     eax, ebx
0x140033e49  mov     rcx, [rbp+0A0h+var_50]
0x140033e4d  xor     rcx, rsp; StackCookie
0x140033e50  call    __security_check_cookie
0x140033e55  add     rsp, 168h
0x140033e5c  pop     r15
0x140033e5e  pop     r14
0x140033e60  pop     r13
0x140033e62  pop     r12
0x140033e64  pop     rdi
0x140033e65  pop     rsi
0x140033e66  pop     rbx
0x140033e67  pop     rbp
0x140033e68  retn
```
