# CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage(_GUID &,std::list<_WWAN_DATA_ENABLEMENT_OBJECT,std::allocator<_WWAN_DATA_ENABLEMENT_OBJECT>> &)

- ea: `0x1800303d8`
- end: `0x180030651`
- name: `?_SetEnablementPoliciesToPersistedStorage@CWwanDataExecutor@@CAXAEAU_GUID@@AEAV?$list@U_WWAN_DATA_ENABLEMENT_OBJECT@@V?$allocator@U_WWAN_DATA_ENABLEMENT_OBJECT@@@std@@@std@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d808`

## callees

- `0x1800085d0`
- `0x1800094d0`
- `0x1800094f4`
- `0x180011650`
- `0x180012300`
- `0x1800123cc`
- `0x180013288`
- `0x180013588`
- `0x18001375c`
- `0x180014154`
- `0x180014f1c`
- `0x18001a63c`
- `0x1800303d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030419`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030419`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800304de`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800304de`
- `MobileNetworking!PersistentRegPathSetDWORD` at `0x1800305ce`
- `MobileNetworking!PersistentRegPathSetDWORD` at `0x1800305ce`

## string_xrefs

- `0x18003048b`: `creating registry key with error [%u] for enablement policy Policy path = [%s]`
- `0x180030504`: `error [%u] deleting registry key for enablement policy Policy path = [%s]`
- `0x180030515`: `deleted registry key for enablement policy Policy path = [%s]`
- `0x1800305f5`: `writing enablement policy to registry with error [%u]. Policy path = [%s]`
- `0x180030611`: `Wrote enablement policy to registry. Policy path = [%s], Position = %d, fEnable = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage(GUID *rguid, __int64 ***a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rax
  int v6; // r9d
  __int64 v8; // rax
  int v9; // r9d
  unsigned int v10; // esi
  __int64 **v11; // rdi
  __int64 *i; // rbx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // edx
  __int64 v17; // r9
  __int64 v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+28h] [rbp-D8h]
  struct _GUID Buf1; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+40h] [rbp-C0h]
  _BYTE v22[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[40]; // [rsp+88h] [rbp-78h] BYREF
  OLECHAR sz[48]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(sz, 0, 0x5Eu);
  StringFromGUID2(rguid, sz, 47);
  std::wstring::wstring((__int64)v23, (__int64)L"DataEnablementForPhone");
  std::wstring::append(v23, L"\\");
  std::wstring::append(v23, sz);
  std::wstring::wstring(v22);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  GetPersistentRegPathWstring(0, v4, v22);
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  if ( !v6 )
  {
    RegDeleteKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0);
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
    if ( v9 )
    {
      HIDWORD(v18) = HIDWORD(v8);
      WwanLog::Error(
        "CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage",
        0,
        L"error [%u] deleting registry key for enablement policy Policy path = [%s]");
    }
    else
    {
      WwanLog::Info(
        "CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage",
        0,
        L"deleted registry key for enablement policy Policy path = [%s]",
        v8);
    }
    v10 = 1;
    v11 = *a2;
    for ( i = *v11; ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)v11 )
        goto LABEL_3;
      Buf1 = (struct _GUID)*((_OWORD *)i + 1);
      v21 = *((_DWORD *)i + 8);
      std::wstring::wstring(v24);
      if ( !memcmp_0(&Buf1, &WWAN_PROFILE_SET_GUID_INTERNET_AO, 0x10u) )
      {
        v13 = L"InternetAlwaysOn";
      }
      else
      {
        if ( memcmp_0(&Buf1, &WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES, 0x10u) )
        {
          v17 = v10++;
          WwanLog::Info(
            "CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage",
            &Buf1,
            L"ignored profileSetGuid Position %d",
            v17);
          goto LABEL_17;
        }
        v13 = L"AllProfiles";
      }
      std::wstring::assign(v24, v13);
      ++v10;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
      PersistentRegPathSetDWORD(0, v14);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
      if ( v16 )
      {
        WwanLog::Error(
          "CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage",
          0,
          L"writing enablement policy to registry with error [%u]. Policy path = [%s]",
          v16,
          v15);
      }
      else
      {
        LODWORD(v19) = v21;
        LODWORD(v18) = v10;
        WwanLog::Info(
          "CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage",
          0,
          L"Wrote enablement policy to registry. Policy path = [%s], Position = %d, fEnable = %d",
          v15,
          v18,
          v19);
      }
LABEL_17:
      std::wstring::_Tidy_deallocate(v24);
    }
  }
  WwanLog::Error(
    "CWwanDataExecutor::_SetEnablementPoliciesToPersistedStorage",
    0,
    L"creating registry key with error [%u] for enablement policy Policy path = [%s]");
LABEL_3:
  std::wstring::_Tidy_deallocate(v22);
  return std::wstring::_Tidy_deallocate(v23);
}

```

## disassembly

```asm
0x1800303d8  push    rbp
0x1800303da  push    rbx
0x1800303db  push    rsi
0x1800303dc  push    rdi
0x1800303dd  lea     rbp, [rsp-28h]
0x1800303e2  sub     rsp, 128h
0x1800303e9  mov     rax, cs:__security_cookie
0x1800303f0  xor     rax, rsp
0x1800303f3  mov     [rbp+40h+var_30], rax
0x1800303f7  mov     rdi, rdx
0x1800303fa  mov     rbx, rcx
0x1800303fd  xor     edx, edx; Val
0x1800303ff  lea     r8d, [rdx+5Eh]; Size
0x180030403  lea     rcx, [rbp+40h+sz]; void *
0x180030407  call    memset_0
0x18003040c  mov     r8d, 2Fh ; '/'; cchMax
0x180030412  lea     rdx, [rbp+40h+sz]; lpsz
0x180030416  mov     rcx, rbx; rguid
0x180030419  call    cs:__imp_StringFromGUID2
0x18003041f  lea     rdx, ?sc_wszEnablementPolicyRegSubPath@CWwanDataExecutor@@0QBGB; "DataEnablementForPhone"
0x180030426  lea     rcx, [rsp+140h+var_D8]
0x18003042b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030430  nop
0x180030431  lea     rdx, SubBlock; "\\"
0x180030438  lea     rcx, [rsp+140h+var_D8]
0x18003043d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180030442  lea     rdx, [rbp+40h+sz]
0x180030446  lea     rcx, [rsp+140h+var_D8]
0x18003044b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180030450  lea     rcx, [rsp+140h+var_F8]
0x180030455  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003045a  nop
0x18003045b  lea     rcx, [rsp+140h+var_D8]
0x180030460  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030465  mov     rdx, rax
0x180030468  lea     r8, [rsp+140h+var_F8]
0x18003046d  xor     ecx, ecx
0x18003046f  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x180030474  mov     r9d, eax
0x180030477  lea     rcx, [rsp+140h+var_F8]
0x18003047c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030481  test    r9d, r9d
0x180030484  jz      short loc_1800304CE
0x180030486  mov     [rsp+140h+var_120], rax
0x18003048b  lea     r8, aCreatingRegist; "creating registry key with error [%u] f"...
0x180030492  xor     edx, edx; struct _GUID *
0x180030494  lea     rcx, aCwwandataexecu_21; "CWwanDataExecutor::_SetEnablementPolici"...
0x18003049b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800304a0  nop
0x1800304a1  lea     rcx, [rsp+140h+var_F8]
0x1800304a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800304ab  nop
0x1800304ac  lea     rcx, [rsp+140h+var_D8]
0x1800304b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800304b6  mov     rcx, [rbp+40h+var_30]
0x1800304ba  xor     rcx, rsp; StackCookie
0x1800304bd  call    __security_check_cookie
0x1800304c2  add     rsp, 128h
0x1800304c9  pop     rdi
0x1800304ca  pop     rsi
0x1800304cb  pop     rbx
0x1800304cc  pop     rbp
0x1800304cd  retn
0x1800304ce  xor     r9d, r9d; Reserved
0x1800304d1  xor     r8d, r8d; samDesired
0x1800304d4  mov     rdx, rax; lpSubKey
0x1800304d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800304de  call    cs:__imp_RegDeleteKeyExW
0x1800304e4  mov     r9d, eax
0x1800304e7  lea     rcx, [rsp+140h+var_F8]
0x1800304ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800304f1  xor     edx, edx; struct _GUID *
0x1800304f3  lea     rcx, aCwwandataexecu_21; "CWwanDataExecutor::_SetEnablementPolici"...
0x1800304fa  test    r9d, r9d
0x1800304fd  jz      short loc_180030512
0x1800304ff  mov     [rsp+140h+var_120], rax
0x180030504  lea     r8, aErrorUDeleting; "error [%u] deleting registry key for en"...
0x18003050b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180030510  jmp     short loc_180030521
0x180030512  mov     r9, rax
0x180030515  lea     r8, aDeletedRegistr_0; "deleted registry key for enablement pol"...
0x18003051c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180030521  mov     esi, 1
0x180030526  mov     rdi, [rdi]
0x180030529  mov     rbx, [rdi]
0x18003052c  cmp     rbx, rdi
0x18003052f  jz      loc_1800304A1
0x180030535  movups  xmm0, xmmword ptr [rbx+10h]
0x180030539  movups  [rsp+140h+Buf1], xmm0
0x18003053e  mov     eax, [rbx+20h]
0x180030541  mov     [rsp+140h+var_100], eax
0x180030545  lea     rcx, [rbp+40h+var_B8]
0x180030549  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003054e  nop
0x18003054f  mov     r8d, 10h; Size
0x180030555  lea     rdx, WWAN_PROFILE_SET_GUID_INTERNET_AO; Buf2
0x18003055c  lea     rcx, [rsp+140h+Buf1]; Buf1
0x180030561  call    memcmp_0
0x180030566  test    eax, eax
0x180030568  jnz     short loc_180030573
0x18003056a  lea     rdx, ?sc_wszProfileSetPolicyAlwaysOnInternetValue@CWwanDataExecutor@@0QBGB; "InternetAlwaysOn"
0x180030571  jmp     short loc_180030599
0x180030573  mov     r8d, 10h; Size
0x180030579  lea     rdx, WWAN_PROFILE_SET_GUID_ALL_HOST_PROFILES; Buf2
0x180030580  lea     rcx, [rsp+140h+Buf1]; Buf1
0x180030585  call    memcmp_0
0x18003058a  test    eax, eax
0x18003058c  jnz     loc_180030621
0x180030592  lea     rdx, ?sc_wszProfileSetPolicyAllProfilesValue@CWwanDataExecutor@@0QBGB; "AllProfiles"
0x180030599  lea     rcx, [rbp+40h+var_B8]
0x18003059d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800305a2  mov     r9d, esi
0x1800305a5  inc     esi
0x1800305a7  shl     r9d, 10h
0x1800305ab  movzx   eax, word ptr [rsp+140h+var_100]
0x1800305b0  or      r9d, eax
0x1800305b3  lea     rcx, [rbp+40h+var_B8]
0x1800305b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800305bc  mov     r8, rax
0x1800305bf  lea     rcx, [rsp+140h+var_D8]
0x1800305c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800305c9  mov     rdx, rax
0x1800305cc  xor     ecx, ecx
0x1800305ce  call    cs:__imp_PersistentRegPathSetDWORD
0x1800305d4  mov     edx, eax
0x1800305d6  lea     rcx, [rbp+40h+var_B8]
0x1800305da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800305df  mov     r9, rax
0x1800305e2  lea     rcx, aCwwandataexecu_21; "CWwanDataExecutor::_SetEnablementPolici"...
0x1800305e9  test    edx, edx
0x1800305eb  jz      short loc_180030605
0x1800305ed  mov     [rsp+140h+var_120], rax
0x1800305f2  mov     r9d, edx
0x1800305f5  lea     r8, aWritingEnablem; "writing enablement policy to registry w"...
0x1800305fc  xor     edx, edx; struct _GUID *
0x1800305fe  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180030603  jmp     short loc_18003063F
0x180030605  mov     eax, [rsp+140h+var_100]
0x180030609  mov     dword ptr [rsp+140h+var_118], eax
0x18003060d  mov     dword ptr [rsp+140h+var_120], esi
0x180030611  lea     r8, aWroteEnablemen; "Wrote enablement policy to registry. Po"...
0x180030618  xor     edx, edx; struct _GUID *
0x18003061a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003061f  jmp     short loc_18003063F
0x180030621  mov     r9d, esi
0x180030624  inc     esi
0x180030626  lea     r8, aIgnoredProfile; "ignored profileSetGuid Position %d"
0x18003062d  lea     rdx, [rsp+140h+Buf1]; struct _GUID *
0x180030632  lea     rcx, aCwwandataexecu_21; "CWwanDataExecutor::_SetEnablementPolici"...
0x180030639  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003063e  nop
0x18003063f  lea     rcx, [rbp+40h+var_B8]
0x180030643  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030648  mov     rbx, [rbx]
0x18003064b  jmp     loc_18003052C
```
