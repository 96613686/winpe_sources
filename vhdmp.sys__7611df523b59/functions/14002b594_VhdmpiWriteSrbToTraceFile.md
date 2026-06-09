# VhdmpiWriteSrbToTraceFile

- ea: `0x14002b594`
- end: `0x14002b8e9`
- name: `VhdmpiWriteSrbToTraceFile`
- size: `853`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14002afcc`
- `0x14002b2d0`

## callees

- `0x140014660`
- `0x14001b7fc`
- `0x14001bc68`
- `0x14002aad4`
- `0x14002b594`
- `0x14005da00`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14002b5fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002b5fe`
- `ntoskrnl!ZwWriteFile` at `0x14002b808`
- `ntoskrnl!ZwWriteFile` at `0x14002b87a`
- `ntoskrnl!ZwWriteFile` at `0x14002b808`
- `ntoskrnl!ZwWriteFile` at `0x14002b87a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b8c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b8c5`
- `ntoskrnl!ExAllocatePool2` at `0x14002b71b`
- `ntoskrnl!ExAllocatePool2` at `0x14002b71b`

## pseudocode

```c
__int64 __fastcall VhdmpiWriteSrbToTraceFile(__int64 *a1, void *a2, int a3, unsigned int a4)
{
  __int64 v4; // rsi
  NTSTATUS Status; // r14d
  bool v7; // zf
  int v8; // eax
  void *v9; // r15
  int v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // r9d
  unsigned __int8 v13; // r13
  void *Pool2; // rax
  void *v15; // rbx
  PVOID Buffer; // rcx
  char v17; // bl
  void *v18; // rax
  char v20; // [rsp+58h] [rbp-19h]
  union _LARGE_INTEGER v21; // [rsp+60h] [rbp-11h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+68h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-1h] BYREF
  unsigned __int8 v24; // [rsp+D8h] [rbp+67h] BYREF
  PVOID v25; // [rsp+E0h] [rbp+6Fh]
  int v26; // [rsp+E8h] [rbp+77h]
  unsigned int v27; // [rsp+F0h] [rbp+7Fh]

  v27 = a4;
  v26 = a3;
  v25 = a2;
  v4 = *a1;
  Status = 0;
  ByteOffset.QuadPart = 0;
  IoStatusBlock = 0;
  v21.QuadPart = 0;
  v7 = *(_QWORD *)(v4 + 2152) == -1;
  v24 = 0;
  if ( !v7 && ((unsigned __int8)VhdmpiIsCTLogTrackingEnabled(v4) || (*(_DWORD *)(v4 + 2144) & 0x80u) != 0) )
  {
    if ( KeGetCurrentIrql() )
    {
      return (unsigned int)-1073741608;
    }
    else
    {
      v8 = *((_DWORD *)a1 + 15);
      v9 = 0;
      if ( v8 == 1 || v8 == 4 )
      {
        v10 = 1;
      }
      else
      {
        v10 = 0;
        if ( v8 == 8 )
        {
          v10 = 2;
          v25 = 0;
          v27 = *((_DWORD *)a1 + 13);
        }
      }
      v11 = *((_DWORD *)a1 + 17) | 0x10u;
      if ( (void (__fastcall *)(void *, int))a1[11] != VhdmpiRawIoEndIo )
        v11 = *((unsigned int *)a1 + 17);
      v20 = v11;
      VhdmpiAcquirePassiveLock(v4 + 2184, v11, VhdmpiRawIoEndIo);
      if ( *(_QWORD *)(v4 + 2152) == -1
        || !(unsigned __int8)VhdmpiIsCTLogTrackingEnabled(v4) && (*(_DWORD *)(v4 + 2144) & 0x80u) == 0 )
      {
        goto LABEL_42;
      }
      Status = -1073741823;
      v12 = v10 == 1 ? *((_DWORD *)a1 + 13) : 0;
      if ( !VhdmpiTraceIORequestMetadata(
              (struct _VHD_VIRTUAL_DISK *)v4,
              &v24,
              a1[4],
              v12,
              v10,
              v26,
              *((_DWORD *)a1 + 69),
              v20,
              (a1[8] & 0x20) != 0,
              v27) )
        goto LABEL_42;
      v13 = v24;
      if ( v24 )
      {
        Pool2 = (void *)ExAllocatePool2(72, 4096, 1749305430);
        v9 = Pool2;
        if ( Pool2 )
        {
          v15 = *(void **)(v4 + 2160);
          memmove(Pool2, v15, 0x1000u);
          memset(v15, 0, 0x1000u);
        }
      }
      Buffer = v25;
      if ( v25 && (*(_DWORD *)(v4 + 2144) & 2) == 0 )
      {
        ByteOffset = *(union _LARGE_INTEGER *)(v4 + 2176);
        *(_QWORD *)(v4 + 2176) += *((unsigned int *)a1 + 13);
      }
      if ( v13
        && (v21 = *(union _LARGE_INTEGER *)(v4 + 2176),
            *(_QWORD *)(v4 + 2176) += 4096LL,
            *(union _LARGE_INTEGER *)(v4 + 2168) = v21,
            !v9) )
      {
        v17 = 1;
      }
      else
      {
        VhdmpiReleasePassiveLock(v4 + 2184);
        Buffer = v25;
        v17 = 0;
      }
      if ( !Buffer
        || (*(_DWORD *)(v4 + 2144) & 2) != 0
        || (Status = ZwWriteFile(
                       *(HANDLE *)(v4 + 2152),
                       0,
                       0,
                       0,
                       &IoStatusBlock,
                       Buffer,
                       *((_DWORD *)a1 + 13),
                       &ByteOffset,
                       0),
            Status >= 0)
        && (Status = IoStatusBlock.Status, IoStatusBlock.Status >= 0) )
      {
        if ( v13 )
        {
          v18 = v9;
          if ( !v9 )
            v18 = *(void **)(v4 + 2160);
          Status = ZwWriteFile(*(HANDLE *)(v4 + 2152), 0, 0, 0, &IoStatusBlock, v18, 0x1000u, &v21, 0);
          if ( Status >= 0 )
          {
            Status = IoStatusBlock.Status;
            if ( IoStatusBlock.Status >= 0 && !v9 )
              memset(*(void **)(v4 + 2160), 0, 0x1000u);
          }
        }
      }
      if ( v17 )
LABEL_42:
        VhdmpiReleasePassiveLock(v4 + 2184);
      if ( v9 )
        ExFreePoolWithTag(v9, 0x68444856u);
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14002b594  mov     rax, rsp
0x14002b597  mov     [rax+20h], r9d
0x14002b59b  mov     [rax+18h], r8d
0x14002b59f  mov     [rax+10h], rdx
0x14002b5a3  push    rbp
0x14002b5a4  push    rbx
0x14002b5a5  push    rsi
0x14002b5a6  push    rdi
0x14002b5a7  push    r12
0x14002b5a9  push    r13
0x14002b5ab  push    r14
0x14002b5ad  push    r15
0x14002b5af  lea     rbp, [rax-5Fh]
0x14002b5b3  sub     rsp, 88h
0x14002b5ba  mov     rsi, [rcx]
0x14002b5bd  xor     r14d, r14d
0x14002b5c0  xorps   xmm0, xmm0
0x14002b5c3  mov     qword ptr [rbp+57h+var_60], r14
0x14002b5c7  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x14002b5cb  mov     qword ptr [rbp+57h+var_68], r14
0x14002b5cf  mov     r12, rcx
0x14002b5d2  cmp     qword ptr [rsi+868h], 0FFFFFFFFFFFFFFFFh
0x14002b5da  mov     [rbp+57h+arg_0], r14b
0x14002b5de  jz      loc_14002B8D1
0x14002b5e4  mov     rcx, rsi
0x14002b5e7  call    VhdmpiIsCTLogTrackingEnabled
0x14002b5ec  test    al, al
0x14002b5ee  jnz     short loc_14002B5FE
0x14002b5f0  mov     eax, [rsi+860h]
0x14002b5f6  test    al, al
0x14002b5f8  jns     loc_14002B8D1
0x14002b5fe  call    cs:__imp_KeGetCurrentIrql
0x14002b605  nop     dword ptr [rax+rax+00h]
0x14002b60a  test    al, al
0x14002b60c  jz      short loc_14002B619
0x14002b60e  mov     r14d, 0C00000D8h
0x14002b614  jmp     loc_14002B8D1
0x14002b619  mov     eax, [r12+3Ch]
0x14002b61e  mov     r13d, 1
0x14002b624  mov     r15, r14
0x14002b627  cmp     eax, r13d
0x14002b62a  jz      short loc_14002B64A
0x14002b62c  cmp     eax, 4
0x14002b62f  jz      short loc_14002B64A
0x14002b631  mov     ebx, r14d
0x14002b634  cmp     eax, 8
0x14002b637  jnz     short loc_14002B64D
0x14002b639  lea     ebx, [rax-6]
0x14002b63c  mov     [rbp+57h+arg_8], r14
0x14002b640  mov     eax, [r12+34h]
0x14002b645  mov     [rbp+57h+arg_18], eax
0x14002b648  jmp     short loc_14002B64D
0x14002b64a  mov     ebx, r13d
0x14002b64d  mov     ecx, [r12+44h]
0x14002b652  lea     r8, ?VhdmpiRawIoEndIo@@YAXPEAXJ@Z; VhdmpiRawIoEndIo(void *,long)
0x14002b659  mov     edx, ecx
0x14002b65b  lea     rdi, [rsi+888h]
0x14002b662  or      edx, 10h
0x14002b665  cmp     [r12+58h], r8
0x14002b66a  cmovnz  edx, ecx
0x14002b66d  mov     rcx, rdi
0x14002b670  mov     dword ptr [rbp+57h+var_70], edx
0x14002b673  call    VhdmpiAcquirePassiveLock
0x14002b678  cmp     qword ptr [rsi+868h], 0FFFFFFFFFFFFFFFFh
0x14002b680  jz      loc_14002B8B0
0x14002b686  mov     rcx, rsi
0x14002b689  call    VhdmpiIsCTLogTrackingEnabled
0x14002b68e  test    al, al
0x14002b690  jnz     short loc_14002B6A0
0x14002b692  mov     eax, [rsi+860h]
0x14002b698  test    al, al
0x14002b69a  jns     loc_14002B8B0
0x14002b6a0  mov     eax, [r12+40h]
0x14002b6a5  mov     r14d, 0C0000001h
0x14002b6ab  mov     edx, [r12+114h]
0x14002b6b3  shr     eax, 5
0x14002b6b6  and     al, r13b
0x14002b6b9  cmp     ebx, r13d
0x14002b6bc  jnz     short loc_14002B6C5
0x14002b6be  mov     r9d, [r12+34h]
0x14002b6c3  jmp     short loc_14002B6C8
0x14002b6c5  xor     r9d, r9d; unsigned int
0x14002b6c8  mov     ecx, [rbp+57h+arg_18]
0x14002b6cb  mov     r8, [r12+20h]; unsigned __int64
0x14002b6d0  mov     [rsp+48h], ecx; unsigned int
0x14002b6d4  mov     rcx, rsi; struct _VHD_VIRTUAL_DISK *
0x14002b6d7  mov     byte ptr [rsp+0C0h+Key], al; char
0x14002b6db  mov     eax, dword ptr [rbp+57h+var_70]
0x14002b6de  mov     dword ptr [rsp+0C0h+ByteOffset], eax; char
0x14002b6e2  mov     eax, [rbp+57h+arg_10]
0x14002b6e5  mov     [rsp+0C0h+Length], edx; unsigned int
0x14002b6e9  lea     rdx, [rbp+57h+arg_0]; unsigned __int8 *
0x14002b6ed  mov     dword ptr [rsp+0C0h+Buffer], eax; char
0x14002b6f1  mov     dword ptr [rsp+0C0h+IoStatusBlock], ebx; char
0x14002b6f5  call    ?VhdmpiTraceIORequestMetadata@@YAEPEAU_VHD_VIRTUAL_DISK@@PEAE_KKKKKKEK@Z; VhdmpiTraceIORequestMetadata(_VHD_VIRTUAL_DISK *,uchar *,unsigned __int64,ulong,ulong,ulong,ulong,ulong,uchar,ulong)
0x14002b6fa  test    al, al
0x14002b6fc  jz      loc_14002B8B0
0x14002b702  mov     r13b, [rbp+57h+arg_0]
0x14002b706  test    r13b, r13b
0x14002b709  jz      short loc_14002B757
0x14002b70b  mov     edx, 1000h
0x14002b710  mov     ecx, 48h ; 'H'
0x14002b715  mov     r8d, 68444856h
0x14002b71b  call    cs:__imp_ExAllocatePool2
0x14002b722  nop     dword ptr [rax+rax+00h]
0x14002b727  mov     r15, rax
0x14002b72a  test    rax, rax
0x14002b72d  jz      short loc_14002B757
0x14002b72f  mov     rbx, [rsi+870h]
0x14002b736  mov     r8d, 1000h; Size
0x14002b73c  mov     rdx, rbx; Src
0x14002b73f  mov     rcx, rax; void *
0x14002b742  call    memmove
0x14002b747  xor     edx, edx; Val
0x14002b749  mov     r8d, 1000h; Size
0x14002b74f  mov     rcx, rbx; void *
0x14002b752  call    memset
0x14002b757  mov     rcx, [rbp+57h+arg_8]
0x14002b75b  test    rcx, rcx
0x14002b75e  jz      short loc_14002B781
0x14002b760  mov     eax, [rsi+860h]
0x14002b766  test    al, 2
0x14002b768  jnz     short loc_14002B781
0x14002b76a  mov     rax, [rsi+880h]
0x14002b771  mov     qword ptr [rbp+57h+var_60], rax
0x14002b775  mov     eax, [r12+34h]
0x14002b77a  add     [rsi+880h], rax
0x14002b781  test    r13b, r13b
0x14002b784  jz      short loc_14002B7AC
0x14002b786  mov     rax, [rsi+880h]
0x14002b78d  mov     qword ptr [rbp+57h+var_68], rax
0x14002b791  add     qword ptr [rsi+880h], 1000h
0x14002b79c  mov     rax, qword ptr [rbp+57h+var_68]
0x14002b7a0  mov     [rsi+878h], rax
0x14002b7a7  test    r15, r15
0x14002b7aa  jz      short loc_14002B7BC
0x14002b7ac  mov     rcx, rdi
0x14002b7af  call    VhdmpiReleasePassiveLock
0x14002b7b4  mov     rcx, [rbp+57h+arg_8]
0x14002b7b8  xor     bl, bl
0x14002b7ba  jmp     short loc_14002B7C1
0x14002b7bc  mov     ebx, 1
0x14002b7c1  test    rcx, rcx
0x14002b7c4  jz      short loc_14002B82C
0x14002b7c6  mov     eax, [rsi+860h]
0x14002b7cc  test    al, 2
0x14002b7ce  jnz     short loc_14002B82C
0x14002b7d0  mov     [rsp+0C0h+Key], 0; Key
0x14002b7d9  lea     rax, [rbp+57h+var_60]
0x14002b7dd  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x14002b7e2  xor     r9d, r9d; ApcContext
0x14002b7e5  mov     eax, [r12+34h]
0x14002b7ea  xor     r8d, r8d; ApcRoutine
0x14002b7ed  mov     [rsp+0C0h+Length], eax; Length
0x14002b7f1  xor     edx, edx; Event
0x14002b7f3  mov     [rsp+0C0h+Buffer], rcx; Buffer
0x14002b7f8  lea     rax, [rbp+57h+var_58]
0x14002b7fc  mov     rcx, [rsi+868h]; FileHandle
0x14002b803  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14002b808  call    cs:__imp_ZwWriteFile
0x14002b80f  nop     dword ptr [rax+rax+00h]
0x14002b814  mov     r14d, eax
0x14002b817  test    eax, eax
0x14002b819  js      loc_14002B8AC
0x14002b81f  mov     r14d, dword ptr [rbp+57h+var_58]
0x14002b823  test    r14d, r14d
0x14002b826  js      loc_14002B8AC
0x14002b82c  test    r13b, r13b
0x14002b82f  jz      short loc_14002B8AC
0x14002b831  mov     rax, r15
0x14002b834  test    r15, r15
0x14002b837  jnz     short loc_14002B840
0x14002b839  mov     rax, [rsi+870h]
0x14002b840  mov     [rsp+0C0h+Key], 0; Key
0x14002b849  lea     rcx, [rbp+57h+var_68]
0x14002b84d  mov     [rsp+0C0h+ByteOffset], rcx; ByteOffset
0x14002b852  mov     r12d, 1000h
0x14002b858  mov     rcx, [rsi+868h]; FileHandle
0x14002b85f  xor     r9d, r9d; ApcContext
0x14002b862  mov     [rsp+0C0h+Length], r12d; Length
0x14002b867  xor     r8d, r8d; ApcRoutine
0x14002b86a  mov     [rsp+0C0h+Buffer], rax; Buffer
0x14002b86f  xor     edx, edx; Event
0x14002b871  lea     rax, [rbp+57h+var_58]
0x14002b875  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14002b87a  call    cs:__imp_ZwWriteFile
0x14002b881  nop     dword ptr [rax+rax+00h]
0x14002b886  mov     r14d, eax
0x14002b889  test    eax, eax
0x14002b88b  js      short loc_14002B8AC
0x14002b88d  mov     r14d, dword ptr [rbp+57h+var_58]
0x14002b891  test    r14d, r14d
0x14002b894  js      short loc_14002B8AC
0x14002b896  test    r15, r15
0x14002b899  jnz     short loc_14002B8AC
0x14002b89b  mov     rcx, [rsi+870h]; void *
0x14002b8a2  mov     r8d, r12d; Size
0x14002b8a5  xor     edx, edx; Val
0x14002b8a7  call    memset
0x14002b8ac  test    bl, bl
0x14002b8ae  jz      short loc_14002B8B8
0x14002b8b0  mov     rcx, rdi
0x14002b8b3  call    VhdmpiReleasePassiveLock
0x14002b8b8  test    r15, r15
0x14002b8bb  jz      short loc_14002B8D1
0x14002b8bd  mov     edx, 68444856h; Tag
0x14002b8c2  mov     rcx, r15; P
0x14002b8c5  call    cs:__imp_ExFreePoolWithTag
0x14002b8cc  nop     dword ptr [rax+rax+00h]
0x14002b8d1  mov     eax, r14d
0x14002b8d4  add     rsp, 88h
0x14002b8db  pop     r15
0x14002b8dd  pop     r14
0x14002b8df  pop     r13
0x14002b8e1  pop     r12
0x14002b8e3  pop     rdi
0x14002b8e4  pop     rsi
0x14002b8e5  pop     rbx
0x14002b8e6  pop     rbp
0x14002b8e7  retn
```
