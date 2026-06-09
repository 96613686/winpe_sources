# VhdmpiCTLogUninitVirtualDiskForTracing(_VHD_VIRTUAL_DISK *)

- ea: `0x140049954`
- end: `0x140049b67`
- name: `?VhdmpiCTLogUninitVirtualDiskForTracing@@YAJPEAU_VHD_VIRTUAL_DISK@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(struct _VHD_VIRTUAL_DISK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14004a0d0`

## callees

- `0x14002b6a4`
- `0x140049954`
- `0x14005dac2`
- `0x14005dbb0`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!ZwWriteFile` at `0x140049a11`
- `ntoskrnl!ZwWriteFile` at `0x140049aa6`
- `ntoskrnl!ZwWriteFile` at `0x140049a11`
- `ntoskrnl!ZwWriteFile` at `0x140049aa6`
- `ntoskrnl!ZwClose` at `0x140049ac8`
- `ntoskrnl!ZwClose` at `0x140049ac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049af0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049af0`

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
0x140049954  mov     [rsp-8+arg_8], rbx
0x140049959  mov     [rsp-8+arg_10], rsi
0x14004995e  push    rbp
0x14004995f  push    rdi
0x140049960  push    r12
0x140049962  lea     rbp, [rsp-0F90h]
0x14004996a  mov     eax, 1090h
0x14004996f  call    __chkstk_0
0x140049974  sub     rsp, rax
0x140049977  mov     rax, cs:__security_cookie
0x14004997e  xor     rax, rsp
0x140049981  mov     [rbp+0FA0h+var_20], rax
0x140049988  mov     rbx, rcx
0x14004998b  mov     qword ptr [rsp+10A0h+var_1050], 0
0x140049994  xorps   xmm0, xmm0
0x140049997  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x14004999b  mov     r12d, 1000h
0x1400499a1  xor     edx, edx; Val
0x1400499a3  mov     r8d, r12d; Size
0x1400499a6  movups  xmmword ptr [rsp+10A0h+var_1048], xmm0
0x1400499ab  call    memset
0x1400499b0  mov     rcx, [rbx+868h]; FileHandle
0x1400499b7  xor     esi, esi
0x1400499b9  xorps   xmm0, xmm0
0x1400499bc  movups  xmmword ptr [rsp+10A0h+var_1038], xmm0
0x1400499c1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400499c5  jz      loc_140049B07
0x1400499cb  mov     rdx, [rbx+870h]
0x1400499d2  lea     rdi, [rbx+880h]
0x1400499d9  cmp     [rdx+8], esi
0x1400499dc  jbe     short loc_140049A36
0x1400499de  mov     rax, [rdi]
0x1400499e1  xor     r9d, r9d; ApcContext
0x1400499e4  mov     [rsp+10A0h+Key], rsi; Key
0x1400499e9  xor     r8d, r8d; ApcRoutine
0x1400499ec  mov     qword ptr [rsp+10A0h+var_1050], rax
0x1400499f1  lea     rax, [rsp+10A0h+var_1050]
0x1400499f6  mov     [rsp+10A0h+ByteOffset], rax; ByteOffset
0x1400499fb  lea     rax, [rsp+10A0h+var_1048]
0x140049a00  mov     [rsp+10A0h+Length], r12d; Length
0x140049a05  mov     [rsp+10A0h+Buffer], rdx; Buffer
0x140049a0a  xor     edx, edx; Event
0x140049a0c  mov     [rsp+10A0h+IoStatusBlock], rax; IoStatusBlock
0x140049a11  call    cs:__imp_ZwWriteFile
0x140049a18  nop     dword ptr [rax+rax+00h]
0x140049a1d  mov     esi, eax
0x140049a1f  test    eax, eax
0x140049a21  js      loc_140049ABB
0x140049a27  mov     esi, dword ptr [rsp+10A0h+var_1048]
0x140049a2b  test    esi, esi
0x140049a2d  js      loc_140049ABB
0x140049a33  add     [rdi], r12
0x140049a36  mov     r8, [rdi]
0x140049a39  lea     rax, [rsp+10A0h+var_1038]
0x140049a3e  mov     [rsp+10A0h+Length], 0; int
0x140049a46  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x140049a4a  mov     [rsp+10A0h+Buffer], rax; __int64
0x140049a4f  mov     r9, r8
0x140049a52  lea     rax, [rsp+10A0h+var_1038]
0x140049a57  xor     edx, edx
0x140049a59  mov     [rsp+10A0h+IoStatusBlock], rax; __int64
0x140049a5e  call    VhdmpiPopulatedLogFileHeader
0x140049a63  mov     rcx, [rbx+868h]; FileHandle
0x140049a6a  lea     rax, [rsp+10A0h+var_1050]
0x140049a6f  mov     [rsp+10A0h+Key], 0; Key
0x140049a78  xor     r9d, r9d; ApcContext
0x140049a7b  mov     [rsp+10A0h+ByteOffset], rax; ByteOffset
0x140049a80  xor     r8d, r8d; ApcRoutine
0x140049a83  lea     rax, [rbp+0FA0h+var_1020]
0x140049a87  mov     [rsp+10A0h+Length], r12d; Length
0x140049a8c  mov     [rsp+10A0h+Buffer], rax; Buffer
0x140049a91  xor     edx, edx; Event
0x140049a93  lea     rax, [rsp+10A0h+var_1048]
0x140049a98  mov     qword ptr [rsp+10A0h+var_1050], 0
0x140049aa1  mov     [rsp+10A0h+IoStatusBlock], rax; IoStatusBlock
0x140049aa6  call    cs:__imp_ZwWriteFile
0x140049aad  nop     dword ptr [rax+rax+00h]
0x140049ab2  test    eax, eax
0x140049ab4  mov     esi, eax
0x140049ab6  cmovns  esi, dword ptr [rsp+10A0h+var_1048]
0x140049abb  mov     rcx, [rbx+868h]; Handle
0x140049ac2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140049ac6  jz      short loc_140049ADF
0x140049ac8  call    cs:__imp_ZwClose
0x140049acf  nop     dword ptr [rax+rax+00h]
0x140049ad4  mov     qword ptr [rbx+868h], 0FFFFFFFFFFFFFFFFh
0x140049adf  mov     rcx, [rbx+870h]; P
0x140049ae6  test    rcx, rcx
0x140049ae9  jz      short loc_140049B07
0x140049aeb  mov     edx, 68444856h; Tag
0x140049af0  call    cs:__imp_ExFreePoolWithTag
0x140049af7  nop     dword ptr [rax+rax+00h]
0x140049afc  mov     qword ptr [rbx+870h], 0
0x140049b07  mov     qword ptr [rbx+868h], 0FFFFFFFFFFFFFFFFh
0x140049b12  mov     eax, esi
0x140049b14  mov     qword ptr [rbx+878h], 0
0x140049b1f  mov     qword ptr [rbx+880h], 0
0x140049b2a  mov     dword ptr [rbx+860h], 0
0x140049b34  mov     qword ptr [rbx+870h], 0
0x140049b3f  mov     rcx, [rbp+0FA0h+var_20]
0x140049b46  xor     rcx, rsp; StackCookie
0x140049b49  call    __security_check_cookie
0x140049b4e  lea     r11, [rsp+10A0h+var_10]
0x140049b56  mov     rbx, [r11+28h]
0x140049b5a  mov     rsi, [r11+30h]
0x140049b5e  mov     rsp, r11
0x140049b61  pop     r12
0x140049b63  pop     rdi
0x140049b64  pop     rbp
0x140049b65  retn
```
