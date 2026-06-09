# CalRpcReadCache

- ea: `0x1800107a8`
- end: `0x18001088f`
- name: `CalRpcReadCache`
- size: `231`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int, int, int, int, int pExceptionObject)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e864`

## callees

- `0x180006bf0`
- `0x180007940`
- `0x180007bc0`
- `0x1800107a8`
- `0x18001991c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010828`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010828`
- `RPCRT4!NdrClientCall3` at `0x1800107eb`
- `RPCRT4!NdrClientCall3` at `0x1800107eb`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CalRpcReadCache(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5, __int64 a6)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800342C8, 0, 0, a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x1800107a8  mov     r11, rsp
0x1800107ab  push    rbx
0x1800107ac  sub     rsp, 60h
0x1800107b0  mov     qword ptr [r11-10h], 0
0x1800107b8  mov     rax, [rsp+68h+arg_28]
0x1800107c0  mov     [r11-28h], rax
0x1800107c4  mov     rax, [rsp+68h+arg_20]
0x1800107cc  mov     [r11-30h], rax
0x1800107d0  mov     [r11-38h], r9
0x1800107d4  mov     [r11-40h], r8d
0x1800107d8  mov     [r11-48h], rdx
0x1800107dc  mov     r9, rcx
0x1800107df  xor     r8d, r8d; pReturnValue
0x1800107e2  xor     edx, edx; nProcNum
0x1800107e4  lea     rcx, stru_1800342C8; pProxyInfo
0x1800107eb  call    cs:__imp_NdrClientCall3
0x1800107f1  mov     [rsp+68h+var_10], rax
0x1800107f6  mov     [rsp+68h+var_18], eax
0x1800107fa  add     rsp, 60h
0x1800107fe  pop     rbx
0x1800107ff  retn
0x180010800  mov     ebx, eax
0x180010802  mov     edx, 2
0x180010807  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001080c  mov     [rsp+arg_48], ebx
0x180010810  call    SCardAccessStartedEvent
0x180010815  test    rax, rax
0x180010818  jnz     short loc_180010823
0x18001081a  lea     ebx, [rax+5]
0x18001081d  mov     [rsp+arg_48], ebx
0x180010821  jmp     short loc_180010841
0x180010823  xor     edx, edx; dwMilliseconds
0x180010825  mov     rcx, rax; hHandle
0x180010828  call    cs:__imp_WaitForSingleObject
0x18001082e  mov     ecx, 8010001Dh
0x180010833  test    eax, eax
0x180010835  cmovnz  ebx, ecx
0x180010838  mov     [rsp+arg_48], ebx
0x18001083c  call    SCardReleaseStartedEvent
0x180010841  lea     rax, WPP_GLOBAL_Control
0x180010848  mov     rcx, cs:WPP_GLOBAL_Control
0x18001084f  cmp     rcx, rax
0x180010852  jz      short loc_180010879
0x180010854  test    byte ptr [rcx+1Ch], 10h
0x180010858  jz      short loc_180010879
0x18001085a  cmp     byte ptr [rcx+19h], 2
0x18001085e  jb      short loc_180010879
0x180010860  mov     edx, 1Eh
0x180010865  mov     [rsp+arg_18], ebx
0x180010869  lea     r8, WPP_4ef5272161b43f82534a52b1beb9ecde_Traceguids
0x180010870  mov     rcx, [rcx+10h]
0x180010874  call    WPP_SF_sd
0x180010879  mov     [rsp+pExceptionObject], ebx
0x18001087d  lea     rdx, _TI1K; pThrowInfo
0x180010884  lea     rcx, [rsp+pExceptionObject]; pExceptionObject
0x180010889  call    _CxxThrowException_0
```
