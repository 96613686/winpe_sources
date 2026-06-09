# CASFContentDescriptionObject::SetCopyright(ushort const *)

- ea: `0x180024838`
- end: `0x1800248ef`
- name: `?SetCopyright@CASFContentDescriptionObject@@QEAAJPEBG@Z`
- size: `183`
- prototype: `int(CASFContentDescriptionObject *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180018a30`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x180005060`
- `0x18000774c`
- `0x180024838`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObject::SetCopyright(CASFContentDescriptionObject *this, unsigned __int16 *a2)
{
  unsigned __int64 v3; // rbx
  void *v6; // rcx
  unsigned __int16 *v7; // rax
  int v8; // eax
  unsigned int v9; // ecx
  unsigned __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( (int)StringCchLengthW(a2, 0x7FFEu, &v10) < 0 )
      return 2147942487LL;
    v3 = v10 + 1;
  }
  v6 = (void *)*((_QWORD *)this + 11);
  *((_WORD *)this + 30) = 2 * v3;
  if ( v6 )
  {
    operator delete(v6);
    *((_QWORD *)this + 11) = 0;
  }
  if ( !*((_WORD *)this + 30) )
    return 0;
  v7 = (unsigned __int16 *)operator new[](saturated_mul(v3, 2u));
  *((_QWORD *)this + 11) = v7;
  if ( v7 )
  {
    v8 = StringCchCopyW(v7, v3, a2);
    v9 = 0;
    if ( v8 < 0 )
      return (unsigned int)v8;
    return v9;
  }
  else
  {
    *((_WORD *)this + 30) = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180024838  push    rbx
0x18002483a  push    rbp
0x18002483b  push    rsi
0x18002483c  push    rdi
0x18002483d  sub     rsp, 28h
0x180024841  xor     ebp, ebp
0x180024843  mov     rsi, rdx
0x180024846  mov     ebx, ebp
0x180024848  mov     rdi, rcx
0x18002484b  mov     [rsp+48h+arg_8], rbx
0x180024850  test    rdx, rdx
0x180024853  jz      short loc_18002487A
0x180024855  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x18002485a  mov     edx, 7FFEh; unsigned __int64
0x18002485f  mov     rcx, rsi; unsigned __int16 *
0x180024862  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180024867  test    eax, eax
0x180024869  jns     short loc_180024872
0x18002486b  mov     eax, 80070057h
0x180024870  jmp     short loc_1800248E6
0x180024872  mov     rbx, [rsp+48h+arg_8]
0x180024877  inc     rbx
0x18002487a  mov     rcx, [rdi+58h]; void *
0x18002487e  movzx   eax, bx
0x180024881  add     ax, ax
0x180024884  mov     [rdi+3Ch], ax
0x180024888  test    rcx, rcx
0x18002488b  jz      short loc_180024896
0x18002488d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024892  mov     [rdi+58h], rbp
0x180024896  cmp     [rdi+3Ch], bp
0x18002489a  jz      short loc_1800248E4
0x18002489c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800248a3  mov     eax, 2
0x1800248a8  mul     rbx
0x1800248ab  cmovb   rax, rcx
0x1800248af  mov     rcx, rax; unsigned __int64
0x1800248b2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800248b7  mov     [rdi+58h], rax
0x1800248bb  test    rax, rax
0x1800248be  jnz     short loc_1800248CB
0x1800248c0  mov     [rdi+3Ch], bp
0x1800248c4  mov     eax, 8007000Eh
0x1800248c9  jmp     short loc_1800248E6
0x1800248cb  mov     r8, rsi; unsigned __int16 *
0x1800248ce  mov     rdx, rbx; unsigned __int64
0x1800248d1  mov     rcx, rax; unsigned __int16 *
0x1800248d4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800248d9  test    eax, eax
0x1800248db  mov     ecx, ebp
0x1800248dd  cmovs   ecx, eax
0x1800248e0  mov     eax, ecx
0x1800248e2  jmp     short loc_1800248E6
0x1800248e4  xor     eax, eax
0x1800248e6  add     rsp, 28h
0x1800248ea  pop     rdi
0x1800248eb  pop     rsi
0x1800248ec  pop     rbp
0x1800248ed  pop     rbx
0x1800248ee  retn
```
