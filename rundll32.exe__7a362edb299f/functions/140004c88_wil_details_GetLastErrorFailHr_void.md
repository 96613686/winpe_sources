# wil::details::GetLastErrorFailHr(void)

- ea: `0x140004c88`
- end: `0x140004cd6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003b94`
- `0x140003ffc`
- `0x14000897c`

## callees

- `0x14000311c`
- `0x140004c88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c8c`

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
0x140004c88  sub     rsp, 48h
0x140004c8c  call    cs:__imp_GetLastError
0x140004c92  test    eax, eax
0x140004c94  jnz     short loc_140004CC7
0x140004c96  mov     rax, [rsp+48h]
0x140004c9b  xor     r9d, r9d; int
0x140004c9e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140004ca6  xor     r8d, r8d; int
0x140004ca9  mov     [rsp+48h+var_20], rax; __int64
0x140004cae  xor     edx, edx; int
0x140004cb0  xor     ecx, ecx; int
0x140004cb2  mov     [rsp+48h+var_28], 0; __int64
0x140004cbb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004cc0  mov     eax, 29Ch
0x140004cc5  jmp     short loc_140004CC9
0x140004cc7  jle     short loc_140004CD1
0x140004cc9  movzx   eax, ax
0x140004ccc  or      eax, 80070000h
0x140004cd1  add     rsp, 48h
0x140004cd5  retn
```
