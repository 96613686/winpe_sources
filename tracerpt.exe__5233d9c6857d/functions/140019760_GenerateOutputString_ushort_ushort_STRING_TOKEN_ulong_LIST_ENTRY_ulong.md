# GenerateOutputString(ushort *,ushort *,_STRING_TOKEN *,ulong,_LIST_ENTRY *,ulong *)

- ea: `0x140019760`
- end: `0x140019958`
- name: `?GenerateOutputString@@YAPEAGPEAG0PEAU_STRING_TOKEN@@KPEAU_LIST_ENTRY@@PEAK@Z`
- size: `504`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, unsigned __int16 *, struct _STRING_TOKEN *, unsigned int, struct _LIST_ENTRY *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140019960`

## callees

- `0x140019760`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001993f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001993f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400197a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019931`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400197a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019931`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400197b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400197b0`

## pseudocode

```c
unsigned __int16 *__fastcall GenerateOutputString(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _STRING_TOKEN *a3,
        unsigned int a4,
        struct _LIST_ENTRY *a5,
        unsigned int *a6)
{
  unsigned __int64 v9; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  void *v12; // rdi
  struct _LIST_ENTRY *v13; // r14
  _WORD *v14; // r8
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v16; // r15
  __int64 Blink_low; // rax
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // r10
  _WORD *v22; // rax
  unsigned __int16 *v23; // r10
  unsigned __int16 *v24; // r10
  unsigned __int64 Blink_high; // r9
  __int64 v26; // rcx
  _WORD *v27; // rcx
  __int64 v28; // r11
  __int64 v29; // rdx
  _WORD *v30; // rsi
  __int64 v31; // rcx
  HANDLE v33; // rax

  v9 = a4 + 1LL;
  if ( v9 < a4 )
    return 0;
  if ( !is_mul_ok(2u, v9) )
    return 0;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 2 * v9);
  v12 = v11;
  if ( !v11 )
    return 0;
  v13 = a5;
  v14 = v11;
  Flink = a5->Flink;
  if ( a5 == a5->Flink )
  {
LABEL_33:
    *v14 = 0;
    *a6 = 0;
    return (unsigned __int16 *)v12;
  }
  while ( 1 )
  {
    v16 = Flink->Flink;
    Blink_low = LODWORD(Flink[1].Blink);
    if ( LODWORD(Flink[1].Flink) )
    {
      if ( !v9 )
        goto LABEL_35;
      if ( v9 > 0x7FFFFFFF )
        break;
      v18 = *((unsigned int *)a3 + 2 * Blink_low + 1);
      if ( v18 > 0x7FFFFFFE )
        break;
      v19 = (unsigned int)v18;
      v20 = v9;
      v21 = *((unsigned int *)a3 + 2 * Blink_low);
      v22 = v14;
      v23 = &a1[v21];
      do
      {
        if ( !v19 )
          break;
        if ( !*v23 )
          break;
        *v22++ = *v23++;
        --v19;
        --v20;
      }
      while ( v20 );
      goto LABEL_22;
    }
    v24 = &a2[Blink_low];
    Blink_high = HIDWORD(Flink[1].Blink);
    if ( HIDWORD(Flink[1].Flink) )
    {
      v28 = 0;
      v29 = 0;
      v30 = v14;
      if ( (_DWORD)Blink_high )
      {
        do
        {
          v31 = (unsigned int)(v29 + 1);
          if ( v24[v29] != 92 )
            v31 = (unsigned int)v29;
          v28 = (unsigned int)(v28 + 1);
          v29 = (unsigned int)(v31 + 1);
          *v30++ = v24[v31];
        }
        while ( (unsigned int)v29 < (unsigned int)Blink_high );
        v13 = a5;
      }
      v14 += v28;
      v9 -= (unsigned int)v28;
      goto LABEL_32;
    }
    if ( !v9 )
      goto LABEL_35;
    if ( v9 > 0x7FFFFFFF )
      break;
    v18 = (unsigned int)Blink_high;
    if ( Blink_high > 0x7FFFFFFE )
      break;
    v26 = (unsigned int)Blink_high;
    v20 = v9;
    v22 = v14;
    do
    {
      if ( !v26 )
        break;
      if ( !*v24 )
        break;
      *v22++ = *v24++;
      --v26;
      --v20;
    }
    while ( v20 );
LABEL_22:
    v27 = v22 - 1;
    if ( v20 )
      v27 = v22;
    *v27 = 0;
    if ( !v20 )
      goto LABEL_35;
    v14 += v18;
    v9 -= v18;
LABEL_32:
    Flink = v16;
    if ( v13 == v16 )
      goto LABEL_33;
  }
  *v14 = 0;
LABEL_35:
  v33 = GetProcessHeap();
  HeapFree(v33, 0, v12);
  return 0;
}

```

## disassembly

```asm
0x140019760  push    rbx
0x140019762  push    rbp
0x140019763  push    rsi
0x140019764  push    rdi
0x140019765  push    r12
0x140019767  push    r13
0x140019769  push    r14
0x14001976b  push    r15
0x14001976d  sub     rsp, 38h
0x140019771  mov     eax, r9d
0x140019774  mov     rbp, r8
0x140019777  mov     r12, rdx
0x14001977a  mov     r13, rcx
0x14001977d  lea     rbx, [rax+1]
0x140019781  cmp     rbx, rax
0x140019784  jb      loc_140019945
0x14001978a  xor     esi, esi
0x14001978c  mov     rax, rbx
0x14001978f  lea     ecx, [rsi+2]
0x140019792  mul     rcx
0x140019795  mov     rdi, rax
0x140019798  test    rdx, rdx
0x14001979b  jnz     loc_140019945
0x1400197a1  call    cs:__imp_GetProcessHeap
0x1400197a7  mov     r8, rdi; dwBytes
0x1400197aa  lea     edx, [rsi+8]; dwFlags
0x1400197ad  mov     rcx, rax; hHeap
0x1400197b0  call    cs:__imp_HeapAlloc
0x1400197b6  mov     rdi, rax
0x1400197b9  test    rax, rax
0x1400197bc  jz      loc_140019945
0x1400197c2  mov     r14, [rsp+78h+arg_20]
0x1400197ca  mov     r8, rax
0x1400197cd  mov     rcx, [r14]
0x1400197d0  cmp     r14, rcx
0x1400197d3  jz      loc_14001991A
0x1400197d9  mov     r15, [rcx]
0x1400197dc  mov     eax, [rcx+18h]
0x1400197df  cmp     [rcx+10h], esi
0x1400197e2  jz      short loc_14001984C
0x1400197e4  test    rbx, rbx
0x1400197e7  jz      loc_140019931
0x1400197ed  cmp     rbx, 7FFFFFFFh
0x1400197f4  ja      loc_14001992D
0x1400197fa  mov     edx, [rbp+rax*8+4]
0x1400197fe  cmp     rdx, 7FFFFFFEh
0x140019805  ja      loc_14001992D
0x14001980b  mov     eax, [rbp+rax*8+0]
0x14001980f  mov     ecx, edx
0x140019811  mov     r9, rbx
0x140019814  lea     r10, ds:0[rax*2]
0x14001981c  mov     rax, r8
0x14001981f  add     r10, r13
0x140019822  test    rcx, rcx
0x140019825  jz      loc_1400198AB
0x14001982b  movzx   r11d, word ptr [r10]
0x14001982f  test    r11w, r11w
0x140019833  jz      short loc_1400198AB
0x140019835  mov     [rax], r11w
0x140019839  add     r10, 2
0x14001983d  add     rax, 2
0x140019841  dec     rcx
0x140019844  sub     r9, 1
0x140019848  jnz     short loc_140019822
0x14001984a  jmp     short loc_1400198AB
0x14001984c  lea     r10, [r12+rax*2]
0x140019850  mov     r9d, [rcx+1Ch]
0x140019854  cmp     [rcx+14h], esi
0x140019857  jnz     short loc_1400198C4
0x140019859  test    rbx, rbx
0x14001985c  jz      loc_140019931
0x140019862  cmp     rbx, 7FFFFFFFh
0x140019869  ja      loc_14001992D
0x14001986f  mov     edx, r9d
0x140019872  cmp     r9, 7FFFFFFEh
0x140019879  ja      loc_14001992D
0x14001987f  mov     ecx, edx
0x140019881  mov     r9, rbx
0x140019884  mov     rax, r8
0x140019887  test    rcx, rcx
0x14001988a  jz      short loc_1400198AB
0x14001988c  movzx   r11d, word ptr [r10]
0x140019890  test    r11w, r11w
0x140019894  jz      short loc_1400198AB
0x140019896  mov     [rax], r11w
0x14001989a  add     r10, 2
0x14001989e  add     rax, 2
0x1400198a2  dec     rcx
0x1400198a5  sub     r9, 1
0x1400198a9  jnz     short loc_140019887
0x1400198ab  test    r9, r9
0x1400198ae  lea     rcx, [rax-2]
0x1400198b2  cmovnz  rcx, rax
0x1400198b6  mov     [rcx], si
0x1400198b9  jz      short loc_140019931
0x1400198bb  lea     r8, [r8+rdx*2]
0x1400198bf  sub     rbx, rdx
0x1400198c2  jmp     short loc_14001990E
0x1400198c4  xor     r11d, r11d
0x1400198c7  xor     edx, edx
0x1400198c9  mov     rsi, r8
0x1400198cc  test    r9d, r9d
0x1400198cf  jz      short loc_140019902
0x1400198d1  lea     ecx, [rdx+1]
0x1400198d4  mov     r14d, 5Ch ; '\'
0x1400198da  cmp     r14w, [r10+rdx*2]
0x1400198df  cmovnz  ecx, edx
0x1400198e2  inc     r11d
0x1400198e5  mov     edx, ecx
0x1400198e7  inc     edx
0x1400198e9  movzx   eax, word ptr [r10+rcx*2]
0x1400198ee  mov     [rsi], ax
0x1400198f1  lea     rsi, [rsi+2]
0x1400198f5  cmp     edx, r9d
0x1400198f8  jb      short loc_1400198D1
0x1400198fa  mov     r14, [rsp+78h+arg_20]
0x140019902  mov     eax, r11d
0x140019905  lea     r8, [r8+r11*2]
0x140019909  sub     rbx, rax
0x14001990c  xor     esi, esi
0x14001990e  mov     rcx, r15
0x140019911  cmp     r14, r15
0x140019914  jnz     loc_1400197D9
0x14001991a  mov     rax, [rsp+78h+arg_28]
0x140019922  mov     [r8], si
0x140019926  mov     [rax], esi
0x140019928  mov     rax, rdi
0x14001992b  jmp     short loc_140019947
0x14001992d  mov     [r8], si
0x140019931  call    cs:__imp_GetProcessHeap
0x140019937  mov     r8, rdi; lpMem
0x14001993a  xor     edx, edx; dwFlags
0x14001993c  mov     rcx, rax; hHeap
0x14001993f  call    cs:__imp_HeapFree
0x140019945  xor     eax, eax
0x140019947  add     rsp, 38h
0x14001994b  pop     r15
0x14001994d  pop     r14
0x14001994f  pop     r13
0x140019951  pop     r12
0x140019953  pop     rdi
0x140019954  pop     rsi
0x140019955  pop     rbp
0x140019956  pop     rbx
0x140019957  retn
```
