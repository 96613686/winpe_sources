# CBlackboardFactory::SetWorkingDirectory(ushort const *)

- ea: `0x18001847c`
- end: `0x180018534`
- name: `?SetWorkingDirectory@CBlackboardFactory@@QEAAHPEBG@Z`
- size: `184`
- prototype: `int(CBlackboardFactory *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800188e0`

## callees

- `0x180009da4`
- `0x180009e30`
- `0x180017f94`
- `0x18001847c`

## pseudocode

```c
_BOOL8 __fastcall CBlackboardFactory::SetWorkingDirectory(CBlackboardFactory *this, size_t *a2)
{
  CBlackboardFactory *v2; // rdi
  __int64 v4; // rdx
  unsigned __int16 v5; // bp
  unsigned __int16 **v6; // rsi

  v2 = Block;
  if ( !a2 || !*(_WORD *)a2 )
    return (unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize((char *)Block + 40, 0) != 0;
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)a2 + v4) );
  v5 = *((_WORD *)a2 + (unsigned int)(v4 - 1));
  v6 = (unsigned __int16 **)((char *)Block + 40);
  if ( !(unsigned int)CDynamicArray<unsigned short,unsigned short *>::SetSize(
                        (char *)Block + 40,
                        (v5 != 92) + 1 + (unsigned int)v4)
    || (int)StringCchCopyW(*v6, *((_QWORD *)v2 + 6), a2) < 0 )
  {
    return 0;
  }
  if ( v5 != 92 )
    StringCchCatW(*v6, *((_QWORD *)v2 + 6), L"\\");
  return 1;
}

```

## disassembly

```asm
0x18001847c  push    rbx
0x18001847e  push    rbp
0x18001847f  push    rsi
0x180018480  push    rdi
0x180018481  push    r14
0x180018483  push    r15
0x180018485  sub     rsp, 28h
0x180018489  mov     rdi, cs:Block
0x180018490  xor     r14d, r14d
0x180018493  mov     rbx, rdx
0x180018496  test    rdx, rdx
0x180018499  jz      short loc_180018511
0x18001849b  cmp     [rdx], r14w
0x18001849f  jz      short loc_180018511
0x1800184a1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800184a5  inc     rdx
0x1800184a8  cmp     [rbx+rdx*2], r14w
0x1800184ad  jnz     short loc_1800184A5
0x1800184af  lea     eax, [rdx-1]
0x1800184b2  mov     r15d, 5Ch ; '\'
0x1800184b8  movzx   ebp, word ptr [rbx+rax*2]
0x1800184bc  lea     rsi, [rdi+28h]
0x1800184c0  mov     eax, r14d
0x1800184c3  cmp     r15w, bp
0x1800184c7  mov     rcx, rsi
0x1800184ca  setnz   al
0x1800184cd  inc     eax
0x1800184cf  add     edx, eax
0x1800184d1  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x1800184d6  test    eax, eax
0x1800184d8  jz      short loc_18001850D
0x1800184da  mov     rdx, [rdi+30h]; unsigned __int64
0x1800184de  mov     r8, rbx; unsigned __int16 *
0x1800184e1  mov     rcx, [rsi]; unsigned __int16 *
0x1800184e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800184e9  test    eax, eax
0x1800184eb  js      short loc_18001850D
0x1800184ed  cmp     r15w, bp
0x1800184f1  jz      short loc_180018506
0x1800184f3  mov     rdx, [rdi+30h]; unsigned __int64
0x1800184f7  lea     r8, asc_18002FE70; "\\"
0x1800184fe  mov     rcx, [rsi]; unsigned __int16 *
0x180018501  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018506  mov     eax, 1
0x18001850b  jmp     short loc_180018526
0x18001850d  xor     eax, eax
0x18001850f  jmp     short loc_180018526
0x180018511  lea     rcx, [rdi+28h]
0x180018515  xor     edx, edx
0x180018517  call    ?SetSize@?$CDynamicArray@GPEAG@@QEAAH_K@Z; CDynamicArray<ushort,ushort *>::SetSize(unsigned __int64)
0x18001851c  test    eax, eax
0x18001851e  mov     ecx, r14d
0x180018521  setnz   cl
0x180018524  mov     eax, ecx
0x180018526  add     rsp, 28h
0x18001852a  pop     r15
0x18001852c  pop     r14
0x18001852e  pop     rdi
0x18001852f  pop     rsi
0x180018530  pop     rbp
0x180018531  pop     rbx
0x180018532  retn
```
