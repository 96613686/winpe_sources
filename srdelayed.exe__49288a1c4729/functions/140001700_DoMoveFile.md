# DoMoveFile

- ea: `0x140001700`
- end: `0x140001839`
- name: `DoMoveFile`
- size: `313`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400028a4`

## callees

- `0x140001700`
- `0x1400021d0`
- `0x14000268c`
- `0x14000371d`
- `0x140003770`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140001780`
- `ntdll!RtlAllocateHeap` at `0x140001780`
- `ntdll!NtSetInformationFile` at `0x1400017cb`
- `ntdll!NtSetInformationFile` at `0x1400017cb`
- `ntdll!NtClose` at `0x1400017f3`
- `ntdll!NtClose` at `0x1400017f3`
- `ntdll!RtlFreeHeap` at `0x140001810`
- `ntdll!RtlFreeHeap` at `0x140001810`

## pseudocode

```c
__int64 __fastcall DoMoveFile(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  void *v3; // rbx
  int v4; // edi
  size_t Length; // rdi
  char *Heap; // rax
  HANDLE FileHandle; // [rsp+30h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-60h] BYREF
  _OWORD v10[2]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v11; // [rsp+68h] [rbp-30h]

  FileHandle = 0;
  memset(v10, 0, sizeof(v10));
  v3 = 0;
  v11 = 0;
  IoStatusBlock = 0;
  v4 = MoveDeleteCommon(&FileHandle, a1, a2, v10);
  if ( v4 >= 0 )
  {
    Length = a2->Length;
    Heap = (char *)RtlAllocateHeap(
                     *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                     0,
                     (unsigned int)(Length + 24));
    v3 = Heap;
    if ( Heap )
    {
      *Heap = 1;
      *((_QWORD *)Heap + 1) = 0;
      *((_DWORD *)Heap + 4) = Length;
      memcpy_0(Heap + 20, a2->Buffer, Length);
      v4 = NtSetInformationFile(FileHandle, &IoStatusBlock, v3, Length + 24, FileRenameInformation);
      if ( v4 >= 0 )
        v4 = SetBasicFileInformation(a2, v10);
    }
    else
    {
      v4 = -1073741801;
    }
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v3 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140001700  mov     r11, rsp
0x140001703  mov     [r11+18h], rbx
0x140001707  push    rbp
0x140001708  push    rdi
0x140001709  push    r14
0x14000170b  sub     rsp, 80h
0x140001712  mov     rax, cs:__security_cookie
0x140001719  xor     rax, rsp
0x14000171c  mov     [rsp+98h+var_28], rax
0x140001721  xorps   xmm1, xmm1
0x140001724  mov     qword ptr [r11-68h], 0
0x14000172c  mov     rbp, rdx
0x14000172f  lea     r9, [r11-50h]
0x140001733  mov     r8, rdx
0x140001736  xorps   xmm0, xmm0
0x140001739  mov     rdx, rcx
0x14000173c  xor     eax, eax
0x14000173e  movups  [rsp+98h+var_50], xmm1
0x140001743  lea     rcx, [r11-68h]
0x140001747  xor     ebx, ebx
0x140001749  movups  [rsp+98h+var_40], xmm1
0x14000174e  mov     [r11-30h], rax
0x140001752  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x140001757  call    MoveDeleteCommon
0x14000175c  mov     edi, eax
0x14000175e  test    eax, eax
0x140001760  js      loc_1400017E6
0x140001766  movzx   edi, word ptr [rbp+0]
0x14000176a  xor     edx, edx; Flags
0x14000176c  mov     rcx, gs:60h
0x140001775  lea     r14d, [rdi+18h]
0x140001779  mov     rcx, [rcx+30h]; HeapHandle
0x14000177d  mov     r8d, r14d; Size
0x140001780  call    cs:__imp_RtlAllocateHeap
0x140001786  mov     rbx, rax
0x140001789  test    rax, rax
0x14000178c  jnz     short loc_140001795
0x14000178e  mov     edi, 0C0000017h
0x140001793  jmp     short loc_1400017E6
0x140001795  mov     byte ptr [rax], 1
0x140001798  lea     rcx, [rax+14h]; void *
0x14000179c  mov     qword ptr [rax+8], 0
0x1400017a4  mov     r8, rdi; MaxCount
0x1400017a7  mov     [rax+10h], edi
0x1400017aa  mov     rdx, [rbp+8]; Src
0x1400017ae  call    memcpy_0
0x1400017b3  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x1400017b8  lea     rdx, [rsp+98h+IoStatusBlock]; IoStatusBlock
0x1400017bd  mov     r9d, r14d; Length
0x1400017c0  mov     [rsp+98h+FileInformationClass], 0Ah; FileInformationClass
0x1400017c8  mov     r8, rbx; FileInformation
0x1400017cb  call    cs:__imp_NtSetInformationFile
0x1400017d1  mov     edi, eax
0x1400017d3  test    eax, eax
0x1400017d5  js      short loc_1400017E6
0x1400017d7  lea     rdx, [rsp+98h+var_50]
0x1400017dc  mov     rcx, rbp
0x1400017df  call    SetBasicFileInformation
0x1400017e4  mov     edi, eax
0x1400017e6  cmp     [rsp+98h+FileHandle], 0
0x1400017ec  jz      short loc_1400017F9
0x1400017ee  mov     rcx, [rsp+98h+FileHandle]; Handle
0x1400017f3  call    cs:__imp_NtClose
0x1400017f9  test    rbx, rbx
0x1400017fc  jz      short loc_140001816
0x1400017fe  mov     rcx, gs:60h
0x140001807  mov     r8, rbx; BaseAddress
0x14000180a  xor     edx, edx; Flags
0x14000180c  mov     rcx, [rcx+30h]; HeapHandle
0x140001810  call    cs:__imp_RtlFreeHeap
0x140001816  mov     eax, edi
0x140001818  mov     rcx, [rsp+98h+var_28]
0x14000181d  xor     rcx, rsp; StackCookie
0x140001820  call    __security_check_cookie
0x140001825  mov     rbx, [rsp+98h+arg_10]
0x14000182d  add     rsp, 80h
0x140001834  pop     r14
0x140001836  pop     rdi
0x140001837  pop     rbp
0x140001838  retn
```
