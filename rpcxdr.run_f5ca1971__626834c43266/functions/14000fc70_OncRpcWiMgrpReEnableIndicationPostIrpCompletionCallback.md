# OncRpcWiMgrpReEnableIndicationPostIrpCompletionCallback

- ea: `0x14000fc70`
- end: `0x14000fcdc`
- name: `OncRpcWiMgrpReEnableIndicationPostIrpCompletionCallback`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140006798`
- `0x140008034`
- `0x14000fc70`
- `0x140010080`

## pseudocode

```c
__int64 __fastcall OncRpcWiMgrpReEnableIndicationPostIrpCompletionCallback(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // r9

  v1 = *(_QWORD *)(a1 + 56);
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 48LL) )
  {
    v2 = *(_QWORD *)(v1 + 2432);
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids, v2);
      }
      OncRpcConnMgrpConnectionDisconnectBySystem(*(_QWORD *)(v1 + 2432));
    }
  }
  return OncRpcWiMgrpSrvWorkItemFreeInternal(v1);
}

```

## disassembly

```asm
0x14000fc70  push    rbx
0x14000fc72  sub     rsp, 20h
0x14000fc76  mov     rax, [rcx+28h]
0x14000fc7a  mov     rbx, [rcx+38h]
0x14000fc7e  cmp     dword ptr [rax+30h], 0
0x14000fc82  jz      short loc_14000FCCD
0x14000fc84  mov     r9, [rbx+980h]
0x14000fc8b  test    r9, r9
0x14000fc8e  jz      short loc_14000FCCD
0x14000fc90  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc97  lea     rax, WPP_GLOBAL_Control
0x14000fc9e  cmp     rcx, rax
0x14000fca1  jz      short loc_14000FCC1
0x14000fca3  test    dword ptr [rcx+2Ch], 100h
0x14000fcaa  jz      short loc_14000FCC1
0x14000fcac  mov     rcx, [rcx+18h]
0x14000fcb0  lea     r8, WPP_cf8ac67cd1d9331d79f7433cf770f93d_Traceguids
0x14000fcb7  mov     edx, 13h
0x14000fcbc  call    WPP_SF_q
0x14000fcc1  mov     rcx, [rbx+980h]
0x14000fcc8  call    OncRpcConnMgrpConnectionDisconnectBySystem
0x14000fccd  mov     rcx, rbx
0x14000fcd0  call    OncRpcWiMgrpSrvWorkItemFreeInternal
0x14000fcd5  add     rsp, 20h
0x14000fcd9  pop     rbx
0x14000fcda  retn
```
