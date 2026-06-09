# WimpFSFIntegrityValidateWimHeader

- ea: `0x14002a3e4`
- end: `0x14002a4ca`
- name: `WimpFSFIntegrityValidateWimHeader`
- size: `230`
- prototype: `__int64 __fastcall(PRTL_BITMAP BitMapHeader)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400284d8`

## callees

- `0x140027ffc`
- `0x14002a3e4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a4b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a4b2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a417`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a417`
- `FLTMGR!FltReadFile` at `0x14002a47c`
- `FLTMGR!FltReadFile` at `0x14002a47c`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityValidateWimHeader(PRTL_BITMAP BitMapHeader, __int64 a2, struct _FILE_OBJECT *a3)
{
  PVOID Buffer; // rdi
  int v7; // ebx
  struct _FLT_INSTANCE *v8; // rcx
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-38h] BYREF
  ULONG BytesRead; // [rsp+A8h] [rbp+20h] BYREF

  BytesRead = 0;
  ByteOffset.QuadPart = 0;
  Buffer = ExAllocatePoolWithTag(PagedPool, 0x1000u, 0x69637077u);
  if ( Buffer )
  {
    v8 = *(struct _FLT_INSTANCE **)(a2 + 120);
    ByteOffset.QuadPart = 0;
    v7 = FltReadFile(v8, a3, &ByteOffset, 0x1000u, Buffer, 4u, &BytesRead, 0, 0);
    if ( v7 >= 0 )
    {
      ByteOffset.QuadPart = 0;
      v7 = WimFSFCheckIntegrityOfBlocks(BitMapHeader, 0, (__int64)Buffer, BytesRead);
    }
    ExFreePoolWithTag(Buffer, 0x69637077u);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14002a3e4  mov     rax, rsp
0x14002a3e7  push    rbx
0x14002a3e8  push    rbp
0x14002a3e9  push    rsi
0x14002a3ea  push    rdi
0x14002a3eb  sub     rsp, 68h
0x14002a3ef  mov     rbx, r8
0x14002a3f2  mov     dword ptr [rax+20h], 0
0x14002a3f9  mov     rbp, rdx
0x14002a3fc  mov     qword ptr [rax-38h], 0
0x14002a404  mov     rsi, rcx
0x14002a407  mov     edx, 1000h; NumberOfBytes
0x14002a40c  mov     ecx, 1; PoolType
0x14002a411  mov     r8d, 69637077h; Tag
0x14002a417  call    cs:__imp_ExAllocatePoolWithTag
0x14002a41e  nop     dword ptr [rax+rax+00h]
0x14002a423  mov     rdi, rax
0x14002a426  test    rax, rax
0x14002a429  jnz     short loc_14002A435
0x14002a42b  mov     ebx, 0C0000017h
0x14002a430  jmp     loc_14002A4BE
0x14002a435  mov     rcx, [rbp+78h]; InitiatingInstance
0x14002a439  lea     rax, [rsp+88h+arg_18]
0x14002a441  mov     [rsp+88h+CallbackContext], 0; CallbackContext
0x14002a44a  lea     r8, [rsp+88h+ByteOffset]; ByteOffset
0x14002a44f  mov     [rsp+88h+CallbackRoutine], 0; CallbackRoutine
0x14002a458  mov     r9d, 1000h; Length
0x14002a45e  mov     [rsp+88h+BytesRead], rax; BytesRead
0x14002a463  mov     rdx, rbx; FileObject
0x14002a466  mov     [rsp+88h+Flags], 4; Flags
0x14002a46e  mov     [rsp+88h+Buffer], rdi; Buffer
0x14002a473  mov     qword ptr [rsp+88h+ByteOffset], 0
0x14002a47c  call    cs:__imp_FltReadFile
0x14002a483  nop     dword ptr [rax+rax+00h]
0x14002a488  mov     ebx, eax
0x14002a48a  test    eax, eax
0x14002a48c  js      short loc_14002A4AA
0x14002a48e  mov     r9d, [rsp+88h+arg_18]
0x14002a496  xor     edx, edx
0x14002a498  mov     r8, rdi
0x14002a49b  mov     qword ptr [rsp+88h+ByteOffset], rdx
0x14002a4a0  mov     rcx, rsi; BitMapHeader
0x14002a4a3  call    WimFSFCheckIntegrityOfBlocks
0x14002a4a8  mov     ebx, eax
0x14002a4aa  mov     edx, 69637077h; Tag
0x14002a4af  mov     rcx, rdi; P
0x14002a4b2  call    cs:__imp_ExFreePoolWithTag
0x14002a4b9  nop     dword ptr [rax+rax+00h]
0x14002a4be  mov     eax, ebx
0x14002a4c0  add     rsp, 68h
0x14002a4c4  pop     rdi
0x14002a4c5  pop     rsi
0x14002a4c6  pop     rbp
0x14002a4c7  pop     rbx
0x14002a4c8  retn
```
