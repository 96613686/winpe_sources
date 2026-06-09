# wil::details::GetLastErrorFailHr(void)

- ea: `0x180004998`
- end: `0x1800049e9`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `81`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004144`
- `0x1800044e8`

## callees

- `0x180003908`
- `0x180004998`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049a3`

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
0x180004998  push    rbx
0x18000499a  sub     rsp, 40h
0x18000499e  mov     rbx, [rsp+48h]
0x1800049a3  call    cs:__imp_GetLastError
0x1800049a9  test    eax, eax
0x1800049ab  jnz     short loc_1800049D7
0x1800049ad  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800049b5  mov     [rsp+48h+var_20], rbx; __int64
0x1800049ba  mov     [rsp+48h+var_28], 0; __int64
0x1800049c3  xor     r9d, r9d; int
0x1800049c6  xor     r8d, r8d; int
0x1800049c9  xor     edx, edx; int
0x1800049cb  xor     ecx, ecx; int
0x1800049cd  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800049d2  mov     eax, 29Ch
0x1800049d7  test    eax, eax
0x1800049d9  jle     short loc_1800049E3
0x1800049db  movzx   eax, ax
0x1800049de  or      eax, 80070000h
0x1800049e3  add     rsp, 40h
0x1800049e7  pop     rbx
0x1800049e8  retn
```
