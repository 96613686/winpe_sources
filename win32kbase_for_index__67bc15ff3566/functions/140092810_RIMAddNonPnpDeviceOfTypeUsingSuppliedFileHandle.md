# RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle

- ea: `0x140092810`
- end: `0x140092dd5`
- name: `RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle`
- size: `1477`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140091660`

## callees

- `0x140049df8`
- `0x140049ec0`
- `0x140062ff0`
- `0x1400682c0`
- `0x14007b930`
- `0x14007efd0`
- `0x140092750`
- `0x140092810`
- `0x1400dd4cc`
- `0x1400ff080`
- `0x140137f60`
- `0x140138a74`
- `0x1401a0318`
- `0x1401aab9c`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140092a62`
- `ntoskrnl!ProbeForRead` at `0x140092a62`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140092b02`
- `ntoskrnl!ExRaiseAccessViolation` at `0x140092b02`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140092ab5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140092ab5`
- `ntoskrnl!ObfDereferenceObject` at `0x140092c35`
- `ntoskrnl!ObfDereferenceObject` at `0x140092c35`
- `WIN32K!W32GetUserSessionState` at `0x140092886`
- `WIN32K!W32GetUserSessionState` at `0x140092916`
- `WIN32K!W32GetUserSessionState` at `0x140092c73`
- `WIN32K!W32GetUserSessionState` at `0x140092d17`
- `WIN32K!W32GetUserSessionState` at `0x140092daa`
- `WIN32K!W32GetUserSessionState` at `0x140092886`
- `WIN32K!W32GetUserSessionState` at `0x140092916`
- `WIN32K!W32GetUserSessionState` at `0x140092c73`
- `WIN32K!W32GetUserSessionState` at `0x140092d17`
- `WIN32K!W32GetUserSessionState` at `0x140092daa`

## pseudocode

```c
__int64 __fastcall RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle(
        char *a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        int a5,
        _QWORD *a6)
{
  char v6; // bl
  bool v7; // r14
  __int64 UserSessionState; // rax
  int v9; // r8d
  int v10; // edx
  char v11; // bl
  bool v12; // r14
  __int64 v13; // rax
  int v14; // r8d
  int v15; // edx
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // r14d
  struct RawInputManagerObject *v20; // r15
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  int ULongFromUser; // ebx
  char v26; // bl
  bool v27; // r15
  __int64 v28; // rax
  int v29; // r8d
  int v30; // edx
  char v31; // bl
  int v32; // edx
  int v33; // r8d
  __int64 v34; // r9
  __int16 v35; // [rsp+30h] [rbp-B8h]
  struct RIMDEV *v36; // [rsp+50h] [rbp-98h] BYREF
  PVOID Object; // [rsp+58h] [rbp-90h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-88h] BYREF
  int v39; // [rsp+70h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-70h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+88h] [rbp-60h]
  char *v42; // [rsp+90h] [rbp-58h]
  __int128 v43; // [rsp+98h] [rbp-50h]
  char *v44; // [rsp+F0h] [rbp+8h]
  unsigned int v46; // [rsp+100h] [rbp+18h]
  bool Handlea; // [rsp+108h] [rbp+20h]

  v46 = a3;
  v44 = a1;
  Object = 0;
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v6 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v6 = 0;
  }
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(a1, a2, a3);
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v10,
      v9,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      30,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    a1 = v44;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v11 = 0;
    }
    v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = W32GetUserSessionState(WPP_GLOBAL_Control, a2, a3);
      LOBYTE(v14) = v12;
      LOBYTE(v15) = v11;
      WPP_RECORDER_AND_TRACE_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v15,
        v14,
        *(_QWORD *)(v13 + 19408),
        4,
        1,
        31,
        (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
        13);
    }
    return 3221225485LL;
  }
  v19 = RawInputManagerObjectResolveHandle(a1, 3u, 1, &Object);
  if ( v19 >= 0 )
  {
    v20 = (struct RawInputManagerObject *)Object;
    v42 = (char *)Object + 96;
    RIMLockExclusive((char *)Object + 96);
    if ( *((_BYTE *)v20 + 73) || *((_BYTE *)v20 + 74) )
    {
      v19 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v31 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v31 = 0;
      }
      Handlea = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v31 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v34 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v21, v22) + 19408);
      v35 = 33;
    }
    else
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(v46) & *((_DWORD *)v20 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        if ( a5 )
        {
          v43 = 0;
          ULongFromUser = RtlReadULongFromUser(a2);
          LODWORD(v43) = ULongFromUser;
          *((_QWORD *)&v43 + 1) = RtlReadULong64FromUser(a2 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v43);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v43 + 1);
          ProbeForRead(*((volatile void **)&v43 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
          {
            if ( (SourceString.Length & 1) != 0 )
            {
              LODWORD(v36) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 991);
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
            v19 = -1073741801;
            v39 = -1073741801;
          }
        }
        if ( v19 >= 0 )
        {
          v36 = 0;
          v19 = RIMCreateDev(v20, 0, 0, (__int64)&v36);
          if ( v19 >= 0 )
          {
            *((_DWORD *)v36 + 42) |= 1u;
            v19 = rimOnPnpArrived(v20, v36, a4);
            if ( v19 >= 0 )
            {
              rimDoRimDevChange(v20, v36, 2);
              if ( a6 )
              {
                if ( a5 )
                  RtlWriteULong64ToUser(a6, *((_QWORD *)v36 + 2));
                else
                  *a6 = *((_QWORD *)v36 + 2);
              }
            }
            if ( v19 < 0 )
              RIMFreeDev(v20, v36);
          }
        }
        if ( DestinationString.Buffer )
          GreDeleteFastMutex(DestinationString.Buffer);
        goto LABEL_41;
      }
      v19 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v31 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v31 = 0;
      }
      Handlea = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v31 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v34 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v23, v24) + 19408);
      v35 = 32;
    }
    LOBYTE(v33) = Handlea;
    LOBYTE(v32) = v31;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v32,
      v33,
      v34,
      3,
      1,
      v35,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_41:
    RIMUnlockExclusive(v42);
    ObfDereferenceObject(v20);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v26 = 0;
  }
  v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v28 = W32GetUserSessionState(WPP_GLOBAL_Control, v17, v18);
    LOBYTE(v29) = v27;
    LOBYTE(v30) = v26;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v30,
      v29,
      *(_QWORD *)(v28 + 19408),
      4,
      1,
      34,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140092810  mov     rax, rsp
0x140092813  mov     [rax+20h], r9
0x140092817  mov     [rax+18h], r8d
0x14009281b  mov     [rax+10h], rdx
0x14009281f  mov     [rax+8], rcx
0x140092823  push    rbx
0x140092824  push    rdi
0x140092825  push    r12
0x140092827  push    r13
0x140092829  push    r14
0x14009282b  push    r15
0x14009282d  sub     rsp, 0B8h
0x140092834  xor     edi, edi
0x140092836  mov     [rsp+0E8h+Object], rdi
0x14009283b  lea     r13, WPP_GLOBAL_Control
0x140092842  mov     r10, cs:WPP_GLOBAL_Control
0x140092849  cmp     r10, r13
0x14009284c  jz      short loc_14009285F
0x14009284e  mov     eax, [r10+2Ch]
0x140092852  test    al, 1
0x140092854  jz      short loc_14009285F
0x140092856  cmp     byte ptr [r10+29h], 4
0x14009285b  mov     bl, 1
0x14009285d  jnb     short loc_140092862
0x14009285f  mov     bl, dil
0x140092862  lea     r12, WPP_RECORDER_INITIALIZED
0x140092869  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140092870  setnz   r14b
0x140092874  test    bl, bl
0x140092876  jnz     short loc_140092886
0x140092878  test    r14b, r14b
0x14009287b  jnz     short loc_140092886
0x14009287d  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140092884  jmp     short loc_1400928D6
0x140092886  call    cs:__imp_W32GetUserSessionState
0x14009288d  nop     dword ptr [rax+rax+00h]
0x140092892  mov     r9, [rax+4BD0h]
0x140092899  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400928a0  mov     [rsp+0E8h+var_B0], r15
0x1400928a5  mov     word ptr [rsp+0E8h+var_B8], 1Eh
0x1400928ac  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1400928b4  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400928b9  mov     r8b, r14b
0x1400928bc  mov     dl, bl
0x1400928be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400928c5  mov     rcx, [rcx+18h]
0x1400928c9  call    WPP_RECORDER_AND_TRACE_SF_
0x1400928ce  mov     rcx, [rsp+0E8h+arg_0]
0x1400928d6  cmp     [rsp+0E8h+Handle], rdi
0x1400928de  jnz     loc_140092969
0x1400928e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400928eb  cmp     rcx, r13
0x1400928ee  jz      short loc_1400928FF
0x1400928f0  mov     eax, [rcx+2Ch]
0x1400928f3  test    al, 1
0x1400928f5  jz      short loc_1400928FF
0x1400928f7  cmp     byte ptr [rcx+29h], 4
0x1400928fb  mov     bl, 1
0x1400928fd  jnb     short loc_140092902
0x1400928ff  mov     bl, dil
0x140092902  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140092909  setnz   r14b
0x14009290d  test    bl, bl
0x14009290f  jnz     short loc_140092916
0x140092911  test    r14b, r14b
0x140092914  jz      short loc_14009295F
0x140092916  call    cs:__imp_W32GetUserSessionState
0x14009291d  nop     dword ptr [rax+rax+00h]
0x140092922  mov     r9, [rax+4BD0h]
0x140092929  mov     [rsp+0E8h+var_A8], 0C000000Dh
0x140092931  mov     [rsp+0E8h+var_B0], r15
0x140092936  mov     word ptr [rsp+0E8h+var_B8], 1Fh
0x14009293d  mov     dword ptr [rsp+0E8h+var_C0], 1
0x140092945  mov     byte ptr [rsp+0E8h+var_C8], 4
0x14009294a  mov     r8b, r14b
0x14009294d  mov     dl, bl
0x14009294f  mov     rcx, cs:WPP_GLOBAL_Control
0x140092956  mov     rcx, [rcx+18h]
0x14009295a  call    WPP_RECORDER_AND_TRACE_SF_d
0x14009295f  mov     eax, 0C000000Dh
0x140092964  jmp     loc_140092CC3
0x140092969  lea     r9, [rsp+0E8h+Object]
0x14009296e  mov     edx, 3
0x140092973  lea     r8d, [rdx-2]
0x140092977  call    RawInputManagerObjectResolveHandle
0x14009297c  mov     r14d, eax
0x14009297f  test    eax, eax
0x140092981  js      loc_140092C41
0x140092987  mov     r15, [rsp+0E8h+Object]
0x14009298c  lea     rax, [r15+60h]
0x140092990  mov     [rsp+0E8h+var_58], rax
0x140092998  mov     rcx, rax
0x14009299b  call    RIMLockExclusive
0x1400929a0  cmp     [r15+49h], dil
0x1400929a4  jnz     loc_140092D69
0x1400929aa  cmp     [r15+4Ah], dil
0x1400929ae  jnz     loc_140092D69
0x1400929b4  mov     ecx, [rsp+0E8h+arg_10]
0x1400929bb  call    DeviceTypeToRimInputType
0x1400929c0  test    [r15+4Ch], eax
0x1400929c4  jz      loc_140092CD6
0x1400929ca  xorps   xmm0, xmm0
0x1400929cd  movups  xmmword ptr [rsp+0E8h+SourceString.Length], xmm0
0x1400929d2  mov     r12, rdi
0x1400929d5  mov     [rsp+0E8h+var_60], rdi
0x1400929dd  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1400929e2  cmp     [rsp+0E8h+arg_20], edi
0x1400929e9  jnz     short loc_1400929FD
0x1400929eb  mov     r12, [rsp+0E8h+arg_8]
0x1400929f3  mov     ebx, 2
0x1400929f8  jmp     loc_140092B33
0x1400929fd  movups  [rsp+0E8h+var_50], xmm0
0x140092a05  mov     rcx, [rsp+0E8h+arg_8]
0x140092a0d  call    RtlReadULongFromUser
0x140092a12  mov     ebx, eax
0x140092a14  mov     dword ptr [rsp+0E8h+var_50], ebx
0x140092a1b  mov     rcx, [rsp+0E8h+arg_8]
0x140092a23  add     rcx, 8
0x140092a27  call    RtlReadULong64FromUser
0x140092a2c  mov     qword ptr [rsp+0E8h+var_50+8], rax
0x140092a34  movzx   edx, bx
0x140092a37  mov     [rsp+0E8h+SourceString.Length], dx
0x140092a3c  shr     ebx, 10h
0x140092a3f  mov     [rsp+0E8h+SourceString.MaximumLength], bx
0x140092a44  mov     ecx, dword ptr [rsp+0E8h+var_50+4]
0x140092a4b  mov     dword ptr [rsp+0E8h+SourceString+4], ecx
0x140092a4f  mov     [rsp+0E8h+SourceString.Buffer], rax
0x140092a54  mov     ebx, 2
0x140092a59  add     rdx, rbx; Length
0x140092a5c  mov     r8d, ebx; Alignment
0x140092a5f  mov     rcx, rax; Address
0x140092a62  call    cs:__imp_ProbeForRead
0x140092a69  nop     dword ptr [rax+rax+00h]
0x140092a6e  movzx   eax, [rsp+0E8h+SourceString.Length]
0x140092a73  cmp     ax, [rsp+0E8h+SourceString.MaximumLength]
0x140092a78  ja      short loc_140092ADD
0x140092a7a  mov     byte ptr [rsp+0E8h+SourceString.Length], al
0x140092a7e  test    al, 1
0x140092a80  jnz     short loc_140092ADD
0x140092a82  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x140092a87  mov     [rsp+0E8h+DestinationString.Length], ax
0x140092a8c  mov     edx, eax; unsigned __int64
0x140092a8e  mov     ecx, 100h; unsigned __int64
0x140092a93  mov     r8d, 706D7452h; unsigned int
0x140092a99  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x140092a9e  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x140092aa6  test    rax, rax
0x140092aa9  jz      short loc_140092AD0
0x140092aab  lea     rdx, [rsp+0E8h+SourceString]; SourceString
0x140092ab0  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x140092ab5  call    cs:__imp_RtlCopyUnicodeString
0x140092abc  nop     dword ptr [rax+rax+00h]
0x140092ac1  lea     r12, [rsp+0E8h+DestinationString]
0x140092ac6  mov     [rsp+0E8h+var_60], r12
0x140092ace  jmp     short loc_140092ADB
0x140092ad0  mov     r14d, 0C0000017h
0x140092ad6  mov     [rsp+0E8h+var_78], r14d
0x140092adb  jmp     short loc_140092B33
0x140092add  test    byte ptr [rsp+0E8h+SourceString.Length], 1
0x140092ae2  jz      short loc_140092B02
0x140092ae4  mov     dword ptr [rsp+0E8h+var_98], 20000h
0x140092aec  mov     r8d, 3DFh
0x140092af2  mov     edx, dword ptr [rsp+0E8h+var_98]
0x140092af6  lea     rcx, aIxptelassert; "IXPTelAssert"
0x140092afd  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x140092b02  call    cs:__imp_ExRaiseAccessViolation
0x140092b09  nop     dword ptr [rax+rax+00h]
0x140092b0e  nop
0x140092b0f  mov     r14d, 0C000000Dh
0x140092b15  mov     [rsp+0E8h+var_78], r14d
0x140092b1a  xor     edi, edi
0x140092b1c  lea     r13, WPP_GLOBAL_Control
0x140092b23  lea     ebx, [rdi+2]
0x140092b26  mov     r15, [rsp+0E8h+Object]
0x140092b2b  mov     r12, [rsp+0E8h+var_60]
0x140092b33  test    r14d, r14d
0x140092b36  js      loc_140092C0C
0x140092b3c  mov     [rsp+0E8h+var_98], rdi
0x140092b41  lea     rax, [rsp+0E8h+var_98]
0x140092b46  mov     [rsp+0E8h+var_B8], rax; __int64
0x140092b4b  mov     [rsp+0E8h+var_C0], rdi; __int64
0x140092b50  mov     [rsp+0E8h+var_C8], edi; int
0x140092b54  mov     r9d, 1
0x140092b5a  mov     r8, r12
0x140092b5d  mov     edx, [rsp+0E8h+arg_10]
0x140092b64  mov     rcx, r15; struct RawInputManagerObject *
0x140092b67  call    RIMCreateDev
0x140092b6c  mov     r14d, eax
0x140092b6f  test    eax, eax
0x140092b71  js      loc_140092C0C
0x140092b77  mov     rax, [rsp+0E8h+var_98]
0x140092b7c  or      dword ptr [rax+0A8h], 1
0x140092b83  mov     r8, [rsp+0E8h+Handle]; Handle
0x140092b8b  mov     rdx, [rsp+0E8h+var_98]; struct RIMDEV *
0x140092b90  mov     rcx, r15; struct RawInputManagerObject *
0x140092b93  call    rimOnPnpArrived
0x140092b98  mov     r14d, eax
0x140092b9b  test    eax, eax
0x140092b9d  js      short loc_140092BFA
0x140092b9f  mov     r8d, ebx
0x140092ba2  mov     rdx, [rsp+0E8h+var_98]
0x140092ba7  mov     rcx, r15
0x140092baa  call    rimDoRimDevChange
0x140092baf  mov     r8, [rsp+0E8h+arg_28]
0x140092bb7  test    r8, r8
0x140092bba  jz      short loc_140092BFA
0x140092bbc  cmp     [rsp+0E8h+arg_20], edi
0x140092bc3  jnz     short loc_140092BD3
0x140092bc5  mov     rax, [rsp+0E8h+var_98]
0x140092bca  mov     rcx, [rax+10h]
0x140092bce  mov     [r8], rcx
0x140092bd1  jmp     short loc_140092BFA
0x140092bd3  mov     rdx, [rsp+0E8h+var_98]
0x140092bd8  mov     rdx, [rdx+10h]
0x140092bdc  mov     rcx, r8
0x140092bdf  call    RtlWriteULong64ToUser
0x140092be4  jmp     short loc_140092BFA
0x140092be6  xor     edi, edi
0x140092be8  mov     r14d, 0C000000Dh
0x140092bee  lea     r13, WPP_GLOBAL_Control
0x140092bf5  mov     r15, [rsp+0E8h+Object]
0x140092bfa  test    r14d, r14d
0x140092bfd  jns     short loc_140092C0C
0x140092bff  mov     rdx, [rsp+0E8h+var_98]; struct RIMDEV *
0x140092c04  mov     rcx, r15; struct RawInputManagerObject *
0x140092c07  call    RIMFreeDev
0x140092c0c  mov     rcx, [rsp+0E8h+DestinationString.Buffer]; Buffer
0x140092c14  test    rcx, rcx
0x140092c17  jz      short loc_140092C1E
0x140092c19  call    GreDeleteFastMutex
0x140092c1e  lea     r12, WPP_RECORDER_INITIALIZED
0x140092c25  mov     rcx, [rsp+0E8h+var_58]
0x140092c2d  call    RIMUnlockExclusive
0x140092c32  mov     rcx, r15; Object
0x140092c35  call    cs:__imp_ObfDereferenceObject
0x140092c3c  nop     dword ptr [rax+rax+00h]
0x140092c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140092c48  cmp     rcx, r13
0x140092c4b  jz      short loc_140092C5C
0x140092c4d  mov     eax, [rcx+2Ch]
0x140092c50  test    al, 1
0x140092c52  jz      short loc_140092C5C
0x140092c54  cmp     byte ptr [rcx+29h], 4
0x140092c58  mov     bl, 1
0x140092c5a  jnb     short loc_140092C5F
0x140092c5c  mov     bl, dil
0x140092c5f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140092c66  setnz   r15b
0x140092c6a  test    bl, bl
0x140092c6c  jnz     short loc_140092C73
0x140092c6e  test    r15b, r15b
0x140092c71  jz      short loc_140092CC0
0x140092c73  call    cs:__imp_W32GetUserSessionState
0x140092c7a  nop     dword ptr [rax+rax+00h]
0x140092c7f  mov     r9, [rax+4BD0h]
0x140092c86  mov     [rsp+0E8h+var_A8], r14d
0x140092c8b  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140092c92  mov     [rsp+0E8h+var_B0], rax
0x140092c97  mov     word ptr [rsp+0E8h+var_B8], 22h ; '"'
0x140092c9e  mov     dword ptr [rsp+0E8h+var_C0], 1
0x140092ca6  mov     byte ptr [rsp+0E8h+var_C8], 4
0x140092cab  mov     r8b, r15b
0x140092cae  mov     dl, bl
0x140092cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140092cb7  mov     rcx, [rcx+18h]
0x140092cbb  call    WPP_RECORDER_AND_TRACE_SF_d
0x140092cc0  mov     eax, r14d
0x140092cc3  add     rsp, 0B8h
0x140092cca  pop     r15
0x140092ccc  pop     r14
0x140092cce  pop     r13
0x140092cd0  pop     r12
0x140092cd2  pop     rdi
0x140092cd3  pop     rbx
0x140092cd4  retn
0x140092cd6  mov     r14d, 0C00000BBh
0x140092cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x140092ce3  cmp     rcx, r13
0x140092ce6  jz      short loc_140092CF7
0x140092ce8  mov     eax, [rcx+2Ch]
0x140092ceb  test    al, 1
0x140092ced  jz      short loc_140092CF7
0x140092cef  cmp     byte ptr [rcx+29h], 3
0x140092cf3  mov     bl, 1
0x140092cf5  jnb     short loc_140092CFA
0x140092cf7  mov     bl, dil
0x140092cfa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140092d01  setnz   al
0x140092d04  mov     byte ptr [rsp+0E8h+Handle], al
0x140092d0b  test    bl, bl
0x140092d0d  jnz     short loc_140092D17
0x140092d0f  test    al, al
0x140092d11  jz      loc_140092C25
0x140092d17  call    cs:__imp_W32GetUserSessionState
0x140092d1e  nop     dword ptr [rax+rax+00h]
0x140092d23  mov     r9, [rax+4BD0h]
0x140092d2a  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140092d31  mov     [rsp+0E8h+var_B0], rax
0x140092d36  mov     word ptr [rsp+0E8h+var_B8], 20h ; ' '
0x140092d3d  mov     dword ptr [rsp+0E8h+var_C0], 1
  ... truncated ...
```
