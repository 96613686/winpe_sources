# NCoreLibrary::ClsidToString(_GUID const &,NCoreLibrary::TString &)

- ea: `0x180014008`
- end: `0x180014056`
- name: `?ClsidToString@NCoreLibrary@@YAJAEBU_GUID@@AEAVTString@1@@Z`
- size: `78`
- prototype: `int(NCoreLibrary *__hidden this, const struct _GUID *, struct NCoreLibrary::TString *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180011df8`
- `0x180011fec`

## callees

- `0x180013f00`
- `0x180014008`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180014043`
- `ole32!CoTaskMemFree` at `0x180014043`
- `ole32!StringFromIID` at `0x180014023`
- `ole32!StringFromIID` at `0x180014023`

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
0x180014008  mov     [rsp+arg_0], rbx
0x18001400d  push    rdi
0x18001400e  sub     rsp, 20h
0x180014012  mov     rdi, rdx
0x180014015  mov     [rsp+28h+lpsz], 0
0x18001401e  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x180014023  call    cs:__imp_StringFromIID
0x180014029  mov     ebx, eax
0x18001402b  test    eax, eax
0x18001402d  js      short loc_180014049
0x18001402f  mov     rdx, [rsp+28h+lpsz]; unsigned __int16 *
0x180014034  mov     rcx, rdi; this
0x180014037  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x18001403c  mov     rcx, [rsp+28h+lpsz]; pv
0x180014041  mov     ebx, eax
0x180014043  call    cs:__imp_CoTaskMemFree
0x180014049  mov     eax, ebx
0x18001404b  mov     rbx, [rsp+28h+arg_0]
0x180014050  add     rsp, 20h
0x180014054  pop     rdi
0x180014055  retn
```
