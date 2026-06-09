# CXWizardTaskUIBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,0,3303,0,0>::CanHostTask(_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x180004c30`
- end: `0x180004c9c`
- name: `?CanHostTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@$0A@$0A@$0MOH@$0A@$0A@@@UEAAJQEAU_GUID@@QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180004bb0`

## callees

- `0x180002294`
- `0x180004c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004c49`

## pseudocode

```c
__int64 __fastcall CXWizardTaskUIBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,0,3303,0,0>::CanHostTask(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 result; // rax

  *a3 = 0;
  v4 = CoTaskMemAlloc(0x40u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  memset_0(v4, 0, 0x40u);
  *v5 = 64;
  result = 0;
  v5[1] = 3;
  *((_QWORD *)v5 + 4) = hModule;
  *((_QWORD *)v5 + 6) = 3303;
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x180004c30  mov     [rsp+arg_0], rbx
0x180004c35  push    rdi
0x180004c36  sub     rsp, 20h
0x180004c3a  mov     ecx, 40h ; '@'; cb
0x180004c3f  mov     qword ptr [r8], 0
0x180004c46  mov     rdi, r8
0x180004c49  call    cs:__imp_CoTaskMemAlloc
0x180004c4f  mov     rbx, rax
0x180004c52  test    rax, rax
0x180004c55  jz      short loc_180004C8C
0x180004c57  xor     edx, edx; Val
0x180004c59  mov     rcx, rax; void *
0x180004c5c  lea     r8d, [rdx+40h]; Size
0x180004c60  call    memset_0
0x180004c65  mov     dword ptr [rbx], 40h ; '@'
0x180004c6b  xor     eax, eax
0x180004c6d  mov     dword ptr [rbx+4], 3
0x180004c74  mov     rcx, cs:hModule
0x180004c7b  mov     [rbx+20h], rcx
0x180004c7f  mov     qword ptr [rbx+30h], 0CE7h
0x180004c87  mov     [rdi], rbx
0x180004c8a  jmp     short loc_180004C91
0x180004c8c  mov     eax, 8007000Eh
0x180004c91  mov     rbx, [rsp+28h+arg_0]
0x180004c96  add     rsp, 20h
0x180004c9a  pop     rdi
0x180004c9b  retn
```
