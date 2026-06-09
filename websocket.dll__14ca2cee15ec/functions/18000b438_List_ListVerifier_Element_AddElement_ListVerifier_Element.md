# List<ListVerifier::Element>::AddElement(ListVerifier::Element *)

- ea: `0x18000b438`
- end: `0x18000b4ee`
- name: `?AddElement@?$List@UElement@ListVerifier@@@@QEAAJPEAUElement@ListVerifier@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800093c4`
- `0x18000aaf0`
- `0x18000ab50`

## callees

- `0x180001234`
- `0x180001274`
- `0x18000b438`
- `0x18000dc00`

## pseudocode

```c
__int64 __fastcall List<ListVerifier::Element>::AddElement(unsigned int *a1, __int64 a2)
{
  unsigned int v2; // eax
  unsigned int v5; // edi
  void *v6; // rsi
  const void *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax

  v2 = *a1;
  if ( a1[1] != *a1 )
  {
LABEL_11:
    v9 = 3LL * a1[1];
    v10 = *((_QWORD *)a1 + 1);
    *(_OWORD *)(v10 + 8 * v9) = *(_OWORD *)a2;
    *(_QWORD *)(v10 + 8 * v9 + 16) = *(_QWORD *)(a2 + 16);
    ++a1[1];
    return 0;
  }
  if ( !v2 )
  {
    v5 = 4;
LABEL_6:
    v6 = operator new(saturated_mul(v5, 0x18u));
    if ( !v6 )
      return 2147942414LL;
    v8 = (const void *)*((_QWORD *)a1 + 1);
    if ( v8 )
    {
      memcpy_0(v6, v8, 24LL * *a1);
      operator delete(*((void **)a1 + 1));
    }
    *a1 = v5;
    *((_QWORD *)a1 + 1) = v6;
    goto LABEL_11;
  }
  if ( v2 <= 0x7FFFFFFF )
  {
    v5 = 2 * v2;
    goto LABEL_6;
  }
  return 2147942934LL;
}

```

## disassembly

```asm
0x18000b438  push    rbx
0x18000b43a  push    rbp
0x18000b43b  push    rsi
0x18000b43c  push    rdi
0x18000b43d  sub     rsp, 28h
0x18000b441  mov     eax, [rcx]
0x18000b443  mov     rbp, rdx
0x18000b446  mov     rbx, rcx
0x18000b449  cmp     [rcx+4], eax
0x18000b44c  jnz     short loc_18000B4BB
0x18000b44e  test    eax, eax
0x18000b450  jnz     short loc_18000B457
0x18000b452  lea     edi, [rax+4]
0x18000b455  jmp     short loc_18000B465
0x18000b457  cmp     eax, 7FFFFFFFh
0x18000b45c  ja      loc_18000B4E7
0x18000b462  lea     edi, [rax+rax]
0x18000b465  mov     ecx, edi
0x18000b467  mov     eax, 18h
0x18000b46c  mul     rcx
0x18000b46f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b476  cmovb   rax, rcx
0x18000b47a  mov     rcx, rax; Size
0x18000b47d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b482  mov     rsi, rax
0x18000b485  test    rax, rax
0x18000b488  jnz     short loc_18000B491
0x18000b48a  mov     eax, 8007000Eh
0x18000b48f  jmp     short loc_18000B4DE
0x18000b491  mov     rdx, [rbx+8]; Src
0x18000b495  test    rdx, rdx
0x18000b498  jz      short loc_18000B4B5
0x18000b49a  mov     eax, [rbx]
0x18000b49c  mov     rcx, rsi; void *
0x18000b49f  lea     r8, [rax+rax*2]
0x18000b4a3  shl     r8, 3; Size
0x18000b4a7  call    memcpy_0
0x18000b4ac  mov     rcx, [rbx+8]; Block
0x18000b4b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b4b5  mov     [rbx], edi
0x18000b4b7  mov     [rbx+8], rsi
0x18000b4bb  mov     eax, [rbx+4]
0x18000b4be  movups  xmm0, xmmword ptr [rbp+0]
0x18000b4c2  lea     rcx, [rax+rax*2]
0x18000b4c6  mov     rax, [rbx+8]
0x18000b4ca  movups  xmmword ptr [rax+rcx*8], xmm0
0x18000b4ce  movsd   xmm1, qword ptr [rbp+10h]
0x18000b4d3  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x18000b4d9  inc     dword ptr [rbx+4]
0x18000b4dc  xor     eax, eax
0x18000b4de  add     rsp, 28h
0x18000b4e2  pop     rdi
0x18000b4e3  pop     rsi
0x18000b4e4  pop     rbp
0x18000b4e5  pop     rbx
0x18000b4e6  retn
0x18000b4e7  mov     eax, 80070216h
0x18000b4ec  jmp     short loc_18000B4DE
```
