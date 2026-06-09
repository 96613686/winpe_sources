# TdiRegisterNetAddress

- ea: `0x140002880`
- end: `0x140002a68`
- name: `TdiRegisterNetAddress`
- size: `488`
- prototype: `NTSTATUS __stdcall(PTA_ADDRESS Address, PUNICODE_STRING DeviceName, PTDI_PNP_CONTEXT Context, HANDLE *RegistrationHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002880`
- `0x140002f50`
- `0x140005600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400028b1`
- `ntoskrnl!ExAllocatePool2` at `0x140002955`
- `ntoskrnl!ExAllocatePool2` at `0x1400029a6`
- `ntoskrnl!ExAllocatePool2` at `0x1400028b1`
- `ntoskrnl!ExAllocatePool2` at `0x140002955`
- `ntoskrnl!ExAllocatePool2` at `0x1400029a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a57`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400029fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a57`

## pseudocode

```c
NTSTATUS __stdcall TdiRegisterNetAddress(
        PTA_ADDRESS Address,
        PUNICODE_STRING DeviceName,
        PTDI_PNP_CONTEXT Context,
        HANDLE *RegistrationHandle)
{
  __int64 Pool2; // rax
  __int64 v9; // rbx
  NTSTATUS v11; // edi
  __int64 v12; // rax
  void *v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx

  Pool2 = ExAllocatePool2(64, Address->AddressLength + 124LL, 1699300436);
  v9 = Pool2;
  if ( !Pool2 )
    return -1073741670;
  *(_BYTE *)(Pool2 + 16) = 1;
  *(_WORD *)(Pool2 + 120) = Address->AddressLength;
  *(_WORD *)(Pool2 + 122) = Address->AddressType;
  memmove((void *)(Pool2 + 124), Address->Address, Address->AddressLength);
  *RegistrationHandle = (HANDLE)v9;
  if ( DeviceName )
  {
    v13 = (void *)ExAllocatePool2(64, DeviceName->MaximumLength, 1967735892);
    *(_QWORD *)(v9 + 72) = v13;
    if ( !v13 )
      goto LABEL_15;
    memmove(v13, DeviceName->Buffer, DeviceName->MaximumLength);
    *(_WORD *)(v9 + 64) = DeviceName->Length;
    *(_WORD *)(v9 + 66) = DeviceName->MaximumLength;
  }
  else
  {
    *(_QWORD *)(v9 + 72) = 0;
  }
  if ( Context )
  {
    v12 = ExAllocatePool2(64, Context->ContextSize + 8LL, 1984513108);
    *(_QWORD *)(v9 + 88) = v12;
    if ( v12 )
    {
      *(_WORD *)(v12 + 2) = Context->ContextType;
      **(_WORD **)(v9 + 88) = Context->ContextSize;
      memmove((void *)(*(_QWORD *)(v9 + 88) + 8LL), Context->ContextData, Context->ContextSize);
      goto LABEL_7;
    }
    v14 = *(void **)(v9 + 72);
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
LABEL_15:
    ExFreePoolWithTag((PVOID)v9, 0);
    return -1073741670;
  }
  *(_QWORD *)(v9 + 88) = 0;
LABEL_7:
  v11 = TdiHandleSerializedRequest(v9, 11);
  if ( v11 )
  {
    *RegistrationHandle = 0;
    v15 = *(void **)(v9 + 72);
    if ( v15 )
    {
      ExFreePoolWithTag(v15, 0);
      *(_QWORD *)(v9 + 72) = 0;
    }
    v16 = *(void **)(v9 + 88);
    if ( v16 )
    {
      ExFreePoolWithTag(v16, 0);
      *(_QWORD *)(v9 + 88) = 0;
    }
    ExFreePoolWithTag((PVOID)v9, 0);
  }
  return v11;
}

```

## disassembly

```asm
0x140002880  mov     [rsp+arg_8], rbx
0x140002885  mov     [rsp+arg_10], rsi
0x14000288a  push    rdi
0x14000288b  push    r14
0x14000288d  push    r15
0x14000288f  sub     rsp, 20h
0x140002893  mov     r14, rdx
0x140002896  mov     rsi, r8
0x140002899  movzx   edx, word ptr [rcx]
0x14000289c  mov     rdi, rcx
0x14000289f  add     rdx, 7Ch ; '|'
0x1400028a3  mov     ecx, 40h ; '@'
0x1400028a8  mov     r8d, 65494454h
0x1400028ae  mov     r15, r9
0x1400028b1  call    cs:__imp_ExAllocatePool2
0x1400028b8  nop     dword ptr [rax+rax+00h]
0x1400028bd  mov     rbx, rax
0x1400028c0  test    rax, rax
0x1400028c3  jnz     short loc_1400028DF
0x1400028c5  mov     eax, 0C000009Ah
0x1400028ca  mov     rbx, [rsp+38h+arg_8]
0x1400028cf  mov     rsi, [rsp+38h+arg_10]
0x1400028d4  add     rsp, 20h
0x1400028d8  pop     r15
0x1400028da  pop     r14
0x1400028dc  pop     rdi
0x1400028dd  retn
0x1400028df  mov     byte ptr [rax+10h], 1
0x1400028e3  lea     rdx, [rdi+4]; Src
0x1400028e7  movzx   eax, word ptr [rdi]
0x1400028ea  lea     rcx, [rbx+7Ch]; void *
0x1400028ee  mov     [rbx+78h], ax
0x1400028f2  movzx   eax, word ptr [rdi+2]
0x1400028f6  mov     [rbx+7Ah], ax
0x1400028fa  movzx   r8d, word ptr [rdi]; Size
0x1400028fe  mov     [rsp+38h+arg_0], rbp
0x140002903  call    memmove
0x140002908  xor     ebp, ebp
0x14000290a  mov     [r15], rbx
0x14000290d  test    r14, r14
0x140002910  jnz     loc_140002996
0x140002916  mov     [rbx+48h], rbp
0x14000291a  test    rsi, rsi
0x14000291d  jnz     short loc_140002943
0x14000291f  mov     [rbx+58h], rbp
0x140002923  mov     edx, 0Bh
0x140002928  mov     rcx, rbx
0x14000292b  call    TdiHandleSerializedRequest
0x140002930  mov     edi, eax
0x140002932  test    eax, eax
0x140002934  jnz     loc_140002A19
0x14000293a  mov     rbp, [rsp+38h+arg_0]
0x14000293f  mov     eax, edi
0x140002941  jmp     short loc_1400028CA
0x140002943  movzx   edx, word ptr [rsi]
0x140002946  mov     ecx, 40h ; '@'
0x14000294b  add     rdx, 8
0x14000294f  mov     r8d, 76494454h
0x140002955  call    cs:__imp_ExAllocatePool2
0x14000295c  nop     dword ptr [rax+rax+00h]
0x140002961  mov     [rbx+58h], rax
0x140002965  mov     rcx, rax
0x140002968  test    rax, rax
0x14000296b  jz      short loc_1400029E2
0x14000296d  movzx   eax, word ptr [rsi+2]
0x140002971  lea     rdx, [rsi+8]; Src
0x140002975  mov     [rcx+2], ax
0x140002979  mov     rcx, [rbx+58h]
0x14000297d  movzx   eax, word ptr [rsi]
0x140002980  mov     [rcx], ax
0x140002983  mov     rcx, [rbx+58h]
0x140002987  movzx   r8d, word ptr [rsi]; Size
0x14000298b  add     rcx, 8; void *
0x14000298f  call    memmove
0x140002994  jmp     short loc_140002923
0x140002996  movzx   edx, word ptr [r14+2]
0x14000299b  mov     ecx, 40h ; '@'
0x1400029a0  mov     r8d, 75494454h
0x1400029a6  call    cs:__imp_ExAllocatePool2
0x1400029ad  nop     dword ptr [rax+rax+00h]
0x1400029b2  mov     [rbx+48h], rax
0x1400029b6  test    rax, rax
0x1400029b9  jz      short loc_1400029F9
0x1400029bb  movzx   r8d, word ptr [r14+2]; Size
0x1400029c0  mov     rcx, rax; void *
0x1400029c3  mov     rdx, [r14+8]; Src
0x1400029c7  call    memmove
0x1400029cc  movzx   eax, word ptr [r14]
0x1400029d0  mov     [rbx+40h], ax
0x1400029d4  movzx   eax, word ptr [r14+2]
0x1400029d9  mov     [rbx+42h], ax
0x1400029dd  jmp     loc_14000291A
0x1400029e2  mov     rcx, [rbx+48h]; P
0x1400029e6  test    rcx, rcx
0x1400029e9  jz      short loc_1400029F9
0x1400029eb  xor     edx, edx; Tag
0x1400029ed  call    cs:__imp_ExFreePoolWithTag
0x1400029f4  nop     dword ptr [rax+rax+00h]
0x1400029f9  xor     edx, edx; Tag
0x1400029fb  mov     rcx, rbx; P
0x1400029fe  call    cs:__imp_ExFreePoolWithTag
0x140002a05  nop     dword ptr [rax+rax+00h]
0x140002a0a  mov     rbp, [rsp+38h+arg_0]
0x140002a0f  mov     eax, 0C000009Ah
0x140002a14  jmp     loc_1400028CA
0x140002a19  mov     [r15], rbp
0x140002a1c  mov     rcx, [rbx+48h]; P
0x140002a20  test    rcx, rcx
0x140002a23  jz      short loc_140002A37
0x140002a25  xor     edx, edx; Tag
0x140002a27  call    cs:__imp_ExFreePoolWithTag
0x140002a2e  nop     dword ptr [rax+rax+00h]
0x140002a33  mov     [rbx+48h], rbp
0x140002a37  mov     rcx, [rbx+58h]; P
0x140002a3b  test    rcx, rcx
0x140002a3e  jz      short loc_140002A52
0x140002a40  xor     edx, edx; Tag
0x140002a42  call    cs:__imp_ExFreePoolWithTag
0x140002a49  nop     dword ptr [rax+rax+00h]
0x140002a4e  mov     [rbx+58h], rbp
0x140002a52  xor     edx, edx; Tag
0x140002a54  mov     rcx, rbx; P
0x140002a57  call    cs:__imp_ExFreePoolWithTag
0x140002a5e  nop     dword ptr [rax+rax+00h]
0x140002a63  jmp     loc_14000293A
```
