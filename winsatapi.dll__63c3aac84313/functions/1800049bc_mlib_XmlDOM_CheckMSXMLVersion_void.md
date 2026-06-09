# mlib::XmlDOM::CheckMSXMLVersion(void)

- ea: `0x1800049bc`
- end: `0x180004a40`
- name: `?CheckMSXMLVersion@XmlDOM@mlib@@SA_NXZ`
- size: `132`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003230`
- `0x180003548`
- `0x180006580`

## callees

- `0x1800049bc`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800049f1`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800049f1`

## pseudocode

```c
bool mlib::XmlDOM::CheckMSXMLVersion(void)
{
  HRESULT ClassObject; // ebx
  bool v1; // bl
  LPVOID v3; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  ClassObject = CoGetClassObject(
                  &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
                  1u,
                  0,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  &v3);
  if ( ClassObject >= 0 )
  {
    mlib::XmlDOM::clsIDDocument = GUID_88d96a05_f192_11d4_a65f_0040963251e5;
    mlib::XmlDOM::clsIDSchema = GUID_88d96a07_f192_11d4_a65f_0040963251e5;
  }
  v1 = ClassObject >= 0;
  if ( v3 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
  return v1;
}

```

## disassembly

```asm
0x1800049bc  mov     r11, rsp
0x1800049bf  push    rbx
0x1800049c0  sub     rsp, 40h
0x1800049c4  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFEh
0x1800049cc  mov     qword ptr [r11+8], 0
0x1800049d4  lea     rax, [r11+8]
0x1800049d8  mov     [r11-28h], rax
0x1800049dc  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x1800049e3  xor     r8d, r8d; pvReserved
0x1800049e6  lea     edx, [r8+1]; dwClsContext
0x1800049ea  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x1800049f1  call    cs:__imp_CoGetClassObject
0x1800049f7  mov     ebx, eax
0x1800049f9  test    eax, eax
0x1800049fb  js      short loc_180004A1B
0x1800049fd  movups  xmm0, xmmword ptr cs:_GUID_88d96a05_f192_11d4_a65f_0040963251e5.Data1
0x180004a04  movdqu  xmmword ptr cs:?clsIDDocument@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm0; _GUID mlib::XmlDOM::clsIDDocument ...
0x180004a0c  movups  xmm1, xmmword ptr cs:_GUID_88d96a07_f192_11d4_a65f_0040963251e5.Data1
0x180004a13  movdqu  xmmword ptr cs:?clsIDSchema@XmlDOM@mlib@@0U_GUID@@A.Data1, xmm1; _GUID mlib::XmlDOM::clsIDSchema ...
0x180004a1b  shr     ebx, 1Fh
0x180004a1e  xor     bl, 1
0x180004a21  mov     rcx, [rsp+48h+arg_0]
0x180004a26  test    rcx, rcx
0x180004a29  jz      short loc_180004A38
0x180004a2b  mov     rax, [rcx]
0x180004a2e  mov     rax, [rax+10h]
0x180004a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a37  nop
0x180004a38  mov     al, bl
0x180004a3a  add     rsp, 40h
0x180004a3e  pop     rbx
0x180004a3f  retn
```
