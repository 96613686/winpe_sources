# IsolationAwareTaskDialog

- ea: `0x18000dbd0`
- end: `0x18000dcba`
- name: `IsolationAwareTaskDialog`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c220`
- `0x18000c500`

## callees

- `0x180009a60`
- `0x18000d8dc`
- `0x18000d908`
- `0x18000dbd0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18000dcad`
- `KERNEL32!DeactivateActCtx` at `0x180029531`
- `KERNEL32!DeactivateActCtx` at `0x18000dcad`
- `KERNEL32!DeactivateActCtx` at `0x180029531`

## string_xrefs

- `0x18000dc2f`: `TaskDialog`

## pseudocode

```c
__int64 __fastcall IsolationAwareTaskDialog(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  HINSTANCE v7; // r14
  __int64 (__fastcall *v8)(__int64, HINSTANCE, __int64, __int64, __int64, int, __int64, _QWORD); // rbx
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  ULONG_PTR ulCookie; // [rsp+90h] [rbp+18h] BYREF

  v7 = g_hInst;
  v8 = (__int64 (__fastcall *)(__int64, HINSTANCE, __int64, __int64, __int64, int, __int64, _QWORD))`IsolationAwareTaskDialog'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
  }
  if ( !v8 )
  {
    v10 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialog");
    v8 = (__int64 (__fastcall *)(__int64, HINSTANCE, __int64, __int64, __int64, int, __int64, _QWORD))v10;
    if ( !v10 )
    {
      v11 = CommctrlIsolationAwarePrivateJVaQPGbueRfhYg();
      goto LABEL_10;
    }
    `IsolationAwareTaskDialog'::`2'::s_pfn = v10;
  }
  v11 = v8(a1, v7, 51, a4, a5, 1, 65534, 0);
LABEL_10:
  v12 = v11;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return v12;
}

```

## disassembly

```asm
0x18000dbd0  mov     rax, rsp
0x18000dbd3  mov     [rax+18h], r8
0x18000dbd7  push    rbx
0x18000dbd8  push    rsi
0x18000dbd9  push    rdi
0x18000dbda  push    r14
0x18000dbdc  sub     rsp, 58h
0x18000dbe0  mov     rdi, r9
0x18000dbe3  mov     rsi, rcx
0x18000dbe6  mov     r14, cs:g_hInst
0x18000dbed  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialog@@9@4P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22H2PEAH@ZEA; long (*`IsolationAwareTaskDialog'::`2'::s_pfn)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,int,ushort const *,int *)
0x18000dbf4  mov     qword ptr [rax+18h], 0
0x18000dbfc  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000dc03  jnz     short loc_18000DC2A
0x18000dc05  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000dc0c  jnz     short loc_18000DC2A
0x18000dc0e  lea     rcx, [rax+18h]; lpCookie
0x18000dc12  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000dc17  test    eax, eax
0x18000dc19  jnz     short loc_18000DC2A
0x18000dc1b  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x18000dc20  add     rsp, 58h
0x18000dc24  pop     r14
0x18000dc26  pop     rdi
0x18000dc27  pop     rsi
0x18000dc28  pop     rbx
0x18000dc29  retn
0x18000dc2a  test    rbx, rbx
0x18000dc2d  jnz     short loc_18000DC51
0x18000dc2f  lea     rcx, aTaskdialog; "TaskDialog"
0x18000dc36  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000dc3b  mov     rbx, rax
0x18000dc3e  test    rax, rax
0x18000dc41  jnz     short loc_18000DC4A
0x18000dc43  call    CommctrlIsolationAwarePrivateJVaQPGbueRfhYg
0x18000dc48  jmp     short loc_18000DC8F
0x18000dc4a  mov     cs:?s_pfn@?1??IsolationAwareTaskDialog@@9@4P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22H2PEAH@ZEA, rax; long (*`IsolationAwareTaskDialog'::`2'::s_pfn)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,int,ushort const *,int *)
0x18000dc51  mov     [rsp+78h+var_40], 0
0x18000dc5a  mov     [rsp+78h+var_48], 0FFFEh
0x18000dc63  mov     [rsp+78h+var_50], 1
0x18000dc6b  mov     rax, [rsp+78h+arg_20]
0x18000dc73  mov     [rsp+78h+var_58], rax
0x18000dc78  mov     r9, rdi
0x18000dc7b  mov     r8d, 33h ; '3'
0x18000dc81  mov     rdx, r14
0x18000dc84  mov     rcx, rsi
0x18000dc87  mov     rax, rbx
0x18000dc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc8f  mov     ebx, eax
0x18000dc91  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000dc98  jz      short loc_18000DCA3
0x18000dc9a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000dca1  jnz     short loc_18000DCB3
0x18000dca3  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x18000dcab  xor     ecx, ecx; dwFlags
0x18000dcad  call    cs:__imp_DeactivateActCtx
0x18000dcb3  mov     eax, ebx
0x18000dcb5  jmp     loc_18000DC20
0x18002950d  push    rbp
0x18002950f  sub     rsp, 50h
0x180029513  mov     rbp, rdx
0x180029516  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002951d  jz      short loc_180029528
0x18002951f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180029526  jnz     short loc_180029538
0x180029528  mov     rdx, [rbp+90h]; ulCookie
0x18002952f  xor     ecx, ecx; dwFlags
0x180029531  call    cs:__imp_DeactivateActCtx
0x180029537  nop
0x180029538  add     rsp, 50h
0x18002953c  pop     rbp
0x18002953d  retn
```
