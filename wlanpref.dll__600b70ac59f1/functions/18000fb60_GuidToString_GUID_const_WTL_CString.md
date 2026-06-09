# GuidToString(_GUID const &,WTL::CString &)

- ea: `0x18000fb60`
- end: `0x18000fbf8`
- name: `?GuidToString@@YAJAEBU_GUID@@AEAVCString@WTL@@@Z`
- size: `152`
- prototype: `int(const struct _GUID *, struct WTL::CString *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fdf0`
- `0x180027ad4`

## callees

- `0x1800036ac`
- `0x18000cf1c`
- `0x18000d1d0`
- `0x18000fb60`
- `0x180011190`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18000fb7b`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18000fb7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbe5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GuidToString(const struct _GUID *a1, struct WTL::CString *a2)
{
  HRESULT v3; // eax
  signed int v4; // ebx
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r8
  const wchar_t *v8; // [rsp+40h] [rbp+18h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp+20h] BYREF

  lpsz = 0;
  v3 = StringFromIID(a1, &lpsz);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    WTL::CString::CString((WTL::CString *)&v8, lpsz);
    WTL::CString::Replace(&v8, (wchar_t *)L"{", v5);
    WTL::CString::Replace(&v8, (wchar_t *)L"}", v6);
    WTL::CString::operator=(a2);
    WTL::CString::~CString((WTL::CString *)&v8);
    v4 = 0;
  }
  CoTaskMemFree(lpsz);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000fb60  mov     [rsp+arg_0], rbx
0x18000fb65  push    rdi
0x18000fb66  sub     rsp, 20h
0x18000fb6a  mov     rdi, rdx
0x18000fb6d  mov     [rsp+28h+lpsz], 0
0x18000fb76  lea     rdx, [rsp+28h+lpsz]; lplpsz
0x18000fb7b  call    cs:__imp_StringFromIID
0x18000fb81  mov     ebx, eax
0x18000fb83  test    eax, eax
0x18000fb85  jle     short loc_18000FB90
0x18000fb87  movzx   ebx, ax
0x18000fb8a  or      ebx, 80070000h
0x18000fb90  test    ebx, ebx
0x18000fb92  js      short loc_18000FBE0
0x18000fb94  mov     rdx, [rsp+28h+lpsz]; Source
0x18000fb99  lea     rcx, [rsp+28h+arg_10]; this
0x18000fb9e  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18000fba3  nop
0x18000fba4  lea     rdx, asc_180035058; "{"
0x18000fbab  lea     rcx, [rsp+28h+arg_10]; this
0x18000fbb0  call    ?Replace@CString@WTL@@QEAAHPEBG0@Z; WTL::CString::Replace(ushort const *,ushort const *)
0x18000fbb5  lea     rdx, asc_18003505C; "}"
0x18000fbbc  lea     rcx, [rsp+28h+arg_10]; this
0x18000fbc1  call    ?Replace@CString@WTL@@QEAAHPEBG0@Z; WTL::CString::Replace(ushort const *,ushort const *)
0x18000fbc6  lea     rdx, [rsp+28h+arg_10]
0x18000fbcb  mov     rcx, rdi; this
0x18000fbce  call    ??4CString@WTL@@QEAAAEAV01@AEBV01@@Z; WTL::CString::operator=(WTL::CString const &)
0x18000fbd3  nop
0x18000fbd4  lea     rcx, [rsp+28h+arg_10]; this
0x18000fbd9  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18000fbde  xor     ebx, ebx
0x18000fbe0  mov     rcx, [rsp+28h+lpsz]; pv
0x18000fbe5  call    cs:__imp_CoTaskMemFree
0x18000fbeb  mov     eax, ebx
0x18000fbed  mov     rbx, [rsp+28h+arg_0]
0x18000fbf2  add     rsp, 20h
0x18000fbf6  pop     rdi
0x18000fbf7  retn
```
