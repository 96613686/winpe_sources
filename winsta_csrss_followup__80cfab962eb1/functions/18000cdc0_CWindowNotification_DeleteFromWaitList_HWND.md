# CWindowNotification::DeleteFromWaitList(HWND__ *)

- ea: `0x18000cdc0`
- end: `0x18000ceae`
- name: `?DeleteFromWaitList@CWindowNotification@@AEAAJPEAUHWND__@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CWindowNotification *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b64c`

## callees

- `0x180005b40`
- `0x18000cdc0`
- `0x18000ceb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cddf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cddf`

## string_xrefs

- `0x18000cdff`: `CWindowNotification::DeleteFromWaitList`

## pseudocode

```c
__int64 __fastcall CWindowNotification::DeleteFromWaitList(CWindowNotification *this, HWND a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  NotificationItem *v5; // rbx
  CWindowNotification *v6; // rdi
  unsigned int v7; // edi
  volatile signed __int32 *v8; // rcx
  NotificationItem **v9; // rcx
  NotificationItem **v10; // rdx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1632);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1632));
  v6 = (CWindowNotification *)*((_QWORD *)this + 201);
  if ( v6 == (CWindowNotification *)((char *)this + 1608) )
    goto LABEL_2;
  do
  {
    v8 = (volatile signed __int32 *)((char *)v6 - 16);
    v5 = (CWindowNotification *)((char *)v6 - 16);
    if ( v6 != (CWindowNotification *)16 )
      _InterlockedIncrement(v8 + 2);
    if ( a2 == *((HWND *)v8 + 12) )
      break;
    v6 = *(CWindowNotification **)v6;
    v5 = 0;
    if ( v8 )
      NotificationItem::Release((NotificationItem *)v8);
  }
  while ( v6 != (CWindowNotification *)((char *)this + 1608) );
  if ( !v5 )
  {
LABEL_2:
    v7 = -2147024894;
    _DbgPrintMessage(8, "Finding item failed: 0x%x in %s", -2147024894, "CWindowNotification::DeleteFromWaitList");
  }
  else
  {
    v9 = (NotificationItem **)*((_QWORD *)v5 + 2);
    if ( v9[1] != (NotificationItem *)((char *)v5 + 16)
      || (v10 = (NotificationItem **)*((_QWORD *)v5 + 3), *v10 != (NotificationItem *)((char *)v5 + 16)) )
    {
      __fastfail(3u);
    }
    *v10 = (NotificationItem *)v9;
    v9[1] = (NotificationItem *)v10;
    NotificationItem::Release(v5);
    _InterlockedDecrement((volatile signed __int32 *)this + 406);
    v7 = 0;
  }
  LeaveCriticalSection(v2);
  if ( v5 )
    NotificationItem::Release(v5);
  return v7;
}

```

## disassembly

```asm
0x18000cdc0  push    rbx
0x18000cdc2  push    rbp
0x18000cdc3  push    rsi
0x18000cdc4  push    rdi
0x18000cdc5  push    r14
0x18000cdc7  push    r15
0x18000cdc9  sub     rsp, 28h
0x18000cdcd  lea     r14, [rcx+660h]
0x18000cdd4  mov     rbp, rcx
0x18000cdd7  mov     rcx, r14; lpCriticalSection
0x18000cdda  mov     r15, rdx
0x18000cddd  xor     ebx, ebx
0x18000cddf  call    cs:__imp_EnterCriticalSection
0x18000cde6  nop     dword ptr [rax+rax+00h]
0x18000cdeb  lea     rsi, [rbp+648h]
0x18000cdf2  mov     rdi, [rsi]
0x18000cdf5  cmp     rdi, rsi
0x18000cdf8  jnz     short loc_18000CE1C
0x18000cdfa  mov     edi, 80070002h
0x18000cdff  lea     r9, aCwindownotific_4; "CWindowNotification::DeleteFromWaitList"
0x18000ce06  mov     r8d, edi
0x18000ce09  lea     rdx, aFindingItemFai; "Finding item failed: 0x%x in %s"
0x18000ce10  mov     ecx, 8; int
0x18000ce15  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ce1a  jmp     short loc_18000CE74
0x18000ce1c  lea     rcx, [rdi-10h]; this
0x18000ce20  mov     rbx, rcx
0x18000ce23  test    rcx, rcx
0x18000ce26  jz      short loc_18000CE2C
0x18000ce28  lock inc dword ptr [rcx+8]
0x18000ce2c  cmp     r15, [rcx+60h]
0x18000ce30  jz      short loc_18000CE41
0x18000ce32  mov     rdi, [rdi]
0x18000ce35  xor     ebx, ebx
0x18000ce37  test    rcx, rcx
0x18000ce3a  jnz     short loc_18000CEA0
0x18000ce3c  cmp     rdi, rsi
0x18000ce3f  jnz     short loc_18000CE1C
0x18000ce41  test    rbx, rbx
0x18000ce44  jz      short loc_18000CDFA
0x18000ce46  lea     rax, [rbx+10h]
0x18000ce4a  mov     rcx, [rax]
0x18000ce4d  cmp     [rcx+8], rax
0x18000ce51  jnz     short loc_18000CEA7
0x18000ce53  mov     rdx, [rax+8]
0x18000ce57  cmp     [rdx], rax
0x18000ce5a  jnz     short loc_18000CEA7
0x18000ce5c  mov     [rdx], rcx
0x18000ce5f  mov     [rcx+8], rdx
0x18000ce63  mov     rcx, rbx; this
0x18000ce66  call    ?Release@NotificationItem@@QEAAJXZ; NotificationItem::Release(void)
0x18000ce6b  lock dec dword ptr [rbp+658h]
0x18000ce72  xor     edi, edi
0x18000ce74  mov     rcx, r14; lpCriticalSection
0x18000ce77  call    cs:__imp_LeaveCriticalSection
0x18000ce7e  nop     dword ptr [rax+rax+00h]
0x18000ce83  test    rbx, rbx
0x18000ce86  jz      short loc_18000CE90
0x18000ce88  mov     rcx, rbx; this
0x18000ce8b  call    ?Release@NotificationItem@@QEAAJXZ; NotificationItem::Release(void)
0x18000ce90  mov     eax, edi
0x18000ce92  add     rsp, 28h
0x18000ce96  pop     r15
0x18000ce98  pop     r14
0x18000ce9a  pop     rdi
0x18000ce9b  pop     rsi
0x18000ce9c  pop     rbp
0x18000ce9d  pop     rbx
0x18000ce9e  retn
0x18000cea0  call    ?Release@NotificationItem@@QEAAJXZ; NotificationItem::Release(void)
0x18000cea5  jmp     short loc_18000CE3C
0x18000cea7  mov     ecx, 3
0x18000ceac  int     29h; Win8: RtlFailFast(ecx)
```
