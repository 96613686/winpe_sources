# GenerateDeleteAltName

- ea: `0x140001afc`
- end: `0x140001dc9`
- name: `GenerateDeleteAltName`
- size: `717`
- prototype: `__int64 __fastcall(HANDLE FileHandle, _BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1400028a4`

## callees

- `0x14000127c`
- `0x140001afc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140001baf`
- `ntdll!RtlAllocateHeap` at `0x140001baf`
- `ntdll!NtWriteFile` at `0x140001c98`
- `ntdll!NtWriteFile` at `0x140001d11`
- `ntdll!NtWriteFile` at `0x140001c98`
- `ntdll!NtWriteFile` at `0x140001d11`
- `ntdll!RtlReAllocateHeap` at `0x140001bba`
- `ntdll!RtlReAllocateHeap` at `0x140001bba`
- `ntdll!RtlFreeHeap` at `0x140001d79`
- `ntdll!RtlFreeHeap` at `0x140001d99`
- `ntdll!RtlFreeHeap` at `0x140001d79`
- `ntdll!RtlFreeHeap` at `0x140001d99`

## pseudocode

```c
__int64 __fastcall GenerateDeleteAltName(HANDLE FileHandle, _BYTE *a2)
{
  NTSTATUS v3; // ebx
  char *Buffer; // rsi
  PVOID *v5; // r14
  union _LARGE_INTEGER v6; // rdi
  ULONG v7; // r13d
  ULONG Length; // r12d
  void *v9; // rcx
  char *Heap; // rax
  PVOID *v11; // r8
  PVOID *v12; // rdi
  _QWORD *v13; // rax
  PVOID *v14; // rcx
  char *v16; // [rsp+50h] [rbp-20h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-18h] BYREF
  __int64 v19; // [rsp+C0h] [rbp+50h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+C8h] [rbp+58h] BYREF

  ByteOffset.QuadPart = 0;
  v19 = 0;
  IoStatusBlock = 0;
  if ( FileHandle && a2 )
  {
    if ( g_fDelayedList == &g_fDelayedList )
    {
      v3 = 0;
      *a2 = 0;
    }
    else
    {
      Buffer = 0;
      v5 = (PVOID *)g_fDelayedList;
      v6.QuadPart = qword_1400056D8 - 2;
      v7 = 0;
      qword_1400056D8 -= 2;
      do
      {
        Length = *((unsigned __int16 *)v5 + 8) + 64;
        if ( Length > v7 )
        {
          v9 = *(void **)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL);
          if ( Buffer )
            Heap = (char *)RtlReAllocateHeap(v9, 0, Buffer, Length);
          else
            Heap = (char *)RtlAllocateHeap(v9, 0, Length);
          if ( !Heap )
          {
            v3 = -1073741801;
            goto LABEL_20;
          }
          v6.QuadPart = qword_1400056D8;
          Buffer = Heap;
          v7 = Length;
        }
        v16 = &Buffer[v7];
        v3 = Add2Entry(Buffer, &c_ucsDeleteFile, v16, &v19);
        if ( v3 < 0 )
          goto LABEL_20;
        v3 = Add2Entry(v19, &c_ucsAltName, v16, &v19);
        if ( v3 < 0 )
          goto LABEL_20;
        v3 = Add2Entry(v19, v5 + 2, v16, &v19);
        if ( v3 < 0 )
          goto LABEL_20;
        v3 = Add2Entry(v19, &c_ucsNotExecuted, v16, &v19);
        if ( v3 < 0 )
          goto LABEL_20;
        ByteOffset = v6;
        v3 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
        if ( v3 < 0 )
          goto LABEL_20;
        v5 = (PVOID *)*v5;
        v6.QuadPart = LODWORD(IoStatusBlock.Information) + qword_1400056D8;
        qword_1400056D8 = v6.QuadPart;
      }
      while ( v5 != &g_fDelayedList );
      ByteOffset = v6;
      v3 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, &qword_140004350, 2u, &ByteOffset, 0);
      if ( v3 >= 0 )
      {
        qword_1400056D8 += LODWORD(IoStatusBlock.Information);
        *a2 = 1;
      }
LABEL_20:
      if ( Buffer )
      {
        v11 = (PVOID *)Buffer;
        goto LABEL_28;
      }
    }
  }
  else
  {
    v3 = -1073741811;
  }
  while ( 1 )
  {
    v12 = (PVOID *)g_fDelayedList;
    if ( g_fDelayedList == &g_fDelayedList )
      break;
    v13 = *(_QWORD **)g_fDelayedList;
    if ( *(PVOID *)(*(_QWORD *)g_fDelayedList + 8LL) != g_fDelayedList
      || (v14 = (PVOID *)*((_QWORD *)g_fDelayedList + 1), *v14 != g_fDelayedList) )
    {
      __fastfail(3u);
    }
    *v14 = v13;
    v13[1] = v14;
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v12[3]);
    v11 = v12;
    v12[3] = 0;
LABEL_28:
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v11);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140001afc  mov     [rsp-38h+arg_8], rbx
0x140001b01  mov     [rsp-38h+FileHandle], rcx
0x140001b06  push    rbp
0x140001b07  push    rsi
0x140001b08  push    rdi
0x140001b09  push    r12
0x140001b0b  push    r13
0x140001b0d  push    r14
0x140001b0f  push    r15
0x140001b11  mov     rbp, rsp
0x140001b14  sub     rsp, 70h
0x140001b18  mov     rax, rcx
0x140001b1b  mov     qword ptr [rbp+arg_18], 0
0x140001b23  mov     [rbp+arg_10], 0
0x140001b2b  xorps   xmm0, xmm0
0x140001b2e  lea     rcx, g_fDelayedList
0x140001b35  mov     r15, rdx
0x140001b38  movups  xmmword ptr [rbp+var_18], xmm0
0x140001b3c  test    rax, rax
0x140001b3f  jz      loc_140001D3C
0x140001b45  test    rdx, rdx
0x140001b48  jz      loc_140001D3C
0x140001b4e  cmp     cs:g_fDelayedList, rcx
0x140001b55  jnz     short loc_140001B60
0x140001b57  xor     ebx, ebx
0x140001b59  mov     [rdx], bl
0x140001b5b  jmp     loc_140001D41
0x140001b60  mov     rdi, cs:qword_1400056D8
0x140001b67  xor     esi, esi
0x140001b69  mov     r14, cs:g_fDelayedList
0x140001b70  sub     rdi, 2
0x140001b74  xor     r13d, r13d
0x140001b77  mov     cs:qword_1400056D8, rdi
0x140001b7e  cmp     r14, rcx
0x140001b81  jz      loc_140001CD3
0x140001b87  movzx   r12d, word ptr [r14+10h]
0x140001b8c  add     r12d, 40h ; '@'
0x140001b90  cmp     r12d, r13d
0x140001b93  jbe     short loc_140001BD6
0x140001b95  mov     rax, gs:60h
0x140001b9e  xor     edx, edx; Flags
0x140001ba0  mov     r9d, r12d; Size
0x140001ba3  mov     rcx, [rax+30h]; Heap
0x140001ba7  test    rsi, rsi
0x140001baa  jnz     short loc_140001BB7
0x140001bac  mov     r8d, r9d; Size
0x140001baf  call    cs:__imp_RtlAllocateHeap
0x140001bb5  jmp     short loc_140001BC0
0x140001bb7  mov     r8, rsi; Ptr
0x140001bba  call    cs:__imp_RtlReAllocateHeap
0x140001bc0  test    rax, rax
0x140001bc3  jz      loc_140001D35
0x140001bc9  mov     rdi, cs:qword_1400056D8
0x140001bd0  mov     rsi, rax
0x140001bd3  mov     r13d, r12d
0x140001bd6  mov     eax, r13d
0x140001bd9  lea     r9, [rbp+arg_10]
0x140001bdd  add     rax, rsi
0x140001be0  lea     rdx, c_ucsDeleteFile
0x140001be7  mov     r8, rax
0x140001bea  mov     [rbp+var_20], rax
0x140001bee  mov     rcx, rsi
0x140001bf1  call    Add2Entry
0x140001bf6  mov     ebx, eax
0x140001bf8  test    eax, eax
0x140001bfa  js      loc_140001D2B
0x140001c00  mov     r8, [rbp+var_20]
0x140001c04  lea     r9, [rbp+arg_10]
0x140001c08  mov     rcx, [rbp+arg_10]
0x140001c0c  lea     rdx, c_ucsAltName
0x140001c13  call    Add2Entry
0x140001c18  mov     ebx, eax
0x140001c1a  test    eax, eax
0x140001c1c  js      loc_140001D2B
0x140001c22  mov     r8, [rbp+var_20]
0x140001c26  lea     r9, [rbp+arg_10]
0x140001c2a  mov     rcx, [rbp+arg_10]
0x140001c2e  lea     rdx, [r14+10h]
0x140001c32  call    Add2Entry
0x140001c37  mov     ebx, eax
0x140001c39  test    eax, eax
0x140001c3b  js      loc_140001D2B
0x140001c41  mov     r8, [rbp+var_20]
0x140001c45  lea     r9, [rbp+arg_10]
0x140001c49  mov     rcx, [rbp+arg_10]
0x140001c4d  lea     rdx, c_ucsNotExecuted
0x140001c54  call    Add2Entry
0x140001c59  mov     ebx, eax
0x140001c5b  test    eax, eax
0x140001c5d  js      loc_140001D2B
0x140001c63  mov     rcx, [rbp+FileHandle]; FileHandle
0x140001c67  lea     rax, [rbp+arg_18]
0x140001c6b  mov     [rsp+70h+Key], 0; Key
0x140001c74  xor     r9d, r9d; ApcContext
0x140001c77  mov     [rsp+70h+ByteOffset], rax; ByteOffset
0x140001c7c  xor     r8d, r8d; ApcRoutine
0x140001c7f  mov     [rsp+70h+Length], r12d; Length
0x140001c84  lea     rax, [rbp+var_18]
0x140001c88  mov     [rsp+70h+Buffer], rsi; Buffer
0x140001c8d  xor     edx, edx; Event
0x140001c8f  mov     [rsp+70h+IoStatusBlock], rax; IoStatusBlock
0x140001c94  mov     qword ptr [rbp+arg_18], rdi
0x140001c98  call    cs:__imp_NtWriteFile
0x140001c9e  mov     ebx, eax
0x140001ca0  test    eax, eax
0x140001ca2  js      loc_140001D2B
0x140001ca8  mov     eax, dword ptr [rbp+var_18.Information]
0x140001cab  mov     rdi, cs:qword_1400056D8
0x140001cb2  mov     r14, [r14]
0x140001cb5  add     rdi, rax
0x140001cb8  lea     rax, g_fDelayedList
0x140001cbf  mov     cs:qword_1400056D8, rdi
0x140001cc6  cmp     r14, rax
0x140001cc9  jnz     loc_140001B87
0x140001ccf  mov     rax, [rbp+FileHandle]
0x140001cd3  mov     [rsp+70h+Key], 0; Key
0x140001cdc  lea     rcx, [rbp+arg_18]
0x140001ce0  mov     [rsp+70h+ByteOffset], rcx; ByteOffset
0x140001ce5  xor     r9d, r9d; ApcContext
0x140001ce8  lea     rcx, qword_140004350
0x140001cef  mov     [rsp+70h+Length], 2; Length
0x140001cf7  mov     [rsp+70h+Buffer], rcx; Buffer
0x140001cfc  xor     r8d, r8d; ApcRoutine
0x140001cff  lea     rcx, [rbp+var_18]
0x140001d03  mov     qword ptr [rbp+arg_18], rdi
0x140001d07  mov     [rsp+70h+IoStatusBlock], rcx; IoStatusBlock
0x140001d0c  xor     edx, edx; Event
0x140001d0e  mov     rcx, rax; FileHandle
0x140001d11  call    cs:__imp_NtWriteFile
0x140001d17  mov     ebx, eax
0x140001d19  test    eax, eax
0x140001d1b  js      short loc_140001D2B
0x140001d1d  mov     eax, dword ptr [rbp+var_18.Information]
0x140001d20  add     cs:qword_1400056D8, rax
0x140001d27  mov     byte ptr [r15], 1
0x140001d2b  test    rsi, rsi
0x140001d2e  jz      short loc_140001D9F
0x140001d30  mov     r8, rsi
0x140001d33  jmp     short loc_140001D8A
0x140001d35  mov     ebx, 0C0000017h
0x140001d3a  jmp     short loc_140001D2B
0x140001d3c  mov     ebx, 0C000000Dh
0x140001d41  mov     rdi, cs:g_fDelayedList
0x140001d48  cmp     rdi, rcx
0x140001d4b  jz      short loc_140001DAF
0x140001d4d  mov     rax, [rdi]
0x140001d50  cmp     [rax+8], rdi
0x140001d54  jnz     short loc_140001DA8
0x140001d56  mov     rcx, [rdi+8]
0x140001d5a  cmp     [rcx], rdi
0x140001d5d  jnz     short loc_140001DA8
0x140001d5f  mov     [rcx], rax
0x140001d62  xor     edx, edx; Flags
0x140001d64  mov     [rax+8], rcx
0x140001d68  mov     rcx, gs:60h
0x140001d71  mov     r8, [rdi+18h]; BaseAddress
0x140001d75  mov     rcx, [rcx+30h]; HeapHandle
0x140001d79  call    cs:__imp_RtlFreeHeap
0x140001d7f  mov     r8, rdi; BaseAddress
0x140001d82  mov     qword ptr [rdi+18h], 0
0x140001d8a  mov     rcx, gs:60h
0x140001d93  xor     edx, edx; Flags
0x140001d95  mov     rcx, [rcx+30h]; HeapHandle
0x140001d99  call    cs:__imp_RtlFreeHeap
0x140001d9f  lea     rcx, g_fDelayedList
0x140001da6  jmp     short loc_140001D41
0x140001da8  mov     ecx, 3
0x140001dad  int     29h; Win8: RtlFailFast(ecx)
0x140001daf  mov     eax, ebx
0x140001db1  mov     rbx, [rsp+70h+arg_8]
0x140001db9  add     rsp, 70h
0x140001dbd  pop     r15
0x140001dbf  pop     r14
0x140001dc1  pop     r13
0x140001dc3  pop     r12
0x140001dc5  pop     rdi
0x140001dc6  pop     rsi
0x140001dc7  pop     rbp
0x140001dc8  retn
```
