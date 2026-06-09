# VmBusQueryInterfaceIrpPreprocess

- ea: `0x1400053a0`
- end: `0x1400054f3`
- name: `VmBusQueryInterfaceIrpPreprocess`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400053a0`
- `0x1400055cc`
- `0x140006da0`
- `0x140007430`
- `0x140017190`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400054ae`
- `ntoskrnl!IofCompleteRequest` at `0x1400054ae`

## pseudocode

```c
__int64 __fastcall VmBusQueryInterfaceIrpPreprocess(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v5; // rax
  __int64 v6; // r9
  _QWORD *p_SecurityQos; // rcx
  __int64 v8; // rdx
  unsigned int v9; // edi
  LARGE_INTEGER ByteOffset; // rcx
  __int64 v11; // rsi

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14001C160);
  p_SecurityQos = &CurrentStackLocation->Parameters.Create.SecurityContext->SecurityQos;
  v8 = *p_SecurityQos - *(_QWORD *)&GUID_VMBUS_INTERFACE_STANDARD.Data1;
  if ( *p_SecurityQos == *(_QWORD *)&GUID_VMBUS_INTERFACE_STANDARD.Data1 )
    v8 = p_SecurityQos[1] - *(_QWORD *)GUID_VMBUS_INTERFACE_STANDARD.Data4;
  if ( v8 )
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, IRP *))(WdfFunctions_01033 + 272))(
             WdfDriverGlobals,
             a1,
             a2);
  }
  else
  {
    v9 = -1073741637;
    if ( CurrentStackLocation->Parameters.QueryInterface.Version == 13
      && CurrentStackLocation->Parameters.QueryInterface.Size == 320 )
    {
      ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
      v11 = v5 + 288;
      *(_QWORD *)(ByteOffset.QuadPart + 16) = BusPdoReferenceInterface;
      *(_QWORD *)(ByteOffset.QuadPart + 24) = BusPdoDereferenceInterface;
      *(_QWORD *)(ByteOffset.QuadPart + 32) = BusPdoCloseChannel;
      *(_DWORD *)ByteOffset.QuadPart = 852288;
      *(_QWORD *)(ByteOffset.QuadPart + 8) = v5 + 288;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SharedIoctlFillOutDeviceInterface)(
        (LARGE_INTEGER)ByteOffset.QuadPart,
        13,
        320,
        v6);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9bc149055a283eb2988b2e39efb7d62e_Traceguids, a1);
      }
      v9 = 0;
      BusPdoReferenceInterface(v11);
      a2->IoStatus.Information = 0;
    }
    a2->IoStatus.Status = v9;
    IofCompleteRequest(a2, 0);
    return v9;
  }
}

```

## disassembly

```asm
0x1400053a0  push    rbx
0x1400053a2  push    rbp
0x1400053a3  push    rsi
0x1400053a4  push    rdi
0x1400053a5  sub     rsp, 28h
0x1400053a9  mov     rax, cs:WdfFunctions_01033
0x1400053b0  mov     rbx, rdx
0x1400053b3  mov     rsi, [rdx+0B8h]
0x1400053ba  mov     rbp, rcx
0x1400053bd  mov     r8, cs:off_14001C160
0x1400053c4  mov     rdx, rcx
0x1400053c7  mov     rcx, cs:WdfDriverGlobals
0x1400053ce  mov     rax, [rax+650h]
0x1400053d5  call    _guard_dispatch_icall
0x1400053da  mov     rcx, [rsi+8]
0x1400053de  mov     rdx, [rcx]
0x1400053e1  sub     rdx, qword ptr cs:GUID_VMBUS_INTERFACE_STANDARD.Data1
0x1400053e8  jnz     short loc_1400053F5
0x1400053ea  mov     rdx, [rcx+8]
0x1400053ee  sub     rdx, qword ptr cs:GUID_VMBUS_INTERFACE_STANDARD.Data4
0x1400053f5  test    rdx, rdx
0x1400053f8  jnz     loc_1400054BE
0x1400053fe  mov     edx, 0Dh
0x140005403  mov     edi, 0C00000BBh
0x140005408  cmp     [rsi+12h], dx
0x14000540c  jnz     loc_1400054A6
0x140005412  mov     r8d, 140h
0x140005418  cmp     [rsi+10h], r8w
0x14000541d  jnz     loc_1400054A6
0x140005423  mov     rcx, [rsi+18h]
0x140005427  lea     rsi, [rax+120h]
0x14000542e  lea     rax, BusPdoReferenceInterface
0x140005435  mov     [rcx+10h], rax
0x140005439  lea     rax, BusPdoDereferenceInterface
0x140005440  mov     [rcx+18h], rax
0x140005444  lea     rax, BusPdoCloseChannel
0x14000544b  mov     [rcx+20h], rax
0x14000544f  mov     dword ptr [rcx], 0D0140h
0x140005455  mov     [rcx+8], rsi
0x140005459  call    SharedIoctlFillOutDeviceInterface
0x14000545e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005465  lea     rax, WPP_GLOBAL_Control
0x14000546c  cmp     rcx, rax
0x14000546f  jz      short loc_140005498
0x140005471  test    dword ptr [rcx+2Ch], 800h
0x140005478  jz      short loc_140005498
0x14000547a  cmp     byte ptr [rcx+29h], 4
0x14000547e  jb      short loc_140005498
0x140005480  mov     rcx, [rcx+18h]
0x140005484  lea     r8, WPP_9bc149055a283eb2988b2e39efb7d62e_Traceguids
0x14000548b  mov     edx, 0Ah
0x140005490  mov     r9, rbp
0x140005493  call    WPP_SF_q
0x140005498  xor     edi, edi
0x14000549a  mov     rcx, rsi
0x14000549d  call    BusPdoReferenceInterface
0x1400054a2  mov     [rbx+38h], rdi
0x1400054a6  xor     edx, edx; PriorityBoost
0x1400054a8  mov     [rbx+30h], edi
0x1400054ab  mov     rcx, rbx; Irp
0x1400054ae  call    cs:__imp_IofCompleteRequest
0x1400054b5  nop     dword ptr [rax+rax+00h]
0x1400054ba  mov     eax, edi
0x1400054bc  jmp     short loc_1400054E9
0x1400054be  inc     byte ptr [rbx+43h]
0x1400054c1  mov     r8, rbx
0x1400054c4  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x1400054cc  mov     rdx, rbp
0x1400054cf  mov     rax, cs:WdfFunctions_01033
0x1400054d6  mov     rcx, cs:WdfDriverGlobals
0x1400054dd  mov     rax, [rax+110h]
0x1400054e4  call    _guard_dispatch_icall
0x1400054e9  add     rsp, 28h
0x1400054ed  pop     rdi
0x1400054ee  pop     rsi
0x1400054ef  pop     rbp
0x1400054f0  pop     rbx
0x1400054f1  retn
```
