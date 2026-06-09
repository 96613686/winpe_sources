# CPXWizardFactoryRegistration::UnregisterTask(_GUID const *)

- ea: `0x1800076b0`
- end: `0x18000771c`
- name: `?UnregisterTask@CPXWizardFactoryRegistration@@UEAAJPEBU_GUID@@@Z`
- size: `108`
- prototype: `int(CPXWizardFactoryRegistration *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800076b0`
- `0x180007820`
- `0x18000c240`

## pseudocode

```c
__int64 __fastcall CPXWizardFactoryRegistration::UnregisterTask(CPXWizardFactoryRegistration *this, struct _GUID *a2)
{
  __int64 v2; // rax
  unsigned int v3; // ebx

  if ( a2 )
  {
    v2 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v2 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( !v2 )
      a2 = 0;
  }
  v3 = HrUnregisterWizardFactoryComponent(a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800076b0  push    rbx
0x1800076b2  sub     rsp, 20h
0x1800076b6  test    rdx, rdx
0x1800076b9  jz      short loc_1800076D9
0x1800076bb  mov     rax, [rdx]
0x1800076be  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800076c5  jnz     short loc_1800076D2
0x1800076c7  mov     rax, [rdx+8]
0x1800076cb  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800076d2  test    rax, rax
0x1800076d5  jnz     short loc_1800076D9
0x1800076d7  xor     edx, edx
0x1800076d9  mov     rcx, rdx; rguid
0x1800076dc  call    ?HrUnregisterWizardFactoryComponent@@YAJPEBU_GUID@@@Z; HrUnregisterWizardFactoryComponent(_GUID const *)
0x1800076e1  mov     ebx, eax
0x1800076e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076ea  lea     rax, WPP_GLOBAL_Control
0x1800076f1  cmp     rcx, rax
0x1800076f4  jz      short loc_180007714
0x1800076f6  test    byte ptr [rcx+1Ch], 10h
0x1800076fa  jz      short loc_180007714
0x1800076fc  mov     rcx, [rcx+10h]
0x180007700  lea     r8, WPP_20901bc7607430ca4b9b3565b6281836_Traceguids
0x180007707  mov     edx, 17h
0x18000770c  mov     r9d, ebx
0x18000770f  call    WPP_SF_D
0x180007714  mov     eax, ebx
0x180007716  add     rsp, 20h
0x18000771a  pop     rbx
0x18000771b  retn
```
