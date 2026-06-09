# WriteLong

- ea: `0x18001191c`
- end: `0x1800119ef`
- name: `WriteLong`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011640`

## callees

- `0x18001191c`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall WriteLong(__int64 a1, int a2, unsigned int a3)
{
  __int64 v3; // r9
  unsigned __int8 v4; // si
  __int64 v5; // rdi
  unsigned __int64 v7; // rax
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // [rsp+30h] [rbp+8h]

  v3 = *(_QWORD *)a1;
  v4 = a2;
  v5 = a3;
  if ( !*(_QWORD *)a1 || a3 + 4 < a3 )
    return 1002;
  v7 = *(unsigned int *)(a1 + 8);
  v11 = a3 + 4;
  if ( v11 <= v7 )
  {
LABEL_4:
    *(_DWORD *)(v5 + v3) = HIBYTE(a2) | ((BYTE2(a2) | ((BYTE1(a2) | (v4 << 8)) << 8)) << 8);
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 16) )
    return 1002;
  v9 = 11 * (int)v7 / 0xAu;
  if ( v9 <= v11 )
  {
    *(_DWORD *)(a1 + 8) = a3 + 4;
    LODWORD(v9) = a3 + 4;
  }
  else
  {
    *(_DWORD *)(a1 + 8) = v9;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(a1 + 16))(v3, (unsigned int)v9);
  *(_QWORD *)a1 = v10;
  v3 = v10;
  if ( v10 )
    goto LABEL_4;
  *(_DWORD *)(a1 + 8) = 0;
  return 1005;
}

```

## disassembly

```asm
0x18001191c  mov     [rsp+arg_10], rbx
0x180011921  mov     [rsp+arg_18], rsi
0x180011926  mov     [rsp+arg_8], edx
0x18001192a  push    rdi
0x18001192b  sub     rsp, 20h
0x18001192f  mov     r9, [rcx]
0x180011932  mov     esi, edx
0x180011934  mov     edi, r8d
0x180011937  mov     rbx, rcx
0x18001193a  mov     [rsp+28h+arg_0], 0
0x180011943  test    r9, r9
0x180011946  jz      short loc_180011998
0x180011948  lea     r8d, [rdi+4]
0x18001194c  cmp     r8d, edi
0x18001194f  jb      short loc_180011998
0x180011951  mov     eax, [rcx+8]
0x180011954  mov     dword ptr [rsp+28h+arg_0], r8d
0x180011959  cmp     [rsp+28h+arg_0], rax
0x18001195e  ja      short loc_18001199F
0x180011960  movzx   eax, byte ptr [rsp+28h+arg_8+1]
0x180011965  movzx   ecx, sil
0x180011969  shl     ecx, 8
0x18001196c  or      ecx, eax
0x18001196e  movzx   eax, byte ptr [rsp+28h+arg_8+2]
0x180011973  shl     ecx, 8
0x180011976  or      ecx, eax
0x180011978  movzx   eax, byte ptr [rsp+28h+arg_8+3]
0x18001197d  shl     ecx, 8
0x180011980  or      ecx, eax
0x180011982  mov     [rdi+r9], ecx
0x180011986  xor     eax, eax
0x180011988  mov     rbx, [rsp+28h+arg_10]
0x18001198d  mov     rsi, [rsp+28h+arg_18]
0x180011992  add     rsp, 20h
0x180011996  pop     rdi
0x180011997  retn
0x180011998  mov     eax, 3EAh
0x18001199d  jmp     short loc_180011988
0x18001199f  cmp     qword ptr [rcx+10h], 0
0x1800119a4  jz      short loc_180011998
0x1800119a6  imul    ecx, eax, 0Bh
0x1800119a9  mov     eax, 0CCCCCCCDh
0x1800119ae  mul     ecx
0x1800119b0  shr     edx, 3
0x1800119b3  mov     eax, edx
0x1800119b5  cmp     rax, [rsp+28h+arg_0]
0x1800119ba  jbe     short loc_1800119C1
0x1800119bc  mov     [rbx+8], eax
0x1800119bf  jmp     short loc_1800119C8
0x1800119c1  mov     [rbx+8], r8d
0x1800119c5  mov     eax, r8d
0x1800119c8  mov     edx, eax
0x1800119ca  mov     rcx, r9
0x1800119cd  mov     rax, [rbx+10h]
0x1800119d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119d6  mov     [rbx], rax
0x1800119d9  mov     r9, rax
0x1800119dc  test    rax, rax
0x1800119df  jnz     loc_180011960
0x1800119e5  mov     [rbx+8], eax
0x1800119e8  mov     eax, 3EDh
0x1800119ed  jmp     short loc_180011988
```
