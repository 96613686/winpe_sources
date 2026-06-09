# DoDeleteFile

- ea: `0x140001680`
- end: `0x1400016f8`
- name: `DoDeleteFile`
- size: `120`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400028a4`

## callees

- `0x140001680`
- `0x1400021d0`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1400016d5`
- `ntdll!NtSetInformationFile` at `0x1400016d5`
- `ntdll!NtClose` at `0x1400016ea`
- `ntdll!NtClose` at `0x1400016ea`

## pseudocode

```c
__int64 __fastcall DoDeleteFile(struct _UNICODE_STRING *a1)
{
  int v1; // edi
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-18h] BYREF
  char FileInformation; // [rsp+58h] [rbp+10h] BYREF
  HANDLE FileHandle; // [rsp+60h] [rbp+18h] BYREF

  FileHandle = 0;
  FileInformation = 0;
  IoStatusBlock = 0;
  v1 = MoveDeleteCommon(&FileHandle, a1, a1, 0);
  if ( v1 >= 0 )
  {
    FileInformation = 1;
    v1 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 1u, FileDispositionInformation);
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140001680  mov     rax, rsp
0x140001683  push    rdi
0x140001684  sub     rsp, 40h
0x140001688  xorps   xmm0, xmm0
0x14000168b  mov     qword ptr [rax+18h], 0
0x140001693  mov     r8, rcx
0x140001696  mov     byte ptr [rax+10h], 0
0x14000169a  mov     rdx, rcx
0x14000169d  xor     r9d, r9d
0x1400016a0  lea     rcx, [rax+18h]
0x1400016a4  movups  xmmword ptr [rax-18h], xmm0
0x1400016a8  call    MoveDeleteCommon
0x1400016ad  mov     edi, eax
0x1400016af  test    eax, eax
0x1400016b1  js      short loc_1400016DD
0x1400016b3  mov     rcx, [rsp+48h+FileHandle]; FileHandle
0x1400016b8  lea     r8, [rsp+48h+FileInformation]; FileInformation
0x1400016bd  mov     r9d, 1; Length
0x1400016c3  mov     [rsp+48h+FileInformation], 1
0x1400016c8  lea     rdx, [rsp+48h+IoStatusBlock]; IoStatusBlock
0x1400016cd  mov     [rsp+48h+FileInformationClass], 0Dh; FileInformationClass
0x1400016d5  call    cs:__imp_NtSetInformationFile
0x1400016db  mov     edi, eax
0x1400016dd  cmp     [rsp+48h+FileHandle], 0
0x1400016e3  jz      short loc_1400016F0
0x1400016e5  mov     rcx, [rsp+48h+FileHandle]; Handle
0x1400016ea  call    cs:__imp_NtClose
0x1400016f0  mov     eax, edi
0x1400016f2  add     rsp, 40h
0x1400016f6  pop     rdi
0x1400016f7  retn
```
