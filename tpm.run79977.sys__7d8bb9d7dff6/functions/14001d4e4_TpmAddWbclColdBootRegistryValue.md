# TpmAddWbclColdBootRegistryValue

- ea: `0x14001d4e4`
- end: `0x14001d635`
- name: `TpmAddWbclColdBootRegistryValue`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140012568`

## callees

- `0x140009f70`
- `0x14000b6c8`
- `0x14001d02c`
- `0x14001d198`
- `0x14001d4e4`
- `0x140045430`

## pseudocode

```c
__int64 __fastcall TpmAddWbclColdBootRegistryValue(__int64 a1)
{
  int v1; // edi
  unsigned __int8 *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // eax
  unsigned __int8 *v6; // rax
  __int64 v7; // rcx
  unsigned __int64 retaddr; // [rsp+38h] [rbp+8h]
  unsigned __int64 v10; // [rsp+40h] [rbp+10h] BYREF
  __int64 v11; // [rsp+48h] [rbp+18h] BYREF

  LODWORD(v10) = 0;
  v11 = 0;
  v1 = TpmRegistry::QueryValue(a1, L"WBCL", 0, &v10);
  if ( v1 >= 0 )
  {
    v2 = TpmAlloc(1, (unsigned int)v10, retaddr);
    wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::reset(
      &v11,
      v2);
    if ( !v11 )
    {
LABEL_3:
      v1 = -1073741670;
      goto LABEL_12;
    }
    v1 = TpmRegistry::QueryValue(v3, L"WBCL", v11, &v10);
    if ( v1 >= 0 )
    {
      v1 = TpmRegistry::AssignValue(1, L"WBCLColdboot", 3u, v11, v10);
      if ( v1 >= 0 )
      {
        LODWORD(v10) = 0;
        v5 = TpmRegistry::QueryValue(v4, L"WBCLDrtm", 0, &v10);
        v1 = v5;
        if ( v5 == -1073741772 )
        {
          v1 = 0;
          goto LABEL_12;
        }
        if ( v5 < 0 )
          goto LABEL_12;
        v6 = TpmAlloc(1, (unsigned int)v10, retaddr);
        wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::reset(
          &v11,
          v6);
        if ( !v11 )
          goto LABEL_3;
        v1 = TpmRegistry::QueryValue(v7, L"WBCLDrtm", v11, &v10);
        if ( v1 >= 0 )
          v1 = TpmRegistry::AssignValue(1, L"WBCLDrtmColdboot", 3u, v11, v10);
      }
    }
  }
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&v11);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001d4e4  mov     [rsp-8+arg_10], rdi
0x14001d4e9  push    rbp
0x14001d4ea  mov     rbp, rsp
0x14001d4ed  sub     rsp, 30h
0x14001d4f1  lea     r9, [rbp+arg_0]
0x14001d4f5  mov     dword ptr [rbp+arg_0], 0
0x14001d4fc  xor     r8d, r8d
0x14001d4ff  mov     [rbp+arg_8], 0
0x14001d507  lea     rdx, aWbcl; "WBCL"
0x14001d50e  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGPEAEPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,uchar *,ulong *)
0x14001d513  mov     edi, eax
0x14001d515  test    eax, eax
0x14001d517  js      loc_14001D61E
0x14001d51d  mov     r8, [rbp+8]; unsigned __int64
0x14001d521  mov     cl, 1; bool
0x14001d523  mov     edx, dword ptr [rbp+arg_0]; unsigned __int64
0x14001d526  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14001d52b  mov     rdx, rax
0x14001d52e  lea     rcx, [rbp+arg_8]
0x14001d532  call    ?reset@?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?TpmFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAAXPEAE@Z; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::reset(uchar *)
0x14001d537  cmp     [rbp+arg_8], 0
0x14001d53c  jnz     short loc_14001D548
0x14001d53e  mov     edi, 0C000009Ah
0x14001d543  jmp     loc_14001D61E
0x14001d548  mov     r8, [rbp+arg_8]
0x14001d54c  lea     r9, [rbp+arg_0]
0x14001d550  lea     rdx, aWbcl; "WBCL"
0x14001d557  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGPEAEPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,uchar *,ulong *)
0x14001d55c  mov     edi, eax
0x14001d55e  test    eax, eax
0x14001d560  js      loc_14001D61E
0x14001d566  mov     eax, dword ptr [rbp+arg_0]
0x14001d569  lea     rdx, aWbclcoldboot; "WBCLColdboot"
0x14001d570  mov     r9, [rbp+arg_8]
0x14001d574  mov     r8d, 3
0x14001d57a  mov     [rsp+30h+var_10], eax
0x14001d57e  lea     ecx, [r8-2]
0x14001d582  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x14001d587  mov     edi, eax
0x14001d589  test    eax, eax
0x14001d58b  js      loc_14001D61E
0x14001d591  lea     r9, [rbp+arg_0]
0x14001d595  mov     dword ptr [rbp+arg_0], 0
0x14001d59c  xor     r8d, r8d
0x14001d59f  lea     rdx, aWbcldrtm; "WBCLDrtm"
0x14001d5a6  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGPEAEPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,uchar *,ulong *)
0x14001d5ab  mov     edi, eax
0x14001d5ad  cmp     eax, 0C0000034h
0x14001d5b2  jnz     short loc_14001D5B8
0x14001d5b4  xor     edi, edi
0x14001d5b6  jmp     short loc_14001D61E
0x14001d5b8  test    eax, eax
0x14001d5ba  js      short loc_14001D61E
0x14001d5bc  mov     r8, [rbp+8]; unsigned __int64
0x14001d5c0  mov     cl, 1; bool
0x14001d5c2  mov     edx, dword ptr [rbp+arg_0]; unsigned __int64
0x14001d5c5  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14001d5ca  mov     rdx, rax
0x14001d5cd  lea     rcx, [rbp+arg_8]
0x14001d5d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?TpmFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAAXPEAE@Z; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::reset(uchar *)
0x14001d5d6  cmp     [rbp+arg_8], 0
0x14001d5db  jz      loc_14001D53E
0x14001d5e1  mov     r8, [rbp+arg_8]
0x14001d5e5  lea     r9, [rbp+arg_0]
0x14001d5e9  lea     rdx, aWbcldrtm; "WBCLDrtm"
0x14001d5f0  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGPEAEPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,uchar *,ulong *)
0x14001d5f5  mov     edi, eax
0x14001d5f7  test    eax, eax
0x14001d5f9  js      short loc_14001D61E
0x14001d5fb  mov     eax, dword ptr [rbp+arg_0]
0x14001d5fe  lea     rdx, aWbcldrtmcoldbo; "WBCLDrtmColdboot"
0x14001d605  mov     r9, [rbp+arg_8]
0x14001d609  mov     r8d, 3
0x14001d60f  mov     [rsp+30h+var_10], eax
0x14001d613  lea     ecx, [r8-2]
0x14001d617  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x14001d61c  mov     edi, eax
0x14001d61e  lea     rcx, [rbp+arg_8]
0x14001d622  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?TpmFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&TpmFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x14001d627  mov     eax, edi
0x14001d629  mov     rdi, [rsp+30h+arg_10]
0x14001d62e  add     rsp, 30h
0x14001d632  pop     rbp
0x14001d633  retn
```
