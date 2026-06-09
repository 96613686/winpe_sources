# VhdmpiCTLogUninitVirtualDiskForTracing(_VHD_VIRTUAL_DISK *)

- ea: `0x140049564`
- end: `0x140049777`
- name: `?VhdmpiCTLogUninitVirtualDiskForTracing@@YAJPEAU_VHD_VIRTUAL_DISK@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140049ce0`

## callees

- `0x14002b184`
- `0x140049564`
- `0x14005d6d2`
- `0x14005d7c0`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!ZwWriteFile` at `0x140049621`
- `ntoskrnl!ZwWriteFile` at `0x1400496b6`
- `ntoskrnl!ZwWriteFile` at `0x140049621`
- `ntoskrnl!ZwWriteFile` at `0x1400496b6`
- `ntoskrnl!ZwClose` at `0x1400496d8`
- `ntoskrnl!ZwClose` at `0x1400496d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049700`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049700`

## pseudocode

```c
__int64 __fastcall VhdmpiCTLogUninitVirtualDiskForTracing(struct _VHD_VIRTUAL_DISK *a1)
{
  void *v2; // rcx
  NTSTATUS Status; // esi
  _DWORD *Buffer; // rdx
  union _LARGE_INTEGER *v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 result; // rax
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v12[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v13[4096]; // [rsp+80h] [rbp-80h] BYREF

  ByteOffset.QuadPart = 0;
  IoStatusBlock = 0;
  memset(v13, 0, sizeof(v13));
  v2 = (void *)*((_QWORD *)a1 + 269);
  Status = 0;
  *(_OWORD *)v12 = 0;
  if ( v2 == (void *)-1LL )
    goto LABEL_12;
  Buffer = (_DWORD *)*((_QWORD *)a1 + 270);
  v5 = (union _LARGE_INTEGER *)((char *)a1 + 2176);
  if ( !Buffer[2] )
    goto LABEL_6;
  ByteOffset = *v5;
  Status = ZwWriteFile(v2, 0, 0, 0, &IoStatusBlock, Buffer, 0x1000u, &ByteOffset, 0);
  if ( Status >= 0 )
  {
    Status = IoStatusBlock.Status;
    if ( IoStatusBlock.Status >= 0 )
    {
      v5->QuadPart += 4096LL;
LABEL_6:
      VhdmpiPopulatedLogFileHeader(v13, (__int64)v12, (__int64)v12, 0);
      v6 = (void *)*((_QWORD *)a1 + 269);
      ByteOffset.QuadPart = 0;
      Status = ZwWriteFile(v6, 0, 0, 0, &IoStatusBlock, v13, 0x1000u, &ByteOffset, 0);
      if ( Status >= 0 )
        Status = IoStatusBlock.Status;
    }
  }
  v7 = (void *)*((_QWORD *)a1 + 269);
  if ( v7 != (void *)-1LL )
  {
    ZwClose(v7);
    *((_QWORD *)a1 + 269) = -1;
  }
  v8 = (void *)*((_QWORD *)a1 + 270);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0x68444856u);
    *((_QWORD *)a1 + 270) = 0;
  }
LABEL_12:
  *((_QWORD *)a1 + 269) = -1;
  result = (unsigned int)Status;
  *((_QWORD *)a1 + 271) = 0;
  *((_QWORD *)a1 + 272) = 0;
  *((_DWORD *)a1 + 536) = 0;
  *((_QWORD *)a1 + 270) = 0;
  return result;
}

```

## disassembly

```asm
0x140049564  mov     [rsp-8+arg_8], rbx
0x140049569  mov     [rsp-8+arg_10], rsi
0x14004956e  push    rbp
0x14004956f  push    rdi
0x140049570  push    r12
0x140049572  lea     rbp, [rsp-0F90h]
0x14004957a  mov     eax, 1090h
0x14004957f  call    __chkstk_0
0x140049584  sub     rsp, rax
0x140049587  mov     rax, cs:__security_cookie
0x14004958e  xor     rax, rsp
0x140049591  mov     [rbp+0FA0h+var_20], rax
0x140049598  mov     rbx, rcx
0x14004959b  mov     qword ptr [rsp+10A0h+var_1050], 0
0x1400495a4  xorps   xmm0, xmm0
0x1400495a7  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x1400495ab  mov     r12d, 1000h
0x1400495b1  xor     edx, edx; Val
0x1400495b3  mov     r8d, r12d; Size
0x1400495b6  movups  xmmword ptr [rsp+10A0h+var_1048], xmm0
0x1400495bb  call    memset
0x1400495c0  mov     rcx, [rbx+868h]; FileHandle
0x1400495c7  xor     esi, esi
0x1400495c9  xorps   xmm0, xmm0
0x1400495cc  movups  xmmword ptr [rsp+10A0h+var_1038], xmm0
0x1400495d1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400495d5  jz      loc_140049717
0x1400495db  mov     rdx, [rbx+870h]
0x1400495e2  lea     rdi, [rbx+880h]
0x1400495e9  cmp     [rdx+8], esi
0x1400495ec  jbe     short loc_140049646
0x1400495ee  mov     rax, [rdi]
0x1400495f1  xor     r9d, r9d; ApcContext
0x1400495f4  mov     [rsp+10A0h+Key], rsi; Key
0x1400495f9  xor     r8d, r8d; ApcRoutine
0x1400495fc  mov     qword ptr [rsp+10A0h+var_1050], rax
0x140049601  lea     rax, [rsp+10A0h+var_1050]
0x140049606  mov     [rsp+10A0h+ByteOffset], rax; ByteOffset
0x14004960b  lea     rax, [rsp+10A0h+var_1048]
0x140049610  mov     [rsp+10A0h+Length], r12d; Length
0x140049615  mov     [rsp+10A0h+Buffer], rdx; Buffer
0x14004961a  xor     edx, edx; Event
0x14004961c  mov     [rsp+10A0h+IoStatusBlock], rax; IoStatusBlock
0x140049621  call    cs:__imp_ZwWriteFile
0x140049628  nop     dword ptr [rax+rax+00h]
0x14004962d  mov     esi, eax
0x14004962f  test    eax, eax
0x140049631  js      loc_1400496CB
0x140049637  mov     esi, dword ptr [rsp+10A0h+var_1048]
0x14004963b  test    esi, esi
0x14004963d  js      loc_1400496CB
0x140049643  add     [rdi], r12
0x140049646  mov     r8, [rdi]
0x140049649  lea     rax, [rsp+10A0h+var_1038]
0x14004964e  mov     [rsp+10A0h+Length], 0; int
0x140049656  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x14004965a  mov     [rsp+10A0h+Buffer], rax; __int64
0x14004965f  mov     r9, r8
0x140049662  lea     rax, [rsp+10A0h+var_1038]
0x140049667  xor     edx, edx
0x140049669  mov     [rsp+10A0h+IoStatusBlock], rax; __int64
0x14004966e  call    VhdmpiPopulatedLogFileHeader
0x140049673  mov     rcx, [rbx+868h]; FileHandle
0x14004967a  lea     rax, [rsp+10A0h+var_1050]
0x14004967f  mov     [rsp+10A0h+Key], 0; Key
0x140049688  xor     r9d, r9d; ApcContext
0x14004968b  mov     [rsp+10A0h+ByteOffset], rax; ByteOffset
0x140049690  xor     r8d, r8d; ApcRoutine
0x140049693  lea     rax, [rbp+0FA0h+var_1020]
0x140049697  mov     [rsp+10A0h+Length], r12d; Length
0x14004969c  mov     [rsp+10A0h+Buffer], rax; Buffer
0x1400496a1  xor     edx, edx; Event
0x1400496a3  lea     rax, [rsp+10A0h+var_1048]
0x1400496a8  mov     qword ptr [rsp+10A0h+var_1050], 0
0x1400496b1  mov     [rsp+10A0h+IoStatusBlock], rax; IoStatusBlock
0x1400496b6  call    cs:__imp_ZwWriteFile
0x1400496bd  nop     dword ptr [rax+rax+00h]
0x1400496c2  test    eax, eax
0x1400496c4  mov     esi, eax
0x1400496c6  cmovns  esi, dword ptr [rsp+10A0h+var_1048]
0x1400496cb  mov     rcx, [rbx+868h]; Handle
0x1400496d2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400496d6  jz      short loc_1400496EF
0x1400496d8  call    cs:__imp_ZwClose
0x1400496df  nop     dword ptr [rax+rax+00h]
0x1400496e4  mov     qword ptr [rbx+868h], 0FFFFFFFFFFFFFFFFh
0x1400496ef  mov     rcx, [rbx+870h]; P
0x1400496f6  test    rcx, rcx
0x1400496f9  jz      short loc_140049717
0x1400496fb  mov     edx, 68444856h; Tag
0x140049700  call    cs:__imp_ExFreePoolWithTag
0x140049707  nop     dword ptr [rax+rax+00h]
0x14004970c  mov     qword ptr [rbx+870h], 0
0x140049717  mov     qword ptr [rbx+868h], 0FFFFFFFFFFFFFFFFh
0x140049722  mov     eax, esi
0x140049724  mov     qword ptr [rbx+878h], 0
0x14004972f  mov     qword ptr [rbx+880h], 0
0x14004973a  mov     dword ptr [rbx+860h], 0
0x140049744  mov     qword ptr [rbx+870h], 0
0x14004974f  mov     rcx, [rbp+0FA0h+var_20]
0x140049756  xor     rcx, rsp; StackCookie
0x140049759  call    __security_check_cookie
0x14004975e  lea     r11, [rsp+10A0h+var_10]
0x140049766  mov     rbx, [r11+28h]
0x14004976a  mov     rsi, [r11+30h]
0x14004976e  mov     rsp, r11
0x140049771  pop     r12
0x140049773  pop     rdi
0x140049774  pop     rbp
0x140049775  retn
```
