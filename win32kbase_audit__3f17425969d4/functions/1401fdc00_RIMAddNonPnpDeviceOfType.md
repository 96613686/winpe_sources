# RIMAddNonPnpDeviceOfType

- ea: `0x1401fdc00`
- end: `0x1401fe11a`
- name: `RIMAddNonPnpDeviceOfType`
- size: `1306`
- prototype: `__int64 __fastcall(char *, struct _UNICODE_STRING *, unsigned int, int, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140049df8`
- `0x140049ec0`
- `0x140062ff0`
- `0x1400682c0`
- `0x14007b930`
- `0x14007efd0`
- `0x140092750`
- `0x1400dd4cc`
- `0x1400ff080`
- `0x140137f60`
- `0x1401a0318`
- `0x1401aab9c`
- `0x1401fdc00`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fddb6`
- `ntoskrnl!ProbeForRead` at `0x1401fddb6`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fde69`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fde69`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fde12`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fde12`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fdf83`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fdf83`
- `WIN32K!W32GetUserSessionState` at `0x1401fdc6d`
- `WIN32K!W32GetUserSessionState` at `0x1401fdfc1`
- `WIN32K!W32GetUserSessionState` at `0x1401fe062`
- `WIN32K!W32GetUserSessionState` at `0x1401fe0ef`
- `WIN32K!W32GetUserSessionState` at `0x1401fdc6d`
- `WIN32K!W32GetUserSessionState` at `0x1401fdfc1`
- `WIN32K!W32GetUserSessionState` at `0x1401fe062`
- `WIN32K!W32GetUserSessionState` at `0x1401fe0ef`

## pseudocode

```c
__int64 __fastcall RIMAddNonPnpDeviceOfType(char *a1, struct _UNICODE_STRING *a2, unsigned int a3, int a4, _QWORD *a5)
{
  char v5; // bl
  char v6; // r14
  __int64 UserSessionState; // rax
  __int64 v8; // rdx
  int v9; // r14d
  struct RawInputManagerObject *v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rdx
  struct _UNICODE_STRING *p_DestinationString; // r12
  int v14; // ebx
  int ULongFromUser; // ebx
  char v16; // bl
  bool v17; // r15
  __int64 v18; // rax
  int v19; // r8d
  int v20; // edx
  char v22; // bl
  __int64 v23; // r9
  char v24; // bl
  __int64 v25; // r9
  char v26; // [rsp+50h] [rbp-98h]
  char v27; // [rsp+50h] [rbp-98h]
  struct RIMDEV *v28; // [rsp+58h] [rbp-90h] BYREF
  PVOID Object; // [rsp+60h] [rbp-88h] BYREF
  UNICODE_STRING SourceString; // [rsp+68h] [rbp-80h] BYREF
  int v31; // [rsp+78h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-68h] BYREF
  struct _UNICODE_STRING *v33; // [rsp+90h] [rbp-58h]
  __int64 v34; // [rsp+98h] [rbp-50h]
  __int128 v35; // [rsp+A0h] [rbp-48h]

  Object = 0;
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v5 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v5 = 0;
  }
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(a1, a2);
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v5,
      v6,
      *(_QWORD *)(UserSessionState + 19408),
      4u,
      1u,
      0x1Au,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
  }
  v9 = RawInputManagerObjectResolveHandle(a1, 3u, 1, &Object);
  if ( v9 >= 0 )
  {
    v10 = (struct RawInputManagerObject *)Object;
    v34 = (__int64)Object + 96;
    RIMLockExclusive((__int64)Object + 96);
    if ( *((_BYTE *)v10 + 73) || *((_BYTE *)v10 + 74) )
    {
      v9 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v24 = 0;
      }
      v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v25 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v11) + 19408);
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v24,
          v27,
          v25,
          3u,
          1u,
          0x1Cu,
          (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
      }
    }
    else if ( ((unsigned int)DeviceTypeToRimInputType(a3) & *((_DWORD *)v10 + 19)) != 0 )
    {
      SourceString = 0;
      p_DestinationString = 0;
      v33 = 0;
      DestinationString = 0;
      v14 = a4;
      if ( a4 )
      {
        v35 = 0;
        ULongFromUser = RtlReadULongFromUser(a2);
        LODWORD(v35) = ULongFromUser;
        *((_QWORD *)&v35 + 1) = RtlReadULong64FromUser(&a2->Buffer);
        *(_DWORD *)&SourceString.Length = ULongFromUser;
        *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v35);
        SourceString.Buffer = (PWSTR)*((_QWORD *)&v35 + 1);
        ProbeForRead(*((volatile void **)&v35 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
        if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
        {
          if ( (SourceString.Length & 1) != 0 )
          {
            LODWORD(v28) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM((__int64)"IXPTelAssert", 0x20000, 833);
          }
          ExRaiseAccessViolation();
        }
        DestinationString.MaximumLength = SourceString.Length;
        DestinationString.Length = SourceString.Length;
        DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(256, SourceString.Length, 0x706D7452u);
        if ( DestinationString.Buffer )
        {
          RtlCopyUnicodeString(&DestinationString, &SourceString);
          p_DestinationString = &DestinationString;
          v33 = &DestinationString;
        }
        else
        {
          v9 = -1073741801;
          v31 = -1073741801;
        }
        v14 = a4;
      }
      else
      {
        p_DestinationString = a2;
      }
      if ( v9 >= 0 )
      {
        v28 = 0;
        v9 = RIMCreateDev(v10, a3, p_DestinationString, 1, 0, 0, &v28);
        if ( v9 >= 0 )
        {
          *((_DWORD *)v28 + 42) |= 1u;
          v9 = rimOnPnpArrived(v10, v28, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          if ( v9 >= 0 )
          {
            if ( v14 )
              RtlWriteULong64ToUser(a5, *((_QWORD *)v28 + 2));
            else
              *a5 = *((_QWORD *)v28 + 2);
          }
          if ( v9 < 0 )
            RIMFreeDev(v10, v28);
        }
      }
      if ( DestinationString.Buffer )
        GreDeleteFastMutex((_DWORD *)DestinationString.Buffer, v12);
    }
    else
    {
      v9 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v22 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v22 = 0;
      }
      v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v22 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v23 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v12) + 19408);
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v22,
          v26,
          v23,
          3u,
          1u,
          0x1Bu,
          (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
      }
    }
    RIMUnlockExclusive(v34);
    ObfDereferenceObject(v10);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v16 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v16 = 0;
  }
  v17 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v18 = W32GetUserSessionState(WPP_GLOBAL_Control, v8);
    LOBYTE(v19) = v17;
    LOBYTE(v20) = v16;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v20,
      v19,
      *(_QWORD *)(v18 + 19408),
      4,
      1,
      29,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1401fdc00  mov     rax, rsp
0x1401fdc03  mov     [rax+20h], r9d
0x1401fdc07  mov     [rax+18h], r8d
0x1401fdc0b  mov     [rax+10h], rdx
0x1401fdc0f  mov     [rax+8], rcx
0x1401fdc13  push    rbx
0x1401fdc14  push    rdi
0x1401fdc15  push    r12
0x1401fdc17  push    r13
0x1401fdc19  push    r14
0x1401fdc1b  push    r15
0x1401fdc1d  sub     rsp, 0B8h
0x1401fdc24  xor     edi, edi
0x1401fdc26  mov     [rsp+0E8h+Object], rdi
0x1401fdc2b  lea     r13, WPP_GLOBAL_Control
0x1401fdc32  mov     r10, cs:WPP_GLOBAL_Control
0x1401fdc39  cmp     r10, r13
0x1401fdc3c  jz      short loc_1401FDC4F
0x1401fdc3e  mov     eax, [r10+2Ch]
0x1401fdc42  test    al, 1
0x1401fdc44  jz      short loc_1401FDC4F
0x1401fdc46  cmp     byte ptr [r10+29h], 4
0x1401fdc4b  mov     bl, 1
0x1401fdc4d  jnb     short loc_1401FDC52
0x1401fdc4f  mov     bl, dil
0x1401fdc52  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fdc59  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fdc60  setnz   r14b
0x1401fdc64  test    bl, bl
0x1401fdc66  jnz     short loc_1401FDC6D
0x1401fdc68  test    r14b, r14b
0x1401fdc6b  jz      short loc_1401FDCB5
0x1401fdc6d  call    cs:__imp_W32GetUserSessionState
0x1401fdc74  nop     dword ptr [rax+rax+00h]
0x1401fdc79  mov     r9, [rax+4BD0h]
0x1401fdc80  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fdc87  mov     [rsp+0E8h+var_B0], r15
0x1401fdc8c  mov     word ptr [rsp+0E8h+var_B8], 1Ah
0x1401fdc93  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fdc9b  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1401fdca0  mov     r8b, r14b
0x1401fdca3  mov     dl, bl
0x1401fdca5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fdcac  mov     rcx, [rcx+18h]
0x1401fdcb0  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fdcb5  lea     r9, [rsp+0E8h+Object]
0x1401fdcba  mov     edx, 3
0x1401fdcbf  lea     r8d, [rdx-2]
0x1401fdcc3  mov     rcx, [rsp+0E8h+arg_0]
0x1401fdccb  call    RawInputManagerObjectResolveHandle
0x1401fdcd0  mov     r14d, eax
0x1401fdcd3  test    eax, eax
0x1401fdcd5  js      loc_1401FDF8F
0x1401fdcdb  mov     r15, [rsp+0E8h+Object]
0x1401fdce0  lea     rax, [r15+60h]
0x1401fdce4  mov     [rsp+0E8h+var_50], rax
0x1401fdcec  mov     rcx, rax
0x1401fdcef  call    RIMLockExclusive
0x1401fdcf4  cmp     [r15+49h], dil
0x1401fdcf8  jnz     loc_1401FE0B1
0x1401fdcfe  cmp     [r15+4Ah], dil
0x1401fdd02  jnz     loc_1401FE0B1
0x1401fdd08  mov     ecx, [rsp+0E8h+arg_10]
0x1401fdd0f  call    DeviceTypeToRimInputType
0x1401fdd14  test    [r15+4Ch], eax
0x1401fdd18  jz      loc_1401FE024
0x1401fdd1e  xorps   xmm0, xmm0
0x1401fdd21  movups  xmmword ptr [rsp+0E8h+SourceString.Length], xmm0
0x1401fdd26  mov     r12, rdi
0x1401fdd29  mov     [rsp+0E8h+var_58], rdi
0x1401fdd31  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1401fdd39  mov     ebx, [rsp+0E8h+arg_18]
0x1401fdd40  test    ebx, ebx
0x1401fdd42  jnz     short loc_1401FDD51
0x1401fdd44  mov     r12, [rsp+0E8h+arg_8]
0x1401fdd4c  jmp     loc_1401FDE9E
0x1401fdd51  movups  [rsp+0E8h+var_48], xmm0
0x1401fdd59  mov     rcx, [rsp+0E8h+arg_8]
0x1401fdd61  call    RtlReadULongFromUser
0x1401fdd66  mov     ebx, eax
0x1401fdd68  mov     dword ptr [rsp+0E8h+var_48], ebx
0x1401fdd6f  mov     rcx, [rsp+0E8h+arg_8]
0x1401fdd77  add     rcx, 8
0x1401fdd7b  call    RtlReadULong64FromUser
0x1401fdd80  mov     qword ptr [rsp+0E8h+var_48+8], rax
0x1401fdd88  movzx   edx, bx
0x1401fdd8b  mov     [rsp+0E8h+SourceString.Length], dx
0x1401fdd90  shr     ebx, 10h
0x1401fdd93  mov     [rsp+0E8h+SourceString.MaximumLength], bx
0x1401fdd98  mov     ecx, dword ptr [rsp+0E8h+var_48+4]
0x1401fdd9f  mov     dword ptr [rsp+0E8h+SourceString+4], ecx
0x1401fdda3  mov     [rsp+0E8h+SourceString.Buffer], rax
0x1401fdda8  mov     ebx, 2
0x1401fddad  add     rdx, rbx; Length
0x1401fddb0  mov     r8d, ebx; Alignment
0x1401fddb3  mov     rcx, rax; Address
0x1401fddb6  call    cs:__imp_ProbeForRead
0x1401fddbd  nop     dword ptr [rax+rax+00h]
0x1401fddc2  movzx   eax, [rsp+0E8h+SourceString.Length]
0x1401fddc7  cmp     ax, [rsp+0E8h+SourceString.MaximumLength]
0x1401fddcc  ja      short loc_1401FDE44
0x1401fddce  mov     byte ptr [rsp+0E8h+SourceString.Length], al
0x1401fddd2  test    al, 1
0x1401fddd4  jnz     short loc_1401FDE44
0x1401fddd6  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x1401fddde  mov     [rsp+0E8h+DestinationString.Length], ax
0x1401fdde6  mov     edx, eax; unsigned __int64
0x1401fdde8  mov     ecx, 100h; unsigned __int64
0x1401fdded  mov     r8d, 706D7452h; unsigned int
0x1401fddf3  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fddf8  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x1401fde00  test    rax, rax
0x1401fde03  jz      short loc_1401FDE30
0x1401fde05  lea     rdx, [rsp+0E8h+SourceString]; SourceString
0x1401fde0a  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x1401fde12  call    cs:__imp_RtlCopyUnicodeString
0x1401fde19  nop     dword ptr [rax+rax+00h]
0x1401fde1e  lea     r12, [rsp+0E8h+DestinationString]
0x1401fde26  mov     [rsp+0E8h+var_58], r12
0x1401fde2e  jmp     short loc_1401FDE3B
0x1401fde30  mov     r14d, 0C0000017h
0x1401fde36  mov     [rsp+0E8h+var_70], r14d
0x1401fde3b  mov     ebx, [rsp+0E8h+arg_18]
0x1401fde42  jmp     short loc_1401FDE9E
0x1401fde44  test    byte ptr [rsp+0E8h+SourceString.Length], 1
0x1401fde49  jz      short loc_1401FDE69
0x1401fde4b  mov     dword ptr [rsp+0E8h+var_90], 20000h
0x1401fde53  mov     r8d, 341h
0x1401fde59  mov     edx, dword ptr [rsp+0E8h+var_90]
0x1401fde5d  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fde64  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fde69  call    cs:__imp_ExRaiseAccessViolation
0x1401fde70  nop     dword ptr [rax+rax+00h]
0x1401fde75  nop
0x1401fde76  mov     r14d, 0C000000Dh
0x1401fde7c  mov     [rsp+0E8h+var_70], r14d
0x1401fde81  xor     edi, edi
0x1401fde83  lea     r13, WPP_GLOBAL_Control
0x1401fde8a  mov     r15, [rsp+0E8h+Object]
0x1401fde8f  mov     r12, [rsp+0E8h+var_58]
0x1401fde97  mov     ebx, [rsp+0E8h+arg_18]
0x1401fde9e  test    r14d, r14d
0x1401fdea1  js      loc_1401FDF5A
0x1401fdea7  mov     [rsp+0E8h+var_90], rdi
0x1401fdeac  lea     rax, [rsp+0E8h+var_90]
0x1401fdeb1  mov     [rsp+0E8h+var_B8], rax; __int64
0x1401fdeb6  mov     [rsp+0E8h+var_C0], rdi; __int64
0x1401fdebb  mov     [rsp+0E8h+var_C8], edi; int
0x1401fdebf  mov     r9d, 1
0x1401fdec5  mov     r8, r12
0x1401fdec8  mov     edx, [rsp+0E8h+arg_10]
0x1401fdecf  mov     rcx, r15; struct RawInputManagerObject *
0x1401fded2  call    RIMCreateDev
0x1401fded7  mov     r14d, eax
0x1401fdeda  test    eax, eax
0x1401fdedc  js      short loc_1401FDF5A
0x1401fdede  mov     rax, [rsp+0E8h+var_90]
0x1401fdee3  or      dword ptr [rax+0A8h], 1
0x1401fdeea  or      r8, 0FFFFFFFFFFFFFFFFh; Handle
0x1401fdeee  mov     rdx, [rsp+0E8h+var_90]; struct RIMDEV *
0x1401fdef3  mov     rcx, r15; struct RawInputManagerObject *
0x1401fdef6  call    rimOnPnpArrived
0x1401fdefb  mov     r14d, eax
0x1401fdefe  test    eax, eax
0x1401fdf00  js      short loc_1401FDF48
0x1401fdf02  test    ebx, ebx
0x1401fdf04  jnz     short loc_1401FDF1C
0x1401fdf06  mov     rax, [rsp+0E8h+var_90]
0x1401fdf0b  mov     rcx, [rax+10h]
0x1401fdf0f  mov     rax, [rsp+0E8h+arg_20]
0x1401fdf17  mov     [rax], rcx
0x1401fdf1a  jmp     short loc_1401FDF48
0x1401fdf1c  mov     rdx, [rsp+0E8h+var_90]
0x1401fdf21  mov     rdx, [rdx+10h]
0x1401fdf25  mov     rcx, [rsp+0E8h+arg_20]
0x1401fdf2d  call    RtlWriteULong64ToUser
0x1401fdf32  jmp     short loc_1401FDF48
0x1401fdf34  xor     edi, edi
0x1401fdf36  mov     r14d, 0C000000Dh
0x1401fdf3c  lea     r13, WPP_GLOBAL_Control
0x1401fdf43  mov     r15, [rsp+0E8h+Object]
0x1401fdf48  test    r14d, r14d
0x1401fdf4b  jns     short loc_1401FDF5A
0x1401fdf4d  mov     rdx, [rsp+0E8h+var_90]; struct RIMDEV *
0x1401fdf52  mov     rcx, r15; struct RawInputManagerObject *
0x1401fdf55  call    RIMFreeDev
0x1401fdf5a  mov     rcx, [rsp+0E8h+DestinationString.Buffer]; Buffer
0x1401fdf62  test    rcx, rcx
0x1401fdf65  jz      short loc_1401FDF6C
0x1401fdf67  call    GreDeleteFastMutex
0x1401fdf6c  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fdf73  mov     rcx, [rsp+0E8h+var_50]
0x1401fdf7b  call    RIMUnlockExclusive
0x1401fdf80  mov     rcx, r15; Object
0x1401fdf83  call    cs:__imp_ObfDereferenceObject
0x1401fdf8a  nop     dword ptr [rax+rax+00h]
0x1401fdf8f  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fdf96  cmp     rcx, r13
0x1401fdf99  jz      short loc_1401FDFAA
0x1401fdf9b  mov     eax, [rcx+2Ch]
0x1401fdf9e  test    al, 1
0x1401fdfa0  jz      short loc_1401FDFAA
0x1401fdfa2  cmp     byte ptr [rcx+29h], 4
0x1401fdfa6  mov     bl, 1
0x1401fdfa8  jnb     short loc_1401FDFAD
0x1401fdfaa  mov     bl, dil
0x1401fdfad  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fdfb4  setnz   r15b
0x1401fdfb8  test    bl, bl
0x1401fdfba  jnz     short loc_1401FDFC1
0x1401fdfbc  test    r15b, r15b
0x1401fdfbf  jz      short loc_1401FE00E
0x1401fdfc1  call    cs:__imp_W32GetUserSessionState
0x1401fdfc8  nop     dword ptr [rax+rax+00h]
0x1401fdfcd  mov     r9, [rax+4BD0h]
0x1401fdfd4  mov     [rsp+0E8h+var_A8], r14d
0x1401fdfd9  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fdfe0  mov     [rsp+0E8h+var_B0], rax
0x1401fdfe5  mov     word ptr [rsp+0E8h+var_B8], 1Dh
0x1401fdfec  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fdff4  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1401fdff9  mov     r8b, r15b
0x1401fdffc  mov     dl, bl
0x1401fdffe  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fe005  mov     rcx, [rcx+18h]
0x1401fe009  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401fe00e  mov     eax, r14d
0x1401fe011  add     rsp, 0B8h
0x1401fe018  pop     r15
0x1401fe01a  pop     r14
0x1401fe01c  pop     r13
0x1401fe01e  pop     r12
0x1401fe020  pop     rdi
0x1401fe021  pop     rbx
0x1401fe022  retn
0x1401fe024  mov     r14d, 0C00000BBh
0x1401fe02a  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fe031  cmp     rcx, r13
0x1401fe034  jz      short loc_1401FE045
0x1401fe036  mov     eax, [rcx+2Ch]
0x1401fe039  test    al, 1
0x1401fe03b  jz      short loc_1401FE045
0x1401fe03d  cmp     byte ptr [rcx+29h], 3
0x1401fe041  mov     bl, 1
0x1401fe043  jnb     short loc_1401FE048
0x1401fe045  mov     bl, dil
0x1401fe048  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fe04f  setnz   al
0x1401fe052  mov     [rsp+0E8h+var_98], al
0x1401fe056  test    bl, bl
0x1401fe058  jnz     short loc_1401FE062
0x1401fe05a  test    al, al
0x1401fe05c  jz      loc_1401FDF73
0x1401fe062  call    cs:__imp_W32GetUserSessionState
0x1401fe069  nop     dword ptr [rax+rax+00h]
0x1401fe06e  mov     r9, [rax+4BD0h]
0x1401fe075  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fe07c  mov     [rsp+0E8h+var_B0], rax
0x1401fe081  mov     word ptr [rsp+0E8h+var_B8], 1Bh
0x1401fe088  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fe090  mov     byte ptr [rsp+0E8h+var_C8], 3
0x1401fe095  mov     r8b, [rsp+0E8h+var_98]
0x1401fe09a  mov     dl, bl
0x1401fe09c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fe0a3  mov     rcx, [rcx+18h]
0x1401fe0a7  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fe0ac  jmp     loc_1401FDF73
0x1401fe0b1  mov     r14d, 0C00000BBh
0x1401fe0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fe0be  cmp     rcx, r13
0x1401fe0c1  jz      short loc_1401FE0D2
0x1401fe0c3  mov     eax, [rcx+2Ch]
0x1401fe0c6  test    al, 1
0x1401fe0c8  jz      short loc_1401FE0D2
0x1401fe0ca  cmp     byte ptr [rcx+29h], 3
0x1401fe0ce  mov     bl, 1
0x1401fe0d0  jnb     short loc_1401FE0D5
0x1401fe0d2  mov     bl, dil
0x1401fe0d5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fe0dc  setnz   al
0x1401fe0df  mov     [rsp+0E8h+var_98], al
0x1401fe0e3  test    bl, bl
0x1401fe0e5  jnz     short loc_1401FE0EF
0x1401fe0e7  test    al, al
0x1401fe0e9  jz      loc_1401FDF73
0x1401fe0ef  call    cs:__imp_W32GetUserSessionState
0x1401fe0f6  nop     dword ptr [rax+rax+00h]
0x1401fe0fb  mov     r9, [rax+4BD0h]
0x1401fe102  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fe109  mov     [rsp+0E8h+var_B0], rax
0x1401fe10e  mov     word ptr [rsp+0E8h+var_B8], 1Ch
0x1401fe115  jmp     loc_1401FE088
```
