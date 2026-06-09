# CWindowNotification::DeleteWindowNotification(void *,HWND__ *,int)

- ea: `0x18000b64c`
- end: `0x18000b75b`
- name: `?DeleteWindowNotification@CWindowNotification@@SAJPEAXPEAUHWND__@@H@Z`
- size: `271`
- prototype: `__int64 __fastcall(void *, HWND, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b610`
- `0x18000d150`
- `0x18002b130`

## callees

- `0x180005b40`
- `0x18000b64c`
- `0x18000b868`
- `0x18000c0c4`
- `0x18000cdc0`
- `0x18000ceec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b70c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b70c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b66d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b66d`

## string_xrefs

- `0x18000b6ea`: `CWindowNotification::DeleteWindowNotification`

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
0x18000b64c  push    rbx
0x18000b64e  push    rbp
0x18000b64f  push    rsi
0x18000b650  push    rdi
0x18000b651  push    r12
0x18000b653  push    r13
0x18000b655  push    r14
0x18000b657  push    r15
0x18000b659  sub     rsp, 28h
0x18000b65d  mov     r15, rcx
0x18000b660  mov     ebp, r8d
0x18000b663  lea     rcx, ?g_WindowNotificationCS@CWindowNotification@@2VCCriticalSection@@A; lpCriticalSection
0x18000b66a  mov     r12, rdx
0x18000b66d  call    cs:__imp_EnterCriticalSection
0x18000b674  nop     dword ptr [rax+rax+00h]
0x18000b679  mov     r14, cs:?g_WindowNotificationListHead@CWindowNotification@@2U_LIST_ENTRY@@A; _LIST_ENTRY CWindowNotification::g_WindowNotificationListHead
0x18000b680  lea     r13, ?g_WindowNotificationListHead@CWindowNotification@@2U_LIST_ENTRY@@A; _LIST_ENTRY CWindowNotification::g_WindowNotificationListHead
0x18000b687  cmp     r14, r13
0x18000b68a  jz      loc_18000B739
0x18000b690  lea     rdi, [r14-638h]
0x18000b697  test    rdi, rdi
0x18000b69a  jz      short loc_18000B6A0
0x18000b69c  lock inc dword ptr [rdi+8]
0x18000b6a0  mov     rdx, r15; void *
0x18000b6a3  mov     rcx, rdi; this
0x18000b6a6  call    ?IsSameTargetServer@CWindowNotification@@QEAAHPEAX@Z; CWindowNotification::IsSameTargetServer(void *)
0x18000b6ab  cmp     eax, 1
0x18000b6ae  jnz     loc_18000B73D
0x18000b6b4  mov     rdx, r12; HWND
0x18000b6b7  mov     rcx, rdi; this
0x18000b6ba  call    ?DeleteFromWaitList@CWindowNotification@@AEAAJPEAUHWND__@@@Z; CWindowNotification::DeleteFromWaitList(HWND__ *)
0x18000b6bf  mov     esi, eax
0x18000b6c1  test    eax, eax
0x18000b6c3  js      short loc_18000B73D
0x18000b6c5  test    rdi, rdi
0x18000b6c8  jz      short loc_18000B6E2
0x18000b6ca  cmp     dword ptr [rdi+658h], 0
0x18000b6d1  jnz     short loc_18000B6DD
0x18000b6d3  mov     edx, ebp; int
0x18000b6d5  mov     rcx, rdi; this
0x18000b6d8  call    ?RemoveWindowNotificationFromList@CWindowNotification@@SAJPEAV1@H@Z; CWindowNotification::RemoveWindowNotificationFromList(CWindowNotification *,int)
0x18000b6dd  mov     rbx, rdi
0x18000b6e0  jmp     short loc_18000B705
0x18000b6e2  mov     rbx, rdi
0x18000b6e5  mov     esi, 80070002h
0x18000b6ea  lea     r9, aCwindownotific_3; "CWindowNotification::DeleteWindowNotifi"...
0x18000b6f1  mov     r8d, esi
0x18000b6f4  lea     rdx, aPwindownotific_0; "pWindowNotification not found failed: 0"...
0x18000b6fb  mov     ecx, 8; int
0x18000b700  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000b705  lea     rcx, ?g_WindowNotificationCS@CWindowNotification@@2VCCriticalSection@@A; lpCriticalSection
0x18000b70c  call    cs:__imp_LeaveCriticalSection
0x18000b713  nop     dword ptr [rax+rax+00h]
0x18000b718  test    rbx, rbx
0x18000b71b  jz      short loc_18000B725
0x18000b71d  mov     rcx, rbx; this
0x18000b720  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x18000b725  mov     eax, esi
0x18000b727  add     rsp, 28h
0x18000b72b  pop     r15
0x18000b72d  pop     r14
0x18000b72f  pop     r13
0x18000b731  pop     r12
0x18000b733  pop     rdi
0x18000b734  pop     rsi
0x18000b735  pop     rbp
0x18000b736  pop     rbx
0x18000b737  retn
0x18000b739  xor     ebx, ebx
0x18000b73b  jmp     short loc_18000B6E5
0x18000b73d  mov     r14, [r14]
0x18000b740  xor     ebx, ebx
0x18000b742  test    rdi, rdi
0x18000b745  jnz     short loc_18000B751
0x18000b747  cmp     r14, r13
0x18000b74a  jz      short loc_18000B6E5
0x18000b74c  jmp     loc_18000B690
0x18000b751  mov     rcx, rdi; this
0x18000b754  call    ?Release@CWaitItem@@QEAAJXZ; CWaitItem::Release(void)
0x18000b759  jmp     short loc_18000B747
```
