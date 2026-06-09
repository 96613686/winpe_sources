# CSsdpNotifyRequestManager::HrRemoveNotifyRequest(void *)

- ea: `0x18002e8fc`
- end: `0x18002e9bc`
- name: `?HrRemoveNotifyRequest@CSsdpNotifyRequestManager@@QEAAJPEAX@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002cc60`

## callees

- `0x180015d9c`
- `0x18002e470`
- `0x18002e8fc`
- `0x18002f028`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e9ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e9ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e90b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e90b`

## pseudocode

```c
__int64 __fastcall CSsdpNotifyRequestManager::HrRemoveNotifyRequest(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  int v4; // eax
  int v5; // eax
  unsigned int v6; // ebx

  EnterCriticalSection(this);
  v4 = CSsdpNotifyRequestManager::HrRemoveInternal((CSsdpNotifyRequestManager *)this, 0, 0, a2, 0);
  if ( v4 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, a2, v4);
  v5 = CSsdpNotifyRequestManager::HrOperateNotifySemaphoreFromList(this, a2, 2);
  v6 = v5;
  if ( v5 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, a2, v5);
  LeaveCriticalSection(this);
  return v6;
}

```

## disassembly

```asm
0x18002e8fc  push    rbx
0x18002e8fe  push    rbp
0x18002e8ff  push    rsi
0x18002e900  push    rdi
0x18002e901  sub     rsp, 38h
0x18002e905  mov     rsi, rdx
0x18002e908  mov     rdi, rcx
0x18002e90b  call    cs:__imp_EnterCriticalSection
0x18002e911  mov     r9, rsi; void *
0x18002e914  mov     [rsp+58h+var_38], 0; struct CSsdpNotifyRequest *
0x18002e91d  xor     r8d, r8d; int
0x18002e920  xor     edx, edx; int
0x18002e922  mov     rcx, rdi; this
0x18002e925  call    ?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z; CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)
0x18002e92a  lea     rbp, WPP_GLOBAL_Control
0x18002e931  test    eax, eax
0x18002e933  jns     short loc_18002E963
0x18002e935  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e93c  cmp     rcx, rbp
0x18002e93f  jz      short loc_18002E963
0x18002e941  test    byte ptr [rcx+1Ch], 1
0x18002e945  jz      short loc_18002E963
0x18002e947  mov     rcx, [rcx+10h]
0x18002e94b  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18002e952  mov     edx, 59h ; 'Y'
0x18002e957  mov     dword ptr [rsp+58h+var_38], eax
0x18002e95b  mov     r9, rsi
0x18002e95e  call    WPP_SF_qd
0x18002e963  mov     r8d, 2
0x18002e969  mov     rdx, rsi
0x18002e96c  mov     rcx, rdi
0x18002e96f  call    ?HrOperateNotifySemaphoreFromList@CSsdpNotifyRequestManager@@QEAAJPEAXW4_Semaphore_OPERATION@@@Z; CSsdpNotifyRequestManager::HrOperateNotifySemaphoreFromList(void *,_Semaphore_OPERATION)
0x18002e974  mov     ebx, eax
0x18002e976  test    eax, eax
0x18002e978  jns     short loc_18002E9A8
0x18002e97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e981  cmp     rcx, rbp
0x18002e984  jz      short loc_18002E9A8
0x18002e986  test    byte ptr [rcx+1Ch], 1
0x18002e98a  jz      short loc_18002E9A8
0x18002e98c  mov     rcx, [rcx+10h]
0x18002e990  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18002e997  mov     edx, 5Ah ; 'Z'
0x18002e99c  mov     dword ptr [rsp+58h+var_38], eax
0x18002e9a0  mov     r9, rsi
0x18002e9a3  call    WPP_SF_qd
0x18002e9a8  mov     rcx, rdi; lpCriticalSection
0x18002e9ab  call    cs:__imp_LeaveCriticalSection
0x18002e9b1  mov     eax, ebx
0x18002e9b3  add     rsp, 38h
0x18002e9b7  pop     rdi
0x18002e9b8  pop     rsi
0x18002e9b9  pop     rbp
0x18002e9ba  pop     rbx
0x18002e9bb  retn
```
