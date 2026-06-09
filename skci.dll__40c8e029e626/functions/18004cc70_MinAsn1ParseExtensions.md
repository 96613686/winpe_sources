# MinAsn1ParseExtensions

- ea: `0x18004cc70`
- end: `0x18004cd4e`
- name: `MinAsn1ParseExtensions`
- size: `222`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180044b10`
- `0x18004e128`

## callees

- `0x18004cc70`
- `0x18004dd2c`
- `0x18004de78`

## pseudocode

```c
__int64 __fastcall MinAsn1ParseExtensions(unsigned int *a1, unsigned int *a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdx
  __int64 v7; // rbp
  unsigned int v8; // r12d
  __int64 result; // rax
  int v10; // edi
  int v11; // esi
  int Values; // ecx
  int v13; // eax
  int v14; // [rsp+70h] [rbp+8h] BYREF
  __int64 v15; // [rsp+78h] [rbp+10h] BYREF

  v3 = 0;
  v5 = *a1;
  v15 = 0;
  v14 = 0;
  if ( (_DWORD)v5 )
  {
    v7 = *((_QWORD *)a1 + 1);
    v8 = *a2;
    if ( (int)MinAsn1ExtractContent(v7, v5, &v14, &v15) > 0 )
    {
      v10 = v15;
      v11 = v14;
      while ( 1 )
      {
        if ( !v11 || (unsigned int)v3 >= v8 )
        {
          result = (unsigned int)(v10 - v7);
          goto LABEL_14;
        }
        v14 = 4;
        Values = MinAsn1ExtractValues(v10, v11, (unsigned int)&v14, (unsigned int)&qword_180035D70, 5, a3 + 80 * v3);
        if ( Values <= 0 )
          break;
        v13 = *(_DWORD *)(a3 + 80 * v3 + 16);
        v10 += v13;
        v11 -= v13;
        v3 = (unsigned int)(v3 + 1);
      }
      if ( !Values )
        Values = -1;
      result = (unsigned int)(Values + v7 - v10);
    }
    else
    {
      result = 0xFFFFFFFFLL;
    }
  }
  else
  {
    result = 0;
  }
LABEL_14:
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x18004cc70  mov     rax, rsp
0x18004cc73  mov     [rax+18h], rbx
0x18004cc77  push    rbp
0x18004cc78  push    rsi
0x18004cc79  push    rdi
0x18004cc7a  push    r12
0x18004cc7c  push    r13
0x18004cc7e  push    r14
0x18004cc80  push    r15
0x18004cc82  sub     rsp, 30h
0x18004cc86  xor     ebx, ebx
0x18004cc88  mov     r14, rdx
0x18004cc8b  mov     edx, [rcx]
0x18004cc8d  mov     r13, r8
0x18004cc90  mov     [rax+10h], rbx
0x18004cc94  mov     [rax+8], ebx
0x18004cc97  test    edx, edx
0x18004cc99  jz      loc_18004CD30
0x18004cc9f  mov     rbp, [rcx+8]
0x18004cca3  lea     r9, [rax+10h]
0x18004cca7  mov     r12d, [r14]
0x18004ccaa  lea     r8, [rax+8]
0x18004ccae  mov     rcx, rbp
0x18004ccb1  call    MinAsn1ExtractContent
0x18004ccb6  test    eax, eax
0x18004ccb8  jg      short loc_18004CCBF
0x18004ccba  or      eax, 0FFFFFFFFh
0x18004ccbd  jmp     short loc_18004CD32
0x18004ccbf  mov     rdi, [rsp+68h+arg_8]
0x18004ccc4  mov     esi, [rsp+68h+arg_0]
0x18004ccc8  test    esi, esi
0x18004ccca  jz      short loc_18004CD2A
0x18004cccc  cmp     ebx, r12d
0x18004cccf  jnb     short loc_18004CD2A
0x18004ccd1  lea     r15, [rbx+rbx*4]
0x18004ccd5  mov     [rsp+68h+arg_0], 4
0x18004ccdd  shl     r15, 4
0x18004cce1  lea     r9, qword_180035D70
0x18004cce8  add     r15, r13
0x18004cceb  lea     r8, [rsp+68h+arg_0]
0x18004ccf0  mov     [rsp+68h+var_40], r15
0x18004ccf5  mov     edx, esi
0x18004ccf7  mov     rcx, rdi
0x18004ccfa  mov     [rsp+68h+var_48], 5
0x18004cd02  call    MinAsn1ExtractValues
0x18004cd07  mov     ecx, eax
0x18004cd09  test    eax, eax
0x18004cd0b  jle     short loc_18004CD1A
0x18004cd0d  mov     eax, [r15+10h]
0x18004cd11  add     rdi, rax
0x18004cd14  sub     esi, eax
0x18004cd16  inc     ebx
0x18004cd18  jmp     short loc_18004CCC8
0x18004cd1a  or      eax, 0FFFFFFFFh
0x18004cd1d  test    ecx, ecx
0x18004cd1f  cmovz   ecx, eax
0x18004cd22  mov     eax, ebp
0x18004cd24  sub     eax, edi
0x18004cd26  add     eax, ecx
0x18004cd28  jmp     short loc_18004CD32
0x18004cd2a  mov     eax, edi
0x18004cd2c  sub     eax, ebp
0x18004cd2e  jmp     short loc_18004CD32
0x18004cd30  xor     eax, eax
0x18004cd32  mov     [r14], ebx
0x18004cd35  mov     rbx, [rsp+68h+arg_10]
0x18004cd3d  add     rsp, 30h
0x18004cd41  pop     r15
0x18004cd43  pop     r14
0x18004cd45  pop     r13
0x18004cd47  pop     r12
0x18004cd49  pop     rdi
0x18004cd4a  pop     rsi
0x18004cd4b  pop     rbp
0x18004cd4c  retn
```
