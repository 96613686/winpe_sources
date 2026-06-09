# CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,uchar *,short)

- ea: `0x18001e670`
- end: `0x18001e711`
- name: `?CompRpcpErrorAddRecord@@YAXKKGKPEAEF@Z`
- size: `161`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned __int16, unsigned int, unsigned __int8 *, __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b2b0`

## callees

- `0x180024629`
- `0x180024640`

## import_xrefs

- `RPCRT4!RpcErrorAddRecord` at `0x18001e6ee`
- `RPCRT4!RpcErrorAddRecord` at `0x18001e6ee`

## pseudocode

```c
void __fastcall CompRpcpErrorAddRecord(__int64 a1, __int64 a2, __int64 a3, int a4, unsigned __int8 *a5, __int16 a6)
{
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+20h] [rbp-69h] BYREF

  memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
  ErrorInfo.Version = 1;
  ErrorInfo.DetectionLocation = 1385;
  ErrorInfo.Parameters[1].u.BVal.Size = a6;
  ErrorInfo.Parameters[1].u.PVal = (ULONGLONG)a5;
  ErrorInfo.NumberOfParameters = 2;
  ErrorInfo.GeneratingComponent = 14;
  ErrorInfo.Status = 0x10000;
  ErrorInfo.Parameters[0].ParameterType = eeptLongVal;
  ErrorInfo.Parameters[0].u.LVal = a4;
  ErrorInfo.Parameters[1].ParameterType = eeptBinary;
  RpcErrorAddRecord(&ErrorInfo);
}

```

## disassembly

```asm
0x18001e670  mov     [rsp-8+arg_0], rbx
0x18001e675  push    rbp
0x18001e676  lea     rbp, [rsp-47h]
0x18001e67b  sub     rsp, 0D0h
0x18001e682  mov     rax, cs:__security_cookie
0x18001e689  xor     rax, rsp
0x18001e68c  mov     [rbp+47h+var_10], rax
0x18001e690  xor     edx, edx; Val
0x18001e692  lea     rcx, [rbp+47h+ErrorInfo]; void *
0x18001e696  mov     r8d, 98h; Size
0x18001e69c  mov     ebx, r9d
0x18001e69f  call    memset_0
0x18001e6a4  mov     eax, 569h
0x18001e6a9  mov     [rbp+47h+ErrorInfo.Version], 1
0x18001e6b0  mov     [rbp+47h+ErrorInfo.DetectionLocation], ax
0x18001e6b4  lea     rcx, [rbp+47h+ErrorInfo]; ErrorInfo
0x18001e6b8  movzx   eax, [rbp+47h+arg_28]
0x18001e6bc  mov     word ptr [rbp+47h+ErrorInfo.Parameters.u+20h], ax
0x18001e6c0  mov     rax, [rbp+47h+arg_20]
0x18001e6c4  mov     qword ptr [rbp+47h+ErrorInfo.Parameters.u+18h], rax
0x18001e6c8  mov     [rbp+47h+ErrorInfo.NumberOfParameters], 2
0x18001e6cf  mov     [rbp+47h+ErrorInfo.GeneratingComponent], 0Eh
0x18001e6d6  mov     [rbp+47h+ErrorInfo.Status], 10000h
0x18001e6dd  mov     [rbp+47h+ErrorInfo.Parameters.ParameterType], 3
0x18001e6e4  mov     dword ptr [rbp+47h+ErrorInfo.Parameters.u], ebx
0x18001e6e7  mov     [rbp+47h+ErrorInfo.Parameters.ParameterType+18h], 7
0x18001e6ee  call    cs:__imp_RpcErrorAddRecord
0x18001e6f4  mov     rcx, [rbp+47h+var_10]
0x18001e6f8  xor     rcx, rsp; StackCookie
0x18001e6fb  call    __security_check_cookie
0x18001e700  mov     rbx, [rsp+0D0h+arg_0]
0x18001e708  add     rsp, 0D0h
0x18001e70f  pop     rbp
0x18001e710  retn
```
