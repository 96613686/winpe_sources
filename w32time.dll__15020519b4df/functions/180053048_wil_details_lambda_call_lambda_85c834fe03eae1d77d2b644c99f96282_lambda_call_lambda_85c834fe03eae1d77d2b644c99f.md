# wil::details::lambda_call__lambda_85c834fe03eae1d77d2b644c99f96282___::_lambda_call__lambda_85c834fe03eae1d77d2b644c99f96282___

- ea: `0x180053048`
- end: `0x180053077`
- name: `wil::details::lambda_call__lambda_85c834fe03eae1d77d2b644c99f96282___::_lambda_call__lambda_85c834fe03eae1d77d2b644c99f96282___`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006a5dc`
- `0x18006abc2`

## callees

- `0x180053048`

## import_xrefs

- `SspiCli!DeleteSecurityContext` at `0x180053064`
- `SspiCli!DeleteSecurityContext` at `0x180053064`

## pseudocode

```c
SECURITY_STATUS __fastcall wil::details::lambda_call__lambda_85c834fe03eae1d77d2b644c99f96282___::_lambda_call__lambda_85c834fe03eae1d77d2b644c99f96282___(
        __int64 a1)
{
  SECURITY_STATUS result; // eax
  struct _SecHandle *v2; // rcx

  result = 0;
  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    v2 = *(struct _SecHandle **)a1;
    if ( v2->dwLower || v2->dwUpper )
      return DeleteSecurityContext(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180053048  sub     rsp, 28h
0x18005304c  xor     eax, eax
0x18005304e  cmp     [rcx+8], al
0x180053051  jz      short loc_180053071
0x180053053  mov     [rcx+8], al
0x180053056  mov     rcx, [rcx]; phContext
0x180053059  cmp     [rcx], rax
0x18005305c  jnz     short loc_180053064
0x18005305e  cmp     [rcx+8], rax
0x180053062  jz      short loc_180053071
0x180053064  call    cs:__imp_DeleteSecurityContext
0x18005306b  nop     dword ptr [rax+rax+00h]
0x180053070  nop
0x180053071  add     rsp, 28h
0x180053075  retn
```
