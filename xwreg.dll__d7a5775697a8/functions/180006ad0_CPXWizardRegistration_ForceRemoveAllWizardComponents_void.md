# CPXWizardRegistration::ForceRemoveAllWizardComponents(void)

- ea: `0x180006ad0`
- end: `0x180006b16`
- name: `?ForceRemoveAllWizardComponents@CPXWizardRegistration@@UEAAJXZ`
- size: `70`
- prototype: `__int64 __fastcall(CPXWizardRegistration *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006ad0`
- `0x180007820`
- `0x18000dd3c`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistration::ForceRemoveAllWizardComponents(CPXWizardRegistration *this)
{
  unsigned int v1; // ebx

  v1 = HrForcefullyRemoveAllWizardComponents();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180006ad0  push    rbx
0x180006ad2  sub     rsp, 20h
0x180006ad6  call    ?HrForcefullyRemoveAllWizardComponents@@YAJXZ; HrForcefullyRemoveAllWizardComponents(void)
0x180006adb  mov     ebx, eax
0x180006add  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ae4  lea     rax, WPP_GLOBAL_Control
0x180006aeb  cmp     rcx, rax
0x180006aee  jz      short loc_180006B0E
0x180006af0  test    byte ptr [rcx+1Ch], 10h
0x180006af4  jz      short loc_180006B0E
0x180006af6  mov     rcx, [rcx+10h]
0x180006afa  lea     r8, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids
0x180006b01  mov     edx, 12h
0x180006b06  mov     r9d, ebx
0x180006b09  call    WPP_SF_D
0x180006b0e  mov     eax, ebx
0x180006b10  add     rsp, 20h
0x180006b14  pop     rbx
0x180006b15  retn
```
