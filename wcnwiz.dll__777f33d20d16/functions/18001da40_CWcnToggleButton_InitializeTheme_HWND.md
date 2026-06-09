# CWcnToggleButton::InitializeTheme(HWND__ *)

- ea: `0x18001da40`
- end: `0x18001da97`
- name: `?InitializeTheme@CWcnToggleButton@@AEAAXPEAUHWND__@@@Z`
- size: `87`
- prototype: `void __fastcall(CWcnToggleButton *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001d818`
- `0x18001dc88`

## callees

- `0x18001d74c`
- `0x18001da40`

## import_xrefs

- `UxTheme!IsAppThemed` at `0x18001da65`
- `UxTheme!IsAppThemed` at `0x18001da65`
- `UxTheme!CloseThemeData` at `0x18001da58`
- `UxTheme!CloseThemeData` at `0x18001da58`
- `UxTheme!OpenThemeData` at `0x18001da79`
- `UxTheme!OpenThemeData` at `0x18001da79`

## string_xrefs

- `0x18001da6f`: `TaskDialog`

## pseudocode

```c
void __fastcall CWcnToggleButton::InitializeTheme(CWcnToggleButton *this, HWND a2)
{
  void *v4; // rcx

  v4 = *(void **)this;
  if ( v4 )
  {
    CloseThemeData(v4);
    *(_QWORD *)this = 0;
  }
  if ( IsAppThemed() )
    *(_QWORD *)this = OpenThemeData(a2, L"TaskDialog");
  CWcnToggleButton::CalculateState(this, a2);
}

```

## disassembly

```asm
0x18001da40  mov     [rsp+arg_0], rbx
0x18001da45  push    rdi
0x18001da46  sub     rsp, 20h
0x18001da4a  mov     rbx, rcx
0x18001da4d  mov     rdi, rdx
0x18001da50  mov     rcx, [rcx]; hTheme
0x18001da53  test    rcx, rcx
0x18001da56  jz      short loc_18001DA65
0x18001da58  call    cs:__imp_CloseThemeData
0x18001da5e  mov     qword ptr [rbx], 0
0x18001da65  call    cs:__imp_IsAppThemed
0x18001da6b  test    eax, eax
0x18001da6d  jz      short loc_18001DA82
0x18001da6f  lea     rdx, pszClassList; "TaskDialog"
0x18001da76  mov     rcx, rdi; hwnd
0x18001da79  call    cs:__imp_OpenThemeData
0x18001da7f  mov     [rbx], rax
0x18001da82  mov     rdx, rdi; HWND
0x18001da85  mov     rcx, rbx; this
0x18001da88  mov     rbx, [rsp+28h+arg_0]
0x18001da8d  add     rsp, 20h
0x18001da91  pop     rdi
0x18001da92  jmp     ?CalculateState@CWcnToggleButton@@AEAAXPEAUHWND__@@@Z; CWcnToggleButton::CalculateState(HWND__ *)
```
