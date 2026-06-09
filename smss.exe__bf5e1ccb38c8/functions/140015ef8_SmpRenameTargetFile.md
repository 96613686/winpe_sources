# SmpRenameTargetFile

- ea: `0x140015ef8`
- end: `0x140016012`
- name: `SmpRenameTargetFile`
- size: `282`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x140015ae8`
- `0x140016018`
- `0x140016958`
- `0x140016b94`

## callees

- `0x1400130f4`
- `0x140015ef8`
- `0x14001cc11`
- `0x14001cc29`

## import_xrefs

- `ntdll!NtClose` at `0x140015ff9`
- `ntdll!NtClose` at `0x140015ff9`
- `ntdll!RtlAllocateHeap` at `0x140015f47`
- `ntdll!RtlAllocateHeap` at `0x140015f47`
- `ntdll!RtlFreeHeap` at `0x140015fea`
- `ntdll!RtlFreeHeap` at `0x140015fea`
- `ntdll!NtSetInformationFile` at `0x140015fd0`
- `ntdll!NtSetInformationFile` at `0x140015fd0`

## pseudocode

```c
__int64 __fastcall SmpRenameTargetFile(const void **a1, void *a2, int a3, char a4)
{
  ULONG v5; // r14d
  __int64 v6; // rcx
  __int64 v9; // rbx
  _BYTE *Heap; // rsi
  unsigned int v12; // edi
  char v13; // al
  unsigned int v14; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-58h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+8h] BYREF

  v5 = *(unsigned __int16 *)a1 + 26;
  IoStatusBlock = 0;
  v6 = *(_QWORD *)&KeGetPcr()->MajorVersion;
  v9 = -1;
  Handle = (HANDLE)-1LL;
  Heap = RtlAllocateHeap(*(PVOID *)(v6 + 48), SmBaseTag, v5);
  if ( Heap )
  {
    if ( !a4 || (v13 = SmpCheckFolderForRedirections(a1, &Handle), v9 = (__int64)Handle, v13) )
    {
      memset_0(Heap, 0, v5);
      *((_QWORD *)Heap + 1) = 0;
      *Heap = a3 != 0;
      v14 = *(unsigned __int16 *)a1;
      *((_DWORD *)Heap + 4) = v14;
      memcpy_0(Heap + 20, a1[1], v14);
      v12 = NtSetInformationFile(a2, &IoStatusBlock, Heap, v5, FileRenameInformation);
    }
    else
    {
      v12 = -1073740533;
    }
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Heap);
    if ( v9 != -1 )
      NtClose((HANDLE)v9);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v12;
}

```

## disassembly

```asm
0x140015ef8  mov     rax, rsp
0x140015efb  push    rbx
0x140015efc  push    rbp
0x140015efd  push    rsi
0x140015efe  push    rdi
0x140015eff  push    r12
0x140015f01  push    r13
0x140015f03  push    r14
0x140015f05  push    r15
0x140015f07  sub     rsp, 48h
0x140015f0b  movzx   r14d, word ptr [rcx]
0x140015f0f  mov     rdi, rcx
0x140015f12  xorps   xmm0, xmm0
0x140015f15  add     r14d, 1Ah
0x140015f19  movups  xmmword ptr [rax-58h], xmm0
0x140015f1d  mov     rcx, gs:60h
0x140015f26  mov     r12d, r8d
0x140015f29  mov     r13, rdx
0x140015f2c  mov     r8d, r14d; Size
0x140015f2f  mov     edx, cs:SmBaseTag; Flags
0x140015f35  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140015f39  mov     bpl, r9b
0x140015f3c  mov     [rax+8], rbx
0x140015f40  mov     rcx, [rcx+30h]; HeapHandle
0x140015f44  mov     r15d, r14d
0x140015f47  call    cs:__imp_RtlAllocateHeap
0x140015f4d  mov     rsi, rax
0x140015f50  test    rax, rax
0x140015f53  jnz     short loc_140015F5F
0x140015f55  mov     edi, 0C0000017h
0x140015f5a  jmp     loc_140015FFF
0x140015f5f  test    bpl, bpl
0x140015f62  jz      short loc_140015F87
0x140015f64  lea     rdx, [rsp+88h+Handle]
0x140015f6c  mov     rcx, rdi
0x140015f6f  call    SmpCheckFolderForRedirections
0x140015f74  mov     rbx, [rsp+88h+Handle]
0x140015f7c  test    al, al
0x140015f7e  jnz     short loc_140015F87
0x140015f80  mov     edi, 0C000050Bh
0x140015f85  jmp     short loc_140015FD8
0x140015f87  mov     r8, r15; Size
0x140015f8a  xor     edx, edx; Val
0x140015f8c  mov     rcx, rsi; void *
0x140015f8f  call    memset_0
0x140015f94  mov     qword ptr [rsi+8], 0
0x140015f9c  lea     rcx, [rsi+14h]; void *
0x140015fa0  test    r12d, r12d
0x140015fa3  setnz   al
0x140015fa6  mov     [rsi], al
0x140015fa8  movzx   eax, word ptr [rdi]
0x140015fab  mov     [rsi+10h], eax
0x140015fae  mov     r8d, eax; MaxCount
0x140015fb1  mov     rdx, [rdi+8]; Src
0x140015fb5  call    memcpy_0
0x140015fba  mov     r9d, r14d; Length
0x140015fbd  mov     [rsp+88h+FileInformationClass], 0Ah; FileInformationClass
0x140015fc5  mov     r8, rsi; FileInformation
0x140015fc8  lea     rdx, [rsp+88h+IoStatusBlock]; IoStatusBlock
0x140015fcd  mov     rcx, r13; FileHandle
0x140015fd0  call    cs:__imp_NtSetInformationFile
0x140015fd6  mov     edi, eax
0x140015fd8  mov     rcx, gs:60h
0x140015fe1  mov     r8, rsi; BaseAddress
0x140015fe4  xor     edx, edx; Flags
0x140015fe6  mov     rcx, [rcx+30h]; HeapHandle
0x140015fea  call    cs:__imp_RtlFreeHeap
0x140015ff0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140015ff4  jz      short loc_140015FFF
0x140015ff6  mov     rcx, rbx; Handle
0x140015ff9  call    cs:__imp_NtClose
0x140015fff  mov     eax, edi
0x140016001  add     rsp, 48h
0x140016005  pop     r15
0x140016007  pop     r14
0x140016009  pop     r13
0x14001600b  pop     r12
0x14001600d  pop     rdi
0x14001600e  pop     rsi
0x14001600f  pop     rbp
0x140016010  pop     rbx
0x140016011  retn
```
