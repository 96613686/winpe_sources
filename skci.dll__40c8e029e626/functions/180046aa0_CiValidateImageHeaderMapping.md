# CiValidateImageHeaderMapping

- ea: `0x180046aa0`
- end: `0x180046c77`
- name: `CiValidateImageHeaderMapping`
- size: `471`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180011ef0`

## callees

- `0x180010a88`
- `0x180046aa0`

## import_xrefs

- `securekernel!RtlImageNtHeaderEx` at `0x180046ae5`
- `securekernel!RtlImageNtHeaderEx` at `0x180046ae5`

## pseudocode

```c
__int64 __fastcall CiValidateImageHeaderMapping(unsigned __int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned __int64 v8; // r14
  NTSTATUS v9; // edx
  __int64 v10; // r11
  unsigned __int64 v11; // rcx
  _WORD *v12; // r8
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r12
  unsigned int v15; // r9d
  __int64 v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // r10
  unsigned __int64 v19; // rcx
  __int64 v21; // [rsp+60h] [rbp+8h] BYREF
  ULONG pulResult; // [rsp+68h] [rbp+10h] BYREF

  v21 = 0;
  pulResult = 0;
  v8 = a2 + a1;
  if ( v8 < a1 )
    return (unsigned int)-1073741675;
  v9 = RtlImageNtHeaderEx(0, a1, a2, &v21);
  if ( v9 >= 0 )
  {
    v10 = v21;
    v11 = *(unsigned __int16 *)(v21 + 20);
    v12 = (_WORD *)(v21 + 24);
    v13 = v21 + 24 + v11;
    v14 = -1;
    if ( v13 >= v21 + 24 )
      v14 = v21 + 24 + v11;
    v9 = v13 < v21 + 24 ? 0xC0000095 : 0;
    if ( v13 < (unsigned __int64)v12 || v14 > v8 || (unsigned int)v11 < 0x1A )
      return (unsigned int)-1073741701;
    if ( *v12 == 523 )
    {
      if ( v11 < 0xB0 )
        return (unsigned int)-1073741701;
    }
    else
    {
      if ( *v12 != 267 )
        return (unsigned int)-1073741701;
      if ( v11 < 0xA0 )
        return (unsigned int)-1073741701;
    }
    v15 = *(_DWORD *)(v21 + 84);
    if ( v15 <= a2 )
    {
      v16 = *(unsigned __int16 *)(v21 + 6);
      if ( (_WORD)v16 )
      {
        v17 = v11 + v21 + 24;
        if ( v17 < v14 )
          return (unsigned int)-1073741701;
        v9 = RtlULongLongToULong(40 * v16, &pulResult);
        if ( v9 < 0 )
          return (unsigned int)v9;
        v19 = v17 + pulResult;
        if ( v19 >= v17 )
          v18 = v17 + pulResult;
        v9 = v19 < v17 ? 0xC0000095 : 0;
        if ( v19 < v17 || v18 > v8 )
          return (unsigned int)-1073741701;
        if ( v18 - a1 > v15 )
          return (unsigned int)-1073741701;
      }
      *a3 = v10;
      if ( a4 )
        *a4 = v15;
    }
    else
    {
      return (unsigned int)-1073741306;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180046aa0  mov     rax, rsp
0x180046aa3  mov     [rax+18h], rbx
0x180046aa7  mov     [rax+20h], rsi
0x180046aab  push    rdi
0x180046aac  push    r12
0x180046aae  push    r13
0x180046ab0  push    r14
0x180046ab2  push    r15
0x180046ab4  sub     rsp, 30h
0x180046ab8  mov     r15, r9
0x180046abb  mov     r13, r8
0x180046abe  mov     ebx, edx
0x180046ac0  mov     rsi, rcx
0x180046ac3  xor     edi, edi
0x180046ac5  mov     [rax+8], rdi
0x180046ac9  mov     [rax+10h], edi
0x180046acc  mov     r8d, edx
0x180046acf  lea     r14, [rbx+rcx]
0x180046ad3  cmp     r14, rcx
0x180046ad6  jb      loc_180046C57
0x180046adc  lea     r9, [rax+8]
0x180046ae0  mov     rdx, rcx
0x180046ae3  xor     ecx, ecx
0x180046ae5  call    cs:__imp_RtlImageNtHeaderEx
0x180046aec  nop     dword ptr [rax+rax+00h]
0x180046af1  mov     edx, eax
0x180046af3  mov     [rsp+58h+var_38], eax
0x180046af7  test    eax, eax
0x180046af9  js      loc_180046C5C
0x180046aff  mov     r11, [rsp+58h+arg_0]
0x180046b04  movzx   ecx, word ptr [r11+14h]
0x180046b09  lea     r8, [r11+18h]
0x180046b0d  lea     rax, [r8+rcx]
0x180046b11  or      r10, 0FFFFFFFFFFFFFFFFh
0x180046b15  mov     r12, r10
0x180046b18  cmp     rax, r8
0x180046b1b  cmovnb  r12, rax
0x180046b1f  sbb     edx, edx
0x180046b21  mov     edi, 0C0000095h
0x180046b26  and     edx, edi
0x180046b28  mov     [rsp+58h+var_38], edx
0x180046b2c  cmp     rax, r8
0x180046b2f  jb      loc_180046C44
0x180046b35  cmp     r12, r14
0x180046b38  ja      loc_180046C44
0x180046b3e  cmp     ecx, 1Ah
0x180046b41  jb      loc_180046C44
0x180046b47  movzx   eax, word ptr [r8]
0x180046b4b  mov     r8d, 20Bh
0x180046b51  cmp     ax, r8w
0x180046b55  jnz     short loc_180046B6C
0x180046b57  cmp     rcx, 0B0h
0x180046b5e  jnb     short loc_180046B93
0x180046b60  lea     edx, [rdi-1Ah]
0x180046b63  mov     [rsp+58h+var_38], edx
0x180046b67  jmp     loc_180046C5C
0x180046b6c  mov     r8d, 10Bh
0x180046b72  cmp     ax, r8w
0x180046b76  jnz     loc_180046C39
0x180046b7c  cmp     rcx, 0A0h
0x180046b83  jnb     short loc_180046B93
0x180046b85  mov     edx, 0C000007Bh
0x180046b8a  mov     [rsp+58h+var_38], edx
0x180046b8e  jmp     loc_180046C5C
0x180046b93  mov     r9d, [r11+54h]
0x180046b97  cmp     r9d, ebx
0x180046b9a  jbe     short loc_180046BAA
0x180046b9c  mov     edx, 0C0000206h
0x180046ba1  mov     [rsp+58h+var_38], edx
0x180046ba5  jmp     loc_180046C5C
0x180046baa  movzx   eax, word ptr [r11+6]
0x180046baf  test    ax, ax
0x180046bb2  jz      short loc_180046C2B
0x180046bb4  lea     rbx, [r11+18h]
0x180046bb8  add     rbx, rcx
0x180046bbb  cmp     rbx, r12
0x180046bbe  jnb     short loc_180046BCE
0x180046bc0  mov     edx, 0C000007Bh
0x180046bc5  mov     [rsp+58h+var_38], edx
0x180046bc9  jmp     loc_180046C5C
0x180046bce  lea     rcx, [rax+rax*4]
0x180046bd2  shl     rcx, 3; ullOperand
0x180046bd6  lea     rdx, [rsp+58h+pulResult]; pulResult
0x180046bdb  call    RtlULongLongToULong
0x180046be0  mov     edx, eax
0x180046be2  mov     [rsp+58h+var_38], eax
0x180046be6  test    eax, eax
0x180046be8  js      short loc_180046C5C
0x180046bea  mov     ecx, [rsp+58h+pulResult]
0x180046bee  add     rcx, rbx
0x180046bf1  cmp     rcx, rbx
0x180046bf4  cmovnb  r10, rcx
0x180046bf8  sbb     edx, edx
0x180046bfa  and     edx, edi
0x180046bfc  mov     [rsp+58h+var_38], edx
0x180046c00  cmp     rcx, rbx
0x180046c03  jb      short loc_180046C20
0x180046c05  cmp     r10, r14
0x180046c08  ja      short loc_180046C20
0x180046c0a  sub     r10, rsi
0x180046c0d  mov     eax, r9d
0x180046c10  cmp     r10, rax
0x180046c13  jbe     short loc_180046C2B
0x180046c15  mov     edx, 0C000007Bh
0x180046c1a  mov     [rsp+58h+var_38], edx
0x180046c1e  jmp     short loc_180046C5C
0x180046c20  mov     edx, 0C000007Bh
0x180046c25  mov     [rsp+58h+var_38], edx
0x180046c29  jmp     short loc_180046C5C
0x180046c2b  mov     [r13+0], r11
0x180046c2f  test    r15, r15
0x180046c32  jz      short loc_180046C37
0x180046c34  mov     [r15], r9d
0x180046c37  jmp     short loc_180046C5C
0x180046c39  mov     edx, 0C000007Bh
0x180046c3e  mov     [rsp+58h+var_38], edx
0x180046c42  jmp     short loc_180046C5C
0x180046c44  mov     edx, 0C000007Bh
0x180046c49  mov     [rsp+58h+var_38], edx
0x180046c4d  jmp     short loc_180046C5C
0x180046c4f  mov     edx, eax
0x180046c51  mov     [rsp+58h+var_38], eax
0x180046c55  jmp     short loc_180046C5C
0x180046c57  mov     edx, 0C0000095h
0x180046c5c  mov     eax, edx
0x180046c5e  mov     rbx, [rsp+58h+arg_10]
0x180046c63  mov     rsi, [rsp+58h+arg_18]
0x180046c68  add     rsp, 30h
0x180046c6c  pop     r15
0x180046c6e  pop     r14
0x180046c70  pop     r13
0x180046c72  pop     r12
0x180046c74  pop     rdi
0x180046c75  retn
```
