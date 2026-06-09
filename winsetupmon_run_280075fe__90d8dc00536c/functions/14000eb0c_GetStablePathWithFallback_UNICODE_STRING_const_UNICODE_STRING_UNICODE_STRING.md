# GetStablePathWithFallback(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14000eb0c`
- end: `0x14000eb61`
- name: `?GetStablePathWithFallback@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z`
- size: `85`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PUNICODE_STRING DestinationString, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140001a94`
- `0x14000c410`

## callees

- `0x14000dd24`
- `0x14000e1d0`
- `0x14000e778`
- `0x14000eb0c`

## pseudocode

```c
__int64 __fastcall GetStablePathWithFallback(
        PCUNICODE_STRING String2,
        PUNICODE_STRING DestinationString,
        struct _UNICODE_STRING *a3)
{
  __int64 result; // rax

  result = GetStablePath(String2, DestinationString, a3);
  if ( (_DWORD)result == -1073741637 )
  {
    result = GetNtPath(String2, DestinationString, a3);
    if ( (_DWORD)result == -1073741637 )
      return Duplicate(String2, DestinationString);
  }
  return result;
}

```

## disassembly

```asm
0x14000eb0c  mov     [rsp+arg_0], rbx
0x14000eb11  mov     [rsp+arg_8], rsi
0x14000eb16  push    rdi
0x14000eb17  sub     rsp, 20h
0x14000eb1b  mov     rsi, r8
0x14000eb1e  mov     rbx, rdx
0x14000eb21  mov     rdi, rcx
0x14000eb24  call    ?GetStablePath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetStablePath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000eb29  cmp     eax, 0C00000BBh
0x14000eb2e  jnz     short loc_14000EB50
0x14000eb30  mov     r8, rsi; struct _UNICODE_STRING *
0x14000eb33  mov     rdx, rbx; DestinationString
0x14000eb36  mov     rcx, rdi; String2
0x14000eb39  call    ?GetNtPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetNtPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000eb3e  cmp     eax, 0C00000BBh
0x14000eb43  jnz     short loc_14000EB50
0x14000eb45  mov     rdx, rbx; DestinationString
0x14000eb48  mov     rcx, rdi; SourceString
0x14000eb4b  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x14000eb50  mov     rbx, [rsp+28h+arg_0]
0x14000eb55  mov     rsi, [rsp+28h+arg_8]
0x14000eb5a  add     rsp, 20h
0x14000eb5e  pop     rdi
0x14000eb5f  retn
```
