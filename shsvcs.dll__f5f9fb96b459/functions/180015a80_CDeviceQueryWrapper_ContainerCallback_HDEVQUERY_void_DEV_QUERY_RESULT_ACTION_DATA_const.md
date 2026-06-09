# CDeviceQueryWrapper::ContainerCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x180015a80`
- end: `0x180015f47`
- name: `?ContainerCallback@CDeviceQueryWrapper@@SAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `1223`
- prototype: `void __fastcall(struct HDEVQUERY__ *, void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180015a80`
- `0x180018bc4`
- `0x18001bc64`
- `0x18001bcd4`
- `0x18002b518`
- `0x18002f7b4`
- `0x18002f864`
- `0x18002fa6c`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015dc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015e58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015da1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015da1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015e20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015eed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015f18`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180015b04`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180015b04`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180015ce4`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180015ce4`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180015dab`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180015ef6`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180015dab`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180015ef6`

## pseudocode

```c
void __fastcall CDeviceQueryWrapper::ContainerCallback(
        struct HDEVQUERY__ *a1,
        void *a2,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a3)
{
  const wchar_t *v4; // rsi
  const wchar_t *v5; // r9
  const OLECHAR *v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  __int64 v8; // r8
  __int64 i; // rdx
  __int64 v10; // rax
  const wchar_t *v11; // r9
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  __int64 v16; // r14
  int v17; // r8d
  __int64 v18; // r15
  struct _RTL_CRITICAL_SECTION *v19; // rcx
  __int64 v20; // [rsp+50h] [rbp-29h] BYREF
  __int64 v21; // [rsp+58h] [rbp-21h] BYREF
  DEVPROPKEY v22; // [rsp+60h] [rbp-19h]
  int v23; // [rsp+74h] [rbp-5h]
  __int64 v24; // [rsp+78h] [rbp-1h]
  int v25; // [rsp+80h] [rbp+7h]
  int v26; // [rsp+84h] [rbp+Bh]
  GUID *p_pclsid; // [rsp+88h] [rbp+Fh]
  GUID pclsid; // [rsp+90h] [rbp+17h] BYREF

  v4 = L"Unknown";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v5 = L"Unknown";
    if ( *((_QWORD *)a3 + 2) )
      v5 = (const wchar_t *)*((_QWORD *)a3 + 2);
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d2608f05d7e63dcd545f1264c7f6746f_Traceguids, v5);
  }
  if ( *(_DWORD *)a3 )
  {
    v6 = (const OLECHAR *)*((_QWORD *)a3 + 2);
    pclsid = 0;
    if ( CLSIDFromString(v6, &pclsid) >= 0 )
    {
      if ( *(_DWORD *)a3 == 1 )
      {
        if ( dword_18003FCCC > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                           + (unsigned int)tls_index)
                                         + 4LL) )
        {
          Init_thread_header(&dword_18003FCCC);
          if ( dword_18003FCCC == -1 )
          {
            *(DEVPROPKEY *)byte_18003FAA0 = DEVPKEY_Device_ContainerId;
            *(DEVPROPKEY *)byte_18003FAC0 = DEVPKEY_DeviceInterface_ClassGuid;
            dword_18003FAB4 = 0;
            qword_18003FAB8 = 0;
            *(DEVPROPKEY *)byte_18003FAE0 = DEVPKEY_DeviceInterface_Enabled;
            dword_18003FAD4 = 0;
            qword_18003FAD8 = 0;
            dword_18003FAF4 = 0;
            qword_18003FAF8 = 0;
            Init_thread_footer(&dword_18003FCCC);
          }
        }
        v22 = DEVPKEY_Device_ContainerId;
        v21 = 2;
        v23 = 0;
        v7 = (struct _RTL_CRITICAL_SECTION *)(qword_18003FB80 + 176);
        v24 = 0;
        if ( qword_18003FB80 == -168 )
          v7 = 0;
        v25 = 13;
        v26 = 16;
        p_pclsid = &pclsid;
        v20 = 0;
        EnterCriticalSection(v7);
        v8 = *(_QWORD *)(qword_18003FB80 + 96);
        if ( v8 )
        {
          for ( i = *(_QWORD *)(v8
                              + 8
                              * ((*(unsigned int *)&pclsid.Data4[4]
                                ^ (unsigned __int64)(*(_DWORD *)pclsid.Data4 ^ *(_DWORD *)&pclsid.Data2 ^ pclsid.Data1))
                               % *(unsigned int *)(qword_18003FB80 + 112))); i; i = *(_QWORD *)(i + 24) )
          {
            if ( *(_DWORD *)(i + 32) == (*(_DWORD *)&pclsid.Data4[4]
                                       ^ *(_DWORD *)pclsid.Data4
                                       ^ *(_DWORD *)&pclsid.Data2
                                       ^ pclsid.Data1) )
            {
              v10 = *(_QWORD *)i - *(_QWORD *)&pclsid.Data1;
              if ( *(_QWORD *)i == *(_QWORD *)&pclsid.Data1 )
                v10 = *(_QWORD *)(i + 8) - *(_QWORD *)pclsid.Data4;
              if ( !v10 )
              {
                v20 = *(_QWORD *)(i + 16);
                goto LABEL_49;
              }
            }
          }
        }
        if ( (int)DevCreateObjectQuery(
                    1,
                    1,
                    3,
                    byte_18003FAA0,
                    1,
                    &v21,
                    CDeviceQueryWrapper::InterfaceCallbackEnabledDisabled,
                    0,
                    &v20) < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( *((_QWORD *)a3 + 2) )
              v4 = (const wchar_t *)*((_QWORD *)a3 + 2);
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_d2608f05d7e63dcd545f1264c7f6746f_Traceguids, v4);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v11 = L"Unknown";
            if ( *((_QWORD *)a3 + 2) )
              v11 = (const wchar_t *)*((_QWORD *)a3 + 2);
            WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v20, (_DWORD)v11, v20);
          }
          if ( !ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::SetAt(
                  qword_18003FB80 + 96,
                  &pclsid,
                  &v20) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              if ( *((_QWORD *)a3 + 2) )
                v4 = (const wchar_t *)*((_QWORD *)a3 + 2);
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d2608f05d7e63dcd545f1264c7f6746f_Traceguids, v4);
            }
            v12 = (struct _RTL_CRITICAL_SECTION *)(qword_18003FB80 + 176);
            if ( qword_18003FB80 == -168 )
              v12 = 0;
            LeaveCriticalSection(v12);
            DevCloseObjectQuery(v20);
            v13 = (struct _RTL_CRITICAL_SECTION *)(qword_18003FB80 + 176);
            if ( qword_18003FB80 == -168 )
              v13 = 0;
            EnterCriticalSection(v13);
          }
        }
LABEL_49:
        v14 = (struct _RTL_CRITICAL_SECTION *)(qword_18003FB80 + 176);
        if ( qword_18003FB80 == -168 )
          v14 = 0;
        goto LABEL_67;
      }
      if ( *(_DWORD *)a3 != 3 )
        return;
      v20 = 0;
      v15 = (struct _RTL_CRITICAL_SECTION *)(qword_18003FB80 + 176);
      if ( qword_18003FB80 == -168 )
        v15 = 0;
      EnterCriticalSection(v15);
      v16 = qword_18003FB80;
      if ( !(unsigned __int8)ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::Lookup(
                               qword_18003FB80 + 96,
                               &pclsid,
                               &v20) )
      {
        v14 = (struct _RTL_CRITICAL_SECTION *)(v16 + 176);
        if ( v16 == -168 )
          v14 = 0;
LABEL_67:
        LeaveCriticalSection(v14);
        return;
      }
      v18 = v20;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        if ( *((_QWORD *)a3 + 2) )
          LODWORD(v4) = *((_QWORD *)a3 + 2);
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v17, (_DWORD)v4, v20);
        v16 = qword_18003FB80;
      }
      ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::RemoveKey(
        v16 + 96,
        &pclsid);
      v19 = (struct _RTL_CRITICAL_SECTION *)(qword_18003FB80 + 176);
      if ( qword_18003FB80 == -168 )
        v19 = 0;
      LeaveCriticalSection(v19);
      DevCloseObjectQuery(v18);
    }
  }
}

```

## disassembly

```asm
0x180015a80  push    rbp
0x180015a82  push    rbx
0x180015a83  push    rsi
0x180015a84  push    r12
0x180015a86  lea     rbp, [rsp-3Fh]
0x180015a8b  sub     rsp, 0B8h
0x180015a92  mov     rax, cs:__security_cookie
0x180015a99  xor     rax, rsp
0x180015a9c  mov     [rbp+57h+var_30], rax
0x180015aa0  mov     rbx, r8
0x180015aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180015aaa  lea     r12, WPP_GLOBAL_Control
0x180015ab1  lea     rsi, aUnknown; "Unknown"
0x180015ab8  cmp     rcx, r12
0x180015abb  jz      short loc_180015AEC
0x180015abd  test    byte ptr [rcx+1Ch], 1
0x180015ac1  jz      short loc_180015AEC
0x180015ac3  cmp     byte ptr [rcx+19h], 4
0x180015ac7  jb      short loc_180015AEC
0x180015ac9  mov     rax, [r8+10h]
0x180015acd  mov     r9, rsi
0x180015ad0  mov     rcx, [rcx+10h]
0x180015ad4  lea     r8, WPP_d2608f05d7e63dcd545f1264c7f6746f_Traceguids
0x180015adb  test    rax, rax
0x180015ade  mov     edx, 0Dh
0x180015ae3  cmovnz  r9, rax
0x180015ae7  call    WPP_SF_S
0x180015aec  cmp     dword ptr [rbx], 0
0x180015aef  jz      loc_180015F2E
0x180015af5  mov     rcx, [rbx+10h]; lpsz
0x180015af9  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180015afd  xorps   xmm0, xmm0
0x180015b00  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180015b04  call    cs:__imp_CLSIDFromString
0x180015b0a  test    eax, eax
0x180015b0c  js      loc_180015F2E
0x180015b12  mov     eax, [rbx]
0x180015b14  mov     [rsp+0D0h+arg_0], rdi
0x180015b1c  cmp     eax, 1
0x180015b1f  jnz     loc_180015E2B
0x180015b25  mov     ecx, cs:_tls_index
0x180015b2b  xor     edi, edi
0x180015b2d  mov     rax, gs:58h
0x180015b36  mov     edx, 4
0x180015b3b  mov     rax, [rax+rcx*8]
0x180015b3f  mov     eax, [rdx+rax]
0x180015b42  cmp     cs:dword_18003FCCC, eax
0x180015b48  jle     loc_180015BE8
0x180015b4e  lea     rcx, dword_18003FCCC
0x180015b55  call    _Init_thread_header
0x180015b5a  cmp     cs:dword_18003FCCC, 0FFFFFFFFh
0x180015b61  jnz     loc_180015BE8
0x180015b67  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180015b6e  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180015b74  lea     rcx, dword_18003FCCC
0x180015b7b  mov     dword ptr cs:byte_18003FAA0+10h, eax
0x180015b81  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180015b87  movaps  xmmword ptr cs:byte_18003FAA0, xmm0
0x180015b8e  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180015b95  mov     dword ptr cs:byte_18003FAC0+10h, eax
0x180015b9b  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180015ba1  movaps  xmmword ptr cs:byte_18003FAC0, xmm0
0x180015ba8  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x180015baf  mov     cs:dword_18003FAB4, edi
0x180015bb5  mov     cs:qword_18003FAB8, rdi
0x180015bbc  movaps  xmmword ptr cs:byte_18003FAE0, xmm0
0x180015bc3  mov     cs:dword_18003FAD4, edi
0x180015bc9  mov     cs:qword_18003FAD8, rdi
0x180015bd0  mov     dword ptr cs:byte_18003FAE0+10h, eax
0x180015bd6  mov     cs:dword_18003FAF4, edi
0x180015bdc  mov     cs:qword_18003FAF8, rdi
0x180015be3  call    _Init_thread_footer
0x180015be8  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180015bee  mov     rcx, cs:qword_18003FB80
0x180015bf5  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180015bfc  add     rcx, 0A8h
0x180015c03  mov     [rbp+57h+var_60], eax
0x180015c06  lea     rax, [rbp+57h+pclsid]
0x180015c0a  mov     [rbp+57h+var_78], 2
0x180015c12  movups  [rbp+57h+var_70], xmm0
0x180015c16  mov     [rbp+57h+var_5C], edi
0x180015c19  lea     rcx, [rcx+8]
0x180015c1d  mov     [rbp+57h+var_58], rdi
0x180015c21  cmovz   rcx, rdi; lpCriticalSection
0x180015c25  mov     [rbp+57h+var_50], 0Dh
0x180015c2c  mov     [rbp+57h+var_4C], 10h
0x180015c33  mov     [rbp+57h+var_48], rax
0x180015c37  mov     [rbp+57h+var_80], rdi
0x180015c3b  call    cs:__imp_EnterCriticalSection
0x180015c41  mov     rcx, cs:qword_18003FB80
0x180015c48  mov     r8, [rcx+60h]
0x180015c4c  test    r8, r8
0x180015c4f  jz      short loc_180015CA5
0x180015c51  mov     r9, qword ptr [rbp+57h+pclsid.Data1]
0x180015c55  xor     edx, edx
0x180015c57  mov     r10, qword ptr [rbp+57h+pclsid.Data4]
0x180015c5b  mov     r11d, r9d
0x180015c5e  xor     r11d, dword ptr [rbp+57h+pclsid.Data2]
0x180015c62  xor     r11d, r10d
0x180015c65  xor     r11d, dword ptr [rbp+57h+pclsid.Data4+4]
0x180015c69  mov     eax, r11d
0x180015c6c  div     dword ptr [rcx+70h]
0x180015c6f  mov     rdx, [r8+rdx*8]
0x180015c73  test    rdx, rdx
0x180015c76  jz      short loc_180015CA5
0x180015c78  cmp     [rdx+20h], r11d
0x180015c7c  jnz     short loc_180015C92
0x180015c7e  mov     rax, [rdx]
0x180015c81  sub     rax, r9
0x180015c84  jnz     short loc_180015C8D
0x180015c86  mov     rax, [rdx+8]
0x180015c8a  sub     rax, r10
0x180015c8d  test    rax, rax
0x180015c90  jz      short loc_180015C98
0x180015c92  mov     rdx, [rdx+18h]
0x180015c96  jmp     short loc_180015C73
0x180015c98  mov     rax, [rdx+10h]
0x180015c9c  mov     [rbp+57h+var_80], rax
0x180015ca0  jmp     loc_180015E0A
0x180015ca5  lea     rax, [rbp+57h+var_80]
0x180015ca9  mov     edx, 1
0x180015cae  mov     [rsp+0D0h+var_90], rax
0x180015cb3  lea     r9, byte_18003FAA0
0x180015cba  mov     [rsp+0D0h+var_98], rdi
0x180015cbf  lea     rax, ?InterfaceCallbackEnabledDisabled@CDeviceQueryWrapper@@SAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CDeviceQueryWrapper::InterfaceCallbackEnabledDisabled(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180015cc6  mov     [rsp+0D0h+var_A0], rax
0x180015ccb  mov     ecx, edx
0x180015ccd  lea     rax, [rbp+57h+var_78]
0x180015cd1  mov     r8d, 3
0x180015cd7  mov     [rsp+0D0h+var_A8], rax
0x180015cdc  mov     [rsp+0D0h+var_B0], 1
0x180015ce4  call    cs:__imp_DevCreateObjectQuery
0x180015cea  test    eax, eax
0x180015cec  js      loc_180015DCF
0x180015cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cf9  cmp     rcx, r12
0x180015cfc  jz      short loc_180015D2F
0x180015cfe  test    byte ptr [rcx+1Ch], 1
0x180015d02  jz      short loc_180015D2F
0x180015d04  cmp     byte ptr [rcx+19h], 4
0x180015d08  jb      short loc_180015D2F
0x180015d0a  mov     rax, [rbx+10h]
0x180015d0e  mov     r9, rsi
0x180015d11  mov     r8d, dword ptr [rbp+57h+var_80]
0x180015d15  test    rax, rax
0x180015d18  mov     rcx, [rcx+10h]
0x180015d1c  mov     edx, 0Eh
0x180015d21  cmovnz  r9, rax
0x180015d25  mov     [rsp+0D0h+var_B0], r8d
0x180015d2a  call    WPP_SF_Sd
0x180015d2f  mov     rcx, cs:qword_18003FB80
0x180015d36  lea     r8, [rbp+57h+var_80]
0x180015d3a  add     rcx, 60h ; '`'
0x180015d3e  lea     rdx, [rbp+57h+pclsid]
0x180015d42  call    ?SetAt@?$CAtlMap@U_GUID@@PEAUHDEVQUERY__@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAUHDEVQUERY__@@@4@@ATL@@QEAAPEAU__POSITION@@AEBU_GUID@@AEBQEAUHDEVQUERY__@@@Z; ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::SetAt(_GUID const &,HDEVQUERY__ * const &)
0x180015d47  test    rax, rax
0x180015d4a  jnz     loc_180015E0A
0x180015d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d57  cmp     rcx, r12
0x180015d5a  jz      short loc_180015D8B
0x180015d5c  test    byte ptr [rcx+1Ch], 1
0x180015d60  jz      short loc_180015D8B
0x180015d62  cmp     byte ptr [rcx+19h], 2
0x180015d66  jb      short loc_180015D8B
0x180015d68  mov     rax, [rbx+10h]
0x180015d6c  lea     r8, WPP_d2608f05d7e63dcd545f1264c7f6746f_Traceguids
0x180015d73  mov     rcx, [rcx+10h]
0x180015d77  test    rax, rax
0x180015d7a  mov     edx, 0Fh
0x180015d7f  cmovnz  rsi, rax
0x180015d83  mov     r9, rsi
0x180015d86  call    WPP_SF_S
0x180015d8b  mov     rcx, cs:qword_18003FB80
0x180015d92  add     rcx, 0A8h
0x180015d99  lea     rcx, [rcx+8]
0x180015d9d  cmovz   rcx, rdi; lpCriticalSection
0x180015da1  call    cs:__imp_LeaveCriticalSection
0x180015da7  mov     rcx, [rbp+57h+var_80]
0x180015dab  call    cs:__imp_DevCloseObjectQuery
0x180015db1  mov     rcx, cs:qword_18003FB80
0x180015db8  add     rcx, 0A8h
0x180015dbf  lea     rcx, [rcx+8]
0x180015dc3  cmovz   rcx, rdi; lpCriticalSection
0x180015dc7  call    cs:__imp_EnterCriticalSection
0x180015dcd  jmp     short loc_180015E0A
0x180015dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dd6  cmp     rcx, r12
0x180015dd9  jz      short loc_180015E0A
0x180015ddb  test    byte ptr [rcx+1Ch], 1
0x180015ddf  jz      short loc_180015E0A
0x180015de1  cmp     byte ptr [rcx+19h], 2
0x180015de5  jb      short loc_180015E0A
0x180015de7  mov     rax, [rbx+10h]
0x180015deb  lea     r8, WPP_d2608f05d7e63dcd545f1264c7f6746f_Traceguids
0x180015df2  mov     rcx, [rcx+10h]
0x180015df6  test    rax, rax
0x180015df9  mov     edx, 10h
0x180015dfe  cmovnz  rsi, rax
0x180015e02  mov     r9, rsi
0x180015e05  call    WPP_SF_S
0x180015e0a  mov     rcx, cs:qword_18003FB80
0x180015e11  add     rcx, 0A8h
0x180015e18  lea     rcx, [rcx+8]
0x180015e1c  cmovz   rcx, rdi; lpCriticalSection
0x180015e20  call    cs:__imp_LeaveCriticalSection
0x180015e26  jmp     loc_180015F26
0x180015e2b  cmp     eax, 3
0x180015e2e  jnz     loc_180015F26
0x180015e34  mov     rcx, cs:qword_18003FB80
0x180015e3b  xor     edi, edi
0x180015e3d  add     rcx, 0A8h
0x180015e44  mov     [rsp+0D0h+arg_8], r14
0x180015e4c  mov     [rbp+57h+var_80], rdi
0x180015e50  lea     rcx, [rcx+8]
0x180015e54  cmovz   rcx, rdi; lpCriticalSection
0x180015e58  call    cs:__imp_EnterCriticalSection
0x180015e5e  mov     r14, cs:qword_18003FB80
0x180015e65  lea     r8, [rbp+57h+var_80]
0x180015e69  lea     rdx, [rbp+57h+pclsid]
0x180015e6d  lea     rcx, [r14+60h]
0x180015e71  call    ?Lookup@?$CAtlMap@U_GUID@@PEAUHDEVQUERY__@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAUHDEVQUERY__@@@4@@ATL@@QEBA_NAEBU_GUID@@AEAPEAUHDEVQUERY__@@@Z; ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::Lookup(_GUID const &,HDEVQUERY__ * &)
0x180015e76  test    al, al
0x180015e78  jz      loc_180015F06
0x180015e7e  mov     [rsp+0D0h+var_20], r15
0x180015e86  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e8d  mov     r15, [rbp+57h+var_80]
0x180015e91  cmp     rcx, r12
0x180015e94  jz      short loc_180015ECA
0x180015e96  test    byte ptr [rcx+1Ch], 1
0x180015e9a  jz      short loc_180015ECA
0x180015e9c  cmp     byte ptr [rcx+19h], 4
0x180015ea0  jb      short loc_180015ECA
0x180015ea2  mov     rax, [rbx+10h]
0x180015ea6  mov     edx, 11h
0x180015eab  mov     rcx, [rcx+10h]
0x180015eaf  test    rax, rax
0x180015eb2  mov     [rsp+0D0h+var_B0], r15d
0x180015eb7  cmovnz  rsi, rax
0x180015ebb  mov     r9, rsi
0x180015ebe  call    WPP_SF_Sd
0x180015ec3  mov     r14, cs:qword_18003FB80
0x180015eca  lea     rcx, [r14+60h]
0x180015ece  lea     rdx, [rbp+57h+pclsid]
0x180015ed2  call    ?RemoveKey@?$CAtlMap@U_GUID@@PEAUHDEVQUERY__@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAUHDEVQUERY__@@@4@@ATL@@QEAA_NAEBU_GUID@@@Z; ATL::CAtlMap<_GUID,HDEVQUERY__ *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<HDEVQUERY__ *>>::RemoveKey(_GUID const &)
0x180015ed7  mov     rcx, cs:qword_18003FB80
0x180015ede  add     rcx, 0A8h
0x180015ee5  lea     rcx, [rcx+8]
0x180015ee9  cmovz   rcx, rdi; lpCriticalSection
0x180015eed  call    cs:__imp_LeaveCriticalSection
0x180015ef3  mov     rcx, r15
0x180015ef6  call    cs:__imp_DevCloseObjectQuery
0x180015efc  mov     r15, [rsp+0D0h+var_20]
0x180015f04  jmp     short loc_180015F1E
0x180015f06  lea     rax, [r14+0A8h]
0x180015f0d  test    rax, rax
0x180015f10  lea     rcx, [rax+8]
0x180015f14  cmovz   rcx, rdi; lpCriticalSection
0x180015f18  call    cs:__imp_LeaveCriticalSection
0x180015f1e  mov     r14, [rsp+0D0h+arg_8]
0x180015f26  mov     rdi, [rsp+0D0h+arg_0]
0x180015f2e  mov     rcx, [rbp+57h+var_30]
0x180015f32  xor     rcx, rsp; StackCookie
0x180015f35  call    __security_check_cookie
0x180015f3a  add     rsp, 0B8h
0x180015f41  pop     r12
0x180015f43  pop     rsi
0x180015f44  pop     rbx
0x180015f45  pop     rbp
0x180015f46  retn
```
