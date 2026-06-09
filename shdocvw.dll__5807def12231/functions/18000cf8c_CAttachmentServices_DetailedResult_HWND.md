# CAttachmentServices::DetailedResult(HWND__ *)

- ea: `0x18000cf8c`
- end: `0x18000d00f`
- name: `?DetailedResult@CAttachmentServices@@AEAAJPEAUHWND__@@@Z`
- size: `131`
- prototype: `__int64 __fastcall(CAttachmentServices *this, HWND hWndParent)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18000d110`
- `0x18000f420`
- `0x1800113a0`
- `0x18001143c`

## callees

- `0x1800057fc`
- `0x18000cf8c`
- `0x18001003c`
- `0x180029010`

## import_xrefs

- `SHELL32!__imp_Win32DeleteFile` at `0x18000cff7`
- `SHELL32!__imp_Win32DeleteFile` at `0x18000cff7`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::DetailedResult(CAttachmentServices *this, HWND hWndParent)
{
  const WCHAR *v4; // rcx

  if ( *((int *)this + 72) < 0 )
  {
    if ( hWndParent && *((_DWORD *)this + 74) )
    {
      (*(void (__fastcall **)(CAttachmentServices *))(*(_QWORD *)this + 8LL))(this);
      SHFusionDialogBoxParam(
        g_hinst,
        (LPCWSTR)0x1155,
        hWndParent,
        (DLGPROC)CAttachmentServices::_NotifyDeleteDlgProc,
        (LPARAM)this);
      (*(void (__fastcall **)(CAttachmentServices *))(*(_QWORD *)this + 16LL))(this);
    }
    v4 = (const WCHAR *)*((_QWORD *)this + 5);
    if ( v4 )
      Win32DeleteFile(v4);
  }
  return CAttachmentServices::Result(this);
}

```

## disassembly

```asm
0x18000cf8c  mov     [rsp+arg_0], rbx
0x18000cf91  push    rdi
0x18000cf92  sub     rsp, 30h
0x18000cf96  cmp     dword ptr [rcx+120h], 0
0x18000cf9d  mov     rdi, rdx
0x18000cfa0  mov     rbx, rcx
0x18000cfa3  jge     short loc_18000CFFD
0x18000cfa5  test    rdx, rdx
0x18000cfa8  jz      short loc_18000CFEE
0x18000cfaa  cmp     dword ptr [rcx+128h], 0
0x18000cfb1  jz      short loc_18000CFEE
0x18000cfb3  mov     rax, [rcx]
0x18000cfb6  mov     rax, [rax+8]
0x18000cfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfbf  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000cfc6  lea     r9, ?_NotifyDeleteDlgProc@CAttachmentServices@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000cfcd  mov     r8, rdi; hWndParent
0x18000cfd0  mov     [rsp+38h+var_18], rbx; LPARAM
0x18000cfd5  mov     edx, 1155h; lpTemplateName
0x18000cfda  call    SHFusionDialogBoxParam
0x18000cfdf  mov     rax, [rbx]
0x18000cfe2  mov     rcx, rbx
0x18000cfe5  mov     rax, [rax+10h]
0x18000cfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfee  mov     rcx, [rbx+28h]; pszPath
0x18000cff2  test    rcx, rcx
0x18000cff5  jz      short loc_18000CFFD
0x18000cff7  call    cs:__imp_Win32DeleteFile
0x18000cffd  mov     rcx, rbx; this
0x18000d000  mov     rbx, [rsp+38h+arg_0]
0x18000d005  add     rsp, 30h
0x18000d009  pop     rdi
0x18000d00a  jmp     ?Result@CAttachmentServices@@AEAAJXZ
```
