# NCoreLibrary::ClsidToString(_GUID const &,NCoreLibrary::TString &)

- ea: `0x1800158e4`
- end: `0x18001593f`
- name: `?ClsidToString@NCoreLibrary@@YAJAEBU_GUID@@AEAVTString@1@@Z`
- size: `91`
- prototype: `int(NCoreLibrary *__hidden this, const struct _GUID *, struct NCoreLibrary::TString *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180013528`
- `0x18001374c`

## callees

- `0x1800157d4`
- `0x1800158e4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015925`
- `ole32!CoTaskMemFree` at `0x180015925`
- `ole32!StringFromIID` at `0x1800158ff`
- `ole32!StringFromIID` at `0x1800158ff`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::ClsidToString(const IID *this, struct _GUID *a2, struct NCoreLibrary::TString *a3)
{
  HRESULT v4; // ebx
  LPOLESTR lpsz; // [rsp+40h] [rbp+18h] BYREF

  lpsz = 0;
  v4 = StringFromIID(this, &lpsz);
  if ( v4 >= 0 )
  {
    v4 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)a2, lpsz);
    CoTaskMemFree(lpsz);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800158e4  mov     [rsp+arg_0], rbx
0x1800158e9  push    rdi
0x1800158ea  sub     rsp, 20h
0x1800158ee  mov     rdi, rdx
0x1800158f1  mov     [rsp+28h+lpsz], 0
0x1800158fa  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x1800158ff  call    cs:__imp_StringFromIID
0x180015906  nop     dword ptr [rax+rax+00h]
0x18001590b  mov     ebx, eax
0x18001590d  test    eax, eax
0x18001590f  js      short loc_180015931
0x180015911  mov     rdx, [rsp+28h+lpsz]; unsigned __int16 *
0x180015916  mov     rcx, rdi; this
0x180015919  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x18001591e  mov     rcx, [rsp+28h+lpsz]; pv
0x180015923  mov     ebx, eax
0x180015925  call    cs:__imp_CoTaskMemFree
0x18001592c  nop     dword ptr [rax+rax+00h]
0x180015931  mov     eax, ebx
0x180015933  mov     rbx, [rsp+28h+arg_0]
0x180015938  add     rsp, 20h
0x18001593c  pop     rdi
0x18001593d  retn
```
