# CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::SetValue(ulong,WRITER_SINK_CALLBACK *)

- ea: `0x18000b69c`
- end: `0x18000b772`
- name: `?SetValue@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@QEAAJKPEAUWRITER_SINK_CALLBACK@@@Z`
- size: `214`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000807c`
- `0x18000b478`
- `0x18000e5c0`
- `0x18000ecbc`
- `0x18000ed10`
- `0x180010060`
- `0x1800102b4`
- `0x1800118f8`

## callees

- `0x18000b69c`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::SetValue(
        _DWORD *a1,
        unsigned int a2,
        __int64 (__fastcall **a3)(_QWORD, _QWORD *))
{
  __int64 result; // rax
  _DWORD *v6; // rsi
  _DWORD *i; // rbx
  unsigned int v8; // eax
  __int64 (__fastcall **v9)(_DWORD *, _DWORD **); // rax
  _QWORD *v10; // rax
  __int64 v11; // rdi
  _DWORD *v12; // [rsp+50h] [rbp+8h] BYREF

  if ( !a1 )
    return 2147500035LL;
  v6 = 0;
  for ( i = a1; i; i = (_DWORD *)*((_QWORD *)i + 24) )
  {
    v8 = i[2];
    if ( a2 < v8 )
      break;
    if ( a2 < v8 + 20 )
      goto LABEL_12;
    v6 = i;
  }
  v9 = *(__int64 (__fastcall ***)(_DWORD *, _DWORD **))a1;
  v12 = 0;
  result = (*v9)(a1, &v12);
  if ( (int)result < 0 )
    return result;
  v12[2] = 20 * (a2 / 0x14);
  v10 = v12;
  if ( v6 )
    *((_QWORD *)v6 + 24) = v12;
  v10[24] = i;
  i = v12;
LABEL_12:
  v11 = a2 - i[2];
  if ( ((unsigned int)v11 & 0xFFFFFFF8) >= 0x18 )
    return 2147549183LL;
  *((_BYTE *)i + ((unsigned __int64)(unsigned int)v11 >> 3) + 24) |= *((_BYTE *)&CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::s_bSingleBitMasks
                                                                     + (v11 & 7));
  if ( (unsigned int)v11 >= 0x14 )
    return 2147549183LL;
  *(_QWORD *)&i[2 * v11 + 8] = a3;
  return 0;
}

```

## disassembly

```asm
0x18000b69c  push    rbx
0x18000b69e  push    rbp
0x18000b69f  push    rsi
0x18000b6a0  push    rdi
0x18000b6a1  sub     rsp, 28h
0x18000b6a5  mov     rbp, r8
0x18000b6a8  mov     edi, edx
0x18000b6aa  test    rcx, rcx
0x18000b6ad  jnz     short loc_18000B6B9
0x18000b6af  mov     eax, 80004003h
0x18000b6b4  jmp     loc_18000B769
0x18000b6b9  xor     esi, esi
0x18000b6bb  mov     rbx, rcx
0x18000b6be  test    rbx, rbx
0x18000b6c1  jz      short loc_18000B6DD
0x18000b6c3  mov     eax, [rbx+8]
0x18000b6c6  cmp     edi, eax
0x18000b6c8  jb      short loc_18000B6DD
0x18000b6ca  add     eax, 14h
0x18000b6cd  cmp     edi, eax
0x18000b6cf  jb      short loc_18000B72F
0x18000b6d1  mov     rsi, rbx
0x18000b6d4  mov     rbx, [rbx+0C0h]
0x18000b6db  jmp     short loc_18000B6BE
0x18000b6dd  mov     rax, [rcx]
0x18000b6e0  lea     rdx, [rsp+48h+arg_0]
0x18000b6e5  mov     [rsp+48h+arg_0], 0
0x18000b6ee  mov     rax, [rax]
0x18000b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6f6  test    eax, eax
0x18000b6f8  js      short loc_18000B769
0x18000b6fa  mov     eax, 0CCCCCCCDh
0x18000b6ff  mul     edi
0x18000b701  mov     rax, [rsp+48h+arg_0]
0x18000b706  shr     edx, 4
0x18000b709  lea     ecx, [rdx+rdx*4]
0x18000b70c  shl     ecx, 2
0x18000b70f  mov     [rax+8], ecx
0x18000b712  mov     rax, [rsp+48h+arg_0]
0x18000b717  test    rsi, rsi
0x18000b71a  jz      short loc_18000B723
0x18000b71c  mov     [rsi+0C0h], rax
0x18000b723  mov     [rax+0C0h], rbx
0x18000b72a  mov     rbx, [rsp+48h+arg_0]
0x18000b72f  sub     edi, [rbx+8]
0x18000b732  mov     eax, edi
0x18000b734  and     eax, 0FFFFFFF8h
0x18000b737  cmp     eax, 18h
0x18000b73a  jnb     short loc_18000B764
0x18000b73c  mov     eax, edi
0x18000b73e  lea     r8, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::s_bSingleBitMasks
0x18000b745  and     eax, 7
0x18000b748  mov     ecx, edi
0x18000b74a  shr     rcx, 3
0x18000b74e  mov     al, [rax+r8]
0x18000b752  or      [rcx+rbx+18h], al
0x18000b756  cmp     edi, 14h
0x18000b759  jnb     short loc_18000B764
0x18000b75b  mov     [rbx+rdi*8+20h], rbp
0x18000b760  xor     eax, eax
0x18000b762  jmp     short loc_18000B769
0x18000b764  mov     eax, 8000FFFFh
0x18000b769  add     rsp, 28h
0x18000b76d  pop     rdi
0x18000b76e  pop     rsi
0x18000b76f  pop     rbp
0x18000b770  pop     rbx
0x18000b771  retn
```
