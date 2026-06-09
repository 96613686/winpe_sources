# wil::details::GetLastErrorFailHr(void)

- ea: `0x180005678`
- end: `0x1800056c6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e4c`
- `0x1800041f0`
- `0x180004830`

## callees

- `0x180002e54`
- `0x180005678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000567c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000567c`

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
0x180005678  sub     rsp, 48h
0x18000567c  call    cs:__imp_GetLastError
0x180005682  test    eax, eax
0x180005684  jnz     short loc_1800056B7
0x180005686  mov     rax, [rsp+48h]
0x18000568b  xor     r9d, r9d; int
0x18000568e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180005696  xor     r8d, r8d; int
0x180005699  mov     [rsp+48h+var_20], rax; __int64
0x18000569e  xor     edx, edx; int
0x1800056a0  xor     ecx, ecx; int
0x1800056a2  mov     [rsp+48h+var_28], 0; __int64
0x1800056ab  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800056b0  mov     eax, 29Ch
0x1800056b5  jmp     short loc_1800056B9
0x1800056b7  jle     short loc_1800056C1
0x1800056b9  movzx   eax, ax
0x1800056bc  or      eax, 80070000h
0x1800056c1  add     rsp, 48h
0x1800056c5  retn
```
