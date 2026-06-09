# CWshURLShortcut::GetClassInfoA(ITypeInfo * *)

- ea: `0x180004fd0`
- end: `0x180005001`
- name: `?GetClassInfoA@CWshURLShortcut@@UEAAJPEAPEAUITypeInfo@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(CWshURLShortcut *__hidden this, struct ITypeInfo **)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008560`
- `0x18000d930`

## callees

- `0x180004fd0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWshURLShortcut::GetClassInfoA(CWshURLShortcut *this, struct ITypeInfo **a2)
{
  if ( a2 )
    return (*(__int64 (__fastcall **)(char *, _QWORD, __int64, struct ITypeInfo **))(*((_QWORD *)this - 1) + 32LL))(
             (char *)this - 8,
             0,
             2048,
             a2);
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180004fd0  sub     rsp, 38h
0x180004fd4  test    rdx, rdx
0x180004fd7  jnz     short loc_180004FE3
0x180004fd9  mov     eax, 80004003h
0x180004fde  add     rsp, 38h
0x180004fe2  retn
0x180004fe3  mov     rax, [rcx-8]
0x180004fe7  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180004feb  mov     r9, rdx
0x180004fee  mov     r8d, 800h
0x180004ff4  xor     edx, edx
0x180004ff6  mov     rax, [rax+20h]
0x180004ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fff  jmp     short loc_180004FDE
```
