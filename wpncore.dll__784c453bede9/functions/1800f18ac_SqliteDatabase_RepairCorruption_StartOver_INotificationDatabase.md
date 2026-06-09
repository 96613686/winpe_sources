# SqliteDatabase::RepairCorruption_StartOver(INotificationDatabase *)

- ea: `0x1800f18ac`
- end: `0x1800f1bcb`
- name: `?RepairCorruption_StartOver@SqliteDatabase@@SAXPEAUINotificationDatabase@@@Z`
- size: `799`
- prototype: `void __fastcall(struct INotificationDatabase *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f1714`

## callees

- `0x18000e5f4`
- `0x18001bf30`
- `0x18002bf64`
- `0x18002ee38`
- `0x1800542a8`
- `0x180065b08`
- `0x18006bf70`
- `0x18008a97c`
- `0x1800b99f0`
- `0x1800f18ac`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800f1980`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800f19a8`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800f1980`
- `api-ms-win-crt-private-l1-1-0!_o_remove` at `0x1800f19a8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f199d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f199d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f18ea`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f18ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SqliteDatabase::RepairCorruption_StartOver(struct INotificationDatabase *a1)
{
  int v2; // r12d
  HRESULT v3; // eax
  int v4; // eax
  __int64 (__fastcall *v5)(struct INotificationDatabase *, __int64 *); // rbx
  int v6; // eax
  unsigned __int8 v7; // bl
  unsigned int i; // r14d
  char v9; // al
  int v10; // eax
  int v11; // eax
  wil *v12; // rcx
  int v13; // [rsp+20h] [rbp-D8h]
  unsigned __int8 v14; // [rsp+30h] [rbp-C8h]
  unsigned int v16; // [rsp+34h] [rbp-C4h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C0h] BYREF
  char *FileName; // [rsp+40h] [rbp-B8h] BYREF
  GUID pguid; // [rsp+48h] [rbp-B0h] BYREF
  char **p_FileName; // [rsp+80h] [rbp-78h]
  __int64 v21; // [rsp+88h] [rbp-70h]
  GUID *p_pguid; // [rsp+90h] [rbp-68h]
  __int64 v23; // [rsp+98h] [rbp-60h]
  __int64 *v24; // [rsp+A0h] [rbp-58h]
  __int64 v25; // [rsp+A8h] [rbp-50h]
  unsigned int *v26; // [rsp+B0h] [rbp-48h]
  __int64 v27; // [rsp+B8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v2 = 0;
  pguid = GUID_NULL;
  v3 = CoCreateGuid(&pguid);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCAD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v3,
      v13);
  try
  {
    v4 = (*(__int64 (__fastcall **)(struct INotificationDatabase *))(*(_QWORD *)a1 + 48LL))(a1);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCAF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v4,
        v13);
    v17 = 0;
    v5 = *(__int64 (__fastcall **)(struct INotificationDatabase *, __int64 *))(*(_QWORD *)a1 + 32LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v17,
      0);
    v6 = v5(a1, &v17);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v6,
        v13);
    ConvertUtf16ToUtf8(&FileName, v17);
    v7 = 1;
    if ( remove(FileName) )
    {
      for ( i = 0; i < 5; ++i )
      {
        Sleep(0x7D0u);
        if ( !remove(FileName) )
          goto LABEL_10;
      }
      v9 = 1;
      v7 = 0;
    }
    else
    {
LABEL_10:
      v9 = 0;
    }
    v14 = v7;
    if ( v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCBF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)0x8000FFFFLL,
        v13);
    v16 = 0;
    v10 = (*(__int64 (__fastcall **)(struct INotificationDatabase *, unsigned int *))(*(_QWORD *)a1 + 40LL))(a1, &v16);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCC1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v10,
        v13);
    v11 = (*(__int64 (__fastcall **)(struct INotificationDatabase *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(
            a1,
            v17,
            v16);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCC2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
        (const char *)(unsigned int)v11,
        v13);
    wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(&FileName, 0);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  }
  catch ( ... )
  {
    v16 = wil::ResultFromCaughtException(v12);
    v2 = v16;
    v7 = v14;
  }
  if ( (unsigned int)dword_18015C038 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18015C038, 0x400000000000LL) )
  {
    v16 = v7;
    LODWORD(v17) = v2;
    FileName = (char *)0x1000000;
    v26 = &v16;
    v27 = 4;
    v24 = &v17;
    v25 = 4;
    p_pguid = &pguid;
    v23 = 16;
    p_FileName = &FileName;
    v21 = 8;
    v13 = 6;
    tlgWriteTransfer_EventWriteTransfer(&dword_18015C038, &byte_18013A0BF, 0, 0);
  }
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCD2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v2,
      v13);
}

```

## disassembly

```asm
0x1800f18ac  push    rbx
0x1800f18ae  push    r12
0x1800f18b0  push    r14
0x1800f18b2  push    r15
0x1800f18b4  sub     rsp, 0D8h
0x1800f18bb  mov     rax, cs:__security_cookie
0x1800f18c2  xor     rax, rsp
0x1800f18c5  mov     [rsp+0F8h+var_38], rax
0x1800f18cd  mov     r15, rcx
0x1800f18d0  xor     r12d, r12d
0x1800f18d3  mov     [rsp+0F8h+var_C8], r12b
0x1800f18d8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800f18df  movdqu  xmmword ptr [rsp+0F8h+pguid.Data1], xmm0
0x1800f18e5  lea     rcx, [rsp+0F8h+pguid]; pguid
0x1800f18ea  call    cs:__imp_CoCreateGuid
0x1800f18f0  mov     rcx, [rsp+0F8h]; this
0x1800f18f8  test    eax, eax
0x1800f18fa  jns     short loc_1800F1910
0x1800f18fc  mov     r9d, eax; char *
0x1800f18ff  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f1906  mov     edx, 0CADh; void *
0x1800f190b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f1910  mov     rax, [r15]
0x1800f1913  mov     rcx, r15
0x1800f1916  mov     rax, [rax+30h]
0x1800f191a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f191f  mov     rcx, [rsp+0F8h]; this
0x1800f1927  test    eax, eax
0x1800f1929  js      loc_1800F1B44
0x1800f192f  mov     [rsp+0F8h+var_C0], 0
0x1800f1938  mov     rax, [r15]
0x1800f193b  mov     rbx, [rax+20h]
0x1800f193f  xor     edx, edx
0x1800f1941  lea     rcx, [rsp+0F8h+var_C0]
0x1800f1946  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f194b  lea     rdx, [rsp+0F8h+var_C0]
0x1800f1950  mov     rcx, r15
0x1800f1953  mov     rax, rbx
0x1800f1956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f195b  mov     rcx, [rsp+0F8h]; this
0x1800f1963  test    eax, eax
0x1800f1965  js      loc_1800F1B59
0x1800f196b  mov     rdx, [rsp+0F8h+var_C0]
0x1800f1970  lea     rcx, [rsp+0F8h+FileName]
0x1800f1975  call    ?ConvertUtf16ToUtf8@@YA?AV?$unique_ptr@DUprocess_heap_deleter@wil@@@wistd@@PEBG@Z; ConvertUtf16ToUtf8(ushort const *)
0x1800f197a  nop
0x1800f197b  mov     rcx, [rsp+0F8h+FileName]; FileName
0x1800f1980  call    cs:__imp_remove
0x1800f1986  mov     ebx, 1
0x1800f198b  test    eax, eax
0x1800f198d  jz      short loc_1800F19B7
0x1800f198f  xor     r14d, r14d
0x1800f1992  cmp     r14d, 5
0x1800f1996  jnb     short loc_1800F19BB
0x1800f1998  mov     ecx, 7D0h; dwMilliseconds
0x1800f199d  call    cs:__imp_Sleep
0x1800f19a3  mov     rcx, [rsp+0F8h+FileName]; FileName
0x1800f19a8  call    cs:__imp_remove
0x1800f19ae  test    eax, eax
0x1800f19b0  jz      short loc_1800F19B7
0x1800f19b2  add     r14d, ebx
0x1800f19b5  jmp     short loc_1800F1992
0x1800f19b7  xor     al, al
0x1800f19b9  jmp     short loc_1800F19BF
0x1800f19bb  mov     al, bl
0x1800f19bd  xor     bl, bl
0x1800f19bf  mov     [rsp+0F8h+var_C8], bl
0x1800f19c3  mov     rcx, [rsp+0F8h]; this
0x1800f19cb  test    al, al
0x1800f19cd  jnz     loc_1800F1B6E
0x1800f19d3  mov     [rsp+0F8h+var_C4], 0
0x1800f19db  mov     rax, [r15]
0x1800f19de  lea     rdx, [rsp+0F8h+var_C4]
0x1800f19e3  mov     rcx, r15
0x1800f19e6  mov     rax, [rax+28h]
0x1800f19ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f19ef  mov     rcx, [rsp+0F8h]; this
0x1800f19f7  test    eax, eax
0x1800f19f9  js      loc_1800F1B85
0x1800f19ff  mov     rax, [r15]
0x1800f1a02  mov     r8d, [rsp+0F8h+var_C4]
0x1800f1a07  mov     rdx, [rsp+0F8h+var_C0]
0x1800f1a0c  mov     rcx, r15
0x1800f1a0f  mov     rax, [rax+18h]
0x1800f1a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1a18  mov     rcx, [rsp+0F8h]; this
0x1800f1a20  test    eax, eax
0x1800f1a22  js      loc_1800F1B99
0x1800f1a28  xor     edx, edx
0x1800f1a2a  lea     rcx, [rsp+0F8h+FileName]
0x1800f1a2f  call    ?reset@?$unique_ptr@U_GUID@@Uprocess_heap_deleter@wil@@@wistd@@QEAAXPEAU_GUID@@@Z; wistd::unique_ptr<_GUID,wil::process_heap_deleter>::reset(_GUID *)
0x1800f1a34  nop
0x1800f1a35  lea     rcx, [rsp+0F8h+var_C0]
0x1800f1a3a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800f1a3f  nop
0x1800f1a40  jmp     short loc_1800F1A4B
0x1800f1a42  mov     r12d, [rsp+0F8h+var_C4]
0x1800f1a47  mov     bl, [rsp+0F8h+var_C8]
0x1800f1a4b  mov     eax, cs:dword_18015C038
0x1800f1a51  cmp     eax, 5
0x1800f1a54  jbe     loc_1800F1B1C
0x1800f1a5a  mov     rdx, 400000000000h
0x1800f1a64  lea     rcx, dword_18015C038
0x1800f1a6b  call    _tlgKeywordOn
0x1800f1a70  test    al, al
0x1800f1a72  jz      loc_1800F1B1C
0x1800f1a78  movzx   eax, bl
0x1800f1a7b  mov     [rsp+0F8h+var_C4], eax
0x1800f1a7f  mov     dword ptr [rsp+0F8h+var_C0], r12d
0x1800f1a84  mov     [rsp+0F8h+FileName], 1000000h
0x1800f1a8d  lea     rax, [rsp+0F8h+var_C4]
0x1800f1a92  mov     [rsp+0F8h+var_48], rax
0x1800f1a9a  mov     [rsp+0F8h+var_40], 4
0x1800f1aa6  lea     rax, [rsp+0F8h+var_C0]
0x1800f1aab  mov     [rsp+0F8h+var_58], rax
0x1800f1ab3  mov     [rsp+0F8h+var_50], 4
0x1800f1abf  lea     rax, [rsp+0F8h+pguid]
0x1800f1ac4  mov     [rsp+0F8h+var_68], rax
0x1800f1acc  mov     [rsp+0F8h+var_60], 10h
0x1800f1ad8  lea     rax, [rsp+0F8h+FileName]
0x1800f1add  mov     [rsp+0F8h+var_78], rax
0x1800f1ae5  mov     [rsp+0F8h+var_70], 8
0x1800f1af1  lea     rax, [rsp+0F8h+var_98]
0x1800f1af6  mov     [rsp+0F8h+var_D0], rax
0x1800f1afb  mov     [rsp+0F8h+var_D8], 6; int
0x1800f1b03  xor     r9d, r9d
0x1800f1b06  xor     r8d, r8d
0x1800f1b09  lea     rdx, byte_18013A0BF
0x1800f1b10  lea     rcx, dword_18015C038
0x1800f1b17  call    _tlgWriteTransfer_EventWriteTransfer
0x1800f1b1c  test    r12d, r12d
0x1800f1b1f  js      loc_1800F1BAE
0x1800f1b25  mov     rcx, [rsp+0F8h+var_38]
0x1800f1b2d  xor     rcx, rsp; StackCookie
0x1800f1b30  call    __security_check_cookie
0x1800f1b35  add     rsp, 0D8h
0x1800f1b3c  pop     r15
0x1800f1b3e  pop     r14
0x1800f1b40  pop     r12
0x1800f1b42  pop     rbx
0x1800f1b43  retn
0x1800f1b44  mov     r9d, eax; char *
0x1800f1b47  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f1b4e  mov     edx, 0CAFh; void *
0x1800f1b53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1b59  mov     r9d, eax; char *
0x1800f1b5c  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f1b63  mov     edx, 0CB1h; void *
0x1800f1b68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1b6e  mov     r9d, 8000FFFFh; char *
0x1800f1b74  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f1b7b  mov     edx, 0CBFh; void *
0x1800f1b80  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1b85  mov     r9d, eax; char *
0x1800f1b88  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f1b8f  mov     edx, 0CC1h; void *
0x1800f1b94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1b99  mov     r9d, eax; char *
0x1800f1b9c  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f1ba3  mov     edx, 0CC2h; void *
0x1800f1ba8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f1bae  mov     rcx, [rsp+0F8h]; this
0x1800f1bb6  mov     r9d, r12d; char *
0x1800f1bb9  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f1bc0  mov     edx, 0CD2h; void *
0x1800f1bc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
