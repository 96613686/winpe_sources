# VhdmpiSetDeviceSecurity

- ea: `0x14004953c`
- end: `0x1400495c7`
- name: `VhdmpiSetDeviceSecurity`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400b7188`

## callees

- `0x14004953c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140049576`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140049576`
- `ntoskrnl!ZwSetSecurityObject` at `0x140049595`
- `ntoskrnl!ZwSetSecurityObject` at `0x140049595`
- `ntoskrnl!ZwClose` at `0x1400495ad`
- `ntoskrnl!ZwClose` at `0x1400495ad`

## pseudocode

```c
__int64 __fastcall VhdmpiSetDeviceSecurity(void *a1, void *a2)
{
  NTSTATUS v3; // ebx
  HANDLE Handle; // [rsp+60h] [rbp+18h] BYREF

  Handle = 0;
  v3 = ObOpenObjectByPointer(a1, 0x200u, 0, 0x40000u, 0, 0, &Handle);
  if ( v3 >= 0 )
    v3 = ZwSetSecurityObject(Handle, 4u, a2);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14004953c  mov     r11, rsp
0x14004953f  mov     [r11+8], rbx
0x140049543  push    rdi
0x140049544  sub     rsp, 40h
0x140049548  lea     rax, [r11+18h]
0x14004954c  mov     qword ptr [r11+18h], 0
0x140049554  mov     [r11-18h], rax
0x140049558  mov     rdi, rdx
0x14004955b  mov     [rsp+48h+AccessMode], 0; AccessMode
0x140049560  mov     r9d, 40000h; DesiredAccess
0x140049566  xor     r8d, r8d; PassedAccessState
0x140049569  mov     qword ptr [r11-28h], 0
0x140049571  mov     edx, 200h; HandleAttributes
0x140049576  call    cs:__imp_ObOpenObjectByPointer
0x14004957d  nop     dword ptr [rax+rax+00h]
0x140049582  mov     ebx, eax
0x140049584  test    eax, eax
0x140049586  js      short loc_1400495A3
0x140049588  mov     rcx, [rsp+48h+Handle]; Handle
0x14004958d  mov     r8, rdi; SecurityDescriptor
0x140049590  mov     edx, 4; SecurityInformation
0x140049595  call    cs:__imp_ZwSetSecurityObject
0x14004959c  nop     dword ptr [rax+rax+00h]
0x1400495a1  mov     ebx, eax
0x1400495a3  mov     rcx, [rsp+48h+Handle]; Handle
0x1400495a8  test    rcx, rcx
0x1400495ab  jz      short loc_1400495B9
0x1400495ad  call    cs:__imp_ZwClose
0x1400495b4  nop     dword ptr [rax+rax+00h]
0x1400495b9  mov     eax, ebx
0x1400495bb  mov     rbx, [rsp+48h+arg_0]
0x1400495c0  add     rsp, 40h
0x1400495c4  pop     rdi
0x1400495c5  retn
```
