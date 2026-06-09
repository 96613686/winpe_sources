# RtlReportErrorOrigination

- ea: `0x180007568`
- end: `0x180007599`
- name: `RtlReportErrorOrigination`
- size: `49`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `40`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800020d0`
- `0x1800022c4`
- `0x1800047f0`
- `0x1800075a0`
- `0x180007620`
- `0x1800077f4`
- `0x1800078c8`
- `0x180007bcc`
- `0x180007cc0`
- `0x180007d8c`
- `0x180007ed8`
- `0x180007f68`
- `0x180008248`
- `0x180008954`
- `0x180008aac`
- `0x180008e30`
- `0x180009150`
- `0x1800092dc`
- `0x1800097dc`
- `0x180009a88`
- `0x180009be8`
- `0x180009cb4`
- `0x180009e30`
- `0x18000a384`
- `0x18000a570`
- `0x1800118a4`
- `0x1800119e8`
- `0x1800134c0`
- `0x1800136a0`
- `0x1800191d0`
- `0x18001a17c`
- `0x18001a260`
- `0x18001aa14`
- `0x18001ab5c`
- `0x18001ad50`
- `0x18001aed4`
- `0x18001b048`
- `0x18001b30c`
- `0x18001b698`

## callees

- `0x180007568`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000758e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000758e`

## pseudocode

```c
void __fastcall RtlReportErrorOrigination(__int64 a1, __int64 a2, int a3)
{
  if ( a3 == g_NTSTATUS_to_break_on )
    __debugbreak();
  if ( a3 == -1073741595 )
    RaiseException(0xC0000420, 1u, 0, 0);
}

```

## disassembly

```asm
0x180007568  sub     rsp, 28h
0x18000756c  cmp     r8d, cs:g_NTSTATUS_to_break_on
0x180007573  jnz     short loc_180007576
0x180007575  int     3; Trap to Debugger
0x180007576  cmp     r8d, 0C00000E5h
0x18000757d  jnz     short loc_180007594
0x18000757f  xor     r9d, r9d; lpArguments
0x180007582  xor     r8d, r8d; nNumberOfArguments
0x180007585  mov     ecx, 0C0000420h; dwExceptionCode
0x18000758a  lea     edx, [r9+1]; dwExceptionFlags
0x18000758e  call    cs:__imp_RaiseException
0x180007594  add     rsp, 28h
0x180007598  retn
```
