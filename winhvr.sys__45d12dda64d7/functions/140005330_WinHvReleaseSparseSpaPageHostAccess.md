# WinHvReleaseSparseSpaPageHostAccess

- ea: `0x140005330`
- end: `0x1400053ae`
- name: `WinHvReleaseSparseSpaPageHostAccess`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003b70`

## pseudocode

```c
__int64 __fastcall WinHvReleaseSparseSpaPageHostAccess(
        __int64 a1,
        char a2,
        int a3,
        unsigned __int64 a4,
        char *a5,
        _QWORD *a6)
{
  _DWORD v7[2]; // [rsp+80h] [rbp-18h] BYREF
  __int64 v8; // [rsp+88h] [rbp-10h]

  v8 = a1;
  v7[1] = a3;
  v7[0] = a2 & 3;
  return WinHvpSpecialListRepHypercall(216, a4, v7, 0x10u, 0, 0, a5, 8u, 0, 0, 0, 0, 0, 0, a6);
}

```

## disassembly

```asm
0x140005330  mov     r11, rsp
0x140005333  sub     rsp, 98h
0x14000533a  mov     al, dl
0x14000533c  mov     [r11-10h], rcx
0x140005340  xor     ecx, ecx
0x140005342  mov     [r11-14h], r8d
0x140005346  and     eax, 3
0x140005349  lea     r8, [r11-18h]
0x14000534d  mov     [r11-18h], eax
0x140005351  mov     r10, r9
0x140005354  mov     rax, [rsp+98h+arg_28]
0x14000535c  mov     rdx, r10
0x14000535f  mov     [r11-28h], rax
0x140005363  lea     r9d, [rcx+10h]
0x140005367  mov     rax, [rsp+98h+arg_20]
0x14000536f  mov     [r11-30h], rcx
0x140005373  mov     [r11-38h], rcx
0x140005377  mov     [rsp+98h+var_40], ecx
0x14000537b  mov     [r11-48h], rcx
0x14000537f  mov     [r11-50h], rcx
0x140005383  mov     [r11-58h], rcx
0x140005387  mov     [rsp+98h+var_60], 8
0x14000538f  mov     [r11-68h], rax
0x140005393  mov     [r11-70h], rcx
0x140005397  mov     [r11-78h], rcx
0x14000539b  mov     ecx, 0D8h
0x1400053a0  call    WinHvpSpecialListRepHypercall
0x1400053a5  add     rsp, 98h
0x1400053ac  retn
```
