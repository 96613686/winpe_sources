# IsolationAwareTaskDialog

- ea: `0x180007bc8`
- end: `0x180007cb7`
- name: `IsolationAwareTaskDialog`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000750c`

## callees

- `0x180003e54`
- `0x180003fa8`
- `0x180006258`
- `0x180007bc8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007caa`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000af93`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007caa`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000af93`

## string_xrefs

- `0x180007c2a`: `TaskDialog`

## pseudocode

```c
__int64 __fastcall IsolationAwareTaskDialog(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, __int64, __int64); // rbx
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  ULONG_PTR ulCookie; // [rsp+78h] [rbp+20h] BYREF

  v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))`IsolationAwareTaskDialog'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
  }
  if ( !v4 )
  {
    v6 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialog");
    v4 = (__int64 (__fastcall *)(__int64, __int64, __int64))v6;
    if ( !v6 )
    {
      v7 = CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
      goto LABEL_10;
    }
    `IsolationAwareTaskDialog'::`2'::s_pfn = v6;
  }
  v7 = v4(a1, a2, 1182);
LABEL_10:
  v8 = v7;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return v8;
}

```

## disassembly

```asm
0x180007bc8  mov     rax, rsp
0x180007bcb  mov     [rax+8], rbx
0x180007bcf  mov     [rax+10h], rsi
0x180007bd3  mov     [rax+20h], r9
0x180007bd7  push    rdi
0x180007bd8  sub     rsp, 50h
0x180007bdc  mov     rdi, rdx
0x180007bdf  mov     rsi, rcx
0x180007be2  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialog@@9@4P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22H2PEAH@ZEA; long (*`IsolationAwareTaskDialog'::`2'::s_pfn)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,int,ushort const *,int *)
0x180007be9  mov     qword ptr [rax+20h], 0
0x180007bf1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007bf8  jnz     short loc_180007C25
0x180007bfa  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007c01  jnz     short loc_180007C25
0x180007c03  lea     rcx, [rax+20h]; lpCookie
0x180007c07  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180007c0c  test    eax, eax
0x180007c0e  jnz     short loc_180007C25
0x180007c10  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x180007c15  mov     rbx, [rsp+58h+arg_0]
0x180007c1a  mov     rsi, [rsp+58h+arg_8]
0x180007c1f  add     rsp, 50h
0x180007c23  pop     rdi
0x180007c24  retn
0x180007c25  test    rbx, rbx
0x180007c28  jnz     short loc_180007C4C
0x180007c2a  lea     rcx, aTaskdialog; "TaskDialog"
0x180007c31  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180007c36  mov     rbx, rax
0x180007c39  test    rax, rax
0x180007c3c  jnz     short loc_180007C45
0x180007c3e  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x180007c43  jmp     short loc_180007C8F
0x180007c45  mov     cs:?s_pfn@?1??IsolationAwareTaskDialog@@9@4P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22H2PEAH@ZEA, rax; long (*`IsolationAwareTaskDialog'::`2'::s_pfn)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,int,ushort const *,int *)
0x180007c4c  mov     rax, [rsp+58h+arg_38]
0x180007c54  mov     [rsp+58h+var_20], rax
0x180007c59  mov     [rsp+58h+var_28], 0FFFEh
0x180007c62  mov     [rsp+58h+var_30], 20h ; ' '
0x180007c6a  mov     rax, [rsp+58h+arg_20]
0x180007c72  mov     [rsp+58h+var_38], rax
0x180007c77  mov     r9d, 513h
0x180007c7d  lea     r8d, [r9-75h]
0x180007c81  mov     rdx, rdi
0x180007c84  mov     rcx, rsi
0x180007c87  mov     rax, rbx
0x180007c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8f  mov     ebx, eax
0x180007c91  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007c98  jz      short loc_180007CA3
0x180007c9a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007ca1  jnz     short loc_180007CB0
0x180007ca3  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x180007ca8  xor     ecx, ecx; dwFlags
0x180007caa  call    cs:__imp_DeactivateActCtx
0x180007cb0  mov     eax, ebx
0x180007cb2  jmp     loc_180007C15
0x18000af72  push    rbp
0x18000af74  sub     rsp, 50h
0x18000af78  mov     rbp, rdx
0x18000af7b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000af82  jz      short loc_18000AF8D
0x18000af84  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000af8b  jnz     short loc_18000AF9A
0x18000af8d  mov     rdx, [rbp+78h]; ulCookie
0x18000af91  xor     ecx, ecx; dwFlags
0x18000af93  call    cs:__imp_DeactivateActCtx
0x18000af99  nop
0x18000af9a  add     rsp, 50h
0x18000af9e  pop     rbp
0x18000af9f  retn
```
