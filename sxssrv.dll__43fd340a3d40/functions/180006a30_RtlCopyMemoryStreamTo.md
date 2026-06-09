# RtlCopyMemoryStreamTo

- ea: `0x180006a30`
- end: `0x180006aa9`
- name: `RtlCopyMemoryStreamTo`
- size: `121`
- prototype: `HRESULT __stdcall(struct IStream *This, struct IStream *Target, ULARGE_INTEGER Length, PULARGE_INTEGER BytesRead, PULARGE_INTEGER BytesWritten)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006a30`
- `0x180008010`

## pseudocode

```c
HRESULT __stdcall RtlCopyMemoryStreamTo(
        struct IStream *This,
        struct IStream *Target,
        ULARGE_INTEGER Length,
        PULARGE_INTEGER BytesRead,
        PULARGE_INTEGER BytesWritten)
{
  __int64 v6; // rdx
  unsigned __int64 v7; // r11
  ULONGLONG v9; // rcx
  PULARGE_INTEGER v10; // rax
  unsigned int v12; // [rsp+40h] [rbp+8h] BYREF

  v6 = *((_QWORD *)This + 2);
  v7 = *((_QWORD *)This + 4) - v6;
  v12 = 0;
  if ( Length.HighPart )
    Length.LowPart = -1;
  if ( v7 >= Length.LowPart )
    LODWORD(v7) = Length.LowPart;
  if ( (*(int (__fastcall **)(struct IStream *, __int64, _QWORD, unsigned int *))(*(_QWORD *)Target + 32LL))(
         Target,
         v6,
         (unsigned int)v7,
         &v12) >= 0 )
    v9 = v12;
  else
    v9 = 0;
  v10 = BytesWritten;
  BytesRead->QuadPart = v9;
  v10->QuadPart = v9;
  return 0;
}

```

## disassembly

```asm
0x180006a30  mov     [rsp+arg_8], rbx
0x180006a35  push    rdi
0x180006a36  sub     rsp, 30h
0x180006a3a  mov     r11, [rcx+20h]
0x180006a3e  mov     rbx, rdx
0x180006a41  mov     rdx, [rcx+10h]
0x180006a45  mov     rax, r8
0x180006a48  shr     rax, 20h
0x180006a4c  or      ecx, 0FFFFFFFFh
0x180006a4f  sub     r11, rdx
0x180006a52  mov     [rsp+38h+arg_0], 0
0x180006a5a  mov     r10, [rbx]
0x180006a5d  test    eax, eax
0x180006a5f  mov     rdi, r9
0x180006a62  lea     r9, [rsp+38h+arg_0]
0x180006a67  cmovnz  r8d, ecx
0x180006a6b  mov     rcx, rbx
0x180006a6e  mov     eax, r8d
0x180006a71  cmp     r11, rax
0x180006a74  mov     rax, [r10+20h]
0x180006a78  cmovnb  r11d, r8d
0x180006a7c  mov     r8d, r11d
0x180006a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a84  test    eax, eax
0x180006a86  jns     short loc_180006A8C
0x180006a88  xor     ecx, ecx
0x180006a8a  jmp     short loc_180006A90
0x180006a8c  mov     ecx, [rsp+38h+arg_0]
0x180006a90  mov     rax, [rsp+38h+BytesWritten]
0x180006a95  mov     [rdi], rcx
0x180006a98  mov     [rax], rcx
0x180006a9b  xor     eax, eax
0x180006a9d  mov     rbx, [rsp+38h+arg_8]
0x180006aa2  add     rsp, 30h
0x180006aa6  pop     rdi
0x180006aa7  retn
```
