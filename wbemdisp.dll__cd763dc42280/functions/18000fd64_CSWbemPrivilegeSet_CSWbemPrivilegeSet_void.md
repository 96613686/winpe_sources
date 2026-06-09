# CSWbemPrivilegeSet::CSWbemPrivilegeSet(void)

- ea: `0x18000fd64`
- end: `0x18000fe05`
- name: `??0CSWbemPrivilegeSet@@QEAA@XZ`
- size: `161`
- prototype: `CSWbemPrivilegeSet *__fastcall(CSWbemPrivilegeSet *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180006850`
- `0x180007bd0`
- `0x180009320`
- `0x180009c20`
- `0x18000a270`
- `0x18000e9a0`
- `0x180010590`
- `0x180011b50`
- `0x18001e8bc`
- `0x18002dec0`
- `0x18002f0c0`

## callees

- `0x180010a9c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000fddd`
- `OLEAUT32!__imp_SysAllocString` at `0x18000fddd`

## string_xrefs

- `0x18000fdd6`: `SWbemPrivilegeSet`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CSWbemPrivilegeSet *__fastcall CSWbemPrivilegeSet::CSWbemPrivilegeSet(CSWbemPrivilegeSet *this)
{
  *(_QWORD *)this = &CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'};
  *((_QWORD *)this + 1) = &CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'};
  *((_QWORD *)this + 4) = &CDispatchHelp::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  std::map<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>::map<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>((char *)this + 112);
  *((_QWORD *)this + 9) = this;
  *((GUID *)this + 5) = IID_ISWbemPrivilegeSet;
  *((GUID *)this + 6) = CLSID_SWbemPrivilegeSet;
  *((_QWORD *)this + 5) = SysAllocString(L"SWbemPrivilegeSet");
  *((_DWORD *)this + 32) = 1;
  *((_BYTE *)this + 24) = 1;
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x18000fd64  mov     [rsp+arg_0], rcx
0x18000fd69  push    rbx
0x18000fd6a  sub     rsp, 20h
0x18000fd6e  mov     rbx, rcx
0x18000fd71  lea     rax, ??_7CSWbemPrivilegeSet@@6BISWbemPrivilegeSet@@@; const CSWbemPrivilegeSet::`vftable'{for `ISWbemPrivilegeSet'}
0x18000fd78  mov     [rcx], rax
0x18000fd7b  lea     rax, ??_7CSWbemPrivilegeSet@@6BISupportErrorInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `ISupportErrorInfo'}
0x18000fd82  mov     [rcx+8], rax
0x18000fd86  lea     rax, ??_7CSWbemPrivilegeSet@@6BIProvideClassInfo@@@; const CSWbemPrivilegeSet::`vftable'{for `IProvideClassInfo'}
0x18000fd8d  mov     [rcx+10h], rax
0x18000fd91  lea     rax, ??_7CDispatchHelp@@6B@; const CDispatchHelp::`vftable'
0x18000fd98  mov     [rcx+20h], rax
0x18000fd9c  xor     eax, eax
0x18000fd9e  mov     [rcx+38h], rax
0x18000fda2  mov     [rcx+40h], rax
0x18000fda6  mov     [rcx+48h], rax
0x18000fdaa  mov     [rcx+28h], rax
0x18000fdae  mov     [rcx+30h], eax
0x18000fdb1  add     rcx, 70h ; 'p'
0x18000fdb5  call    ??0?$map@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@std@@QEAA@XZ; std::map<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>::map<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>>(void)
0x18000fdba  movups  xmm1, xmmword ptr cs:CLSID_SWbemPrivilegeSet.Data1
0x18000fdc1  movups  xmm0, xmmword ptr cs:IID_ISWbemPrivilegeSet.Data1
0x18000fdc8  mov     [rbx+48h], rbx
0x18000fdcc  movdqu  xmmword ptr [rbx+50h], xmm0
0x18000fdd1  movdqu  xmmword ptr [rbx+60h], xmm1
0x18000fdd6  lea     rcx, aSwbemprivilege_0; "SWbemPrivilegeSet"
0x18000fddd  call    cs:__imp_SysAllocString
0x18000fde3  mov     [rbx+28h], rax
0x18000fde7  mov     dword ptr [rbx+80h], 1
0x18000fdf1  mov     byte ptr [rbx+18h], 1
0x18000fdf5  lock inc cs:?g_cObj@@3JA; long g_cObj
0x18000fdfc  mov     rax, rbx
0x18000fdff  add     rsp, 20h
0x18000fe03  pop     rbx
0x18000fe04  retn
```
