# SymCryptModElementSetValueUint32

- ea: `0x18002565c`
- end: `0x1800256af`
- name: `SymCryptModElementSetValueUint32`
- size: `83`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180023e94`
- `0x180029704`
- `0x18002cac8`
- `0x18002cc18`
- `0x180030da0`
- `0x180031d60`
- `0x1800323d0`

## callees

- `0x18002af7c`

## pseudocode

```c
__int64 __fastcall SymCryptModElementSetValueUint32(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4, __int64 a5)
{
  SymCryptFdefModElementSetValueUint32Generic();
  return (*(__int64 (__fastcall **)(_DWORD *, __int64, __int64, __int64))((char *)off_180035130 + (*a2 & 0x380)))(
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x18002565c  mov     [rsp+arg_0], rbx
0x180025661  mov     [rsp+arg_8], rsi
0x180025666  push    rdi
0x180025667  sub     rsp, 30h
0x18002566b  mov     rbx, r9
0x18002566e  mov     rdi, r8
0x180025671  mov     rsi, rdx
0x180025674  call    SymCryptFdefModElementSetValueUint32Generic
0x180025679  mov     eax, [rsi]
0x18002567b  lea     rcx, off_180035130
0x180025682  mov     r9, [rsp+38h+arg_20]
0x180025687  and     eax, 380h
0x18002568c  mov     r8, rbx
0x18002568f  mov     rdx, rdi
0x180025692  mov     rax, [rax+rcx]
0x180025696  mov     rcx, rsi
0x180025699  call    rax
0x18002569b  nop     dword ptr [rax]
0x18002569e  mov     rbx, [rsp+38h+arg_0]
0x1800256a3  mov     rsi, [rsp+38h+arg_8]
0x1800256a8  add     rsp, 30h
0x1800256ac  pop     rdi
0x1800256ad  retn
```
