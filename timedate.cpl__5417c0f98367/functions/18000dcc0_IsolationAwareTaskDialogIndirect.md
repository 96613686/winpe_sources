# IsolationAwareTaskDialogIndirect

- ea: `0x18000dcc0`
- end: `0x18000dd70`
- name: `IsolationAwareTaskDialogIndirect`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c2b0`

## callees

- `0x180009a60`
- `0x18000d8dc`
- `0x18000d908`
- `0x18000dcc0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000dd66`
- `KERNEL32!DeactivateActCtx` at `0x180029566`
- `KERNEL32!DeactivateActCtx` at `0x18000dd66`
- `KERNEL32!DeactivateActCtx` at `0x180029566`

## string_xrefs

- `0x18000dd16`: `TaskDialogIndirect`

## pseudocode

```c
__int64 __fastcall IsolationAwareTaskDialogIndirect(__int64 a1)
{
  __int64 (__fastcall *v2)(__int64, _QWORD, _QWORD, _QWORD); // rbx
  __int64 v4; // rax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  ULONG_PTR ulCookie; // [rsp+58h] [rbp+20h] BYREF

  v2 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))`IsolationAwareTaskDialogIndirect'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
  }
  if ( !v2 )
  {
    v4 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialogIndirect");
    v2 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v4;
    if ( !v4 )
    {
      v5 = CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
      goto LABEL_10;
    }
    `IsolationAwareTaskDialogIndirect'::`2'::s_pfn = v4;
  }
  v5 = v2(a1, 0, 0, 0);
LABEL_10:
  v6 = v5;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return v6;
}

```

## disassembly

```asm
0x18000dcc0  mov     rax, rsp
0x18000dcc3  mov     [rax+8], rbx
0x18000dcc7  mov     [rax+20h], r9
0x18000dccb  push    rdi
0x18000dccc  sub     rsp, 30h
0x18000dcd0  mov     rdi, rcx
0x18000dcd3  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18000dcda  mov     qword ptr [rax+20h], 0
0x18000dce2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000dce9  jnz     short loc_18000DD11
0x18000dceb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000dcf2  jnz     short loc_18000DD11
0x18000dcf4  lea     rcx, [rax+20h]; lpCookie
0x18000dcf8  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000dcfd  test    eax, eax
0x18000dcff  jnz     short loc_18000DD11
0x18000dd01  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x18000dd06  mov     rbx, [rsp+38h+arg_0]
0x18000dd0b  add     rsp, 30h
0x18000dd0f  pop     rdi
0x18000dd10  retn
0x18000dd11  test    rbx, rbx
0x18000dd14  jnz     short loc_18000DD38
0x18000dd16  lea     rcx, aTaskdialogindi; "TaskDialogIndirect"
0x18000dd1d  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000dd22  mov     rbx, rax
0x18000dd25  test    rax, rax
0x18000dd28  jnz     short loc_18000DD31
0x18000dd2a  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x18000dd2f  jmp     short loc_18000DD4B
0x18000dd31  mov     cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA, rax; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18000dd38  xor     r9d, r9d
0x18000dd3b  xor     r8d, r8d
0x18000dd3e  xor     edx, edx
0x18000dd40  mov     rcx, rdi
0x18000dd43  mov     rax, rbx
0x18000dd46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd4b  mov     ebx, eax
0x18000dd4d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000dd54  jz      short loc_18000DD5F
0x18000dd56  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000dd5d  jnz     short loc_18000DD6C
0x18000dd5f  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000dd64  xor     ecx, ecx; dwFlags
0x18000dd66  call    cs:__imp_DeactivateActCtx
0x18000dd6c  mov     eax, ebx
0x18000dd6e  jmp     short loc_18000DD06
0x180029545  push    rbp
0x180029547  sub     rsp, 30h
0x18002954b  mov     rbp, rdx
0x18002954e  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180029555  jz      short loc_180029560
0x180029557  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002955e  jnz     short loc_18002956D
0x180029560  mov     rdx, [rbp+58h]; ulCookie
0x180029564  xor     ecx, ecx; dwFlags
0x180029566  call    cs:__imp_DeactivateActCtx
0x18002956c  nop
0x18002956d  add     rsp, 30h
0x180029571  pop     rbp
0x180029572  retn
```
