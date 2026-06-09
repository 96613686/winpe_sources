# USBD_UrbAllocate

- ea: `0x14000b1f0`
- end: `0x14000b406`
- name: `USBD_UrbAllocate`
- size: `534`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, PURB *Urb)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000aed0`
- `0x1400114d8`
- `0x1400133e0`
- `0x140023694`
- `0x14002b99c`
- `0x14002c430`
- `0x14002ca84`

## callees

- `0x14000b1f0`
- `0x140014d50`
- `0x140015100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b2e4`
- `ntoskrnl!DbgPrintEx` at `0x14000b2c2`
- `ntoskrnl!DbgPrintEx` at `0x14000b342`
- `ntoskrnl!DbgPrintEx` at `0x14000b370`
- `ntoskrnl!DbgPrintEx` at `0x14000b39d`
- `ntoskrnl!DbgPrintEx` at `0x14000b3c3`
- `ntoskrnl!DbgPrintEx` at `0x14000b3f5`
- `ntoskrnl!DbgPrintEx` at `0x14000b2c2`
- `ntoskrnl!DbgPrintEx` at `0x14000b342`
- `ntoskrnl!DbgPrintEx` at `0x14000b370`
- `ntoskrnl!DbgPrintEx` at `0x14000b39d`
- `ntoskrnl!DbgPrintEx` at `0x14000b3c3`
- `ntoskrnl!DbgPrintEx` at `0x14000b3f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b284`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b284`

## string_xrefs

- `0x14000b3e8`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`
- `0x14000b267`: `UsbdHandleInfo->PendingDelete is set, UsbdHandleInfo 0x%p\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_UrbAllocate(USBD_HANDLE USBDHandle, PURB *Urb)
{
  __int64 (__fastcall *v4)(_QWORD); // rax
  NTSTATUS v5; // edi
  struct _URB *PoolWithTag; // rax
  void (__fastcall *v8)(_QWORD); // rax

  if ( USBDHandle )
  {
    if ( Urb )
    {
      if ( *((_BYTE *)USBDHandle + 225) )
      {
        if ( g_EnableDbgPrints )
          DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete is set, UsbdHandleInfo 0x%p\n", USBDHandle);
      }
      else
      {
        if ( *((int *)USBDHandle + 55) >= 1 )
        {
          _InterlockedIncrement((volatile signed __int32 *)USBDHandle + 55);
          v4 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 15);
          if ( v4 )
          {
            v5 = v4(*((_QWORD *)USBDHandle + 6));
          }
          else
          {
            PoolWithTag = (struct _URB *)ExAllocatePoolWithTag(PoolType, 0x98u, *((_DWORD *)USBDHandle + 16));
            *Urb = PoolWithTag;
            if ( PoolWithTag )
            {
              memset(PoolWithTag, 0, sizeof(struct _URB));
              v5 = 0;
            }
            else
            {
              if ( g_EnableDbgPrints )
                DbgPrintEx(0x4Du, 0, "Insufficient Memory to allocate URB\n");
              v5 = -1073741670;
            }
          }
          if ( v5 >= 0 )
            return v5;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)USBDHandle + 55, 0xFFFFFFFF) <= 1 )
          {
            if ( *((_BYTE *)USBDHandle + 225) )
            {
              v8 = (void (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 14);
              if ( v8 )
                v8(*((_QWORD *)USBDHandle + 6));
              ExFreePoolWithTag(USBDHandle, *((_DWORD *)USBDHandle + 16));
            }
            else if ( g_EnableDbgPrints )
            {
              DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", USBDHandle);
            }
          }
LABEL_18:
          *Urb = 0;
          return v5;
        }
        if ( g_EnableDbgPrints )
          DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->ReferenceCount must be 1 or higher 0x%p\n", USBDHandle);
      }
      v5 = -1073741436;
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "USBDInternal_ReferenceHandle failed %x\n", -1073741436);
      goto LABEL_18;
    }
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Urb cant be NULL\n");
    return -1073741811;
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
    v5 = -1073741811;
    if ( Urb )
      goto LABEL_18;
  }
  return v5;
}

```

## disassembly

```asm
0x14000b1f0  push    rbx
0x14000b1f2  push    rdi
0x14000b1f3  push    r14
0x14000b1f5  push    r15
0x14000b1f7  sub     rsp, 28h
0x14000b1fb  mov     r14, rdx
0x14000b1fe  mov     rbx, rcx
0x14000b201  test    rcx, rcx
0x14000b204  jz      loc_14000B2AD
0x14000b20a  test    rdx, rdx
0x14000b20d  jz      loc_14000B32D
0x14000b213  cmp     byte ptr [rcx+0E1h], 0
0x14000b21a  jnz     short loc_14000B25A
0x14000b21c  cmp     dword ptr [rcx+0DCh], 1
0x14000b223  jl      loc_14000B358
0x14000b229  lock inc dword ptr [rcx+0DCh]
0x14000b230  mov     rax, [rcx+78h]
0x14000b234  test    rax, rax
0x14000b237  jz      short loc_14000B273
0x14000b239  mov     rcx, [rcx+30h]
0x14000b23d  call    _guard_dispatch_icall
0x14000b242  mov     edi, eax
0x14000b244  test    edi, edi
0x14000b246  js      loc_14000B2FC
0x14000b24c  mov     eax, edi
0x14000b24e  add     rsp, 28h
0x14000b252  pop     r15
0x14000b254  pop     r14
0x14000b256  pop     rdi
0x14000b257  pop     rbx
0x14000b258  retn
0x14000b25a  cmp     cs:g_EnableDbgPrints, 0
0x14000b261  jz      loc_14000B37C
0x14000b267  lea     r8, aUsbdhandleinfo_0; "UsbdHandleInfo->PendingDelete is set, U"...
0x14000b26e  jmp     loc_14000B368
0x14000b273  mov     r8d, [rcx+40h]; Tag
0x14000b277  mov     edi, 98h
0x14000b27c  mov     ecx, cs:PoolType; PoolType
0x14000b282  mov     edx, edi; NumberOfBytes
0x14000b284  call    cs:__imp_ExAllocatePoolWithTag
0x14000b28b  nop     dword ptr [rax+rax+00h]
0x14000b290  mov     [r14], rax
0x14000b293  test    rax, rax
0x14000b296  jz      loc_14000B3AE
0x14000b29c  mov     r8d, edi; Size
0x14000b29f  xor     edx, edx; Val
0x14000b2a1  mov     rcx, rax; void *
0x14000b2a4  call    memset
0x14000b2a9  xor     edi, edi
0x14000b2ab  jmp     short loc_14000B244
0x14000b2ad  cmp     cs:g_EnableDbgPrints, 0
0x14000b2b4  jz      short loc_14000B2CE
0x14000b2b6  xor     edx, edx; Level
0x14000b2b8  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14000b2bf  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b2c2  call    cs:__imp_DbgPrintEx
0x14000b2c9  nop     dword ptr [rax+rax+00h]
0x14000b2ce  mov     edi, 0C000000Dh
0x14000b2d3  test    r14, r14
0x14000b2d6  jz      loc_14000B24C
0x14000b2dc  jmp     short loc_14000B2F0
0x14000b2de  mov     edx, [rbx+40h]; Tag
0x14000b2e1  mov     rcx, rbx; P
0x14000b2e4  call    cs:__imp_ExFreePoolWithTag
0x14000b2eb  nop     dword ptr [rax+rax+00h]
0x14000b2f0  mov     qword ptr [r14], 0
0x14000b2f7  jmp     loc_14000B24C
0x14000b2fc  or      eax, 0FFFFFFFFh
0x14000b2ff  lock xadd [rbx+0DCh], eax
0x14000b307  sub     eax, 1
0x14000b30a  jg      short loc_14000B2F0
0x14000b30c  cmp     byte ptr [rbx+0E1h], 0
0x14000b313  jz      loc_14000B3D9
0x14000b319  mov     rax, [rbx+70h]
0x14000b31d  test    rax, rax
0x14000b320  jz      short loc_14000B2DE
0x14000b322  mov     rcx, [rbx+30h]
0x14000b326  call    _guard_dispatch_icall
0x14000b32b  jmp     short loc_14000B2DE
0x14000b32d  cmp     cs:g_EnableDbgPrints, 0
0x14000b334  jz      short loc_14000B34E
0x14000b336  xor     edx, edx; Level
0x14000b338  lea     r8, aUrbCantBeNull; "Urb cant be NULL\n"
0x14000b33f  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b342  call    cs:__imp_DbgPrintEx
0x14000b349  nop     dword ptr [rax+rax+00h]
0x14000b34e  mov     edi, 0C000000Dh
0x14000b353  jmp     loc_14000B24C
0x14000b358  cmp     cs:g_EnableDbgPrints, 0
0x14000b35f  jz      short loc_14000B37C
0x14000b361  lea     r8, aUsbdhandleinfo; "UsbdHandleInfo->ReferenceCount must be "...
0x14000b368  xor     edx, edx; Level
0x14000b36a  mov     r9, rbx
0x14000b36d  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b370  call    cs:__imp_DbgPrintEx
0x14000b377  nop     dword ptr [rax+rax+00h]
0x14000b37c  cmp     cs:g_EnableDbgPrints, 0
0x14000b383  mov     edi, 0C0000184h
0x14000b388  jz      loc_14000B2F0
0x14000b38e  xor     edx, edx; Level
0x14000b390  lea     r8, aUsbdinternalRe; "USBDInternal_ReferenceHandle failed %x"...
0x14000b397  mov     r9d, edi
0x14000b39a  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b39d  call    cs:__imp_DbgPrintEx
0x14000b3a4  nop     dword ptr [rax+rax+00h]
0x14000b3a9  jmp     loc_14000B2F0
0x14000b3ae  cmp     cs:g_EnableDbgPrints, 0
0x14000b3b5  jz      short loc_14000B3CF
0x14000b3b7  xor     edx, edx; Level
0x14000b3b9  lea     r8, aInsufficientMe; "Insufficient Memory to allocate URB\n"
0x14000b3c0  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b3c3  call    cs:__imp_DbgPrintEx
0x14000b3ca  nop     dword ptr [rax+rax+00h]
0x14000b3cf  mov     edi, 0C000009Ah
0x14000b3d4  jmp     loc_14000B244
0x14000b3d9  cmp     cs:g_EnableDbgPrints, 0
0x14000b3e0  jz      loc_14000B2F0
0x14000b3e6  xor     edx, edx; Level
0x14000b3e8  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14000b3ef  mov     r9, rbx
0x14000b3f2  lea     ecx, [rdx+4Dh]; ComponentId
0x14000b3f5  call    cs:__imp_DbgPrintEx
0x14000b3fc  nop     dword ptr [rax+rax+00h]
0x14000b401  jmp     loc_14000B2F0
```
