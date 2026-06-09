# CompRpcpErrorAddRecord(ulong,ulong,ushort)

- ea: `0x18001e4a4`
- end: `0x18001e51e`
- name: `?CompRpcpErrorAddRecord@@YAXKKG@Z`
- size: `122`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned __int16)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800081e8`
- `0x180008d20`
- `0x180009620`
- `0x18000d0cc`
- `0x18000d288`
- `0x18000d41c`
- `0x18000d5a0`
- `0x18000ef2c`
- `0x18000f74c`
- `0x1800114d0`
- `0x18001b024`
- `0x18001f214`
- `0x18001fc58`

## callees

- `0x180024629`
- `0x180024640`

## import_xrefs

- `RPCRT4!RpcErrorAddRecord` at `0x18001e4fd`
- `RPCRT4!RpcErrorAddRecord` at `0x18001e4fd`

## pseudocode

```c
void __fastcall CompRpcpErrorAddRecord(ULONG a1, ULONG a2, USHORT a3)
{
  RPC_EXTENDED_ERROR_INFO ErrorInfo; // [rsp+20h] [rbp-C8h] BYREF

  memset_0(&ErrorInfo, 0, sizeof(ErrorInfo));
  ErrorInfo.Version = 1;
  ErrorInfo.NumberOfParameters = 0;
  ErrorInfo.GeneratingComponent = a1;
  ErrorInfo.Status = a2;
  ErrorInfo.DetectionLocation = a3;
  RpcErrorAddRecord(&ErrorInfo);
}

```

## disassembly

```asm
0x18001e4a4  push    rbx
0x18001e4a6  push    rsi
0x18001e4a7  push    rdi
0x18001e4a8  sub     rsp, 0D0h
0x18001e4af  mov     rax, cs:__security_cookie
0x18001e4b6  xor     rax, rsp
0x18001e4b9  mov     [rsp+0E8h+var_28], rax
0x18001e4c1  movzx   esi, r8w
0x18001e4c5  mov     edi, edx
0x18001e4c7  mov     ebx, ecx
0x18001e4c9  xor     edx, edx; Val
0x18001e4cb  mov     r8d, 98h; Size
0x18001e4d1  lea     rcx, [rsp+0E8h+ErrorInfo]; void *
0x18001e4d6  call    memset_0
0x18001e4db  lea     rcx, [rsp+0E8h+ErrorInfo]; ErrorInfo
0x18001e4e0  mov     [rsp+0E8h+ErrorInfo.Version], 1
0x18001e4e8  mov     [rsp+0E8h+ErrorInfo.NumberOfParameters], 0
0x18001e4f0  mov     [rsp+0E8h+ErrorInfo.GeneratingComponent], ebx
0x18001e4f4  mov     [rsp+0E8h+ErrorInfo.Status], edi
0x18001e4f8  mov     [rsp+0E8h+ErrorInfo.DetectionLocation], si
0x18001e4fd  call    cs:__imp_RpcErrorAddRecord
0x18001e503  mov     rcx, [rsp+0E8h+var_28]
0x18001e50b  xor     rcx, rsp; StackCookie
0x18001e50e  call    __security_check_cookie
0x18001e513  add     rsp, 0D0h
0x18001e51a  pop     rdi
0x18001e51b  pop     rsi
0x18001e51c  pop     rbx
0x18001e51d  retn
```
