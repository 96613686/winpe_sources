# PopulateFunctionDescriptorArray

- ea: `0x1400281ac`
- end: `0x1400282dd`
- name: `PopulateFunctionDescriptorArray`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400275b0`
- `0x1400281ac`

## callees

- `0x140027968`
- `0x1400281ac`
- `0x1400282e4`
- `0x1400283ac`

## pseudocode

```c
__int64 __fastcall PopulateFunctionDescriptorArray(
        __int64 a1,
        __int64 **a2,
        unsigned __int8 a3,
        char *a4,
        unsigned __int8 *a5)
{
  __int64 *v5; // rdi
  int v6; // ebp
  unsigned __int8 v7; // bl
  __int64 v12; // rax
  unsigned __int8 v14; // [rsp+68h] [rbp+10h] BYREF

  v5 = *a2;
  v6 = 0;
  v7 = 0;
  do
  {
    while ( 1 )
    {
      if ( v5 == (__int64 *)a2 )
        goto LABEL_18;
      if ( v7 >= a3 )
        goto LABEL_16;
      v12 = v5[4];
      if ( *(_BYTE *)(v12 + 5) == 2 && *(_BYTE *)(v12 + 6) == 8 )
        break;
      v6 = PopulateFunctionDescriptorElement(a1, v5, a4);
      if ( v6 < 0 )
        goto LABEL_15;
      a4 += 80;
      ++v7;
LABEL_14:
      v5 = (__int64 *)*v5;
    }
    if ( *((_DWORD *)v5 + 11) )
    {
      v6 = PopulateLogicalHandsetElement(a1, v5, a4);
      if ( v6 < 0 )
        goto LABEL_15;
      a4 += 80;
      ++v7;
    }
    if ( v7 < a3 )
    {
      v14 = 0;
      v6 = PopulateFunctionDescriptorArray(a1, (int)v5 + 16, a3 - v7, (_DWORD)a4, (__int64)&v14);
      if ( v6 >= 0 )
      {
        a4 += 80 * v14;
        v7 += v14;
        goto LABEL_14;
      }
    }
LABEL_15:
    v5 = (__int64 *)*v5;
  }
  while ( v6 >= 0 );
LABEL_16:
  if ( v6 < 0 )
    goto LABEL_21;
  if ( v5 == (__int64 *)a2 )
  {
LABEL_18:
    if ( v7 <= a3 )
    {
      *a5 = v7;
      return (unsigned int)v6;
    }
  }
  v6 = -1073741595;
LABEL_21:
  while ( v7 )
  {
    a4 -= 80;
    DestroyFunctionDescriptorElement(a4);
    --v7;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400281ac  mov     [rsp+arg_0], rbx
0x1400281b1  mov     [rsp+arg_10], rbp
0x1400281b6  push    rsi
0x1400281b7  push    rdi
0x1400281b8  push    r12
0x1400281ba  push    r14
0x1400281bc  push    r15
0x1400281be  sub     rsp, 30h
0x1400281c2  mov     rdi, [rdx]
0x1400281c5  xor     ebp, ebp
0x1400281c7  xor     bl, bl
0x1400281c9  mov     rsi, r9
0x1400281cc  mov     r14b, r8b
0x1400281cf  mov     r15, rdx
0x1400281d2  mov     r12, rcx
0x1400281d5  cmp     rdi, r15
0x1400281d8  jz      loc_140028298
0x1400281de  cmp     bl, r14b
0x1400281e1  jnb     loc_14002828F
0x1400281e7  mov     rax, [rdi+20h]
0x1400281eb  cmp     byte ptr [rax+5], 2
0x1400281ef  jnz     short loc_140028262
0x1400281f1  cmp     byte ptr [rax+6], 8
0x1400281f5  jnz     short loc_140028262
0x1400281f7  cmp     dword ptr [rdi+2Ch], 0
0x1400281fb  jz      short loc_140028219
0x1400281fd  mov     r8, rsi
0x140028200  mov     rdx, rdi
0x140028203  mov     rcx, r12
0x140028206  call    PopulateLogicalHandsetElement
0x14002820b  mov     ebp, eax
0x14002820d  test    eax, eax
0x14002820f  js      short loc_140028284
0x140028211  add     rsi, 50h ; 'P'
0x140028215  inc     bl
0x140028217  jmp     short loc_14002821D
0x140028219  test    ebp, ebp
0x14002821b  js      short loc_140028284
0x14002821d  cmp     bl, r14b
0x140028220  jnb     short loc_140028284
0x140028222  mov     r8b, r14b
0x140028225  mov     [rsp+58h+arg_8], 0
0x14002822a  lea     rax, [rsp+58h+arg_8]
0x14002822f  sub     r8b, bl
0x140028232  lea     rdx, [rdi+10h]
0x140028236  mov     [rsp+58h+var_38], rax
0x14002823b  mov     r9, rsi
0x14002823e  mov     rcx, r12
0x140028241  call    PopulateFunctionDescriptorArray
0x140028246  mov     ebp, eax
0x140028248  test    eax, eax
0x14002824a  js      short loc_140028284
0x14002824c  movzx   eax, [rsp+58h+arg_8]
0x140028251  lea     rcx, [rax+rax*4]
0x140028255  shl     rcx, 4
0x140028259  add     rsi, rcx
0x14002825c  add     bl, [rsp+58h+arg_8]
0x140028260  jmp     short loc_14002827C
0x140028262  mov     r8, rsi
0x140028265  mov     rdx, rdi
0x140028268  mov     rcx, r12
0x14002826b  call    PopulateFunctionDescriptorElement
0x140028270  mov     ebp, eax
0x140028272  test    eax, eax
0x140028274  js      short loc_140028284
0x140028276  add     rsi, 50h ; 'P'
0x14002827a  inc     bl
0x14002827c  mov     rdi, [rdi]
0x14002827f  jmp     loc_1400281D5
0x140028284  mov     rdi, [rdi]
0x140028287  test    ebp, ebp
0x140028289  jns     loc_1400281D5
0x14002828f  test    ebp, ebp
0x140028291  js      short loc_1400282AE
0x140028293  cmp     rdi, r15
0x140028296  jnz     short loc_1400282A9
0x140028298  cmp     bl, r14b
0x14002829b  ja      short loc_1400282A9
0x14002829d  mov     rax, [rsp+58h+arg_20]
0x1400282a5  mov     [rax], bl
0x1400282a7  jmp     short loc_1400282C3
0x1400282a9  mov     ebp, 0C00000E5h
0x1400282ae  test    bl, bl
0x1400282b0  jz      short loc_1400282C3
0x1400282b2  sub     rsi, 50h ; 'P'
0x1400282b6  mov     rcx, rsi; void *
0x1400282b9  call    DestroyFunctionDescriptorElement
0x1400282be  add     bl, 0FFh
0x1400282c1  jnz     short loc_1400282B2
0x1400282c3  mov     rbx, [rsp+58h+arg_0]
0x1400282c8  mov     eax, ebp
0x1400282ca  mov     rbp, [rsp+58h+arg_10]
0x1400282cf  add     rsp, 30h
0x1400282d3  pop     r15
0x1400282d5  pop     r14
0x1400282d7  pop     r12
0x1400282d9  pop     rdi
0x1400282da  pop     rsi
0x1400282db  retn
```
