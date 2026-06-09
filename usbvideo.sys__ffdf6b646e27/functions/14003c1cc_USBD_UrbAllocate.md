# USBD_UrbAllocate

- ea: `0x14003c1cc`
- end: `0x14003c3b3`
- name: `USBD_UrbAllocate`
- size: `487`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, PURB *Urb)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140038d54`

## callees

- `0x14003c1cc`
- `0x140040a70`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c392`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c392`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c2ed`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c2ed`
- `ntoskrnl!DbgPrintEx` at `0x14003c1f6`
- `ntoskrnl!DbgPrintEx` at `0x14003c22f`
- `ntoskrnl!DbgPrintEx` at `0x14003c281`
- `ntoskrnl!DbgPrintEx` at `0x14003c2ae`
- `ntoskrnl!DbgPrintEx` at `0x14003c315`
- `ntoskrnl!DbgPrintEx` at `0x14003c36c`
- `ntoskrnl!DbgPrintEx` at `0x14003c1f6`
- `ntoskrnl!DbgPrintEx` at `0x14003c22f`
- `ntoskrnl!DbgPrintEx` at `0x14003c281`
- `ntoskrnl!DbgPrintEx` at `0x14003c2ae`
- `ntoskrnl!DbgPrintEx` at `0x14003c315`
- `ntoskrnl!DbgPrintEx` at `0x14003c36c`

## string_xrefs

- `0x14003c35f`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`
- `0x14003c257`: `UsbdHandleInfo->PendingDelete is set, UsbdHandleInfo 0x%p\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_UrbAllocate(USBD_HANDLE USBDHandle, PURB *Urb)
{
  NTSTATUS v4; // edi
  __int64 (__fastcall *v5)(_QWORD); // rax
  struct _URB *PoolWithTag; // rax
  void (__fastcall *v7)(_QWORD); // rax

  if ( USBDHandle )
  {
    if ( !Urb )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Urb cant be NULL\n");
      return -1073741811;
    }
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
        v5 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 15);
        if ( v5 )
        {
          v4 = v5(*((_QWORD *)USBDHandle + 6));
        }
        else
        {
          PoolWithTag = (struct _URB *)ExAllocatePoolWithTag(PoolType, 0x98u, *((_DWORD *)USBDHandle + 16));
          *Urb = PoolWithTag;
          if ( PoolWithTag )
          {
            memset(PoolWithTag, 0, sizeof(struct _URB));
            v4 = 0;
          }
          else
          {
            if ( g_EnableDbgPrints )
              DbgPrintEx(0x4Du, 0, "Insufficient Memory to allocate URB\n");
            v4 = -1073741670;
          }
        }
        if ( v4 < 0 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)USBDHandle + 55, 0xFFFFFFFF) <= 1 )
          {
            if ( *((_BYTE *)USBDHandle + 225) )
            {
              v7 = (void (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 14);
              if ( v7 )
                v7(*((_QWORD *)USBDHandle + 6));
              ExFreePoolWithTag(USBDHandle, *((_DWORD *)USBDHandle + 16));
            }
            else if ( g_EnableDbgPrints )
            {
              DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", USBDHandle);
            }
          }
          goto LABEL_33;
        }
        return v4;
      }
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->ReferenceCount must be 1 or higher 0x%p\n", USBDHandle);
    }
    v4 = -1073741436;
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "USBDInternal_ReferenceHandle failed %x\n", -1073741436);
    goto LABEL_33;
  }
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
  v4 = -1073741811;
  if ( Urb )
LABEL_33:
    *Urb = 0;
  return v4;
}

```

## disassembly

```asm
0x14003c1cc  push    rbx
0x14003c1ce  push    rdi
0x14003c1cf  push    r14
0x14003c1d1  push    r15
0x14003c1d3  sub     rsp, 28h
0x14003c1d7  mov     r14, rdx
0x14003c1da  mov     rbx, rcx
0x14003c1dd  test    rcx, rcx
0x14003c1e0  jnz     short loc_14003C215
0x14003c1e2  cmp     cs:g_EnableDbgPrints, cl
0x14003c1e8  jz      short loc_14003C202
0x14003c1ea  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14003c1f1  xor     edx, edx; Level
0x14003c1f3  lea     ecx, [rbx+4Dh]; ComponentId
0x14003c1f6  call    cs:__imp_DbgPrintEx
0x14003c1fd  nop     dword ptr [rax+rax+00h]
0x14003c202  mov     edi, 0C000000Dh
0x14003c207  test    r14, r14
0x14003c20a  jz      loc_14003C3A5
0x14003c210  jmp     loc_14003C39E
0x14003c215  test    r14, r14
0x14003c218  jnz     short loc_14003C245
0x14003c21a  cmp     cs:g_EnableDbgPrints, r14b
0x14003c221  jz      short loc_14003C23B
0x14003c223  xor     edx, edx; Level
0x14003c225  lea     r8, aUrbCantBeNull; "Urb cant be NULL\n"
0x14003c22c  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c22f  call    cs:__imp_DbgPrintEx
0x14003c236  nop     dword ptr [rax+rax+00h]
0x14003c23b  mov     edi, 0C000000Dh
0x14003c240  jmp     loc_14003C3A5
0x14003c245  cmp     byte ptr [rcx+0E1h], 0
0x14003c24c  jz      short loc_14003C260
0x14003c24e  cmp     cs:g_EnableDbgPrints, 0
0x14003c255  jz      short loc_14003C28D
0x14003c257  lea     r8, aUsbdhandleinfo_0; "UsbdHandleInfo->PendingDelete is set, U"...
0x14003c25e  jmp     short loc_14003C279
0x14003c260  cmp     dword ptr [rcx+0DCh], 1
0x14003c267  jge     short loc_14003C2BF
0x14003c269  cmp     cs:g_EnableDbgPrints, 0
0x14003c270  jz      short loc_14003C28D
0x14003c272  lea     r8, aUsbdhandleinfo; "UsbdHandleInfo->ReferenceCount must be "...
0x14003c279  xor     edx, edx; Level
0x14003c27b  mov     r9, rbx
0x14003c27e  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c281  call    cs:__imp_DbgPrintEx
0x14003c288  nop     dword ptr [rax+rax+00h]
0x14003c28d  cmp     cs:g_EnableDbgPrints, 0
0x14003c294  mov     edi, 0C0000184h
0x14003c299  jz      loc_14003C39E
0x14003c29f  xor     edx, edx; Level
0x14003c2a1  lea     r8, aUsbdinternalRe; "USBDInternal_ReferenceHandle failed %x"...
0x14003c2a8  mov     r9d, edi
0x14003c2ab  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c2ae  call    cs:__imp_DbgPrintEx
0x14003c2b5  nop     dword ptr [rax+rax+00h]
0x14003c2ba  jmp     loc_14003C39E
0x14003c2bf  lock inc dword ptr [rcx+0DCh]
0x14003c2c6  mov     rax, [rcx+78h]
0x14003c2ca  test    rax, rax
0x14003c2cd  jz      short loc_14003C2DC
0x14003c2cf  mov     rcx, [rcx+30h]
0x14003c2d3  call    _guard_dispatch_icall
0x14003c2d8  mov     edi, eax
0x14003c2da  jmp     short loc_14003C337
0x14003c2dc  mov     r8d, [rcx+40h]; Tag
0x14003c2e0  mov     edi, 98h
0x14003c2e5  mov     ecx, cs:PoolType; PoolType
0x14003c2eb  mov     edx, edi; NumberOfBytes
0x14003c2ed  call    cs:__imp_ExAllocatePoolWithTag
0x14003c2f4  nop     dword ptr [rax+rax+00h]
0x14003c2f9  mov     [r14], rax
0x14003c2fc  test    rax, rax
0x14003c2ff  jnz     short loc_14003C328
0x14003c301  cmp     cs:g_EnableDbgPrints, al
0x14003c307  jz      short loc_14003C321
0x14003c309  lea     r8, aInsufficientMe; "Insufficient Memory to allocate URB\n"
0x14003c310  xor     edx, edx; Level
0x14003c312  lea     ecx, [rdi-4Bh]; ComponentId
0x14003c315  call    cs:__imp_DbgPrintEx
0x14003c31c  nop     dword ptr [rax+rax+00h]
0x14003c321  mov     edi, 0C000009Ah
0x14003c326  jmp     short loc_14003C337
0x14003c328  mov     r8, rdi; Size
0x14003c32b  xor     edx, edx; Val
0x14003c32d  mov     rcx, rax; void *
0x14003c330  call    memset
0x14003c335  xor     edi, edi
0x14003c337  test    edi, edi
0x14003c339  jns     short loc_14003C3A5
0x14003c33b  or      eax, 0FFFFFFFFh
0x14003c33e  lock xadd [rbx+0DCh], eax
0x14003c346  sub     eax, 1
0x14003c349  jg      short loc_14003C39E
0x14003c34b  cmp     byte ptr [rbx+0E1h], 0
0x14003c352  jnz     short loc_14003C37A
0x14003c354  cmp     cs:g_EnableDbgPrints, 0
0x14003c35b  jz      short loc_14003C39E
0x14003c35d  xor     edx, edx; Level
0x14003c35f  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14003c366  mov     r9, rbx
0x14003c369  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c36c  call    cs:__imp_DbgPrintEx
0x14003c373  nop     dword ptr [rax+rax+00h]
0x14003c378  jmp     short loc_14003C39E
0x14003c37a  mov     rax, [rbx+70h]
0x14003c37e  test    rax, rax
0x14003c381  jz      short loc_14003C38C
0x14003c383  mov     rcx, [rbx+30h]
0x14003c387  call    _guard_dispatch_icall
0x14003c38c  mov     edx, [rbx+40h]; Tag
0x14003c38f  mov     rcx, rbx; P
0x14003c392  call    cs:__imp_ExFreePoolWithTag
0x14003c399  nop     dword ptr [rax+rax+00h]
0x14003c39e  mov     qword ptr [r14], 0
0x14003c3a5  mov     eax, edi
0x14003c3a7  add     rsp, 28h
0x14003c3ab  pop     r15
0x14003c3ad  pop     r14
0x14003c3af  pop     rdi
0x14003c3b0  pop     rbx
0x14003c3b1  retn
```
