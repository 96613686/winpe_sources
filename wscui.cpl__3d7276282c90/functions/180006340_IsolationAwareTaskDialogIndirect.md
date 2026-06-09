# IsolationAwareTaskDialogIndirect

- ea: `0x180006340`
- end: `0x1800063f6`
- name: `IsolationAwareTaskDialogIndirect`
- size: `182`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800054f0`
- `0x18000592c`
- `0x180005cf4`
- `0x1800072a4`

## callees

- `0x180003e54`
- `0x180003fa8`
- `0x180006258`
- `0x180006340`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800063ec`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000adf8`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800063ec`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000adf8`

## string_xrefs

- `0x18000639b`: `TaskDialogIndirect`

## pseudocode

```c
__int64 __fastcall IsolationAwareTaskDialogIndirect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, __int64); // rbx
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  ULONG_PTR ulCookie; // [rsp+70h] [rbp+18h] BYREF

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))`IsolationAwareTaskDialogIndirect'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
  }
  if ( !v7 )
  {
    v9 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialogIndirect");
    v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))v9;
    if ( !v9 )
    {
      v10 = CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
      goto LABEL_10;
    }
    `IsolationAwareTaskDialogIndirect'::`2'::s_pfn = v9;
  }
  v10 = v7(a1, a2, 0, a4);
LABEL_10:
  v11 = v10;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return v11;
}

```

## disassembly

```asm
0x180006340  mov     [rsp+ulCookie], r8
0x180006345  push    rbx
0x180006346  push    rsi
0x180006347  push    rdi
0x180006348  push    r14
0x18000634a  sub     rsp, 38h
0x18000634e  mov     rdi, r9
0x180006351  mov     rsi, rdx
0x180006354  mov     r14, rcx
0x180006357  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18000635e  mov     [rsp+58h+ulCookie], 0
0x180006367  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000636e  jnz     short loc_180006396
0x180006370  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006377  jnz     short loc_180006396
0x180006379  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x18000637e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180006383  test    eax, eax
0x180006385  jnz     short loc_180006396
0x180006387  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x18000638c  add     rsp, 38h
0x180006390  pop     r14
0x180006392  pop     rdi
0x180006393  pop     rsi
0x180006394  pop     rbx
0x180006395  retn
0x180006396  test    rbx, rbx
0x180006399  jnz     short loc_1800063BD
0x18000639b  lea     rcx, ProcName; "TaskDialogIndirect"
0x1800063a2  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800063a7  mov     rbx, rax
0x1800063aa  test    rax, rax
0x1800063ad  jnz     short loc_1800063B6
0x1800063af  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x1800063b4  jmp     short loc_1800063D1
0x1800063b6  mov     cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA, rax; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x1800063bd  mov     r9, rdi
0x1800063c0  xor     r8d, r8d
0x1800063c3  mov     rdx, rsi
0x1800063c6  mov     rcx, r14
0x1800063c9  mov     rax, rbx
0x1800063cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d1  mov     ebx, eax
0x1800063d3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800063da  jz      short loc_1800063E5
0x1800063dc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800063e3  jnz     short loc_1800063F2
0x1800063e5  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x1800063ea  xor     ecx, ecx; dwFlags
0x1800063ec  call    cs:__imp_DeactivateActCtx
0x1800063f2  mov     eax, ebx
0x1800063f4  jmp     short loc_18000638C
0x18000add7  push    rbp
0x18000add9  sub     rsp, 30h
0x18000addd  mov     rbp, rdx
0x18000ade0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ade7  jz      short loc_18000ADF2
0x18000ade9  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000adf0  jnz     short loc_18000ADFF
0x18000adf2  mov     rdx, [rbp+70h]; ulCookie
0x18000adf6  xor     ecx, ecx; dwFlags
0x18000adf8  call    cs:__imp_DeactivateActCtx
0x18000adfe  nop
0x18000adff  add     rsp, 30h
0x18000ae03  pop     rbp
0x18000ae04  retn
```
