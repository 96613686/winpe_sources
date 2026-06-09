# VidIoControlFast

- ea: `0x14002da60`
- end: `0x14002df81`
- name: `VidIoControlFast`
- size: `1313`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callees

- `0x140004818`
- `0x140010270`
- `0x140012b3c`
- `0x140021650`
- `0x14002da60`
- `0x140031a08`
- `0x140031d8c`
- `0x140031fa4`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14002dcc0`
- `ntoskrnl!EtwWriteTransfer` at `0x14002dcc0`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002dcd8`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002dcd8`
- `HAL!KeQueryPerformanceCounter` at `0x14002dadc`
- `HAL!KeQueryPerformanceCounter` at `0x14002de0c`
- `HAL!KeQueryPerformanceCounter` at `0x14002df00`
- `HAL!KeQueryPerformanceCounter` at `0x14002dadc`
- `HAL!KeQueryPerformanceCounter` at `0x14002de0c`
- `HAL!KeQueryPerformanceCounter` at `0x14002df00`

## pseudocode

```c
char __fastcall VidIoControlFast(
        __int64 a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        void *a5,
        int a6,
        unsigned int a7,
        __int64 a8)
{
  __int64 v11; // rdi
  LARGE_INTEGER v12; // rcx
  unsigned __int16 v13; // r14
  unsigned __int64 v14; // rdi
  int v15; // edx
  int v16; // ebx
  __int64 v17; // rbx
  __int64 v18; // rax
  int Next; // eax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  __int64 UserDataCount; // [rsp+20h] [rbp-E0h]
  int UserData; // [rsp+28h] [rbp-D8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  void *v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+78h] [rbp-88h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+88h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+A8h] [rbp-58h]
  int v36; // [rsp+ACh] [rbp-54h]
  const char *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  const char *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  int *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  int *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  _DWORD *v47; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+108h] [rbp+8h]
  __int64 v49; // [rsp+110h] [rbp+10h]
  _DWORD v50[2]; // [rsp+118h] [rbp+18h] BYREF
  __int64 *v51; // [rsp+120h] [rbp+20h]
  __int64 v52; // [rsp+128h] [rbp+28h]
  int *v53; // [rsp+130h] [rbp+30h]
  __int64 v54; // [rsp+138h] [rbp+38h]

  PerformanceFrequency.QuadPart = 0;
  v24 = 0;
  v25 = a5;
  v31 = 0;
  if ( (a7 & 3) != 3 )
    return 0;
  v11 = *(_QWORD *)(a1 + 24);
  *(LARGE_INTEGER *)&v31 = KeQueryPerformanceCounter(0);
  v13 = (a7 >> 2) & 0x3FF;
  v14 = v11 & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v14 )
  {
    if ( *(_DWORD *)v14 != 544176197 )
    {
      if ( *(_DWORD *)v14 != 1853125200 )
      {
        v16 = -1073741816;
        goto LABEL_23;
      }
      v15 = *(_DWORD *)(v14 + 48);
      if ( v15 != 1 && a7 != 2232784 )
      {
        v16 = -1073741811;
        if ( (unsigned int)dword_140064110 > 2
          && (qword_140064120 & 0x100) != 0
          && (qword_140064128 & 0x100) == qword_140064128 )
        {
          v38 = 31;
          v37 = "VidIoControlPartitionIsAllowed";
          v40 = 41;
          v39 = "onecore\\vm\\vid\\sys\\driver\\vidiocontrol.c";
          v50[1] = 0;
          v41 = &v26;
          v28 = v15;
          v43 = &v27;
          v26 = 8117;
          v45 = v14 + 656;
          v42 = 4;
          v47 = v50;
          v49 = *(_QWORD *)(v14 + 128);
          v50[0] = *(unsigned __int16 *)(v14 + 120);
          v29 = *(_QWORD *)(v14 + 648);
          v51 = &v29;
          v53 = &v28;
          v33.Ptr = (ULONGLONG)off_140064118;
          *(_DWORD *)&EventDescriptor.Level = 2;
          v27 = -1073741811;
          v44 = 4;
          v46 = 16;
          v48 = 2;
          v52 = 8;
          v54 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 256;
          v33.Size = *(unsigned __int16 *)off_140064118;
          v34 = word_14005C0FA;
          v33.Reserved = 2;
          v35 = 110;
          v36 = 1;
          LODWORD(v25) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &v33);
        }
        goto LABEL_47;
      }
      v17 = *(_QWORD *)(v14 + 10240);
      if ( v17 != PsGetCurrentProcess() && a7 != 2232419 && a7 != 2232563 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_d02e4ee7584e3e1b78981b48a2d50880_Traceguids);
        }
        v16 = -1073741790;
        goto LABEL_47;
      }
      v18 = *(_QWORD *)(v14 + 16) & 0x8000LL;
      if ( a7 == 2232551 )
      {
        if ( v18 )
        {
          v16 = -1073741790;
LABEL_23:
          *(_DWORD *)a8 = v16;
          goto LABEL_24;
        }
        if ( !*(_BYTE *)(v14 + 832) )
        {
          v16 = -1073741811;
          goto LABEL_33;
        }
        Next = VidDispatchInterfaceHandleAndGetNext((int)v14 + 832, a4, (_DWORD)a3, a6, (__int64)&v24);
      }
      else if ( v18 )
      {
        Next = VidExoFastIoControlPartition(v14, a3, a4, (__int64)v25, a6, a7, &v24);
      }
      else
      {
        Next = VidIoControlFastPartition(v14, (char *)a3, a4, v25, a6, a7, &v24);
      }
      v16 = Next;
LABEL_33:
      if ( v13 < 0xD4u )
      {
        *((LARGE_INTEGER *)&v31 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
        v20 = 1000000LL * (*((_QWORD *)&v31 + 1) - (_QWORD)v31) / PerformanceFrequency.QuadPart;
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v14 + 1528)
                                                          + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 292)));
        _InterlockedAdd64(
          (volatile signed __int64 *)(*(_QWORD *)(v14 + 1528) + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 293)),
          v20);
      }
      goto LABEL_47;
    }
    v24 = 0;
    if ( a7 != 2228227 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_53d96694b39d3dfcc5b4a99ce18d6688_Traceguids, a7);
      }
      v16 = -1073741822;
      goto LABEL_45;
    }
    UserData = 2228227;
  }
  else
  {
    UserData = a7;
  }
  LODWORD(UserDataCount) = a6;
  v16 = VidIoControlFastDriver(v12.QuadPart, a3, a4, a5, UserDataCount, UserData, &v24);
LABEL_45:
  if ( v13 < 0x2Au )
  {
    *((LARGE_INTEGER *)&v31 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
    v21 = 1000000LL * (*((_QWORD *)&v31 + 1) - (_QWORD)v31) / PerformanceFrequency.QuadPart;
    _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45)
                                                      + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 47)));
    _InterlockedAdd64(
      (volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45) + 8LL * (2 * ((a7 >> 2) & 0x3FF) + 48)),
      v21);
  }
LABEL_47:
  *(_DWORD *)a8 = v16;
  if ( v16 >= 0 && v16 != 258 )
  {
    *(_QWORD *)(a8 + 8) = v24;
    return 1;
  }
LABEL_24:
  *(_QWORD *)(a8 + 8) = v16;
  return 1;
}

```

## disassembly

```asm
0x14002da60  push    rbp
0x14002da62  push    rbx
0x14002da63  push    rsi
0x14002da64  push    r12
0x14002da66  push    r13
0x14002da68  push    r15
0x14002da6a  lea     rbp, [rsp-58h]
0x14002da6f  sub     rsp, 158h
0x14002da76  mov     rax, cs:__security_cookie
0x14002da7d  xor     rax, rsp
0x14002da80  mov     [rbp+80h+var_40], rax
0x14002da84  mov     esi, [rbp+80h+arg_30]
0x14002da8a  xor     eax, eax
0x14002da8c  mov     rbx, [rbp+80h+arg_20]
0x14002da93  xorps   xmm0, xmm0
0x14002da96  mov     r15, [rbp+80h+arg_38]
0x14002da9d  mov     r13d, r9d
0x14002daa0  mov     qword ptr [rbp+80h+PerformanceFrequency], rax
0x14002daa4  mov     r12, r8
0x14002daa7  mov     [rsp+180h+var_140], rax
0x14002daac  mov     eax, esi
0x14002daae  and     eax, 3
0x14002dab1  mov     [rsp+180h+var_138], rbx
0x14002dab6  movups  [rsp+180h+var_108], xmm0
0x14002dabb  cmp     al, 3
0x14002dabd  jz      short loc_14002DAC6
0x14002dabf  xor     al, al
0x14002dac1  jmp     loc_14002DD6F
0x14002dac6  mov     [rsp+180h+arg_8], rdi
0x14002dace  mov     rdi, [rcx+18h]
0x14002dad2  xor     ecx, ecx; PerformanceFrequency
0x14002dad4  mov     [rsp+180h+var_30], r14
0x14002dadc  call    cs:__imp_KeQueryPerformanceCounter
0x14002dae3  nop     dword ptr [rax+rax+00h]
0x14002dae8  mov     r14d, esi
0x14002daeb  mov     qword ptr [rsp+180h+var_108], rax
0x14002daf0  shr     r14d, 2
0x14002daf4  mov     eax, 3FFh
0x14002daf9  and     r14w, ax
0x14002dafd  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14002db01  jz      loc_14002DECD
0x14002db07  mov     eax, [rdi]
0x14002db09  cmp     eax, 206F7845h
0x14002db0e  jz      loc_14002DE69
0x14002db14  cmp     eax, 6E747250h
0x14002db19  jnz     loc_14002DE5F
0x14002db1f  mov     edx, [rdi+30h]
0x14002db22  cmp     edx, 1
0x14002db25  jz      loc_14002DCD1
0x14002db2b  cmp     esi, 2211D0h
0x14002db31  jz      loc_14002DCD1
0x14002db37  mov     eax, cs:dword_140064110
0x14002db3d  mov     ebx, 0C000000Dh
0x14002db42  cmp     eax, 2
0x14002db45  jbe     loc_14002DF5C
0x14002db4b  mov     rcx, cs:qword_140064128
0x14002db52  mov     rax, cs:qword_140064120
0x14002db59  bt      rax, 8
0x14002db5e  jnb     loc_14002DF5C
0x14002db64  mov     rax, rcx
0x14002db67  and     eax, 100h
0x14002db6c  cmp     rax, rcx
0x14002db6f  jnz     loc_14002DF5C
0x14002db75  lea     rax, aVidiocontrolpa; "VidIoControlPartitionIsAllowed"
0x14002db7c  mov     [rbp+80h+var_C8], 1Fh
0x14002db84  mov     [rbp+80h+var_D0], rax
0x14002db88  xor     ecx, ecx
0x14002db8a  lea     rax, aOnecoreVmVidSy_31; "onecore\\vm\\vid\\sys\\driver\\vidiocon"...
0x14002db91  mov     [rbp+80h+var_B8], 29h ; ')'
0x14002db99  mov     [rbp+80h+var_C0], rax
0x14002db9d  mov     [rbp+80h+var_64], ecx
0x14002dba0  lea     rax, [rsp+180h+var_130]
0x14002dba5  mov     [rbp+80h+var_B0], rax
0x14002dba9  xor     r9d, r9d; RelatedActivityId
0x14002dbac  mov     [rsp+180h+var_128], edx
0x14002dbb0  lea     rax, [rsp+180h+var_12C]
0x14002dbb5  mov     [rbp+80h+var_A0], rax
0x14002dbb9  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x14002dbbe  mov     [rsp+180h+var_130], 1FB5h
0x14002dbc6  lea     rax, [rdi+290h]
0x14002dbcd  mov     [rbp+80h+var_90], rax
0x14002dbd1  xor     r8d, r8d; ActivityId
0x14002dbd4  mov     [rbp+80h+var_A8], 4
0x14002dbdc  lea     rax, [rbp+80h+var_68]
0x14002dbe0  mov     [rbp+80h+var_80], rax
0x14002dbe4  mov     rax, [rdi+80h]
0x14002dbeb  mov     [rbp+80h+var_70], rax
0x14002dbef  movzx   eax, word ptr [rdi+78h]
0x14002dbf3  mov     [rbp+80h+var_68], eax
0x14002dbf6  mov     rax, [rdi+288h]
0x14002dbfd  mov     [rsp+180h+var_120], rax
0x14002dc02  lea     rax, [rsp+180h+var_120]
0x14002dc07  mov     [rbp+80h+var_60], rax
0x14002dc0b  lea     rax, [rsp+180h+var_128]
0x14002dc10  mov     [rbp+80h+var_50], rax
0x14002dc14  mov     rax, cs:qword_14005C0F0
0x14002dc1b  movzx   ecx, ax
0x14002dc1e  mov     rax, cs:off_140064118
0x14002dc25  mov     [rbp+80h+var_F0.Ptr], rax
0x14002dc29  mov     dword ptr [rsp+180h+EventDescriptor.Level], ecx
0x14002dc2d  lea     rcx, _TraceLoggingMetadata
0x14002dc34  mov     [rsp+180h+var_12C], ebx
0x14002dc38  mov     [rbp+80h+var_98], 4
0x14002dc40  mov     [rbp+80h+var_88], 10h
0x14002dc48  mov     [rbp+80h+var_78], 2
0x14002dc50  mov     [rbp+80h+var_58], 8
0x14002dc58  mov     [rbp+80h+var_48], 4
0x14002dc60  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x14002dc68  mov     [rsp+180h+EventDescriptor.Keyword], 100h
0x14002dc71  movzx   eax, word ptr [rax]
0x14002dc74  mov     [rbp+80h+var_F0.Size], eax
0x14002dc77  lea     rax, word_14005C0FA
0x14002dc7e  mov     [rbp+80h+var_E0], rax
0x14002dc82  lea     rax, _TraceLoggingMetadataEnd
0x14002dc89  sub     eax, ecx
0x14002dc8b  mov     dword ptr [rbp+80h+var_F0.0Ch], 2
0x14002dc92  mov     [rbp+80h+var_D8], 6Eh ; 'n'
0x14002dc99  mov     [rbp+80h+var_D4], 1
0x14002dca0  mov     dword ptr [rsp+180h+var_138], eax
0x14002dca4  mov     eax, dword ptr [rsp+180h+var_138]
0x14002dca8  mov     rcx, cs:RegHandle; RegHandle
0x14002dcaf  lea     rax, [rbp+80h+var_F0]
0x14002dcb3  mov     [rsp+180h+UserData], rax; UserData
0x14002dcb8  mov     [rsp+180h+UserDataCount], 0Bh; UserDataCount
0x14002dcc0  call    cs:__imp_EtwWriteTransfer
0x14002dcc7  nop     dword ptr [rax+rax+00h]
0x14002dccc  jmp     loc_14002DF5C
0x14002dcd1  mov     rbx, [rdi+2800h]
0x14002dcd8  call    cs:__imp_PsGetCurrentProcess
0x14002dcdf  nop     dword ptr [rax+rax+00h]
0x14002dce4  cmp     rbx, rax
0x14002dce7  jz      short loc_14002DD38
0x14002dce9  cmp     esi, 221063h
0x14002dcef  jz      short loc_14002DD38
0x14002dcf1  cmp     esi, 2210F3h
0x14002dcf7  jz      short loc_14002DD38
0x14002dcf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dd00  lea     rax, WPP_GLOBAL_Control
0x14002dd07  cmp     rcx, rax
0x14002dd0a  jz      short loc_14002DD2E
0x14002dd0c  mov     eax, [rcx+2Ch]
0x14002dd0f  test    al, 2
0x14002dd11  jz      short loc_14002DD2E
0x14002dd13  cmp     byte ptr [rcx+29h], 2
0x14002dd17  jb      short loc_14002DD2E
0x14002dd19  mov     rcx, [rcx+18h]
0x14002dd1d  lea     r8, WPP_d02e4ee7584e3e1b78981b48a2d50880_Traceguids
0x14002dd24  mov     edx, 0Dh
0x14002dd29  call    WPP_SF_
0x14002dd2e  mov     ebx, 0C0000022h
0x14002dd33  jmp     loc_14002DF5C
0x14002dd38  mov     rax, [rdi+10h]
0x14002dd3c  and     eax, 8000h
0x14002dd41  cmp     esi, 2210E7h
0x14002dd47  jnz     short loc_14002DDC0
0x14002dd49  test    rax, rax
0x14002dd4c  jz      short loc_14002DD8D
0x14002dd4e  mov     ebx, 0C0000022h
0x14002dd53  mov     [r15], ebx
0x14002dd56  movsxd  rax, ebx
0x14002dd59  mov     [r15+8], rax
0x14002dd5d  mov     rdi, [rsp+180h+arg_8]
0x14002dd65  mov     al, 1
0x14002dd67  mov     r14, [rsp+180h+var_30]
0x14002dd6f  mov     rcx, [rbp+80h+var_40]
0x14002dd73  xor     rcx, rsp; StackCookie
0x14002dd76  call    __security_check_cookie
0x14002dd7b  add     rsp, 158h
0x14002dd82  pop     r15
0x14002dd84  pop     r13
0x14002dd86  pop     r12
0x14002dd88  pop     rsi
0x14002dd89  pop     rbx
0x14002dd8a  pop     rbp
0x14002dd8b  retn
0x14002dd8d  lea     rcx, [rdi+340h]
0x14002dd94  movzx   eax, byte ptr [rcx]
0x14002dd97  test    al, al
0x14002dd99  jnz     short loc_14002DDA2
0x14002dd9b  mov     ebx, 0C000000Dh
0x14002dda0  jmp     short loc_14002DDF9
0x14002dda2  mov     r9d, [rbp+80h+arg_28]
0x14002dda9  lea     rax, [rsp+180h+var_140]
0x14002ddae  mov     r8, r12
0x14002ddb1  mov     qword ptr [rsp+180h+UserDataCount], rax
0x14002ddb6  mov     edx, r13d
0x14002ddb9  call    VidDispatchInterfaceHandleAndGetNext
0x14002ddbe  jmp     short loc_14002DDF7
0x14002ddc0  mov     r9, [rsp+180h+var_138]
0x14002ddc5  test    rax, rax
0x14002ddc8  lea     rax, [rsp+180h+var_140]
0x14002ddcd  mov     r8d, r13d
0x14002ddd0  mov     [rsp+180h+var_150], rax; __int64
0x14002ddd5  mov     rdx, r12; Src
0x14002ddd8  mov     eax, [rbp+80h+arg_28]
0x14002ddde  mov     rcx, rdi; int
0x14002dde1  mov     dword ptr [rsp+180h+UserData], esi; int
0x14002dde5  mov     [rsp+180h+UserDataCount], eax; int
0x14002dde9  jz      short loc_14002DDF2
0x14002ddeb  call    VidExoFastIoControlPartition
0x14002ddf0  jmp     short loc_14002DDF7
0x14002ddf2  call    VidIoControlFastPartition
0x14002ddf7  mov     ebx, eax
0x14002ddf9  mov     eax, 0D4h
0x14002ddfe  cmp     r14w, ax
0x14002de02  jnb     loc_14002DF5C
0x14002de08  lea     rcx, [rbp+80h+PerformanceFrequency]; PerformanceFrequency
0x14002de0c  call    cs:__imp_KeQueryPerformanceCounter
0x14002de13  nop     dword ptr [rax+rax+00h]
0x14002de18  mov     qword ptr [rbp+80h+var_108+8], rax
0x14002de1c  sub     rax, qword ptr [rsp+180h+var_108]
0x14002de21  mov     rcx, [rdi+5F8h]
0x14002de28  imul    rax, 0F4240h
0x14002de2f  movzx   r8d, r14w
0x14002de33  cqo
0x14002de35  idiv    qword ptr [rbp+80h+PerformanceFrequency]
0x14002de39  lea     edx, ds:124h[r8*2]
0x14002de41  lock inc qword ptr [rcx+rdx*8]
0x14002de46  mov     rcx, [rdi+5F8h]
0x14002de4d  lea     edx, ds:125h[r8*2]
0x14002de55  lock add [rcx+rdx*8], rax
0x14002de5a  jmp     loc_14002DF5C
0x14002de5f  mov     ebx, 0C0000008h
0x14002de64  jmp     loc_14002DD53
0x14002de69  mov     [rsp+180h+var_140], 0
0x14002de72  cmp     esi, 220003h
0x14002de78  jz      short loc_14002DEB9
0x14002de7a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002de81  lea     rax, WPP_GLOBAL_Control
0x14002de88  cmp     rcx, rax
0x14002de8b  jz      short loc_14002DEB2
0x14002de8d  mov     eax, [rcx+2Ch]
0x14002de90  test    al, 1
0x14002de92  jz      short loc_14002DEB2
0x14002de94  cmp     byte ptr [rcx+29h], 3
0x14002de98  jb      short loc_14002DEB2
0x14002de9a  mov     rcx, [rcx+18h]
0x14002de9e  lea     r8, WPP_53d96694b39d3dfcc5b4a99ce18d6688_Traceguids
0x14002dea5  mov     edx, 0Ch
0x14002deaa  mov     r9d, esi
0x14002dead  call    WPP_SF_d
0x14002deb2  mov     ebx, 0C0000002h
0x14002deb7  jmp     short loc_14002DEF5
0x14002deb9  lea     rax, [rsp+180h+var_140]
0x14002debe  mov     [rsp+180h+var_150], rax
0x14002dec3  mov     dword ptr [rsp+180h+UserData], 220003h
0x14002decb  jmp     short loc_14002DEDB
0x14002decd  lea     rax, [rsp+180h+var_140]
0x14002ded2  mov     [rsp+180h+var_150], rax
0x14002ded7  mov     dword ptr [rsp+180h+UserData], esi
0x14002dedb  mov     eax, [rbp+80h+arg_28]
0x14002dee1  mov     r9, rbx
0x14002dee4  mov     r8d, r13d
0x14002dee7  mov     [rsp+180h+UserDataCount], eax
0x14002deeb  mov     rdx, r12
0x14002deee  call    VidIoControlFastDriver
0x14002def3  mov     ebx, eax
0x14002def5  cmp     r14w, 2Ah ; '*'
0x14002defa  jnb     short loc_14002DF5C
0x14002defc  lea     rcx, [rbp+80h+PerformanceFrequency]; PerformanceFrequency
0x14002df00  call    cs:__imp_KeQueryPerformanceCounter
0x14002df07  nop     dword ptr [rax+rax+00h]
0x14002df0c  mov     rcx, cs:VidDeviceExtension
0x14002df13  mov     qword ptr [rbp+80h+var_108+8], rax
0x14002df17  sub     rax, qword ptr [rsp+180h+var_108]
0x14002df1c  imul    rax, 0F4240h
0x14002df23  movzx   r9d, r14w
0x14002df27  cqo
0x14002df29  idiv    qword ptr [rbp+80h+PerformanceFrequency]
0x14002df2d  mov     rdx, [rcx+168h]
0x14002df34  lea     r8d, ds:2Fh[r9*2]
0x14002df3c  lock inc qword ptr [rdx+r8*8]
0x14002df41  mov     rcx, cs:VidDeviceExtension
0x14002df48  lea     r8d, ds:30h[r9*2]
0x14002df50  mov     rdx, [rcx+168h]
0x14002df57  lock add [rdx+r8*8], rax
0x14002df5c  mov     [r15], ebx
0x14002df5f  test    ebx, ebx
0x14002df61  js      loc_14002DD56
0x14002df67  cmp     ebx, 102h
0x14002df6d  jz      loc_14002DD56
0x14002df73  mov     rcx, [rsp+180h+var_140]
0x14002df78  mov     [r15+8], rcx
0x14002df7c  jmp     loc_14002DD5D
```
