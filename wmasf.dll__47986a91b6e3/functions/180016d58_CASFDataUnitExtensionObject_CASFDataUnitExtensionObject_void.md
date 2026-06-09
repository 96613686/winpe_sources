# CASFDataUnitExtensionObject::CASFDataUnitExtensionObject(void)

- ea: `0x180016d58`
- end: `0x180016dea`
- name: `??0CASFDataUnitExtensionObject@@QEAA@XZ`
- size: `146`
- prototype: `CASFDataUnitExtensionObject *__fastcall(CASFDataUnitExtensionObject *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002350`
- `0x180007ca0`

## callees

- `0x180016f38`

## pseudocode

```c
CASFDataUnitExtensionObject *__fastcall CASFDataUnitExtensionObject::CASFDataUnitExtensionObject(
        CASFDataUnitExtensionObject *this)
{
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &CASFUnknown<IASFContentDescriptionObjectv1>::`vftable'{for `IASFContentDescriptionObjectv1'};
  *((_QWORD *)this + 1) = &CASFUnknown<IASFLanguageListObject>::`vftable'{for `IASFUnknownPriv'};
  *((_QWORD *)this + 2) = &CASFUnknown<IASFColorTableObject>::`vftable'{for `CPoolReleaseItem'};
  *(_QWORD *)this = &CASFDataUnitExtensionObject::`vftable'{for `IASFDataUnitExtensionObject'};
  *((_QWORD *)this + 1) = &CASFDataUnitExtensionObject::`vftable'{for `IASFUnknownPriv'};
  *((GUID *)this + 3) = GUID_NULL;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = &CASFDataUnitExtensionObject::`vftable'{for `CPoolReleaseItem'};
  *((_QWORD *)this + 8) = 24;
  *((_DWORD *)this + 20) = 1;
  *((_QWORD *)this + 14) = 0;
  *((GUID *)this + 3) = CLSID_ASFDataUnitExtensionObject;
  CASFDataUnitExtensionObject::FreshStart(this);
  return this;
}

```

## disassembly

```asm
0x180016d58  push    rbx
0x180016d5a  sub     rsp, 20h
0x180016d5e  mov     rbx, rcx
0x180016d61  lea     rax, ??_7?$CASFUnknown@UIASFContentDescriptionObjectv1@@@@6BIASFContentDescriptionObjectv1@@@; const CASFUnknown<IASFContentDescriptionObjectv1>::`vftable'{for `IASFContentDescriptionObjectv1'}
0x180016d68  xor     ecx, ecx
0x180016d6a  mov     [rbx+18h], rcx
0x180016d6e  mov     [rbx], rax
0x180016d71  lea     rax, ??_7?$CASFUnknown@UIASFLanguageListObject@@@@6BIASFUnknownPriv@@@; const CASFUnknown<IASFLanguageListObject>::`vftable'{for `IASFUnknownPriv'}
0x180016d78  mov     [rbx+8], rax
0x180016d7c  lea     rax, ??_7?$CASFUnknown@UIASFColorTableObject@@@@6BCPoolReleaseItem@@@; const CASFUnknown<IASFColorTableObject>::`vftable'{for `CPoolReleaseItem'}
0x180016d83  mov     [rbx+10h], rax
0x180016d87  lea     rax, ??_7CASFDataUnitExtensionObject@@6BIASFDataUnitExtensionObject@@@; const CASFDataUnitExtensionObject::`vftable'{for `IASFDataUnitExtensionObject'}
0x180016d8e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180016d95  mov     [rbx], rax
0x180016d98  lea     rax, ??_7CASFDataUnitExtensionObject@@6BIASFUnknownPriv@@@; const CASFDataUnitExtensionObject::`vftable'{for `IASFUnknownPriv'}
0x180016d9f  mov     [rbx+8], rax
0x180016da3  lea     rax, ??_7CASFDataUnitExtensionObject@@6BCPoolReleaseItem@@@; const CASFDataUnitExtensionObject::`vftable'{for `CPoolReleaseItem'}
0x180016daa  movdqu  xmmword ptr [rbx+30h], xmm0
0x180016daf  mov     [rbx+48h], ecx
0x180016db2  mov     [rbx+20h], rcx
0x180016db6  mov     [rbx+10h], rax
0x180016dba  mov     qword ptr [rbx+40h], 18h
0x180016dc2  mov     dword ptr [rbx+50h], 1
0x180016dc9  movups  xmm0, xmmword ptr cs:CLSID_ASFDataUnitExtensionObject.Data1
0x180016dd0  mov     [rbx+70h], rcx
0x180016dd4  mov     rcx, rbx; this
0x180016dd7  movdqu  xmmword ptr [rbx+30h], xmm0
0x180016ddc  call    ?FreshStart@CASFDataUnitExtensionObject@@IEAAXXZ; CASFDataUnitExtensionObject::FreshStart(void)
0x180016de1  mov     rax, rbx
0x180016de4  add     rsp, 20h
0x180016de8  pop     rbx
0x180016de9  retn
```
