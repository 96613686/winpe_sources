# attachISRead

- ea: `0x180011c40`
- end: `0x180011cdb`
- name: `attachISRead`
- size: `155`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011be8`
- `0x180011ce4`

## callees

- `0x180011c40`
- `0x180044010`

## pseudocode

```c
__int64 __fastcall attachISRead(__int64 a1, __int64 a2)
{
  __int64 *v3; // rsi
  __int64 v5; // rdx
  unsigned int *v6; // rax
  unsigned int v7; // ecx
  __int64 result; // rax

  v3 = (__int64 *)(a1 + 40);
  (*(void (__fastcall **)(__int64, __int64))(a2 + 96))(a2, a1 + 40);
  v5 = *v3;
  *(_QWORD *)(a1 + 16) = a1 - 0x2000;
  *(_QWORD *)(a1 + 24) = a1 - 0x2000;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(a2 + 88))(a2, v5) )
    return 0xFFFFFFFFLL;
  (*(void (__fastcall **)(__int64, _QWORD, __int64))(a2 + 64))(a2, *(_QWORD *)(a1 + 16), 0x2000);
  v6 = *(unsigned int **)(a1 + 16);
  *v3 += 0x2000;
  v7 = *v6;
  result = 0;
  *(_QWORD *)(a1 + 4) = _byteswap_ulong(v7);
  *(_DWORD *)(a1 + 12) = -8194;
  *(_QWORD *)(a1 + 32) = a2;
  return result;
}

```

## disassembly

```asm
0x180011c40  mov     [rsp+arg_0], rbx
0x180011c45  mov     [rsp+arg_8], rsi
0x180011c4a  push    rdi
0x180011c4b  sub     rsp, 20h
0x180011c4f  mov     rdi, rdx
0x180011c52  lea     rsi, [rcx+28h]
0x180011c56  mov     rbx, rcx
0x180011c59  mov     rdx, rsi
0x180011c5c  mov     rcx, rdi
0x180011c5f  mov     rax, [rdi+60h]
0x180011c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c68  mov     rdx, [rsi]
0x180011c6b  lea     rax, [rbx-2000h]
0x180011c72  mov     [rbx+10h], rax
0x180011c76  mov     rcx, rdi
0x180011c79  mov     [rbx+18h], rax
0x180011c7d  mov     rax, [rdi+58h]
0x180011c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c86  test    eax, eax
0x180011c88  jnz     short loc_180011CD6
0x180011c8a  mov     rdx, [rbx+10h]
0x180011c8e  mov     r8d, 2000h
0x180011c94  mov     rax, [rdi+40h]
0x180011c98  mov     rcx, rdi
0x180011c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ca0  mov     rax, [rbx+10h]
0x180011ca4  add     qword ptr [rsi], 2000h
0x180011cab  mov     ecx, [rax]
0x180011cad  xor     eax, eax
0x180011caf  bswap   ecx
0x180011cb1  mov     [rbx+4], ecx
0x180011cb4  mov     dword ptr [rbx+8], 0
0x180011cbb  mov     dword ptr [rbx+0Ch], 0FFFFDFFEh
0x180011cc2  mov     [rbx+20h], rdi
0x180011cc6  mov     rbx, [rsp+28h+arg_0]
0x180011ccb  mov     rsi, [rsp+28h+arg_8]
0x180011cd0  add     rsp, 20h
0x180011cd4  pop     rdi
0x180011cd5  retn
0x180011cd6  or      eax, 0FFFFFFFFh
0x180011cd9  jmp     short loc_180011CC6
```
