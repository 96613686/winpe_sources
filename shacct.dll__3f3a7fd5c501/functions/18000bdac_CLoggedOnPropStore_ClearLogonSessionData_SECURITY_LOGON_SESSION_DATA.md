# CLoggedOnPropStore::_ClearLogonSessionData(_SECURITY_LOGON_SESSION_DATA *)

- ea: `0x18000bdac`
- end: `0x18000be04`
- name: `?_ClearLogonSessionData@CLoggedOnPropStore@@AEAAXPEAU_SECURITY_LOGON_SESSION_DATA@@@Z`
- size: `88`
- prototype: `void __fastcall(CLoggedOnPropStore *__hidden this, struct _SECURITY_LOGON_SESSION_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013de0`

## callees

- `0x18000bdac`
- `0x1800140ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bdf8`

## pseudocode

```c
void __fastcall CLoggedOnPropStore::_ClearLogonSessionData(
        CLoggedOnPropStore *this,
        struct _SECURITY_LOGON_SESSION_DATA *a2)
{
  PSID Sid; // rcx

  if ( a2 )
  {
    _FreeUnicodeString((struct _UNICODE_STRING *)&a2->UserName);
    _FreeUnicodeString((struct _UNICODE_STRING *)&a2->LogonDomain);
    _FreeUnicodeString((struct _UNICODE_STRING *)&a2->AuthenticationPackage);
    _FreeUnicodeString((struct _UNICODE_STRING *)&a2->LogonServer);
    _FreeUnicodeString((struct _UNICODE_STRING *)&a2->DnsDomainName);
    _FreeUnicodeString((struct _UNICODE_STRING *)&a2->Upn);
    Sid = a2->Sid;
    if ( Sid )
      CoTaskMemFree(Sid);
  }
}

```

## disassembly

```asm
0x18000bdac  test    rdx, rdx
0x18000bdaf  jz      short locret_18000BE03
0x18000bdb1  push    rbx
0x18000bdb2  sub     rsp, 20h
0x18000bdb6  lea     rcx, [rdx+10h]; struct _UNICODE_STRING *
0x18000bdba  mov     rbx, rdx
0x18000bdbd  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x18000bdc2  lea     rcx, [rbx+20h]; struct _UNICODE_STRING *
0x18000bdc6  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x18000bdcb  lea     rcx, [rbx+30h]; struct _UNICODE_STRING *
0x18000bdcf  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x18000bdd4  lea     rcx, [rbx+58h]; struct _UNICODE_STRING *
0x18000bdd8  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x18000bddd  lea     rcx, [rbx+68h]; struct _UNICODE_STRING *
0x18000bde1  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x18000bde6  lea     rcx, [rbx+78h]; struct _UNICODE_STRING *
0x18000bdea  call    ?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z; _FreeUnicodeString(_UNICODE_STRING *)
0x18000bdef  mov     rcx, [rbx+48h]; pv
0x18000bdf3  test    rcx, rcx
0x18000bdf6  jz      short loc_18000BDFE
0x18000bdf8  call    cs:__imp_CoTaskMemFree
0x18000bdfe  add     rsp, 20h
0x18000be02  pop     rbx
0x18000be03  retn
```
