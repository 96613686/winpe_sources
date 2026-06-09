# VhdmpiWriteSrbToTraceFile

- ea: `0x14002bab4`
- end: `0x14002be09`
- name: `VhdmpiWriteSrbToTraceFile`
- size: `853`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14002b4ec`
- `0x14002b7f0`

## callees

- `0x140014b00`
- `0x14001bc1c`
- `0x14001c088`
- `0x14002aff4`
- `0x14002bab4`
- `0x14005de00`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14002bb1e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002bb1e`
- `ntoskrnl!ZwWriteFile` at `0x14002bd28`
- `ntoskrnl!ZwWriteFile` at `0x14002bd9a`
- `ntoskrnl!ZwWriteFile` at `0x14002bd28`
- `ntoskrnl!ZwWriteFile` at `0x14002bd9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bde5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bde5`
- `ntoskrnl!ExAllocatePool2` at `0x14002bc3b`
- `ntoskrnl!ExAllocatePool2` at `0x14002bc3b`

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
  int v11; // edx
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
      v11 = *((_DWORD *)a1 + 17) | 0x10;
      if ( (void (__fastcall *)(void *, int))a1[11] != VhdmpiRawIoEndIo )
        v11 = *((_DWORD *)a1 + 17);
      v20 = v11;
      VhdmpiAcquirePassiveLock(v4 + 2184);
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
0x14002bab4  mov     rax, rsp
0x14002bab7  mov     [rax+20h], r9d
0x14002babb  mov     [rax+18h], r8d
0x14002babf  mov     [rax+10h], rdx
0x14002bac3  push    rbp
0x14002bac4  push    rbx
0x14002bac5  push    rsi
0x14002bac6  push    rdi
0x14002bac7  push    r12
0x14002bac9  push    r13
0x14002bacb  push    r14
0x14002bacd  push    r15
0x14002bacf  lea     rbp, [rax-5Fh]
0x14002bad3  sub     rsp, 88h
0x14002bada  mov     rsi, [rcx]
0x14002badd  xor     r14d, r14d
0x14002bae0  xorps   xmm0, xmm0
0x14002bae3  mov     qword ptr [rbp+57h+var_60], r14
0x14002bae7  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x14002baeb  mov     qword ptr [rbp+57h+var_68], r14
0x14002baef  mov     r12, rcx
0x14002baf2  cmp     qword ptr [rsi+868h], 0FFFFFFFFFFFFFFFFh
0x14002bafa  mov     [rbp+57h+arg_0], r14b
0x14002bafe  jz      loc_14002BDF1
0x14002bb04  mov     rcx, rsi
0x14002bb07  call    VhdmpiIsCTLogTrackingEnabled
0x14002bb0c  test    al, al
0x14002bb0e  jnz     short loc_14002BB1E
0x14002bb10  mov     eax, [rsi+860h]
0x14002bb16  test    al, al
0x14002bb18  jns     loc_14002BDF1
0x14002bb1e  call    cs:__imp_KeGetCurrentIrql
0x14002bb25  nop     dword ptr [rax+rax+00h]
0x14002bb2a  test    al, al
0x14002bb2c  jz      short loc_14002BB39
0x14002bb2e  mov     r14d, 0C00000D8h
0x14002bb34  jmp     loc_14002BDF1
0x14002bb39  mov     eax, [r12+3Ch]
0x14002bb3e  mov     r13d, 1
0x14002bb44  mov     r15, r14
0x14002bb47  cmp     eax, r13d
0x14002bb4a  jz      short loc_14002BB6A
0x14002bb4c  cmp     eax, 4
0x14002bb4f  jz      short loc_14002BB6A
0x14002bb51  mov     ebx, r14d
0x14002bb54  cmp     eax, 8
0x14002bb57  jnz     short loc_14002BB6D
0x14002bb59  lea     ebx, [rax-6]
0x14002bb5c  mov     [rbp+57h+arg_8], r14
0x14002bb60  mov     eax, [r12+34h]
0x14002bb65  mov     [rbp+57h+arg_18], eax
0x14002bb68  jmp     short loc_14002BB6D
0x14002bb6a  mov     ebx, r13d
0x14002bb6d  mov     ecx, [r12+44h]
0x14002bb72  lea     r8, ?VhdmpiRawIoEndIo@@YAXPEAXJ@Z; VhdmpiRawIoEndIo(void *,long)
0x14002bb79  mov     edx, ecx
0x14002bb7b  lea     rdi, [rsi+888h]
0x14002bb82  or      edx, 10h
0x14002bb85  cmp     [r12+58h], r8
0x14002bb8a  cmovnz  edx, ecx
0x14002bb8d  mov     rcx, rdi
0x14002bb90  mov     dword ptr [rbp+57h+var_70], edx
0x14002bb93  call    VhdmpiAcquirePassiveLock
0x14002bb98  cmp     qword ptr [rsi+868h], 0FFFFFFFFFFFFFFFFh
0x14002bba0  jz      loc_14002BDD0
0x14002bba6  mov     rcx, rsi
0x14002bba9  call    VhdmpiIsCTLogTrackingEnabled
0x14002bbae  test    al, al
0x14002bbb0  jnz     short loc_14002BBC0
0x14002bbb2  mov     eax, [rsi+860h]
0x14002bbb8  test    al, al
0x14002bbba  jns     loc_14002BDD0
0x14002bbc0  mov     eax, [r12+40h]
0x14002bbc5  mov     r14d, 0C0000001h
0x14002bbcb  mov     edx, [r12+114h]
0x14002bbd3  shr     eax, 5
0x14002bbd6  and     al, r13b
0x14002bbd9  cmp     ebx, r13d
0x14002bbdc  jnz     short loc_14002BBE5
0x14002bbde  mov     r9d, [r12+34h]
0x14002bbe3  jmp     short loc_14002BBE8
0x14002bbe5  xor     r9d, r9d; unsigned int
0x14002bbe8  mov     ecx, [rbp+57h+arg_18]
0x14002bbeb  mov     r8, [r12+20h]; unsigned __int64
0x14002bbf0  mov     [rsp+48h], ecx; unsigned int
0x14002bbf4  mov     rcx, rsi; struct _VHD_VIRTUAL_DISK *
0x14002bbf7  mov     byte ptr [rsp+0C0h+Key], al; char
0x14002bbfb  mov     eax, dword ptr [rbp+57h+var_70]
0x14002bbfe  mov     dword ptr [rsp+0C0h+ByteOffset], eax; char
0x14002bc02  mov     eax, [rbp+57h+arg_10]
0x14002bc05  mov     [rsp+0C0h+Length], edx; unsigned int
0x14002bc09  lea     rdx, [rbp+57h+arg_0]; unsigned __int8 *
0x14002bc0d  mov     dword ptr [rsp+0C0h+Buffer], eax; char
0x14002bc11  mov     dword ptr [rsp+0C0h+IoStatusBlock], ebx; char
0x14002bc15  call    ?VhdmpiTraceIORequestMetadata@@YAEPEAU_VHD_VIRTUAL_DISK@@PEAE_KKKKKKEK@Z; VhdmpiTraceIORequestMetadata(_VHD_VIRTUAL_DISK *,uchar *,unsigned __int64,ulong,ulong,ulong,ulong,ulong,uchar,ulong)
0x14002bc1a  test    al, al
0x14002bc1c  jz      loc_14002BDD0
0x14002bc22  mov     r13b, [rbp+57h+arg_0]
0x14002bc26  test    r13b, r13b
0x14002bc29  jz      short loc_14002BC77
0x14002bc2b  mov     edx, 1000h
0x14002bc30  mov     ecx, 48h ; 'H'
0x14002bc35  mov     r8d, 68444856h
0x14002bc3b  call    cs:__imp_ExAllocatePool2
0x14002bc42  nop     dword ptr [rax+rax+00h]
0x14002bc47  mov     r15, rax
0x14002bc4a  test    rax, rax
0x14002bc4d  jz      short loc_14002BC77
0x14002bc4f  mov     rbx, [rsi+870h]
0x14002bc56  mov     r8d, 1000h; Size
0x14002bc5c  mov     rdx, rbx; Src
0x14002bc5f  mov     rcx, rax; void *
0x14002bc62  call    memmove
0x14002bc67  xor     edx, edx; Val
0x14002bc69  mov     r8d, 1000h; Size
0x14002bc6f  mov     rcx, rbx; void *
0x14002bc72  call    memset
0x14002bc77  mov     rcx, [rbp+57h+arg_8]
0x14002bc7b  test    rcx, rcx
0x14002bc7e  jz      short loc_14002BCA1
0x14002bc80  mov     eax, [rsi+860h]
0x14002bc86  test    al, 2
0x14002bc88  jnz     short loc_14002BCA1
0x14002bc8a  mov     rax, [rsi+880h]
0x14002bc91  mov     qword ptr [rbp+57h+var_60], rax
0x14002bc95  mov     eax, [r12+34h]
0x14002bc9a  add     [rsi+880h], rax
0x14002bca1  test    r13b, r13b
0x14002bca4  jz      short loc_14002BCCC
0x14002bca6  mov     rax, [rsi+880h]
0x14002bcad  mov     qword ptr [rbp+57h+var_68], rax
0x14002bcb1  add     qword ptr [rsi+880h], 1000h
0x14002bcbc  mov     rax, qword ptr [rbp+57h+var_68]
0x14002bcc0  mov     [rsi+878h], rax
0x14002bcc7  test    r15, r15
0x14002bcca  jz      short loc_14002BCDC
0x14002bccc  mov     rcx, rdi
0x14002bccf  call    VhdmpiReleasePassiveLock
0x14002bcd4  mov     rcx, [rbp+57h+arg_8]
0x14002bcd8  xor     bl, bl
0x14002bcda  jmp     short loc_14002BCE1
0x14002bcdc  mov     ebx, 1
0x14002bce1  test    rcx, rcx
0x14002bce4  jz      short loc_14002BD4C
0x14002bce6  mov     eax, [rsi+860h]
0x14002bcec  test    al, 2
0x14002bcee  jnz     short loc_14002BD4C
0x14002bcf0  mov     [rsp+0C0h+Key], 0; Key
0x14002bcf9  lea     rax, [rbp+57h+var_60]
0x14002bcfd  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x14002bd02  xor     r9d, r9d; ApcContext
0x14002bd05  mov     eax, [r12+34h]
0x14002bd0a  xor     r8d, r8d; ApcRoutine
0x14002bd0d  mov     [rsp+0C0h+Length], eax; Length
0x14002bd11  xor     edx, edx; Event
0x14002bd13  mov     [rsp+0C0h+Buffer], rcx; Buffer
0x14002bd18  lea     rax, [rbp+57h+var_58]
0x14002bd1c  mov     rcx, [rsi+868h]; FileHandle
0x14002bd23  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14002bd28  call    cs:__imp_ZwWriteFile
0x14002bd2f  nop     dword ptr [rax+rax+00h]
0x14002bd34  mov     r14d, eax
0x14002bd37  test    eax, eax
0x14002bd39  js      loc_14002BDCC
0x14002bd3f  mov     r14d, dword ptr [rbp+57h+var_58]
0x14002bd43  test    r14d, r14d
0x14002bd46  js      loc_14002BDCC
0x14002bd4c  test    r13b, r13b
0x14002bd4f  jz      short loc_14002BDCC
0x14002bd51  mov     rax, r15
0x14002bd54  test    r15, r15
0x14002bd57  jnz     short loc_14002BD60
0x14002bd59  mov     rax, [rsi+870h]
0x14002bd60  mov     [rsp+0C0h+Key], 0; Key
0x14002bd69  lea     rcx, [rbp+57h+var_68]
0x14002bd6d  mov     [rsp+0C0h+ByteOffset], rcx; ByteOffset
0x14002bd72  mov     r12d, 1000h
0x14002bd78  mov     rcx, [rsi+868h]; FileHandle
0x14002bd7f  xor     r9d, r9d; ApcContext
0x14002bd82  mov     [rsp+0C0h+Length], r12d; Length
0x14002bd87  xor     r8d, r8d; ApcRoutine
0x14002bd8a  mov     [rsp+0C0h+Buffer], rax; Buffer
0x14002bd8f  xor     edx, edx; Event
0x14002bd91  lea     rax, [rbp+57h+var_58]
0x14002bd95  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14002bd9a  call    cs:__imp_ZwWriteFile
0x14002bda1  nop     dword ptr [rax+rax+00h]
0x14002bda6  mov     r14d, eax
0x14002bda9  test    eax, eax
0x14002bdab  js      short loc_14002BDCC
0x14002bdad  mov     r14d, dword ptr [rbp+57h+var_58]
0x14002bdb1  test    r14d, r14d
0x14002bdb4  js      short loc_14002BDCC
0x14002bdb6  test    r15, r15
0x14002bdb9  jnz     short loc_14002BDCC
0x14002bdbb  mov     rcx, [rsi+870h]; void *
0x14002bdc2  mov     r8d, r12d; Size
0x14002bdc5  xor     edx, edx; Val
0x14002bdc7  call    memset
0x14002bdcc  test    bl, bl
0x14002bdce  jz      short loc_14002BDD8
0x14002bdd0  mov     rcx, rdi
0x14002bdd3  call    VhdmpiReleasePassiveLock
0x14002bdd8  test    r15, r15
0x14002bddb  jz      short loc_14002BDF1
0x14002bddd  mov     edx, 68444856h; Tag
0x14002bde2  mov     rcx, r15; P
0x14002bde5  call    cs:__imp_ExFreePoolWithTag
0x14002bdec  nop     dword ptr [rax+rax+00h]
0x14002bdf1  mov     eax, r14d
0x14002bdf4  add     rsp, 88h
0x14002bdfb  pop     r15
0x14002bdfd  pop     r14
0x14002bdff  pop     r13
0x14002be01  pop     r12
0x14002be03  pop     rdi
0x14002be04  pop     rsi
0x14002be05  pop     rbx
0x14002be06  pop     rbp
0x14002be07  retn
```
