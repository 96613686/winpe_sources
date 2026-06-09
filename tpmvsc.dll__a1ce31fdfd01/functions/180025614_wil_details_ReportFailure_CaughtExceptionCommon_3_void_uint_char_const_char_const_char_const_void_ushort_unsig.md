# wil::details::ReportFailure_CaughtExceptionCommon<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x180025614`
- end: `0x18002563d`
- name: `??$ReportFailure_CaughtExceptionCommon@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `41`
- prototype: `void __fastcall __noreturn(__int64, int, int, int, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800255c4`

## callees

- `0x180025644`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommon<3>(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  char v8; // [rsp+50h] [rbp-18h] BYREF

  wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>((unsigned int)&v8, a2, a3, a4);
}

```

## disassembly

```asm
0x180025614  sub     rsp, 68h
0x180025618  mov     rax, [rsp+68h+arg_38]
0x180025620  lea     rcx, [rsp+68h+var_18]
0x180025625  mov     [rsp+68h+var_30], rax
0x18002562a  mov     rax, [rsp+68h+arg_30]
0x180025632  mov     [rsp+68h+var_38], rax
0x180025637  call    ??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)
```
