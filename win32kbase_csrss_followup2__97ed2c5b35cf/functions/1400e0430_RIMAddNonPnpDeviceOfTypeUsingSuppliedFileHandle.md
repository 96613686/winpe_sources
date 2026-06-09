# RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle

- ea: `0x1400e0430`
- end: `0x1400e09f5`
- name: `RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle`
- size: `1477`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400df280`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x140065730`
- `0x1400729c8`
- `0x140072a90`
- `0x1400951c0`
- `0x1400e0370`
- `0x1400e0430`
- `0x1400f9f50`
- `0x140135db0`
- `0x1401368c4`
- `0x140184c20`
- `0x14019e958`
- `0x1401a9f9c`
- `0x1402bb164`
- `0x1402bb1a0`
- `0x1402bb310`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400e0682`
- `ntoskrnl!ProbeForRead` at `0x1400e0682`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400e0722`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400e0722`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e06d5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400e06d5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e0855`
- `ntoskrnl!ObfDereferenceObject` at `0x1400e0855`
- `WIN32K!W32GetUserSessionState` at `0x1400e04a6`
- `WIN32K!W32GetUserSessionState` at `0x1400e0536`
- `WIN32K!W32GetUserSessionState` at `0x1400e0893`
- `WIN32K!W32GetUserSessionState` at `0x1400e0937`
- `WIN32K!W32GetUserSessionState` at `0x1400e09ca`
- `WIN32K!W32GetUserSessionState` at `0x1400e04a6`
- `WIN32K!W32GetUserSessionState` at `0x1400e0536`
- `WIN32K!W32GetUserSessionState` at `0x1400e0893`
- `WIN32K!W32GetUserSessionState` at `0x1400e0937`
- `WIN32K!W32GetUserSessionState` at `0x1400e09ca`

## pseudocode

```c
__int64 __fastcall RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
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
  int v17; // r14d
  struct RawInputManagerObject *v18; // r15
  int ULongFromUser; // ebx
  char v20; // bl
  bool v21; // r15
  __int64 v22; // rax
  int v23; // r8d
  int v24; // edx
  char v25; // bl
  int v26; // edx
  int v27; // r8d
  __int64 v28; // r9
  __int16 v29; // [rsp+30h] [rbp-B8h]
  struct RIMDEV *v30; // [rsp+50h] [rbp-98h] BYREF
  PVOID Object; // [rsp+58h] [rbp-90h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-88h] BYREF
  int v33; // [rsp+70h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-70h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+88h] [rbp-60h]
  char *v36; // [rsp+90h] [rbp-58h]
  __int128 v37; // [rsp+98h] [rbp-50h]
  __int64 v38; // [rsp+F0h] [rbp+8h]
  bool Handlea; // [rsp+108h] [rbp+20h]

  v38 = a1;
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
    UserSessionState = W32GetUserSessionState(a1);
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
    a1 = v38;
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
      v13 = W32GetUserSessionState(WPP_GLOBAL_Control);
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
  v17 = RawInputManagerObjectResolveHandle(a1, 3, 1, &Object);
  if ( v17 >= 0 )
  {
    v18 = (struct RawInputManagerObject *)Object;
    v36 = (char *)Object + 96;
    RIMLockExclusive((char *)Object + 96);
    if ( *((_BYTE *)v18 + 73) || *((_BYTE *)v18 + 74) )
    {
      v17 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v25 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v25 = 0;
      }
      Handlea = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v25 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v28 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
      v29 = 33;
    }
    else
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(a3) & *((_DWORD *)v18 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        if ( a5 )
        {
          v37 = 0;
          ULongFromUser = RtlReadULongFromUser(a2);
          LODWORD(v37) = ULongFromUser;
          *((_QWORD *)&v37 + 1) = RtlReadULong64FromUser(a2 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v37);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v37 + 1);
          ProbeForRead(*((volatile void **)&v37 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
          {
            if ( (SourceString.Length & 1) != 0 )
            {
              LODWORD(v30) = 0x20000;
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
            v17 = -1073741801;
            v33 = -1073741801;
          }
        }
        if ( v17 >= 0 )
        {
          v30 = 0;
          v17 = RIMCreateDev(v18, 0, 0, (__int64)&v30);
          if ( v17 >= 0 )
          {
            *((_DWORD *)v30 + 42) |= 1u;
            v17 = rimOnPnpArrived(v18, v30, a4);
            if ( v17 >= 0 )
            {
              rimDoRimDevChange(v18, v30, 2);
              if ( a6 )
              {
                if ( a5 )
                  RtlWriteULong64ToUser(a6, *((_QWORD *)v30 + 2));
                else
                  *a6 = *((_QWORD *)v30 + 2);
              }
            }
            if ( v17 < 0 )
              RIMFreeDev(v18, v30);
          }
        }
        if ( DestinationString.Buffer )
          GreDeleteFastMutex(DestinationString.Buffer);
        goto LABEL_41;
      }
      v17 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v25 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v25 = 0;
      }
      Handlea = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v25 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v28 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
      v29 = 32;
    }
    LOBYTE(v27) = Handlea;
    LOBYTE(v26) = v25;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v26,
      v27,
      v28,
      3,
      1,
      v29,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_41:
    RIMUnlockExclusive(v36);
    ObfDereferenceObject(v18);
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
    v22 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v23) = v21;
    LOBYTE(v24) = v20;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v24,
      v23,
      *(_QWORD *)(v22 + 19408),
      4,
      1,
      34,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400e0430  mov     rax, rsp
0x1400e0433  mov     [rax+20h], r9
0x1400e0437  mov     [rax+18h], r8d
0x1400e043b  mov     [rax+10h], rdx
0x1400e043f  mov     [rax+8], rcx
0x1400e0443  push    rbx
0x1400e0444  push    rdi
0x1400e0445  push    r12
0x1400e0447  push    r13
0x1400e0449  push    r14
0x1400e044b  push    r15
0x1400e044d  sub     rsp, 0B8h
0x1400e0454  xor     edi, edi
0x1400e0456  mov     [rsp+0E8h+Object], rdi
0x1400e045b  lea     r13, WPP_GLOBAL_Control
0x1400e0462  mov     r10, cs:WPP_GLOBAL_Control
0x1400e0469  cmp     r10, r13
0x1400e046c  jz      short loc_1400E047F
0x1400e046e  mov     eax, [r10+2Ch]
0x1400e0472  test    al, 1
0x1400e0474  jz      short loc_1400E047F
0x1400e0476  cmp     byte ptr [r10+29h], 4
0x1400e047b  mov     bl, 1
0x1400e047d  jnb     short loc_1400E0482
0x1400e047f  mov     bl, dil
0x1400e0482  lea     r12, WPP_RECORDER_INITIALIZED
0x1400e0489  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400e0490  setnz   r14b
0x1400e0494  test    bl, bl
0x1400e0496  jnz     short loc_1400E04A6
0x1400e0498  test    r14b, r14b
0x1400e049b  jnz     short loc_1400E04A6
0x1400e049d  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400e04a4  jmp     short loc_1400E04F6
0x1400e04a6  call    cs:__imp_W32GetUserSessionState
0x1400e04ad  nop     dword ptr [rax+rax+00h]
0x1400e04b2  mov     r9, [rax+4BD0h]
0x1400e04b9  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400e04c0  mov     [rsp+0E8h+var_B0], r15
0x1400e04c5  mov     word ptr [rsp+0E8h+var_B8], 1Eh
0x1400e04cc  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1400e04d4  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400e04d9  mov     r8b, r14b
0x1400e04dc  mov     dl, bl
0x1400e04de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e04e5  mov     rcx, [rcx+18h]
0x1400e04e9  call    WPP_RECORDER_AND_TRACE_SF_
0x1400e04ee  mov     rcx, [rsp+0E8h+arg_0]
0x1400e04f6  cmp     [rsp+0E8h+Handle], rdi
0x1400e04fe  jnz     loc_1400E0589
0x1400e0504  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e050b  cmp     rcx, r13
0x1400e050e  jz      short loc_1400E051F
0x1400e0510  mov     eax, [rcx+2Ch]
0x1400e0513  test    al, 1
0x1400e0515  jz      short loc_1400E051F
0x1400e0517  cmp     byte ptr [rcx+29h], 4
0x1400e051b  mov     bl, 1
0x1400e051d  jnb     short loc_1400E0522
0x1400e051f  mov     bl, dil
0x1400e0522  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400e0529  setnz   r14b
0x1400e052d  test    bl, bl
0x1400e052f  jnz     short loc_1400E0536
0x1400e0531  test    r14b, r14b
0x1400e0534  jz      short loc_1400E057F
0x1400e0536  call    cs:__imp_W32GetUserSessionState
0x1400e053d  nop     dword ptr [rax+rax+00h]
0x1400e0542  mov     r9, [rax+4BD0h]
0x1400e0549  mov     [rsp+0E8h+var_A8], 0C000000Dh
0x1400e0551  mov     [rsp+0E8h+var_B0], r15
0x1400e0556  mov     word ptr [rsp+0E8h+var_B8], 1Fh
0x1400e055d  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1400e0565  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400e056a  mov     r8b, r14b
0x1400e056d  mov     dl, bl
0x1400e056f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e0576  mov     rcx, [rcx+18h]
0x1400e057a  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400e057f  mov     eax, 0C000000Dh
0x1400e0584  jmp     loc_1400E08E3
0x1400e0589  lea     r9, [rsp+0E8h+Object]
0x1400e058e  mov     edx, 3
0x1400e0593  lea     r8d, [rdx-2]
0x1400e0597  call    RawInputManagerObjectResolveHandle
0x1400e059c  mov     r14d, eax
0x1400e059f  test    eax, eax
0x1400e05a1  js      loc_1400E0861
0x1400e05a7  mov     r15, [rsp+0E8h+Object]
0x1400e05ac  lea     rax, [r15+60h]
0x1400e05b0  mov     [rsp+0E8h+var_58], rax
0x1400e05b8  mov     rcx, rax
0x1400e05bb  call    RIMLockExclusive
0x1400e05c0  cmp     [r15+49h], dil
0x1400e05c4  jnz     loc_1400E0989
0x1400e05ca  cmp     [r15+4Ah], dil
0x1400e05ce  jnz     loc_1400E0989
0x1400e05d4  mov     ecx, [rsp+0E8h+arg_10]
0x1400e05db  call    DeviceTypeToRimInputType
0x1400e05e0  test    [r15+4Ch], eax
0x1400e05e4  jz      loc_1400E08F6
0x1400e05ea  xorps   xmm0, xmm0
0x1400e05ed  movups  xmmword ptr [rsp+0E8h+SourceString.Length], xmm0
0x1400e05f2  mov     r12, rdi
0x1400e05f5  mov     [rsp+0E8h+var_60], rdi
0x1400e05fd  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1400e0602  cmp     [rsp+0E8h+arg_20], edi
0x1400e0609  jnz     short loc_1400E061D
0x1400e060b  mov     r12, [rsp+0E8h+arg_8]
0x1400e0613  mov     ebx, 2
0x1400e0618  jmp     loc_1400E0753
0x1400e061d  movups  [rsp+0E8h+var_50], xmm0
0x1400e0625  mov     rcx, [rsp+0E8h+arg_8]
0x1400e062d  call    RtlReadULongFromUser
0x1400e0632  mov     ebx, eax
0x1400e0634  mov     dword ptr [rsp+0E8h+var_50], ebx
0x1400e063b  mov     rcx, [rsp+0E8h+arg_8]
0x1400e0643  add     rcx, 8
0x1400e0647  call    RtlReadULong64FromUser
0x1400e064c  mov     qword ptr [rsp+0E8h+var_50+8], rax
0x1400e0654  movzx   edx, bx
0x1400e0657  mov     [rsp+0E8h+SourceString.Length], dx
0x1400e065c  shr     ebx, 10h
0x1400e065f  mov     [rsp+0E8h+SourceString.MaximumLength], bx
0x1400e0664  mov     ecx, dword ptr [rsp+0E8h+var_50+4]
0x1400e066b  mov     dword ptr [rsp+0E8h+SourceString+4], ecx
0x1400e066f  mov     [rsp+0E8h+SourceString.Buffer], rax
0x1400e0674  mov     ebx, 2
0x1400e0679  add     rdx, rbx; Length
0x1400e067c  mov     r8d, ebx; Alignment
0x1400e067f  mov     rcx, rax; Address
0x1400e0682  call    cs:__imp_ProbeForRead
0x1400e0689  nop     dword ptr [rax+rax+00h]
0x1400e068e  movzx   eax, [rsp+0E8h+SourceString.Length]
0x1400e0693  cmp     ax, [rsp+0E8h+SourceString.MaximumLength]
0x1400e0698  ja      short loc_1400E06FD
0x1400e069a  mov     byte ptr [rsp+0E8h+SourceString.Length], al
0x1400e069e  test    al, 1
0x1400e06a0  jnz     short loc_1400E06FD
0x1400e06a2  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x1400e06a7  mov     [rsp+0E8h+DestinationString.Length], ax
0x1400e06ac  mov     edx, eax; unsigned __int64
0x1400e06ae  mov     ecx, 100h; unsigned __int64
0x1400e06b3  mov     r8d, 706D7452h; unsigned int
0x1400e06b9  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400e06be  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x1400e06c6  test    rax, rax
0x1400e06c9  jz      short loc_1400E06F0
0x1400e06cb  lea     rdx, [rsp+0E8h+SourceString]; SourceString
0x1400e06d0  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x1400e06d5  call    cs:__imp_RtlCopyUnicodeString
0x1400e06dc  nop     dword ptr [rax+rax+00h]
0x1400e06e1  lea     r12, [rsp+0E8h+DestinationString]
0x1400e06e6  mov     [rsp+0E8h+var_60], r12
0x1400e06ee  jmp     short loc_1400E06FB
0x1400e06f0  mov     r14d, 0C0000017h
0x1400e06f6  mov     [rsp+0E8h+var_78], r14d
0x1400e06fb  jmp     short loc_1400E0753
0x1400e06fd  test    byte ptr [rsp+0E8h+SourceString.Length], 1
0x1400e0702  jz      short loc_1400E0722
0x1400e0704  mov     dword ptr [rsp+0E8h+var_98], 20000h
0x1400e070c  mov     r8d, 3DFh
0x1400e0712  mov     edx, dword ptr [rsp+0E8h+var_98]
0x1400e0716  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400e071d  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400e0722  call    cs:__imp_ExRaiseAccessViolation
0x1400e0729  nop     dword ptr [rax+rax+00h]
0x1400e072e  nop
0x1400e072f  mov     r14d, 0C000000Dh
0x1400e0735  mov     [rsp+0E8h+var_78], r14d
0x1400e073a  xor     edi, edi
0x1400e073c  lea     r13, WPP_GLOBAL_Control
0x1400e0743  lea     ebx, [rdi+2]
0x1400e0746  mov     r15, [rsp+0E8h+Object]
0x1400e074b  mov     r12, [rsp+0E8h+var_60]
0x1400e0753  test    r14d, r14d
0x1400e0756  js      loc_1400E082C
0x1400e075c  mov     [rsp+0E8h+var_98], rdi
0x1400e0761  lea     rax, [rsp+0E8h+var_98]
0x1400e0766  mov     [rsp+0E8h+var_B8], rax; __int64
0x1400e076b  mov     [rsp+0E8h+var_C0], rdi; __int64
0x1400e0770  mov     [rsp+0E8h+var_C8], edi; int
0x1400e0774  mov     r9d, 1
0x1400e077a  mov     r8, r12
0x1400e077d  mov     edx, [rsp+0E8h+arg_10]
0x1400e0784  mov     rcx, r15; struct RawInputManagerObject *
0x1400e0787  call    RIMCreateDev
0x1400e078c  mov     r14d, eax
0x1400e078f  test    eax, eax
0x1400e0791  js      loc_1400E082C
0x1400e0797  mov     rax, [rsp+0E8h+var_98]
0x1400e079c  or      dword ptr [rax+0A8h], 1
0x1400e07a3  mov     r8, [rsp+0E8h+Handle]; Handle
0x1400e07ab  mov     rdx, [rsp+0E8h+var_98]; struct RIMDEV *
0x1400e07b0  mov     rcx, r15; struct RawInputManagerObject *
0x1400e07b3  call    rimOnPnpArrived
0x1400e07b8  mov     r14d, eax
0x1400e07bb  test    eax, eax
0x1400e07bd  js      short loc_1400E081A
0x1400e07bf  mov     r8d, ebx
0x1400e07c2  mov     rdx, [rsp+0E8h+var_98]
0x1400e07c7  mov     rcx, r15
0x1400e07ca  call    rimDoRimDevChange
0x1400e07cf  mov     r8, [rsp+0E8h+arg_28]
0x1400e07d7  test    r8, r8
0x1400e07da  jz      short loc_1400E081A
0x1400e07dc  cmp     [rsp+0E8h+arg_20], edi
0x1400e07e3  jnz     short loc_1400E07F3
0x1400e07e5  mov     rax, [rsp+0E8h+var_98]
0x1400e07ea  mov     rcx, [rax+10h]
0x1400e07ee  mov     [r8], rcx
0x1400e07f1  jmp     short loc_1400E081A
0x1400e07f3  mov     rdx, [rsp+0E8h+var_98]
0x1400e07f8  mov     rdx, [rdx+10h]
0x1400e07fc  mov     rcx, r8
0x1400e07ff  call    RtlWriteULong64ToUser
0x1400e0804  jmp     short loc_1400E081A
0x1400e0806  xor     edi, edi
0x1400e0808  mov     r14d, 0C000000Dh
0x1400e080e  lea     r13, WPP_GLOBAL_Control
0x1400e0815  mov     r15, [rsp+0E8h+Object]
0x1400e081a  test    r14d, r14d
0x1400e081d  jns     short loc_1400E082C
0x1400e081f  mov     rdx, [rsp+0E8h+var_98]; struct RIMDEV *
0x1400e0824  mov     rcx, r15; struct RawInputManagerObject *
0x1400e0827  call    RIMFreeDev
0x1400e082c  mov     rcx, [rsp+0E8h+DestinationString.Buffer]; Buffer
0x1400e0834  test    rcx, rcx
0x1400e0837  jz      short loc_1400E083E
0x1400e0839  call    GreDeleteFastMutex
0x1400e083e  lea     r12, WPP_RECORDER_INITIALIZED
0x1400e0845  mov     rcx, [rsp+0E8h+var_58]
0x1400e084d  call    RIMUnlockExclusive
0x1400e0852  mov     rcx, r15; Object
0x1400e0855  call    cs:__imp_ObfDereferenceObject
0x1400e085c  nop     dword ptr [rax+rax+00h]
0x1400e0861  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e0868  cmp     rcx, r13
0x1400e086b  jz      short loc_1400E087C
0x1400e086d  mov     eax, [rcx+2Ch]
0x1400e0870  test    al, 1
0x1400e0872  jz      short loc_1400E087C
0x1400e0874  cmp     byte ptr [rcx+29h], 4
0x1400e0878  mov     bl, 1
0x1400e087a  jnb     short loc_1400E087F
0x1400e087c  mov     bl, dil
0x1400e087f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400e0886  setnz   r15b
0x1400e088a  test    bl, bl
0x1400e088c  jnz     short loc_1400E0893
0x1400e088e  test    r15b, r15b
0x1400e0891  jz      short loc_1400E08E0
0x1400e0893  call    cs:__imp_W32GetUserSessionState
0x1400e089a  nop     dword ptr [rax+rax+00h]
0x1400e089f  mov     r9, [rax+4BD0h]
0x1400e08a6  mov     [rsp+0E8h+var_A8], r14d
0x1400e08ab  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400e08b2  mov     [rsp+0E8h+var_B0], rax
0x1400e08b7  mov     word ptr [rsp+0E8h+var_B8], 22h ; '"'
0x1400e08be  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1400e08c6  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400e08cb  mov     r8b, r15b
0x1400e08ce  mov     dl, bl
0x1400e08d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e08d7  mov     rcx, [rcx+18h]
0x1400e08db  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400e08e0  mov     eax, r14d
0x1400e08e3  add     rsp, 0B8h
0x1400e08ea  pop     r15
0x1400e08ec  pop     r14
0x1400e08ee  pop     r13
0x1400e08f0  pop     r12
0x1400e08f2  pop     rdi
0x1400e08f3  pop     rbx
0x1400e08f4  retn
0x1400e08f6  mov     r14d, 0C00000BBh
0x1400e08fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e0903  cmp     rcx, r13
0x1400e0906  jz      short loc_1400E0917
0x1400e0908  mov     eax, [rcx+2Ch]
0x1400e090b  test    al, 1
0x1400e090d  jz      short loc_1400E0917
0x1400e090f  cmp     byte ptr [rcx+29h], 3
0x1400e0913  mov     bl, 1
0x1400e0915  jnb     short loc_1400E091A
0x1400e0917  mov     bl, dil
0x1400e091a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400e0921  setnz   al
0x1400e0924  mov     byte ptr [rsp+0E8h+Handle], al
0x1400e092b  test    bl, bl
0x1400e092d  jnz     short loc_1400E0937
0x1400e092f  test    al, al
0x1400e0931  jz      loc_1400E0845
0x1400e0937  call    cs:__imp_W32GetUserSessionState
0x1400e093e  nop     dword ptr [rax+rax+00h]
0x1400e0943  mov     r9, [rax+4BD0h]
0x1400e094a  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400e0951  mov     [rsp+0E8h+var_B0], rax
0x1400e0956  mov     word ptr [rsp+0E8h+var_B8], 20h ; ' '
0x1400e095d  mov     dword ptr [rsp+0E8h+var_C0], 1
  ... truncated ...
```
