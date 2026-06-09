# CPXWizardTask::HrEnsureRegistryInfoModuleLoaded(void)

- ea: `0x18001e0b8`
- end: `0x18001e173`
- name: `?HrEnsureRegistryInfoModuleLoaded@CPXWizardTask@@AEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CPXWizardTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001da60`
- `0x18001e180`

## callees

- `0x18000ae04`
- `0x18001e0b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e0f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e0f3`

## pseudocode

```c
__int64 __fastcall CPXWizardTask::HrEnsureRegistryInfoModuleLoaded(CPXWizardTask *this)
{
  _QWORD *v1; // rbx
  HRESULT Instance; // eax
  unsigned int v4; // edi
  PVOID *v5; // rcx

  v1 = (_QWORD *)((char *)this + 96);
  if ( *((_QWORD *)this + 12) )
    return 0;
  Instance = CoCreateInstance(&CLSID_CPXWizardRegistryInfo, 0, 0x401u, &IID_IPXWizardRegistryInfo, (LPVOID *)this + 12);
  v4 = Instance;
  if ( Instance >= 0 )
    goto LABEL_7;
  *v1 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_8;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
      (unsigned int)Instance);
LABEL_7:
    v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_8:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
      WPP_SF_d(v5[2], 11, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18001e0b8  mov     [rsp+arg_0], rbx
0x18001e0bd  mov     [rsp+arg_8], rsi
0x18001e0c2  push    rdi
0x18001e0c3  sub     rsp, 30h
0x18001e0c7  lea     rbx, [rcx+60h]
0x18001e0cb  cmp     qword ptr [rbx], 0
0x18001e0cf  jz      short loc_18001E0D8
0x18001e0d1  xor     eax, eax
0x18001e0d3  jmp     loc_18001E163
0x18001e0d8  lea     r9, IID_IPXWizardRegistryInfo; riid
0x18001e0df  mov     [rsp+38h+ppv], rbx; ppv
0x18001e0e4  xor     edx, edx; pUnkOuter
0x18001e0e6  lea     rcx, CLSID_CPXWizardRegistryInfo; rclsid
0x18001e0ed  mov     r8d, 401h; dwClsContext
0x18001e0f3  call    cs:__imp_CoCreateInstance
0x18001e0f9  lea     rsi, WPP_GLOBAL_Control
0x18001e100  mov     edi, eax
0x18001e102  test    eax, eax
0x18001e104  jns     short loc_18001E137
0x18001e106  mov     qword ptr [rbx], 0
0x18001e10d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e114  cmp     rcx, rsi
0x18001e117  jz      short loc_18001E161
0x18001e119  test    byte ptr [rcx+1Ch], 4
0x18001e11d  jz      short loc_18001E13E
0x18001e11f  mov     rcx, [rcx+10h]
0x18001e123  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e12a  mov     edx, 0Ah
0x18001e12f  mov     r9d, eax
0x18001e132  call    WPP_SF_d
0x18001e137  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e13e  cmp     rcx, rsi
0x18001e141  jz      short loc_18001E161
0x18001e143  test    byte ptr [rcx+1Ch], 10h
0x18001e147  jz      short loc_18001E161
0x18001e149  mov     rcx, [rcx+10h]
0x18001e14d  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e154  mov     edx, 0Bh
0x18001e159  mov     r9d, edi
0x18001e15c  call    WPP_SF_d
0x18001e161  mov     eax, edi
0x18001e163  mov     rbx, [rsp+38h+arg_0]
0x18001e168  mov     rsi, [rsp+38h+arg_8]
0x18001e16d  add     rsp, 30h
0x18001e171  pop     rdi
0x18001e172  retn
```
