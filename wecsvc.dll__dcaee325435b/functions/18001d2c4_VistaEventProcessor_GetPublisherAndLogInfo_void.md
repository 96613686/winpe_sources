# VistaEventProcessor::GetPublisherAndLogInfo(void)

- ea: `0x18001d2c4`
- end: `0x18001d8a0`
- name: `?GetPublisherAndLogInfo@VistaEventProcessor@@AEAAXXZ`
- size: `1500`
- prototype: `void __fastcall(VistaEventProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c750`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x180006334`
- `0x18001cce8`
- `0x18001d0dc`
- `0x18001d2c4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001d68a`
- `msvcrt!_wcsicmp` at `0x18001d68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d30f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d30f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5bc`
- `wevtapi!EvtOpenPublisherMetadata` at `0x18001d2fd`
- `wevtapi!EvtOpenPublisherMetadata` at `0x18001d2fd`
- `wevtapi!EvtClose` at `0x18001d39c`
- `wevtapi!EvtGetObjectArraySize` at `0x18001d5ae`
- `wevtapi!EvtGetObjectArraySize` at `0x18001d5ae`

## pseudocode

```c
void __fastcall VistaEventProcessor::GetPublisherAndLogInfo(VistaEventProcessor *this)
{
  const WCHAR *v2; // rdx
  EVT_HANDLE v3; // rax
  void *v4; // rdi
  DWORD LastError; // ebx
  __int64 v6; // rax
  void *v7; // rsi
  DWORD v8; // ebx
  DWORD i; // edi
  const wchar_t *v10; // rdx
  void **pExceptionObject; // [rsp+30h] [rbp-59h] BYREF
  char v12; // [rsp+38h] [rbp-51h]
  const char *v13; // [rsp+40h] [rbp-49h]
  __int64 v14; // [rsp+48h] [rbp-41h]
  __int64 v15; // [rsp+50h] [rbp-39h]
  int v16; // [rsp+58h] [rbp-31h]
  int v17; // [rsp+5Ch] [rbp-2Dh]
  int v18; // [rsp+60h] [rbp-29h]
  __int128 v19; // [rsp+68h] [rbp-21h] BYREF
  __int64 v20; // [rsp+78h] [rbp-11h]
  _BYTE v21[8]; // [rsp+80h] [rbp-9h] BYREF
  BOOL (__stdcall *v22)(EVT_HANDLE); // [rsp+88h] [rbp-1h]
  void *v23; // [rsp+90h] [rbp+7h]
  _BYTE v24[8]; // [rsp+98h] [rbp+Fh] BYREF
  BOOL (__stdcall *v25)(EVT_HANDLE); // [rsp+A0h] [rbp+17h]
  EVT_HANDLE v26; // [rsp+A8h] [rbp+1Fh]
  DWORD ObjectArraySize; // [rsp+F0h] [rbp+67h] BYREF

  v2 = (const WCHAR *)((char *)this + 48);
  if ( *((_QWORD *)this + 9) >= 8u )
    v2 = *(const WCHAR **)v2;
  v3 = EvtOpenPublisherMetadata(0, v2, 0, 0x400u, 0);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, LastError);
    }
    v12 = 0;
    v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v14 = 0;
    v15 = 0;
    v16 = LastError;
    v17 = -1;
    v18 = 258;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v24[0] = 0;
  v25 = EvtClose;
  v26 = v3;
  v19 = 0;
  v20 = 0;
  VistaEventProcessor::GetEvtPublisherProperty(v3, EvtPublisherMetadataPublisherGuid);
  if ( MEMORY[0xC] != 15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 87);
    }
    v12 = 0;
    v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v14 = 0;
    v15 = 0;
    v16 = 87;
    v17 = -1;
    v18 = 270;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *(_OWORD *)((char *)this + 84) = *(_OWORD *)*(_QWORD *)v19;
  v6 = *(_QWORD *)((char *)this + 84) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)((char *)this + 92) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 87);
    }
    v12 = 0;
    v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v14 = 0;
    v15 = 0;
    v16 = 87;
    v17 = -1;
    v18 = 276;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  VistaEventProcessor::GetEvtPublisherProperty(v4, EvtPublisherMetadataChannelReferences);
  if ( *(_DWORD *)(v19 + 12) != 32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 4312);
    }
    v12 = 0;
    v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v14 = 0;
    v15 = 0;
    v16 = 4312;
    v17 = -1;
    v18 = 289;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v7 = *(void **)v19;
  v21[0] = 0;
  v22 = EvtClose;
  v23 = v7;
  ObjectArraySize = 0;
  if ( !EvtGetObjectArraySize(v7, &ObjectArraySize) )
  {
    v8 = GetLastError();
    if ( !v8 )
      v8 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, v8);
    }
    v12 = 0;
    v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v14 = 0;
    v15 = 0;
    v16 = v8;
    v17 = -1;
    v18 = 298;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  for ( i = 0; i < ObjectArraySize; ++i )
  {
    VistaEventProcessor::GetEvtArrayProperty(v7, 7u, i);
    if ( *(_DWORD *)(v19 + 12) != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 13);
      }
      v12 = 0;
      v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
      v14 = 0;
      v15 = 0;
      v16 = 13;
      v17 = -1;
      v18 = 310;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v10 = (const wchar_t *)((char *)this + 16);
    if ( *((_QWORD *)this + 5) >= 8u )
      v10 = *(const wchar_t **)v10;
    if ( !_wcsicmp(*(const wchar_t **)v19, v10) )
    {
      VistaEventProcessor::GetEvtArrayProperty(v7, 8u, i);
      if ( *(_DWORD *)(v19 + 12) != 8 || *(_DWORD *)v19 > 8u )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 13);
        }
        v12 = 0;
        v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
        v14 = 0;
        v15 = 0;
        v16 = 13;
        v17 = -1;
        v18 = 322;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::GenericException *)&pExceptionObject;
      }
      *((_QWORD *)this + 13) = 0x8000000000000000uLL >> *(_DWORD *)v19;
      VistaEventProcessor::GetEvtArrayProperty(v7, 9u, i);
      if ( *(_DWORD *)(v19 + 12) != 8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 13);
        }
        v12 = 0;
        v13 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
        v14 = 0;
        v15 = 0;
        v16 = 13;
        v17 = -1;
        v18 = 334;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::GenericException *)&pExceptionObject;
      }
      *((_DWORD *)this + 20) = *(_DWORD *)v19;
      break;
    }
  }
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v21);
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(&v19);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v24);
}

```

## disassembly

```asm
0x18001d2c4  push    rbp
0x18001d2c6  push    rbx
0x18001d2c7  push    rsi
0x18001d2c8  push    rdi
0x18001d2c9  push    r14
0x18001d2cb  push    r15
0x18001d2cd  lea     rbp, [rsp-2Fh]
0x18001d2d2  sub     rsp, 0B8h
0x18001d2d9  mov     rbx, rcx
0x18001d2dc  lea     rdx, [rcx+30h]
0x18001d2e0  cmp     qword ptr [rdx+18h], 8
0x18001d2e5  jb      short loc_18001D2EA
0x18001d2e7  mov     rdx, [rdx]; PublisherId
0x18001d2ea  xor     r15d, r15d
0x18001d2ed  mov     [rsp+0E0h+Flags], r15d; Flags
0x18001d2f2  mov     r9d, 400h; Locale
0x18001d2f8  xor     r8d, r8d; LogFilePath
0x18001d2fb  xor     ecx, ecx; Session
0x18001d2fd  call    cs:__imp_EvtOpenPublisherMetadata
0x18001d303  mov     rdi, rax
0x18001d306  test    rax, rax
0x18001d309  jnz     loc_18001D39C
0x18001d30f  call    cs:__imp_GetLastError
0x18001d315  mov     ebx, eax
0x18001d317  mov     eax, 507h
0x18001d31c  test    ebx, ebx
0x18001d31e  cmovz   ebx, eax
0x18001d321  lea     rcx, WPP_GLOBAL_Control
0x18001d328  mov     r10, cs:WPP_GLOBAL_Control
0x18001d32f  cmp     r10, rcx
0x18001d332  jz      short loc_18001D358
0x18001d334  test    byte ptr [r10+1Ch], 1
0x18001d339  jz      short loc_18001D358
0x18001d33b  cmp     byte ptr [r10+19h], 2
0x18001d340  jb      short loc_18001D358
0x18001d342  lea     edx, [rdi+17h]
0x18001d345  mov     r9d, ebx
0x18001d348  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d34f  mov     rcx, [r10+10h]
0x18001d353  call    WPP_SF_D
0x18001d358  mov     [rbp+57h+var_A8], r15b
0x18001d35c  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d363  mov     [rbp+57h+var_A0], rax
0x18001d367  mov     [rbp+57h+var_98], r15
0x18001d36b  mov     [rbp+57h+var_90], r15
0x18001d36f  mov     [rbp+57h+var_88], ebx
0x18001d372  mov     [rbp+57h+var_84], 0FFFFFFFFh
0x18001d379  mov     [rbp+57h+var_80], 102h
0x18001d380  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d387  mov     [rbp+57h+pExceptionObject], rax
0x18001d38b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d392  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001d396  call    _CxxThrowException_0
0x18001d39c  mov     r14, cs:__imp_EvtClose
0x18001d3a3  mov     [rbp+57h+var_48], r15b
0x18001d3a7  mov     [rbp+57h+var_40], r14
0x18001d3ab  mov     [rbp+57h+var_38], rdi
0x18001d3af  xorps   xmm0, xmm0
0x18001d3b2  movdqu  [rbp+57h+var_78], xmm0
0x18001d3b7  mov     [rbp+57h+var_68], r15
0x18001d3bb  lea     r8, [rbp+57h+var_78]
0x18001d3bf  xor     edx, edx; PropertyId
0x18001d3c1  mov     rcx, rdi; PublisherMetadata
0x18001d3c4  call    ?GetEvtPublisherProperty@VistaEventProcessor@@CAXPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VistaEventProcessor::GetEvtPublisherProperty(void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,std::vector<uchar> &)
0x18001d3c9  mov     rax, qword ptr [rbp+57h+var_78]
0x18001d3cd  cmp     dword ptr [rax+0Ch], 0Fh
0x18001d3d1  jz      short loc_18001D451
0x18001d3d3  lea     rcx, WPP_GLOBAL_Control
0x18001d3da  mov     ebx, 57h ; 'W'
0x18001d3df  mov     rax, cs:WPP_GLOBAL_Control
0x18001d3e6  cmp     rax, rcx
0x18001d3e9  jz      short loc_18001D40D
0x18001d3eb  test    byte ptr [rax+1Ch], 1
0x18001d3ef  jz      short loc_18001D40D
0x18001d3f1  cmp     byte ptr [rax+19h], 2
0x18001d3f5  jb      short loc_18001D40D
0x18001d3f7  lea     edx, [rbx-3Fh]
0x18001d3fa  mov     r9d, ebx
0x18001d3fd  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d404  mov     rcx, [rax+10h]
0x18001d408  call    WPP_SF_D
0x18001d40d  mov     [rbp+57h+var_A8], r15b
0x18001d411  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d418  mov     [rbp+57h+var_A0], rax
0x18001d41c  mov     [rbp+57h+var_98], r15
0x18001d420  mov     [rbp+57h+var_90], r15
0x18001d424  mov     [rbp+57h+var_88], ebx
0x18001d427  mov     [rbp+57h+var_84], 0FFFFFFFFh
0x18001d42e  mov     [rbp+57h+var_80], 10Eh
0x18001d435  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d43c  mov     [rbp+57h+pExceptionObject], rax
0x18001d440  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d447  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001d44b  call    _CxxThrowException_0
0x18001d451  mov     rax, [rax]
0x18001d454  movups  xmm0, xmmword ptr [rax]
0x18001d457  movdqu  xmmword ptr [rbx+54h], xmm0
0x18001d45c  mov     rax, [rbx+54h]
0x18001d460  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18001d467  jnz     short loc_18001D474
0x18001d469  mov     rax, [rbx+5Ch]
0x18001d46d  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18001d474  test    rax, rax
0x18001d477  jnz     short loc_18001D4F5
0x18001d479  lea     rcx, WPP_GLOBAL_Control
0x18001d480  lea     ebx, [rax+57h]
0x18001d483  mov     rax, cs:WPP_GLOBAL_Control
0x18001d48a  cmp     rax, rcx
0x18001d48d  jz      short loc_18001D4B1
0x18001d48f  test    byte ptr [rax+1Ch], 1
0x18001d493  jz      short loc_18001D4B1
0x18001d495  cmp     byte ptr [rax+19h], 2
0x18001d499  jb      short loc_18001D4B1
0x18001d49b  lea     edx, [rbx-3Eh]
0x18001d49e  mov     r9d, ebx
0x18001d4a1  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d4a8  mov     rcx, [rax+10h]
0x18001d4ac  call    WPP_SF_D
0x18001d4b1  mov     [rbp+57h+var_A8], r15b
0x18001d4b5  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d4bc  mov     [rbp+57h+var_A0], rax
0x18001d4c0  mov     [rbp+57h+var_98], r15
0x18001d4c4  mov     [rbp+57h+var_90], r15
0x18001d4c8  mov     [rbp+57h+var_88], ebx
0x18001d4cb  mov     [rbp+57h+var_84], 0FFFFFFFFh
0x18001d4d2  mov     [rbp+57h+var_80], 114h
0x18001d4d9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d4e0  mov     [rbp+57h+pExceptionObject], rax
0x18001d4e4  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d4eb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001d4ef  call    _CxxThrowException_0
0x18001d4f5  lea     r8, [rbp+57h+var_78]
0x18001d4f9  mov     edx, 6; PropertyId
0x18001d4fe  mov     rcx, rdi; PublisherMetadata
0x18001d501  call    ?GetEvtPublisherProperty@VistaEventProcessor@@CAXPEAXW4_EVT_PUBLISHER_METADATA_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VistaEventProcessor::GetEvtPublisherProperty(void *,_EVT_PUBLISHER_METADATA_PROPERTY_ID,std::vector<uchar> &)
0x18001d506  mov     rsi, qword ptr [rbp+57h+var_78]
0x18001d50a  cmp     dword ptr [rsi+0Ch], 20h ; ' '
0x18001d50e  jz      loc_18001D594
0x18001d514  lea     rcx, WPP_GLOBAL_Control
0x18001d51b  mov     ebx, 10D8h
0x18001d520  mov     rax, cs:WPP_GLOBAL_Control
0x18001d527  cmp     rax, rcx
0x18001d52a  jz      short loc_18001D550
0x18001d52c  test    byte ptr [rax+1Ch], 1
0x18001d530  jz      short loc_18001D550
0x18001d532  cmp     byte ptr [rax+19h], 2
0x18001d536  jb      short loc_18001D550
0x18001d538  mov     edx, 1Ah
0x18001d53d  mov     r9d, ebx
0x18001d540  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d547  mov     rcx, [rax+10h]
0x18001d54b  call    WPP_SF_D
0x18001d550  mov     [rbp+57h+var_A8], r15b
0x18001d554  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d55b  mov     [rbp+57h+var_A0], rax
0x18001d55f  mov     [rbp+57h+var_98], r15
0x18001d563  mov     [rbp+57h+var_90], r15
0x18001d567  mov     [rbp+57h+var_88], ebx
0x18001d56a  mov     [rbp+57h+var_84], 0FFFFFFFFh
0x18001d571  mov     [rbp+57h+var_80], 121h
0x18001d578  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d57f  mov     [rbp+57h+pExceptionObject], rax
0x18001d583  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d58a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001d58e  call    _CxxThrowException_0
0x18001d594  mov     rsi, [rsi]
0x18001d597  mov     [rbp+57h+var_60], r15b
0x18001d59b  mov     [rbp+57h+var_58], r14
0x18001d59f  mov     [rbp+57h+var_50], rsi
0x18001d5a3  mov     [rbp+57h+ObjectArraySize], r15d
0x18001d5a7  lea     rdx, [rbp+57h+ObjectArraySize]; ObjectArraySize
0x18001d5ab  mov     rcx, rsi; ObjectArray
0x18001d5ae  call    cs:__imp_EvtGetObjectArraySize
0x18001d5b4  test    eax, eax
0x18001d5b6  jnz     loc_18001D64B
0x18001d5bc  call    cs:__imp_GetLastError
0x18001d5c2  mov     ebx, eax
0x18001d5c4  mov     eax, 507h
0x18001d5c9  test    ebx, ebx
0x18001d5cb  cmovz   ebx, eax
0x18001d5ce  lea     rcx, WPP_GLOBAL_Control
0x18001d5d5  mov     r10, cs:WPP_GLOBAL_Control
0x18001d5dc  cmp     r10, rcx
0x18001d5df  jz      short loc_18001D607
0x18001d5e1  test    byte ptr [r10+1Ch], 1
0x18001d5e6  jz      short loc_18001D607
0x18001d5e8  cmp     byte ptr [r10+19h], 2
0x18001d5ed  jb      short loc_18001D607
0x18001d5ef  mov     edx, 1Bh
0x18001d5f4  mov     r9d, ebx
0x18001d5f7  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d5fe  mov     rcx, [r10+10h]
0x18001d602  call    WPP_SF_D
0x18001d607  mov     [rbp+57h+var_A8], r15b
0x18001d60b  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d612  mov     [rbp+57h+var_A0], rax
0x18001d616  mov     [rbp+57h+var_98], r15
0x18001d61a  mov     [rbp+57h+var_90], r15
0x18001d61e  mov     [rbp+57h+var_88], ebx
0x18001d621  mov     [rbp+57h+var_84], 0FFFFFFFFh
0x18001d628  mov     [rbp+57h+var_80], 12Ah
0x18001d62f  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d636  mov     [rbp+57h+pExceptionObject], rax
0x18001d63a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d641  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001d645  call    _CxxThrowException_0
0x18001d64b  mov     edi, r15d
0x18001d64e  cmp     edi, [rbp+57h+ObjectArraySize]
0x18001d651  jnb     loc_18001D777
0x18001d657  lea     r9, [rbp+57h+var_78]
0x18001d65b  mov     r8d, edi; ArrayIndex
0x18001d65e  mov     edx, 7; PropertyId
0x18001d663  mov     rcx, rsi; ObjectArray
0x18001d666  call    ?GetEvtArrayProperty@VistaEventProcessor@@CAXPEAXKKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VistaEventProcessor::GetEvtArrayProperty(void *,ulong,ulong,std::vector<uchar> &)
0x18001d66b  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001d66f  cmp     dword ptr [rcx+0Ch], 1
0x18001d673  jnz     loc_18001D822
0x18001d679  lea     rdx, [rbx+10h]
0x18001d67d  cmp     qword ptr [rbx+28h], 8
0x18001d682  jb      short loc_18001D687
0x18001d684  mov     rdx, [rdx]; String2
0x18001d687  mov     rcx, [rcx]; String1
0x18001d68a  call    cs:__imp__wcsicmp
0x18001d690  test    eax, eax
0x18001d692  jz      short loc_18001D698
0x18001d694  inc     edi
0x18001d696  jmp     short loc_18001D64E
0x18001d698  lea     r9, [rbp+57h+var_78]
0x18001d69c  mov     r8d, edi; ArrayIndex
0x18001d69f  mov     edx, 8; PropertyId
0x18001d6a4  mov     rcx, rsi; ObjectArray
0x18001d6a7  call    ?GetEvtArrayProperty@VistaEventProcessor@@CAXPEAXKKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VistaEventProcessor::GetEvtArrayProperty(void *,ulong,ulong,std::vector<uchar> &)
0x18001d6ac  mov     rax, qword ptr [rbp+57h+var_78]
0x18001d6b0  cmp     dword ptr [rax+0Ch], 8
0x18001d6b4  jnz     loc_18001D7A4
0x18001d6ba  mov     ecx, [rax]
0x18001d6bc  cmp     ecx, 8
0x18001d6bf  ja      loc_18001D7A4
0x18001d6c5  mov     rax, 8000000000000000h
0x18001d6cf  shr     rax, cl
0x18001d6d2  mov     [rbx+68h], rax
0x18001d6d6  lea     r9, [rbp+57h+var_78]
0x18001d6da  mov     r8d, edi; ArrayIndex
0x18001d6dd  mov     edx, 9; PropertyId
0x18001d6e2  mov     rcx, rsi; ObjectArray
0x18001d6e5  call    ?GetEvtArrayProperty@VistaEventProcessor@@CAXPEAXKKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VistaEventProcessor::GetEvtArrayProperty(void *,ulong,ulong,std::vector<uchar> &)
0x18001d6ea  mov     rax, qword ptr [rbp+57h+var_78]
0x18001d6ee  cmp     dword ptr [rax+0Ch], 8
0x18001d6f2  jz      short loc_18001D772
0x18001d6f4  lea     rcx, WPP_GLOBAL_Control
0x18001d6fb  mov     ebx, 0Dh
0x18001d700  mov     rax, cs:WPP_GLOBAL_Control
0x18001d707  cmp     rax, rcx
0x18001d70a  jz      short loc_18001D72E
0x18001d70c  test    byte ptr [rax+1Ch], 1
0x18001d710  jz      short loc_18001D72E
0x18001d712  cmp     byte ptr [rax+19h], 2
0x18001d716  jb      short loc_18001D72E
0x18001d718  lea     edx, [rbx+11h]
0x18001d71b  mov     r9d, ebx
0x18001d71e  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001d725  mov     rcx, [rax+10h]
0x18001d729  call    WPP_SF_D
0x18001d72e  mov     [rbp+57h+var_A8], r15b
0x18001d732  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001d739  mov     [rbp+57h+var_A0], rax
0x18001d73d  mov     [rbp+57h+var_98], r15
0x18001d741  mov     [rbp+57h+var_90], r15
0x18001d745  mov     [rbp+57h+var_88], ebx
0x18001d748  mov     [rbp+57h+var_84], 0FFFFFFFFh
0x18001d74f  mov     [rbp+57h+var_80], 14Eh
0x18001d756  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d75d  mov     [rbp+57h+pExceptionObject], rax
0x18001d761  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001d768  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001d76c  call    _CxxThrowException_0
0x18001d772  mov     eax, [rax]
0x18001d774  mov     [rbx+50h], eax
0x18001d777  lea     rcx, [rbp+57h+var_60]
0x18001d77b  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001d780  nop
0x18001d781  lea     rcx, [rbp+57h+var_78]
0x18001d785  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18001d78a  nop
0x18001d78b  lea     rcx, [rbp+57h+var_48]
0x18001d78f  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001d794  add     rsp, 0B8h
0x18001d79b  pop     r15
0x18001d79d  pop     r14
0x18001d79f  pop     rdi
0x18001d7a0  pop     rsi
0x18001d7a1  pop     rbx
0x18001d7a2  pop     rbp
0x18001d7a3  retn
0x18001d7a4  lea     rcx, WPP_GLOBAL_Control
0x18001d7ab  mov     ebx, 0Dh
0x18001d7b0  mov     rax, cs:WPP_GLOBAL_Control
0x18001d7b7  cmp     rax, rcx
0x18001d7ba  jz      short loc_18001D7DE
0x18001d7bc  test    byte ptr [rax+1Ch], 1
  ... truncated ...
```
