# WriteWord

- ea: `0x180011f00`
- end: `0x180011fc0`
- name: `WriteWord`
- size: `192`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800110d0`
- `0x1800119f8`
- `0x180027f64`
- `0x180029228`
- `0x1800297f8`

## callees

- `0x180011f00`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall WriteWord(__int64 a1, __int16 a2, unsigned int a3)
{
  __int64 v3; // r9
  __int64 v5; // rdi
  unsigned __int8 v6; // si
  unsigned __int64 v7; // rax
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // [rsp+30h] [rbp+8h]
  unsigned __int8 v12; // [rsp+39h] [rbp+11h]

  v12 = HIBYTE(a2);
  v3 = *(_QWORD *)a1;
  v5 = a3;
  v6 = a2;
  if ( !*(_QWORD *)a1 || a3 + 2 < a3 )
    return 1002;
  v7 = *(unsigned int *)(a1 + 8);
  v11 = a3 + 2;
  if ( v11 <= v7 )
  {
LABEL_4:
    *(_WORD *)(v5 + v3) = v12 | (v6 << 8);
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 16) )
    return 1002;
  v9 = 11 * (int)v7 / 0xAu;
  if ( v9 <= v11 )
  {
    *(_DWORD *)(a1 + 8) = a3 + 2;
    LODWORD(v9) = a3 + 2;
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
0x180011f00  mov     [rsp+arg_10], rbx
0x180011f05  mov     [rsp+arg_18], rsi
0x180011f0a  mov     [rsp+arg_8], dx
0x180011f0f  push    rdi
0x180011f10  sub     rsp, 20h
0x180011f14  mov     r9, [rcx]
0x180011f17  mov     rbx, rcx
0x180011f1a  mov     edi, r8d
0x180011f1d  movzx   esi, dx
0x180011f20  mov     [rsp+28h+arg_0], 0
0x180011f29  test    r9, r9
0x180011f2c  jz      short loc_180011F6D
0x180011f2e  lea     r8d, [rdi+2]
0x180011f32  cmp     r8d, edi
0x180011f35  jb      short loc_180011F6D
0x180011f37  mov     eax, [rcx+8]
0x180011f3a  mov     dword ptr [rsp+28h+arg_0], r8d
0x180011f3f  cmp     [rsp+28h+arg_0], rax
0x180011f44  ja      short loc_180011F74
0x180011f46  movzx   eax, byte ptr [rsp+28h+arg_8+1]
0x180011f4b  movzx   ecx, sil
0x180011f4f  shl     cx, 8
0x180011f53  or      cx, ax
0x180011f56  mov     [rdi+r9], cx
0x180011f5b  xor     eax, eax
0x180011f5d  mov     rbx, [rsp+28h+arg_10]
0x180011f62  mov     rsi, [rsp+28h+arg_18]
0x180011f67  add     rsp, 20h
0x180011f6b  pop     rdi
0x180011f6c  retn
0x180011f6d  mov     eax, 3EAh
0x180011f72  jmp     short loc_180011F5D
0x180011f74  cmp     qword ptr [rcx+10h], 0
0x180011f79  jz      short loc_180011F6D
0x180011f7b  imul    ecx, eax, 0Bh
0x180011f7e  mov     eax, 0CCCCCCCDh
0x180011f83  mul     ecx
0x180011f85  shr     edx, 3
0x180011f88  mov     eax, edx
0x180011f8a  cmp     rax, [rsp+28h+arg_0]
0x180011f8f  jbe     short loc_180011F96
0x180011f91  mov     [rbx+8], eax
0x180011f94  jmp     short loc_180011F9D
0x180011f96  mov     [rbx+8], r8d
0x180011f9a  mov     eax, r8d
0x180011f9d  mov     edx, eax
0x180011f9f  mov     rcx, r9
0x180011fa2  mov     rax, [rbx+10h]
0x180011fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fab  mov     [rbx], rax
0x180011fae  mov     r9, rax
0x180011fb1  test    rax, rax
0x180011fb4  jnz     short loc_180011F46
0x180011fb6  mov     [rbx+8], eax
0x180011fb9  mov     eax, 3EDh
0x180011fbe  jmp     short loc_180011F5D
```
