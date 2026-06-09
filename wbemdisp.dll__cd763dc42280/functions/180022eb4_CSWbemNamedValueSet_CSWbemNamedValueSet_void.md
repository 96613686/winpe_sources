# CSWbemNamedValueSet::CSWbemNamedValueSet(void)

- ea: `0x180022eb4`
- end: `0x180022fa4`
- name: `??0CSWbemNamedValueSet@@QEAA@XZ`
- size: `240`
- prototype: `CSWbemNamedValueSet *__fastcall(struct IDispatch *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010c90`

## callees

- `0x1800126c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022f89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022f89`

## pseudocode

```c
struct IDispatch *__fastcall CSWbemNamedValueSet::CSWbemNamedValueSet(struct IDispatch *this)
{
  struct IDispatch *ppv; // rbx
  struct IDispatch *v3; // rcx
  GUID v5; // [rsp+30h] [rbp-28h] BYREF
  GUID v6; // [rsp+40h] [rbp-18h] BYREF

  ppv = this + 6;
  this[5].lpVtbl = 0;
  this->lpVtbl = (struct IDispatchVtbl *)&CSWbemNamedValueSet::`vftable'{for `ISWbemNamedValueSet'};
  this[6].lpVtbl = 0;
  this[1].lpVtbl = (struct IDispatchVtbl *)&CSWbemNamedValueSet::`vftable'{for `ISWbemInternalContext'};
  this[2].lpVtbl = (struct IDispatchVtbl *)&CSWbemNamedValueSet::`vftable'{for `IObjectSafety'};
  this[3].lpVtbl = (struct IDispatchVtbl *)&CSWbemNamedValueSet::`vftable'{for `ISupportErrorInfo'};
  this[4].lpVtbl = (struct IDispatchVtbl *)&CSWbemNamedValueSet::`vftable'{for `IProvideClassInfo'};
  v3 = this + 7;
  v3[3].lpVtbl = 0;
  v3[4].lpVtbl = 0;
  v3[5].lpVtbl = 0;
  v3[1].lpVtbl = 0;
  LODWORD(v3[2].lpVtbl) = 0;
  v3->lpVtbl = (struct IDispatchVtbl *)&CSWbemNamedValueSet::CContextDispatchHelp::`vftable';
  this[17].lpVtbl = 0;
  HIDWORD(this[18].lpVtbl) = 0;
  LOBYTE(this[18].lpVtbl) = 1;
  v5 = CLSID_SWbemNamedValueSet;
  v6 = IID_ISWbemNamedValueSet;
  CDispatchHelp::SetObj((CDispatchHelp *)v3, this, &v6, &v5, L"SWbemNamedValueSet");
  CoCreateInstance(&CLSID_WbemContext, 0, 1u, &IID_IWbemContext, (LPVOID *)&ppv->lpVtbl);
  _InterlockedIncrement(&g_cObj);
  return this;
}

```

## disassembly

```asm
0x180022eb4  mov     r11, rsp
0x180022eb7  mov     [r11+8], rbx
0x180022ebb  push    rdi
0x180022ebc  sub     rsp, 50h
0x180022ec0  xor     edx, edx
0x180022ec2  lea     rbx, [rcx+30h]
0x180022ec6  mov     [rcx+28h], rdx
0x180022eca  lea     rax, ??_7CSWbemNamedValueSet@@6BISWbemNamedValueSet@@@; const CSWbemNamedValueSet::`vftable'{for `ISWbemNamedValueSet'}
0x180022ed1  mov     [rcx], rax
0x180022ed4  lea     r9, [r11-28h]; struct _GUID *
0x180022ed8  mov     [rbx], rdx
0x180022edb  lea     rax, ??_7CSWbemNamedValueSet@@6BISWbemInternalContext@@@; const CSWbemNamedValueSet::`vftable'{for `ISWbemInternalContext'}
0x180022ee2  mov     [rcx+8], rax
0x180022ee6  lea     r8, [r11-18h]; struct _GUID *
0x180022eea  mov     rdi, rcx
0x180022eed  lea     rax, ??_7CSWbemNamedValueSet@@6BIObjectSafety@@@; const CSWbemNamedValueSet::`vftable'{for `IObjectSafety'}
0x180022ef4  mov     [rcx+10h], rax
0x180022ef8  lea     rax, ??_7CSWbemNamedValueSet@@6BISupportErrorInfo@@@; const CSWbemNamedValueSet::`vftable'{for `ISupportErrorInfo'}
0x180022eff  mov     [rcx+18h], rax
0x180022f03  lea     rax, ??_7CSWbemNamedValueSet@@6BIProvideClassInfo@@@; const CSWbemNamedValueSet::`vftable'{for `IProvideClassInfo'}
0x180022f0a  mov     [rcx+20h], rax
0x180022f0e  add     rcx, 38h ; '8'; this
0x180022f12  lea     rax, ??_7CContextDispatchHelp@CSWbemNamedValueSet@@6B@; const CSWbemNamedValueSet::CContextDispatchHelp::`vftable'
0x180022f19  mov     [rcx+18h], rdx
0x180022f1d  mov     [rcx+20h], rdx
0x180022f21  mov     [rcx+28h], rdx
0x180022f25  mov     [rcx+8], rdx
0x180022f29  mov     [rcx+10h], edx
0x180022f2c  mov     [rcx], rax
0x180022f2f  lea     rax, aSwbemnamedvalu; "SWbemNamedValueSet"
0x180022f36  mov     [rdi+88h], rdx
0x180022f3d  mov     [rdi+94h], edx
0x180022f43  mov     rdx, rdi; struct IDispatch *
0x180022f46  mov     byte ptr [rdi+90h], 1
0x180022f4d  movups  xmm0, xmmword ptr cs:CLSID_SWbemNamedValueSet.Data1
0x180022f54  mov     [r11-38h], rax
0x180022f58  movups  xmm1, xmmword ptr cs:IID_ISWbemNamedValueSet.Data1
0x180022f5f  movdqu  [rsp+58h+var_28], xmm0
0x180022f65  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm1
0x180022f6b  call    ?SetObj@CDispatchHelp@@QEAAXPEAUIDispatch@@U_GUID@@1PEAG@Z; CDispatchHelp::SetObj(IDispatch *,_GUID,_GUID,ushort *)
0x180022f70  xor     edx, edx; pUnkOuter
0x180022f72  mov     [rsp+58h+ppv], rbx; ppv
0x180022f77  lea     r9, IID_IWbemContext; riid
0x180022f7e  lea     rcx, CLSID_WbemContext; rclsid
0x180022f85  lea     r8d, [rdx+1]; dwClsContext
0x180022f89  call    cs:__imp_CoCreateInstance
0x180022f8f  lock inc cs:?g_cObj@@3JA; long g_cObj
0x180022f96  mov     rbx, [rsp+58h+arg_0]
0x180022f9b  mov     rax, rdi
0x180022f9e  add     rsp, 50h
0x180022fa2  pop     rdi
0x180022fa3  retn
```
