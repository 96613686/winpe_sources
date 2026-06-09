# wil::details::GetLastErrorFailHr(void)

- ea: `0x180008834`
- end: `0x180008885`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042fc`
- `0x180008080`
- `0x18000845c`

## callees

- `0x1800034d8`
- `0x180008834`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000883f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000883f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this)
{
  signed int result; // eax
  wil::details *v2; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  result = GetLastError();
  if ( !result )
  {
    LODWORD(v2) = -2147024228;
    wil::details::ReportFailure_Hr<2>(0, 0, 0, 0, 0, retaddr, v2);
    result = 668;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008834  push    rbx
0x180008836  sub     rsp, 40h
0x18000883a  mov     rbx, [rsp+48h]
0x18000883f  call    cs:__imp_GetLastError
0x180008845  test    eax, eax
0x180008847  jnz     short loc_180008873
0x180008849  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180008851  mov     [rsp+48h+var_20], rbx; __int64
0x180008856  mov     [rsp+48h+var_28], 0; __int64
0x18000885f  xor     r9d, r9d; int
0x180008862  xor     r8d, r8d; int
0x180008865  xor     edx, edx; int
0x180008867  xor     ecx, ecx; int
0x180008869  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000886e  mov     eax, 29Ch
0x180008873  test    eax, eax
0x180008875  jle     short loc_18000887F
0x180008877  movzx   eax, ax
0x18000887a  or      eax, 80070000h
0x18000887f  add     rsp, 40h
0x180008883  pop     rbx
0x180008884  retn
```
