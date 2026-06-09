# AudioSrvBinding

- ea: `0x1800072fc`
- end: `0x18000739a`
- name: `AudioSrvBinding`
- size: `158`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800065d0`

## callees

- `0x1800072fc`
- `0x180011d6c`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007347`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180007347`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000732f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000732f`
- `RPCRT4!RpcStringFreeW` at `0x180007354`
- `RPCRT4!RpcStringFreeW` at `0x180007354`

## pseudocode

```c
__int64 AudioSrvBinding()
{
  unsigned int v0; // ebx
  RPC_WSTR StringBinding; // [rsp+40h] [rbp+8h] BYREF

  StringBinding = 0;
  v0 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"Audiosrv", 0, &StringBinding);
  if ( v0 || (v0 = RpcBindingFromStringBindingW(StringBinding, &AudioSrv_IfHandle), RpcStringFreeW(&StringBinding), v0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x1800072fc  mov     r11, rsp
0x1800072ff  push    rbx
0x180007300  sub     rsp, 30h
0x180007304  lea     rax, [r11+8]
0x180007308  mov     qword ptr [r11+8], 0
0x180007310  mov     [r11-10h], rax
0x180007314  lea     r9, Endpoint; "Audiosrv"
0x18000731b  xor     r8d, r8d; NetworkAddr
0x18000731e  mov     qword ptr [r11-18h], 0
0x180007326  lea     rdx, ProtSeq; "ncalrpc"
0x18000732d  xor     ecx, ecx; ObjUuid
0x18000732f  call    cs:__imp_RpcStringBindingComposeW
0x180007335  mov     ebx, eax
0x180007337  test    eax, eax
0x180007339  jnz     short loc_18000735E
0x18000733b  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180007340  lea     rdx, AudioSrv_IfHandle; Binding
0x180007347  call    cs:__imp_RpcBindingFromStringBindingW
0x18000734d  lea     rcx, [rsp+38h+StringBinding]; String
0x180007352  mov     ebx, eax
0x180007354  call    cs:__imp_RpcStringFreeW
0x18000735a  test    ebx, ebx
0x18000735c  jz      short loc_180007392
0x18000735e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007365  lea     rax, WPP_GLOBAL_Control
0x18000736c  cmp     rcx, rax
0x18000736f  jz      short loc_180007392
0x180007371  test    dword ptr [rcx+1Ch], 400000h
0x180007378  jz      short loc_180007392
0x18000737a  mov     rcx, [rcx+10h]
0x18000737e  lea     r8, WPP_d09965cb4e7936f4cd6f01087cde1378_Traceguids
0x180007385  mov     edx, 0Ah
0x18000738a  mov     r9d, ebx
0x18000738d  call    WPP_SF_d
0x180007392  mov     eax, ebx
0x180007394  add     rsp, 30h
0x180007398  pop     rbx
0x180007399  retn
```
