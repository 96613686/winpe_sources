# CHostObj::CreateObjectHelper(ushort *,_GUID *,IUnknown * *)

- ea: `0x14000f2f0`
- end: `0x14000f3ef`
- name: `?CreateObjectHelper@CHostObj@@IEAAJPEAGPEAU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `255`
- prototype: `int(CHostObj *__hidden this, unsigned __int16 *, struct _GUID *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f1b0`
- `0x14000f700`

## callees

- `0x14000997c`
- `0x140009b54`
- `0x140009f30`
- `0x14000a098`
- `0x14000f2f0`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x14000f30d`
- `ole32!CLSIDFromProgID` at `0x14000f30d`
- `ole32!CoCreateInstance` at `0x14000f3ba`
- `ole32!CoCreateInstance` at `0x14000f3ba`

## string_xrefs

- `0x14000f323`: `WScript.CreateObject`
- `0x14000f360`: `WScript.CreateObject`
- `0x14000f3c9`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::CreateObjectHelper(CHostObj *this, unsigned __int16 *a2, struct _GUID *a3, LPVOID *a4)
{
  HRESULT v8; // eax
  HRESULT IsClassAllowed; // ebx
  CHost *v10; // rcx
  int v12; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v13; // [rsp+38h] [rbp-30h] BYREF

  v8 = CLSIDFromProgID(a2, a3);
  IsClassAllowed = v8;
  if ( v8 >= 0 )
  {
    v10 = (CHost *)*((_QWORD *)this + 16);
    v12 = 0;
    IsClassAllowed = CHost::WldpIsClassAllowed(v10, a3, &v12);
    if ( IsClassAllowed >= 0 )
    {
      if ( v12 )
      {
        IsClassAllowed = CoCreateInstance(a3, 0, 0x15u, &IID_IUnknown, a4);
        if ( IsClassAllowed >= 0 )
          return (unsigned int)IsClassAllowed;
      }
      else
      {
        IsClassAllowed = -2147024891;
      }
    }
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Fu, a2);
    return (unsigned int)IsClassAllowed;
  }
  if ( v8 == -2147221005 )
  {
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Du, a2);
    return (unsigned int)-2147352567;
  }
  else
  {
    v13 = 0;
    FormatHResult(v8, &v13);
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", v13);
  }
  return (unsigned int)IsClassAllowed;
}

```

## disassembly

```asm
0x14000f2f0  push    rbx
0x14000f2f2  push    rbp
0x14000f2f3  push    rsi
0x14000f2f4  push    rdi
0x14000f2f5  push    r14
0x14000f2f7  sub     rsp, 40h
0x14000f2fb  mov     rdi, rdx
0x14000f2fe  mov     rbp, rcx
0x14000f301  mov     rcx, rdi; lpszProgID
0x14000f304  mov     rdx, r8; lpclsid
0x14000f307  mov     r14, r9
0x14000f30a  mov     rsi, r8
0x14000f30d  call    cs:__imp_CLSIDFromProgID
0x14000f313  mov     ebx, eax
0x14000f315  test    eax, eax
0x14000f317  jns     short loc_14000F375
0x14000f319  cmp     eax, 800401F3h
0x14000f31e  jnz     short loc_14000F346
0x14000f320  mov     r9, rdi
0x14000f323  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14000f32a  mov     r8d, 0C1Dh; unsigned int
0x14000f330  lea     rcx, IID_IHost; struct _GUID *
0x14000f337  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x14000f33c  mov     ebx, 80020009h
0x14000f341  jmp     loc_14000F3E2
0x14000f346  lea     rdx, [rsp+68h+var_30]; unsigned __int16 **
0x14000f34b  mov     [rsp+68h+var_30], 0
0x14000f354  mov     ecx, eax; dwMessageId
0x14000f356  call    ?FormatHResult@@YAJJPEAPEAG@Z; FormatHResult(long,ushort * *)
0x14000f35b  mov     r8, [rsp+68h+var_30]; unsigned __int16 *
0x14000f360  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14000f367  lea     rcx, IID_IHost; struct _GUID *
0x14000f36e  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBG1ZZ; Signal_Exception(_GUID const &,ushort const *,ushort const *,...)
0x14000f373  jmp     short loc_14000F3E2
0x14000f375  mov     rcx, [rbp+80h]; this
0x14000f37c  lea     r8, [rsp+68h+var_38]; int *
0x14000f381  mov     rdx, rsi; struct _GUID *
0x14000f384  mov     [rsp+68h+var_38], 0
0x14000f38c  call    ?WldpIsClassAllowed@CHost@@QEAAJAEBU_GUID@@PEAH@Z; CHost::WldpIsClassAllowed(_GUID const &,int *)
0x14000f391  mov     ebx, eax
0x14000f393  test    eax, eax
0x14000f395  js      short loc_14000F3C6
0x14000f397  cmp     [rsp+68h+var_38], 0
0x14000f39c  jnz     short loc_14000F3A5
0x14000f39e  mov     ebx, 80070005h
0x14000f3a3  jmp     short loc_14000F3C6
0x14000f3a5  xor     edx, edx; pUnkOuter
0x14000f3a7  mov     [rsp+68h+ppv], r14; ppv
0x14000f3ac  lea     r9, IID_IUnknown; riid
0x14000f3b3  mov     rcx, rsi; rclsid
0x14000f3b6  lea     r8d, [rdx+15h]; dwClsContext
0x14000f3ba  call    cs:__imp_CoCreateInstance
0x14000f3c0  mov     ebx, eax
0x14000f3c2  test    eax, eax
0x14000f3c4  jns     short loc_14000F3E2
0x14000f3c6  mov     r9, rdi
0x14000f3c9  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14000f3d0  mov     r8d, 0C1Fh; unsigned int
0x14000f3d6  lea     rcx, IID_IHost; struct _GUID *
0x14000f3dd  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x14000f3e2  mov     eax, ebx
0x14000f3e4  add     rsp, 40h
0x14000f3e8  pop     r14
0x14000f3ea  pop     rdi
0x14000f3eb  pop     rsi
0x14000f3ec  pop     rbp
0x14000f3ed  pop     rbx
0x14000f3ee  retn
```
