# tlx::replace<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void (void *),&MyEvtRpcFree(void *),0>> &)

- ea: `0x18000de84`
- end: `0x18000dec4`
- name: `??$replace@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6AXPEAX@Z$1?MyEvtRpcFree@@YAX0@Z$0A@@tlx@@@0@@Z`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d650`
- `0x18000d818`
- `0x18000dac0`
- `0x18000e248`
- `0x18000f4e8`
- `0x180027ddc`
- `0x180028960`

## callees

- `0x18000de84`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000deb4`
- `RPCRT4!NdrClientCall3` at `0x18000deb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall tlx::replace<tlx::handle_traits<void *,void (void *),&void MyEvtRpcFree(void *),0>>(__int64 *a1)
{
  __int64 v2; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
  {
    v4 = v2;
    NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xDu, 0, &v4);
  }
  return a1;
}

```

## disassembly

```asm
0x18000de84  push    rbx
0x18000de86  sub     rsp, 20h
0x18000de8a  mov     rbx, rcx
0x18000de8d  mov     rax, [rcx]
0x18000de90  mov     qword ptr [rcx], 0
0x18000de97  test    rax, rax
0x18000de9a  jz      short loc_18000DEBB
0x18000de9c  mov     [rsp+28h+arg_0], rax
0x18000dea1  lea     r9, [rsp+28h+arg_0]
0x18000dea6  xor     r8d, r8d; pReturnValue
0x18000dea9  lea     edx, [r8+0Dh]; nProcNum
0x18000dead  lea     rcx, pProxyInfo; pProxyInfo
0x18000deb4  call    cs:__imp_NdrClientCall3
0x18000deba  nop
0x18000debb  mov     rax, rbx
0x18000debe  add     rsp, 20h
0x18000dec2  pop     rbx
0x18000dec3  retn
```
