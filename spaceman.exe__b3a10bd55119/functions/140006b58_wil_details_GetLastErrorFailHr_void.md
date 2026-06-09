# wil::details::GetLastErrorFailHr(void)

- ea: `0x140006b58`
- end: `0x140006ba6`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `78`
- prototype: `signed int __fastcall(wil::details *this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400054ac`
- `0x140005850`
- `0x140005dd0`

## callees

- `0x140004630`
- `0x140006b58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006b5c`

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
0x140006b58  sub     rsp, 48h
0x140006b5c  call    cs:__imp_GetLastError
0x140006b62  test    eax, eax
0x140006b64  jnz     short loc_140006B97
0x140006b66  mov     rax, [rsp+48h]
0x140006b6b  xor     r9d, r9d; int
0x140006b6e  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140006b76  xor     r8d, r8d; int
0x140006b79  mov     [rsp+48h+var_20], rax; __int64
0x140006b7e  xor     edx, edx; int
0x140006b80  xor     ecx, ecx; int
0x140006b82  mov     [rsp+48h+var_28], 0; __int64
0x140006b8b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006b90  mov     eax, 29Ch
0x140006b95  jmp     short loc_140006B99
0x140006b97  jle     short loc_140006BA1
0x140006b99  movzx   eax, ax
0x140006b9c  or      eax, 80070000h
0x140006ba1  add     rsp, 48h
0x140006ba5  retn
```
