# CNTFSSecurity::CNTFSSecurity(_SE_OBJECT_TYPE,int)

- ea: `0x1800061b0`
- end: `0x18000627b`
- name: `??0CNTFSSecurity@@QEAA@W4_SE_OBJECT_TYPE@@H@Z`
- size: `203`
- prototype: `CNTFSSecurity *__fastcall(CNTFSSecurity *__hidden this, enum _SE_OBJECT_TYPE, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005b00`
- `0x18000a66c`

## callees

- `0x18000be34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006267`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006267`

## pseudocode

```c
CNTFSSecurity *__fastcall CNTFSSecurity::CNTFSSecurity(CNTFSSecurity *this, enum _SE_OBJECT_TYPE a2, int a3)
{
  HINSTANCE v5; // rcx

  CSecurityInformation::CSecurityInformation(this, a2);
  v5 = g_hInstance;
  *(_QWORD *)this = &CNTFSSecurity::`vftable'{for `ISecurityInformation'};
  *((_DWORD *)this + 96) = a3;
  *((_QWORD *)this + 1) = &CSecurityInformation::`vftable'{for `IEffectivePermission'};
  *((_QWORD *)this + 2) = &CFSSecurity::`vftable'{for `IEffectivePermission2'};
  *((_QWORD *)this + 3) = &CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'};
  *((_QWORD *)this + 4) = &CFSSecurity::`vftable'{for `ISecurityInformation3'};
  *((_QWORD *)this + 5) = &CNTFSSecurity::`vftable'{for `ISecurityInformation4'};
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_BYTE *)this + 408) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_BYTE *)this + 424) = 0;
  LoadStringW(v5, 0x5Cu, (LPWSTR)this + 213, 100);
  return this;
}

```

## disassembly

```asm
0x1800061b0  mov     [rsp+arg_0], rbx
0x1800061b5  push    rdi
0x1800061b6  sub     rsp, 20h
0x1800061ba  mov     ebx, r8d
0x1800061bd  mov     rdi, rcx
0x1800061c0  call    ??0CSecurityInformation@@QEAA@W4_SE_OBJECT_TYPE@@@Z; CSecurityInformation::CSecurityInformation(_SE_OBJECT_TYPE)
0x1800061c5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800061cc  lea     rax, ??_7CNTFSSecurity@@6BISecurityInformation@@@; const CNTFSSecurity::`vftable'{for `ISecurityInformation'}
0x1800061d3  mov     [rdi], rax
0x1800061d6  lea     r8, [rdi+1AAh]; lpBuffer
0x1800061dd  lea     rax, ??_7CSecurityInformation@@6BIEffectivePermission@@@; const CSecurityInformation::`vftable'{for `IEffectivePermission'}
0x1800061e4  mov     [rdi+180h], ebx
0x1800061ea  mov     [rdi+8], rax
0x1800061ee  lea     rax, ??_7CFSSecurity@@6BIEffectivePermission2@@@; const CFSSecurity::`vftable'{for `IEffectivePermission2'}
0x1800061f5  mov     [rdi+10h], rax
0x1800061f9  lea     rax, ??_7CNTFSSecurity@@6BISecurityObjectTypeInfo@@@; const CNTFSSecurity::`vftable'{for `ISecurityObjectTypeInfo'}
0x180006200  mov     [rdi+18h], rax
0x180006204  lea     rax, ??_7CFSSecurity@@6BISecurityInformation3@@@; const CFSSecurity::`vftable'{for `ISecurityInformation3'}
0x18000620b  mov     [rdi+20h], rax
0x18000620f  lea     rax, ??_7CNTFSSecurity@@6BISecurityInformation4@@@; const CNTFSSecurity::`vftable'{for `ISecurityInformation4'}
0x180006216  mov     [rdi+28h], rax
0x18000621a  xor     eax, eax
0x18000621c  mov     [rdi+140h], rax
0x180006223  mov     [rdi+160h], rax
0x18000622a  mov     [rdi+168h], rax
0x180006231  lea     edx, [rax+5Ch]; uID
0x180006234  mov     [rdi+170h], rax
0x18000623b  lea     r9d, [rax+64h]; cchBufferMax
0x18000623f  mov     [rdi+178h], rax
0x180006246  mov     [rdi+188h], rax
0x18000624d  mov     [rdi+190h], rax
0x180006254  mov     [rdi+198h], al
0x18000625a  mov     [rdi+1A0h], rax
0x180006261  mov     [rdi+1A8h], al
0x180006267  call    cs:__imp_LoadStringW
0x18000626d  mov     rbx, [rsp+28h+arg_0]
0x180006272  mov     rax, rdi
0x180006275  add     rsp, 20h
0x180006279  pop     rdi
0x18000627a  retn
```
