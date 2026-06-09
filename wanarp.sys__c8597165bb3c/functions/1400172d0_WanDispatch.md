# WanDispatch

- ea: `0x1400172d0`
- end: `0x14001753b`
- name: `WanDispatch`
- size: `619`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT, IRP *)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400035e4`
- `0x1400036e8`
- `0x1400038e8`
- `0x140003adc`
- `0x140011618`
- `0x14001203c`
- `0x1400120fc`
- `0x140012460`
- `0x1400124bc`
- `0x1400129e4`
- `0x140012ccc`
- `0x140012e3c`
- `0x14001324c`
- `0x140013708`
- `0x1400139e8`
- `0x1400172d0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001744b`
- `ntoskrnl!IofCompleteRequest` at `0x14001744b`
- `ntoskrnl!MmLockPagableDataSection` at `0x1400174c1`
- `ntoskrnl!MmLockPagableDataSection` at `0x1400174c1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017513`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017513`

## pseudocode

```c
__int64 __fastcall WanDispatch(PDEVICE_OBJECT a1, IRP *a2)
{
  bool v2; // zf
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  bool v5; // si
  UCHAR MajorFunction; // al
  unsigned int v7; // ebx
  unsigned int LowPart; // ebx
  ULONG Options; // ebp
  ULONG Length; // r14d
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  unsigned int started; // eax
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 *v18; // rcx

  v2 = a1 == DeviceObject;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Information = 0;
  v5 = v2;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction )
  {
    if ( MajorFunction == 2 )
    {
      v7 = 0;
      goto LABEL_29;
    }
    if ( MajorFunction != 14 )
    {
      if ( MajorFunction == 18 )
      {
        v7 = 0;
        LOBYTE(CurrentStackLocation) = v2;
        WanpDriverCleanupNotification(CurrentStackLocation);
      }
      else
      {
        v7 = -1073741811;
      }
      goto LABEL_29;
    }
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    Options = CurrentStackLocation->Parameters.Create.Options;
    Length = CurrentStackLocation->Parameters.Read.Length;
    LOBYTE(CurrentStackLocation) = v2;
    if ( !(unsigned __int8)EnterModuleCode(CurrentStackLocation) )
    {
      v7 = -1073741810;
LABEL_29:
      a2->IoStatus.Status = v7;
      IofCompleteRequest(a2, 2);
      return v7;
    }
    if ( LowPart > 0x90018018 )
    {
      switch ( LowPart )
      {
        case 0x9001801C:
          started = WanAllocLuidIndex(a2, Options, Length);
          goto LABEL_36;
        case 0x90018020:
          started = WanFreeLuidIndex(a2, Options);
          goto LABEL_36;
        case 0x90018024:
          LOBYTE(v13) = v5;
          started = WanRecreateInterface(a2, Options, v12, v13);
          goto LABEL_36;
        case 0x90018028:
          started = WanSetInterfaceSubnetInfo(a2->AssociatedIrp.MasterIrp, Options);
          goto LABEL_36;
        case 0x9001802C:
          LOBYTE(v13) = v5;
          started = WanSetIpAddresses(a2, Options, v12, v13);
          goto LABEL_36;
      }
    }
    else
    {
      switch ( LowPart )
      {
        case 0x90018018:
          LOBYTE(v13) = v5;
          started = WanStartStopQueuing(a2, Options, Length, v13);
          goto LABEL_36;
        case 0x90018000:
          LOBYTE(v13) = v5;
          started = WanProcessNotification(a2, Options, Length, v13);
          goto LABEL_36;
        case 0x90018004:
          LOBYTE(v13) = v5;
          started = WanAddUserModeInterface(a2, Options, Length, v13);
          goto LABEL_36;
        case 0x90018008:
          LOBYTE(v13) = v5;
          started = WanDeleteUserModeInterface(a2, Options, v12, v13);
          goto LABEL_36;
        case 0x9001800C:
          LOBYTE(v13) = v5;
          started = WanProcessConnectionFailure(a2, Options, v12, v13);
          goto LABEL_36;
        case 0x90018014:
          LOBYTE(v13) = v5;
          started = WanMapServerAdapter(a2, Options, Length, v13);
LABEL_36:
          v7 = started;
          goto LABEL_28;
      }
    }
    v7 = -1073741811;
    goto LABEL_28;
  }
  if ( !g_fPagesLocked )
  {
    MmLockPagableDataSection(&WanpCreateAdapter);
    g_fPagesLocked = 1;
  }
  LOBYTE(CurrentStackLocation) = v5;
  v16 = WanpStartModule(CurrentStackLocation);
  v7 = v16;
  if ( v16 )
  {
    if ( v16 != 259 )
      goto LABEL_29;
    v18 = qword_140009A88;
    if ( !v5 )
      v18 = (__int64 *)&stru_140009BA8;
    v7 = KeWaitForSingleObject(v18, Executive, 0, 0, 0);
  }
  LOBYTE(v17) = v5;
  if ( !(unsigned __int8)EnterModuleCode(v17) )
  {
    v7 = -1073741823;
    goto LABEL_29;
  }
LABEL_28:
  LOBYTE(v11) = v5;
  ExitModuleCode(v11);
  if ( v7 != 259 )
    goto LABEL_29;
  return v7;
}

```

## disassembly

```asm
0x1400172d0  push    rbx
0x1400172d2  push    rbp
0x1400172d3  push    rsi
0x1400172d4  push    rdi
0x1400172d5  push    r14
0x1400172d7  sub     rsp, 30h
0x1400172db  cmp     rcx, cs:DeviceObject
0x1400172e2  mov     rdi, rdx
0x1400172e5  mov     rcx, [rdx+0B8h]
0x1400172ec  mov     qword ptr [rdx+38h], 0
0x1400172f4  setz    sil
0x1400172f8  mov     al, [rcx]
0x1400172fa  test    al, al
0x1400172fc  jz      loc_1400174B1
0x140017302  cmp     al, 2
0x140017304  jz      loc_1400174AD
0x14001730a  cmp     al, 0Eh
0x14001730c  jz      short loc_14001732B
0x14001730e  cmp     al, 12h
0x140017310  jz      short loc_14001731C
0x140017312  mov     ebx, 0C000000Dh
0x140017317  jmp     loc_140017443
0x14001731c  xor     ebx, ebx
0x14001731e  mov     cl, sil
0x140017321  call    WanpDriverCleanupNotification
0x140017326  jmp     loc_140017443
0x14001732b  mov     ebx, [rcx+18h]
0x14001732e  mov     ebp, [rcx+10h]
0x140017331  mov     r14d, [rcx+8]
0x140017335  mov     cl, sil
0x140017338  call    EnterModuleCode
0x14001733d  test    al, al
0x14001733f  jnz     short loc_14001734B
0x140017341  mov     ebx, 0C000000Eh
0x140017346  jmp     loc_140017443
0x14001734b  mov     eax, 90018018h
0x140017350  cmp     ebx, eax
0x140017352  ja      loc_140017402
0x140017358  jz      loc_1400173ED
0x14001735e  cmp     ebx, 90018000h
0x140017364  jz      short loc_1400173D8
0x140017366  cmp     ebx, 90018004h
0x14001736c  jz      short loc_1400173C3
0x14001736e  cmp     ebx, 90018008h
0x140017374  jz      short loc_1400173B1
0x140017376  cmp     ebx, 9001800Ch
0x14001737c  jz      short loc_14001739F
0x14001737e  cmp     ebx, 90018014h
0x140017384  jnz     loc_14001742E
0x14001738a  mov     r9b, sil
0x14001738d  mov     r8d, r14d
0x140017390  mov     edx, ebp
0x140017392  mov     rcx, rdi
0x140017395  call    WanMapServerAdapter
0x14001739a  jmp     loc_1400174A9
0x14001739f  mov     r9b, sil
0x1400173a2  mov     edx, ebp
0x1400173a4  mov     rcx, rdi
0x1400173a7  call    WanProcessConnectionFailure
0x1400173ac  jmp     loc_1400174A9
0x1400173b1  mov     r9b, sil
0x1400173b4  mov     edx, ebp
0x1400173b6  mov     rcx, rdi
0x1400173b9  call    WanDeleteUserModeInterface
0x1400173be  jmp     loc_1400174A9
0x1400173c3  mov     r9b, sil
0x1400173c6  mov     r8d, r14d
0x1400173c9  mov     edx, ebp
0x1400173cb  mov     rcx, rdi
0x1400173ce  call    WanAddUserModeInterface
0x1400173d3  jmp     loc_1400174A9
0x1400173d8  mov     r9b, sil
0x1400173db  mov     r8d, r14d
0x1400173de  mov     edx, ebp
0x1400173e0  mov     rcx, rdi
0x1400173e3  call    WanProcessNotification
0x1400173e8  jmp     loc_1400174A9
0x1400173ed  mov     r9b, sil
0x1400173f0  mov     r8d, r14d
0x1400173f3  mov     edx, ebp
0x1400173f5  mov     rcx, rdi
0x1400173f8  call    WanStartStopQueuing
0x1400173fd  jmp     loc_1400174A9
0x140017402  cmp     ebx, 9001801Ch
0x140017408  jz      loc_14001749C
0x14001740e  cmp     ebx, 90018020h
0x140017414  jz      short loc_140017490
0x140017416  cmp     ebx, 90018024h
0x14001741c  jz      short loc_140017481
0x14001741e  cmp     ebx, 90018028h
0x140017424  jz      short loc_140017474
0x140017426  cmp     ebx, 9001802Ch
0x14001742c  jz      short loc_140017465
0x14001742e  mov     ebx, 0C000000Dh
0x140017433  mov     cl, sil
0x140017436  call    ExitModuleCode
0x14001743b  cmp     ebx, 103h
0x140017441  jz      short loc_140017457
0x140017443  mov     dl, 2; PriorityBoost
0x140017445  mov     [rdi+30h], ebx
0x140017448  mov     rcx, rdi; Irp
0x14001744b  call    cs:__imp_IofCompleteRequest
0x140017452  nop     dword ptr [rax+rax+00h]
0x140017457  mov     eax, ebx
0x140017459  add     rsp, 30h
0x14001745d  pop     r14
0x14001745f  pop     rdi
0x140017460  pop     rsi
0x140017461  pop     rbp
0x140017462  pop     rbx
0x140017463  retn
0x140017465  mov     r9b, sil
0x140017468  mov     edx, ebp
0x14001746a  mov     rcx, rdi
0x14001746d  call    WanSetIpAddresses
0x140017472  jmp     short loc_1400174A9
0x140017474  mov     rcx, [rdi+18h]
0x140017478  mov     edx, ebp
0x14001747a  call    WanSetInterfaceSubnetInfo
0x14001747f  jmp     short loc_1400174A9
0x140017481  mov     r9b, sil
0x140017484  mov     edx, ebp
0x140017486  mov     rcx, rdi
0x140017489  call    WanRecreateInterface
0x14001748e  jmp     short loc_1400174A9
0x140017490  mov     edx, ebp
0x140017492  mov     rcx, rdi
0x140017495  call    WanFreeLuidIndex
0x14001749a  jmp     short loc_1400174A9
0x14001749c  mov     r8d, r14d
0x14001749f  mov     edx, ebp
0x1400174a1  mov     rcx, rdi
0x1400174a4  call    WanAllocLuidIndex
0x1400174a9  mov     ebx, eax
0x1400174ab  jmp     short loc_140017433
0x1400174ad  xor     ebx, ebx
0x1400174af  jmp     short loc_140017443
0x1400174b1  cmp     cs:g_fPagesLocked, 0
0x1400174b8  jnz     short loc_1400174D4
0x1400174ba  lea     rcx, WanpCreateAdapter; AddressWithinSection
0x1400174c1  call    cs:__imp_MmLockPagableDataSection
0x1400174c8  nop     dword ptr [rax+rax+00h]
0x1400174cd  mov     cs:g_fPagesLocked, 1
0x1400174d4  mov     cl, sil
0x1400174d7  call    WanpStartModule
0x1400174dc  mov     ebx, eax
0x1400174de  test    eax, eax
0x1400174e0  jz      short loc_140017521
0x1400174e2  cmp     eax, 103h
0x1400174e7  jnz     loc_140017443
0x1400174ed  test    sil, sil
0x1400174f0  mov     [rsp+58h+Timeout], 0; Timeout
0x1400174f9  lea     rax, stru_140009BA8
0x140017500  lea     rcx, qword_140009A88
0x140017507  cmovz   rcx, rax; Object
0x14001750b  xor     r9d, r9d; Alertable
0x14001750e  xor     r8d, r8d; WaitMode
0x140017511  xor     edx, edx; WaitReason
0x140017513  call    cs:__imp_KeWaitForSingleObject
0x14001751a  nop     dword ptr [rax+rax+00h]
0x14001751f  mov     ebx, eax
0x140017521  mov     cl, sil
0x140017524  call    EnterModuleCode
0x140017529  test    al, al
0x14001752b  jnz     loc_140017433
0x140017531  mov     ebx, 0C0000001h
0x140017536  jmp     loc_140017443
```
