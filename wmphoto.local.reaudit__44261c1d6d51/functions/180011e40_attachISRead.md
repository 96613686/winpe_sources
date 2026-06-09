# attachISRead

- ea: `0x180011e40`
- end: `0x180011edc`
- name: `attachISRead`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011de8`
- `0x180011ee4`

## callees

- `0x180011e40`
- `0x180045010`

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
0x180011e40  mov     [rsp+arg_0], rbx
0x180011e45  mov     [rsp+arg_8], rsi
0x180011e4a  push    rdi
0x180011e4b  sub     rsp, 20h
0x180011e4f  mov     rdi, rdx
0x180011e52  lea     rsi, [rcx+28h]
0x180011e56  mov     rbx, rcx
0x180011e59  mov     rdx, rsi
0x180011e5c  mov     rcx, rdi
0x180011e5f  mov     rax, [rdi+60h]
0x180011e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e68  mov     rdx, [rsi]
0x180011e6b  lea     rax, [rbx-2000h]
0x180011e72  mov     [rbx+10h], rax
0x180011e76  mov     rcx, rdi
0x180011e79  mov     [rbx+18h], rax
0x180011e7d  mov     rax, [rdi+58h]
0x180011e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e86  test    eax, eax
0x180011e88  jnz     short loc_180011ED7
0x180011e8a  mov     rdx, [rbx+10h]
0x180011e8e  mov     r8d, 2000h
0x180011e94  mov     rax, [rdi+40h]
0x180011e98  mov     rcx, rdi
0x180011e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea0  mov     rax, [rbx+10h]
0x180011ea4  add     qword ptr [rsi], 2000h
0x180011eab  mov     ecx, [rax]
0x180011ead  xor     eax, eax
0x180011eaf  bswap   ecx
0x180011eb1  mov     [rbx+4], ecx
0x180011eb4  mov     dword ptr [rbx+8], 0
0x180011ebb  mov     dword ptr [rbx+0Ch], 0FFFFDFFEh
0x180011ec2  mov     [rbx+20h], rdi
0x180011ec6  mov     rbx, [rsp+28h+arg_0]
0x180011ecb  mov     rsi, [rsp+28h+arg_8]
0x180011ed0  add     rsp, 20h
0x180011ed4  pop     rdi
0x180011ed5  retn
0x180011ed7  or      eax, 0FFFFFFFFh
0x180011eda  jmp     short loc_180011EC6
```
