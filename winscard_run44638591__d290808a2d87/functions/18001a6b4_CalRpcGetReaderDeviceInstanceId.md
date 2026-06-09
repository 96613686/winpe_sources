# CalRpcGetReaderDeviceInstanceId

- ea: `0x18001a6b4`
- end: `0x18001a785`
- name: `CalRpcGetReaderDeviceInstanceId`
- size: `209`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, int, int pExceptionObject)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800117a4`

## callees

- `0x180006bf0`
- `0x180007940`
- `0x180007bc0`
- `0x18001991c`
- `0x18001a6b4`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a71e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a71e`
- `RPCRT4!NdrClientCall3` at `0x18001a6e1`
- `RPCRT4!NdrClientCall3` at `0x18001a6e1`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CalRpcGetReaderDeviceInstanceId(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180034330, 0x12u, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001a6b4  mov     rax, rsp
0x18001a6b7  push    rbx
0x18001a6b8  sub     rsp, 50h
0x18001a6bc  mov     qword ptr [rax-10h], 0
0x18001a6c4  mov     [rax-28h], r9
0x18001a6c8  mov     [rax-30h], r8
0x18001a6cc  mov     [rax-38h], rdx
0x18001a6d0  mov     r9, rcx
0x18001a6d3  xor     r8d, r8d; pReturnValue
0x18001a6d6  lea     edx, [r8+12h]; nProcNum
0x18001a6da  lea     rcx, stru_180034330; pProxyInfo
0x18001a6e1  call    cs:__imp_NdrClientCall3
0x18001a6e7  mov     [rsp+58h+var_10], rax
0x18001a6ec  mov     [rsp+58h+var_18], eax
0x18001a6f0  add     rsp, 50h
0x18001a6f4  pop     rbx
0x18001a6f5  retn
0x18001a6f6  mov     ebx, eax
0x18001a6f8  mov     edx, 2
0x18001a6fd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001a702  mov     [rsp+arg_38], ebx
0x18001a706  call    SCardAccessStartedEvent
0x18001a70b  test    rax, rax
0x18001a70e  jnz     short loc_18001A719
0x18001a710  lea     ebx, [rax+5]
0x18001a713  mov     [rsp+arg_38], ebx
0x18001a717  jmp     short loc_18001A737
0x18001a719  xor     edx, edx; dwMilliseconds
0x18001a71b  mov     rcx, rax; hHandle
0x18001a71e  call    cs:__imp_WaitForSingleObject
0x18001a724  mov     ecx, 8010001Dh
0x18001a729  test    eax, eax
0x18001a72b  cmovnz  ebx, ecx
0x18001a72e  mov     [rsp+arg_38], ebx
0x18001a732  call    SCardReleaseStartedEvent
0x18001a737  lea     rax, WPP_GLOBAL_Control
0x18001a73e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a745  cmp     rcx, rax
0x18001a748  jz      short loc_18001A76F
0x18001a74a  test    byte ptr [rcx+1Ch], 10h
0x18001a74e  jz      short loc_18001A76F
0x18001a750  cmp     byte ptr [rcx+19h], 2
0x18001a754  jb      short loc_18001A76F
0x18001a756  mov     edx, 1Ch
0x18001a75b  mov     [rsp+arg_18], ebx
0x18001a75f  lea     r8, WPP_4ef5272161b43f82534a52b1beb9ecde_Traceguids
0x18001a766  mov     rcx, [rcx+10h]
0x18001a76a  call    WPP_SF_sd
0x18001a76f  mov     [rsp+pExceptionObject], ebx
0x18001a773  lea     rdx, _TI1K; pThrowInfo
0x18001a77a  lea     rcx, [rsp+pExceptionObject]; pExceptionObject
0x18001a77f  call    _CxxThrowException_0
```
