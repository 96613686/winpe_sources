# RemoveWindowSubclass

- ea: `0x180014f1c`
- end: `0x180014f73`
- name: `RemoveWindowSubclass`
- size: `87`
- prototype: `BOOL __stdcall(HWND hWnd, SUBCLASSPROC pfnSubclass, UINT_PTR uIdSubclass)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018e30`

## callees

- `0x180014f1c`
- `0x180014fd0`
- `0x18001d010`

## pseudocode

```c
BOOL __stdcall RemoveWindowSubclass(HWND hWnd, SUBCLASSPROC pfnSubclass, UINT_PTR uIdSubclass)
{
  __int64 (__fastcall *v3)(HWND, __int64 (__fastcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, unsigned __int64), UINT_PTR); // rax

  v3 = (__int64 (__fastcall *)(HWND, __int64 (__fastcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, unsigned __int64), UINT_PTR))qword_18002E2F0;
  if ( qword_18002E2F0 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_18002E2F0, (const CHAR *)0x19C);
    v3 = (__int64 (__fastcall *)(HWND, __int64 (__fastcall *)(HWND, UINT, WPARAM, LPARAM, UINT_PTR, unsigned __int64), UINT_PTR))qword_18002E2F0;
  }
  if ( v3 )
    LODWORD(v3) = v3(hWnd, LogonScreenHelper::RestrictedEditSubclassProc, uIdSubclass);
  return (int)v3;
}

```

## disassembly

```asm
0x180014f1c  mov     [rsp+arg_0], rbx
0x180014f21  push    rdi
0x180014f22  sub     rsp, 20h
0x180014f26  mov     rax, cs:qword_18002E2F0
0x180014f2d  mov     rbx, r8
0x180014f30  mov     rdi, rcx
0x180014f33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014f37  jnz     short loc_180014F51
0x180014f39  mov     edx, 19Ch
0x180014f3e  lea     rcx, qword_18002E2F0
0x180014f45  call    _GetProcFromComCtl32
0x180014f4a  mov     rax, cs:qword_18002E2F0
0x180014f51  test    rax, rax
0x180014f54  jz      short loc_180014F68
0x180014f56  mov     r8, rbx
0x180014f59  lea     rdx, ?RestrictedEditSubclassProc@LogonScreenHelper@@SA_JPEAUHWND__@@I_K_J11@Z; LogonScreenHelper::RestrictedEditSubclassProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x180014f60  mov     rcx, rdi
0x180014f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f68  mov     rbx, [rsp+28h+arg_0]
0x180014f6d  add     rsp, 20h
0x180014f71  pop     rdi
0x180014f72  retn
```
