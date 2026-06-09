# INIT_OBJA_EX

- ea: `0x180001c74`
- end: `0x180001cce`
- name: `INIT_OBJA_EX`
- size: `90`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, const WCHAR *, int, __int64)`
- caller_count: `13`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004428`
- `0x180004f5c`
- `0x180008d44`
- `0x180009864`
- `0x180009904`
- `0x18000c73c`
- `0x18000d620`
- `0x18000e4e4`
- `0x18000e66c`
- `0x18000e740`
- `0x18000e8d4`
- `0x18000ec38`
- `0x18000f7e4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180001c92`
- `ntdll!RtlInitUnicodeString` at `0x180001c92`

## pseudocode

```c
__int64 __fastcall INIT_OBJA_EX(__int64 a1, struct _UNICODE_STRING *a2, const WCHAR *a3, int a4, __int64 a5)
{
  __int64 result; // rax

  RtlInitUnicodeString(a2, a3);
  result = a5;
  *(_QWORD *)(a1 + 16) = a2;
  *(_QWORD *)(a1 + 8) = a5;
  *(_DWORD *)a1 = 48;
  *(_DWORD *)(a1 + 24) = a4;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x180001c74  mov     [rsp+arg_0], rbx
0x180001c79  mov     [rsp+arg_8], rsi
0x180001c7e  push    rdi
0x180001c7f  sub     rsp, 20h
0x180001c83  mov     rbx, rdx
0x180001c86  mov     rsi, rcx
0x180001c89  mov     rcx, rbx; DestinationString
0x180001c8c  mov     rdx, r8; SourceString
0x180001c8f  mov     edi, r9d
0x180001c92  call    cs:__imp_RtlInitUnicodeString
0x180001c98  mov     rax, [rsp+28h+arg_20]
0x180001c9d  mov     [rsi+10h], rbx
0x180001ca1  mov     rbx, [rsp+28h+arg_0]
0x180001ca6  mov     [rsi+8], rax
0x180001caa  mov     dword ptr [rsi], 30h ; '0'
0x180001cb0  mov     [rsi+18h], edi
0x180001cb3  mov     qword ptr [rsi+20h], 0
0x180001cbb  mov     qword ptr [rsi+28h], 0
0x180001cc3  mov     rsi, [rsp+28h+arg_8]
0x180001cc8  add     rsp, 20h
0x180001ccc  pop     rdi
0x180001ccd  retn
```
