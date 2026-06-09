# BufferCreated

- ea: `0x140003bd0`
- end: `0x140003c1b`
- name: `BufferCreated`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003bd0`
- `0x140017190`

## pseudocode

```c
__int64 __fastcall BufferCreated(int a1, int a2, __int64 a3)
{
  __int64 v3; // r11
  _DWORD *v4; // rax

  v3 = *(_QWORD *)(a3 + 8);
  if ( a1 >= 0 )
  {
    v4 = *(_DWORD **)(a3 + 16);
    *(_DWORD *)(a3 + 4) = a2;
    *v4 = a2;
  }
  _InterlockedExchange64((volatile __int64 *)(a3 + 24), 0);
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD, __int64))(WdfFunctions_01033 + 2120))(
           WdfDriverGlobals,
           v3,
           (unsigned int)a1,
           4);
}

```

## disassembly

```asm
0x140003bd0  sub     rsp, 38h
0x140003bd4  mov     r11, [r8+8]
0x140003bd8  mov     r10d, ecx
0x140003bdb  test    ecx, ecx
0x140003bdd  js      short loc_140003BE9
0x140003bdf  mov     rax, [r8+10h]
0x140003be3  mov     [r8+4], edx
0x140003be7  mov     [rax], edx
0x140003be9  xor     eax, eax
0x140003beb  mov     r9d, 4
0x140003bf1  xchg    rax, [r8+18h]
0x140003bf5  mov     rcx, cs:WdfFunctions_01033
0x140003bfc  mov     r8d, r10d
0x140003bff  mov     rdx, r11
0x140003c02  mov     rax, [rcx+848h]
0x140003c09  mov     rcx, cs:WdfDriverGlobals
0x140003c10  call    _guard_dispatch_icall
0x140003c15  add     rsp, 38h
0x140003c19  retn
```
