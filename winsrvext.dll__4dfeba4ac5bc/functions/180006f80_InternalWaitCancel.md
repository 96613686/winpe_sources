# InternalWaitCancel

- ea: `0x180006f80`
- end: `0x180006fcc`
- name: `InternalWaitCancel`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180005474`
- `0x18000592c`

## import_xrefs

- `ntdll!NtWaitForMultipleObjects` at `0x180006fba`
- `ntdll!NtWaitForMultipleObjects` at `0x180006fba`

## pseudocode

```c
NTSTATUS __fastcall InternalWaitCancel(void *a1, unsigned int a2)
{
  HANDLE v3[3]; // [rsp+30h] [rbp-18h] BYREF
  union _LARGE_INTEGER v4; // [rsp+50h] [rbp+8h] BYREF

  v3[1] = gheventCancel;
  v3[0] = a1;
  v4.QuadPart = -10000LL * a2;
  return NtWaitForMultipleObjects(2u, v3, WaitAny, 0, &v4);
}

```

## disassembly

```asm
0x180006f80  mov     r11, rsp
0x180006f83  sub     rsp, 48h
0x180006f87  mov     rax, cs:gheventCancel
0x180006f8e  xor     r9d, r9d; Alertable
0x180006f91  mov     [r11-10h], rax
0x180006f95  mov     eax, edx
0x180006f97  lea     rdx, [r11-18h]; Object
0x180006f9b  mov     [r11-18h], rcx
0x180006f9f  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x180006fa6  lea     rax, [r11+8]
0x180006faa  mov     [r11+8], rcx
0x180006fae  lea     r8d, [r9+1]; WaitType
0x180006fb2  lea     ecx, [r9+2]; Count
0x180006fb6  mov     [r11-28h], rax
0x180006fba  call    cs:__imp_NtWaitForMultipleObjects
0x180006fc1  nop     dword ptr [rax+rax+00h]
0x180006fc6  add     rsp, 48h
0x180006fca  retn
```
