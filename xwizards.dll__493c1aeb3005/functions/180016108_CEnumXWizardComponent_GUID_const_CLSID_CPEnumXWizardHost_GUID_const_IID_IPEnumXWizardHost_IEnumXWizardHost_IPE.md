# CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardHost,&_GUID const IID_IPEnumXWizardHost,IEnumXWizardHost,IPEnumXWizardHost>::CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardHost,&_GUID const IID_IPEnumXWizardHost,IEnumXWizardHost,IPEnumXWizardHost>(void)

- ea: `0x180016108`
- end: `0x180016179`
- name: `??0?$CEnumXWizardComponent@$1?CLSID_CPEnumXWizardHost@@3U_GUID@@B$1?IID_IPEnumXWizardHost@@3U2@BUIEnumXWizardHost@@UIPEnumXWizardHost@@@@QEAA@XZ`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016bac`

## callees

- `0x180016108`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001615a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001615a`

## pseudocode

```c
__int64 __fastcall CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardHost,&_GUID const IID_IPEnumXWizardHost,IEnumXWizardHost,IPEnumXWizardHost>::CEnumXWizardComponent<&_GUID const CLSID_CPEnumXWizardHost,&_GUID const IID_IPEnumXWizardHost,IEnumXWizardHost,IPEnumXWizardHost>(
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
  if ( CoCreateInstance(&CLSID_CPEnumXWizardHost, 0, 0x401u, &IID_IPEnumXWizardHost, (LPVOID *)(a1 + 96)) < 0 )
    *v1 = 0;
  return a1;
}

```

## disassembly

```asm
0x180016108  mov     [rsp+arg_0], rbx
0x18001610d  push    rdi
0x18001610e  sub     rsp, 30h
0x180016112  mov     dword ptr [rcx+8], 0
0x180016119  lea     rdi, [rcx+60h]
0x18001611d  xor     eax, eax
0x18001611f  mov     [rsp+38h+ppv], rdi; ppv
0x180016124  xorps   xmm0, xmm0
0x180016127  lea     r9, IID_IPEnumXWizardHost; riid
0x18001612e  movups  xmmword ptr [rcx+10h], xmm0
0x180016132  mov     rbx, rcx
0x180016135  xor     edx, edx; pUnkOuter
0x180016137  movups  xmmword ptr [rcx+20h], xmm0
0x18001613b  mov     [rcx+30h], rax
0x18001613f  mov     r8d, 401h; dwClsContext
0x180016145  mov     [rcx+38h], al
0x180016148  movups  xmmword ptr [rcx+40h], xmm0
0x18001614c  mov     [rcx+50h], rax
0x180016150  mov     [rcx+58h], eax
0x180016153  lea     rcx, CLSID_CPEnumXWizardHost; rclsid
0x18001615a  call    cs:__imp_CoCreateInstance
0x180016160  test    eax, eax
0x180016162  jns     short loc_18001616B
0x180016164  mov     qword ptr [rdi], 0
0x18001616b  mov     rax, rbx
0x18001616e  mov     rbx, [rsp+38h+arg_0]
0x180016173  add     rsp, 30h
0x180016177  pop     rdi
0x180016178  retn
```
