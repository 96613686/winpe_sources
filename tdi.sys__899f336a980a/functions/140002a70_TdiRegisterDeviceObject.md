# TdiRegisterDeviceObject

- ea: `0x140002a70`
- end: `0x140002b6f`
- name: `TdiRegisterDeviceObject`
- size: `255`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DeviceName, HANDLE *RegistrationHandle)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002a70`
- `0x140002f50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140002a95`
- `ntoskrnl!ExAllocatePool2` at `0x140002ad3`
- `ntoskrnl!ExAllocatePool2` at `0x140002a95`
- `ntoskrnl!ExAllocatePool2` at `0x140002ad3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002b01`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002b01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002b31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002b31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002b49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002b5a`

## pseudocode

```c
NTSTATUS __stdcall TdiRegisterDeviceObject(PUNICODE_STRING DeviceName, HANDLE *RegistrationHandle)
{
  __int64 Pool2; // rbx
  void *v6; // rbp
  NTSTATUS v7; // edi

  Pool2 = ExAllocatePool2(64, 136, 1665746004);
  if ( !Pool2 )
    return -1073741670;
  v6 = (void *)ExAllocatePool2(64, DeviceName->MaximumLength, 1682523220);
  if ( v6 )
  {
    *(_BYTE *)(Pool2 + 16) = 0;
    *(_WORD *)(Pool2 + 122) = DeviceName->MaximumLength;
    *(_QWORD *)(Pool2 + 128) = v6;
    RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 120), DeviceName);
    *RegistrationHandle = (HANDLE)Pool2;
    v7 = TdiHandleSerializedRequest(Pool2, 13);
    if ( v7 )
    {
      ExFreePoolWithTag(v6, 0);
      ExFreePoolWithTag((PVOID)Pool2, 0);
      *RegistrationHandle = 0;
    }
    return v7;
  }
  else
  {
    ExFreePoolWithTag((PVOID)Pool2, 0);
    return -1073741670;
  }
}

```

## disassembly

```asm
0x140002a70  mov     [rsp+arg_8], rbx
0x140002a75  mov     [rsp+arg_10], rsi
0x140002a7a  push    rdi
0x140002a7b  sub     rsp, 20h
0x140002a7f  mov     rsi, rdx
0x140002a82  mov     rdi, rcx
0x140002a85  mov     edx, 88h
0x140002a8a  mov     ecx, 40h ; '@'
0x140002a8f  mov     r8d, 63494454h
0x140002a95  call    cs:__imp_ExAllocatePool2
0x140002a9c  nop     dword ptr [rax+rax+00h]
0x140002aa1  mov     rbx, rax
0x140002aa4  test    rax, rax
0x140002aa7  jnz     short loc_140002ABF
0x140002aa9  mov     eax, 0C000009Ah
0x140002aae  mov     rbx, [rsp+28h+arg_8]
0x140002ab3  mov     rsi, [rsp+28h+arg_10]
0x140002ab8  add     rsp, 20h
0x140002abc  pop     rdi
0x140002abd  retn
0x140002abf  movzx   edx, word ptr [rdi+2]
0x140002ac3  mov     ecx, 40h ; '@'
0x140002ac8  mov     r8d, 64494454h
0x140002ace  mov     [rsp+28h+arg_0], rbp
0x140002ad3  call    cs:__imp_ExAllocatePool2
0x140002ada  nop     dword ptr [rax+rax+00h]
0x140002adf  mov     rbp, rax
0x140002ae2  test    rax, rax
0x140002ae5  jz      short loc_140002B2C
0x140002ae7  mov     byte ptr [rbx+10h], 0
0x140002aeb  lea     rcx, [rbx+78h]; DestinationString
0x140002aef  movzx   eax, word ptr [rdi+2]
0x140002af3  mov     rdx, rdi; SourceString
0x140002af6  mov     [rbx+7Ah], ax
0x140002afa  mov     [rbx+80h], rbp
0x140002b01  call    cs:__imp_RtlCopyUnicodeString
0x140002b08  nop     dword ptr [rax+rax+00h]
0x140002b0d  mov     edx, 0Dh
0x140002b12  mov     [rsi], rbx
0x140002b15  mov     rcx, rbx
0x140002b18  call    TdiHandleSerializedRequest
0x140002b1d  mov     edi, eax
0x140002b1f  test    eax, eax
0x140002b21  jnz     short loc_140002B44
0x140002b23  mov     eax, edi
0x140002b25  mov     rbp, [rsp+28h+arg_0]
0x140002b2a  jmp     short loc_140002AAE
0x140002b2c  xor     edx, edx; Tag
0x140002b2e  mov     rcx, rbx; P
0x140002b31  call    cs:__imp_ExFreePoolWithTag
0x140002b38  nop     dword ptr [rax+rax+00h]
0x140002b3d  mov     eax, 0C000009Ah
0x140002b42  jmp     short loc_140002B25
0x140002b44  xor     edx, edx; Tag
0x140002b46  mov     rcx, rbp; P
0x140002b49  call    cs:__imp_ExFreePoolWithTag
0x140002b50  nop     dword ptr [rax+rax+00h]
0x140002b55  xor     edx, edx; Tag
0x140002b57  mov     rcx, rbx; P
0x140002b5a  call    cs:__imp_ExFreePoolWithTag
0x140002b61  nop     dword ptr [rax+rax+00h]
0x140002b66  mov     qword ptr [rsi], 0
0x140002b6d  jmp     short loc_140002B23
```
