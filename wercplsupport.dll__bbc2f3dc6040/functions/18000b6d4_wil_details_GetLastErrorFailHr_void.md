# wil::details::GetLastErrorFailHr(void)

- ea: `0x18000b6d4`
- end: `0x18000b722`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009b78`
- `0x180009f58`
- `0x18000a410`

## callees

- `0x18000883c`
- `0x18000b6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6d8`

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
0x18000b6d4  sub     rsp, 48h
0x18000b6d8  call    cs:__imp_GetLastError
0x18000b6de  test    eax, eax
0x18000b6e0  jnz     short loc_18000B713
0x18000b6e2  mov     rax, [rsp+48h]
0x18000b6e7  xor     r9d, r9d; int
0x18000b6ea  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x18000b6f2  xor     r8d, r8d; int
0x18000b6f5  mov     [rsp+48h+var_20], rax; __int64
0x18000b6fa  xor     edx, edx; int
0x18000b6fc  xor     ecx, ecx; int
0x18000b6fe  mov     [rsp+48h+var_28], 0; __int64
0x18000b707  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b70c  mov     eax, 29Ch
0x18000b711  jmp     short loc_18000B715
0x18000b713  jle     short loc_18000B71D
0x18000b715  movzx   eax, ax
0x18000b718  or      eax, 80070000h
0x18000b71d  add     rsp, 48h
0x18000b721  retn
```
