# CWindowNotification::DeleteFromWaitList(HWND__ *)

- ea: `0x180002ed8`
- end: `0x180002fb9`
- name: `?DeleteFromWaitList@CWindowNotification@@AEAAJPEAUHWND__@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(CWindowNotification *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001908`

## callees

- `0x180002ed8`
- `0x180002fc0`
- `0x180007890`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ef7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ef7`

## string_xrefs

- `0x180002f11`: `CWindowNotification::DeleteFromWaitList`

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
0x180002ed8  push    rbx
0x180002eda  push    rbp
0x180002edb  push    rsi
0x180002edc  push    rdi
0x180002edd  push    r14
0x180002edf  push    r15
0x180002ee1  sub     rsp, 28h
0x180002ee5  lea     r14, [rcx+660h]
0x180002eec  mov     rbp, rcx
0x180002eef  mov     rcx, r14; lpCriticalSection
0x180002ef2  mov     r15, rdx
0x180002ef5  xor     ebx, ebx
0x180002ef7  call    cs:__imp_EnterCriticalSection
0x180002efd  lea     rsi, [rbp+648h]
0x180002f04  mov     rdi, [rsi]
0x180002f07  cmp     rdi, rsi
0x180002f0a  jnz     short loc_180002F2E
0x180002f0c  mov     edi, 80070002h
0x180002f11  lea     r9, aCwindownotific_4; "CWindowNotification::DeleteFromWaitList"
0x180002f18  mov     r8d, edi
0x180002f1b  lea     rdx, aFindingItemFai; "Finding item failed: 0x%x in %s"
0x180002f22  mov     ecx, 8; int
0x180002f27  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180002f2c  jmp     short loc_180002F86
0x180002f2e  lea     rcx, [rdi-10h]; this
0x180002f32  mov     rbx, rcx
0x180002f35  test    rcx, rcx
0x180002f38  jz      short loc_180002F3E
0x180002f3a  lock inc dword ptr [rcx+8]
0x180002f3e  cmp     r15, [rcx+60h]
0x180002f42  jz      short loc_180002F53
0x180002f44  mov     rdi, [rdi]
0x180002f47  xor     ebx, ebx
0x180002f49  test    rcx, rcx
0x180002f4c  jnz     short loc_180002FAB
0x180002f4e  cmp     rdi, rsi
0x180002f51  jnz     short loc_180002F2E
0x180002f53  test    rbx, rbx
0x180002f56  jz      short loc_180002F0C
0x180002f58  lea     rax, [rbx+10h]
0x180002f5c  mov     rcx, [rax]
0x180002f5f  cmp     [rcx+8], rax
0x180002f63  jnz     short loc_180002FB2
0x180002f65  mov     rdx, [rax+8]
0x180002f69  cmp     [rdx], rax
0x180002f6c  jnz     short loc_180002FB2
0x180002f6e  mov     [rdx], rcx
0x180002f71  mov     [rcx+8], rdx
0x180002f75  mov     rcx, rbx; this
0x180002f78  call    ?Release@NotificationItem@@QEAAJXZ; NotificationItem::Release(void)
0x180002f7d  lock dec dword ptr [rbp+658h]
0x180002f84  xor     edi, edi
0x180002f86  mov     rcx, r14; lpCriticalSection
0x180002f89  call    cs:__imp_LeaveCriticalSection
0x180002f8f  test    rbx, rbx
0x180002f92  jz      short loc_180002F9C
0x180002f94  mov     rcx, rbx; this
0x180002f97  call    ?Release@NotificationItem@@QEAAJXZ; NotificationItem::Release(void)
0x180002f9c  mov     eax, edi
0x180002f9e  add     rsp, 28h
0x180002fa2  pop     r15
0x180002fa4  pop     r14
0x180002fa6  pop     rdi
0x180002fa7  pop     rsi
0x180002fa8  pop     rbp
0x180002fa9  pop     rbx
0x180002faa  retn
0x180002fab  call    ?Release@NotificationItem@@QEAAJXZ; NotificationItem::Release(void)
0x180002fb0  jmp     short loc_180002F4E
0x180002fb2  mov     ecx, 3
0x180002fb7  int     29h; Win8: RtlFailFast(ecx)
```
