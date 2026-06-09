# CPXWizardTask::GetHostInfo(_GUID * const,_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x18001d8c0`
- end: `0x18001da58`
- name: `?GetHostInfo@CPXWizardTask@@UEAAJQEAU_GUID@@0QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `408`
- prototype: `int(CPXWizardTask *__hidden this, struct _GUID *const, struct _GUID *const, struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18001d8c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d981`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d981`

## pseudocode

```c
__int64 __fastcall CPXWizardTask::GetHostInfo(
        CPXWizardTask *this,
        struct _GUID *const a2,
        struct _GUID *const a3,
        struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const a4)
{
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 && a3 && a4 )
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_NULL.Data4
      || *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a3->Data4 == *(_QWORD *)GUID_NULL.Data4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
          2147500035LL);
      return 2147500035LL;
    }
    *a4 = 0;
    ppv = 0;
    v7 = CoCreateInstance(a3, 0, 0x401u, &IID_IXWizardTaskEvent, &ppv);
    if ( (v7 & 0x80000000) == 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const, struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const))(*(_QWORD *)ppv + 48LL))(
             ppv,
             a2,
             a4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v7;
      v9 = 47;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v7;
      v9 = 46;
    }
    WPP_SF_d(v8[2], v9, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, v7);
    return v7;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147942487LL);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001d8c0  mov     [rsp+arg_0], rbx
0x18001d8c5  mov     [rsp+arg_10], rsi
0x18001d8ca  push    rdi
0x18001d8cb  sub     rsp, 30h
0x18001d8cf  mov     rsi, r9
0x18001d8d2  mov     rax, r8
0x18001d8d5  mov     rdi, rdx
0x18001d8d8  test    rdx, rdx
0x18001d8db  jz      loc_18001DA0F
0x18001d8e1  test    rax, rax
0x18001d8e4  jz      loc_18001DA0F
0x18001d8ea  test    r9, r9
0x18001d8ed  jz      loc_18001DA0F
0x18001d8f3  mov     rdx, qword ptr cs:GUID_NULL.Data1
0x18001d8fa  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x18001d901  cmp     [rdi], rdx
0x18001d904  jnz     short loc_18001D90C
0x18001d906  cmp     [rdi+8], rcx
0x18001d90a  jz      short loc_18001D917
0x18001d90c  cmp     [r8], rdx
0x18001d90f  jnz     short loc_18001D955
0x18001d911  cmp     [r8+8], rcx
0x18001d915  jnz     short loc_18001D955
0x18001d917  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d91e  lea     rax, WPP_GLOBAL_Control
0x18001d925  cmp     rcx, rax
0x18001d928  jz      short loc_18001D94B
0x18001d92a  test    byte ptr [rcx+1Ch], 8
0x18001d92e  jz      short loc_18001D94B
0x18001d930  mov     rcx, [rcx+10h]
0x18001d934  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001d93b  mov     edx, 2Dh ; '-'
0x18001d940  mov     r9d, 80004003h
0x18001d946  call    WPP_SF_d
0x18001d94b  mov     eax, 80004003h
0x18001d950  jmp     loc_18001DA48
0x18001d955  lea     rcx, [rsp+38h+arg_8]
0x18001d95a  mov     qword ptr [r9], 0
0x18001d961  mov     [rsp+38h+ppv], rcx; ppv
0x18001d966  lea     r9, IID_IXWizardTaskEvent; riid
0x18001d96d  mov     rcx, rax; rclsid
0x18001d970  mov     [rsp+38h+arg_8], 0
0x18001d979  xor     edx, edx; pUnkOuter
0x18001d97b  mov     r8d, 401h; dwClsContext
0x18001d981  call    cs:__imp_CoCreateInstance
0x18001d987  mov     ebx, eax
0x18001d989  test    eax, eax
0x18001d98b  jns     short loc_18001D9C5
0x18001d98d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d994  lea     rax, WPP_GLOBAL_Control
0x18001d99b  cmp     rcx, rax
0x18001d99e  jz      short loc_18001D9BE
0x18001d9a0  test    byte ptr [rcx+1Ch], 10h
0x18001d9a4  jz      short loc_18001D9BE
0x18001d9a6  mov     edx, 2Eh ; '.'
0x18001d9ab  mov     rcx, [rcx+10h]
0x18001d9af  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001d9b6  mov     r9d, ebx
0x18001d9b9  call    WPP_SF_d
0x18001d9be  mov     eax, ebx
0x18001d9c0  jmp     loc_18001DA48
0x18001d9c5  mov     rcx, [rsp+38h+arg_8]
0x18001d9ca  mov     r8, rsi
0x18001d9cd  mov     rdx, rdi
0x18001d9d0  mov     rax, [rcx]
0x18001d9d3  mov     rax, [rax+30h]
0x18001d9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9dc  mov     rcx, [rsp+38h+arg_8]
0x18001d9e1  mov     ebx, eax
0x18001d9e3  mov     rdx, [rcx]
0x18001d9e6  mov     rax, [rdx+10h]
0x18001d9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9f6  lea     rax, WPP_GLOBAL_Control
0x18001d9fd  cmp     rcx, rax
0x18001da00  jz      short loc_18001D9BE
0x18001da02  test    byte ptr [rcx+1Ch], 10h
0x18001da06  jz      short loc_18001D9BE
0x18001da08  mov     edx, 2Fh ; '/'
0x18001da0d  jmp     short loc_18001D9AB
0x18001da0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da16  lea     rax, WPP_GLOBAL_Control
0x18001da1d  cmp     rcx, rax
0x18001da20  jz      short loc_18001DA43
0x18001da22  test    byte ptr [rcx+1Ch], 8
0x18001da26  jz      short loc_18001DA43
0x18001da28  mov     rcx, [rcx+10h]
0x18001da2c  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001da33  mov     edx, 2Ch ; ','
0x18001da38  mov     r9d, 80070057h
0x18001da3e  call    WPP_SF_d
0x18001da43  mov     eax, 80070057h
0x18001da48  mov     rbx, [rsp+38h+arg_0]
0x18001da4d  mov     rsi, [rsp+38h+arg_10]
0x18001da52  add     rsp, 30h
0x18001da56  pop     rdi
0x18001da57  retn
```
