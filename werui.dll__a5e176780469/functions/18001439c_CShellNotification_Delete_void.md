# CShellNotification::Delete(void)

- ea: `0x18001439c`
- end: `0x180014430`
- name: `?Delete@CShellNotification@@QEAAJXZ`
- size: `148`
- prototype: `__int64 __fastcall(CShellNotification *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180010234`
- `0x180013f10`

## callees

- `0x180003fe4`
- `0x180013ef0`
- `0x18001439c`
- `0x180014438`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800143b2`
- `KERNEL32!EnterCriticalSection` at `0x1800143b2`
- `KERNEL32!GetLastError` at `0x1800143db`
- `KERNEL32!GetLastError` at `0x1800143db`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18001440d`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x18001440d`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800143f5`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800143f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShellNotification::Delete(CShellNotification *this)
{
  unsigned int v2; // edi
  DWORD LastError; // eax
  char *v5; // [rsp+20h] [rbp-18h] BYREF
  char v6; // [rsp+28h] [rbp-10h]

  v5 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v6 = 1;
  if ( *(_DWORD *)this )
  {
    if ( (unsigned int)CShellNotification::InvokeShell_NotifyIcon(
                         this,
                         2u,
                         (struct _NOTIFYICONDATAW *)((char *)this + 88)) )
    {
      v2 = -2147467259;
      if ( IsWindow(*((HWND *)this + 1)) )
        PostMessageW(*((HWND *)this + 1), 0x12u, 0, 0);
      *(_DWORD *)this = 0;
    }
    else
    {
      LastError = GetLastError();
      v2 = ERROR_HR_FROM_WIN32(LastError);
    }
  }
  else
  {
    v2 = 0;
  }
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v5);
  return v2;
}

```

## disassembly

```asm
0x18001439c  mov     [rsp+arg_0], rbx
0x1800143a1  push    rdi
0x1800143a2  sub     rsp, 30h
0x1800143a6  mov     rbx, rcx
0x1800143a9  add     rcx, 18h; lpCriticalSection
0x1800143ad  mov     [rsp+38h+var_18], rcx
0x1800143b2  call    cs:__imp_EnterCriticalSection
0x1800143b8  mov     [rsp+38h+var_10], 1
0x1800143bd  cmp     dword ptr [rbx], 0
0x1800143c0  jnz     short loc_1800143C6
0x1800143c2  xor     edi, edi
0x1800143c4  jmp     short loc_180014419
0x1800143c6  lea     r8, [rbx+58h]; struct _NOTIFYICONDATAW *
0x1800143ca  mov     edx, 2; unsigned int
0x1800143cf  mov     rcx, rbx; this
0x1800143d2  call    ?InvokeShell_NotifyIcon@CShellNotification@@AEAAHKPEAU_NOTIFYICONDATAW@@@Z; CShellNotification::InvokeShell_NotifyIcon(ulong,_NOTIFYICONDATAW *)
0x1800143d7  test    eax, eax
0x1800143d9  jnz     short loc_1800143EC
0x1800143db  call    cs:__imp_GetLastError
0x1800143e1  mov     ecx, eax; unsigned int
0x1800143e3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800143e8  mov     edi, eax
0x1800143ea  jmp     short loc_180014419
0x1800143ec  mov     edi, 80004005h
0x1800143f1  mov     rcx, [rbx+8]; hWnd
0x1800143f5  call    cs:__imp_IsWindow
0x1800143fb  test    eax, eax
0x1800143fd  jz      short loc_180014413
0x1800143ff  xor     r9d, r9d; lParam
0x180014402  xor     r8d, r8d; wParam
0x180014405  lea     edx, [r9+12h]; Msg
0x180014409  mov     rcx, [rbx+8]; hWnd
0x18001440d  call    cs:__imp_PostMessageW
0x180014413  mov     dword ptr [rbx], 0
0x180014419  lea     rcx, [rsp+38h+var_18]
0x18001441e  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x180014423  mov     eax, edi
0x180014425  mov     rbx, [rsp+38h+arg_0]
0x18001442a  add     rsp, 30h
0x18001442e  pop     rdi
0x18001442f  retn
```
