# CSsdpNotifyRequestManager::HrRemoveNotifyRequest(void *)

- ea: `0x180030ab0`
- end: `0x180030b7d`
- name: `?HrRemoveNotifyRequest@CSsdpNotifyRequestManager@@QEAAJPEAX@Z`
- size: `205`
- prototype: `__int64 __fastcall(CSsdpNotifyRequestManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002ec70`

## callees

- `0x180018128`
- `0x1800305cc`
- `0x180030ab0`
- `0x180031278`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030b65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030b65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030abf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030abf`

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
0x180030ab0  push    rbx
0x180030ab2  push    rbp
0x180030ab3  push    rsi
0x180030ab4  push    rdi
0x180030ab5  sub     rsp, 38h
0x180030ab9  mov     rsi, rdx
0x180030abc  mov     rdi, rcx
0x180030abf  call    cs:__imp_EnterCriticalSection
0x180030ac6  nop     dword ptr [rax+rax+00h]
0x180030acb  mov     r9, rsi; void *
0x180030ace  mov     [rsp+58h+var_38], 0; struct CSsdpNotifyRequest *
0x180030ad7  xor     r8d, r8d; int
0x180030ada  xor     edx, edx; int
0x180030adc  mov     rcx, rdi; this
0x180030adf  call    ?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z; CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)
0x180030ae4  lea     rbp, WPP_GLOBAL_Control
0x180030aeb  test    eax, eax
0x180030aed  jns     short loc_180030B1D
0x180030aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180030af6  cmp     rcx, rbp
0x180030af9  jz      short loc_180030B1D
0x180030afb  test    byte ptr [rcx+1Ch], 1
0x180030aff  jz      short loc_180030B1D
0x180030b01  mov     rcx, [rcx+10h]
0x180030b05  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180030b0c  mov     edx, 59h ; 'Y'
0x180030b11  mov     dword ptr [rsp+58h+var_38], eax
0x180030b15  mov     r9, rsi
0x180030b18  call    WPP_SF_qd
0x180030b1d  mov     r8d, 2
0x180030b23  mov     rdx, rsi
0x180030b26  mov     rcx, rdi
0x180030b29  call    ?HrOperateNotifySemaphoreFromList@CSsdpNotifyRequestManager@@QEAAJPEAXW4_Semaphore_OPERATION@@@Z; CSsdpNotifyRequestManager::HrOperateNotifySemaphoreFromList(void *,_Semaphore_OPERATION)
0x180030b2e  mov     ebx, eax
0x180030b30  test    eax, eax
0x180030b32  jns     short loc_180030B62
0x180030b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b3b  cmp     rcx, rbp
0x180030b3e  jz      short loc_180030B62
0x180030b40  test    byte ptr [rcx+1Ch], 1
0x180030b44  jz      short loc_180030B62
0x180030b46  mov     rcx, [rcx+10h]
0x180030b4a  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x180030b51  mov     edx, 5Ah ; 'Z'
0x180030b56  mov     dword ptr [rsp+58h+var_38], eax
0x180030b5a  mov     r9, rsi
0x180030b5d  call    WPP_SF_qd
0x180030b62  mov     rcx, rdi; lpCriticalSection
0x180030b65  call    cs:__imp_LeaveCriticalSection
0x180030b6c  nop     dword ptr [rax+rax+00h]
0x180030b71  mov     eax, ebx
0x180030b73  add     rsp, 38h
0x180030b77  pop     rdi
0x180030b78  pop     rsi
0x180030b79  pop     rbp
0x180030b7a  pop     rbx
0x180030b7b  retn
```
