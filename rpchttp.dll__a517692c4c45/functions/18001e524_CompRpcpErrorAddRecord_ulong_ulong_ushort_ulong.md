# CompRpcpErrorAddRecord(ulong,ulong,ushort,ulong)

- ea: `0x18001e524`
- end: `0x18001e5b6`
- name: `?CompRpcpErrorAddRecord@@YAXKKGK@Z`
- size: `146`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006050`
- `0x1800081e8`
- `0x18000f74c`
- `0x180019b1c`
- `0x18001a9cc`
- `0x18001b2b0`
- `0x18001cb10`
- `0x18001fc58`

## callees

- `0x180024629`
- `0x180024640`

## import_xrefs

- `RPCRT4!RpcErrorAddRecord` at `0x18001e58d`
- `RPCRT4!RpcErrorAddRecord` at `0x18001e58d`

## pseudocode

```c
void __fastcall CompRpcpErrorAddRecord(ULONG a1, ULONG a2, USHORT a3, int a4)
{
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+20h] [rbp-C8h] BYREF

  memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
  ErrorInfo.GeneratingComponent = a1;
  ErrorInfo.Version = 1;
  ErrorInfo.NumberOfParameters = 1;
  ErrorInfo.Status = a2;
  ErrorInfo.DetectionLocation = a3;
  ErrorInfo.Parameters[0].ParameterType = eeptLongVal;
  ErrorInfo.Parameters[0].u.LVal = a4;
  RpcErrorAddRecord(&ErrorInfo);
}

```

## disassembly

```asm
0x18001e524  mov     [rsp+arg_18], rbx
0x18001e529  push    rbp
0x18001e52a  push    rsi
0x18001e52b  push    rdi
0x18001e52c  sub     rsp, 0D0h
0x18001e533  mov     rax, cs:__security_cookie
0x18001e53a  xor     rax, rsp
0x18001e53d  mov     [rsp+0E8h+var_28], rax
0x18001e545  movzx   esi, r8w
0x18001e549  mov     edi, edx
0x18001e54b  mov     ebx, ecx
0x18001e54d  xor     edx, edx; Val
0x18001e54f  mov     r8d, 98h; Size
0x18001e555  lea     rcx, [rsp+0E8h+ErrorInfo]; void *
0x18001e55a  mov     ebp, r9d
0x18001e55d  call    memset_0
0x18001e562  mov     eax, 1
0x18001e567  mov     [rsp+0E8h+ErrorInfo.GeneratingComponent], ebx
0x18001e56b  lea     rcx, [rsp+0E8h+ErrorInfo]; ErrorInfo
0x18001e570  mov     [rsp+0E8h+ErrorInfo.Version], eax
0x18001e574  mov     [rsp+0E8h+ErrorInfo.NumberOfParameters], eax
0x18001e578  mov     [rsp+0E8h+ErrorInfo.Status], edi
0x18001e57c  mov     [rsp+0E8h+ErrorInfo.DetectionLocation], si
0x18001e581  mov     [rsp+0E8h+ErrorInfo.Parameters.ParameterType], 3
0x18001e589  mov     dword ptr [rsp+0E8h+ErrorInfo.Parameters.u], ebp
0x18001e58d  call    cs:__imp_RpcErrorAddRecord
0x18001e593  mov     rcx, [rsp+0E8h+var_28]
0x18001e59b  xor     rcx, rsp; StackCookie
0x18001e59e  call    __security_check_cookie
0x18001e5a3  mov     rbx, [rsp+0E8h+arg_18]
0x18001e5ab  add     rsp, 0D0h
0x18001e5b2  pop     rdi
0x18001e5b3  pop     rsi
0x18001e5b4  pop     rbp
0x18001e5b5  retn
```
