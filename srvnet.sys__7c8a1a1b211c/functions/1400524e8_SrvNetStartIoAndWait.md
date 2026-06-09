# SrvNetStartIoAndWait

- ea: `0x1400524e8`
- end: `0x14005259c`
- name: `SrvNetStartIoAndWait`
- size: `180`
- prototype: `__int64 __fastcall(PIRP Irp, PDEVICE_OBJECT DeviceObject, PVOID Object)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140043b58`
- `0x140043c14`
- `0x140052190`
- `0x1400522b0`

## callees

- `0x140016cc8`
- `0x1400524e8`

## import_xrefs

- `ntoskrnl!IoQueueThreadIrp` at `0x1400524fd`
- `ntoskrnl!IoQueueThreadIrp` at `0x1400524fd`
- `ntoskrnl!IofCallDriver` at `0x14005250f`
- `ntoskrnl!IofCallDriver` at `0x14005250f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052550`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052550`

## pseudocode

```c
__int64 __fastcall SrvNetStartIoAndWait(PIRP Irp, PDEVICE_OBJECT DeviceObject, PVOID Object, unsigned int *a4)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx

  IoQueueThreadIrp(Irp);
  v8 = IofCallDriver(DeviceObject, Irp);
  v9 = v8;
  if ( v8 == 259 )
  {
    KeWaitForSingleObject(Object, UserRequest, 0, 0, 0);
LABEL_3:
    v9 = *a4;
    if ( (*a4 & 0x80000000) == 0 )
      return v9;
    goto LABEL_6;
  }
  if ( v8 >= 0 )
    goto LABEL_3;
LABEL_6:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f4edf8bb09033153e0e3095b0e0d8d4b_Traceguids, Irp, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x1400524e8  push    rbx
0x1400524ea  push    rbp
0x1400524eb  push    rsi
0x1400524ec  push    rdi
0x1400524ed  sub     rsp, 38h
0x1400524f1  mov     rsi, r9
0x1400524f4  mov     rbp, r8
0x1400524f7  mov     rbx, rdx
0x1400524fa  mov     rdi, rcx
0x1400524fd  call    cs:__imp_IoQueueThreadIrp
0x140052504  nop     dword ptr [rax+rax+00h]
0x140052509  mov     rdx, rdi; Irp
0x14005250c  mov     rcx, rbx; DeviceObject
0x14005250f  call    cs:__imp_IofCallDriver
0x140052516  nop     dword ptr [rax+rax+00h]
0x14005251b  mov     ebx, eax
0x14005251d  cmp     eax, 103h
0x140052522  jz      short loc_14005253A
0x140052524  test    eax, eax
0x140052526  js      short loc_14005255E
0x140052528  mov     ebx, [rsi]
0x14005252a  test    ebx, ebx
0x14005252c  js      short loc_14005255E
0x14005252e  mov     eax, ebx
0x140052530  add     rsp, 38h
0x140052534  pop     rdi
0x140052535  pop     rsi
0x140052536  pop     rbp
0x140052537  pop     rbx
0x140052538  retn
0x14005253a  xor     r9d, r9d; Alertable
0x14005253d  mov     [rsp+58h+Timeout], 0; Timeout
0x140052546  xor     r8d, r8d; WaitMode
0x140052549  mov     rcx, rbp; Object
0x14005254c  lea     edx, [r9+6]; WaitReason
0x140052550  call    cs:__imp_KeWaitForSingleObject
0x140052557  nop     dword ptr [rax+rax+00h]
0x14005255c  jmp     short loc_140052528
0x14005255e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052565  lea     rax, WPP_GLOBAL_Control
0x14005256c  cmp     rcx, rax
0x14005256f  jz      short loc_14005252E
0x140052571  mov     eax, [rcx+2Ch]
0x140052574  test    al, 10h
0x140052576  jz      short loc_14005252E
0x140052578  cmp     byte ptr [rcx+29h], 1
0x14005257c  jb      short loc_14005252E
0x14005257e  mov     rcx, [rcx+18h]
0x140052582  lea     r8, WPP_f4edf8bb09033153e0e3095b0e0d8d4b_Traceguids
0x140052589  mov     edx, 0Bh
0x14005258e  mov     dword ptr [rsp+58h+Timeout], ebx
0x140052592  mov     r9, rdi
0x140052595  call    WPP_SF_qD
0x14005259a  jmp     short loc_14005252E
```
