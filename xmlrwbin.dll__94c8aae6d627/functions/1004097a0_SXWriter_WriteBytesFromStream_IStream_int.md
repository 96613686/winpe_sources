# SXWriter::WriteBytesFromStream(IStream *,int)

- ea: `0x1004097a0`
- end: `0x100409837`
- name: `?WriteBytesFromStream@SXWriter@@IEAAXPEAUIStream@@H@Z`
- size: `151`
- prototype: `void __fastcall(SXWriter *__hidden this, struct IStream *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1004089c0`
- `0x1004095b0`

## callees

- `0x100401350`
- `0x1004086f0`
- `0x100408840`
- `0x1004097a0`
- `0x100424580`

## pseudocode

```c
void __fastcall SXWriter::WriteBytesFromStream(SXWriter *this, struct IStream *a2, signed int a3)
{
  unsigned int v3; // ebx
  struct IStream *v4; // rdi
  SXWriter *v5; // rsi
  int v6; // eax
  int v7; // [rsp+30h] [rbp-18h] BYREF
  _BYTE v8[16]; // [rsp+38h] [rbp-10h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( a3 <= 2048 )
    goto LABEL_4;
  SXWriter::writeBuffer(this);
  v6 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, int *, _BYTE *))v4->lpVtbl->CopyTo)(
         v4,
         *((_QWORD *)v5 + 15),
         v3,
         &v7,
         v8);
  if ( v6 == -2147467263 )
  {
    a3 = v3;
    a2 = v4;
    this = v5;
LABEL_4:
    _mm_lfence();
    SXWriter::streamXfer(this, a2, a3);
    return;
  }
  if ( v6 || v7 != v3 )
  {
    MXRRaiseException(-2147467259);
    JUMPOUT(0x100409836LL);
  }
}

```

## disassembly

```asm
0x1004097a0  mov     [rsp+arg_0], rbx
0x1004097a5  mov     [rsp+arg_8], rsi
0x1004097aa  push    rdi
0x1004097ab  sub     rsp, 40h
0x1004097af  mov     ebx, r8d
0x1004097b2  mov     rdi, rdx
0x1004097b5  mov     rsi, rcx
0x1004097b8  cmp     r8d, 800h
0x1004097bf  jle     short loc_10040980A
0x1004097c1  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x1004097c6  mov     rax, [rdi]
0x1004097c9  lea     rcx, [rsp+48h+var_10]
0x1004097ce  mov     rdx, [rsi+78h]
0x1004097d2  lea     r9, [rsp+48h+var_18]
0x1004097d7  mov     [rsp+48h+var_28], rcx
0x1004097dc  mov     rcx, rdi
0x1004097df  mov     dword ptr [rsp+48h+arg_18], ebx
0x1004097e3  mov     rax, [rax+38h]
0x1004097e7  mov     dword ptr [rsp+48h+arg_18+4], 0
0x1004097ef  mov     r8, [rsp+48h+arg_18]
0x1004097f4  call    cs:__guard_dispatch_icall_fptr
0x1004097fa  cmp     eax, 80004001h
0x1004097ff  jnz     short loc_100409822
0x100409801  mov     r8d, ebx; unsigned int
0x100409804  mov     rdx, rdi; struct IStream *
0x100409807  mov     rcx, rsi; this
0x10040980a  lfence
0x10040980d  call    ?streamXfer@SXWriter@@AEAAXPEAUIStream@@K@Z; SXWriter::streamXfer(IStream *,ulong)
0x100409812  mov     rbx, [rsp+48h+arg_0]
0x100409817  mov     rsi, [rsp+48h+arg_8]
0x10040981c  add     rsp, 40h
0x100409820  pop     rdi
0x100409821  retn
0x100409822  test    eax, eax
0x100409824  jnz     short loc_10040982C
0x100409826  cmp     [rsp+48h+var_18], ebx
0x10040982a  jz      short loc_100409812
0x10040982c  mov     ecx, 80004005h; int
0x100409831  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
