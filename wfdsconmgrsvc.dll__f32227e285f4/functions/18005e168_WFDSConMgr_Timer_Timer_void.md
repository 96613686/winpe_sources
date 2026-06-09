# WFDSConMgr::Timer::~Timer(void)

- ea: `0x18005e168`
- end: `0x18005e1e3`
- name: `??1Timer@WFDSConMgr@@UEAA@XZ`
- size: `123`
- prototype: `void __fastcall(WFDSConMgr::Timer *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004f60`
- `0x180005310`
- `0x180010620`
- `0x18002bee0`
- `0x18002c3a0`
- `0x18005e1f0`

## callees

- `0x180006740`
- `0x18005e168`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005e1bd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005e1bd`

## pseudocode

```c
void __fastcall WFDSConMgr::Timer::~Timer(WFDSConMgr::Timer *this)
{
  bool v1; // zf

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &WFDSConMgr::Timer::`vftable';
  if ( !v1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_621daf02e21a36dfd02ebab89b470631_Traceguids, this);
    }
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 3));
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
  }
  *(_QWORD *)this = &WFDSConMgr::CThreadpoolTask::`vftable';
}

```

## disassembly

```asm
0x18005e168  push    rbx
0x18005e16a  sub     rsp, 20h
0x18005e16e  cmp     qword ptr [rcx+18h], 0
0x18005e173  lea     rax, ??_7Timer@WFDSConMgr@@6B@; const WFDSConMgr::Timer::`vftable'
0x18005e17a  mov     [rcx], rax
0x18005e17d  mov     rbx, rcx
0x18005e180  jz      short loc_18005E1D3
0x18005e182  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e189  lea     rax, WPP_GLOBAL_Control
0x18005e190  cmp     rcx, rax
0x18005e193  jz      short loc_18005E1B9
0x18005e195  cmp     byte ptr [rcx+19h], 4
0x18005e199  jb      short loc_18005E1B9
0x18005e19b  test    byte ptr [rcx+1Ch], 1
0x18005e19f  jz      short loc_18005E1B9
0x18005e1a1  mov     rcx, [rcx+10h]
0x18005e1a5  lea     r8, WPP_621daf02e21a36dfd02ebab89b470631_Traceguids
0x18005e1ac  mov     edx, 0Ch
0x18005e1b1  mov     r9, rbx
0x18005e1b4  call    WPP_SF_q
0x18005e1b9  mov     rcx, [rbx+18h]; pti
0x18005e1bd  call    cs:__imp_CloseThreadpoolTimer
0x18005e1c3  mov     qword ptr [rbx+18h], 0
0x18005e1cb  mov     qword ptr [rbx+20h], 0
0x18005e1d3  lea     rax, ??_7CThreadpoolTask@WFDSConMgr@@6B@; const WFDSConMgr::CThreadpoolTask::`vftable'
0x18005e1da  mov     [rbx], rax
0x18005e1dd  add     rsp, 20h
0x18005e1e1  pop     rbx
0x18005e1e2  retn
```
