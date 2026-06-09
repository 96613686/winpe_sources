# wil::details::GetLastErrorFailHr(void)

- ea: `0x1400033d8`
- end: `0x140003426`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400026bc`
- `0x140002a8c`
- `0x14000539c`

## callees

- `0x140001e88`
- `0x1400033d8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400033dc`
- `KERNEL32!GetLastError` at `0x1400033dc`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( result )
  {
    if ( result <= 0 )
      return result;
  }
  else
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    LOWORD(result) = 668;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x1400033d8  sub     rsp, 48h
0x1400033dc  call    cs:__imp_GetLastError
0x1400033e2  test    eax, eax
0x1400033e4  jnz     short loc_140003417
0x1400033e6  mov     rax, [rsp+48h]
0x1400033eb  xor     r9d, r9d; int
0x1400033ee  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1400033f6  xor     r8d, r8d; int
0x1400033f9  mov     [rsp+48h+var_20], rax; __int64
0x1400033fe  xor     edx, edx; int
0x140003400  xor     ecx, ecx; int
0x140003402  mov     [rsp+48h+var_28], 0; __int64
0x14000340b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003410  mov     eax, 29Ch
0x140003415  jmp     short loc_140003419
0x140003417  jle     short loc_140003421
0x140003419  movzx   eax, ax
0x14000341c  or      eax, 80070000h
0x140003421  add     rsp, 48h
0x140003425  retn
```
