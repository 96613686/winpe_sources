# CWSHExtension::DoPropertySheet(void)

- ea: `0x180006130`
- end: `0x18000614b`
- name: `?DoPropertySheet@CWSHExtension@@UEAAJXZ`
- size: `27`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006130`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWSHExtension::DoPropertySheet(CWSHExtension *this)
{
  __int64 v1; // rax
  __int64 (*v2)(void); // rax

  v1 = *(_QWORD *)this;
  if ( Global::g_fWindowsNT )
    v2 = *(__int64 (**)(void))(v1 + 40);
  else
    v2 = *(__int64 (**)(void))(v1 + 48);
  return v2();
}

```

## disassembly

```asm
0x180006130  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x180006137  mov     rax, [rcx]
0x18000613a  jz      short loc_180006142
0x18000613c  mov     rax, [rax+28h]
0x180006140  jmp     short loc_180006146
0x180006142  mov     rax, [rax+30h]
0x180006146  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
