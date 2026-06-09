# SubscriptionConfigWriter::DeleteAllPasswordEntries(ushort const *)

- ea: `0x1800155e8`
- end: `0x18001583c`
- name: `?DeleteAllPasswordEntries@SubscriptionConfigWriter@@SAXPEBG@Z`
- size: `596`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003f08`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x180003e6c`
- `0x1800062d4`
- `0x1800064e0`
- `0x180011c24`
- `0x180011d6c`
- `0x180011e68`
- `0x180011f40`
- `0x1800155e8`
- `0x1800159e0`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015667`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001574e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015667`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001574e`

## string_xrefs

- `0x180015719`: `CommonPassword`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SubscriptionConfigWriter::DeleteAllPasswordEntries(const unsigned __int16 *a1)
{
  const WCHAR *v2; // rdx
  unsigned int v3; // eax
  unsigned int v4; // ebx
  HKEY v5; // rdx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  HKEY hKey; // [rsp+30h] [rbp-79h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-71h] BYREF
  HKEY CurrentSubKey; // [rsp+40h] [rbp-69h] BYREF
  char v13[8]; // [rsp+48h] [rbp-61h] BYREF
  int v14; // [rsp+50h] [rbp-59h]
  LPCWSTR lpSubKey[4]; // [rsp+80h] [rbp-29h] BYREF
  void **pExceptionObject; // [rsp+A0h] [rbp-9h] BYREF
  char v17; // [rsp+A8h] [rbp-1h]
  const char *v18; // [rsp+B0h] [rbp+7h]
  __int64 v19; // [rsp+B8h] [rbp+Fh]
  __int64 v20; // [rsp+C0h] [rbp+17h]
  unsigned int v21; // [rsp+C8h] [rbp+1Fh]
  int v22; // [rsp+CCh] [rbp+23h]
  int v23; // [rsp+D0h] [rbp+27h]
  __int16 v24[8]; // [rsp+D8h] [rbp+2Fh] BYREF
  __int64 v25; // [rsp+E8h] [rbp+3Fh]
  __int64 v26; // [rsp+F0h] [rbp+47h]

  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  std::wstring::append(lpSubKey, L"\\Subscriptions\\");
  std::wstring::append(lpSubKey, a1);
  hKey = 0;
  v2 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] >= (LPCWSTR)8 )
    v2 = lpSubKey[0];
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0x2001Fu, &hKey);
  v4 = v3;
  if ( v3 != 2 )
  {
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v3);
      }
      v17 = 0;
      v18 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
      v19 = 0;
      v20 = 0;
      v21 = v4;
      v22 = -1;
      v23 = 656;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v26 = 7;
    v25 = 0;
    v24[0] = 0;
    SubscriptionConfigWriter::DeletePassword(hKey, L"CommonPassword");
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, L"EventSources", 0, 0x20019u, &phkResult) )
    {
      v5 = phkResult;
      phkResult = 0;
      RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v13, v5);
      v14 = 0;
      if ( !RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v13) )
      {
        do
        {
          v19 = 7;
          v18 = 0;
          LOWORD(pExceptionObject) = 0;
          CurrentSubKey = RegistryKeyEnumerator::GetCurrentSubKey((RegistryKeyEnumerator *)v13, 0x2001Fu);
          SubscriptionConfigWriter::DeletePassword(CurrentSubKey, L"TargetId");
          v6 = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v13);
          wmi::AutoRegKey::Close((wmi::AutoRegKey *)&CurrentSubKey);
          LOBYTE(v7) = 1;
          std::wstring::_Tidy(&pExceptionObject, v7, 0);
        }
        while ( !v6 );
      }
      RegistryKeyEnumerator::~RegistryKeyEnumerator((RegistryKeyEnumerator *)v13);
    }
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(v24, v8, 0);
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(lpSubKey, v9, 0);
}

```

## disassembly

```asm
0x1800155e8  mov     [rsp-8+arg_8], rbx
0x1800155ed  push    rbp
0x1800155ee  lea     rbp, [rsp-57h]
0x1800155f3  sub     rsp, 100h
0x1800155fa  mov     rax, cs:__security_cookie
0x180015601  xor     rax, rsp
0x180015604  mov     [rbp+57h+var_8], rax
0x180015608  mov     rbx, rcx
0x18001560b  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180015612  lea     rcx, [rbp+57h+lpSubKey]
0x180015616  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001561b  nop
0x18001561c  lea     rdx, aSubscriptions_1; "\\Subscriptions\\"
0x180015623  lea     rcx, [rbp+57h+lpSubKey]
0x180015627  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001562c  mov     rdx, rbx
0x18001562f  lea     rcx, [rbp+57h+lpSubKey]
0x180015633  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180015638  mov     [rbp+57h+hKey], 0
0x180015640  lea     rdx, [rbp+57h+lpSubKey]
0x180015644  cmp     [rbp+57h+var_68], 8
0x180015649  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001564e  lea     rax, [rbp+57h+hKey]
0x180015652  mov     [rsp+100h+phkResult], rax; phkResult
0x180015657  mov     r9d, 2001Fh; samDesired
0x18001565d  xor     r8d, r8d; ulOptions
0x180015660  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015667  call    cs:__imp_RegOpenKeyExW
0x18001566d  mov     ebx, eax
0x18001566f  cmp     eax, 2
0x180015672  jz      loc_180015807
0x180015678  test    eax, eax
0x18001567a  jz      loc_180015703
0x180015680  lea     rax, WPP_GLOBAL_Control
0x180015687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001568e  cmp     rcx, rax
0x180015691  jz      short loc_1800156B7
0x180015693  test    byte ptr [rcx+1Ch], 40h
0x180015697  jz      short loc_1800156B7
0x180015699  cmp     byte ptr [rcx+19h], 2
0x18001569d  jb      short loc_1800156B7
0x18001569f  mov     edx, 19h
0x1800156a4  mov     r9d, ebx
0x1800156a7  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x1800156ae  mov     rcx, [rcx+10h]
0x1800156b2  call    WPP_SF_D
0x1800156b7  mov     [rbp+57h+var_58], 0
0x1800156bb  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800156c2  mov     [rbp+57h+var_50], rax
0x1800156c6  mov     [rbp+57h+var_48], 0
0x1800156ce  mov     [rbp+57h+var_40], 0
0x1800156d6  mov     [rbp+57h+var_38], ebx
0x1800156d9  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x1800156e0  mov     [rbp+57h+var_30], 290h
0x1800156e7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800156ee  mov     [rbp+57h+pExceptionObject], rax
0x1800156f2  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800156f9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800156fd  call    _CxxThrowException_0
0x180015703  mov     [rbp+57h+var_10], 7
0x18001570b  mov     [rbp+57h+var_18], 0
0x180015713  xor     eax, eax
0x180015715  mov     [rbp+57h+var_28], ax
0x180015719  lea     rdx, aCommonpassword; "CommonPassword"
0x180015720  mov     rcx, [rbp+57h+hKey]; hKey
0x180015724  call    ?DeletePassword@SubscriptionConfigWriter@@CAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::DeletePassword(HKEY__ *,ushort const *)
0x180015729  mov     [rbp+57h+var_C8], 0
0x180015731  lea     rax, [rbp+57h+var_C8]
0x180015735  mov     [rsp+100h+phkResult], rax; phkResult
0x18001573a  mov     r9d, 20019h; samDesired
0x180015740  xor     r8d, r8d; ulOptions
0x180015743  lea     rdx, aEventsources; "EventSources"
0x18001574a  mov     rcx, [rbp+57h+hKey]; hKey
0x18001574e  call    cs:__imp_RegOpenKeyExW
0x180015754  test    eax, eax
0x180015756  jnz     loc_1800157EE
0x18001575c  mov     rdx, [rbp+57h+var_C8]; HKEY
0x180015760  mov     [rbp+57h+var_C8], 0
0x180015768  lea     rcx, [rbp+57h+var_B8]; this
0x18001576c  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *)
0x180015771  nop
0x180015772  mov     [rbp+57h+var_B0], 0
0x180015779  lea     rcx, [rbp+57h+var_B8]; this
0x18001577d  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x180015782  test    eax, eax
0x180015784  jnz     short loc_1800157E4
0x180015786  mov     [rbp+57h+var_48], 7
0x18001578e  mov     [rbp+57h+var_50], 0
0x180015796  xor     eax, eax
0x180015798  mov     word ptr [rbp+57h+pExceptionObject], ax
0x18001579c  mov     edx, 2001Fh; unsigned int
0x1800157a1  lea     rcx, [rbp+57h+var_B8]; this
0x1800157a5  call    ?GetCurrentSubKey@RegistryKeyEnumerator@@QEBAPEAUHKEY__@@K@Z; RegistryKeyEnumerator::GetCurrentSubKey(ulong)
0x1800157aa  mov     [rbp+57h+var_C0], rax
0x1800157ae  lea     rdx, aTargetid; "TargetId"
0x1800157b5  mov     rcx, rax; hKey
0x1800157b8  call    ?DeletePassword@SubscriptionConfigWriter@@CAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::DeletePassword(HKEY__ *,ushort const *)
0x1800157bd  lea     rcx, [rbp+57h+var_B8]; this
0x1800157c1  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x1800157c6  mov     ebx, eax
0x1800157c8  lea     rcx, [rbp+57h+var_C0]; this
0x1800157cc  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800157d1  nop
0x1800157d2  xor     r8d, r8d
0x1800157d5  mov     dl, 1
0x1800157d7  lea     rcx, [rbp+57h+pExceptionObject]
0x1800157db  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800157e0  test    ebx, ebx
0x1800157e2  jz      short loc_180015786
0x1800157e4  lea     rcx, [rbp+57h+var_B8]; this
0x1800157e8  call    ??1RegistryKeyEnumerator@@QEAA@XZ; RegistryKeyEnumerator::~RegistryKeyEnumerator(void)
0x1800157ed  nop
0x1800157ee  lea     rcx, [rbp+57h+var_C8]; this
0x1800157f2  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800157f7  nop
0x1800157f8  xor     r8d, r8d
0x1800157fb  mov     dl, 1
0x1800157fd  lea     rcx, [rbp+57h+var_28]
0x180015801  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015806  nop
0x180015807  lea     rcx, [rbp+57h+hKey]; this
0x18001580b  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180015810  nop
0x180015811  xor     r8d, r8d
0x180015814  mov     dl, 1
0x180015816  lea     rcx, [rbp+57h+lpSubKey]
0x18001581a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001581f  mov     rcx, [rbp+57h+var_8]
0x180015823  xor     rcx, rsp; StackCookie
0x180015826  call    __security_check_cookie
0x18001582b  mov     rbx, [rsp+100h+arg_8]
0x180015833  add     rsp, 100h
0x18001583a  pop     rbp
0x18001583b  retn
```
