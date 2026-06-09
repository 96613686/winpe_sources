# HandlePdoQueryInterface

- ea: `0x14002ad60`
- end: `0x14002aebe`
- name: `HandlePdoQueryInterface`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140010650`

## callees

- `0x1400029d0`
- `0x140003388`
- `0x14002ad60`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002ad89`
- `ntoskrnl!RtlCompareMemory` at `0x14002ada8`
- `ntoskrnl!RtlCompareMemory` at `0x14002ad89`
- `ntoskrnl!RtlCompareMemory` at `0x14002ada8`

## pseudocode

```c
__int64 __fastcall HandlePdoQueryInterface(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned int Status; // ebx
  _LARGE_INTEGER v7; // rax
  _LARGE_INTEGER ByteOffset; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( RtlCompareMemory(CurrentStackLocation->Parameters.Create.SecurityContext, &GUID_D3COLD_SUPPORT_INTERFACE, 0x10u) == 16 )
  {
    if ( CurrentStackLocation->Parameters.QueryInterface.Size == 72
      && CurrentStackLocation->Parameters.QueryInterface.Version == 1 )
    {
      Status = 0;
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 232) + 441LL) )
      {
        ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
        *(_QWORD *)(ByteOffset.QuadPart + 32) = D3ColdSupportInterfaceFunctionSetD3ColdSupport;
        *(_QWORD *)(ByteOffset.QuadPart + 40) = D3ColdSupportInterfaceFunctionGetIdleWakeInfo;
        *(_QWORD *)(ByteOffset.QuadPart + 24) = D3ColdSupportFunctionInterfaceDereference;
        *(_QWORD *)(ByteOffset.QuadPart + 16) = D3ColdSupportFunctionInterfaceReference;
        *(_QWORD *)(ByteOffset.QuadPart + 48) = D3ColdSupportInterfaceFunctionGetD3ColdCapability;
        *(_QWORD *)(ByteOffset.QuadPart + 56) = D3ColdSupportInterfaceFunctionGetBusDriverD3ColdSupport;
        *(_QWORD *)(ByteOffset.QuadPart + 64) = D3ColdSupportInterfaceFunctionGetLastTransitionStatus;
        *(_DWORD *)ByteOffset.QuadPart = 65608;
        *(_QWORD *)(ByteOffset.QuadPart + 8) = a1;
        goto LABEL_10;
      }
    }
    goto LABEL_6;
  }
  if ( RtlCompareMemory(CurrentStackLocation->Parameters.Create.SecurityContext, &GUID_PNP_LOCATION_INTERFACE, 0x10u) == 16 )
  {
    if ( CurrentStackLocation->Parameters.QueryInterface.Size >= 0x28u
      && CurrentStackLocation->Parameters.QueryInterface.Version )
    {
      v7 = CurrentStackLocation->Parameters.Read.ByteOffset;
      Status = 0;
      *(_QWORD *)(v7.QuadPart + 16) = PnpLocationInterfaceDereference;
      *(_QWORD *)(v7.QuadPart + 24) = PnpLocationInterfaceDereference;
      *(_QWORD *)(v7.QuadPart + 32) = PnpLocationInterfaceGetLocationStrings;
      *(_DWORD *)v7.QuadPart = 65576;
      *(_QWORD *)(v7.QuadPart + 8) = a1;
      goto LABEL_10;
    }
LABEL_6:
    Status = a2->IoStatus.Status;
LABEL_10:
    UsbcCompleteIrp(*(_QWORD *)(a1 + 232), Status, a2);
    return Status;
  }
  return (unsigned int)UsbcForwardIrp(*(_QWORD *)(a1 + 232), *(_QWORD *)(*(_QWORD *)(a1 + 232) + 32LL), a2);
}

```

## disassembly

```asm
0x14002ad60  push    rbx
0x14002ad62  push    rbp
0x14002ad63  push    rsi
0x14002ad64  push    rdi
0x14002ad65  sub     rsp, 28h
0x14002ad69  mov     rsi, [rdx+0B8h]
0x14002ad70  mov     rdi, rdx
0x14002ad73  mov     rbp, rcx
0x14002ad76  lea     rdx, GUID_D3COLD_SUPPORT_INTERFACE; Source2
0x14002ad7d  mov     ebx, 10h
0x14002ad82  mov     r8d, ebx; Length
0x14002ad85  mov     rcx, [rsi+8]; Source1
0x14002ad89  call    cs:__imp_RtlCompareMemory
0x14002ad90  nop     dword ptr [rax+rax+00h]
0x14002ad95  cmp     rax, rbx
0x14002ad98  jz      short loc_14002ADDA
0x14002ad9a  mov     rcx, [rsi+8]; Source1
0x14002ad9e  lea     rdx, GUID_PNP_LOCATION_INTERFACE; Source2
0x14002ada5  mov     r8d, ebx; Length
0x14002ada8  call    cs:__imp_RtlCompareMemory
0x14002adaf  nop     dword ptr [rax+rax+00h]
0x14002adb4  cmp     rax, rbx
0x14002adb7  jz      short loc_14002ADEA
0x14002adb9  mov     rcx, [rbp+0E8h]
0x14002adc0  mov     r8, rdi
0x14002adc3  mov     rdx, [rcx+20h]
0x14002adc7  call    UsbcForwardIrp
0x14002adcc  mov     ebx, eax
0x14002adce  mov     eax, ebx
0x14002add0  add     rsp, 28h
0x14002add4  pop     rdi
0x14002add5  pop     rsi
0x14002add6  pop     rbp
0x14002add7  pop     rbx
0x14002add8  retn
0x14002adda  mov     edx, 48h ; 'H'
0x14002addf  cmp     [rsi+10h], dx
0x14002ade3  jz      short loc_14002AE42
0x14002ade5  mov     ebx, [rdi+30h]
0x14002ade8  jmp     short loc_14002AE2F
0x14002adea  mov     edx, 28h ; '('
0x14002adef  cmp     [rsi+10h], dx
0x14002adf3  jb      short loc_14002ADE5
0x14002adf5  lea     ecx, [rdx-27h]
0x14002adf8  cmp     [rsi+12h], cx
0x14002adfc  jb      short loc_14002ADE5
0x14002adfe  mov     rax, [rsi+18h]
0x14002ae02  lea     rcx, PnpLocationInterfaceDereference
0x14002ae09  xor     ebx, ebx
0x14002ae0b  mov     [rax+10h], rcx
0x14002ae0f  lea     rcx, PnpLocationInterfaceDereference
0x14002ae16  mov     [rax+18h], rcx
0x14002ae1a  lea     rcx, PnpLocationInterfaceGetLocationStrings
0x14002ae21  mov     [rax+20h], rcx
0x14002ae25  mov     dword ptr [rax], 10028h
0x14002ae2b  mov     [rax+8], rbp
0x14002ae2f  mov     rcx, [rbp+0E8h]
0x14002ae36  mov     r8, rdi
0x14002ae39  mov     edx, ebx
0x14002ae3b  call    UsbcCompleteIrp
0x14002ae40  jmp     short loc_14002ADCE
0x14002ae42  mov     ecx, 1
0x14002ae47  cmp     [rsi+12h], cx
0x14002ae4b  jnz     short loc_14002ADE5
0x14002ae4d  mov     rax, [rbp+0E8h]
0x14002ae54  xor     ebx, ebx
0x14002ae56  cmp     [rax+1B9h], bl
0x14002ae5c  jz      short loc_14002ADE5
0x14002ae5e  mov     rax, [rsi+18h]
0x14002ae62  lea     rcx, D3ColdSupportInterfaceFunctionSetD3ColdSupport
0x14002ae69  mov     [rax+20h], rcx
0x14002ae6d  lea     rcx, D3ColdSupportInterfaceFunctionGetIdleWakeInfo
0x14002ae74  mov     [rax+28h], rcx
0x14002ae78  lea     rcx, D3ColdSupportFunctionInterfaceDereference
0x14002ae7f  mov     [rax+18h], rcx
0x14002ae83  lea     rcx, D3ColdSupportFunctionInterfaceReference
0x14002ae8a  mov     [rax+10h], rcx
0x14002ae8e  lea     rcx, D3ColdSupportInterfaceFunctionGetD3ColdCapability
0x14002ae95  mov     [rax+30h], rcx
0x14002ae99  lea     rcx, D3ColdSupportInterfaceFunctionGetBusDriverD3ColdSupport
0x14002aea0  mov     [rax+38h], rcx
0x14002aea4  lea     rcx, D3ColdSupportInterfaceFunctionGetLastTransitionStatus
0x14002aeab  mov     [rax+40h], rcx
0x14002aeaf  mov     dword ptr [rax], 10048h
0x14002aeb5  mov     [rax+8], rbp
0x14002aeb9  jmp     loc_14002AE2F
```
