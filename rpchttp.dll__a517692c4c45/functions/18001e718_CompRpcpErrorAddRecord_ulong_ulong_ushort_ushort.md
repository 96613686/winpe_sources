# CompRpcpErrorAddRecord(ulong,ulong,ushort,ushort *)

- ea: `0x18001e718`
- end: `0x18001e7ab`
- name: `?CompRpcpErrorAddRecord@@YAXKKGPEAG@Z`
- size: `147`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned __int16, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800081e8`
- `0x18001f214`

## callees

- `0x180024629`
- `0x180024640`

## import_xrefs

- `RPCRT4!RpcErrorAddRecord` at `0x18001e782`
- `RPCRT4!RpcErrorAddRecord` at `0x18001e782`

## pseudocode

```c
void __fastcall CompRpcpErrorAddRecord(ULONG a1, ULONG a2, USHORT a3, unsigned __int16 *a4)
{
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+20h] [rbp-C8h] BYREF

  memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
  ErrorInfo.GeneratingComponent = a1;
  ErrorInfo.Version = 1;
  ErrorInfo.NumberOfParameters = 1;
  ErrorInfo.Status = a2;
  ErrorInfo.DetectionLocation = a3;
  ErrorInfo.Parameters[0].ParameterType = eeptUnicodeString;
  ErrorInfo.Parameters[0].u.PVal = (ULONGLONG)a4;
  RpcErrorAddRecord(&ErrorInfo);
}

```

## disassembly

```asm
0x18001e718  mov     [rsp+arg_18], rbx
0x18001e71d  push    rbp
0x18001e71e  push    rsi
0x18001e71f  push    rdi
0x18001e720  sub     rsp, 0D0h
0x18001e727  mov     rax, cs:__security_cookie
0x18001e72e  xor     rax, rsp
0x18001e731  mov     [rsp+0E8h+var_28], rax
0x18001e739  movzx   esi, r8w
0x18001e73d  mov     edi, edx
0x18001e73f  mov     ebx, ecx
0x18001e741  xor     edx, edx; Val
0x18001e743  mov     r8d, 98h; Size
0x18001e749  lea     rcx, [rsp+0E8h+ErrorInfo]; void *
0x18001e74e  mov     rbp, r9
0x18001e751  call    memset_0
0x18001e756  mov     eax, 1
0x18001e75b  mov     [rsp+0E8h+ErrorInfo.GeneratingComponent], ebx
0x18001e75f  lea     rcx, [rsp+0E8h+ErrorInfo]; ErrorInfo
0x18001e764  mov     [rsp+0E8h+ErrorInfo.Version], eax
0x18001e768  mov     [rsp+0E8h+ErrorInfo.NumberOfParameters], eax
0x18001e76c  mov     [rsp+0E8h+ErrorInfo.Status], edi
0x18001e770  mov     [rsp+0E8h+ErrorInfo.DetectionLocation], si
0x18001e775  mov     [rsp+0E8h+ErrorInfo.Parameters.ParameterType], 2
0x18001e77d  mov     qword ptr [rsp+0E8h+ErrorInfo.Parameters.u], rbp
0x18001e782  call    cs:__imp_RpcErrorAddRecord
0x18001e788  mov     rcx, [rsp+0E8h+var_28]
0x18001e790  xor     rcx, rsp; StackCookie
0x18001e793  call    __security_check_cookie
0x18001e798  mov     rbx, [rsp+0E8h+arg_18]
0x18001e7a0  add     rsp, 0D0h
0x18001e7a7  pop     rdi
0x18001e7a8  pop     rsi
0x18001e7a9  pop     rbp
0x18001e7aa  retn
```
