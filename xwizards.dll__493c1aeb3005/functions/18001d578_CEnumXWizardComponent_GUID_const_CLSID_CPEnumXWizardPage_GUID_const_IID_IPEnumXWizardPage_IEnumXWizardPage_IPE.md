# CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardPage,&_GUID const IID_IPEnumXWizardPage,IEnumXWizardPage,IPEnumXWizardPage>::CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardPage,&_GUID const IID_IPEnumXWizardPage,IEnumXWizardPage,IPEnumXWizardPage>(void)

- ea: `0x18001d578`
- end: `0x18001d5e9`
- name: `??0?$CEnumXWizardComponent@$1?CLSID_CPEnumXWizardPage@@3U_GUID@@B$1?IID_IPEnumXWizardPage@@3U2@BUIEnumXWizardPage@@UIPEnumXWizardPage@@@@QEAA@XZ`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ddc4`

## callees

- `0x18001d578`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d5ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d5ca`

## pseudocode

```c
__int64 __fastcall CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardPage,&_GUID const IID_IPEnumXWizardPage,IEnumXWizardPage,IPEnumXWizardPage>::CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardPage,&_GUID const IID_IPEnumXWizardPage,IEnumXWizardPage,IPEnumXWizardPage>(
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
  if ( CoCreateInstance(&CLSID_CPEnumXWizardPage, 0, 0x401u, &IID_IPEnumXWizardPage, (LPVOID *)(a1 + 96)) < 0 )
    *v1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18001d578  mov     [rsp+arg_0], rbx
0x18001d57d  push    rdi
0x18001d57e  sub     rsp, 30h
0x18001d582  mov     dword ptr [rcx+8], 0
0x18001d589  lea     rdi, [rcx+60h]
0x18001d58d  xor     eax, eax
0x18001d58f  mov     [rsp+38h+ppv], rdi; ppv
0x18001d594  xorps   xmm0, xmm0
0x18001d597  lea     r9, IID_IPEnumXWizardPage; riid
0x18001d59e  movups  xmmword ptr [rcx+10h], xmm0
0x18001d5a2  mov     rbx, rcx
0x18001d5a5  xor     edx, edx; pUnkOuter
0x18001d5a7  movups  xmmword ptr [rcx+20h], xmm0
0x18001d5ab  mov     [rcx+30h], rax
0x18001d5af  mov     r8d, 401h; dwClsContext
0x18001d5b5  mov     [rcx+38h], al
0x18001d5b8  movups  xmmword ptr [rcx+40h], xmm0
0x18001d5bc  mov     [rcx+50h], rax
0x18001d5c0  mov     [rcx+58h], eax
0x18001d5c3  lea     rcx, CLSID_CPEnumXWizardPage; rclsid
0x18001d5ca  call    cs:__imp_CoCreateInstance
0x18001d5d0  test    eax, eax
0x18001d5d2  jns     short loc_18001D5DB
0x18001d5d4  mov     qword ptr [rdi], 0
0x18001d5db  mov     rax, rbx
0x18001d5de  mov     rbx, [rsp+38h+arg_0]
0x18001d5e3  add     rsp, 30h
0x18001d5e7  pop     rdi
0x18001d5e8  retn
```
