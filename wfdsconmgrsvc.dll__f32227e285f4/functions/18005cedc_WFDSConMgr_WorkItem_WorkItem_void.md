# WFDSConMgr::WorkItem::~WorkItem(void)

- ea: `0x18005cedc`
- end: `0x18005cf57`
- name: `??1WorkItem@WFDSConMgr@@UEAA@XZ`
- size: `123`
- prototype: `void __fastcall(WFDSConMgr::WorkItem *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180030748`
- `0x18003cd24`
- `0x18004fad4`
- `0x18005d060`
- `0x1800678b9`

## callees

- `0x180006740`
- `0x18005cedc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005cf31`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005cf31`

## pseudocode

```c
void __fastcall WFDSConMgr::WorkItem::~WorkItem(WFDSConMgr::WorkItem *this)
{
  bool v1; // zf

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &WFDSConMgr::WorkItem::`vftable';
  if ( !v1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this);
    }
    CloseThreadpoolWork(*((PTP_WORK *)this + 3));
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
  }
  *(_QWORD *)this = &WFDSConMgr::CThreadpoolTask::`vftable';
}

```

## disassembly

```asm
0x18005cedc  push    rbx
0x18005cede  sub     rsp, 20h
0x18005cee2  cmp     qword ptr [rcx+18h], 0
0x18005cee7  lea     rax, ??_7WorkItem@WFDSConMgr@@6B@; const WFDSConMgr::WorkItem::`vftable'
0x18005ceee  mov     [rcx], rax
0x18005cef1  mov     rbx, rcx
0x18005cef4  jz      short loc_18005CF47
0x18005cef6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cefd  lea     rax, WPP_GLOBAL_Control
0x18005cf04  cmp     rcx, rax
0x18005cf07  jz      short loc_18005CF2D
0x18005cf09  cmp     byte ptr [rcx+19h], 4
0x18005cf0d  jb      short loc_18005CF2D
0x18005cf0f  test    byte ptr [rcx+1Ch], 1
0x18005cf13  jz      short loc_18005CF2D
0x18005cf15  mov     rcx, [rcx+10h]
0x18005cf19  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005cf20  mov     edx, 16h
0x18005cf25  mov     r9, rbx
0x18005cf28  call    WPP_SF_q
0x18005cf2d  mov     rcx, [rbx+18h]; pwk
0x18005cf31  call    cs:__imp_CloseThreadpoolWork
0x18005cf37  mov     qword ptr [rbx+18h], 0
0x18005cf3f  mov     qword ptr [rbx+20h], 0
0x18005cf47  lea     rax, ??_7CThreadpoolTask@WFDSConMgr@@6B@; const WFDSConMgr::CThreadpoolTask::`vftable'
0x18005cf4e  mov     [rbx], rax
0x18005cf51  add     rsp, 20h
0x18005cf55  pop     rbx
0x18005cf56  retn
```
