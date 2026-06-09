# WdipCreatePortAttributes

- ea: `0x180003ef0`
- end: `0x180003f37`
- name: `WdipCreatePortAttributes`
- size: `71`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180009f18`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x180003eff`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180003eff`

## pseudocode

```c
__int64 __fastcall WdipCreatePortAttributes(__int64 a1)
{
  __int64 result; // rax

  *(_DWORD *)a1 = 393216;
  *(_QWORD *)(a1 + 16) = AlpcMaxAllowedMessageLength();
  result = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 4) = 0;
  *(_DWORD *)(a1 + 12) = 0;
  *(_DWORD *)(a1 + 4) = 12;
  *(_BYTE *)(a1 + 12) = 1;
  return result;
}

```

## disassembly

```asm
0x180003ef0  push    rbx
0x180003ef2  sub     rsp, 20h
0x180003ef6  mov     rbx, rcx
0x180003ef9  mov     dword ptr [rcx], 60000h
0x180003eff  call    cs:__imp_AlpcMaxAllowedMessageLength
0x180003f05  mov     [rbx+10h], rax
0x180003f09  xor     eax, eax
0x180003f0b  mov     [rbx+20h], rax
0x180003f0f  mov     [rbx+28h], rax
0x180003f13  mov     [rbx+38h], rax
0x180003f17  mov     [rbx+30h], rax
0x180003f1b  mov     [rbx+18h], rax
0x180003f1f  mov     [rbx+4], rax
0x180003f23  mov     [rbx+0Ch], eax
0x180003f26  mov     dword ptr [rbx+4], 0Ch
0x180003f2d  mov     byte ptr [rbx+0Ch], 1
0x180003f31  add     rsp, 20h
0x180003f35  pop     rbx
0x180003f36  retn
```
