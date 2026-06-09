# GetEntry

- ea: `0x140001dd0`
- end: `0x140001f9e`
- name: `GetEntry`
- size: `462`
- prototype: `NTSTATUS __fastcall(HANDLE FileHandle, _WORD *, _WORD *, _WORD *, union _LARGE_INTEGER ByteOffset, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1400028a4`

## callees

- `0x1400012f0`
- `0x140001dd0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140001e6f`
- `ntdll!RtlAllocateHeap` at `0x140001e6f`
- `ntdll!NtReadFile` at `0x140001ee1`
- `ntdll!NtReadFile` at `0x140001ee1`

## pseudocode

```c
NTSTATUS __fastcall GetEntry(
        HANDLE FileHandle,
        _WORD *a2,
        _WORD *a3,
        _WORD *a4,
        union _LARGE_INTEGER ByteOffset,
        __int64 *a6)
{
  _WORD *QuadPart; // rcx
  unsigned int v8; // edx
  int v9; // edi
  char *Buffer; // r9
  __int64 v11; // r14
  char *v12; // rbx
  __int64 v13; // rsi
  NTSTATUS result; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v16[4]; // [rsp+60h] [rbp-20h]

  v16[0] = a2;
  *a2 = 0;
  QuadPart = (_WORD *)ByteOffset.QuadPart;
  v8 = dword_1400056E4;
  v9 = 0;
  *a3 = 0;
  *a4 = 0;
  v16[2] = a4;
  Buffer = (char *)::Buffer;
  *QuadPart = 0;
  v16[1] = a3;
  v16[3] = QuadPart;
  while ( 2 )
  {
    IoStatusBlock = 0;
    ByteOffset.QuadPart = 0;
    v11 = v16[v9];
    v12 = &Buffer[2 * v8];
    v13 = qword_1400056D8 + 2LL * v8;
    while ( 1 )
    {
      if ( v8 != dword_1400056E0 )
        goto LABEL_9;
      if ( !Buffer )
      {
        ::Buffer = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, 0x10000u);
        Buffer = (char *)::Buffer;
        if ( !::Buffer )
          return -1073741801;
      }
      qword_1400056D8 += 2LL * (unsigned int)dword_1400056E0;
      ByteOffset.QuadPart = qword_1400056D8;
      dword_1400056E0 = 0;
      dword_1400056E4 = 0;
      result = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, 0x10000u, &ByteOffset, 0);
      if ( result == -1073741807 )
        break;
      if ( result < 0 )
        return result;
      Buffer = (char *)::Buffer;
      v8 = dword_1400056E4;
      v12 = (char *)::Buffer;
      dword_1400056E0 = LODWORD(IoStatusBlock.Information) >> 1;
LABEL_9:
      dword_1400056E4 = ++v8;
      if ( *(_WORD *)v12 != 0xFEFF )
      {
        if ( !*(_WORD *)v12 )
          goto LABEL_18;
LABEL_14:
        AddToUnicodeString(v11, *(unsigned __int16 *)v12);
        v8 = dword_1400056E4;
        Buffer = (char *)::Buffer;
        goto LABEL_15;
      }
      if ( qword_1400056D8 || v8 != 1 )
        goto LABEL_14;
LABEL_15:
      v12 += 2;
    }
    if ( v13 == qword_1400056D8 )
      return result;
    v8 = dword_1400056E4;
    Buffer = (char *)::Buffer;
LABEL_18:
    if ( (unsigned int)++v9 < 4 )
      continue;
    break;
  }
  *a6 = v13;
  return 0;
}

```

## disassembly

```asm
0x140001dd0  push    rbp
0x140001dd2  push    rbx
0x140001dd3  push    rsi
0x140001dd4  push    rdi
0x140001dd5  push    r12
0x140001dd7  push    r14
0x140001dd9  push    r15
0x140001ddb  mov     rbp, rsp
0x140001dde  sub     rsp, 80h
0x140001de5  xor     r12d, r12d
0x140001de8  mov     [rbp+var_20], rdx
0x140001dec  mov     [rdx], r12w
0x140001df0  mov     r15, rcx
0x140001df3  mov     rcx, qword ptr [rbp+arg_20]
0x140001df7  xorps   xmm0, xmm0
0x140001dfa  mov     edx, cs:dword_1400056E4
0x140001e00  mov     edi, r12d
0x140001e03  movups  [rbp+var_18], xmm0
0x140001e07  mov     [r8], r12w
0x140001e0b  mov     [r9], r12w
0x140001e0f  mov     qword ptr [rbp+var_18+8], r9
0x140001e13  mov     r9, cs:Buffer
0x140001e1a  mov     [rcx], r12w
0x140001e1e  mov     qword ptr [rbp+var_18], r8
0x140001e22  mov     [rbp+var_8], rcx
0x140001e26  mov     eax, edi
0x140001e28  xorps   xmm0, xmm0
0x140001e2b  mov     ecx, edx
0x140001e2d  movups  xmmword ptr [rbp+var_30], xmm0
0x140001e31  mov     qword ptr [rbp+arg_20], r12
0x140001e35  mov     r14, [rbp+rax*8+var_20]
0x140001e3a  mov     rax, cs:qword_1400056D8
0x140001e41  lea     rbx, [r9+rcx*2]
0x140001e45  lea     rsi, [rax+rcx*2]
0x140001e49  cmp     edx, cs:dword_1400056E0
0x140001e4f  jnz     loc_140001F11
0x140001e55  test    r9, r9
0x140001e58  jnz     short loc_140001E88
0x140001e5a  mov     rcx, gs:60h
0x140001e63  xor     edx, edx; Flags
0x140001e65  mov     r8d, 10000h; Size
0x140001e6b  mov     rcx, [rcx+30h]; HeapHandle
0x140001e6f  call    cs:__imp_RtlAllocateHeap
0x140001e75  mov     cs:Buffer, rax
0x140001e7c  mov     r9, rax
0x140001e7f  test    rax, rax
0x140001e82  jz      loc_140001F97
0x140001e88  mov     edx, cs:dword_1400056E0
0x140001e8e  lea     rax, [rbp+arg_20]
0x140001e92  mov     rcx, cs:qword_1400056D8
0x140001e99  mov     [rsp+80h+Key], r12; Key
0x140001e9e  mov     [rsp+80h+ByteOffset], rax; ByteOffset
0x140001ea3  lea     rax, [rbp+var_30]
0x140001ea7  mov     [rsp+80h+Length], 10000h; Length
0x140001eaf  lea     r8, [rcx+rdx*2]
0x140001eb3  mov     [rsp+80h+Buffer], r9; Buffer
0x140001eb8  mov     cs:qword_1400056D8, r8
0x140001ebf  xor     r9d, r9d; ApcContext
0x140001ec2  mov     qword ptr [rbp+arg_20], r8
0x140001ec6  xor     edx, edx; Event
0x140001ec8  xor     r8d, r8d; ApcRoutine
0x140001ecb  mov     cs:dword_1400056E0, r12d
0x140001ed2  mov     rcx, r15; FileHandle
0x140001ed5  mov     cs:dword_1400056E4, r12d
0x140001edc  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x140001ee1  call    cs:__imp_NtReadFile
0x140001ee7  cmp     eax, 0C0000011h
0x140001eec  jz      short loc_140001F5A
0x140001eee  test    eax, eax
0x140001ef0  js      loc_140001F85
0x140001ef6  mov     eax, dword ptr [rbp+var_30.Information]
0x140001ef9  mov     r9, cs:Buffer
0x140001f00  mov     edx, cs:dword_1400056E4
0x140001f06  mov     rbx, r9
0x140001f09  shr     eax, 1
0x140001f0b  mov     cs:dword_1400056E0, eax
0x140001f11  inc     edx
0x140001f13  mov     eax, 0FEFFh
0x140001f18  mov     cs:dword_1400056E4, edx
0x140001f1e  cmp     [rbx], ax
0x140001f21  jnz     short loc_140001F33
0x140001f23  cmp     cs:qword_1400056D8, r12
0x140001f2a  jnz     short loc_140001F39
0x140001f2c  cmp     edx, 1
0x140001f2f  jnz     short loc_140001F39
0x140001f31  jmp     short loc_140001F51
0x140001f33  cmp     [rbx], r12w
0x140001f37  jz      short loc_140001F70
0x140001f39  movzx   edx, word ptr [rbx]
0x140001f3c  mov     rcx, r14
0x140001f3f  call    AddToUnicodeString
0x140001f44  mov     edx, cs:dword_1400056E4
0x140001f4a  mov     r9, cs:Buffer
0x140001f51  add     rbx, 2
0x140001f55  jmp     loc_140001E49
0x140001f5a  cmp     rsi, cs:qword_1400056D8
0x140001f61  jz      short loc_140001F85
0x140001f63  mov     edx, cs:dword_1400056E4
0x140001f69  mov     r9, cs:Buffer
0x140001f70  inc     edi
0x140001f72  cmp     edi, 4
0x140001f75  jb      loc_140001E26
0x140001f7b  mov     rax, [rbp+arg_28]
0x140001f7f  mov     [rax], rsi
0x140001f82  mov     eax, r12d
0x140001f85  add     rsp, 80h
0x140001f8c  pop     r15
0x140001f8e  pop     r14
0x140001f90  pop     r12
0x140001f92  pop     rdi
0x140001f93  pop     rsi
0x140001f94  pop     rbx
0x140001f95  pop     rbp
0x140001f96  retn
0x140001f97  mov     eax, 0C0000017h
0x140001f9c  jmp     short loc_140001F85
```
