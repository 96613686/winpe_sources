# BaseSrvSxsCreateProcess

- ea: `0x180001cd0`
- end: `0x180001d76`
- name: `BaseSrvSxsCreateProcess`
- size: `166`
- prototype: `__int64 __fastcall(void *, void *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001440`
- `0x180001cd0`
- `0x180001d80`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsCreateProcess(void *a1, void *a2, __int64 a3)
{
  __int64 v4; // rbp
  __int64 *v7; // rdi
  __int64 result; // rax
  unsigned __int16 v9; // cx

  v4 = *(_QWORD *)(a3 + 576);
  if ( *(int *)(a3 + 96) < 0 )
  {
    v7 = (__int64 *)(a3 + 584);
    return InternalSxsCreateProcess(a1, a2, a3, v4, *v7);
  }
  v9 = *(_WORD *)(a3 + 592);
  if ( v9 )
  {
    if ( v9 == 5 )
      v9 = 13;
  }
  else
  {
    v9 = 10;
  }
  v7 = (__int64 *)(a3 + 584);
  result = BaseSrvSxsDoSystemDefaultActivationContext(
             v9,
             (union _LARGE_INTEGER)a2,
             *(_QWORD *)(a3 + 576),
             *(_QWORD *)(a3 + 584));
  if ( (int)result >= 0 )
    return InternalSxsCreateProcess(a1, a2, a3, v4, *v7);
  return result;
}

```

## disassembly

```asm
0x180001cd0  mov     [rsp+arg_0], rbx
0x180001cd5  mov     [rsp+arg_8], rbp
0x180001cda  mov     [rsp+arg_10], rsi
0x180001cdf  mov     [rsp+arg_18], rdi
0x180001ce4  push    r14
0x180001ce6  sub     rsp, 30h
0x180001cea  cmp     dword ptr [r8+60h], 0
0x180001cef  mov     rbx, r8
0x180001cf2  mov     rbp, [r8+240h]
0x180001cf9  mov     rsi, rdx
0x180001cfc  mov     r14, rcx
0x180001cff  jge     short loc_180001D3D
0x180001d01  lea     rdi, [r8+248h]
0x180001d08  mov     rax, [rdi]
0x180001d0b  mov     r9, rbp
0x180001d0e  mov     r8, rbx
0x180001d11  mov     [rsp+38h+var_18], rax
0x180001d16  mov     rdx, rsi
0x180001d19  mov     rcx, r14
0x180001d1c  call    InternalSxsCreateProcess
0x180001d21  mov     rbx, [rsp+38h+arg_0]
0x180001d26  mov     rbp, [rsp+38h+arg_8]
0x180001d2b  mov     rsi, [rsp+38h+arg_10]
0x180001d30  mov     rdi, [rsp+38h+arg_18]
0x180001d35  add     rsp, 30h
0x180001d39  pop     r14
0x180001d3b  retn
0x180001d3d  movzx   ecx, word ptr [r8+250h]
0x180001d45  test    cx, cx
0x180001d48  jz      short loc_180001D68
0x180001d4a  cmp     cx, 5
0x180001d4e  jz      short loc_180001D6F
0x180001d50  lea     rdi, [r8+248h]
0x180001d57  mov     r8, rbp
0x180001d5a  mov     r9, [rdi]
0x180001d5d  call    BaseSrvSxsDoSystemDefaultActivationContext
0x180001d62  test    eax, eax
0x180001d64  js      short loc_180001D21
0x180001d66  jmp     short loc_180001D08
0x180001d68  mov     ecx, 0Ah
0x180001d6d  jmp     short loc_180001D50
0x180001d6f  mov     ecx, 0Dh
0x180001d74  jmp     short loc_180001D50
```
