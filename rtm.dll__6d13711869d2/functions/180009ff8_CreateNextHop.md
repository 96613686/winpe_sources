# CreateNextHop

- ea: `0x180009ff8`
- end: `0x18000a0a7`
- name: `CreateNextHop`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008910`

## callees

- `0x180009ff8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000a029`
- `KERNEL32!HeapAlloc` at `0x18000a029`
- `KERNEL32!GetProcessHeap` at `0x18000a017`
- `KERNEL32!GetProcessHeap` at `0x18000a017`

## pseudocode

```c
__int64 __fastcall CreateNextHop(volatile signed __int32 *a1, __int64 a2, _QWORD *a3)
{
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  char *v8; // r9
  __int64 v10; // rax

  *a3 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 8u, 0x50u);
  v8 = v7;
  if ( !v7 )
    return 8;
  _InterlockedIncrement((volatile signed __int32 *)v7);
  *(_OWORD *)(v7 + 24) = *(_OWORD *)a2;
  *((_DWORD *)v7 + 10) = *(_DWORD *)(a2 + 16);
  *((_QWORD *)v7 + 6) = (unsigned __int64)a1 ^ 0x7754DF32;
  *((_DWORD *)v7 + 14) = *(_DWORD *)(a2 + 32);
  _InterlockedIncrement(a1);
  *((_WORD *)v7 + 30) = 0;
  *((_WORD *)v7 + 31) = *(_WORD *)(a2 + 38);
  *((_QWORD *)v7 + 8) = *(_QWORD *)(a2 + 40);
  v10 = *(_QWORD *)(a2 + 48);
  *((_QWORD *)v8 + 9) = v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 ^ 0x7754DF32));
  *a3 = v8;
  return 0;
}

```

## disassembly

```asm
0x180009ff8  mov     [rsp+arg_0], rbx
0x180009ffd  mov     [rsp+arg_8], rsi
0x18000a002  push    rdi
0x18000a003  sub     rsp, 20h
0x18000a007  mov     rbx, r8
0x18000a00a  mov     qword ptr [r8], 0
0x18000a011  mov     rdi, rdx
0x18000a014  mov     rsi, rcx
0x18000a017  call    cs:__imp_GetProcessHeap
0x18000a01d  mov     edx, 8; dwFlags
0x18000a022  mov     rcx, rax; hHeap
0x18000a025  lea     r8d, [rdx+48h]; dwBytes
0x18000a029  call    cs:__imp_HeapAlloc
0x18000a02f  mov     r9, rax
0x18000a032  test    rax, rax
0x18000a035  jnz     short loc_18000A03D
0x18000a037  lea     eax, [r9+8]
0x18000a03b  jmp     short loc_18000A097
0x18000a03d  lock inc dword ptr [rax]
0x18000a040  movups  xmm0, xmmword ptr [rdi]
0x18000a043  mov     ecx, 7754DF32h
0x18000a048  movups  xmmword ptr [rax+18h], xmm0
0x18000a04c  mov     eax, [rdi+10h]
0x18000a04f  mov     [r9+28h], eax
0x18000a053  mov     rax, rsi
0x18000a056  xor     rax, rcx
0x18000a059  mov     [r9+30h], rax
0x18000a05d  mov     eax, [rdi+20h]
0x18000a060  mov     [r9+38h], eax
0x18000a064  lock inc dword ptr [rsi]
0x18000a067  xor     eax, eax
0x18000a069  mov     [r9+3Ch], ax
0x18000a06e  movzx   eax, word ptr [rdi+26h]
0x18000a072  mov     [r9+3Eh], ax
0x18000a077  mov     rax, [rdi+28h]
0x18000a07b  mov     [r9+40h], rax
0x18000a07f  mov     rax, [rdi+30h]
0x18000a083  mov     [r9+48h], rax
0x18000a087  test    rax, rax
0x18000a08a  jz      short loc_18000A092
0x18000a08c  xor     rax, rcx
0x18000a08f  lock inc dword ptr [rax]
0x18000a092  mov     [rbx], r9
0x18000a095  xor     eax, eax
0x18000a097  mov     rbx, [rsp+28h+arg_0]
0x18000a09c  mov     rsi, [rsp+28h+arg_8]
0x18000a0a1  add     rsp, 20h
0x18000a0a5  pop     rdi
0x18000a0a6  retn
```
