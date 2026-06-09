# EnumDesktopProc(ushort *,__int64)

- ea: `0x18001e600`
- end: `0x18001e688`
- name: `?EnumDesktopProc@@YAHPEAG_J@Z`
- size: `136`
- prototype: `__int64 __fastcall(const WCHAR *, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001e600`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001e62b`
- `KERNEL32!GetCurrentThreadId` at `0x18001e62b`
- `USER32!OpenDesktopW` at `0x18001e61d`
- `USER32!OpenDesktopW` at `0x18001e61d`
- `USER32!GetThreadDesktop` at `0x18001e633`
- `USER32!GetThreadDesktop` at `0x18001e633`
- `USER32!SetThreadDesktop` at `0x18001e644`
- `USER32!SetThreadDesktop` at `0x18001e664`
- `USER32!SetThreadDesktop` at `0x18001e644`
- `USER32!SetThreadDesktop` at `0x18001e664`
- `USER32!EnumDesktopWindows` at `0x18001e65b`
- `USER32!EnumDesktopWindows` at `0x18001e65b`
- `USER32!CloseDesktop` at `0x18001e66d`
- `USER32!CloseDesktop` at `0x18001e66d`

## pseudocode

```c
__int64 __fastcall EnumDesktopProc(const WCHAR *a1, LPARAM a2)
{
  HDESK v3; // rbx
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rdi

  v3 = OpenDesktopW(a1, 0, 0, 1u);
  if ( v3 )
  {
    CurrentThreadId = GetCurrentThreadId();
    ThreadDesktop = GetThreadDesktop(CurrentThreadId);
    if ( ThreadDesktop )
    {
      if ( SetThreadDesktop(v3) )
        EnumDesktopWindows(v3, EnumWindowsProc, a2);
      SetThreadDesktop(ThreadDesktop);
    }
    CloseDesktop(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x18001e600  mov     [rsp+arg_0], rbx
0x18001e605  mov     [rsp+arg_8], rsi
0x18001e60a  push    rdi
0x18001e60b  sub     rsp, 20h
0x18001e60f  mov     rsi, rdx
0x18001e612  mov     r9d, 1; dwDesiredAccess
0x18001e618  xor     edx, edx; dwFlags
0x18001e61a  xor     r8d, r8d; fInherit
0x18001e61d  call    cs:__imp_OpenDesktopW
0x18001e623  mov     rbx, rax
0x18001e626  test    rax, rax
0x18001e629  jz      short loc_18001E673
0x18001e62b  call    cs:__imp_GetCurrentThreadId
0x18001e631  mov     ecx, eax; dwThreadId
0x18001e633  call    cs:__imp_GetThreadDesktop
0x18001e639  mov     rdi, rax
0x18001e63c  test    rax, rax
0x18001e63f  jz      short loc_18001E66A
0x18001e641  mov     rcx, rbx; hDesktop
0x18001e644  call    cs:__imp_SetThreadDesktop
0x18001e64a  test    eax, eax
0x18001e64c  jz      short loc_18001E661
0x18001e64e  mov     r8, rsi; lParam
0x18001e651  lea     rdx, ?EnumWindowsProc@@YAHPEAUHWND__@@_J@Z; lpfn
0x18001e658  mov     rcx, rbx; hDesktop
0x18001e65b  call    cs:__imp_EnumDesktopWindows
0x18001e661  mov     rcx, rdi; hDesktop
0x18001e664  call    cs:__imp_SetThreadDesktop
0x18001e66a  mov     rcx, rbx; hDesktop
0x18001e66d  call    cs:__imp_CloseDesktop
0x18001e673  mov     rbx, [rsp+28h+arg_0]
0x18001e678  mov     eax, 1
0x18001e67d  mov     rsi, [rsp+28h+arg_8]
0x18001e682  add     rsp, 20h
0x18001e686  pop     rdi
0x18001e687  retn
```
