# BoundSubscription::CleanupInativeEventresourceCallback(void *,uchar)

- ea: `0x18000b300`
- end: `0x18000b71e`
- name: `?CleanupInativeEventresourceCallback@BoundSubscription@@CAXPEAXE@Z`
- size: `1054`
- prototype: `void __fastcall(char *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x1800062d4`
- `0x1800064e0`
- `0x18000b300`
- `0x1800120f8`
- `0x18001fe50`
- `0x180023010`

## import_xrefs

- `msvcrt!_ltow` at `0x18000b57b`
- `msvcrt!_ltow` at `0x18000b57b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b34b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b34b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b6ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b6e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b413`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b413`

## string_xrefs

- `0x18000b45f`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000b50d`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall BoundSubscription::CleanupInativeEventresourceCallback(char *a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  _QWORD *v3; // rdx
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // edi
  const unsigned __int16 **v7; // rdi
  const unsigned __int16 *v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // r14d
  wchar_t *v11; // rax
  _QWORD *v12; // r9
  const wchar_t *v13; // rax
  const wchar_t *v14; // rcx
  const wchar_t *v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rax
  const wchar_t *v18; // r8
  __int64 v19; // rax
  HKEY hKey; // [rsp+30h] [rbp-168h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+38h] [rbp-160h]
  void **pExceptionObject; // [rsp+40h] [rbp-158h] BYREF
  char v23; // [rsp+48h] [rbp-150h]
  const char *v24; // [rsp+50h] [rbp-148h]
  __int64 v25; // [rsp+58h] [rbp-140h]
  __int64 v26; // [rsp+60h] [rbp-138h]
  unsigned int v27; // [rsp+68h] [rbp-130h]
  int v28; // [rsp+6Ch] [rbp-12Ch]
  int v29; // [rsp+70h] [rbp-128h]
  void **v30; // [rsp+78h] [rbp-120h] BYREF
  char v31; // [rsp+80h] [rbp-118h]
  const char *v32; // [rsp+88h] [rbp-110h]
  __int64 v33; // [rsp+90h] [rbp-108h]
  __int64 v34; // [rsp+98h] [rbp-100h]
  unsigned int v35; // [rsp+A0h] [rbp-F8h]
  int v36; // [rsp+A4h] [rbp-F4h]
  int v37; // [rsp+A8h] [rbp-F0h]
  char *v38; // [rsp+B0h] [rbp-E8h]
  LPCWSTR lpSubKey[4]; // [rsp+B8h] [rbp-E0h] BYREF
  _QWORD v40[5]; // [rsp+D8h] [rbp-C0h] BYREF
  const wchar_t *v41; // [rsp+100h] [rbp-98h] BYREF
  int v42; // [rsp+108h] [rbp-90h]
  int v43; // [rsp+10Ch] [rbp-8Ch]
  const wchar_t *v44; // [rsp+110h] [rbp-88h]
  int v45; // [rsp+118h] [rbp-80h]
  int v46; // [rsp+11Ch] [rbp-7Ch]
  char *v47; // [rsp+120h] [rbp-78h]
  __int64 v48; // [rsp+128h] [rbp-70h]
  const wchar_t *v49; // [rsp+130h] [rbp-68h]
  int v50; // [rsp+138h] [rbp-60h]
  int v51; // [rsp+13Ch] [rbp-5Ch]
  wchar_t Buffer[28]; // [rsp+140h] [rbp-58h] BYREF

  if ( a1 )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
    v21 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
    v38 = a1 + 16;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
    hKey = 0;
    if ( *((_QWORD *)a1 + 30) && !*((_DWORD *)a1 + 14) )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        std::wstring::wstring(
          (__int64)lpSubKey,
          (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
        std::wstring::wstring(
          (__int64)v40,
          (__int64)L"wecsvc auto-cleanup: the inactive state of the EventSource stands longer than the Interval (min): ");
        std::wstring::append((__int64)lpSubKey, (__int64)L"\\Subscriptions\\");
        v3 = (_QWORD *)(*((_QWORD *)a1 + 8) + 56LL);
        if ( *(_QWORD *)(*((_QWORD *)a1 + 8) + 80LL) >= 8u )
          v3 = (_QWORD *)*v3;
        std::wstring::append((__int64)lpSubKey, (__int64)v3);
        std::wstring::append((__int64)lpSubKey, (__int64)L"\\EventSources\\");
        v4 = (const WCHAR *)lpSubKey;
        if ( lpSubKey[3] >= (LPCWSTR)8 )
          v4 = lpSubKey[0];
        v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x2001Fu, &hKey);
        v6 = v5;
        if ( v5 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v5);
          }
          v23 = 0;
          v24 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
          v25 = 0;
          v26 = 0;
          v27 = v6;
          v28 = -1;
          v29 = 1716;
          pExceptionObject = &wmi::GenericException::`vftable';
          throw (wmi::GenericException *)&pExceptionObject;
        }
        v7 = (const unsigned __int16 **)(a1 + 72);
        if ( *((_QWORD *)a1 + 12) < 8u )
          v8 = (const unsigned __int16 *)(a1 + 72);
        else
          v8 = *v7;
        v9 = RegDeleteKeyRecursive(hKey, v8);
        v10 = v9;
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v9);
          }
          v31 = 0;
          v32 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
          v33 = 0;
          v34 = 0;
          v35 = v10;
          v36 = -1;
          v37 = 1722;
          v30 = &wmi::GenericException::`vftable';
          throw (wmi::GenericException *)&v30;
        }
        v11 = _ltow(*((_DWORD *)a1 + 70), Buffer, 10);
        std::wstring::append((__int64)v40, (__int64)v11);
        v12 = (_QWORD *)*((_QWORD *)a1 + 8);
        v13 = (const wchar_t *)(v12 + 7);
        if ( v12[10] >= 8u )
          v13 = *(const wchar_t **)v13;
        v14 = &word_180026AD8;
        v15 = &word_180026AD8;
        if ( v13 )
          v15 = v13;
        v16 = -1;
        v17 = -1;
        do
          ++v17;
        while ( v15[v17] );
        v41 = v15;
        v42 = 2 * v17 + 2;
        v43 = 0;
        if ( *((_QWORD *)a1 + 12) >= 8u )
          v7 = (const unsigned __int16 **)*v7;
        v18 = &word_180026AD8;
        if ( v7 )
          v18 = (const wchar_t *)v7;
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v44 = v18;
        v45 = 2 * v19 + 2;
        v46 = 0;
        v47 = a1 + 180;
        v48 = 4;
        if ( v40[3] < 8u )
        {
          v14 = (const wchar_t *)v40;
        }
        else if ( v40[0] )
        {
          v14 = (const wchar_t *)v40[0];
        }
        do
          ++v16;
        while ( v14[v16] );
        v49 = v14;
        v50 = 2 * v16 + 2;
        v51 = 0;
        (*(void (__fastcall **)(_QWORD, __int64 *, __int64, const wchar_t **))(**(_QWORD **)(v12[13] + 136LL) + 8LL))(
          *(_QWORD *)(v12[13] + 136LL),
          EVTCOLL_EVENT_SOURCE_INACTIVE_CLEANUP,
          4,
          &v41);
        std::wstring::_Tidy(v40, 1, 0);
        std::wstring::_Tidy(lpSubKey, 1, 0);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', 0) )
        {
          v2 = v21;
          __eh34_try_continuation(0, &wmi::Exception `RTTI Type Descriptor', &loc_18000B6DB);
        }
      }
      RegCloseKey(hKey);
    }
    LeaveCriticalSection(v2);
  }
}

```

## disassembly

```asm
0x18000b300  test    rcx, rcx
0x18000b303  jz      locret_18000B71D
0x18000b309  mov     [rsp+arg_8], rbx
0x18000b30e  mov     [rsp+arg_10], rsi
0x18000b313  push    rdi
0x18000b314  push    r14
0x18000b316  push    r15
0x18000b318  sub     rsp, 180h
0x18000b31f  mov     rax, cs:__security_cookie
0x18000b326  xor     rax, rsp
0x18000b329  mov     [rsp+198h+var_20], rax
0x18000b331  mov     rbx, rcx
0x18000b334  xor     r15d, r15d
0x18000b337  lea     rsi, [rcx+10h]
0x18000b33b  mov     [rsp+198h+var_160], rsi
0x18000b340  mov     [rsp+198h+var_E8], rsi
0x18000b348  mov     rcx, rsi; lpCriticalSection
0x18000b34b  call    cs:__imp_EnterCriticalSection
0x18000b351  nop
0x18000b352  mov     [rsp+198h+hKey], r15
0x18000b357  cmp     [rbx+0F0h], r15
0x18000b35e  jz      loc_18000B6EC
0x18000b364  cmp     [rbx+38h], r15d
0x18000b368  jnz     loc_18000B6EC
0x18000b36e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000b375  lea     rcx, [rsp+198h+lpSubKey]
0x18000b37d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000b382  nop
0x18000b383  lea     rdx, aWecsvcAutoClea; "wecsvc auto-cleanup: the inactive state"...
0x18000b38a  lea     rcx, [rsp+198h+var_C0]
0x18000b392  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000b397  nop
0x18000b398  lea     rdx, aSubscriptions_1; "\\Subscriptions\\"
0x18000b39f  lea     rcx, [rsp+198h+lpSubKey]
0x18000b3a7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000b3ac  mov     rdx, [rbx+40h]
0x18000b3b0  add     rdx, 38h ; '8'
0x18000b3b4  cmp     qword ptr [rdx+18h], 8
0x18000b3b9  jb      short loc_18000B3BE
0x18000b3bb  mov     rdx, [rdx]
0x18000b3be  lea     rcx, [rsp+198h+lpSubKey]
0x18000b3c6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000b3cb  lea     rdx, aEventsources_0; "\\EventSources\\"
0x18000b3d2  lea     rcx, [rsp+198h+lpSubKey]
0x18000b3da  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000b3df  lea     rdx, [rsp+198h+lpSubKey]
0x18000b3e7  cmp     [rsp+198h+var_C8], 8
0x18000b3f0  cmovnb  rdx, [rsp+198h+lpSubKey]; lpSubKey
0x18000b3f9  lea     rax, [rsp+198h+hKey]
0x18000b3fe  mov     [rsp+198h+phkResult], rax; phkResult
0x18000b403  mov     r9d, 2001Fh; samDesired
0x18000b409  xor     r8d, r8d; ulOptions
0x18000b40c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b413  call    cs:__imp_RegOpenKeyExW
0x18000b419  mov     edi, eax
0x18000b41b  test    eax, eax
0x18000b41d  jz      loc_18000B4A6
0x18000b423  lea     rdx, WPP_GLOBAL_Control
0x18000b42a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b431  cmp     rcx, rdx
0x18000b434  jz      short loc_18000B45A
0x18000b436  test    byte ptr [rcx+1Ch], 10h
0x18000b43a  jz      short loc_18000B45A
0x18000b43c  cmp     byte ptr [rcx+19h], 2
0x18000b440  jb      short loc_18000B45A
0x18000b442  mov     edx, 2Ch ; ','
0x18000b447  mov     r9d, eax
0x18000b44a  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000b451  mov     rcx, [rcx+10h]
0x18000b455  call    WPP_SF_D
0x18000b45a  mov     [rsp+198h+var_150], r15b
0x18000b45f  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000b466  mov     [rsp+198h+var_148], rax
0x18000b46b  mov     [rsp+198h+var_140], r15
0x18000b470  mov     [rsp+198h+var_138], r15
0x18000b475  mov     [rsp+198h+var_130], edi
0x18000b479  mov     [rsp+198h+var_12C], 0FFFFFFFFh
0x18000b481  mov     [rsp+198h+var_128], 6B4h
0x18000b489  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000b490  mov     [rsp+198h+pExceptionObject], rax
0x18000b495  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b49c  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x18000b4a1  call    _CxxThrowException_0
0x18000b4a6  lea     rdi, [rbx+48h]
0x18000b4aa  cmp     qword ptr [rdi+18h], 8
0x18000b4af  jb      short loc_18000B4B6
0x18000b4b1  mov     rdx, [rdi]
0x18000b4b4  jmp     short loc_18000B4B9
0x18000b4b6  mov     rdx, rdi; unsigned __int16 *
0x18000b4b9  mov     rcx, [rsp+198h+hKey]; HKEY
0x18000b4be  call    ?RegDeleteKeyRecursive@@YAKPEAUHKEY__@@PEBG@Z; RegDeleteKeyRecursive(HKEY__ *,ushort const *)
0x18000b4c3  mov     r14d, eax
0x18000b4c6  test    eax, eax
0x18000b4c8  jz      loc_18000B567
0x18000b4ce  lea     rdx, WPP_GLOBAL_Control
0x18000b4d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4dc  cmp     rcx, rdx
0x18000b4df  jz      short loc_18000B505
0x18000b4e1  test    byte ptr [rcx+1Ch], 10h
0x18000b4e5  jz      short loc_18000B505
0x18000b4e7  cmp     byte ptr [rcx+19h], 2
0x18000b4eb  jb      short loc_18000B505
0x18000b4ed  mov     edx, 2Dh ; '-'
0x18000b4f2  mov     r9d, eax
0x18000b4f5  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000b4fc  mov     rcx, [rcx+10h]
0x18000b500  call    WPP_SF_D
0x18000b505  mov     [rsp+198h+var_118], r15b
0x18000b50d  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000b514  mov     [rsp+198h+var_110], rax
0x18000b51c  mov     [rsp+198h+var_108], r15
0x18000b524  mov     [rsp+198h+var_100], r15
0x18000b52c  mov     [rsp+198h+var_F8], r14d
0x18000b534  mov     [rsp+198h+var_F4], 0FFFFFFFFh
0x18000b53f  mov     [rsp+198h+var_F0], 6BAh
0x18000b54a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000b551  mov     [rsp+198h+var_120], rax
0x18000b556  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b55d  lea     rcx, [rsp+198h+var_120]; pExceptionObject
0x18000b562  call    _CxxThrowException_0
0x18000b567  mov     r8d, 0Ah; Radix
0x18000b56d  lea     rdx, [rsp+198h+Buffer]; Buffer
0x18000b575  mov     ecx, [rbx+118h]; Value
0x18000b57b  call    cs:__imp__ltow
0x18000b581  mov     rdx, rax
0x18000b584  lea     rcx, [rsp+198h+var_C0]
0x18000b58c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000b591  mov     r9, [rbx+40h]
0x18000b595  lea     rax, [r9+38h]
0x18000b599  cmp     qword ptr [rax+18h], 8
0x18000b59e  jb      short loc_18000B5A3
0x18000b5a0  mov     rax, [rax]
0x18000b5a3  lea     rcx, word_180026AD8
0x18000b5aa  mov     r8, rcx
0x18000b5ad  test    rax, rax
0x18000b5b0  cmovnz  r8, rax
0x18000b5b4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b5b8  mov     rax, rdx
0x18000b5bb  inc     rax
0x18000b5be  cmp     [r8+rax*2], r15w
0x18000b5c3  jnz     short loc_18000B5BB
0x18000b5c5  mov     [rsp+198h+var_98], r8
0x18000b5cd  lea     eax, ds:2[rax*2]
0x18000b5d4  mov     [rsp+198h+var_90], eax
0x18000b5db  mov     [rsp+198h+var_8C], r15d
0x18000b5e3  cmp     qword ptr [rdi+18h], 8
0x18000b5e8  jb      short loc_18000B5ED
0x18000b5ea  mov     rdi, [rdi]
0x18000b5ed  mov     r8, rcx
0x18000b5f0  test    rdi, rdi
0x18000b5f3  cmovnz  r8, rdi
0x18000b5f7  mov     rax, rdx
0x18000b5fa  inc     rax
0x18000b5fd  cmp     [r8+rax*2], r15w
0x18000b602  jnz     short loc_18000B5FA
0x18000b604  mov     [rsp+198h+var_88], r8
0x18000b60c  lea     eax, ds:2[rax*2]
0x18000b613  mov     [rsp+198h+var_80], eax
0x18000b61a  mov     [rsp+198h+var_7C], r15d
0x18000b622  lea     rax, [rbx+0B4h]
0x18000b629  mov     [rsp+198h+var_78], rax
0x18000b631  mov     r8d, 4
0x18000b637  mov     [rsp+198h+var_70], r8
0x18000b63f  cmp     [rsp+198h+var_A8], 8
0x18000b648  jb      short loc_18000B65C
0x18000b64a  mov     rax, [rsp+198h+var_C0]
0x18000b652  test    rax, rax
0x18000b655  jz      short loc_18000B664
0x18000b657  mov     rcx, rax
0x18000b65a  jmp     short loc_18000B664
0x18000b65c  lea     rcx, [rsp+198h+var_C0]
0x18000b664  inc     rdx
0x18000b667  cmp     [rcx+rdx*2], r15w
0x18000b66c  jnz     short loc_18000B664
0x18000b66e  mov     [rsp+198h+var_68], rcx
0x18000b676  lea     eax, ds:2[rdx*2]
0x18000b67d  mov     [rsp+198h+var_60], eax
0x18000b684  mov     [rsp+198h+var_5C], r15d
0x18000b68c  mov     rax, [r9+68h]
0x18000b690  mov     rcx, [rax+88h]
0x18000b697  mov     rax, [rcx]
0x18000b69a  lea     r9, [rsp+198h+var_98]
0x18000b6a2  lea     rdx, EVTCOLL_EVENT_SOURCE_INACTIVE_CLEANUP
0x18000b6a9  mov     rax, [rax+8]
0x18000b6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6b2  nop
0x18000b6b3  xor     r8d, r8d
0x18000b6b6  mov     dl, 1
0x18000b6b8  lea     rcx, [rsp+198h+var_C0]
0x18000b6c0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000b6c5  nop
0x18000b6c6  xor     r8d, r8d
0x18000b6c9  mov     dl, 1
0x18000b6cb  lea     rcx, [rsp+198h+lpSubKey]
0x18000b6d3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000b6d8  nop
0x18000b6d9  jmp     short loc_18000B6E0
0x18000b6db  mov     rsi, [rsp+198h+var_160]
0x18000b6e0  mov     rcx, [rsp+198h+hKey]; hKey
0x18000b6e5  call    cs:__imp_RegCloseKey
0x18000b6eb  nop
0x18000b6ec  mov     rcx, rsi; lpCriticalSection
0x18000b6ef  call    cs:__imp_LeaveCriticalSection
0x18000b6f5  mov     rcx, [rsp+198h+var_20]
0x18000b6fd  xor     rcx, rsp; StackCookie
0x18000b700  call    __security_check_cookie
0x18000b705  lea     r11, [rsp+198h+var_18]
0x18000b70d  mov     rbx, [r11+28h]
0x18000b711  mov     rsi, [r11+30h]
0x18000b715  mov     rsp, r11
0x18000b718  pop     r15
0x18000b71a  pop     r14
0x18000b71c  pop     rdi
0x18000b71d  retn
```
