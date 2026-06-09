# WimpFSFIntegrityValidateWimHeader

- ea: `0x14002a394`
- end: `0x14002a47a`
- name: `WimpFSFIntegrityValidateWimHeader`
- size: `230`
- prototype: `__int64 __fastcall(PRTL_BITMAP BitMapHeader)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140028488`

## callees

- `0x140027fac`
- `0x14002a394`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a462`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a462`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a3c7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a3c7`
- `FLTMGR!FltReadFile` at `0x14002a42c`
- `FLTMGR!FltReadFile` at `0x14002a42c`

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
0x14002a394  mov     rax, rsp
0x14002a397  push    rbx
0x14002a398  push    rbp
0x14002a399  push    rsi
0x14002a39a  push    rdi
0x14002a39b  sub     rsp, 68h
0x14002a39f  mov     rbx, r8
0x14002a3a2  mov     dword ptr [rax+20h], 0
0x14002a3a9  mov     rbp, rdx
0x14002a3ac  mov     qword ptr [rax-38h], 0
0x14002a3b4  mov     rsi, rcx
0x14002a3b7  mov     edx, 1000h; NumberOfBytes
0x14002a3bc  mov     ecx, 1; PoolType
0x14002a3c1  mov     r8d, 69637077h; Tag
0x14002a3c7  call    cs:__imp_ExAllocatePoolWithTag
0x14002a3ce  nop     dword ptr [rax+rax+00h]
0x14002a3d3  mov     rdi, rax
0x14002a3d6  test    rax, rax
0x14002a3d9  jnz     short loc_14002A3E5
0x14002a3db  mov     ebx, 0C0000017h
0x14002a3e0  jmp     loc_14002A46E
0x14002a3e5  mov     rcx, [rbp+78h]; InitiatingInstance
0x14002a3e9  lea     rax, [rsp+88h+arg_18]
0x14002a3f1  mov     [rsp+88h+CallbackContext], 0; CallbackContext
0x14002a3fa  lea     r8, [rsp+88h+ByteOffset]; ByteOffset
0x14002a3ff  mov     [rsp+88h+CallbackRoutine], 0; CallbackRoutine
0x14002a408  mov     r9d, 1000h; Length
0x14002a40e  mov     [rsp+88h+BytesRead], rax; BytesRead
0x14002a413  mov     rdx, rbx; FileObject
0x14002a416  mov     [rsp+88h+Flags], 4; Flags
0x14002a41e  mov     [rsp+88h+Buffer], rdi; Buffer
0x14002a423  mov     qword ptr [rsp+88h+ByteOffset], 0
0x14002a42c  call    cs:__imp_FltReadFile
0x14002a433  nop     dword ptr [rax+rax+00h]
0x14002a438  mov     ebx, eax
0x14002a43a  test    eax, eax
0x14002a43c  js      short loc_14002A45A
0x14002a43e  mov     r9d, [rsp+88h+arg_18]
0x14002a446  xor     edx, edx
0x14002a448  mov     r8, rdi
0x14002a44b  mov     qword ptr [rsp+88h+ByteOffset], rdx
0x14002a450  mov     rcx, rsi; BitMapHeader
0x14002a453  call    WimFSFCheckIntegrityOfBlocks
0x14002a458  mov     ebx, eax
0x14002a45a  mov     edx, 69637077h; Tag
0x14002a45f  mov     rcx, rdi; P
0x14002a462  call    cs:__imp_ExFreePoolWithTag
0x14002a469  nop     dword ptr [rax+rax+00h]
0x14002a46e  mov     eax, ebx
0x14002a470  add     rsp, 68h
0x14002a474  pop     rdi
0x14002a475  pop     rsi
0x14002a476  pop     rbp
0x14002a477  pop     rbx
0x14002a478  retn
```
