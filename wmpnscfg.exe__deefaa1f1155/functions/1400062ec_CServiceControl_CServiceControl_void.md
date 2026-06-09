# CServiceControl::CServiceControl(void)

- ea: `0x1400062ec`
- end: `0x1400063cc`
- name: `??0CServiceControl@@QEAA@XZ`
- size: `224`
- prototype: `CServiceControl *__fastcall(CServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140005658`

## callees

- `0x14000491c`
- `0x1400053b4`
- `0x1400062ec`
- `0x140008010`

## pseudocode

```c
CServiceControl *__fastcall CServiceControl::CServiceControl(CServiceControl *this)
{
  *(_QWORD *)this = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
  ATL::CSimpleStringT<unsigned short,0>::SetString(this, L"WMPNetworkSvc", 13);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
  }
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_cb23d491edf93b904e2862226171c496_Traceguids);
  return this;
}

```

## disassembly

```asm
0x1400062ec  mov     [rsp+arg_0], rbx
0x1400062f1  push    rsi
0x1400062f2  sub     rsp, 20h
0x1400062f6  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400062fd  mov     rbx, rcx
0x140006300  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006307  mov     rax, [rax+18h]
0x14000630b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006310  add     rax, 18h
0x140006314  mov     [rbx], rax
0x140006317  mov     rcx, cs:WPP_GLOBAL_Control
0x14000631e  lea     rsi, WPP_GLOBAL_Control
0x140006325  cmp     rcx, rsi
0x140006328  jz      short loc_140006345
0x14000632a  test    byte ptr [rcx+1Ch], 1
0x14000632e  jz      short loc_140006345
0x140006330  mov     rcx, [rcx+10h]
0x140006334  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x14000633b  mov     edx, 0Ah
0x140006340  call    WPP_SF_
0x140006345  mov     r8d, 0Dh
0x14000634b  lea     rdx, aWmpnetworksvc; "WMPNetworkSvc"
0x140006352  mov     rcx, rbx
0x140006355  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000635a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006361  cmp     rcx, rsi
0x140006364  jz      short loc_140006387
0x140006366  test    byte ptr [rcx+1Ch], 2
0x14000636a  jz      short loc_140006387
0x14000636c  cmp     byte ptr [rcx+19h], 4
0x140006370  jb      short loc_140006387
0x140006372  mov     rcx, [rcx+10h]
0x140006376  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x14000637d  mov     edx, 0Bh
0x140006382  call    WPP_SF_
0x140006387  mov     qword ptr [rbx+8], 0
0x14000638f  mov     qword ptr [rbx+10h], 0
0x140006397  mov     rcx, cs:WPP_GLOBAL_Control
0x14000639e  cmp     rcx, rsi
0x1400063a1  jz      short loc_1400063BE
0x1400063a3  test    byte ptr [rcx+1Ch], 1
0x1400063a7  jz      short loc_1400063BE
0x1400063a9  mov     rcx, [rcx+10h]
0x1400063ad  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x1400063b4  mov     edx, 0Ch
0x1400063b9  call    WPP_SF_
0x1400063be  mov     rax, rbx
0x1400063c1  mov     rbx, [rsp+28h+arg_0]
0x1400063c6  add     rsp, 20h
0x1400063ca  pop     rsi
0x1400063cb  retn
```
