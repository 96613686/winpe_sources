# CXWizardTaskUIBaseClass<1570,CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,0,10615,3304,3309,3308,0>::CanHostTask(_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x180004ca4`
- end: `0x180004d20`
- name: `?CanHostTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskConnectToAp@@$1?CLSID_WcnTaskConnectToAnAccessPoint@@3U_GUID@@B$0A@$0CJHH@$0MOI@$0MON@$0MOM@$0A@@@UEAAJQEAU_GUID@@QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004bf0`

## callees

- `0x180002294`
- `0x180004ca4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004cbd`

## pseudocode

```c
__int64 __fastcall CXWizardTaskUIBaseClass<1570,CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,0,10615,3304,3309,3308,0>::CanHostTask(
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
  *((_QWORD *)v5 + 5) = 10615;
  *((_QWORD *)v5 + 6) = 3309;
  *((_QWORD *)v5 + 7) = 3308;
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x180004ca4  mov     [rsp+arg_0], rbx
0x180004ca9  push    rdi
0x180004caa  sub     rsp, 20h
0x180004cae  mov     ecx, 40h ; '@'; cb
0x180004cb3  mov     qword ptr [r8], 0
0x180004cba  mov     rdi, r8
0x180004cbd  call    cs:__imp_CoTaskMemAlloc
0x180004cc3  mov     rbx, rax
0x180004cc6  test    rax, rax
0x180004cc9  jz      short loc_180004D10
0x180004ccb  xor     edx, edx; Val
0x180004ccd  mov     rcx, rax; void *
0x180004cd0  lea     r8d, [rdx+40h]; Size
0x180004cd4  call    memset_0
0x180004cd9  mov     dword ptr [rbx], 40h ; '@'
0x180004cdf  xor     eax, eax
0x180004ce1  mov     dword ptr [rbx+4], 3
0x180004ce8  mov     rcx, cs:hModule
0x180004cef  mov     [rbx+20h], rcx
0x180004cf3  mov     qword ptr [rbx+28h], 2977h
0x180004cfb  mov     qword ptr [rbx+30h], 0CEDh
0x180004d03  mov     qword ptr [rbx+38h], 0CECh
0x180004d0b  mov     [rdi], rbx
0x180004d0e  jmp     short loc_180004D15
0x180004d10  mov     eax, 8007000Eh
0x180004d15  mov     rbx, [rsp+28h+arg_0]
0x180004d1a  add     rsp, 20h
0x180004d1e  pop     rdi
0x180004d1f  retn
```
