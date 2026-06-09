# AccessibilityDialog::SetupLightDismissLayer(void)

- ea: `0x14002284c`
- end: `0x140022927`
- name: `?SetupLightDismissLayer@AccessibilityDialog@@AEAAXXZ`
- size: `219`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400212ec`

## callees

- `0x14000f774`
- `0x14002284c`
- `0x140029010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140022895`
- `ole32!CoCreateInstance` at `0x140022895`

## string_xrefs

- `0x1400228ad`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`
- `0x14002290a`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AccessibilityDialog::SetupLightDismissLayer(AccessibilityDialog *this)
{
  LPVOID *v2; // rbx
  __int64 v3; // rcx
  HRESULT Instance; // eax
  LPVOID v5; // rcx
  int v6; // eax
  int ppv; // [rsp+20h] [rbp-28h]
  _QWORD v8[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = (LPVOID *)((char *)this + 312);
  v3 = *((_QWORD *)this + 39);
  *v2 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  Instance = CoCreateInstance(&CLSID_SimpleLightDismissProvider, 0, 1u, &GUID_b849acb5_8ac5_4fb8_88b6_55c749d25a44, v2);
  if ( Instance < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x200,
      (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v5 = *v2;
  if ( *v2 )
  {
    v8[0] = 3;
    v8[1] = *((_QWORD *)this + 5);
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, AccessibilityDialog *, char *))(*(_QWORD *)v5 + 24LL))(
           v5,
           v8,
           this,
           (char *)this + 304);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
        (const char *)(unsigned int)v6,
        ppv);
  }
}

```

## disassembly

```asm
0x14002284c  mov     [rsp+arg_0], rbx
0x140022851  push    rdi
0x140022852  sub     rsp, 40h
0x140022856  mov     rdi, rcx
0x140022859  lea     rbx, [rcx+138h]
0x140022860  mov     rcx, [rbx]
0x140022863  mov     qword ptr [rbx], 0
0x14002286a  test    rcx, rcx
0x14002286d  jz      short loc_14002287C
0x14002286f  mov     rax, [rcx]
0x140022872  mov     rax, [rax+10h]
0x140022876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002287b  nop
0x14002287c  mov     qword ptr [rsp+48h+ppv], rbx; int
0x140022881  lea     r9, _GUID_b849acb5_8ac5_4fb8_88b6_55c749d25a44; riid
0x140022888  xor     edx, edx; pUnkOuter
0x14002288a  lea     r8d, [rdx+1]; dwClsContext
0x14002288e  lea     rcx, CLSID_SimpleLightDismissProvider; rclsid
0x140022895  call    cs:__imp_CoCreateInstance
0x14002289c  nop     dword ptr [rax+rax+00h]
0x1400228a1  test    eax, eax
0x1400228a3  jns     short loc_1400228BE
0x1400228a5  mov     rcx, [rsp+48h]; this
0x1400228aa  mov     r9d, eax; char *
0x1400228ad  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x1400228b4  mov     edx, 200h; void *
0x1400228b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400228be  mov     rcx, [rbx]
0x1400228c1  test    rcx, rcx
0x1400228c4  jz      short loc_14002291B
0x1400228c6  mov     [rsp+48h+var_18], 3
0x1400228cf  mov     rax, [rdi+28h]
0x1400228d3  mov     [rsp+48h+var_18+8], rax
0x1400228d8  movaps  xmm0, xmmword ptr [rsp+48h+var_18]
0x1400228dd  movdqa  xmmword ptr [rsp+48h+var_18], xmm0
0x1400228e3  mov     rax, [rcx]
0x1400228e6  lea     r9, [rdi+130h]
0x1400228ed  mov     r8, rdi
0x1400228f0  lea     rdx, [rsp+48h+var_18]
0x1400228f5  mov     rax, [rax+18h]
0x1400228f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400228fe  test    eax, eax
0x140022900  jns     short loc_14002291B
0x140022902  mov     rcx, [rsp+48h]; this
0x140022907  mov     r9d, eax; char *
0x14002290a  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140022911  mov     edx, 204h; void *
0x140022916  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14002291b  mov     rbx, [rsp+48h+arg_0]
0x140022920  add     rsp, 40h
0x140022924  pop     rdi
0x140022925  retn
```
