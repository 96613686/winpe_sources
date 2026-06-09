# TaskDialogIndirect

- ea: `0x1800165e8`
- end: `0x18001664a`
- name: `TaskDialogIndirect`
- size: `98`
- prototype: `HRESULT __stdcall(const TASKDIALOGCONFIG *pTaskConfig, int *pnButton, int *pnRadioButton, BOOL *pfVerificationFlagChecked)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ec90`
- `0x1800100ac`

## callees

- `0x1800165e8`
- `0x180016650`
- `0x18001e010`

## string_xrefs

- `0x18001660a`: `TaskDialogIndirect`

## pseudocode

```c
HRESULT __stdcall TaskDialogIndirect(
        const TASKDIALOGCONFIG *pTaskConfig,
        int *pnButton,
        int *pnRadioButton,
        BOOL *pfVerificationFlagChecked)
{
  __int64 (__fastcall *v4)(const TASKDIALOGCONFIG *, int *, int *, BOOL *); // rax

  v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_18002A318;
  if ( qword_18002A318 == -1 )
  {
    GetProcFromComCtl32(&qword_18002A318, "TaskDialogIndirect");
    v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_18002A318;
  }
  if ( v4 )
    return v4(pTaskConfig, pnButton, pnRadioButton, pfVerificationFlagChecked);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x1800165e8  push    rbx
0x1800165ea  push    rbp
0x1800165eb  push    rsi
0x1800165ec  push    rdi
0x1800165ed  sub     rsp, 38h
0x1800165f1  mov     rax, cs:qword_18002A318
0x1800165f8  mov     rbx, r9
0x1800165fb  mov     rdi, r8
0x1800165fe  mov     rsi, rdx
0x180016601  mov     rbp, rcx
0x180016604  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016608  jnz     short loc_180016624
0x18001660a  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x180016611  lea     rcx, qword_18002A318
0x180016618  call    _GetProcFromComCtl32
0x18001661d  mov     rax, cs:qword_18002A318
0x180016624  test    rax, rax
0x180016627  jz      short loc_18001663C
0x180016629  mov     r9, rbx
0x18001662c  mov     r8, rdi
0x18001662f  mov     rdx, rsi
0x180016632  mov     rcx, rbp
0x180016635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001663a  jmp     short loc_180016641
0x18001663c  mov     eax, 80004005h
0x180016641  add     rsp, 38h
0x180016645  pop     rdi
0x180016646  pop     rsi
0x180016647  pop     rbp
0x180016648  pop     rbx
0x180016649  retn
```
