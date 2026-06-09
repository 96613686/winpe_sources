# WFDSConMgr::WorkItem::CreateWork(WFDSConMgr::CThreadpoolEnvironment *)

- ea: `0x18005d3c4`
- end: `0x18005d4af`
- name: `?CreateWork@WorkItem@WFDSConMgr@@QEAAXPEAVCThreadpoolEnvironment@2@@Z`
- size: `235`
- prototype: `void __fastcall(PVOID pv, struct WFDSConMgr::CThreadpoolEnvironment *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180030344`
- `0x18003cb9c`
- `0x18004f7ac`

## callees

- `0x180006740`
- `0x18005c800`
- `0x18005d3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d40d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005d3fe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005d3fe`

## string_xrefs

- `0x18005d431`: `onecoreuap\net\wlan\wfdsconmgr\util\src\threadpool.cpp`
- `0x18005d491`: `onecoreuap\net\wlan\wfdsconmgr\util\src\threadpool.cpp`
- `0x18005d41f`: `CreateThreadpoolWork failed`
- `0x18005d484`: `CreateWork() called on a WorkItem which had already been initialized`
- `0x18005d43a`: `WFDSConMgr::WorkItem::CreateWork`
- `0x18005d49d`: `WFDSConMgr::WorkItem::CreateWork`

## pseudocode

```c
void __fastcall WFDSConMgr::WorkItem::CreateWork(_QWORD *pv, struct WFDSConMgr::CThreadpoolEnvironment *a2)
{
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax

  if ( pv[4] || pv[3] )
    WFDSConMgr::CException::Throw(
      -2147023649,
      "WFDSConMgr::WorkItem::CreateWork",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\threadpool.cpp",
      28,
      L"CreateWork() called on a WorkItem which had already been initialized");
  pv[4] = a2;
  ThreadpoolWork = CreateThreadpoolWork(
                     WFDSConMgr::WorkItem::StartRoutine,
                     pv,
                     (PTP_CALLBACK_ENVIRON)(((unsigned __int64)a2 + 16) & -(__int64)(a2 != 0)));
  pv[3] = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WFDSConMgr::CException::Throw(
      LastError,
      "WFDSConMgr::WorkItem::CreateWork",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\threadpool.cpp",
      21,
      L"CreateThreadpoolWork failed");
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, pv);
  }
}

```

## disassembly

```asm
0x18005d3c4  push    rbx
0x18005d3c6  sub     rsp, 30h
0x18005d3ca  cmp     qword ptr [rcx+20h], 0
0x18005d3cf  mov     rbx, rcx
0x18005d3d2  jnz     loc_18005D484
0x18005d3d8  cmp     qword ptr [rcx+18h], 0
0x18005d3dd  jnz     loc_18005D484
0x18005d3e3  mov     [rcx+20h], rdx
0x18005d3e7  lea     rax, [rdx+10h]
0x18005d3eb  neg     rdx
0x18005d3ee  mov     rdx, rcx; pv
0x18005d3f1  lea     rcx, ?StartRoutine@WorkItem@WFDSConMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAV12@PEAU_TP_WORK@@@Z; pfnwk
0x18005d3f8  sbb     r8, r8
0x18005d3fb  and     r8, rax; pcbe
0x18005d3fe  call    cs:__imp_CreateThreadpoolWork
0x18005d404  mov     [rbx+18h], rax
0x18005d408  test    rax, rax
0x18005d40b  jnz     short loc_18005D447
0x18005d40d  call    cs:__imp_GetLastError
0x18005d413  test    eax, eax
0x18005d415  jle     short loc_18005D41F
0x18005d417  movzx   eax, ax
0x18005d41a  or      eax, 80070000h
0x18005d41f  lea     rcx, aCreatethreadpo_1; "CreateThreadpoolWork failed"
0x18005d426  mov     r9d, 115h; char
0x18005d42c  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x18005d431  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005d438  mov     ecx, eax; int
0x18005d43a  lea     rdx, aWfdsconmgrWork; "WFDSConMgr::WorkItem::CreateWork"
0x18005d441  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18005d447  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d44e  lea     rax, WPP_GLOBAL_Control
0x18005d455  cmp     rcx, rax
0x18005d458  jz      short loc_18005D47E
0x18005d45a  cmp     byte ptr [rcx+19h], 4
0x18005d45e  jb      short loc_18005D47E
0x18005d460  test    byte ptr [rcx+1Ch], 1
0x18005d464  jz      short loc_18005D47E
0x18005d466  mov     rcx, [rcx+10h]
0x18005d46a  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d471  mov     edx, 14h
0x18005d476  mov     r9, rbx
0x18005d479  call    WPP_SF_q
0x18005d47e  add     rsp, 30h
0x18005d482  pop     rbx
0x18005d483  retn
0x18005d484  lea     rax, aCreateworkCall; "CreateWork() called on a WorkItem which"...
0x18005d48b  mov     r9d, 11Ch; char
0x18005d491  lea     r8, aOnecoreuapNetW_22; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005d498  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18005d49d  lea     rdx, aWfdsconmgrWork; "WFDSConMgr::WorkItem::CreateWork"
0x18005d4a4  mov     ecx, 800704DFh; int
0x18005d4a9  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBG@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *)
```
