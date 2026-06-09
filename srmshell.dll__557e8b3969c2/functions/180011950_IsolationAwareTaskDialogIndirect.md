# IsolationAwareTaskDialogIndirect

- ea: `0x180011950`
- end: `0x180011a3a`
- name: `IsolationAwareTaskDialogIndirect`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005fa0`
- `0x18000e6d4`
- `0x18000ea78`

## callees

- `0x1800111c8`
- `0x1800117d4`
- `0x180011950`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119d6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011a2d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e4e1`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011a2d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e4e1`

## string_xrefs

- `0x1800119c2`: `TaskDialogIndirect`

## pseudocode

```c
signed int __fastcall IsolationAwareTaskDialogIndirect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, __int64); // rbx
  signed int result; // eax
  __int64 v9; // rax
  signed int LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+70h] [rbp+18h] BYREF

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))`IsolationAwareTaskDialogIndirect'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    result = GetLastError();
    if ( !result )
      result = 1359;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( !v7 )
  {
    v9 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialogIndirect");
    v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1359;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    `IsolationAwareTaskDialogIndirect'::`2'::s_pfn = v9;
  }
  LastError = v7(a1, a2, 0, a4);
LABEL_17:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return LastError;
}

```

## disassembly

```asm
0x180011950  mov     [rsp+ulCookie], r8
0x180011955  push    rbx
0x180011956  push    rsi
0x180011957  push    rdi
0x180011958  push    r14
0x18001195a  sub     rsp, 38h
0x18001195e  mov     rdi, r9
0x180011961  mov     rsi, rdx
0x180011964  mov     r14, rcx
0x180011967  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18001196e  mov     [rsp+58h+ulCookie], 0
0x180011977  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001197e  jnz     short loc_1800119BD
0x180011980  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011987  jnz     short loc_1800119BD
0x180011989  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x18001198e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180011993  test    eax, eax
0x180011995  jnz     short loc_1800119BD
0x180011997  call    cs:__imp_GetLastError
0x18001199d  mov     ecx, 54Fh
0x1800119a2  test    eax, eax
0x1800119a4  cmovz   eax, ecx
0x1800119a7  test    eax, eax
0x1800119a9  jle     short loc_1800119B3
0x1800119ab  movzx   eax, ax
0x1800119ae  or      eax, 80070000h
0x1800119b3  add     rsp, 38h
0x1800119b7  pop     r14
0x1800119b9  pop     rdi
0x1800119ba  pop     rsi
0x1800119bb  pop     rbx
0x1800119bc  retn
0x1800119bd  test    rbx, rbx
0x1800119c0  jnz     short loc_1800119FE
0x1800119c2  lea     rcx, aTaskdialogindi; "TaskDialogIndirect"
0x1800119c9  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x1800119ce  mov     rbx, rax
0x1800119d1  test    rax, rax
0x1800119d4  jnz     short loc_1800119F7
0x1800119d6  call    cs:__imp_GetLastError
0x1800119dc  mov     ebx, eax
0x1800119de  mov     ecx, 54Fh
0x1800119e3  test    eax, eax
0x1800119e5  cmovz   ebx, ecx
0x1800119e8  test    ebx, ebx
0x1800119ea  jle     short loc_180011A14
0x1800119ec  movzx   ebx, bx
0x1800119ef  or      ebx, 80070000h
0x1800119f5  jmp     short loc_180011A14
0x1800119f7  mov     cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA, rax; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x1800119fe  mov     r9, rdi
0x180011a01  xor     r8d, r8d
0x180011a04  mov     rdx, rsi
0x180011a07  mov     rcx, r14
0x180011a0a  mov     rax, rbx
0x180011a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a12  mov     ebx, eax
0x180011a14  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180011a1b  jz      short loc_180011A26
0x180011a1d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011a24  jnz     short loc_180011A33
0x180011a26  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x180011a2b  xor     ecx, ecx; dwFlags
0x180011a2d  call    cs:__imp_DeactivateActCtx
0x180011a33  mov     eax, ebx
0x180011a35  jmp     loc_1800119B3
0x18001e4c0  push    rbp
0x18001e4c2  sub     rsp, 30h
0x18001e4c6  mov     rbp, rdx
0x18001e4c9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18001e4d0  jz      short loc_18001E4DB
0x18001e4d2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e4d9  jnz     short loc_18001E4E8
0x18001e4db  mov     rdx, [rbp+70h]; ulCookie
0x18001e4df  xor     ecx, ecx; dwFlags
0x18001e4e1  call    cs:__imp_DeactivateActCtx
0x18001e4e7  nop
0x18001e4e8  add     rsp, 30h
0x18001e4ec  pop     rbp
0x18001e4ed  retn
```
