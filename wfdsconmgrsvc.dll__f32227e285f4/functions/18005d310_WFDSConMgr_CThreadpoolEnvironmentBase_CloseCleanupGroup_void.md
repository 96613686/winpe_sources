# WFDSConMgr::CThreadpoolEnvironmentBase::CloseCleanupGroup(void)

- ea: `0x18005d310`
- end: `0x18005d3bc`
- name: `?CloseCleanupGroup@CThreadpoolEnvironmentBase@WFDSConMgr@@IEAAXXZ`
- size: `172`
- prototype: `void __fastcall(WFDSConMgr::CThreadpoolEnvironmentBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d4c0`
- `0x18005d500`

## callees

- `0x180006740`
- `0x18005d310`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005d3a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18005d3a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005d337`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18005d337`

## pseudocode

```c
void __fastcall WFDSConMgr::CThreadpoolEnvironmentBase::CloseCleanupGroup(WFDSConMgr::CThreadpoolEnvironmentBase *this)
{
  PVOID *v2; // rcx

  if ( *((_BYTE *)this + 88) )
    goto LABEL_6;
  *((_BYTE *)this + 88) = 1;
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 1), 0, 0);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids,
      (char *)this + 16);
LABEL_6:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_q(v2[2], 16, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, *((_QWORD *)this + 1));
LABEL_11:
  CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 1));
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x18005d310  mov     [rsp+arg_0], rbx
0x18005d315  push    rdi
0x18005d316  sub     rsp, 20h
0x18005d31a  cmp     byte ptr [rcx+58h], 0
0x18005d31e  lea     rdi, WPP_GLOBAL_Control
0x18005d325  mov     rbx, rcx
0x18005d328  jnz     short loc_18005D36E
0x18005d32a  mov     byte ptr [rcx+58h], 1
0x18005d32e  xor     r8d, r8d; pvCleanupContext
0x18005d331  mov     rcx, [rcx+8]; ptpcg
0x18005d335  xor     edx, edx; fCancelPendingCallbacks
0x18005d337  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18005d33d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d344  cmp     rcx, rdi
0x18005d347  jz      short loc_18005D39F
0x18005d349  cmp     byte ptr [rcx+19h], 4
0x18005d34d  jb      short loc_18005D375
0x18005d34f  test    byte ptr [rcx+1Ch], 1
0x18005d353  jz      short loc_18005D375
0x18005d355  mov     rcx, [rcx+10h]
0x18005d359  lea     r9, [rbx+10h]
0x18005d35d  mov     edx, 0Fh
0x18005d362  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d369  call    WPP_SF_q
0x18005d36e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d375  cmp     rcx, rdi
0x18005d378  jz      short loc_18005D39F
0x18005d37a  cmp     byte ptr [rcx+19h], 4
0x18005d37e  jb      short loc_18005D39F
0x18005d380  test    byte ptr [rcx+1Ch], 1
0x18005d384  jz      short loc_18005D39F
0x18005d386  mov     r9, [rbx+8]
0x18005d38a  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d391  mov     rcx, [rcx+10h]
0x18005d395  mov     edx, 10h
0x18005d39a  call    WPP_SF_q
0x18005d39f  mov     rcx, [rbx+8]; ptpcg
0x18005d3a3  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18005d3a9  mov     qword ptr [rbx+8], 0
0x18005d3b1  mov     rbx, [rsp+28h+arg_0]
0x18005d3b6  add     rsp, 20h
0x18005d3ba  pop     rdi
0x18005d3bb  retn
```
