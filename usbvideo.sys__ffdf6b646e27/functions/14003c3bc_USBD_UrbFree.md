# USBD_UrbFree

- ea: `0x14003c3bc`
- end: `0x14003c4ae`
- name: `USBD_UrbFree`
- size: `242`
- prototype: `void __stdcall(USBD_HANDLE USBDHandle, PURB Urb)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014300`

## callees

- `0x14003c3bc`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c433`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c496`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c433`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c496`
- `ntoskrnl!DbgPrintEx` at `0x14003c3e9`
- `ntoskrnl!DbgPrintEx` at `0x14003c470`
- `ntoskrnl!DbgPrintEx` at `0x14003c3e9`
- `ntoskrnl!DbgPrintEx` at `0x14003c470`

## string_xrefs

- `0x14003c463`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

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
0x14003c3bc  mov     [rsp+arg_0], rbx
0x14003c3c1  push    rdi
0x14003c3c2  sub     rsp, 20h
0x14003c3c6  mov     rax, rdx
0x14003c3c9  mov     rbx, rcx
0x14003c3cc  test    rdx, rdx
0x14003c3cf  jnz     short loc_14003C3FA
0x14003c3d1  cmp     cs:g_EnableDbgPrints, dl
0x14003c3d7  jz      loc_14003C4A2
0x14003c3dd  lea     r8, aUrbCantBeNull; "Urb cant be NULL\n"
0x14003c3e4  xor     edx, edx; Level
0x14003c3e6  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c3e9  call    cs:__imp_DbgPrintEx
0x14003c3f0  nop     dword ptr [rax+rax+00h]
0x14003c3f5  jmp     loc_14003C4A2
0x14003c3fa  test    rbx, rbx
0x14003c3fd  jnz     short loc_14003C414
0x14003c3ff  cmp     cs:g_EnableDbgPrints, bl
0x14003c405  jz      loc_14003C4A2
0x14003c40b  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14003c412  jmp     short loc_14003C3E4
0x14003c414  mov     rdx, [rcx+98h]
0x14003c41b  test    rdx, rdx
0x14003c41e  jz      short loc_14003C42D
0x14003c420  mov     rcx, rax
0x14003c423  mov     rax, rdx
0x14003c426  call    _guard_dispatch_icall
0x14003c42b  jmp     short loc_14003C43F
0x14003c42d  mov     edx, [rcx+40h]; Tag
0x14003c430  mov     rcx, rax; P
0x14003c433  call    cs:__imp_ExFreePoolWithTag
0x14003c43a  nop     dword ptr [rax+rax+00h]
0x14003c43f  or      eax, 0FFFFFFFFh
0x14003c442  lock xadd [rbx+0DCh], eax
0x14003c44a  sub     eax, 1
0x14003c44d  jg      short loc_14003C4A2
0x14003c44f  cmp     byte ptr [rbx+0E1h], 0
0x14003c456  jnz     short loc_14003C47E
0x14003c458  cmp     cs:g_EnableDbgPrints, 0
0x14003c45f  jz      short loc_14003C4A2
0x14003c461  xor     edx, edx; Level
0x14003c463  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14003c46a  mov     r9, rbx
0x14003c46d  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c470  call    cs:__imp_DbgPrintEx
0x14003c477  nop     dword ptr [rax+rax+00h]
0x14003c47c  jmp     short loc_14003C4A2
0x14003c47e  mov     rax, [rbx+70h]
0x14003c482  test    rax, rax
0x14003c485  jz      short loc_14003C490
0x14003c487  mov     rcx, [rbx+30h]
0x14003c48b  call    _guard_dispatch_icall
0x14003c490  mov     edx, [rbx+40h]; Tag
0x14003c493  mov     rcx, rbx; P
0x14003c496  call    cs:__imp_ExFreePoolWithTag
0x14003c49d  nop     dword ptr [rax+rax+00h]
0x14003c4a2  mov     rbx, [rsp+28h+arg_0]
0x14003c4a7  add     rsp, 20h
0x14003c4ab  pop     rdi
0x14003c4ac  retn
```
