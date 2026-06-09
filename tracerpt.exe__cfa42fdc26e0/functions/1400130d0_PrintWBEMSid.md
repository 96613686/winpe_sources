# PrintWBEMSid

- ea: `0x1400130d0`
- end: `0x1400131bf`
- name: `PrintWBEMSid`
- size: `239`
- prototype: `void __fastcall(struct _iobuf *, __int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001232c`

## callees

- `0x140009c78`
- `0x1400130d0`
- `0x140013a04`
- `0x140016360`
- `0x140040130`
- `0x1400401c0`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140013143`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140013143`

## pseudocode

```c
void __fastcall PrintWBEMSid(struct _iobuf *a1, __int64 a2, void *a3)
{
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[1024]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReferencedDomainName[1024]; // [rsp+850h] [rbp+750h] BYREF
  unsigned __int16 v9[2048]; // [rsp+1050h] [rbp+F50h] BYREF

  peUse = 0;
  cchName = 1024;
  cchReferencedDomainName = 1024;
  if ( LookupAccountSidW(0, a3, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse)
    && (int)StringCchPrintfW(v9, 0x800u, L"\\\\%s\\%s", ReferencedDomainName, Name) >= 0 )
  {
    PrintWString(a1, 1, 0, v9);
  }
  else
  {
    TracerptFPutws((wchar_t *)L"System", a1);
  }
}

```

## disassembly

```asm
0x1400130d0  mov     [rsp-8+arg_8], rbx
0x1400130d5  push    rbp
0x1400130d6  lea     rbp, [rsp-1F60h]
0x1400130de  mov     eax, 2060h
0x1400130e3  call    _alloca_probe
0x1400130e8  sub     rsp, rax
0x1400130eb  mov     rax, cs:__security_cookie
0x1400130f2  xor     rax, rsp
0x1400130f5  mov     [rbp+1F60h+var_10], rax
0x1400130fc  mov     rbx, rcx
0x1400130ff  mov     [rsp+2060h+var_2020], 0
0x140013107  mov     ecx, 400h
0x14001310c  lea     r9, [rsp+2060h+cchName]; cchName
0x140013111  mov     [rsp+2060h+cchName], ecx
0x140013115  mov     rdx, r8; Sid
0x140013118  mov     [rsp+2060h+var_201C], ecx
0x14001311c  lea     r8, [rsp+2060h+Name]; Name
0x140013121  lea     rcx, [rsp+2060h+var_2020]
0x140013126  mov     [rsp+2060h+peUse], rcx; peUse
0x14001312b  lea     rcx, [rsp+2060h+var_201C]
0x140013130  mov     [rsp+2060h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x140013135  lea     rcx, [rbp+1F60h+var_1810]
0x14001313c  mov     [rsp+2060h+ReferencedDomainName], rcx; ReferencedDomainName
0x140013141  xor     ecx, ecx; lpSystemName
0x140013143  call    cs:__imp_LookupAccountSidW
0x140013149  test    eax, eax
0x14001314b  jz      short loc_140013190
0x14001314d  lea     rax, [rsp+2060h+Name]
0x140013152  mov     edx, 800h; unsigned __int64
0x140013157  lea     r9, [rbp+1F60h+var_1810]
0x14001315e  mov     [rsp+2060h+ReferencedDomainName], rax
0x140013163  lea     r8, aSS_2; "\\\\%s\\%s"
0x14001316a  lea     rcx, [rbp+1F60h+var_1010]; unsigned __int16 *
0x140013171  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140013176  test    eax, eax
0x140013178  js      short loc_140013190
0x14001317a  lea     r9, [rbp+1F60h+var_1010]; unsigned __int16 *
0x140013181  xor     r8d, r8d; unsigned __int8
0x140013184  mov     dl, 1; unsigned __int8
0x140013186  mov     rcx, rbx; struct _iobuf *
0x140013189  call    ?PrintWString@@YAXPEAU_iobuf@@EEPEAG@Z; PrintWString(_iobuf *,uchar,uchar,ushort *)
0x14001318e  jmp     short loc_14001319F
0x140013190  mov     rdx, rbx; struct _iobuf *
0x140013193  lea     rcx, aSystem; "System"
0x14001319a  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x14001319f  mov     rcx, [rbp+1F60h+var_10]
0x1400131a6  xor     rcx, rsp; StackCookie
0x1400131a9  call    __security_check_cookie
0x1400131ae  mov     rbx, [rsp+2060h+arg_8]
0x1400131b6  add     rsp, 2060h
0x1400131bd  pop     rbp
0x1400131be  retn
```
