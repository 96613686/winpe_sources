# CheckOutOffset

- ea: `0x180012020`
- end: `0x1800120b6`
- name: `CheckOutOffset`
- size: `150`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fd44`
- `0x180010b90`
- `0x180011fc8`
- `0x18002738c`
- `0x1800273f4`

## callees

- `0x180012020`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CheckOutOffset(__int64 *a1, unsigned int a2, unsigned __int64 a3)
{
  __int64 v3; // r10
  unsigned int v5; // r9d
  unsigned __int64 v6; // rax
  __int64 (__fastcall *v8)(__int64, _QWORD); // r11
  unsigned __int64 v9; // rax
  __int64 v10; // rax

  v3 = *a1;
  if ( !*a1 )
    return 1002;
  if ( a3 > 0xFFFFFFFF )
    return 1002;
  v5 = a3 + a2;
  if ( (unsigned int)a3 + a2 < a2 )
    return 1002;
  v6 = *((unsigned int *)a1 + 2);
  if ( v5 <= v6 )
    return 0;
  v8 = (__int64 (__fastcall *)(__int64, _QWORD))a1[2];
  if ( !v8 )
    return 1002;
  v9 = 11 * (int)v6 / 0xAu;
  if ( v9 <= v5 )
  {
    *((_DWORD *)a1 + 2) = v5;
    LODWORD(v9) = a3 + a2;
  }
  else
  {
    *((_DWORD *)a1 + 2) = v9;
  }
  v10 = v8(v3, (unsigned int)v9);
  *a1 = v10;
  if ( v10 )
    return 0;
  *((_DWORD *)a1 + 2) = 0;
  return 1005;
}

```

## disassembly

```asm
0x180012020  push    rbx
0x180012022  sub     rsp, 20h
0x180012026  mov     r10, [rcx]
0x180012029  mov     rbx, rcx
0x18001202c  mov     [rsp+28h+arg_0], 0
0x180012035  test    r10, r10
0x180012038  jz      short loc_180012067
0x18001203a  mov     eax, 0FFFFFFFFh
0x18001203f  cmp     r8, rax
0x180012042  ja      short loc_180012067
0x180012044  lea     r9d, [r8+rdx]
0x180012048  cmp     r9d, edx
0x18001204b  jb      short loc_180012067
0x18001204d  mov     eax, [rcx+8]
0x180012050  mov     dword ptr [rsp+28h+arg_0], r9d
0x180012055  mov     r8, [rsp+28h+arg_0]
0x18001205a  cmp     r8, rax
0x18001205d  ja      short loc_18001206E
0x18001205f  xor     eax, eax
0x180012061  add     rsp, 20h
0x180012065  pop     rbx
0x180012066  retn
0x180012067  mov     eax, 3EAh
0x18001206c  jmp     short loc_180012061
0x18001206e  mov     r11, [rcx+10h]
0x180012072  test    r11, r11
0x180012075  jz      short loc_180012067
0x180012077  imul    ecx, eax, 0Bh
0x18001207a  mov     eax, 0CCCCCCCDh
0x18001207f  mul     ecx
0x180012081  shr     edx, 3
0x180012084  mov     eax, edx
0x180012086  cmp     rax, r8
0x180012089  jbe     short loc_180012090
0x18001208b  mov     [rbx+8], eax
0x18001208e  jmp     short loc_180012097
0x180012090  mov     [rbx+8], r9d
0x180012094  mov     eax, r9d
0x180012097  mov     edx, eax
0x180012099  mov     rcx, r10
0x18001209c  mov     rax, r11
0x18001209f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a4  mov     [rbx], rax
0x1800120a7  test    rax, rax
0x1800120aa  jnz     short loc_18001205F
0x1800120ac  mov     [rbx+8], eax
0x1800120af  mov     eax, 3EDh
0x1800120b4  jmp     short loc_180012061
```
