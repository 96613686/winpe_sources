# CWindowNotification::DeleteWindowNotification(void *,HWND__ *,int)

- ea: `0x180001908`
- end: `0x180001a0a`
- name: `?DeleteWindowNotification@CWindowNotification@@SAJPEAXPEAUHWND__@@H@Z`
- size: `258`
- prototype: `__int64 __fastcall(void *, HWND, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180001810`
- `0x1800018d0`
- `0x180029520`

## callees

- `0x180001908`
- `0x180001afc`
- `0x1800022f0`
- `0x180002ed8`
- `0x180002ff4`
- `0x180007890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800019c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800019c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001929`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001929`

## string_xrefs

- `0x1800019a0`: `CWindowNotification::DeleteWindowNotification`

## pseudocode

```c
__int64 __fastcall CWindowNotification::DeleteWindowNotification(void *a1, HWND a2, int a3)
{
  WCHAR *v6; // r14
  WCHAR *v7; // rdi
  int v8; // esi
  CWaitItem *v9; // rbx

  EnterCriticalSection(&CWindowNotification::g_WindowNotificationCS);
  v6 = *(WCHAR **)&CWindowNotification::g_WindowNotificationListHead;
  if ( *(WCHAR **)&CWindowNotification::g_WindowNotificationListHead == &CWindowNotification::g_WindowNotificationListHead )
  {
    v9 = 0;
    goto LABEL_11;
  }
  while ( 1 )
  {
    v7 = v6 - 796;
    if ( v6 != (WCHAR *)1592 )
      _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
    if ( CWindowNotification::IsSameTargetServer((CWindowNotification *)(v6 - 796), a1) == 1 )
    {
      v8 = CWindowNotification::DeleteFromWaitList((CWindowNotification *)(v6 - 796), a2);
      if ( v8 >= 0 )
        break;
    }
    v6 = *(WCHAR **)v6;
    v9 = 0;
    if ( v7 )
      CWaitItem::Release((CWaitItem *)v7);
    if ( v6 == &CWindowNotification::g_WindowNotificationListHead )
      goto LABEL_11;
  }
  if ( v6 == (WCHAR *)1592 )
  {
    v9 = 0;
LABEL_11:
    v8 = -2147024894;
    _DbgPrintMessage(
      8,
      "pWindowNotification not found failed: 0x%x in %s",
      -2147024894,
      "CWindowNotification::DeleteWindowNotification");
    goto LABEL_12;
  }
  if ( !*((_DWORD *)v7 + 406) )
    CWindowNotification::RemoveWindowNotificationFromList((struct CWindowNotification *)(v6 - 796), a3);
  v9 = (CWaitItem *)(v6 - 796);
LABEL_12:
  LeaveCriticalSection(&CWindowNotification::g_WindowNotificationCS);
  if ( v9 )
    CWaitItem::Release(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001908  push    rbx
0x18000190a  push    rbp
0x18000190b  push    rsi
0x18000190c  push    rdi
0x18000190d  push    r12
0x18000190f  push    r13
0x180001911  push    r14
0x180001913  push    r15
0x180001915  sub     rsp, 28h
0x180001919  mov     r15, rcx
0x18000191c  mov     ebp, r8d
0x18000191f  lea     rcx, ?g_WindowNotificationCS@CWindowNotification@@2VCCriticalSection@@A; lpCriticalSection
0x180001926  mov     r12, rdx
0x180001929  call    cs:__imp_EnterCriticalSection
0x18000192f  mov     r14, cs:?g_WindowNotificationListHead@CWindowNotification@@2U_LIST_ENTRY@@A; _LIST_ENTRY CWindowNotification::g_WindowNotificationListHead
0x180001936  lea     r13, ?g_WindowNotificationListHead@CWindowNotification@@2U_LIST_ENTRY@@A; _LIST_ENTRY CWindowNotification::g_WindowNotificationListHead
0x18000193d  cmp     r14, r13
0x180001940  jz      loc_1800019E8
0x180001946  lea     rdi, [r14-638h]
0x18000194d  test    rdi, rdi
0x180001950  jz      short loc_180001956
0x180001952  lock inc dword ptr [rdi+8]
0x180001956  mov     rdx, r15; void *
0x180001959  mov     rcx, rdi; this
0x18000195c  call    ?IsSameTargetServer@CWindowNotification@@QEAAHPEAX@Z; CWindowNotification::IsSameTargetServer(void *)
0x180001961  cmp     eax, 1
0x180001964  jnz     loc_1800019EC
0x18000196a  mov     rdx, r12; HWND
0x18000196d  mov     rcx, rdi; this
0x180001970  call    ?DeleteFromWaitList@CWindowNotification@@AEAAJPEAUHWND__@@@Z; CWindowNotification::DeleteFromWaitList(HWND__ *)
0x180001975  mov     esi, eax
0x180001977  test    eax, eax
0x180001979  js      short loc_1800019EC
0x18000197b  test    rdi, rdi
0x18000197e  jz      short loc_180001998
0x180001980  cmp     dword ptr [rdi+658h], 0
0x180001987  jnz     short loc_180001993
0x180001989  mov     edx, ebp; int
0x18000198b  mov     rcx, rdi; this
0x18000198e  call    ?RemoveWindowNotificationFromList@CWindowNotification@@SAJPEAV1@H@Z; CWindowNotification::RemoveWindowNotificationFromList(CWindowNotification *,int)
0x180001993  mov     rbx, rdi
0x180001996  jmp     short loc_1800019BB
0x180001998  mov     rbx, rdi
0x18000199b  mov     esi, 80070002h
0x1800019a0  lea     r9, aCwindownotific_3; "CWindowNotification::DeleteWindowNotifi"...
0x1800019a7  mov     r8d, esi
0x1800019aa  lea     rdx, aPwindownotific_0; "pWindowNotification not found failed: 0"...
0x1800019b1  mov     ecx, 8; int
0x1800019b6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800019bb  lea     rcx, ?g_WindowNotificationCS@CWindowNotification@@2VCCriticalSection@@A; lpCriticalSection
0x1800019c2  call    cs:__imp_LeaveCriticalSection
0x1800019c8  test    rbx, rbx
0x1800019cb  jz      short loc_1800019D5
0x1800019cd  mov     rcx, rbx; this
0x1800019d0  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x1800019d5  mov     eax, esi
0x1800019d7  add     rsp, 28h
0x1800019db  pop     r15
0x1800019dd  pop     r14
0x1800019df  pop     r13
0x1800019e1  pop     r12
0x1800019e3  pop     rdi
0x1800019e4  pop     rsi
0x1800019e5  pop     rbp
0x1800019e6  pop     rbx
0x1800019e7  retn
0x1800019e8  xor     ebx, ebx
0x1800019ea  jmp     short loc_18000199B
0x1800019ec  mov     r14, [r14]
0x1800019ef  xor     ebx, ebx
0x1800019f1  test    rdi, rdi
0x1800019f4  jnz     short loc_180001A00
0x1800019f6  cmp     r14, r13
0x1800019f9  jz      short loc_18000199B
0x1800019fb  jmp     loc_180001946
0x180001a00  mov     rcx, rdi; this
0x180001a03  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x180001a08  jmp     short loc_1800019F6
```
