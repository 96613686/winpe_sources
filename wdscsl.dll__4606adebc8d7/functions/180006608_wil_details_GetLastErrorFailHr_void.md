# wil::details::GetLastErrorFailHr(void)

- ea: `0x180006608`
- end: `0x18000665a`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `82`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b34`
- `0x180003f2c`
- `0x180004e8c`

## callees

- `0x180002a8c`
- `0x180006608`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000660c`
- `KERNEL32!GetLastError` at `0x18000660c`

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
0x180006608  sub     rsp, 48h
0x18000660c  call    cs:__imp_GetLastError
0x180006613  nop     dword ptr [rax+rax+00h]
0x180006618  test    eax, eax
0x18000661a  jnz     short loc_18000664A
0x18000661c  mov     rax, [rsp+48h]
0x180006621  xor     r9d, r9d; int
0x180006624  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x18000662c  xor     r8d, r8d; int
0x18000662f  mov     [rsp+48h+var_20], rax; __int64
0x180006634  xor     edx, edx; int
0x180006636  and     [rsp+48h+var_28], 0
0x18000663c  xor     ecx, ecx; int
0x18000663e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180006643  mov     eax, 29Ch
0x180006648  jmp     short loc_18000664C
0x18000664a  jle     short loc_180006654
0x18000664c  movzx   eax, ax
0x18000664f  or      eax, 80070000h
0x180006654  add     rsp, 48h
0x180006658  retn
```
