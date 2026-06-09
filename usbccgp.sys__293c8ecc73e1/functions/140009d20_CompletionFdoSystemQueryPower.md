# CompletionFdoSystemQueryPower

- ea: `0x140009d20`
- end: `0x140009f0a`
- name: `CompletionFdoSystemQueryPower`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400054a0`
- `0x140007020`
- `0x1400092ec`
- `0x140009d20`
- `0x14000b4bc`
- `0x140014458`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140009e3c`
- `ntoskrnl!IofCompleteRequest` at `0x140009e3c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140009e2b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140009e2b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009e63`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140009e63`
- `ntoskrnl!PoRequestPowerIrp` at `0x140009dc0`
- `ntoskrnl!PoRequestPowerIrp` at `0x140009dc0`

## pseudocode

```c
__int64 __fastcall CompletionFdoSystemQueryPower(__int64 a1, IRP *a2, __int64 a3, int a4)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  IRP *Context; // rdi
  POWER_STATE v7; // ebx
  unsigned int LowPart; // r14d
  POWER_STATE v9; // eax
  NTSTATUS v10; // eax
  int v11; // edx
  int Status; // ebx
  int v14; // r9d
  __int64 v15; // rax
  char v16; // [rsp+30h] [rbp-48h]
  char SystemState; // [rsp+38h] [rbp-40h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Context = a2;
  if ( a2->IoStatus.Status < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qLd(*(_QWORD *)(a3 + 1368), (_DWORD)a2, a3, a4);
    Status = Context->IoStatus.Status;
    goto LABEL_16;
  }
  v7.SystemState = PowerSystemWorking;
  if ( a2->PendingReturned )
    CurrentStackLocation->Control |= 1u;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_10;
    v15 = *(_QWORD *)(a3 + 32);
    v14 = 43;
    SystemState = 1;
    v16 = 1;
LABEL_20:
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qLL(
      *(_QWORD *)(a3 + 1368),
      (_DWORD)a2,
      3,
      v14,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      v15,
      v16,
      SystemState);
    goto LABEL_10;
  }
  if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 2
    && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 3
    && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 4
    && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 5 > 1 )
  {
    Status = a2->IoStatus.Status;
LABEL_16:
    Context->IoStatus.Status = Status;
    PoStartNextPowerIrp(Context);
    IofCompleteRequest(Context, 0);
    UsbcReleaseRemoveLock(a3, Context);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a3 + 200), Context, 0x20u);
    return 3221225494LL;
  }
  v9.SystemState = MapSystemStateToDeviceState(a3, LowPart);
  v7.SystemState = v9.SystemState;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    SystemState = v9.SystemState;
    v14 = 42;
    v15 = *(_QWORD *)(a3 + 32);
    v16 = LowPart;
    goto LABEL_20;
  }
LABEL_10:
  v10 = PoRequestPowerIrp(*(PDEVICE_OBJECT *)(a3 + 32), 3u, v7, CallbackFdoDeviceQueryPower, Context, 0);
  Status = v10;
  if ( v10 != 259 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(a3 + 1368),
        v11,
        8,
        44,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *(_QWORD *)(a3 + 32),
        v10);
    }
    goto LABEL_16;
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140009d20  push    rbx
0x140009d22  push    rbp
0x140009d23  push    rsi
0x140009d24  push    rdi
0x140009d25  push    r14
0x140009d27  push    r15
0x140009d29  sub     rsp, 48h
0x140009d2d  mov     ecx, [rdx+30h]
0x140009d30  mov     rsi, r8
0x140009d33  mov     rax, [rdx+0B8h]
0x140009d3a  mov     rdi, rdx
0x140009d3d  test    ecx, ecx
0x140009d3f  js      loc_140009E0E
0x140009d45  cmp     byte ptr [rdx+41h], 0
0x140009d49  mov     ebx, 1
0x140009d4e  jz      short loc_140009D53
0x140009d50  or      [rax+3], bl
0x140009d53  mov     r14d, [rax+18h]
0x140009d57  lea     r15, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140009d5e  mov     ecx, r14d
0x140009d61  sub     ecx, ebx
0x140009d63  jz      loc_140009EE2
0x140009d69  sub     ecx, ebx
0x140009d6b  jz      short loc_140009D81
0x140009d6d  sub     ecx, ebx
0x140009d6f  jz      short loc_140009D81
0x140009d71  sub     ecx, ebx
0x140009d73  jz      short loc_140009D81
0x140009d75  sub     ecx, ebx
0x140009d77  jz      short loc_140009D81
0x140009d79  cmp     ecx, ebx
0x140009d7b  jnz     loc_140009E82
0x140009d81  mov     edx, r14d
0x140009d84  mov     rcx, rsi
0x140009d87  call    MapSystemStateToDeviceState
0x140009d8c  mov     ebx, eax
0x140009d8e  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009d95  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140009d9c  jnz     loc_140009E87
0x140009da2  mov     rcx, [rsi+20h]; DeviceObject
0x140009da6  lea     r9, CallbackFdoDeviceQueryPower; CompletionFunction
0x140009dad  mov     [rsp+78h+Irp], 0; Irp
0x140009db6  mov     r8d, ebx; PowerState
0x140009db9  mov     dl, 3; MinorFunction
0x140009dbb  mov     [rsp+78h+Context], rdi; Context
0x140009dc0  call    cs:__imp_PoRequestPowerIrp
0x140009dc7  nop     dword ptr [rax+rax+00h]
0x140009dcc  mov     ebx, eax
0x140009dce  cmp     eax, 103h
0x140009dd3  jz      loc_140009E6F
0x140009dd9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x140009de0  jz      short loc_140009E25
0x140009de2  mov     rcx, [rsi+20h]
0x140009de6  mov     r9d, 2Ch ; ','
0x140009dec  mov     dword ptr [rsp+78h+var_48], eax
0x140009df0  mov     dl, 2
0x140009df2  mov     [rsp+78h+Irp], rcx
0x140009df7  mov     rcx, [rsi+558h]
0x140009dfe  lea     r8d, [r9-24h]
0x140009e02  mov     [rsp+78h+Context], r15
0x140009e07  call    WPP_RECORDER_SF_qD
0x140009e0c  jmp     short loc_140009E25
0x140009e0e  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009e15  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140009e1c  jnz     loc_140009EBD
0x140009e22  mov     ebx, [rdi+30h]
0x140009e25  mov     rcx, rdi; Irp
0x140009e28  mov     [rdi+30h], ebx
0x140009e2b  call    cs:__imp_PoStartNextPowerIrp
0x140009e32  nop     dword ptr [rax+rax+00h]
0x140009e37  xor     edx, edx; PriorityBoost
0x140009e39  mov     rcx, rdi; Irp
0x140009e3c  call    cs:__imp_IofCompleteRequest
0x140009e43  nop     dword ptr [rax+rax+00h]
0x140009e48  mov     rdx, rdi
0x140009e4b  mov     rcx, rsi
0x140009e4e  call    UsbcReleaseRemoveLock
0x140009e53  lea     rcx, [rsi+0C8h]; RemoveLock
0x140009e5a  mov     r8d, 20h ; ' '; RemlockSize
0x140009e60  mov     rdx, rdi; Tag
0x140009e63  call    cs:__imp_IoReleaseRemoveLockEx
0x140009e6a  nop     dword ptr [rax+rax+00h]
0x140009e6f  mov     eax, 0C0000016h
0x140009e74  add     rsp, 48h
0x140009e78  pop     r15
0x140009e7a  pop     r14
0x140009e7c  pop     rdi
0x140009e7d  pop     rsi
0x140009e7e  pop     rbp
0x140009e7f  pop     rbx
0x140009e80  retn
0x140009e82  mov     ebx, [rdx+30h]
0x140009e85  jmp     short loc_140009E25
0x140009e87  mov     dword ptr [rsp+78h+var_40], eax
0x140009e8b  mov     r9d, 2Ah ; '*'
0x140009e91  mov     rax, [rsi+20h]
0x140009e95  mov     dword ptr [rsp+78h+var_48], r14d
0x140009e9a  mov     rcx, [rsi+558h]
0x140009ea1  mov     r8d, 3
0x140009ea7  mov     [rsp+78h+Irp], rax
0x140009eac  mov     dl, 4
0x140009eae  mov     [rsp+78h+Context], r15
0x140009eb3  call    WPP_RECORDER_SF_qLL
0x140009eb8  jmp     loc_140009DA2
0x140009ebd  mov     eax, [rax+18h]
0x140009ec0  mov     dword ptr [rsp+78h+var_40], ecx
0x140009ec4  mov     rcx, [r8+558h]
0x140009ecb  mov     dword ptr [rsp+78h+var_48], eax
0x140009ecf  mov     rax, [r8+20h]
0x140009ed3  mov     [rsp+78h+Irp], rax
0x140009ed8  call    WPP_RECORDER_SF_qLd
0x140009edd  jmp     loc_140009E22
0x140009ee2  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140009ee9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140009ef0  jz      loc_140009DA2
0x140009ef6  mov     rax, [r8+20h]
0x140009efa  mov     r9d, 2Bh ; '+'
0x140009f00  mov     dword ptr [rsp+78h+var_40], ebx
0x140009f04  mov     dword ptr [rsp+78h+var_48], ebx
0x140009f08  jmp     short loc_140009E9A
```
