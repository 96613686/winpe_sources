# WLInvokeProfileUIFromXMLFile

- ea: `0x180010780`
- end: `0x180010865`
- name: `WLInvokeProfileUIFromXMLFile`
- size: `229`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, HWND, int, int, enum _WL_DISPLAY_PAGES, __int64, int *, __int64, __int64, struct _AUI_CREDS_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010870`

## callees

- `0x180010700`
- `0x180010780`

## import_xrefs

- `wlanapi!WpFreeProfile` at `0x180010844`
- `wlanapi!WpFreeProfile` at `0x180010852`
- `wlanapi!WpFreeProfile` at `0x180010844`
- `wlanapi!WpFreeProfile` at `0x180010852`
- `wlanapi!WpParseProfileXml` at `0x1800107b9`
- `wlanapi!WpParseProfileXml` at `0x1800107b9`
- `wlanapi!WpGenerateProfileXml` at `0x180010832`
- `wlanapi!WpGenerateProfileXml` at `0x180010832`

## pseudocode

```c
__int64 __fastcall WLInvokeProfileUIFromXMLFile(
        __int64 a1,
        struct _GUID *a2,
        HWND a3,
        int a4,
        int a5,
        enum _WL_DISPLAY_PAGES a6,
        __int64 a7,
        int *a8,
        __int64 a9,
        __int64 a10,
        struct _AUI_CREDS_INFO *a11)
{
  __int64 v14; // rbx
  unsigned int ProfileXml; // edi
  unsigned int v16; // eax
  __int64 v18; // [rsp+50h] [rbp-38h] BYREF
  struct _PM_PROFILE *v19; // [rsp+58h] [rbp-30h] BYREF

  v19 = 0;
  v14 = 0;
  v18 = 0;
  ProfileXml = WpParseProfileXml(a1, &v19, a7, a10);
  if ( !ProfileXml )
  {
    v16 = WLInvokeProfileUI(v19, a2, a3, a4, a5, a6, (struct _PM_PROFILE **)&v18, a8, a11);
    v14 = v18;
    ProfileXml = v16;
    if ( !v16 && v18 && a9 )
      ProfileXml = WpGenerateProfileXml(v18);
  }
  if ( v19 )
    WpFreeProfile(v19);
  if ( v14 )
    WpFreeProfile(v14);
  return ProfileXml;
}

```

## disassembly

```asm
0x180010780  push    rbx
0x180010782  push    rbp
0x180010783  push    rsi
0x180010784  push    rdi
0x180010785  push    r14
0x180010787  sub     rsp, 60h
0x18001078b  mov     esi, r9d
0x18001078e  mov     [rsp+88h+var_30], 0
0x180010797  mov     r9, [rsp+88h+arg_48]
0x18001079f  mov     rbp, r8
0x1800107a2  mov     r8, [rsp+88h+arg_30]
0x1800107aa  mov     r14, rdx
0x1800107ad  xor     ebx, ebx
0x1800107af  lea     rdx, [rsp+88h+var_30]
0x1800107b4  mov     [rsp+88h+var_38], rbx
0x1800107b9  call    cs:__imp_WpParseProfileXml
0x1800107bf  mov     edi, eax
0x1800107c1  test    eax, eax
0x1800107c3  jnz     short loc_18001083A
0x1800107c5  mov     rax, [rsp+88h+arg_50]
0x1800107cd  mov     r9d, esi
0x1800107d0  mov     rcx, [rsp+88h+var_30]; struct _PM_PROFILE *
0x1800107d5  mov     r8, rbp
0x1800107d8  mov     [rsp+88h+var_48], rax; __int64
0x1800107dd  mov     rdx, r14
0x1800107e0  mov     rax, [rsp+88h+arg_38]
0x1800107e8  mov     [rsp+88h+var_50], rax; __int64
0x1800107ed  lea     rax, [rsp+88h+var_38]
0x1800107f2  mov     [rsp+88h+var_58], rax; __int64
0x1800107f7  mov     eax, [rsp+88h+arg_28]
0x1800107fe  mov     [rsp+88h+var_60], eax; enum _WL_DISPLAY_PAGES
0x180010802  mov     eax, [rsp+88h+arg_20]
0x180010809  mov     [rsp+88h+var_68], eax; int
0x18001080d  call    WLInvokeProfileUI
0x180010812  mov     rbx, [rsp+88h+var_38]
0x180010817  mov     edi, eax
0x180010819  test    eax, eax
0x18001081b  jnz     short loc_18001083A
0x18001081d  test    rbx, rbx
0x180010820  jz      short loc_18001083A
0x180010822  mov     rdx, [rsp+88h+arg_40]
0x18001082a  test    rdx, rdx
0x18001082d  jz      short loc_18001083A
0x18001082f  mov     rcx, rbx
0x180010832  call    cs:__imp_WpGenerateProfileXml
0x180010838  mov     edi, eax
0x18001083a  mov     rcx, [rsp+88h+var_30]
0x18001083f  test    rcx, rcx
0x180010842  jz      short loc_18001084A
0x180010844  call    cs:__imp_WpFreeProfile
0x18001084a  test    rbx, rbx
0x18001084d  jz      short loc_180010858
0x18001084f  mov     rcx, rbx
0x180010852  call    cs:__imp_WpFreeProfile
0x180010858  mov     eax, edi
0x18001085a  add     rsp, 60h
0x18001085e  pop     r14
0x180010860  pop     rdi
0x180010861  pop     rsi
0x180010862  pop     rbp
0x180010863  pop     rbx
0x180010864  retn
```
