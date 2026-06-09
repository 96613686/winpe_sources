# CAttribSetInResult::Deserialize(uchar * &,uchar *)

- ea: `0x18000ea18`
- end: `0x18000eb09`
- name: `?Deserialize@CAttribSetInResult@@QEAAJAEAPEAEPEAE@Z`
- size: `241`
- prototype: `int(CAttribSetInResult *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000b208`

## callees

- `0x180002ec0`
- `0x180002ecc`
- `0x180008f2c`
- `0x18000e9a0`
- `0x18000ea18`

## pseudocode

```c
__int64 __fastcall CAttribSetInResult::Deserialize(CAttribSetInResult *this, unsigned __int8 **a2, unsigned __int8 *a3)
{
  _WORD *v3; // rsi
  int v7; // ebx
  unsigned __int64 v8; // rax
  void *v9; // rax
  unsigned __int16 v10; // di
  _DWORD *v11; // rcx

  v3 = (_WORD *)((char *)this + 8);
  v7 = SafeMemCopyAndAdvanceInput<unsigned short>((char *)this + 8, a2, a3, 1);
  if ( v7 >= 0 )
  {
    v8 = 8LL * (unsigned __int16)*v3;
    if ( !is_mul_ok((unsigned __int16)*v3, 8u) )
      v8 = -1;
    v9 = operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    *(_QWORD *)this = v9;
    if ( !v9 )
      return (unsigned int)-2147024882;
    memset_0(v9, 0, 8LL * (unsigned __int16)*v3);
    v10 = 0;
    if ( *v3 )
    {
      while ( 1 )
      {
        v11 = operator new[](0xCu, (const struct std::nothrow_t *)&std::nothrow);
        if ( v11 )
        {
          *(_QWORD *)v11 = 0;
          v11[2] = 0;
          *((_BYTE *)v11 + 8) = 1;
        }
        else
        {
          v11 = 0;
        }
        *(_QWORD *)(*(_QWORD *)this + 8LL * v10) = v11;
        if ( !v11 )
          break;
        v7 = CAttrib::Deserialize(*(CAttrib **)(*(_QWORD *)this + 8LL * v10), a2, a3);
        if ( v7 >= 0 && ++v10 < *v3 )
          continue;
        return (unsigned int)v7;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ea18  push    rbx
0x18000ea1a  push    rbp
0x18000ea1b  push    rsi
0x18000ea1c  push    rdi
0x18000ea1d  push    r12
0x18000ea1f  push    r14
0x18000ea21  push    r15
0x18000ea23  sub     rsp, 20h
0x18000ea27  lea     rsi, [rcx+8]
0x18000ea2b  mov     r14, rcx
0x18000ea2e  mov     r12d, 1
0x18000ea34  mov     rcx, rsi
0x18000ea37  mov     r9d, r12d
0x18000ea3a  mov     rbp, r8
0x18000ea3d  mov     r15, rdx
0x18000ea40  call    ??$SafeMemCopyAndAdvanceInput@G@@YAJPEAGAEAPEAEPEAEJ@Z; SafeMemCopyAndAdvanceInput<ushort>(ushort *,uchar * &,uchar *,long)
0x18000ea45  mov     ebx, eax
0x18000ea47  test    eax, eax
0x18000ea49  js      loc_18000EAF8
0x18000ea4f  movzx   ecx, word ptr [rsi]
0x18000ea52  lea     eax, [r12+7]
0x18000ea57  mul     rcx
0x18000ea5a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ea61  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ea68  cmovb   rax, rcx
0x18000ea6c  mov     rcx, rax; unsigned __int64
0x18000ea6f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ea74  mov     [r14], rax
0x18000ea77  test    rax, rax
0x18000ea7a  jz      short loc_18000EAF3
0x18000ea7c  movzx   r8d, word ptr [rsi]
0x18000ea80  xor     edx, edx; Val
0x18000ea82  shl     r8, 3; Size
0x18000ea86  mov     rcx, rax; void *
0x18000ea89  call    memset_0
0x18000ea8e  xor     eax, eax
0x18000ea90  xor     edi, edi
0x18000ea92  cmp     ax, [rsi]
0x18000ea95  jnb     short loc_18000EAF8
0x18000ea97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ea9e  mov     ecx, 0Ch; unsigned __int64
0x18000eaa3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000eaa8  mov     rcx, rax
0x18000eaab  test    rax, rax
0x18000eaae  jz      short loc_18000EABE
0x18000eab0  xor     eax, eax
0x18000eab2  mov     [rcx], rax
0x18000eab5  mov     [rcx+8], eax
0x18000eab8  mov     [rcx+8], r12b
0x18000eabc  jmp     short loc_18000EAC0
0x18000eabe  xor     ecx, ecx
0x18000eac0  mov     rax, [r14]
0x18000eac3  movzx   r9d, di
0x18000eac7  mov     [rax+r9*8], rcx
0x18000eacb  test    rcx, rcx
0x18000eace  jz      short loc_18000EAF3
0x18000ead0  mov     rcx, [r14]
0x18000ead3  mov     r8, rbp; unsigned __int8 *
0x18000ead6  mov     rdx, r15; unsigned __int8 **
0x18000ead9  mov     rcx, [rcx+r9*8]; this
0x18000eadd  call    ?Deserialize@CAttrib@@QEAAJAEAPEAEPEAE@Z; CAttrib::Deserialize(uchar * &,uchar *)
0x18000eae2  mov     ebx, eax
0x18000eae4  test    eax, eax
0x18000eae6  js      short loc_18000EAF8
0x18000eae8  add     di, r12w
0x18000eaec  cmp     di, [rsi]
0x18000eaef  jb      short loc_18000EA97
0x18000eaf1  jmp     short loc_18000EAF8
0x18000eaf3  mov     ebx, 8007000Eh
0x18000eaf8  mov     eax, ebx
0x18000eafa  add     rsp, 20h
0x18000eafe  pop     r15
0x18000eb00  pop     r14
0x18000eb02  pop     r12
0x18000eb04  pop     rdi
0x18000eb05  pop     rsi
0x18000eb06  pop     rbp
0x18000eb07  pop     rbx
0x18000eb08  retn
```
