# Windows::StringUtil::TrimLongPathPrefix<_LUNICODE_STRING>(_LUNICODE_STRING const &)

- ea: `0x1800169d0`
- end: `0x180016a56`
- name: `??$TrimLongPathPrefix@U_LUNICODE_STRING@@@StringUtil@Windows@@YA?AU_LUNICODE_STRING@@AEBU2@@Z`
- size: `134`
- prototype: `__int64 __fastcall(__int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016a5c`

## callees

- `0x1800169d0`
- `0x1800179a1`

## pseudocode

```c
__int64 __fastcall Windows::StringUtil::TrimLongPathPrefix<_LUNICODE_STRING>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rbx
  char *v4; // rbp
  char v6; // cl

  v2 = *a2;
  v3 = a2[1];
  v4 = (char *)a2[2];
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  if ( a1 )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  if ( v2 < 8 )
    goto LABEL_9;
  if ( !memcmp_0(v4, L"\\\\?\\", 8u) )
  {
    v6 = 1;
    if ( a1 )
    {
      *(_QWORD *)(a1 + 8) = v2 - 8;
      *(_QWORD *)a1 = v2 - 8;
      *(_QWORD *)(a1 + 16) = v4 + 8;
    }
  }
  else
  {
    v6 = 0;
  }
  if ( !v6 )
  {
LABEL_9:
    *(_QWORD *)a1 = v2;
    *(_QWORD *)(a1 + 8) = v3;
    *(_QWORD *)(a1 + 16) = v4;
  }
  return a1;
}

```

## disassembly

```asm
0x1800169d0  push    rbx
0x1800169d2  push    rbp
0x1800169d3  push    rsi
0x1800169d4  push    rdi
0x1800169d5  sub     rsp, 28h
0x1800169d9  mov     rsi, [rdx]
0x1800169dc  xor     eax, eax
0x1800169de  mov     rbx, [rdx+8]
0x1800169e2  xorps   xmm0, xmm0
0x1800169e5  mov     rbp, [rdx+10h]
0x1800169e9  mov     rdi, rcx
0x1800169ec  movups  xmmword ptr [rcx], xmm0
0x1800169ef  mov     [rcx+10h], rax
0x1800169f3  test    rcx, rcx
0x1800169f6  jz      short loc_1800169FF
0x1800169f8  movups  xmmword ptr [rcx], xmm0
0x1800169fb  mov     [rcx+10h], rax
0x1800169ff  mov     r8d, 8; Size
0x180016a05  cmp     rsi, r8
0x180016a08  jb      short loc_180016A3F
0x180016a0a  lea     rdx, asc_18001E758; "\\\\?\\"
0x180016a11  mov     rcx, rbp; Buf1
0x180016a14  call    memcmp_0
0x180016a19  test    eax, eax
0x180016a1b  jnz     short loc_180016A39
0x180016a1d  mov     cl, 1
0x180016a1f  test    rdi, rdi
0x180016a22  jz      short loc_180016A3B
0x180016a24  lea     rax, [rsi-8]
0x180016a28  mov     [rdi+8], rax
0x180016a2c  mov     [rdi], rax
0x180016a2f  lea     rax, [rbp+8]
0x180016a33  mov     [rdi+10h], rax
0x180016a37  jmp     short loc_180016A3B
0x180016a39  xor     cl, cl
0x180016a3b  test    cl, cl
0x180016a3d  jnz     short loc_180016A4A
0x180016a3f  mov     [rdi], rsi
0x180016a42  mov     [rdi+8], rbx
0x180016a46  mov     [rdi+10h], rbp
0x180016a4a  mov     rax, rdi
0x180016a4d  add     rsp, 28h
0x180016a51  pop     rdi
0x180016a52  pop     rsi
0x180016a53  pop     rbp
0x180016a54  pop     rbx
0x180016a55  retn
```
