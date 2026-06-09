# USBD_SecureIsochUrbAllocate

- ea: `0x14003c000`
- end: `0x14003c1c4`
- name: `USBD_SecureIsochUrbAllocate`
- size: `452`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140038d54`

## callees

- `0x14003c000`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c19d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c19d`
- `ntoskrnl!DbgPrintEx` at `0x14003c02f`
- `ntoskrnl!DbgPrintEx` at `0x14003c068`
- `ntoskrnl!DbgPrintEx` at `0x14003c0ba`
- `ntoskrnl!DbgPrintEx` at `0x14003c0e7`
- `ntoskrnl!DbgPrintEx` at `0x14003c135`
- `ntoskrnl!DbgPrintEx` at `0x14003c177`
- `ntoskrnl!DbgPrintEx` at `0x14003c02f`
- `ntoskrnl!DbgPrintEx` at `0x14003c068`
- `ntoskrnl!DbgPrintEx` at `0x14003c0ba`
- `ntoskrnl!DbgPrintEx` at `0x14003c0e7`
- `ntoskrnl!DbgPrintEx` at `0x14003c135`
- `ntoskrnl!DbgPrintEx` at `0x14003c177`

## string_xrefs

- `0x14003c16a`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`
- `0x14003c090`: `UsbdHandleInfo->PendingDelete is set, UsbdHandleInfo 0x%p\n`

## pseudocode

```c
__int64 __fastcall USBD_SecureIsochUrbAllocate(PVOID P, __int64 a2, _QWORD *a3)
{
  int v5; // esi
  __int64 (__fastcall *v6)(_QWORD); // rax
  void (__fastcall *v7)(_QWORD); // rax

  if ( P )
  {
    if ( a3 )
    {
      if ( *((_BYTE *)P + 225) )
      {
        if ( g_EnableDbgPrints )
          DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete is set, UsbdHandleInfo 0x%p\n", P);
      }
      else
      {
        if ( *((int *)P + 55) >= 1 )
        {
          _InterlockedIncrement((volatile signed __int32 *)P + 55);
          v6 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)P + 20);
          if ( v6 )
          {
            v5 = v6(*((_QWORD *)P + 6));
            if ( v5 >= 0 )
              return (unsigned int)v5;
          }
          else
          {
            if ( g_EnableDbgPrints )
              DbgPrintEx(0x4Du, 0, "XRBs not supported by core stack for Secure Transfers\n");
            v5 = -1073741637;
          }
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 55, 0xFFFFFFFF) <= 1 )
          {
            if ( *((_BYTE *)P + 225) )
            {
              v7 = (void (__fastcall *)(_QWORD))*((_QWORD *)P + 14);
              if ( v7 )
                v7(*((_QWORD *)P + 6));
              ExFreePoolWithTag(P, *((_DWORD *)P + 16));
            }
            else if ( g_EnableDbgPrints )
            {
              DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", P);
            }
          }
          goto LABEL_31;
        }
        if ( g_EnableDbgPrints )
          DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->ReferenceCount must be 1 or higher 0x%p\n", P);
      }
      v5 = -1073741436;
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "USBDInternal_ReferenceHandle failed %x\n", -1073741436);
      goto LABEL_31;
    }
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Urb cant be NULL\n");
    return (unsigned int)-1073741811;
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
    v5 = -1073741811;
    if ( a3 )
LABEL_31:
      *a3 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003c000  mov     [rsp+arg_0], rbx
0x14003c005  mov     [rsp+arg_8], rsi
0x14003c00a  push    r14
0x14003c00c  sub     rsp, 20h
0x14003c010  mov     r14, r8
0x14003c013  mov     rbx, rcx
0x14003c016  test    rcx, rcx
0x14003c019  jnz     short loc_14003C04E
0x14003c01b  cmp     cs:g_EnableDbgPrints, cl
0x14003c021  jz      short loc_14003C03B
0x14003c023  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14003c02a  xor     edx, edx; Level
0x14003c02c  lea     ecx, [rbx+4Dh]; ComponentId
0x14003c02f  call    cs:__imp_DbgPrintEx
0x14003c036  nop     dword ptr [rax+rax+00h]
0x14003c03b  mov     esi, 0C000000Dh
0x14003c040  test    r14, r14
0x14003c043  jz      loc_14003C1B0
0x14003c049  jmp     loc_14003C1A9
0x14003c04e  test    r14, r14
0x14003c051  jnz     short loc_14003C07E
0x14003c053  cmp     cs:g_EnableDbgPrints, r14b
0x14003c05a  jz      short loc_14003C074
0x14003c05c  xor     edx, edx; Level
0x14003c05e  lea     r8, aUrbCantBeNull; "Urb cant be NULL\n"
0x14003c065  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c068  call    cs:__imp_DbgPrintEx
0x14003c06f  nop     dword ptr [rax+rax+00h]
0x14003c074  mov     esi, 0C000000Dh
0x14003c079  jmp     loc_14003C1B0
0x14003c07e  cmp     byte ptr [rcx+0E1h], 0
0x14003c085  jz      short loc_14003C099
0x14003c087  cmp     cs:g_EnableDbgPrints, 0
0x14003c08e  jz      short loc_14003C0C6
0x14003c090  lea     r8, aUsbdhandleinfo_0; "UsbdHandleInfo->PendingDelete is set, U"...
0x14003c097  jmp     short loc_14003C0B2
0x14003c099  cmp     dword ptr [rcx+0DCh], 1
0x14003c0a0  jge     short loc_14003C0F8
0x14003c0a2  cmp     cs:g_EnableDbgPrints, 0
0x14003c0a9  jz      short loc_14003C0C6
0x14003c0ab  lea     r8, aUsbdhandleinfo; "UsbdHandleInfo->ReferenceCount must be "...
0x14003c0b2  xor     edx, edx; Level
0x14003c0b4  mov     r9, rbx
0x14003c0b7  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c0ba  call    cs:__imp_DbgPrintEx
0x14003c0c1  nop     dword ptr [rax+rax+00h]
0x14003c0c6  cmp     cs:g_EnableDbgPrints, 0
0x14003c0cd  mov     esi, 0C0000184h
0x14003c0d2  jz      loc_14003C1A9
0x14003c0d8  xor     edx, edx; Level
0x14003c0da  lea     r8, aUsbdinternalRe; "USBDInternal_ReferenceHandle failed %x"...
0x14003c0e1  mov     r9d, esi
0x14003c0e4  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c0e7  call    cs:__imp_DbgPrintEx
0x14003c0ee  nop     dword ptr [rax+rax+00h]
0x14003c0f3  jmp     loc_14003C1A9
0x14003c0f8  lock inc dword ptr [rcx+0DCh]
0x14003c0ff  mov     rax, [rcx+0A0h]
0x14003c106  test    rax, rax
0x14003c109  jz      short loc_14003C120
0x14003c10b  mov     rcx, [rcx+30h]
0x14003c10f  call    _guard_dispatch_icall
0x14003c114  mov     esi, eax
0x14003c116  test    eax, eax
0x14003c118  jns     loc_14003C1B0
0x14003c11e  jmp     short loc_14003C146
0x14003c120  cmp     cs:g_EnableDbgPrints, 0
0x14003c127  jz      short loc_14003C141
0x14003c129  xor     edx, edx; Level
0x14003c12b  lea     r8, aXrbsNotSupport; "XRBs not supported by core stack for Se"...
0x14003c132  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c135  call    cs:__imp_DbgPrintEx
0x14003c13c  nop     dword ptr [rax+rax+00h]
0x14003c141  mov     esi, 0C00000BBh
0x14003c146  or      eax, 0FFFFFFFFh
0x14003c149  lock xadd [rbx+0DCh], eax
0x14003c151  sub     eax, 1
0x14003c154  jg      short loc_14003C1A9
0x14003c156  cmp     byte ptr [rbx+0E1h], 0
0x14003c15d  jnz     short loc_14003C185
0x14003c15f  cmp     cs:g_EnableDbgPrints, 0
0x14003c166  jz      short loc_14003C1A9
0x14003c168  xor     edx, edx; Level
0x14003c16a  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14003c171  mov     r9, rbx
0x14003c174  lea     ecx, [rdx+4Dh]; ComponentId
0x14003c177  call    cs:__imp_DbgPrintEx
0x14003c17e  nop     dword ptr [rax+rax+00h]
0x14003c183  jmp     short loc_14003C1A9
0x14003c185  mov     rax, [rbx+70h]
0x14003c189  test    rax, rax
0x14003c18c  jz      short loc_14003C197
0x14003c18e  mov     rcx, [rbx+30h]
0x14003c192  call    _guard_dispatch_icall
0x14003c197  mov     edx, [rbx+40h]; Tag
0x14003c19a  mov     rcx, rbx; P
0x14003c19d  call    cs:__imp_ExFreePoolWithTag
0x14003c1a4  nop     dword ptr [rax+rax+00h]
0x14003c1a9  mov     qword ptr [r14], 0
0x14003c1b0  mov     rbx, [rsp+28h+arg_0]
0x14003c1b5  mov     eax, esi
0x14003c1b7  mov     rsi, [rsp+28h+arg_8]
0x14003c1bc  add     rsp, 20h
0x14003c1c0  pop     r14
0x14003c1c2  retn
```
