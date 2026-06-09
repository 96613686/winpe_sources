# InitializeGraphicsInfrastructure

- ea: `0x1400186c0`
- end: `0x14001898c`
- name: `InitializeGraphicsInfrastructure`
- size: `716`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400ba080`

## callees

- `0x140003330`
- `0x140011a90`
- `0x1400186c0`
- `0x14001ca50`
- `0x14001ca8c`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x14001897b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14001897b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140018888`
- `ntoskrnl!KeWaitForSingleObject` at `0x140018888`
- `ntoskrnl!IofCallDriver` at `0x14001885e`
- `ntoskrnl!IofCallDriver` at `0x14001885e`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14001881f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14001881f`
- `ntoskrnl!ObfDereferenceObject` at `0x140018798`
- `ntoskrnl!ObfDereferenceObject` at `0x140018798`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400188cb`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400188cb`
- `ntoskrnl!KeInitializeEvent` at `0x1400187d7`
- `ntoskrnl!KeInitializeEvent` at `0x1400187d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400188bc`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400188bc`
- `ntoskrnl!ExAllocatePool2` at `0x1400186f0`
- `ntoskrnl!ExAllocatePool2` at `0x1400186f0`
- `watchdog!WdLogSingleEntry0` at `0x140018717`
- `watchdog!WdLogSingleEntry0` at `0x1400188e7`
- `watchdog!WdLogSingleEntry0` at `0x140018717`
- `watchdog!WdLogSingleEntry0` at `0x1400188e7`
- `watchdog!WdLogSingleEntry1` at `0x14001876d`
- `watchdog!WdLogSingleEntry1` at `0x14001883d`
- `watchdog!WdLogSingleEntry1` at `0x1400188a1`
- `watchdog!WdLogSingleEntry1` at `0x14001876d`
- `watchdog!WdLogSingleEntry1` at `0x14001883d`
- `watchdog!WdLogSingleEntry1` at `0x1400188a1`

## pseudocode

```c
__int64 __fastcall InitializeGraphicsInfrastructure(__int64 a1)
{
  __int64 SessionState; // rbx
  __int64 Pool2; // rax
  NTSTATUS Status; // ebx
  Gre::Core *v5; // rcx
  __int64 OutputBuffer; // rdi
  PDEVICE_OBJECT *v7; // rsi
  NTSTATUS Dxgkrnl; // eax
  void *v9; // rcx
  struct _DEVICE_OBJECT *v11; // rdx
  IRP *v12; // rax
  __int64 CurrentProcess; // rax
  _QWORD *ProcessWin32Process; // rax
  _KEVENT Event; // [rsp+50h] [rbp-79h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-61h] BYREF
  _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+80h] [rbp-49h] BYREF
  __int64 v18; // [rsp+B8h] [rbp-11h]
  int v19; // [rsp+C0h] [rbp-9h]
  __int64 v20; // [rsp+C8h] [rbp-1h]
  __int128 v21; // [rsp+D0h] [rbp+7h]
  __int128 v22; // [rsp+E0h] [rbp+17h]
  int v23; // [rsp+138h] [rbp+6Fh] BYREF

  SessionState = W32GetSessionState();
  Pool2 = ExAllocatePool2(256, 848, 809977671);
  *(_QWORD *)(SessionState + 80) = Pool2;
  if ( Pool2 )
  {
    Status = 0;
  }
  else
  {
    Status = -1073741801;
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 101;
  }
  OutputBuffer = *(_QWORD *)(W32GetSessionState() + 80);
  if ( Status < 0 )
  {
LABEL_8:
    if ( Gre::Core::IsSessionGlobalsAreaAllocated(v5) )
    {
      v9 = *(void **)(OutputBuffer + 832);
      if ( v9 )
        ObfDereferenceObject(v9);
      Gre::Core::FreeSessionGlobalsArea((Gre::Core *)v9);
    }
    return (unsigned int)Status;
  }
  v7 = (PDEVICE_OBJECT *)(OutputBuffer + 840);
  Dxgkrnl = DlpLoadDxgkrnl((PFILE_OBJECT *)(OutputBuffer + 832), (PDEVICE_OBJECT *)(OutputBuffer + 840));
  Status = Dxgkrnl;
  if ( (int)(Dxgkrnl + 0x80000000) >= 0 && Dxgkrnl != -1073741554 )
  {
    WdLogSingleEntry1(2, Dxgkrnl);
    WdLogGlobalForLineNumber = 118;
    goto LABEL_8;
  }
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v11 = *v7;
  *(_DWORD *)OutputBuffer = 3212088;
  *(_QWORD *)(OutputBuffer + 8) = a1;
  v12 = IoBuildDeviceIoControlRequest(
          0x23E057u,
          v11,
          (PVOID)OutputBuffer,
          0x338u,
          (PVOID)OutputBuffer,
          0x338u,
          1u,
          &Event,
          &IoStatusBlock);
  if ( !v12 )
  {
    Status = -1073741670;
    WdLogSingleEntry1(2, -1073741670);
    WdLogGlobalForLineNumber = 145;
    goto LABEL_8;
  }
  Status = IofCallDriver(*v7, v12);
  if ( Status == 259 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    Status = IoStatusBlock.Status;
  }
  if ( Status < 0 )
  {
    WdLogSingleEntry1(2, Status);
    WdLogGlobalForLineNumber = 157;
    goto LABEL_8;
  }
  CurrentProcess = PsGetCurrentProcess();
  ProcessWin32Process = (_QWORD *)PsGetProcessWin32Process(CurrentProcess);
  if ( ProcessWin32Process && *ProcessWin32Process )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 165;
  }
  v23 = 0;
  QueryTable.QueryRoutine = 0;
  QueryTable.Name = L"DisableLddmSpriteTearDown";
  QueryTable.Flags = 288;
  QueryTable.EntryContext = (PVOID)(OutputBuffer + 824);
  QueryTable.DefaultType = 67108868;
  QueryTable.DefaultData = &v23;
  QueryTable.DefaultLength = 4;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  RtlQueryRegistryValues(2u, L"GraphicsDrivers", &QueryTable, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400186c0  push    rbp
0x1400186c2  push    rbx
0x1400186c3  push    rsi
0x1400186c4  push    rdi
0x1400186c5  push    r12
0x1400186c7  push    r14
0x1400186c9  lea     rbp, [rsp-2Fh]
0x1400186ce  sub     rsp, 0F8h
0x1400186d5  mov     r14, rcx
0x1400186d8  call    W32GetSessionState
0x1400186dd  mov     edx, 350h
0x1400186e2  mov     ecx, 100h
0x1400186e7  mov     r8d, 30474747h
0x1400186ed  mov     rbx, rax
0x1400186f0  call    cs:__imp_ExAllocatePool2
0x1400186f7  nop     dword ptr [rax+rax+00h]
0x1400186fc  mov     [rbx+50h], rax
0x140018700  mov     r12d, 2
0x140018706  test    rax, rax
0x140018709  jz      short loc_14001870F
0x14001870b  xor     ebx, ebx
0x14001870d  jmp     short loc_14001872D
0x14001870f  mov     ebx, 0C0000017h
0x140018714  mov     ecx, r12d
0x140018717  call    cs:__imp_WdLogSingleEntry0
0x14001871e  nop     dword ptr [rax+rax+00h]
0x140018723  mov     cs:WdLogGlobalForLineNumber, 65h ; 'e'
0x14001872d  call    W32GetSessionState
0x140018732  mov     rdi, [rax+50h]
0x140018736  test    ebx, ebx
0x140018738  js      short loc_140018783
0x14001873a  lea     rsi, [rdi+348h]
0x140018741  mov     rdx, rsi; DeviceObject
0x140018744  lea     rcx, [rdi+340h]; FileObject
0x14001874b  call    DlpLoadDxgkrnl
0x140018750  mov     edx, 80000000h
0x140018755  movsxd  rbx, eax
0x140018758  lea     eax, [rbx+rdx]
0x14001875b  test    edx, eax
0x14001875d  jnz     short loc_1400187BC
0x14001875f  cmp     ebx, 0C000010Eh
0x140018765  jz      short loc_1400187BC
0x140018767  mov     rdx, rbx
0x14001876a  mov     ecx, r12d
0x14001876d  call    cs:__imp_WdLogSingleEntry1
0x140018774  nop     dword ptr [rax+rax+00h]
0x140018779  mov     cs:WdLogGlobalForLineNumber, 76h ; 'v'
0x140018783  call    ?IsSessionGlobalsAreaAllocated@Core@Gre@@YA_NXZ; Gre::Core::IsSessionGlobalsAreaAllocated(void)
0x140018788  test    al, al
0x14001878a  jz      short loc_1400187A9
0x14001878c  mov     rcx, [rdi+340h]; Object
0x140018793  test    rcx, rcx
0x140018796  jz      short loc_1400187A4
0x140018798  call    cs:__imp_ObfDereferenceObject
0x14001879f  nop     dword ptr [rax+rax+00h]
0x1400187a4  call    ?FreeSessionGlobalsArea@Core@Gre@@YAXXZ; Gre::Core::FreeSessionGlobalsArea(void)
0x1400187a9  mov     eax, ebx
0x1400187ab  add     rsp, 0F8h
0x1400187b2  pop     r14
0x1400187b4  pop     r12
0x1400187b6  pop     rdi
0x1400187b7  pop     rsi
0x1400187b8  pop     rbx
0x1400187b9  pop     rbp
0x1400187ba  retn
0x1400187bc  xor     eax, eax
0x1400187be  lea     rcx, [rbp+57h+Event]; Event
0x1400187c2  xorps   xmm0, xmm0
0x1400187c5  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x1400187c9  xor     r8d, r8d; State
0x1400187cc  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x1400187d0  lea     edx, [rax+1]; Type
0x1400187d3  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x1400187d7  call    cs:__imp_KeInitializeEvent
0x1400187de  nop     dword ptr [rax+rax+00h]
0x1400187e3  mov     rdx, [rsi]; DeviceObject
0x1400187e6  lea     rax, [rbp+57h+var_B8]
0x1400187ea  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x1400187ef  mov     r9d, 338h; InputBufferLength
0x1400187f5  lea     rax, [rbp+57h+Event]
0x1400187f9  mov     dword ptr [rdi], 310338h
0x1400187ff  mov     [rsp+120h+var_E8], rax; Event
0x140018804  mov     r8, rdi; InputBuffer
0x140018807  mov     [rsp+120h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x14001880c  mov     ecx, 23E057h; IoControlCode
0x140018811  mov     [rsp+120h+OutputBufferLength], r9d; OutputBufferLength
0x140018816  mov     [rsp+120h+OutputBuffer], rdi; OutputBuffer
0x14001881b  mov     [rdi+8], r14
0x14001881f  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140018826  nop     dword ptr [rax+rax+00h]
0x14001882b  test    rax, rax
0x14001882e  jnz     short loc_140018858
0x140018830  mov     rbx, 0FFFFFFFFC000009Ah
0x140018837  mov     rdx, rbx
0x14001883a  mov     ecx, r12d
0x14001883d  call    cs:__imp_WdLogSingleEntry1
0x140018844  nop     dword ptr [rax+rax+00h]
0x140018849  mov     cs:WdLogGlobalForLineNumber, 91h
0x140018853  jmp     loc_140018783
0x140018858  mov     rcx, [rsi]; DeviceObject
0x14001885b  mov     rdx, rax; Irp
0x14001885e  call    cs:__imp_IofCallDriver
0x140018865  nop     dword ptr [rax+rax+00h]
0x14001886a  mov     ebx, eax
0x14001886c  cmp     eax, 103h
0x140018871  jnz     short loc_140018897
0x140018873  xor     r9d, r9d; Alertable
0x140018876  mov     [rsp+120h+OutputBuffer], 0; Timeout
0x14001887f  xor     r8d, r8d; WaitMode
0x140018882  lea     rcx, [rbp+57h+Event]; Object
0x140018886  xor     edx, edx; WaitReason
0x140018888  call    cs:__imp_KeWaitForSingleObject
0x14001888f  nop     dword ptr [rax+rax+00h]
0x140018894  mov     ebx, dword ptr [rbp+57h+var_B8]
0x140018897  test    ebx, ebx
0x140018899  jns     short loc_1400188BC
0x14001889b  movsxd  rdx, ebx
0x14001889e  mov     ecx, r12d
0x1400188a1  call    cs:__imp_WdLogSingleEntry1
0x1400188a8  nop     dword ptr [rax+rax+00h]
0x1400188ad  mov     cs:WdLogGlobalForLineNumber, 9Dh
0x1400188b7  jmp     loc_140018783
0x1400188bc  call    cs:__imp_PsGetCurrentProcess
0x1400188c3  nop     dword ptr [rax+rax+00h]
0x1400188c8  mov     rcx, rax
0x1400188cb  call    cs:__imp_PsGetProcessWin32Process
0x1400188d2  nop     dword ptr [rax+rax+00h]
0x1400188d7  test    rax, rax
0x1400188da  jz      short loc_1400188FD
0x1400188dc  cmp     qword ptr [rax], 0
0x1400188e0  jz      short loc_1400188FD
0x1400188e2  mov     ecx, 1
0x1400188e7  call    cs:__imp_WdLogSingleEntry0
0x1400188ee  nop     dword ptr [rax+rax+00h]
0x1400188f3  mov     cs:WdLogGlobalForLineNumber, 0A5h
0x1400188fd  xorps   xmm0, xmm0
0x140018900  mov     [rbp+57h+arg_8], 0
0x140018907  lea     rax, aDisablelddmspr; "DisableLddmSpriteTearDown"
0x14001890e  mov     [rbp+57h+QueryTable.QueryRoutine], 0
0x140018916  mov     [rbp+57h+QueryTable.Name], rax
0x14001891a  lea     r8, [rbp+57h+QueryTable]; QueryTable
0x14001891e  lea     rax, [rdi+338h]
0x140018925  mov     [rbp+57h+QueryTable.Flags], 120h
0x14001892c  mov     [rbp+57h+QueryTable.EntryContext], rax
0x140018930  lea     rdx, Path; "GraphicsDrivers"
0x140018937  lea     rax, [rbp+57h+arg_8]
0x14001893b  mov     [rbp+57h+QueryTable.DefaultType], 4000004h
0x140018942  xor     r9d, r9d; Context
0x140018945  mov     [rbp+57h+QueryTable.DefaultData], rax
0x140018949  mov     ecx, r12d; RelativeTo
0x14001894c  mov     [rbp+57h+QueryTable.DefaultLength], 4
0x140018953  mov     [rbp+57h+var_68], 0
0x14001895b  mov     [rbp+57h+var_60], 0
0x140018962  mov     [rbp+57h+var_58], 0
0x14001896a  movups  [rbp+57h+var_50], xmm0
0x14001896e  mov     [rsp+120h+OutputBuffer], 0; Environment
0x140018977  movups  [rbp+57h+var_40], xmm0
0x14001897b  call    cs:__imp_RtlQueryRegistryValues
0x140018982  nop     dword ptr [rax+rax+00h]
0x140018987  jmp     loc_1400187A9
```
