# CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong,ulong)

- ea: `0x18001e5bc`
- end: `0x18001e668`
- name: `?CompRpcpErrorAddRecord@@YAXKKGKK@Z`
- size: `172`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned __int16, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006050`

## callees

- `0x180024629`
- `0x180024640`

## import_xrefs

- `RPCRT4!RpcErrorAddRecord` at `0x18001e63d`
- `RPCRT4!RpcErrorAddRecord` at `0x18001e63d`

## pseudocode

```c
void __fastcall CompRpcpErrorAddRecord(__int64 a1, ULONG a2, USHORT a3, int a4, unsigned int a5)
{
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+20h] [rbp-B8h] BYREF

  memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
  ErrorInfo.Version = 1;
  ErrorInfo.Parameters[0].ParameterType = eeptLongVal;
  ErrorInfo.Parameters[1].ParameterType = eeptLongVal;
  ErrorInfo.Parameters[1].u.LVal = a5;
  ErrorInfo.NumberOfParameters = 2;
  ErrorInfo.GeneratingComponent = 14;
  ErrorInfo.Status = a2;
  ErrorInfo.DetectionLocation = a3;
  ErrorInfo.Parameters[0].u.LVal = a4;
  RpcErrorAddRecord(&ErrorInfo);
}

```

## disassembly

```asm
0x18001e5bc  mov     [rsp+arg_0], rbx
0x18001e5c1  mov     [rsp+arg_18], rsi
0x18001e5c6  push    rdi
0x18001e5c7  sub     rsp, 0D0h
0x18001e5ce  mov     rax, cs:__security_cookie
0x18001e5d5  xor     rax, rsp
0x18001e5d8  mov     [rsp+0D8h+var_18], rax
0x18001e5e0  movzx   edi, r8w
0x18001e5e4  lea     rcx, [rsp+0D8h+ErrorInfo]; void *
0x18001e5e9  mov     ebx, edx
0x18001e5eb  mov     r8d, 98h; Size
0x18001e5f1  xor     edx, edx; Val
0x18001e5f3  mov     esi, r9d
0x18001e5f6  call    memset_0
0x18001e5fb  mov     eax, 3
0x18001e600  mov     [rsp+0D8h+ErrorInfo.Version], 1
0x18001e608  mov     [rsp+0D8h+ErrorInfo.Parameters.ParameterType], eax
0x18001e60c  lea     rcx, [rsp+0D8h+ErrorInfo]; ErrorInfo
0x18001e611  mov     [rsp+0D8h+ErrorInfo.Parameters.ParameterType+18h], eax
0x18001e615  mov     eax, [rsp+0D8h+arg_20]
0x18001e61c  mov     dword ptr [rsp+0D8h+ErrorInfo.Parameters.u+18h], eax
0x18001e620  mov     [rsp+0D8h+ErrorInfo.NumberOfParameters], 2
0x18001e628  mov     [rsp+0D8h+ErrorInfo.GeneratingComponent], 0Eh
0x18001e630  mov     [rsp+0D8h+ErrorInfo.Status], ebx
0x18001e634  mov     [rsp+0D8h+ErrorInfo.DetectionLocation], di
0x18001e639  mov     dword ptr [rsp+0D8h+ErrorInfo.Parameters.u], esi
0x18001e63d  call    cs:__imp_RpcErrorAddRecord
0x18001e643  mov     rcx, [rsp+0D8h+var_18]
0x18001e64b  xor     rcx, rsp; StackCookie
0x18001e64e  call    __security_check_cookie
0x18001e653  lea     r11, [rsp+0D8h+var_8]
0x18001e65b  mov     rbx, [r11+10h]
0x18001e65f  mov     rsi, [r11+28h]
0x18001e663  mov     rsp, r11
0x18001e666  pop     rdi
0x18001e667  retn
```
