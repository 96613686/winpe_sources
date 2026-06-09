# UserIdKeyManagerImplementation::IsLocalConnected(IIdentityProviderExecutionContext *,ushort const *,ushort const *,bool &)

- ea: `0x18002aed4`
- end: `0x18002afcc`
- name: `?IsLocalConnected@UserIdKeyManagerImplementation@@AEAAJPEAVIIdentityProviderExecutionContext@@PEBG1AEA_N@Z`
- size: `248`
- prototype: `int(UserIdKeyManagerImplementation *__hidden this, struct IIdentityProviderExecutionContext *, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002bef0`

## callees

- `0x18000a400`
- `0x180028578`
- `0x180028630`
- `0x18002aed4`
- `0x180050a64`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002af80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002af80`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UserIdKeyManagerImplementation::IsLocalConnected(
        UserIdKeyManagerImplementation *this,
        struct IIdentityProviderExecutionContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool *a5)
{
  bool *v7; // rsi
  __int64 v8; // rax
  struct IWinApiLite *v9; // rax
  int SID; // edi
  unsigned int v11; // ebx
  __int64 bIgnoreCase; // [rsp+20h] [rbp-58h]
  LPCWCH *p_lpString2; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-40h] BYREF
  char v16; // [rsp+40h] [rbp-38h]
  LPCWCH lpString2; // [rsp+80h] [rbp+8h] BYREF

  lpString2 = 0;
  v7 = a5;
  *a5 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = (struct IWinApiLite *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  p_lpString2 = &lpString2;
  v15 = 0;
  v16 = 1;
  SID = CWLIDCCHelper::GetSID(v9, a3, &v15);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpString2);
  if ( SID >= 0 )
  {
    v11 = SID;
    if ( CompareStringOrdinal(a4, -1, lpString2, -1, 1) == 2 )
      *v7 = 1;
  }
  else
  {
    v11 = 0;
    if ( SID != -2147023579 )
      v11 = SID;
  }
  LODWORD(bIgnoreCase) = *v7;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\useridkeymanagerimplementation.cpp",
    0x1DAu,
    L"IsLocalConnected=%d",
    bIgnoreCase);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString2);
  return v11;
}

```

## disassembly

```asm
0x18002aed4  mov     rax, rsp
0x18002aed7  mov     [rax+8], rcx
0x18002aedb  push    rbx
0x18002aedc  push    rbp
0x18002aedd  push    rsi
0x18002aede  push    rdi
0x18002aedf  sub     rsp, 58h
0x18002aee3  mov     rbp, r9
0x18002aee6  mov     rbx, r8
0x18002aee9  mov     qword ptr [rax+8], 0
0x18002aef1  mov     rsi, [rsp+78h+arg_20]
0x18002aef9  mov     byte ptr [rsi], 0
0x18002aefc  mov     rax, [rdx]
0x18002aeff  mov     rcx, rdx
0x18002af02  mov     rax, [rax+8]
0x18002af06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af0b  mov     rdx, rax
0x18002af0e  mov     rcx, [rax]
0x18002af11  mov     rax, [rcx+18h]
0x18002af15  mov     rcx, rdx
0x18002af18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af1d  lea     rcx, [rsp+78h+lpString2]
0x18002af25  mov     [rsp+78h+var_48], rcx
0x18002af2a  mov     [rsp+78h+var_40], 0
0x18002af33  mov     [rsp+78h+var_38], 1
0x18002af38  lea     r8, [rsp+78h+var_40]; unsigned __int16 **
0x18002af3d  mov     rdx, rbx; unsigned __int16 *
0x18002af40  mov     rcx, rax; struct IWinApiLite *
0x18002af43  call    ?GetSID@CWLIDCCHelper@@SAJPEAVIWinApiLite@@PEBGPEAPEAG@Z; CWLIDCCHelper::GetSID(IWinApiLite *,ushort const *,ushort * *)
0x18002af48  mov     edi, eax
0x18002af4a  lea     rcx, [rsp+78h+var_48]
0x18002af4f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002af54  test    edi, edi
0x18002af56  jns     short loc_18002AF65
0x18002af58  xor     ebx, ebx
0x18002af5a  cmp     edi, 80070525h
0x18002af60  cmovnz  ebx, edi
0x18002af63  jmp     short loc_18002AF8E
0x18002af65  mov     ebx, edi
0x18002af67  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18002af6f  or      edx, 0FFFFFFFFh; cchCount1
0x18002af72  mov     r9d, edx; cchCount2
0x18002af75  mov     r8, [rsp+78h+lpString2]; lpString2
0x18002af7d  mov     rcx, rbp; lpString1
0x18002af80  call    cs:__imp_CompareStringOrdinal
0x18002af86  cmp     eax, 2
0x18002af89  jnz     short loc_18002AF8E
0x18002af8b  mov     byte ptr [rsi], 1
0x18002af8e  movzx   ecx, byte ptr [rsi]
0x18002af91  mov     [rsp+78h+bIgnoreCase], ecx
0x18002af95  lea     r9, aIslocalconnect; "IsLocalConnected=%d"
0x18002af9c  mov     r8d, 1DAh; unsigned int
0x18002afa2  lea     rdx, aOnecoreuapDsEx_12; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002afa9  mov     ecx, 5; unsigned __int8
0x18002afae  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002afb3  nop
0x18002afb4  lea     rcx, [rsp+78h+lpString2]
0x18002afbc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002afc1  mov     eax, ebx
0x18002afc3  add     rsp, 58h
0x18002afc7  pop     rdi
0x18002afc8  pop     rsi
0x18002afc9  pop     rbp
0x18002afca  pop     rbx
0x18002afcb  retn
```
