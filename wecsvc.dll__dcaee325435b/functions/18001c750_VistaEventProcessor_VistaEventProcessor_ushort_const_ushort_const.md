# VistaEventProcessor::VistaEventProcessor(ushort const *,ushort const *)

- ea: `0x18001c750`
- end: `0x18001cc4c`
- name: `??0VistaEventProcessor@@QEAA@PEBG0@Z`
- size: `1276`
- prototype: `VistaEventProcessor *__fastcall(VistaEventProcessor *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180003ea0`

## callees

- `0x18000195c`
- `0x180002510`
- `0x1800032dc`
- `0x180003810`
- `0x180006334`
- `0x18000669c`
- `0x18001c750`
- `0x18001cee8`
- `0x18001d2c4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001c9b7`
- `msvcrt!_wcsicmp` at `0x18001c9ed`
- `msvcrt!_wcsicmp` at `0x18001ca20`
- `msvcrt!_wcsicmp` at `0x18001ca51`
- `msvcrt!_wcsicmp` at `0x18001c9b7`
- `msvcrt!_wcsicmp` at `0x18001c9ed`
- `msvcrt!_wcsicmp` at `0x18001ca20`
- `msvcrt!_wcsicmp` at `0x18001ca51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c803`
- `ADVAPI32!EventRegister` at `0x18001ca92`
- `ADVAPI32!EventRegister` at `0x18001ca92`
- `wevtapi!EvtClose` at `0x18001c890`
- `wevtapi!EvtOpenChannelConfig` at `0x18001c7f1`
- `wevtapi!EvtOpenChannelConfig` at `0x18001c7f1`

## pseudocode

```c
VistaEventProcessor *__fastcall VistaEventProcessor::VistaEventProcessor(
        VistaEventProcessor *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const WCHAR *v5; // rsi
  const WCHAR *v6; // rdx
  EVT_HANDLE v7; // rbx
  DWORD LastError; // ebx
  const wchar_t *v9; // rcx
  unsigned __int64 v10; // rax
  const wchar_t *v11; // rcx
  const wchar_t *v12; // rcx
  ULONG v13; // eax
  ULONG v14; // ebx
  __int128 v16; // [rsp+28h] [rbp-39h] BYREF
  __int64 v17; // [rsp+38h] [rbp-29h]
  _BYTE v18[8]; // [rsp+40h] [rbp-21h] BYREF
  BOOL (__stdcall *v19)(EVT_HANDLE); // [rsp+48h] [rbp-19h]
  EVT_HANDLE v20; // [rsp+50h] [rbp-11h]
  void **pExceptionObject; // [rsp+58h] [rbp-9h] BYREF
  char v22; // [rsp+60h] [rbp-1h]
  const char *v23; // [rsp+68h] [rbp+7h]
  __int64 v24; // [rsp+70h] [rbp+Fh]
  __int64 v25; // [rsp+78h] [rbp+17h]
  int v26; // [rsp+80h] [rbp+1Fh]
  int v27; // [rsp+84h] [rbp+23h]
  int v28; // [rsp+88h] [rbp+27h]

  *(_QWORD *)this = &wmi::RefBase::`vftable';
  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &VistaEventProcessor::`vftable';
  v5 = (const WCHAR *)((char *)this + 16);
  if ( !a2 )
    a2 = &word_180026AD8;
  std::wstring::wstring((char *)this + 16, a2);
  if ( !a3 )
    a3 = &word_180026AD8;
  std::wstring::wstring((char *)this + 48, a3);
  if ( !*((_QWORD *)this + 8) && !*((_QWORD *)this + 4) )
    std::wstring::assign(v5, L"ForwardedEvents");
  if ( *((_QWORD *)v5 + 3) < 8u )
    v6 = v5;
  else
    v6 = *(const WCHAR **)v5;
  v7 = EvtOpenChannelConfig(0, v6, 0);
  if ( !v7 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, LastError);
    }
    v22 = 0;
    v23 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v24 = 0;
    v25 = 0;
    v26 = LastError;
    v27 = -1;
    v28 = 35;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v18[0] = 0;
  v19 = EvtClose;
  v20 = v7;
  v16 = 0;
  v17 = 0;
  VistaEventProcessor::GetEvtChannelProperty(v7, EvtChannelConfigEnabled);
  if ( MEMORY[0xC] != 13 || !*(_DWORD *)v16 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 15081);
    }
    v22 = 0;
    v23 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v24 = 0;
    v25 = 0;
    v26 = 15081;
    v27 = -1;
    v28 = 48;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( *((_QWORD *)this + 8) )
    goto LABEL_72;
  VistaEventProcessor::GetEvtChannelProperty(v7, EvtChannelConfigOwningPublisher);
  if ( *(_DWORD *)(v16 + 12) == 1 && *(_QWORD *)v16 )
    std::wstring::assign((char *)this + 48, *(_QWORD *)v16);
  if ( *((_QWORD *)this + 8) )
  {
LABEL_72:
    if ( !*((_QWORD *)this + 4) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 87);
      }
      v22 = 0;
      v23 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
      v24 = 0;
      v25 = 0;
      v26 = 87;
      v27 = -1;
      v28 = 68;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&pExceptionObject;
    }
    VistaEventProcessor::GetPublisherAndLogInfo(this);
  }
  else
  {
    if ( *((_QWORD *)v5 + 3) < 8u )
      v9 = v5;
    else
      v9 = *(const wchar_t **)v5;
    if ( _wcsicmp(v9, L"ForwardedEvents") )
    {
      if ( *((_QWORD *)v5 + 3) < 8u )
        v11 = v5;
      else
        v11 = *(const wchar_t **)v5;
      if ( _wcsicmp(v11, L"Application") )
      {
        if ( *((_QWORD *)v5 + 3) < 8u )
          v12 = v5;
        else
          v12 = *(const wchar_t **)v5;
        if ( _wcsicmp(v12, L"System") )
        {
          if ( *((_QWORD *)v5 + 3) >= 8u )
            v5 = *(const WCHAR **)v5;
          if ( _wcsicmp(v5, L"HardwareEvents") )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, 87);
            }
            v22 = 0;
            v23 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
            v24 = 0;
            v25 = 0;
            v26 = 87;
            v27 = -1;
            v28 = 99;
            pExceptionObject = &wmi::GenericException::`vftable';
            throw (wmi::GenericException *)&pExceptionObject;
          }
          *((_DWORD *)this + 20) = 17;
          v10 = 0x1000000000000000LL;
        }
        else
        {
          *((_DWORD *)this + 20) = 8;
          v10 = 0x4000000000000000LL;
        }
      }
      else
      {
        *((_DWORD *)this + 20) = 9;
        v10 = 0x8000000000000000uLL;
      }
    }
    else
    {
      *((_DWORD *)this + 20) = 16;
      v10 = 0x2000000000000000LL;
    }
    *((_QWORD *)this + 13) = v10;
    *(_OWORD *)((char *)this + 84) = EVENTCOLLECTOR_PROVIDER;
  }
  v13 = EventRegister((LPCGUID)((char *)this + 84), guard_check_icall_nop, 0, (PREGHANDLE)this + 14);
  v14 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids, v13);
    }
    v22 = 0;
    v23 = "admin\\wmi\\events\\forwarding\\collector\\evproc\\colevproc_6x.cpp";
    v24 = 0;
    v25 = 0;
    v26 = v14;
    v27 = -1;
    v28 = 107;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(&v16);
  wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v18);
  return this;
}

```

## disassembly

```asm
0x18001c750  mov     rax, rsp
0x18001c753  mov     [rax+10h], rbx
0x18001c757  mov     [rax+18h], rsi
0x18001c75b  mov     [rax+8], rcx
0x18001c75f  push    rbp
0x18001c760  push    rdi
0x18001c761  push    r12
0x18001c763  push    r14
0x18001c765  push    r15
0x18001c767  lea     rbp, [rax-5Fh]
0x18001c76b  sub     rsp, 90h
0x18001c772  mov     rbx, r8
0x18001c775  mov     rdi, rcx
0x18001c778  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x18001c77f  mov     [rcx], rax
0x18001c782  xor     r12d, r12d
0x18001c785  mov     [rcx+8], r12d
0x18001c789  lea     rax, ??_7VistaEventProcessor@@6B@; const VistaEventProcessor::`vftable'
0x18001c790  mov     [rcx], rax
0x18001c793  lea     rsi, [rcx+10h]
0x18001c797  lea     r15, word_180026AD8
0x18001c79e  test    rdx, rdx
0x18001c7a1  cmovz   rdx, r15
0x18001c7a5  mov     rcx, rsi
0x18001c7a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001c7ad  nop
0x18001c7ae  test    rbx, rbx
0x18001c7b1  cmovz   rbx, r15
0x18001c7b5  mov     rdx, rbx
0x18001c7b8  lea     rcx, [rdi+30h]
0x18001c7bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001c7c1  nop
0x18001c7c2  cmp     [rdi+40h], r12
0x18001c7c6  jnz     short loc_18001C7DD
0x18001c7c8  cmp     [rdi+20h], r12
0x18001c7cc  jnz     short loc_18001C7DD
0x18001c7ce  lea     rdx, aForwardedevent; "ForwardedEvents"
0x18001c7d5  mov     rcx, rsi
0x18001c7d8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001c7dd  cmp     qword ptr [rsi+18h], 8
0x18001c7e2  jb      short loc_18001C7E9
0x18001c7e4  mov     rdx, [rsi]
0x18001c7e7  jmp     short loc_18001C7EC
0x18001c7e9  mov     rdx, rsi; ChannelPath
0x18001c7ec  xor     r8d, r8d; Flags
0x18001c7ef  xor     ecx, ecx; Session
0x18001c7f1  call    cs:__imp_EvtOpenChannelConfig
0x18001c7f7  mov     rbx, rax
0x18001c7fa  test    rax, rax
0x18001c7fd  jnz     loc_18001C890
0x18001c803  call    cs:__imp_GetLastError
0x18001c809  mov     ebx, eax
0x18001c80b  mov     eax, 507h
0x18001c810  test    ebx, ebx
0x18001c812  cmovz   ebx, eax
0x18001c815  lea     rcx, WPP_GLOBAL_Control
0x18001c81c  mov     rax, cs:WPP_GLOBAL_Control
0x18001c823  cmp     rax, rcx
0x18001c826  jz      short loc_18001C84C
0x18001c828  test    byte ptr [rax+1Ch], 1
0x18001c82c  jz      short loc_18001C84C
0x18001c82e  cmp     byte ptr [rax+19h], 2
0x18001c832  jb      short loc_18001C84C
0x18001c834  mov     edx, 0Ah
0x18001c839  mov     r9d, ebx
0x18001c83c  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001c843  mov     rcx, [rax+10h]
0x18001c847  call    WPP_SF_D
0x18001c84c  mov     [rbp+57h+var_58], r12b
0x18001c850  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001c857  mov     [rbp+57h+var_50], rax
0x18001c85b  mov     [rbp+57h+var_48], r12
0x18001c85f  mov     [rbp+57h+var_40], r12
0x18001c863  mov     [rbp+57h+var_38], ebx
0x18001c866  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001c86d  mov     [rbp+57h+var_30], 23h ; '#'
0x18001c874  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001c87b  mov     [rbp+57h+pExceptionObject], rax
0x18001c87f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001c886  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c88a  call    _CxxThrowException_0
0x18001c890  mov     rax, cs:__imp_EvtClose
0x18001c897  mov     [rbp+57h+var_78], r12b
0x18001c89b  mov     [rbp+57h+var_70], rax
0x18001c89f  mov     [rbp+57h+var_68], rbx
0x18001c8a3  xorps   xmm0, xmm0
0x18001c8a6  movdqu  [rbp+57h+var_90], xmm0
0x18001c8ab  mov     [rbp+57h+var_80], r12
0x18001c8af  lea     r8, [rbp+57h+var_90]
0x18001c8b3  xor     edx, edx; PropertyId
0x18001c8b5  mov     rcx, rbx; ChannelConfig
0x18001c8b8  call    ?GetEvtChannelProperty@VistaEventProcessor@@CAXPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VistaEventProcessor::GetEvtChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar> &)
0x18001c8bd  mov     rax, qword ptr [rbp+57h+var_90]
0x18001c8c1  cmp     dword ptr [rax+0Ch], 0Dh
0x18001c8c5  jnz     loc_18001CBCC
0x18001c8cb  cmp     [rax], r12d
0x18001c8ce  jz      loc_18001CBCC
0x18001c8d4  cmp     [rdi+40h], r12
0x18001c8d8  jnz     short loc_18001C910
0x18001c8da  lea     r8, [rbp+57h+var_90]
0x18001c8de  mov     edx, 3; PropertyId
0x18001c8e3  mov     rcx, rbx; ChannelConfig
0x18001c8e6  call    ?GetEvtChannelProperty@VistaEventProcessor@@CAXPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VistaEventProcessor::GetEvtChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar> &)
0x18001c8eb  mov     rdx, qword ptr [rbp+57h+var_90]
0x18001c8ef  cmp     dword ptr [rdx+0Ch], 1
0x18001c8f3  jnz     short loc_18001C906
0x18001c8f5  mov     rdx, [rdx]
0x18001c8f8  test    rdx, rdx
0x18001c8fb  jz      short loc_18001C906
0x18001c8fd  lea     rcx, [rdi+30h]
0x18001c901  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001c906  cmp     [rdi+40h], r12
0x18001c90a  jz      loc_18001C9A1
0x18001c910  cmp     [rdi+20h], r12
0x18001c914  jnz     short loc_18001C994
0x18001c916  lea     rcx, WPP_GLOBAL_Control
0x18001c91d  mov     ebx, 57h ; 'W'
0x18001c922  mov     rax, cs:WPP_GLOBAL_Control
0x18001c929  cmp     rax, rcx
0x18001c92c  jz      short loc_18001C950
0x18001c92e  test    byte ptr [rax+1Ch], 1
0x18001c932  jz      short loc_18001C950
0x18001c934  cmp     byte ptr [rax+19h], 2
0x18001c938  jb      short loc_18001C950
0x18001c93a  lea     edx, [rbx-4Bh]
0x18001c93d  mov     r9d, ebx
0x18001c940  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001c947  mov     rcx, [rax+10h]
0x18001c94b  call    WPP_SF_D
0x18001c950  mov     [rbp+57h+var_58], r12b
0x18001c954  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001c95b  mov     [rbp+57h+var_50], rax
0x18001c95f  mov     [rbp+57h+var_48], r12
0x18001c963  mov     [rbp+57h+var_40], r12
0x18001c967  mov     [rbp+57h+var_38], ebx
0x18001c96a  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001c971  mov     [rbp+57h+var_30], 44h ; 'D'
0x18001c978  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001c97f  mov     [rbp+57h+pExceptionObject], rax
0x18001c983  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001c98a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c98e  call    _CxxThrowException_0
0x18001c994  mov     rcx, rdi; this
0x18001c997  call    ?GetPublisherAndLogInfo@VistaEventProcessor@@AEAAXXZ; VistaEventProcessor::GetPublisherAndLogInfo(void)
0x18001c99c  jmp     loc_18001CA80
0x18001c9a1  cmp     qword ptr [rsi+18h], 8
0x18001c9a6  jb      short loc_18001C9AD
0x18001c9a8  mov     rcx, [rsi]
0x18001c9ab  jmp     short loc_18001C9B0
0x18001c9ad  mov     rcx, rsi; String1
0x18001c9b0  lea     rdx, aForwardedevent; "ForwardedEvents"
0x18001c9b7  call    cs:__imp__wcsicmp
0x18001c9bd  test    eax, eax
0x18001c9bf  jnz     short loc_18001C9D7
0x18001c9c1  mov     dword ptr [rdi+50h], 10h
0x18001c9c8  mov     rax, 2000000000000000h
0x18001c9d2  jmp     loc_18001CA70
0x18001c9d7  cmp     qword ptr [rsi+18h], 8
0x18001c9dc  jb      short loc_18001C9E3
0x18001c9de  mov     rcx, [rsi]
0x18001c9e1  jmp     short loc_18001C9E6
0x18001c9e3  mov     rcx, rsi; String1
0x18001c9e6  lea     rdx, aApplication; "Application"
0x18001c9ed  call    cs:__imp__wcsicmp
0x18001c9f3  test    eax, eax
0x18001c9f5  jnz     short loc_18001CA0A
0x18001c9f7  mov     dword ptr [rdi+50h], 9
0x18001c9fe  mov     rax, 8000000000000000h
0x18001ca08  jmp     short loc_18001CA70
0x18001ca0a  cmp     qword ptr [rsi+18h], 8
0x18001ca0f  jb      short loc_18001CA16
0x18001ca11  mov     rcx, [rsi]
0x18001ca14  jmp     short loc_18001CA19
0x18001ca16  mov     rcx, rsi; String1
0x18001ca19  lea     rdx, aSystem; "System"
0x18001ca20  call    cs:__imp__wcsicmp
0x18001ca26  test    eax, eax
0x18001ca28  jnz     short loc_18001CA3D
0x18001ca2a  mov     dword ptr [rdi+50h], 8
0x18001ca31  mov     rax, 4000000000000000h
0x18001ca3b  jmp     short loc_18001CA70
0x18001ca3d  cmp     qword ptr [rsi+18h], 8
0x18001ca42  jb      short loc_18001CA47
0x18001ca44  mov     rsi, [rsi]
0x18001ca47  lea     rdx, aHardwareevents; "HardwareEvents"
0x18001ca4e  mov     rcx, rsi; String1
0x18001ca51  call    cs:__imp__wcsicmp
0x18001ca57  test    eax, eax
0x18001ca59  jnz     loc_18001CB4E
0x18001ca5f  mov     dword ptr [rdi+50h], 11h
0x18001ca66  mov     rax, 1000000000000000h
0x18001ca70  movups  xmm0, cs:EVENTCOLLECTOR_PROVIDER
0x18001ca77  mov     [rdi+68h], rax
0x18001ca7b  movdqu  xmmword ptr [rdi+54h], xmm0
0x18001ca80  lea     r9, [rdi+70h]; RegHandle
0x18001ca84  lea     rcx, [rdi+54h]; ProviderId
0x18001ca88  xor     r8d, r8d; CallbackContext
0x18001ca8b  lea     rdx, _guard_check_icall_nop; EnableCallback
0x18001ca92  call    cs:__imp_EventRegister
0x18001ca98  mov     ebx, eax
0x18001ca9a  test    eax, eax
0x18001ca9c  jz      short loc_18001CB1B
0x18001ca9e  lea     rcx, WPP_GLOBAL_Control
0x18001caa5  mov     r10, cs:WPP_GLOBAL_Control
0x18001caac  cmp     r10, rcx
0x18001caaf  jz      short loc_18001CAD7
0x18001cab1  test    byte ptr [r10+1Ch], 1
0x18001cab6  jz      short loc_18001CAD7
0x18001cab8  cmp     byte ptr [r10+19h], 2
0x18001cabd  jb      short loc_18001CAD7
0x18001cabf  mov     edx, 0Eh
0x18001cac4  mov     r9d, eax
0x18001cac7  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001cace  mov     rcx, [r10+10h]
0x18001cad2  call    WPP_SF_D
0x18001cad7  mov     [rbp+57h+var_58], r12b
0x18001cadb  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001cae2  mov     [rbp+57h+var_50], rax
0x18001cae6  mov     [rbp+57h+var_48], r12
0x18001caea  mov     [rbp+57h+var_40], r12
0x18001caee  mov     [rbp+57h+var_38], ebx
0x18001caf1  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001caf8  mov     [rbp+57h+var_30], 6Bh ; 'k'
0x18001caff  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001cb06  mov     [rbp+57h+pExceptionObject], rax
0x18001cb0a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001cb11  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001cb15  call    _CxxThrowException_0
0x18001cb1b  lea     rcx, [rbp+57h+var_90]
0x18001cb1f  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x18001cb24  nop
0x18001cb25  lea     rcx, [rbp+57h+var_78]
0x18001cb29  call    ??1?$ScopeGuardImpl1@P6AXPEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@ZPEAV12@@wmi@@QEAA@XZ; wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<ushort>> *),std::vector<std::vector<ushort>> *>(void)
0x18001cb2e  nop
0x18001cb2f  mov     rax, rdi
0x18001cb32  lea     r11, [rsp+0B0h+var_20]
0x18001cb3a  mov     rbx, [r11+38h]
0x18001cb3e  mov     rsi, [r11+40h]
0x18001cb42  mov     rsp, r11
0x18001cb45  pop     r15
0x18001cb47  pop     r14
0x18001cb49  pop     r12
0x18001cb4b  pop     rdi
0x18001cb4c  pop     rbp
0x18001cb4d  retn
0x18001cb4e  lea     rcx, WPP_GLOBAL_Control
0x18001cb55  mov     ebx, 57h ; 'W'
0x18001cb5a  mov     rax, cs:WPP_GLOBAL_Control
0x18001cb61  cmp     rax, rcx
0x18001cb64  jz      short loc_18001CB88
0x18001cb66  test    byte ptr [rax+1Ch], 1
0x18001cb6a  jz      short loc_18001CB88
0x18001cb6c  cmp     byte ptr [rax+19h], 2
0x18001cb70  jb      short loc_18001CB88
0x18001cb72  lea     edx, [rbx-4Ah]
0x18001cb75  mov     r9d, ebx
0x18001cb78  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001cb7f  mov     rcx, [rax+10h]
0x18001cb83  call    WPP_SF_D
0x18001cb88  mov     [rbp+57h+var_58], r12b
0x18001cb8c  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001cb93  mov     [rbp+57h+var_50], rax
0x18001cb97  mov     [rbp+57h+var_48], r12
0x18001cb9b  mov     [rbp+57h+var_40], r12
0x18001cb9f  mov     [rbp+57h+var_38], ebx
0x18001cba2  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001cba9  mov     [rbp+57h+var_30], 63h ; 'c'
0x18001cbb0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001cbb7  mov     [rbp+57h+pExceptionObject], rax
0x18001cbbb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001cbc2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001cbc6  call    _CxxThrowException_0
0x18001cbcc  lea     rcx, WPP_GLOBAL_Control
0x18001cbd3  mov     ebx, 3AE9h
0x18001cbd8  mov     rax, cs:WPP_GLOBAL_Control
0x18001cbdf  cmp     rax, rcx
0x18001cbe2  jz      short loc_18001CC08
0x18001cbe4  test    byte ptr [rax+1Ch], 1
0x18001cbe8  jz      short loc_18001CC08
0x18001cbea  cmp     byte ptr [rax+19h], 2
0x18001cbee  jb      short loc_18001CC08
0x18001cbf0  mov     edx, 0Bh
0x18001cbf5  mov     r9d, ebx
0x18001cbf8  lea     r8, WPP_c0aff9c4222a365e0c5075535ef999c6_Traceguids
0x18001cbff  mov     rcx, [rax+10h]
0x18001cc03  call    WPP_SF_D
0x18001cc08  mov     [rbp+57h+var_58], r12b
0x18001cc0c  lea     rax, aAdminWmiEvents_7; "admin\\wmi\\events\\forwarding\\collect"...
0x18001cc13  mov     [rbp+57h+var_50], rax
0x18001cc17  mov     [rbp+57h+var_48], r12
0x18001cc1b  mov     [rbp+57h+var_40], r12
0x18001cc1f  mov     [rbp+57h+var_38], ebx
0x18001cc22  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001cc29  mov     [rbp+57h+var_30], 30h ; '0'
0x18001cc30  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001cc37  mov     [rbp+57h+pExceptionObject], rax
0x18001cc3b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001cc42  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001cc46  call    _CxxThrowException_0
```
