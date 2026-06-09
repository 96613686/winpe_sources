# WFDSConMgr::SingleObjectWaiter::Cancel(bool)

- ea: `0x18005d09c`
- end: `0x18005d205`
- name: `?Cancel@SingleObjectWaiter@WFDSConMgr@@QEAAX_N@Z`
- size: `361`
- prototype: `void __fastcall(WFDSConMgr::SingleObjectWaiter *__hidden this, bool)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180024874`
- `0x180029008`
- `0x18004c908`
- `0x18005d6c0`

## callees

- `0x1800059c0`
- `0x180006740`
- `0x18005d09c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d10d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005d10d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005d14c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005d14c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005d186`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005d186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d1f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005d1f4`

## pseudocode

```c
void __fastcall WFDSConMgr::SingleObjectWaiter::Cancel(WFDSConMgr::SingleObjectWaiter *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  struct _FILETIME pftTimeout; // [rsp+30h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp+18h] BYREF

  WFDSConMgr::CriticalSection::Lock((char *)this + 72, &lpCriticalSection);
  if ( !*((_QWORD *)this + 4) )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_23;
    }
    v3 = 34;
    goto LABEL_22;
  }
  pftTimeout = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this);
  }
  SetThreadpoolWait(*((PTP_WAIT *)this + 4), 0, &pftTimeout);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this);
  }
  WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 4), 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this);
  }
  CloseThreadpoolWait(*((PTP_WAIT *)this + 4));
  *((_QWORD *)this + 4) = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = 33;
LABEL_22:
    WPP_SF_q(v2[2], v3, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids, this);
  }
LABEL_23:
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18005d09c  mov     [rsp+arg_8], rbx
0x18005d0a1  push    rsi
0x18005d0a2  sub     rsp, 20h
0x18005d0a6  mov     rbx, rcx
0x18005d0a9  lea     rdx, [rsp+28h+lpCriticalSection]
0x18005d0ae  add     rcx, 48h ; 'H'
0x18005d0b2  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18005d0b7  cmp     qword ptr [rbx+20h], 0
0x18005d0bc  jz      loc_18005D1B3
0x18005d0c2  mov     qword ptr [rsp+28h+pftTimeout.dwLowDateTime], 0
0x18005d0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0d2  lea     rsi, WPP_GLOBAL_Control
0x18005d0d9  cmp     rcx, rsi
0x18005d0dc  jz      short loc_18005D102
0x18005d0de  cmp     byte ptr [rcx+19h], 4
0x18005d0e2  jb      short loc_18005D102
0x18005d0e4  test    byte ptr [rcx+1Ch], 1
0x18005d0e8  jz      short loc_18005D102
0x18005d0ea  mov     rcx, [rcx+10h]
0x18005d0ee  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d0f5  mov     edx, 1Eh
0x18005d0fa  mov     r9, rbx
0x18005d0fd  call    WPP_SF_q
0x18005d102  mov     rcx, [rbx+20h]; pwa
0x18005d106  lea     r8, [rsp+28h+pftTimeout]; pftTimeout
0x18005d10b  xor     edx, edx; h
0x18005d10d  call    cs:__imp_SetThreadpoolWait
0x18005d113  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d11a  cmp     rcx, rsi
0x18005d11d  jz      short loc_18005D143
0x18005d11f  cmp     byte ptr [rcx+19h], 4
0x18005d123  jb      short loc_18005D143
0x18005d125  test    byte ptr [rcx+1Ch], 1
0x18005d129  jz      short loc_18005D143
0x18005d12b  mov     rcx, [rcx+10h]
0x18005d12f  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d136  mov     edx, 1Fh
0x18005d13b  mov     r9, rbx
0x18005d13e  call    WPP_SF_q
0x18005d143  mov     rcx, [rbx+20h]; pwa
0x18005d147  mov     edx, 1; fCancelPendingCallbacks
0x18005d14c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005d152  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d159  cmp     rcx, rsi
0x18005d15c  jz      short loc_18005D182
0x18005d15e  cmp     byte ptr [rcx+19h], 4
0x18005d162  jb      short loc_18005D182
0x18005d164  test    byte ptr [rcx+1Ch], 1
0x18005d168  jz      short loc_18005D182
0x18005d16a  mov     rcx, [rcx+10h]
0x18005d16e  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d175  mov     edx, 20h ; ' '
0x18005d17a  mov     r9, rbx
0x18005d17d  call    WPP_SF_q
0x18005d182  mov     rcx, [rbx+20h]; pwa
0x18005d186  call    cs:__imp_CloseThreadpoolWait
0x18005d18c  mov     qword ptr [rbx+20h], 0
0x18005d194  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d19b  cmp     rcx, rsi
0x18005d19e  jz      short loc_18005D1EA
0x18005d1a0  cmp     byte ptr [rcx+19h], 4
0x18005d1a4  jb      short loc_18005D1EA
0x18005d1a6  test    byte ptr [rcx+1Ch], 1
0x18005d1aa  jz      short loc_18005D1EA
0x18005d1ac  mov     edx, 21h ; '!'
0x18005d1b1  jmp     short loc_18005D1D7
0x18005d1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d1ba  lea     rsi, WPP_GLOBAL_Control
0x18005d1c1  cmp     rcx, rsi
0x18005d1c4  jz      short loc_18005D1EA
0x18005d1c6  cmp     byte ptr [rcx+19h], 4
0x18005d1ca  jb      short loc_18005D1EA
0x18005d1cc  test    byte ptr [rcx+1Ch], 1
0x18005d1d0  jz      short loc_18005D1EA
0x18005d1d2  mov     edx, 22h ; '"'
0x18005d1d7  mov     rcx, [rcx+10h]
0x18005d1db  lea     r8, WPP_96a9a6c77a913b5e31449c3b6f365fcd_Traceguids
0x18005d1e2  mov     r9, rbx
0x18005d1e5  call    WPP_SF_q
0x18005d1ea  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x18005d1ef  test    rcx, rcx
0x18005d1f2  jz      short loc_18005D1FA
0x18005d1f4  call    cs:__imp_LeaveCriticalSection
0x18005d1fa  mov     rbx, [rsp+28h+arg_8]
0x18005d1ff  add     rsp, 20h
0x18005d203  pop     rsi
0x18005d204  retn
```
