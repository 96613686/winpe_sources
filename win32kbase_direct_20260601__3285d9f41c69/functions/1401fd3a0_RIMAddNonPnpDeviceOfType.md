# RIMAddNonPnpDeviceOfType

- ea: `0x1401fd3a0`
- end: `0x1401fd8ba`
- name: `RIMAddNonPnpDeviceOfType`
- size: `1306`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x140065730`
- `0x1400729c8`
- `0x140072a90`
- `0x1400951c0`
- `0x1400e0370`
- `0x1400f9f50`
- `0x140135db0`
- `0x140184c20`
- `0x14019e958`
- `0x1401a9f9c`
- `0x1401fd3a0`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fd556`
- `ntoskrnl!ProbeForRead` at `0x1401fd556`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fd609`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fd609`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fd5b2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fd5b2`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fd723`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fd723`
- `WIN32K!W32GetUserSessionState` at `0x1401fd40d`
- `WIN32K!W32GetUserSessionState` at `0x1401fd761`
- `WIN32K!W32GetUserSessionState` at `0x1401fd802`
- `WIN32K!W32GetUserSessionState` at `0x1401fd88f`
- `WIN32K!W32GetUserSessionState` at `0x1401fd40d`
- `WIN32K!W32GetUserSessionState` at `0x1401fd761`
- `WIN32K!W32GetUserSessionState` at `0x1401fd802`
- `WIN32K!W32GetUserSessionState` at `0x1401fd88f`

## pseudocode

```c
__int64 __fastcall RIMAddNonPnpDeviceOfType(__int64 a1, __int64 a2, __int64 a3, int a4, _QWORD *a5)
{
  char v5; // bl
  bool v6; // r14
  __int64 UserSessionState; // rax
  int v8; // r8d
  int v9; // edx
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // r14d
  struct RawInputManagerObject *v13; // r15
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ebx
  int ULongFromUser; // ebx
  char v20; // bl
  bool v21; // r15
  __int64 v22; // rax
  int v23; // r8d
  int v24; // edx
  char v26; // bl
  int v27; // edx
  int v28; // r8d
  __int64 v29; // r9
  __int16 v30; // [rsp+30h] [rbp-B8h]
  bool v31; // [rsp+50h] [rbp-98h]
  struct RIMDEV *v32; // [rsp+58h] [rbp-90h] BYREF
  PVOID Object; // [rsp+60h] [rbp-88h] BYREF
  UNICODE_STRING SourceString; // [rsp+68h] [rbp-80h] BYREF
  int v35; // [rsp+78h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-68h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+90h] [rbp-58h]
  char *v38; // [rsp+98h] [rbp-50h]
  __int128 v39; // [rsp+A0h] [rbp-48h]
  unsigned int v42; // [rsp+100h] [rbp+18h]

  v42 = a3;
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
    UserSessionState = W32GetUserSessionState(a1, a2, a3);
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v9,
      v8,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      26,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
  }
  v12 = RawInputManagerObjectResolveHandle(a1, 3, 1, &Object);
  if ( v12 >= 0 )
  {
    v13 = (struct RawInputManagerObject *)Object;
    v38 = (char *)Object + 96;
    RIMLockExclusive((char *)Object + 96);
    if ( *((_BYTE *)v13 + 73) || *((_BYTE *)v13 + 74) )
    {
      v12 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v26 = 0;
      }
      v31 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v26 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_32;
      v29 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v14, v15) + 19408);
      v30 = 28;
    }
    else
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(v42) & *((_DWORD *)v13 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        v18 = a4;
        if ( a4 )
        {
          v39 = 0;
          ULongFromUser = RtlReadULongFromUser(a2);
          LODWORD(v39) = ULongFromUser;
          *((_QWORD *)&v39 + 1) = RtlReadULong64FromUser(a2 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v39);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v39 + 1);
          ProbeForRead(*((volatile void **)&v39 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
          {
            if ( (SourceString.Length & 1) != 0 )
            {
              LODWORD(v32) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 833);
            }
            ExRaiseAccessViolation();
          }
          DestinationString.MaximumLength = SourceString.Length;
          DestinationString.Length = SourceString.Length;
          DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(0x100u, SourceString.Length, 0x706D7452u);
          if ( DestinationString.Buffer )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            p_DestinationString = &DestinationString;
          }
          else
          {
            v12 = -1073741801;
            v35 = -1073741801;
          }
          v18 = a4;
        }
        if ( v12 >= 0 )
        {
          v32 = 0;
          v12 = RIMCreateDev(v13, 0, 0, (__int64)&v32);
          if ( v12 >= 0 )
          {
            *((_DWORD *)v32 + 42) |= 1u;
            v12 = rimOnPnpArrived(v13, v32, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
            if ( v12 >= 0 )
            {
              if ( v18 )
                RtlWriteULong64ToUser(a5, *((_QWORD *)v32 + 2));
              else
                *a5 = *((_QWORD *)v32 + 2);
            }
            if ( v12 < 0 )
              RIMFreeDev(v13, v32);
          }
        }
        if ( DestinationString.Buffer )
          GreDeleteFastMutex(DestinationString.Buffer);
        goto LABEL_32;
      }
      v12 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v26 = 0;
      }
      v31 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v26 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_32;
      v29 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v16, v17) + 19408);
      v30 = 27;
    }
    LOBYTE(v28) = v31;
    LOBYTE(v27) = v26;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v27,
      v28,
      v29,
      3,
      1,
      v30,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_32:
    RIMUnlockExclusive(v38);
    ObfDereferenceObject(v13);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v20 = 0;
  }
  v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = W32GetUserSessionState(WPP_GLOBAL_Control, v10, v11);
    LOBYTE(v23) = v21;
    LOBYTE(v24) = v20;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v24,
      v23,
      *(_QWORD *)(v22 + 19408),
      4,
      1,
      29,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1401fd3a0  mov     rax, rsp
0x1401fd3a3  mov     [rax+20h], r9d
0x1401fd3a7  mov     [rax+18h], r8d
0x1401fd3ab  mov     [rax+10h], rdx
0x1401fd3af  mov     [rax+8], rcx
0x1401fd3b3  push    rbx
0x1401fd3b4  push    rdi
0x1401fd3b5  push    r12
0x1401fd3b7  push    r13
0x1401fd3b9  push    r14
0x1401fd3bb  push    r15
0x1401fd3bd  sub     rsp, 0B8h
0x1401fd3c4  xor     edi, edi
0x1401fd3c6  mov     [rsp+0E8h+Object], rdi
0x1401fd3cb  lea     r13, WPP_GLOBAL_Control
0x1401fd3d2  mov     r10, cs:WPP_GLOBAL_Control
0x1401fd3d9  cmp     r10, r13
0x1401fd3dc  jz      short loc_1401FD3EF
0x1401fd3de  mov     eax, [r10+2Ch]
0x1401fd3e2  test    al, 1
0x1401fd3e4  jz      short loc_1401FD3EF
0x1401fd3e6  cmp     byte ptr [r10+29h], 4
0x1401fd3eb  mov     bl, 1
0x1401fd3ed  jnb     short loc_1401FD3F2
0x1401fd3ef  mov     bl, dil
0x1401fd3f2  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fd3f9  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fd400  setnz   r14b
0x1401fd404  test    bl, bl
0x1401fd406  jnz     short loc_1401FD40D
0x1401fd408  test    r14b, r14b
0x1401fd40b  jz      short loc_1401FD455
0x1401fd40d  call    cs:__imp_W32GetUserSessionState
0x1401fd414  nop     dword ptr [rax+rax+00h]
0x1401fd419  mov     r9, [rax+4BD0h]
0x1401fd420  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fd427  mov     [rsp+0E8h+var_B0], r15
0x1401fd42c  mov     word ptr [rsp+0E8h+var_B8], 1Ah
0x1401fd433  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fd43b  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1401fd440  mov     r8b, r14b
0x1401fd443  mov     dl, bl
0x1401fd445  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd44c  mov     rcx, [rcx+18h]
0x1401fd450  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fd455  lea     r9, [rsp+0E8h+Object]
0x1401fd45a  mov     edx, 3
0x1401fd45f  lea     r8d, [rdx-2]
0x1401fd463  mov     rcx, [rsp+0E8h+arg_0]
0x1401fd46b  call    RawInputManagerObjectResolveHandle
0x1401fd470  mov     r14d, eax
0x1401fd473  test    eax, eax
0x1401fd475  js      loc_1401FD72F
0x1401fd47b  mov     r15, [rsp+0E8h+Object]
0x1401fd480  lea     rax, [r15+60h]
0x1401fd484  mov     [rsp+0E8h+var_50], rax
0x1401fd48c  mov     rcx, rax
0x1401fd48f  call    RIMLockExclusive
0x1401fd494  cmp     [r15+49h], dil
0x1401fd498  jnz     loc_1401FD851
0x1401fd49e  cmp     [r15+4Ah], dil
0x1401fd4a2  jnz     loc_1401FD851
0x1401fd4a8  mov     ecx, [rsp+0E8h+arg_10]
0x1401fd4af  call    DeviceTypeToRimInputType
0x1401fd4b4  test    [r15+4Ch], eax
0x1401fd4b8  jz      loc_1401FD7C4
0x1401fd4be  xorps   xmm0, xmm0
0x1401fd4c1  movups  xmmword ptr [rsp+0E8h+SourceString.Length], xmm0
0x1401fd4c6  mov     r12, rdi
0x1401fd4c9  mov     [rsp+0E8h+var_58], rdi
0x1401fd4d1  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1401fd4d9  mov     ebx, [rsp+0E8h+arg_18]
0x1401fd4e0  test    ebx, ebx
0x1401fd4e2  jnz     short loc_1401FD4F1
0x1401fd4e4  mov     r12, [rsp+0E8h+arg_8]
0x1401fd4ec  jmp     loc_1401FD63E
0x1401fd4f1  movups  [rsp+0E8h+var_48], xmm0
0x1401fd4f9  mov     rcx, [rsp+0E8h+arg_8]
0x1401fd501  call    RtlReadULongFromUser
0x1401fd506  mov     ebx, eax
0x1401fd508  mov     dword ptr [rsp+0E8h+var_48], ebx
0x1401fd50f  mov     rcx, [rsp+0E8h+arg_8]
0x1401fd517  add     rcx, 8
0x1401fd51b  call    RtlReadULong64FromUser
0x1401fd520  mov     qword ptr [rsp+0E8h+var_48+8], rax
0x1401fd528  movzx   edx, bx
0x1401fd52b  mov     [rsp+0E8h+SourceString.Length], dx
0x1401fd530  shr     ebx, 10h
0x1401fd533  mov     [rsp+0E8h+SourceString.MaximumLength], bx
0x1401fd538  mov     ecx, dword ptr [rsp+0E8h+var_48+4]
0x1401fd53f  mov     dword ptr [rsp+0E8h+SourceString+4], ecx
0x1401fd543  mov     [rsp+0E8h+SourceString.Buffer], rax
0x1401fd548  mov     ebx, 2
0x1401fd54d  add     rdx, rbx; Length
0x1401fd550  mov     r8d, ebx; Alignment
0x1401fd553  mov     rcx, rax; Address
0x1401fd556  call    cs:__imp_ProbeForRead
0x1401fd55d  nop     dword ptr [rax+rax+00h]
0x1401fd562  movzx   eax, [rsp+0E8h+SourceString.Length]
0x1401fd567  cmp     ax, [rsp+0E8h+SourceString.MaximumLength]
0x1401fd56c  ja      short loc_1401FD5E4
0x1401fd56e  mov     byte ptr [rsp+0E8h+SourceString.Length], al
0x1401fd572  test    al, 1
0x1401fd574  jnz     short loc_1401FD5E4
0x1401fd576  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x1401fd57e  mov     [rsp+0E8h+DestinationString.Length], ax
0x1401fd586  mov     edx, eax; unsigned __int64
0x1401fd588  mov     ecx, 100h; unsigned __int64
0x1401fd58d  mov     r8d, 706D7452h; unsigned int
0x1401fd593  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fd598  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x1401fd5a0  test    rax, rax
0x1401fd5a3  jz      short loc_1401FD5D0
0x1401fd5a5  lea     rdx, [rsp+0E8h+SourceString]; SourceString
0x1401fd5aa  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x1401fd5b2  call    cs:__imp_RtlCopyUnicodeString
0x1401fd5b9  nop     dword ptr [rax+rax+00h]
0x1401fd5be  lea     r12, [rsp+0E8h+DestinationString]
0x1401fd5c6  mov     [rsp+0E8h+var_58], r12
0x1401fd5ce  jmp     short loc_1401FD5DB
0x1401fd5d0  mov     r14d, 0C0000017h
0x1401fd5d6  mov     [rsp+0E8h+var_70], r14d
0x1401fd5db  mov     ebx, [rsp+0E8h+arg_18]
0x1401fd5e2  jmp     short loc_1401FD63E
0x1401fd5e4  test    byte ptr [rsp+0E8h+SourceString.Length], 1
0x1401fd5e9  jz      short loc_1401FD609
0x1401fd5eb  mov     dword ptr [rsp+0E8h+var_90], 20000h
0x1401fd5f3  mov     r8d, 341h
0x1401fd5f9  mov     edx, dword ptr [rsp+0E8h+var_90]
0x1401fd5fd  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fd604  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fd609  call    cs:__imp_ExRaiseAccessViolation
0x1401fd610  nop     dword ptr [rax+rax+00h]
0x1401fd615  nop
0x1401fd616  mov     r14d, 0C000000Dh
0x1401fd61c  mov     [rsp+0E8h+var_70], r14d
0x1401fd621  xor     edi, edi
0x1401fd623  lea     r13, WPP_GLOBAL_Control
0x1401fd62a  mov     r15, [rsp+0E8h+Object]
0x1401fd62f  mov     r12, [rsp+0E8h+var_58]
0x1401fd637  mov     ebx, [rsp+0E8h+arg_18]
0x1401fd63e  test    r14d, r14d
0x1401fd641  js      loc_1401FD6FA
0x1401fd647  mov     [rsp+0E8h+var_90], rdi
0x1401fd64c  lea     rax, [rsp+0E8h+var_90]
0x1401fd651  mov     [rsp+0E8h+var_B8], rax; __int64
0x1401fd656  mov     [rsp+0E8h+var_C0], rdi; __int64
0x1401fd65b  mov     [rsp+0E8h+var_C8], edi; int
0x1401fd65f  mov     r9d, 1
0x1401fd665  mov     r8, r12
0x1401fd668  mov     edx, [rsp+0E8h+arg_10]
0x1401fd66f  mov     rcx, r15; struct RawInputManagerObject *
0x1401fd672  call    RIMCreateDev
0x1401fd677  mov     r14d, eax
0x1401fd67a  test    eax, eax
0x1401fd67c  js      short loc_1401FD6FA
0x1401fd67e  mov     rax, [rsp+0E8h+var_90]
0x1401fd683  or      dword ptr [rax+0A8h], 1
0x1401fd68a  or      r8, 0FFFFFFFFFFFFFFFFh; Handle
0x1401fd68e  mov     rdx, [rsp+0E8h+var_90]; struct RIMDEV *
0x1401fd693  mov     rcx, r15; struct RawInputManagerObject *
0x1401fd696  call    rimOnPnpArrived
0x1401fd69b  mov     r14d, eax
0x1401fd69e  test    eax, eax
0x1401fd6a0  js      short loc_1401FD6E8
0x1401fd6a2  test    ebx, ebx
0x1401fd6a4  jnz     short loc_1401FD6BC
0x1401fd6a6  mov     rax, [rsp+0E8h+var_90]
0x1401fd6ab  mov     rcx, [rax+10h]
0x1401fd6af  mov     rax, [rsp+0E8h+arg_20]
0x1401fd6b7  mov     [rax], rcx
0x1401fd6ba  jmp     short loc_1401FD6E8
0x1401fd6bc  mov     rdx, [rsp+0E8h+var_90]
0x1401fd6c1  mov     rdx, [rdx+10h]
0x1401fd6c5  mov     rcx, [rsp+0E8h+arg_20]
0x1401fd6cd  call    RtlWriteULong64ToUser
0x1401fd6d2  jmp     short loc_1401FD6E8
0x1401fd6d4  xor     edi, edi
0x1401fd6d6  mov     r14d, 0C000000Dh
0x1401fd6dc  lea     r13, WPP_GLOBAL_Control
0x1401fd6e3  mov     r15, [rsp+0E8h+Object]
0x1401fd6e8  test    r14d, r14d
0x1401fd6eb  jns     short loc_1401FD6FA
0x1401fd6ed  mov     rdx, [rsp+0E8h+var_90]; struct RIMDEV *
0x1401fd6f2  mov     rcx, r15; struct RawInputManagerObject *
0x1401fd6f5  call    RIMFreeDev
0x1401fd6fa  mov     rcx, [rsp+0E8h+DestinationString.Buffer]; Buffer
0x1401fd702  test    rcx, rcx
0x1401fd705  jz      short loc_1401FD70C
0x1401fd707  call    GreDeleteFastMutex
0x1401fd70c  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fd713  mov     rcx, [rsp+0E8h+var_50]
0x1401fd71b  call    RIMUnlockExclusive
0x1401fd720  mov     rcx, r15; Object
0x1401fd723  call    cs:__imp_ObfDereferenceObject
0x1401fd72a  nop     dword ptr [rax+rax+00h]
0x1401fd72f  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd736  cmp     rcx, r13
0x1401fd739  jz      short loc_1401FD74A
0x1401fd73b  mov     eax, [rcx+2Ch]
0x1401fd73e  test    al, 1
0x1401fd740  jz      short loc_1401FD74A
0x1401fd742  cmp     byte ptr [rcx+29h], 4
0x1401fd746  mov     bl, 1
0x1401fd748  jnb     short loc_1401FD74D
0x1401fd74a  mov     bl, dil
0x1401fd74d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fd754  setnz   r15b
0x1401fd758  test    bl, bl
0x1401fd75a  jnz     short loc_1401FD761
0x1401fd75c  test    r15b, r15b
0x1401fd75f  jz      short loc_1401FD7AE
0x1401fd761  call    cs:__imp_W32GetUserSessionState
0x1401fd768  nop     dword ptr [rax+rax+00h]
0x1401fd76d  mov     r9, [rax+4BD0h]
0x1401fd774  mov     [rsp+0E8h+var_A8], r14d
0x1401fd779  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fd780  mov     [rsp+0E8h+var_B0], rax
0x1401fd785  mov     word ptr [rsp+0E8h+var_B8], 1Dh
0x1401fd78c  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fd794  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1401fd799  mov     r8b, r15b
0x1401fd79c  mov     dl, bl
0x1401fd79e  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd7a5  mov     rcx, [rcx+18h]
0x1401fd7a9  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401fd7ae  mov     eax, r14d
0x1401fd7b1  add     rsp, 0B8h
0x1401fd7b8  pop     r15
0x1401fd7ba  pop     r14
0x1401fd7bc  pop     r13
0x1401fd7be  pop     r12
0x1401fd7c0  pop     rdi
0x1401fd7c1  pop     rbx
0x1401fd7c2  retn
0x1401fd7c4  mov     r14d, 0C00000BBh
0x1401fd7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd7d1  cmp     rcx, r13
0x1401fd7d4  jz      short loc_1401FD7E5
0x1401fd7d6  mov     eax, [rcx+2Ch]
0x1401fd7d9  test    al, 1
0x1401fd7db  jz      short loc_1401FD7E5
0x1401fd7dd  cmp     byte ptr [rcx+29h], 3
0x1401fd7e1  mov     bl, 1
0x1401fd7e3  jnb     short loc_1401FD7E8
0x1401fd7e5  mov     bl, dil
0x1401fd7e8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fd7ef  setnz   al
0x1401fd7f2  mov     [rsp+0E8h+var_98], al
0x1401fd7f6  test    bl, bl
0x1401fd7f8  jnz     short loc_1401FD802
0x1401fd7fa  test    al, al
0x1401fd7fc  jz      loc_1401FD713
0x1401fd802  call    cs:__imp_W32GetUserSessionState
0x1401fd809  nop     dword ptr [rax+rax+00h]
0x1401fd80e  mov     r9, [rax+4BD0h]
0x1401fd815  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fd81c  mov     [rsp+0E8h+var_B0], rax
0x1401fd821  mov     word ptr [rsp+0E8h+var_B8], 1Bh
0x1401fd828  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fd830  mov     byte ptr [rsp+0E8h+var_C8], 3
0x1401fd835  mov     r8b, [rsp+0E8h+var_98]
0x1401fd83a  mov     dl, bl
0x1401fd83c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd843  mov     rcx, [rcx+18h]
0x1401fd847  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fd84c  jmp     loc_1401FD713
0x1401fd851  mov     r14d, 0C00000BBh
0x1401fd857  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fd85e  cmp     rcx, r13
0x1401fd861  jz      short loc_1401FD872
0x1401fd863  mov     eax, [rcx+2Ch]
0x1401fd866  test    al, 1
0x1401fd868  jz      short loc_1401FD872
0x1401fd86a  cmp     byte ptr [rcx+29h], 3
0x1401fd86e  mov     bl, 1
0x1401fd870  jnb     short loc_1401FD875
0x1401fd872  mov     bl, dil
0x1401fd875  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fd87c  setnz   al
0x1401fd87f  mov     [rsp+0E8h+var_98], al
0x1401fd883  test    bl, bl
0x1401fd885  jnz     short loc_1401FD88F
0x1401fd887  test    al, al
0x1401fd889  jz      loc_1401FD713
0x1401fd88f  call    cs:__imp_W32GetUserSessionState
0x1401fd896  nop     dword ptr [rax+rax+00h]
0x1401fd89b  mov     r9, [rax+4BD0h]
0x1401fd8a2  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fd8a9  mov     [rsp+0E8h+var_B0], rax
0x1401fd8ae  mov     word ptr [rsp+0E8h+var_B8], 1Ch
0x1401fd8b5  jmp     loc_1401FD828
```
