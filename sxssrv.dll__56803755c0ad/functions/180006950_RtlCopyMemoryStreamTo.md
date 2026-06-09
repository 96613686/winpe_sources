# RtlCopyMemoryStreamTo

- ea: `0x180006950`
- end: `0x1800069c3`
- name: `RtlCopyMemoryStreamTo`
- size: `115`
- prototype: `HRESULT __stdcall(struct IStream *This, struct IStream *Target, ULARGE_INTEGER Length, PULARGE_INTEGER BytesRead, PULARGE_INTEGER BytesWritten)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006950`
- `0x180007010`

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
  unsigned __int64 v7; // r10
  ULONGLONG v8; // rbx
  PULARGE_INTEGER v10; // rax
  unsigned int v12; // [rsp+40h] [rbp+8h] BYREF

  v6 = *((_QWORD *)This + 2);
  v7 = *((_QWORD *)This + 4) - v6;
  v8 = 0;
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
    v8 = v12;
  v10 = BytesWritten;
  BytesRead->QuadPart = v8;
  v10->QuadPart = v8;
  return 0;
}

```

## disassembly

```asm
0x180006950  mov     [rsp+arg_8], rbx
0x180006955  push    rdi
0x180006956  sub     rsp, 30h
0x18000695a  mov     r10, [rcx+20h]
0x18000695e  mov     r11, rdx
0x180006961  mov     rdx, [rcx+10h]
0x180006965  mov     rax, r8
0x180006968  or      ecx, 0FFFFFFFFh
0x18000696b  shr     rax, 20h
0x18000696f  sub     r10, rdx
0x180006972  xor     ebx, ebx
0x180006974  test    eax, eax
0x180006976  mov     [rsp+38h+arg_0], ebx
0x18000697a  mov     rdi, r9
0x18000697d  lea     r9, [rsp+38h+arg_0]
0x180006982  cmovnz  r8d, ecx
0x180006986  mov     rcx, [r11]
0x180006989  mov     eax, r8d
0x18000698c  cmp     r10, rax
0x18000698f  mov     rax, [rcx+20h]
0x180006993  cmovnb  r10d, r8d
0x180006997  mov     r8d, r10d
0x18000699a  mov     rcx, r11
0x18000699d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069a2  test    eax, eax
0x1800069a4  js      short loc_1800069AA
0x1800069a6  mov     ebx, [rsp+38h+arg_0]
0x1800069aa  mov     rax, [rsp+38h+BytesWritten]
0x1800069af  mov     [rdi], rbx
0x1800069b2  mov     [rax], rbx
0x1800069b5  xor     eax, eax
0x1800069b7  mov     rbx, [rsp+38h+arg_8]
0x1800069bc  add     rsp, 30h
0x1800069c0  pop     rdi
0x1800069c1  retn
```
