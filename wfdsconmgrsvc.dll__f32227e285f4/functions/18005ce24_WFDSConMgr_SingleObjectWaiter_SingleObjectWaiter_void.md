# WFDSConMgr::SingleObjectWaiter::~SingleObjectWaiter(void)

- ea: `0x18005ce24`
- end: `0x18005ce88`
- name: `??1SingleObjectWaiter@WFDSConMgr@@UEAA@XZ`
- size: `100`
- prototype: `void __fastcall(WFDSConMgr::SingleObjectWaiter *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180024180`
- `0x18004c908`
- `0x18005d020`
- `0x1800663d0`
- `0x1800663f8`
- `0x18006aa22`

## callees

- `0x180006740`
- `0x18005ce24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005ce72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005ce72`

## pseudocode

```c
void __fastcall WFDSConMgr::SingleObjectWaiter::~SingleObjectWaiter(WFDSConMgr::SingleObjectWaiter *this)
{
  *(_QWORD *)this = &WFDSConMgr::SingleObjectWaiter::`vftable';
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  *(_QWORD *)this = &WFDSConMgr::CThreadpoolTask::`vftable';
}

```

## disassembly

```asm
0x18005ce24  push    rbx
0x18005ce26  sub     rsp, 20h
0x18005ce2a  lea     rax, ??_7SingleObjectWaiter@WFDSConMgr@@6B@; const WFDSConMgr::SingleObjectWaiter::`vftable'
0x18005ce31  mov     rbx, rcx
0x18005ce34  mov     [rcx], rax
0x18005ce37  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ce3e  lea     rax, WPP_GLOBAL_Control
0x18005ce45  cmp     rcx, rax
0x18005ce48  jz      short loc_18005CE6E
0x18005ce4a  cmp     byte ptr [rcx+19h], 4
0x18005ce4e  jb      short loc_18005CE6E
0x18005ce50  test    byte ptr [rcx+1Ch], 1
0x18005ce54  jz      short loc_18005CE6E
0x18005ce56  mov     rcx, [rcx+10h]
0x18005ce5a  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005ce61  mov     edx, 19h
0x18005ce66  mov     r9, rbx
0x18005ce69  call    WPP_SF_q
0x18005ce6e  lea     rcx, [rbx+48h]; lpCriticalSection
0x18005ce72  call    cs:__imp_DeleteCriticalSection
0x18005ce78  lea     rax, ??_7CThreadpoolTask@WFDSConMgr@@6B@; const WFDSConMgr::CThreadpoolTask::`vftable'
0x18005ce7f  mov     [rbx], rax
0x18005ce82  add     rsp, 20h
0x18005ce86  pop     rbx
0x18005ce87  retn
```
