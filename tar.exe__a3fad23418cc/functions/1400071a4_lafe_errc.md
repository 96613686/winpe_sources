# lafe_errc

- ea: `0x1400071a4`
- end: `0x1400071da`
- name: `lafe_errc`
- size: `54`
- prototype: `void __fastcall __noreturn(int Code)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x140001f9c`
- `0x140003718`
- `0x140003f00`
- `0x140003f80`
- `0x140004160`
- `0x14000422c`
- `0x1400049d4`
- `0x140004b20`
- `0x1400050a0`
- `0x140005390`
- `0x140005a74`
- `0x140005bbc`
- `0x140005fc4`
- `0x1400060d4`
- `0x1400061dc`
- `0x1400063bc`
- `0x140006650`
- `0x1400068f4`
- `0x1400069a8`
- `0x140007314`
- `0x1400074d0`

## callees

- `0x1400071f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x1400071d3`
- `api-ms-win-crt-private-l1-1-0!_o_exit` at `0x1400071d3`

## pseudocode

```c
void __noreturn lafe_errc(int Code, unsigned int a2, __int64 a3, ...)
{
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  lafe_vwarnc(a2, a3, (__int64 *)va);
  exit(Code);
}

```

## disassembly

```asm
0x1400071a4  mov     r11, rsp
0x1400071a7  mov     [r11+18h], r8
0x1400071ab  mov     [r11+20h], r9
0x1400071af  push    rbx
0x1400071b0  sub     rsp, 30h
0x1400071b4  mov     r9, r8
0x1400071b7  mov     qword ptr [r11-18h], 0
0x1400071bf  mov     eax, edx
0x1400071c1  lea     r8, [r11+20h]
0x1400071c5  mov     ebx, ecx
0x1400071c7  mov     rdx, r9
0x1400071ca  mov     ecx, eax
0x1400071cc  call    lafe_vwarnc
0x1400071d1  mov     ecx, ebx; Code
0x1400071d3  call    cs:__imp_exit
```
