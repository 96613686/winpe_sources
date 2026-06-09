# SymCryptEckeyCreate

- ea: `0x1800249c0`
- end: `0x180024a74`
- name: `SymCryptEckeyCreate`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002497c`

## callees

- `0x1800249c0`
- `0x180029364`
- `0x180029ca8`
- `0x18002c2e0`

## pseudocode

```c
__int64 __fastcall SymCryptEckeyCreate(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v4; // r9d
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // r8
  __int64 v8; // rsi
  int v9; // eax
  _DWORD *v10; // rdx
  __int64 result; // rax

  v4 = a3[6] + a3[16];
  if ( v4 )
  {
    if ( v4 <= 0x100000 )
      v5 = (v4 >> 9) + (((v4 & 0x1FF) + 511) >> 9);
    else
      v5 = 0;
  }
  else
  {
    v5 = 1;
  }
  v6 = SymCryptSizeofEcpointEx((unsigned int)a3[9], a3[2] & 0xF);
  *(_DWORD *)a1 = 0;
  *(_BYTE *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = v7;
  v8 = v6;
  *(_QWORD *)(a1 + 16) = SymCryptEcpointCreateEx((_BYTE *)(a1 + 64), v6, v7, *(_DWORD *)(v7 + 8) & 0xF);
  v9 = SymCryptFdefSizeofIntFromDigits(v5);
  if ( v9 )
  {
    v10 = (_DWORD *)(v8 + a1 + 64);
    *v10 = 1732837376;
    v10[1] = v5;
    v10[2] = v9;
  }
  result = a1;
  *(_QWORD *)(a1 + 24) = v10;
  return result;
}

```

## disassembly

```asm
0x1800249c0  mov     [rsp+arg_0], rbx
0x1800249c5  mov     [rsp+arg_8], rsi
0x1800249ca  push    rdi
0x1800249cb  sub     rsp, 20h
0x1800249cf  mov     r9d, [r8+40h]
0x1800249d3  mov     rdi, rcx
0x1800249d6  add     r9d, [r8+18h]
0x1800249da  jnz     short loc_1800249E2
0x1800249dc  lea     ebx, [r9+1]
0x1800249e0  jmp     short loc_180024A05
0x1800249e2  cmp     r9d, 100000h
0x1800249e9  jbe     short loc_1800249EF
0x1800249eb  xor     ebx, ebx
0x1800249ed  jmp     short loc_180024A05
0x1800249ef  mov     ebx, r9d
0x1800249f2  mov     eax, 1FFh
0x1800249f7  and     ebx, eax
0x1800249f9  shr     r9d, 9
0x1800249fd  add     ebx, eax
0x1800249ff  shr     ebx, 9
0x180024a02  add     ebx, r9d
0x180024a05  mov     edx, [r8+8]
0x180024a09  mov     ecx, [r8+24h]
0x180024a0d  and     edx, 0Fh
0x180024a10  call    SymCryptSizeofEcpointEx
0x180024a15  mov     dword ptr [rdi], 0
0x180024a1b  lea     rcx, [rdi+40h]
0x180024a1f  mov     byte ptr [rdi+4], 0
0x180024a23  mov     [rdi+8], r8
0x180024a27  mov     r9d, [r8+8]
0x180024a2b  and     r9d, 0Fh
0x180024a2f  mov     edx, eax
0x180024a31  mov     esi, eax
0x180024a33  call    SymCryptEcpointCreateEx
0x180024a38  mov     ecx, ebx
0x180024a3a  mov     [rdi+10h], rax
0x180024a3e  xor     edx, edx
0x180024a40  call    SymCryptFdefSizeofIntFromDigits
0x180024a45  test    eax, eax
0x180024a47  jz      short loc_180024A5C
0x180024a49  lea     rdx, [rdi+40h]
0x180024a4d  add     rdx, rsi
0x180024a50  mov     dword ptr [rdx], 67490000h
0x180024a56  mov     [rdx+4], ebx
0x180024a59  mov     [rdx+8], eax
0x180024a5c  mov     rbx, [rsp+28h+arg_0]
0x180024a61  mov     rax, rdi
0x180024a64  mov     rsi, [rsp+28h+arg_8]
0x180024a69  mov     [rdi+18h], rdx
0x180024a6d  add     rsp, 20h
0x180024a71  pop     rdi
0x180024a72  retn
```
