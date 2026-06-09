# WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(bool)

- ea: `0x18005d27c`
- end: `0x18005d307`
- name: `?CleanupGroupMembers@CThreadpoolEnvironment@WFDSConMgr@@QEAAX_N@Z`
- size: `139`
- prototype: `void __fastcall(WFDSConMgr::CThreadpoolEnvironment *__hidden this, bool)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180004f60`
- `0x18000fb84`
- `0x1800240b8`
- `0x180030748`
- `0x18003cd24`
- `0x18004c71c`
- `0x18004fad4`

## callees

- `0x180006740`
- `0x180006c60`
- `0x180008a10`
- `0x18005d27c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005d2b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005d2b9`

## pseudocode

```c
void __fastcall WFDSConMgr::CThreadpoolEnvironment::CleanupGroupMembers(WFDSConMgr::CThreadpoolEnvironment *this)
{
  _BYTE v2[24]; // [rsp+20h] [rbp-18h] BYREF

  if ( *((_QWORD *)this + 1) )
  {
    WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(
      (__int64)v2,
      (RTL_SRWLOCK *)this + 12);
    if ( !*((_BYTE *)this + 88) )
    {
      *((_BYTE *)this + 88) = 1;
      WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v2);
      CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 1), 1, 0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids,
          (char *)this + 16);
      }
    }
    WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v2);
  }
}

```

## disassembly

```asm
0x18005d27c  push    rbx
0x18005d27e  sub     rsp, 30h
0x18005d282  cmp     qword ptr [rcx+8], 0
0x18005d287  mov     rbx, rcx
0x18005d28a  jz      short loc_18005D301
0x18005d28c  lea     rdx, [rcx+60h]
0x18005d290  lea     rcx, [rsp+38h+var_18]
0x18005d295  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x18005d29a  cmp     byte ptr [rbx+58h], 0
0x18005d29e  jnz     short loc_18005D2F7
0x18005d2a0  lea     rcx, [rsp+38h+var_18]
0x18005d2a5  mov     byte ptr [rbx+58h], 1
0x18005d2a9  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x18005d2ae  mov     rcx, [rbx+8]; ptpcg
0x18005d2b2  xor     r8d, r8d; pvCleanupContext
0x18005d2b5  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18005d2b9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18005d2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d2c6  lea     rax, WPP_GLOBAL_Control
0x18005d2cd  cmp     rcx, rax
0x18005d2d0  jz      short loc_18005D2F7
0x18005d2d2  cmp     byte ptr [rcx+19h], 4
0x18005d2d6  jb      short loc_18005D2F7
0x18005d2d8  test    byte ptr [rcx+1Ch], 1
0x18005d2dc  jz      short loc_18005D2F7
0x18005d2de  mov     rcx, [rcx+10h]
0x18005d2e2  lea     r9, [rbx+10h]
0x18005d2e6  mov     edx, 12h
0x18005d2eb  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d2f2  call    WPP_SF_q
0x18005d2f7  lea     rcx, [rsp+38h+var_18]
0x18005d2fc  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x18005d301  add     rsp, 30h
0x18005d305  pop     rbx
0x18005d306  retn
```
