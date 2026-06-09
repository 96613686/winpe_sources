# ConstructPathName

- ea: `0x180008d30`
- end: `0x180008d85`
- name: `ConstructPathName`
- size: `85`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800096f8`
- `0x18000a288`
- `0x18000d1c0`

## callees

- `0x180005da4`
- `0x180008d30`
- `0x180009648`
- `0x18002262c`

## pseudocode

```c
_BOOL8 __fastcall ConstructPathName(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a2, unsigned __int16 *a3)
{
  size_t v5; // rdx

  return StringCchCopyW(a3, 0x104u, pszSrc) >= 0 && StringCbAppendWackW(a3) && StringCchCatW(a3, v5, a2) >= 0;
}

```

## disassembly

```asm
0x180008d30  mov     [rsp+arg_0], rbx
0x180008d35  push    rdi
0x180008d36  sub     rsp, 20h
0x180008d3a  mov     rbx, r8
0x180008d3d  mov     rdi, rdx
0x180008d40  mov     r8, rcx; pszSrc
0x180008d43  mov     edx, 104h; cchDest
0x180008d48  mov     rcx, rbx; pszDest
0x180008d4b  call    StringCchCopyW
0x180008d50  test    eax, eax
0x180008d52  js      short loc_180008D77
0x180008d54  mov     rcx, rbx; unsigned __int16 *
0x180008d57  call    StringCbAppendWackW
0x180008d5c  test    rax, rax
0x180008d5f  jz      short loc_180008D77
0x180008d61  mov     r8, rdi; pszSrc
0x180008d64  mov     rcx, rbx; pszDest
0x180008d67  call    StringCchCatW
0x180008d6c  xor     ecx, ecx
0x180008d6e  test    eax, eax
0x180008d70  setns   cl
0x180008d73  mov     eax, ecx
0x180008d75  jmp     short loc_180008D79
0x180008d77  xor     eax, eax
0x180008d79  mov     rbx, [rsp+28h+arg_0]
0x180008d7e  add     rsp, 20h
0x180008d82  pop     rdi
0x180008d83  retn
```
