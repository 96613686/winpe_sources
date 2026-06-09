# CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardTask,&_GUID const IID_IPEnumXWizardTask,IEnumXWizardTask,IPEnumXWizardTask>::CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardTask,&_GUID const IID_IPEnumXWizardTask,IEnumXWizardTask,IPEnumXWizardTask>(void)

- ea: `0x18001c598`
- end: `0x18001c609`
- name: `??0?$CEnumXWizardComponent@$1?CLSID_CPEnumXWizardTask@@3U_GUID@@B$1?IID_IPEnumXWizardTask@@3U2@BUIEnumXWizardTask@@UIPEnumXWizardTask@@@@QEAA@XZ`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c814`

## callees

- `0x18001c598`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c5ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c5ea`

## pseudocode

```c
__int64 __fastcall CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardTask,&_GUID const IID_IPEnumXWizardTask,IEnumXWizardTask,IPEnumXWizardTask>::CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardTask,&_GUID const IID_IPEnumXWizardTask,IEnumXWizardTask,IPEnumXWizardTask>(
        __int64 a1)
{
  _QWORD *v1; // rdi

  *(_DWORD *)(a1 + 8) = 0;
  v1 = (_QWORD *)(a1 + 96);
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 88) = 0;
  if ( CoCreateInstance(&CLSID_CPEnumXWizardTask, 0, 0x401u, &IID_IPEnumXWizardTask, (LPVOID *)(a1 + 96)) < 0 )
    *v1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18001c598  mov     [rsp+arg_0], rbx
0x18001c59d  push    rdi
0x18001c59e  sub     rsp, 30h
0x18001c5a2  mov     dword ptr [rcx+8], 0
0x18001c5a9  lea     rdi, [rcx+60h]
0x18001c5ad  xor     eax, eax
0x18001c5af  mov     [rsp+38h+ppv], rdi; ppv
0x18001c5b4  xorps   xmm0, xmm0
0x18001c5b7  lea     r9, IID_IPEnumXWizardTask; riid
0x18001c5be  movups  xmmword ptr [rcx+10h], xmm0
0x18001c5c2  mov     rbx, rcx
0x18001c5c5  xor     edx, edx; pUnkOuter
0x18001c5c7  movups  xmmword ptr [rcx+20h], xmm0
0x18001c5cb  mov     [rcx+30h], rax
0x18001c5cf  mov     r8d, 401h; dwClsContext
0x18001c5d5  mov     [rcx+38h], al
0x18001c5d8  movups  xmmword ptr [rcx+40h], xmm0
0x18001c5dc  mov     [rcx+50h], rax
0x18001c5e0  mov     [rcx+58h], eax
0x18001c5e3  lea     rcx, CLSID_CPEnumXWizardTask; rclsid
0x18001c5ea  call    cs:__imp_CoCreateInstance
0x18001c5f0  test    eax, eax
0x18001c5f2  jns     short loc_18001C5FB
0x18001c5f4  mov     qword ptr [rdi], 0
0x18001c5fb  mov     rax, rbx
0x18001c5fe  mov     rbx, [rsp+38h+arg_0]
0x18001c603  add     rsp, 30h
0x18001c607  pop     rdi
0x18001c608  retn
```
