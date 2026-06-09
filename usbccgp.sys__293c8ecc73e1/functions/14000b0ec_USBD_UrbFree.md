# USBD_UrbFree

- ea: `0x14000b0ec`
- end: `0x14000b1ea`
- name: `USBD_UrbFree`
- size: `254`
- prototype: `void __stdcall(USBD_HANDLE USBDHandle, PURB Urb)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aed0`
- `0x1400114d8`
- `0x1400133e0`
- `0x14002a1cc`
- `0x14002b99c`
- `0x14002c430`
- `0x14002ca84`

## callees

- `0x14000b0ec`
- `0x140014d50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b155`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b17b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b155`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b17b`
- `ntoskrnl!DbgPrintEx` at `0x14000b1a0`
- `ntoskrnl!DbgPrintEx` at `0x14000b1d9`
- `ntoskrnl!DbgPrintEx` at `0x14000b1a0`
- `ntoskrnl!DbgPrintEx` at `0x14000b1d9`

## string_xrefs

- `0x14000b1cc`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

## pseudocode

```c
void __stdcall USBD_UrbFree(USBD_HANDLE USBDHandle, PURB Urb)
{
  void (__fastcall *v4)(PURB); // rdx
  void (__fastcall *v5)(_QWORD); // rax

  if ( Urb )
  {
    if ( USBDHandle )
    {
      v4 = (void (__fastcall *)(PURB))*((_QWORD *)USBDHandle + 19);
      if ( v4 )
        v4(Urb);
      else
        ExFreePoolWithTag(Urb, *((_DWORD *)USBDHandle + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)USBDHandle + 55, 0xFFFFFFFF) <= 1 )
      {
        if ( *((_BYTE *)USBDHandle + 225) )
        {
          v5 = (void (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 14);
          if ( v5 )
            v5(*((_QWORD *)USBDHandle + 6));
          ExFreePoolWithTag(USBDHandle, *((_DWORD *)USBDHandle + 16));
        }
        else if ( g_EnableDbgPrints )
        {
          DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", USBDHandle);
        }
      }
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
    }
  }
  else if ( g_EnableDbgPrints )
  {
    DbgPrintEx(0x4Du, 0, "Urb cant be NULL\n");
  }
}

```

## disassembly

```asm
0x14000b0ec  mov     [rsp+arg_0], rbx
0x14000b0f1  push    rdi
0x14000b0f2  sub     rsp, 20h
0x14000b0f6  mov     rax, rdx
0x14000b0f9  mov     rbx, rcx
0x14000b0fc  test    rdx, rdx
0x14000b0ff  jz      short loc_14000B163
0x14000b101  test    rcx, rcx
0x14000b104  jz      loc_14000B1AE
0x14000b10a  mov     rdx, [rcx+98h]
0x14000b111  test    rdx, rdx
0x14000b114  jz      short loc_14000B175
0x14000b116  mov     rcx, rax
0x14000b119  mov     rax, rdx
0x14000b11c  call    _guard_dispatch_icall
0x14000b121  or      eax, 0FFFFFFFFh
0x14000b124  lock xadd [rbx+0DCh], eax
0x14000b12c  sub     eax, 1
0x14000b12f  jle     short loc_14000B13D
0x14000b131  mov     rbx, [rsp+28h+arg_0]
0x14000b136  add     rsp, 20h
0x14000b13a  pop     rdi
0x14000b13b  retn
0x14000b13d  cmp     byte ptr [rbx+0E1h], 0
0x14000b144  jz      short loc_14000B1BD
0x14000b146  mov     rax, [rbx+70h]
0x14000b14a  test    rax, rax
0x14000b14d  jnz     short loc_14000B189
0x14000b14f  mov     edx, [rbx+40h]; Tag
0x14000b152  mov     rcx, rbx; P
0x14000b155  call    cs:__imp_ExFreePoolWithTag
0x14000b15c  nop     dword ptr [rax+rax+00h]
0x14000b161  jmp     short loc_14000B131
0x14000b163  cmp     cs:g_EnableDbgPrints, 0
0x14000b16a  jz      short loc_14000B131
0x14000b16c  lea     r8, aUrbCantBeNull; "Urb cant be NULL\n"
0x14000b173  jmp     short loc_14000B19B
0x14000b175  mov     edx, [rcx+40h]; Tag
0x14000b178  mov     rcx, rax; P
0x14000b17b  call    cs:__imp_ExFreePoolWithTag
0x14000b182  nop     dword ptr [rax+rax+00h]
0x14000b187  jmp     short loc_14000B121
0x14000b189  mov     rcx, [rbx+30h]
0x14000b18d  call    _guard_dispatch_icall
0x14000b192  jmp     short loc_14000B14F
0x14000b194  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14000b19b  xor     edx, edx; Level
0x14000b19d  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b1a0  call    cs:__imp_DbgPrintEx
0x14000b1a7  nop     dword ptr [rax+rax+00h]
0x14000b1ac  jmp     short loc_14000B131
0x14000b1ae  cmp     cs:g_EnableDbgPrints, 0
0x14000b1b5  jz      loc_14000B131
0x14000b1bb  jmp     short loc_14000B194
0x14000b1bd  cmp     cs:g_EnableDbgPrints, 0
0x14000b1c4  jz      loc_14000B131
0x14000b1ca  xor     edx, edx; Level
0x14000b1cc  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14000b1d3  mov     r9, rbx
0x14000b1d6  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b1d9  call    cs:__imp_DbgPrintEx
0x14000b1e0  nop     dword ptr [rax+rax+00h]
0x14000b1e5  jmp     loc_14000B131
```
