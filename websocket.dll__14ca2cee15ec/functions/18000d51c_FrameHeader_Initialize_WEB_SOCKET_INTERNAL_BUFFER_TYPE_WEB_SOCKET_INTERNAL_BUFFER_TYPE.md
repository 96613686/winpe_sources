# FrameHeader::Initialize(WEB_SOCKET_INTERNAL_BUFFER_TYPE,WEB_SOCKET_INTERNAL_BUFFER_TYPE)

- ea: `0x18000d51c`
- end: `0x18000d5ff`
- name: `?Initialize@FrameHeader@@QEAAJW4WEB_SOCKET_INTERNAL_BUFFER_TYPE@@0@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c7c0`
- `0x18000cc64`
- `0x18000cef8`
- `0x18000d174`

## callees

- `0x180002578`
- `0x18000d51c`
- `0x18000d608`

## pseudocode

```c
__int64 __fastcall FrameHeader::Initialize(__int64 a1, int a2)
{
  int v4; // r8d
  char v5; // cl
  int v6; // eax
  unsigned int v7; // r8d

  *(_QWORD *)a1 = 0;
  *(_WORD *)(a1 + 8) = 0;
  if ( a2 >= 0 )
  {
    v7 = 0;
    *(_WORD *)a1 = __ROR2__((_WORD)a2 << 7, 8);
    goto LABEL_20;
  }
  if ( !(unsigned int)FrameHeader::IsControl((unsigned int)a2) && ((v4 + 0x7FFFFFFF) & 0xFFFFFFFD) == 0 )
  {
    v5 = 0;
LABEL_17:
    v7 = 0;
LABEL_18:
    *(_BYTE *)a1 = (((a2 + 0x7FFFFFFF) & 0xFFFFFFFD) != 0 ? 0x80 : 0) | v5 & 0x7F | *(_BYTE *)a1 & 0x70;
LABEL_20:
    *(_BYTE *)(a1 + 1) |= 0x7Fu;
    return v7;
  }
  v5 = 1;
  if ( a2 < -2147483646 )
    goto LABEL_17;
  if ( (unsigned int)(a2 + 2147483646) <= 1 )
  {
    v5 = 2;
    goto LABEL_17;
  }
  switch ( a2 )
  {
    case -2147483644:
      v5 = 8;
      goto LABEL_17;
    case -2147483642:
      goto LABEL_14;
    case -1073741824:
      v5 = 9;
      goto LABEL_17;
    case -1073741823:
LABEL_14:
      v5 = 10;
      goto LABEL_17;
  }
  v6 = Trace::Error(-2147024809, 0xD000002D);
  v5 = 0;
  v7 = v6;
  if ( v6 >= 0 )
    goto LABEL_18;
  return v7;
}

```

## disassembly

```asm
0x18000d51c  mov     [rsp+arg_0], rbx
0x18000d521  push    rdi
0x18000d522  sub     rsp, 20h
0x18000d526  xor     eax, eax
0x18000d528  mov     ebx, edx
0x18000d52a  mov     [rcx], rax
0x18000d52d  mov     rdi, rcx
0x18000d530  mov     [rcx+8], ax
0x18000d534  test    edx, 80000000h
0x18000d53a  jbe     loc_18000D5DF
0x18000d540  mov     ecx, edx
0x18000d542  call    ?IsControl@FrameHeader@@SAHW4WEB_SOCKET_INTERNAL_BUFFER_TYPE@@@Z; FrameHeader::IsControl(WEB_SOCKET_INTERNAL_BUFFER_TYPE)
0x18000d547  test    eax, eax
0x18000d549  jnz     short loc_18000D55D
0x18000d54b  lea     eax, [r8+7FFFFFFFh]
0x18000d552  test    eax, 0FFFFFFFDh
0x18000d557  jnz     short loc_18000D55D
0x18000d559  xor     cl, cl
0x18000d55b  jmp     short loc_18000D5BC
0x18000d55d  mov     ecx, 1
0x18000d562  cmp     ebx, 80000002h
0x18000d568  jl      short loc_18000D5BC
0x18000d56a  lea     eax, [rbx+7FFFFFFEh]
0x18000d570  cmp     eax, ecx
0x18000d572  jbe     short loc_18000D5BA
0x18000d574  cmp     ebx, 80000004h
0x18000d57a  jz      short loc_18000D5B6
0x18000d57c  cmp     ebx, 80000006h
0x18000d582  jz      short loc_18000D5B2
0x18000d584  cmp     ebx, 0C0000000h
0x18000d58a  jz      short loc_18000D5AE
0x18000d58c  cmp     ebx, 0C0000001h
0x18000d592  jz      short loc_18000D5B2
0x18000d594  mov     edx, 0D000002Dh; unsigned int
0x18000d599  mov     ecx, 80070057h; int
0x18000d59e  call    ?Error@Trace@@SAJJKZZ; Trace::Error(long,ulong,...)
0x18000d5a3  xor     cl, cl
0x18000d5a5  mov     r8d, eax
0x18000d5a8  test    eax, eax
0x18000d5aa  js      short loc_18000D5F1
0x18000d5ac  jmp     short loc_18000D5BF
0x18000d5ae  mov     cl, 9
0x18000d5b0  jmp     short loc_18000D5BC
0x18000d5b2  mov     cl, 0Ah
0x18000d5b4  jmp     short loc_18000D5BC
0x18000d5b6  mov     cl, 8
0x18000d5b8  jmp     short loc_18000D5BC
0x18000d5ba  mov     cl, 2
0x18000d5bc  xor     r8d, r8d
0x18000d5bf  mov     dl, [rdi]
0x18000d5c1  lea     eax, [rbx+7FFFFFFFh]
0x18000d5c7  and     dl, 0F0h
0x18000d5ca  and     eax, 0FFFFFFFDh
0x18000d5cd  or      dl, cl
0x18000d5cf  neg     eax
0x18000d5d1  sbb     cl, cl
0x18000d5d3  and     dl, 7Fh
0x18000d5d6  and     cl, 80h
0x18000d5d9  or      dl, cl
0x18000d5db  mov     [rdi], dl
0x18000d5dd  jmp     short loc_18000D5ED
0x18000d5df  xor     r8d, r8d
0x18000d5e2  shl     bx, 7
0x18000d5e6  ror     bx, 8
0x18000d5ea  mov     [rcx], bx
0x18000d5ed  or      byte ptr [rdi+1], 7Fh
0x18000d5f1  mov     rbx, [rsp+28h+arg_0]
0x18000d5f6  mov     eax, r8d
0x18000d5f9  add     rsp, 20h
0x18000d5fd  pop     rdi
0x18000d5fe  retn
```
