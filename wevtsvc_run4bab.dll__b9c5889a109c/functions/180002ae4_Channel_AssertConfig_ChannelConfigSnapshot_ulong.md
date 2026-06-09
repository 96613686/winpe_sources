# Channel::AssertConfig(ChannelConfigSnapshot &&,ulong)

- ea: `0x180002ae4`
- end: `0x180003270`
- name: `?AssertConfig@Channel@@AEAAX$$QEAVChannelConfigSnapshot@@K@Z`
- size: `1932`
- prototype: `__int64 __fastcall(Channel *this, struct ChannelConfigSnapshot *, unsigned int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002f1b0`
- `0x1800d5670`

## callees

- `0x180002234`
- `0x1800028fc`
- `0x180002930`
- `0x180002ae4`
- `0x18000349c`
- `0x1800047b0`
- `0x180017b60`
- `0x18003d394`
- `0x18003ee78`
- `0x180047194`
- `0x180047fd8`
- `0x180048ae0`
- `0x18006fc44`
- `0x180092008`
- `0x180098c50`
- `0x18009eaf0`
- `0x18009f0d8`
- `0x1800ad1b8`
- `0x1800c0b18`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b21`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800031fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800031fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003260`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002da1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002d93`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180002d93`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Channel::AssertConfig(Channel *this, struct ChannelConfigSnapshot *a2, unsigned int a3)
{
  unsigned int v3; // r12d
  struct ChannelConfigSnapshot *v4; // r14
  Channel *v5; // rsi
  unsigned int v6; // ebx
  const WCHAR *v7; // rbx
  PSECURITY_DESCRIPTOR *v8; // rax
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  DWORD v12; // ebx
  bool *v13; // rbx
  __int64 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rax
  _QWORD *v23; // r9
  _QWORD *v24; // r8
  __int64 *v25; // rbx
  __int64 *v26; // rcx
  __int64 v27; // rdx
  __int64 FilePathForContainerChannel; // rax
  __int64 v29; // rax
  EventSession *v30; // rcx
  char v31; // r13
  __int64 v32; // rcx
  __int64 v33; // rcx
  DWORD v34; // eax
  int v35; // edx
  __int64 v36; // rcx
  _QWORD *v37; // rdi
  EvtException *v38; // rbx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // [rsp+40h] [rbp-1A8h] BYREF
  __int64 v42; // [rsp+48h] [rbp-1A0h]
  __int64 v43; // [rsp+50h] [rbp-198h] BYREF
  __int64 v44; // [rsp+58h] [rbp-190h]
  _QWORD *v45; // [rsp+60h] [rbp-188h]
  _QWORD v46[2]; // [rsp+70h] [rbp-178h] BYREF
  _QWORD *v47; // [rsp+80h] [rbp-168h]
  _QWORD *v48; // [rsp+88h] [rbp-160h]
  __int64 *v49; // [rsp+90h] [rbp-158h] BYREF
  _QWORD *v50; // [rsp+98h] [rbp-150h] BYREF
  bool *v51; // [rsp+A0h] [rbp-148h]
  LPCRITICAL_SECTION v52; // [rsp+A8h] [rbp-140h]
  __int64 v53[3]; // [rsp+B0h] [rbp-138h] BYREF
  DWORD v54; // [rsp+C8h] [rbp-120h]
  int v55; // [rsp+CCh] [rbp-11Ch]
  int v56; // [rsp+D0h] [rbp-118h]
  char v57; // [rsp+D4h] [rbp-114h]
  char v58[8]; // [rsp+D8h] [rbp-110h] BYREF
  __int64 *v59; // [rsp+E0h] [rbp-108h]
  _QWORD *v60; // [rsp+E8h] [rbp-100h]
  struct ChannelLogConfigData *v61; // [rsp+F0h] [rbp-F8h]
  _QWORD v62[3]; // [rsp+F8h] [rbp-F0h] BYREF
  DWORD v63; // [rsp+110h] [rbp-D8h]
  int v64; // [rsp+114h] [rbp-D4h]
  int v65; // [rsp+118h] [rbp-D0h]
  __int128 pExceptionObject; // [rsp+120h] [rbp-C8h] BYREF
  __int64 v67; // [rsp+130h] [rbp-B8h]
  unsigned int v68; // [rsp+138h] [rbp-B0h]
  int v69; // [rsp+13Ch] [rbp-ACh]
  int v70; // [rsp+140h] [rbp-A8h]
  __int128 v71; // [rsp+148h] [rbp-A0h] BYREF
  __int64 v72; // [rsp+158h] [rbp-90h]
  int v73; // [rsp+160h] [rbp-88h]
  int v74; // [rsp+164h] [rbp-84h]
  int v75; // [rsp+168h] [rbp-80h]
  __int128 v76; // [rsp+170h] [rbp-78h] BYREF
  __int64 v77; // [rsp+180h] [rbp-68h]
  int v78; // [rsp+188h] [rbp-60h]
  int v79; // [rsp+18Ch] [rbp-5Ch]
  int v80; // [rsp+190h] [rbp-58h]
  char *v81; // [rsp+198h] [rbp-50h]
  EvtException *v82; // [rsp+1A0h] [rbp-48h] BYREF
  EvtException *v83; // [rsp+1A8h] [rbp-40h] BYREF
  unsigned int v86; // [rsp+200h] [rbp+18h]
  __int64 v87; // [rsp+208h] [rbp+20h] BYREF

  v86 = a3;
  v3 = a3;
  v4 = a2;
  v5 = this;
  v52 = (LPCRITICAL_SECTION)((char *)this + 16);
  v81 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (v3 & 4) != 0 )
  {
    v6 = *((_DWORD *)v5 + 20);
    if ( v6 != -1 )
    {
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, v6);
        }
        pExceptionObject = 0;
        v67 = 0;
        v68 = v6;
        v69 = -1;
        v70 = 983;
        throw (EvtException *)&pExceptionObject;
      }
      goto LABEL_17;
    }
  }
  if ( *((_BYTE *)v5 + 85) )
  {
    v3 |= 2u;
    v86 = v3;
  }
  if ( *((_BYTE *)v5 + 424) && ChannelConfigSnapshot::Equals((Channel *)((char *)v5 + 168), v4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids,
        *((_QWORD *)v5 + 17));
    }
    goto LABEL_17;
  }
  if ( (unsigned __int8)(*((_BYTE *)v4 + 249) - 2) <= 1u
    && *((_BYTE *)v4 + 251)
    && *((_QWORD *)v5 + 12)
    && *((_BYTE *)v5 + 876) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, 15022);
    }
    v71 = 0;
    v72 = 0;
    v73 = 15022;
    v74 = -1;
    v75 = 1006;
    throw (EvtException *)&v71;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids,
      *((_QWORD *)v5 + 17));
  }
  try
  {
    *((_DWORD *)v5 + 218) = *((unsigned __int8 *)v4 + 248);
    v7 = (const WCHAR *)*((_QWORD *)v4 + 21);
    if ( *((const WCHAR **)v4 + 22) != v7 )
    {
      v87 = 0;
      v8 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v87);
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, v8, 0) )
      {
        LastError = GetLastError();
        v12 = LastError;
        v53[0] = (__int64)&word_1800EC961;
        v53[2] = 0;
        v54 = LastError;
        v55 = -1;
        v56 = -1;
        v57 = 0;
        if ( (v3 & 1) != 0 )
        {
          if ( (Microsoft_Windows_EventlogEnableBits & 2) != 0 )
            McTemplateU0qzz_EventWriteTransfer(v11, v10, LastError, *((_QWORD *)v5 + 17));
          v57 = 1;
        }
        v62[0] = &word_1800EC961;
        v62[1] = 0;
        v62[2] = 0;
        v63 = v12;
        v64 = -1;
        v65 = -1;
        v53[1] = 0;
        throw (EvtException *)v62;
      }
      tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::swap(
        (char *)v5 + 88,
        &v87);
      tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v87);
    }
    v61 = (struct ChannelConfigSnapshot *)((char *)v4 + 56);
    v45 = (_QWORD *)*((_QWORD *)v4 + 19);
    v50 = v45;
    v46[0] = *((_QWORD *)v4 + 7);
    v46[1] = (__int64)(*((_QWORD *)v4 + 8) - v46[0]) >> 1;
    AssignOrThrowOOM((char *)v5 + 104, v46);
    v13 = (bool *)v4 + 251;
    if ( (unsigned __int8)(*((_BYTE *)v4 + 249) - 2) <= 1u )
    {
      LOBYTE(v87) = 1;
    }
    else
    {
      LOBYTE(v87) = 0;
      v51 = (bool *)v4 + 251;
      if ( *v13 )
      {
        v14 = (__int64 *)((char *)v5 + 104);
        v59 = (__int64 *)((char *)v5 + 104);
        if ( (v3 & 2) != 0 )
        {
          try
          {
            v15 = *v14;
            v47 = (_QWORD *)((char *)v5 + 112);
            v46[0] = (char *)v5 + 112;
            v49 = (__int64 *)((char *)v5 + 136);
            v16 = *((_QWORD *)v5 + 17);
            v48 = (_QWORD *)((char *)v5 + 144);
            v60 = (_QWORD *)((char *)v5 + 144);
            v41 = v15;
            v42 = (*((_QWORD *)v5 + 14) - v15) >> 1;
            v43 = v16;
            v44 = (*((_QWORD *)v5 + 18) - v16) >> 1;
            v45 = (_QWORD *)Channel::OpenLogWithRetry(v58, &v43, &v41, v45);
            wmi::AutoRef<File>::Release((char *)v5 + 456);
            v17 = v45;
            *((_QWORD *)v5 + 57) = *v45;
            *v17 = 0;
            wmi::AutoRef<File>::Release(v58);
          }
          catch ( EvtException )
          {
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              v53,
              (char *)this + 104,
              v18,
              v19);
            v43 = 0;
            v44 = 0;
            v41 = *((_QWORD *)this + 17);
            v42 = (__int64)(*((_QWORD *)this + 18) - *((_QWORD *)this + 17)) >> 1;
            GetDefaultLogFilePath(&v41, &v43, *((unsigned __int8 *)a2 + 249), (char *)this + 104);
            v34 = GetLastError();
            if ( (Microsoft_Windows_EventlogEnableBits & 8) != 0 )
              McTemplateU0qzzz_EventWriteTransfer(
                v53[0],
                v35,
                v34,
                *((_QWORD *)this + 17),
                v53[0],
                *((_QWORD *)this + 13));
            v36 = *((_QWORD *)this + 17);
            v43 = *((_QWORD *)this + 13);
            v44 = (__int64)(*((_QWORD *)this + 14) - *((_QWORD *)this + 13)) >> 1;
            v41 = v36;
            v42 = (*((_QWORD *)this + 18) - v36) >> 1;
            v37 = (_QWORD *)Channel::OpenLogWithRetry(&v87, &v41, &v43, v50);
            wmi::AutoRef<File>::Release((char *)this + 456);
            *((_QWORD *)this + 57) = *v37;
            *v37 = 0;
            wmi::AutoRef<File>::Release(&v87);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v53);
            v5 = this;
            v3 = v86;
            v4 = a2;
            v26 = v59;
            v23 = v60;
            LOBYTE(v87) = 0;
            v25 = v49;
            v24 = (_QWORD *)v46[0];
            goto LABEL_44;
          }
        }
        else
        {
          v20 = *v14;
          v47 = (_QWORD *)((char *)v5 + 112);
          v21 = *((_QWORD *)v5 + 17);
          v48 = (_QWORD *)((char *)v5 + 144);
          v43 = v20;
          v44 = (*((_QWORD *)v5 + 14) - v20) >> 1;
          v41 = v21;
          v42 = (*((_QWORD *)v5 + 18) - v21) >> 1;
          v46[0] = Channel::OpenLogWithRetry(&v49, &v41, &v43, v45);
          wmi::AutoRef<File>::Release((char *)v5 + 456);
          v22 = (_QWORD *)v46[0];
          *((_QWORD *)v5 + 57) = *(_QWORD *)v46[0];
          *v22 = 0;
          wmi::AutoRef<File>::Release(&v49);
        }
        v23 = v48;
        v24 = v47;
        v25 = (__int64 *)((char *)v5 + 136);
        v26 = (__int64 *)((char *)v5 + 104);
LABEL_44:
        v27 = *v25;
        v43 = *v26;
        v44 = (*v24 - v43) >> 1;
        v41 = v27;
        v42 = (*v23 - v27) >> 1;
        FilePathForContainerChannel = GetFilePathForContainerChannel(v53, &v41, &v43);
        v29 = utl::make_unique<EvtxFileEventSink,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,unsigned __int64 &,0>(
                v46,
                FilePathForContainerChannel,
                v25,
                &v50);
        utl::unique_ptr<EvtxFileEventSink,utl::default_delete<EvtxFileEventSink>>::operator=((char *)v5 + 464, v29);
        if ( v46[0] )
          utl::default_delete<EvtxFileEventSink>::operator()();
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v53);
        if ( !*((_QWORD *)v5 + 58) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids, 14);
          }
          v76 = 0;
          v77 = 0;
          v78 = 14;
          v79 = -1;
          v80 = 1113;
          throw (EvtException *)&v76;
        }
        v13 = v51;
      }
    }
    v30 = (EventSession *)*((_QWORD *)v5 + 12);
    if ( v30 )
    {
      v31 = 1;
      if ( !*((_BYTE *)v5 + 86) )
        EventSession::StopProcessingEvents(v30);
    }
    else
    {
      v31 = 0;
    }
    v46[0] = (char *)v5 + 472;
    AcquireSRWLockExclusive((PSRWLOCK)v5 + 59);
    Channel::ResetLogging(v5, v61, *v13, v3);
    try
    {
      Channel::ResetPublishing((WCHAR *)v5, v4, v3);
    }
    catch ( EvtException *v82 )
    {
      if ( (v86 & 1) != 0 )
      {
        v38 = v82;
        if ( !*((_BYTE *)v82 + 36) )
        {
          if ( (Microsoft_Windows_EventlogEnableBits & 1) != 0 )
            McTemplateU0qz_EventWriteTransfer(
              v32,
              &INIT_CHANNEL_PUBLISHING,
              *((unsigned int *)v82 + 6),
              *((_QWORD *)this + 17));
          *((_BYTE *)v38 + 36) = 1;
        }
      }
      throw;
    }
    if ( (_BYTE)v87 )
      goto LABEL_66;
    if ( v31 )
    {
      if ( !*((_QWORD *)v5 + 12) )
      {
        _InterlockedDecrement(&g_EnabledChannels);
        goto LABEL_65;
      }
    }
    else if ( *((_QWORD *)v5 + 12) )
    {
      _InterlockedIncrement(&g_EnabledChannels);
LABEL_65:
      *((_BYTE *)v5 + 879) = 1;
    }
LABEL_66:
    ReleaseSRWLockExclusive((PSRWLOCK)v5 + 59);
    *((_DWORD *)v5 + 20) = 0;
  }
  catch ( EvtException *v83 )
  {
    v39 = *((unsigned int *)v83 + 6);
    *((_DWORD *)this + 20) = v39;
    v40 = *((_QWORD *)this + 8);
    if ( this == *(Channel **)(v40 + 32) || this == *(Channel **)(v40 + 40) )
    {
      if ( (Microsoft_Windows_EventlogEnableBits & 0x10) != 0 )
        McTemplateU0qz_EventWriteTransfer(v33, &PRIMARY_CHANNEL_FATAL_ERROR, v39, *((_QWORD *)this + 17));
      EvtTerminateServiceNoFault(*((_DWORD *)this + 20));
    }
    throw;
  }
LABEL_17:
  LeaveCriticalSection(v52);
}

```

## disassembly

```asm
0x180002ae4  mov     r11, rsp
0x180002ae7  mov     [r11+18h], r8d
0x180002aeb  mov     [r11+10h], rdx
0x180002aef  mov     [r11+8], rcx
0x180002af3  push    rbx
0x180002af4  push    rsi
0x180002af5  push    rdi
0x180002af6  push    r12
0x180002af8  push    r13
0x180002afa  push    r14
0x180002afc  push    r15
0x180002afe  sub     rsp, 1B0h
0x180002b05  mov     r12d, r8d
0x180002b08  mov     r14, rdx
0x180002b0b  mov     rsi, rcx
0x180002b0e  lea     rax, [rcx+10h]
0x180002b12  mov     [rsp+1E8h+var_140], rax
0x180002b1a  mov     [r11-50h], rax
0x180002b1e  mov     rcx, rax; lpCriticalSection
0x180002b21  call    cs:__imp_EnterCriticalSection
0x180002b27  nop
0x180002b28  or      r13d, 0FFFFFFFFh
0x180002b2c  test    r12b, 4
0x180002b30  jz      loc_180002BC7
0x180002b36  mov     ebx, [rsi+50h]
0x180002b39  cmp     ebx, r13d
0x180002b3c  jz      loc_180002BC7
0x180002b42  xor     edi, edi
0x180002b44  test    ebx, ebx
0x180002b46  jz      loc_180002C36
0x180002b4c  lea     r15, WPP_GLOBAL_Control
0x180002b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b5a  cmp     rcx, r15
0x180002b5d  jz      short loc_180002B84
0x180002b5f  test    dword ptr [rcx+1Ch], 800h
0x180002b66  jz      short loc_180002B84
0x180002b68  cmp     byte ptr [rcx+19h], 2
0x180002b6c  jb      short loc_180002B84
0x180002b6e  lea     edx, [rdi+21h]
0x180002b71  mov     r9d, ebx
0x180002b74  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x180002b7b  mov     rcx, [rcx+10h]
0x180002b7f  call    WPP_SF_d
0x180002b84  xorps   xmm0, xmm0
0x180002b87  movdqu  [rsp+1E8h+pExceptionObject], xmm0
0x180002b90  mov     [rsp+1E8h+var_B8], rdi
0x180002b98  mov     [rsp+1E8h+var_B0], ebx
0x180002b9f  mov     [rsp+1E8h+var_AC], r13d
0x180002ba7  mov     [rsp+1E8h+var_A8], 3D7h
0x180002bb2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180002bb9  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x180002bc1  call    _CxxThrowException_0
0x180002bc7  xor     edi, edi
0x180002bc9  cmp     [rsi+55h], dil
0x180002bcd  jz      short loc_180002BDB
0x180002bcf  or      r12d, 2
0x180002bd3  mov     [rsp+1E8h+arg_10], r12d
0x180002bdb  lea     rcx, [rsi+0A8h]; this
0x180002be2  cmp     [rcx+100h], dil
0x180002be9  jz      short loc_180002C57
0x180002beb  mov     rdx, r14; struct ChannelConfigSnapshot *
0x180002bee  call    ?Equals@ChannelConfigSnapshot@@QEBA_NAEBV1@@Z; ChannelConfigSnapshot::Equals(ChannelConfigSnapshot const &)
0x180002bf3  test    al, al
0x180002bf5  jz      short loc_180002C57
0x180002bf7  lea     r15, WPP_GLOBAL_Control
0x180002bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c05  cmp     rcx, r15
0x180002c08  jz      short loc_180002C36
0x180002c0a  test    dword ptr [rcx+1Ch], 800h
0x180002c11  jz      short loc_180002C36
0x180002c13  cmp     byte ptr [rcx+19h], 4
0x180002c17  jb      short loc_180002C36
0x180002c19  mov     edx, 22h ; '"'
0x180002c1e  mov     r9, [rsi+88h]
0x180002c25  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x180002c2c  mov     rcx, [rcx+10h]
0x180002c30  call    WPP_SF_S
0x180002c35  nop
0x180002c36  mov     rcx, [rsp+1E8h+var_140]
0x180002c3e  add     rsp, 1B0h
0x180002c45  pop     r15
0x180002c47  pop     r14
0x180002c49  pop     r13
0x180002c4b  pop     r12
0x180002c4d  pop     rdi
0x180002c4e  pop     rsi
0x180002c4f  pop     rbx
0x180002c50  jmp     cs:__imp_LeaveCriticalSection
0x180002c57  mov     al, [r14+0F9h]
0x180002c5e  sub     al, 2
0x180002c60  cmp     al, 1
0x180002c62  ja      loc_180002D10
0x180002c68  cmp     [r14+0FBh], dil
0x180002c6f  jz      loc_180002D10
0x180002c75  cmp     [rsi+60h], rdi
0x180002c79  jz      loc_180002D10
0x180002c7f  cmp     [rsi+36Ch], dil
0x180002c86  jz      loc_180002D10
0x180002c8c  lea     r15, WPP_GLOBAL_Control
0x180002c93  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c9a  cmp     rcx, r15
0x180002c9d  jz      short loc_180002CC9
0x180002c9f  test    dword ptr [rcx+1Ch], 800h
0x180002ca6  jz      short loc_180002CC9
0x180002ca8  cmp     byte ptr [rcx+19h], 2
0x180002cac  jb      short loc_180002CC9
0x180002cae  mov     edx, 23h ; '#'
0x180002cb3  mov     r9d, 3AAEh
0x180002cb9  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x180002cc0  mov     rcx, [rcx+10h]
0x180002cc4  call    WPP_SF_d
0x180002cc9  xorps   xmm0, xmm0
0x180002ccc  movdqu  [rsp+1E8h+var_A0], xmm0
0x180002cd5  mov     [rsp+1E8h+var_90], rdi
0x180002cdd  mov     [rsp+1E8h+var_88], 3AAEh
0x180002ce8  mov     [rsp+1E8h+var_84], r13d
0x180002cf0  mov     [rsp+1E8h+var_80], 3EEh
0x180002cfb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180002d02  lea     rcx, [rsp+1E8h+var_A0]; pExceptionObject
0x180002d0a  call    _CxxThrowException_0
0x180002d10  lea     r15, WPP_GLOBAL_Control
0x180002d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d1e  cmp     rcx, r15
0x180002d21  jz      short loc_180002D4F
0x180002d23  test    dword ptr [rcx+1Ch], 800h
0x180002d2a  jz      short loc_180002D4F
0x180002d2c  cmp     byte ptr [rcx+19h], 4
0x180002d30  jb      short loc_180002D4F
0x180002d32  mov     edx, 24h ; '$'
0x180002d37  mov     r9, [rsi+88h]
0x180002d3e  lea     r8, WPP_90c925f5c8ff3f4567f272a23c56f0b5_Traceguids
0x180002d45  mov     rcx, [rcx+10h]
0x180002d49  call    WPP_SF_S
0x180002d4e  nop
0x180002d4f  movzx   eax, byte ptr [r14+0F8h]
0x180002d57  mov     [rsi+368h], eax
0x180002d5d  mov     rbx, [r14+0A8h]
0x180002d64  cmp     [r14+0B0h], rbx
0x180002d6b  jz      loc_180002E76
0x180002d71  mov     [rsp+1E8h+arg_18], rdi
0x180002d79  lea     rcx, [rsp+1E8h+arg_18]
0x180002d81  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x180002d86  xor     r9d, r9d; SecurityDescriptorSize
0x180002d89  mov     r8, rax; SecurityDescriptor
0x180002d8c  lea     edx, [r9+1]; StringSDRevision
0x180002d90  mov     rcx, rbx; StringSecurityDescriptor
0x180002d93  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002d99  test    eax, eax
0x180002d9b  jnz     loc_180002E57
0x180002da1  call    cs:__imp_GetLastError
0x180002da7  mov     ebx, eax
0x180002da9  lea     r14, word_1800EC961
0x180002db0  mov     [rsp+1E8h+var_138], r14
0x180002db8  mov     [rsp+1E8h+var_128], rdi
0x180002dc0  mov     [rsp+1E8h+var_120], eax
0x180002dc7  mov     [rsp+1E8h+var_11C], r13d
0x180002dcf  mov     [rsp+1E8h+var_118], 0FFFFFFFFh
0x180002dda  mov     [rsp+1E8h+var_114], dil
0x180002de2  test    r12b, 1
0x180002de6  jz      short loc_180002E08
0x180002de8  test    byte ptr cs:Microsoft_Windows_EventlogEnableBits, 2
0x180002def  jz      short loc_180002E00
0x180002df1  mov     r9, [rsi+88h]
0x180002df8  mov     r8d, eax
0x180002dfb  call    McTemplateU0qzz_EventWriteTransfer
0x180002e00  mov     [rsp+1E8h+var_114], 1
0x180002e08  mov     [rsp+1E8h+var_F0], r14
0x180002e10  mov     [rsp+1E8h+var_E8], rdi
0x180002e18  mov     [rsp+1E8h+var_E0], rdi
0x180002e20  mov     [rsp+1E8h+var_D8], ebx
0x180002e27  mov     [rsp+1E8h+var_D4], r13d
0x180002e2f  mov     [rsp+1E8h+var_D0], 0FFFFFFFFh
0x180002e3a  mov     [rsp+1E8h+var_130], rdi
0x180002e42  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180002e49  lea     rcx, [rsp+1E8h+var_F0]; pExceptionObject
0x180002e51  call    _CxxThrowException_0
0x180002e57  lea     rcx, [rsi+58h]
0x180002e5b  lea     rdx, [rsp+1E8h+arg_18]
0x180002e63  call    ?swap@?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAAXAEAV12@@Z; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::swap(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x180002e68  nop
0x180002e69  lea     rcx, [rsp+1E8h+arg_18]
0x180002e71  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x180002e76  lea     rcx, [r14+38h]
0x180002e7a  mov     [rsp+1E8h+var_F8], rcx
0x180002e82  mov     rax, [rcx+60h]
0x180002e86  mov     [rsp+1E8h+var_188], rax
0x180002e8b  mov     [rsp+1E8h+var_150], rax
0x180002e93  mov     rax, [rcx]
0x180002e96  mov     [rsp+1E8h+var_178], rax
0x180002e9b  mov     rcx, [rcx+8]
0x180002e9f  sub     rcx, rax
0x180002ea2  sar     rcx, 1
0x180002ea5  mov     [rsp+1E8h+var_170], rcx
0x180002eaa  lea     rcx, [rsi+68h]
0x180002eae  lea     rdx, [rsp+1E8h+var_178]
0x180002eb3  call    ?AssignOrThrowOOM@@YAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; AssignOrThrowOOM(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180002eb8  mov     al, [r14+0F9h]
0x180002ebf  sub     al, 2
0x180002ec1  lea     rbx, [r14+0FBh]
0x180002ec8  cmp     al, 1
0x180002eca  jbe     loc_1800031CB
0x180002ed0  mov     byte ptr [rsp+1E8h+arg_18], dil
0x180002ed8  mov     [rsp+1E8h+var_148], rbx
0x180002ee0  cmp     [rbx], dil
0x180002ee3  jz      loc_1800031D3
0x180002ee9  lea     rax, [rsi+68h]
0x180002eed  mov     [rsp+1E8h+var_108], rax
0x180002ef5  test    r12b, 2
0x180002ef9  jz      loc_180002FFF
0x180002eff  mov     rdx, [rax]
0x180002f02  lea     r8, [rax+8]
0x180002f06  mov     [rsp+1E8h+var_168], r8
0x180002f0e  mov     [rsp+1E8h+var_178], r8
0x180002f13  lea     rax, [rsi+88h]
0x180002f1a  mov     [rsp+1E8h+var_158], rax
0x180002f22  mov     rcx, [rax]
0x180002f25  lea     r9, [rax+8]
0x180002f29  mov     [rsp+1E8h+var_160], r9
0x180002f31  mov     [rsp+1E8h+var_100], r9
0x180002f39  mov     [rsp+1E8h+var_1A8], rdx
0x180002f3e  mov     rax, [r8]
0x180002f41  sub     rax, rdx
0x180002f44  sar     rax, 1
0x180002f47  mov     [rsp+1E8h+var_1A0], rax
0x180002f4c  mov     [rsp+1E8h+var_198], rcx
0x180002f51  mov     rax, [r9]
0x180002f54  sub     rax, rcx
0x180002f57  sar     rax, 1
0x180002f5a  mov     [rsp+1E8h+var_190], rax
0x180002f5f  mov     r9, [rsp+1E8h+var_188]
0x180002f64  lea     r8, [rsp+1E8h+var_1A8]
0x180002f69  lea     rdx, [rsp+1E8h+var_198]
0x180002f6e  lea     rcx, [rsp+1E8h+var_110]
0x180002f76  call    ?OpenLogWithRetry@Channel@@CA?AV?$AutoRef@VFile@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@0_K@Z; Channel::OpenLogWithRetry(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,unsigned __int64)
0x180002f7b  mov     [rsp+1E8h+var_188], rax
0x180002f80  lea     rbx, [rsi+1C8h]
0x180002f87  mov     rcx, rbx
0x180002f8a  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x180002f8f  mov     rax, [rsp+1E8h+var_188]
0x180002f94  mov     rcx, [rax]
0x180002f97  mov     [rbx], rcx
0x180002f9a  mov     [rax], rdi
0x180002f9d  lea     rcx, [rsp+1E8h+var_110]
0x180002fa5  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x180002faa  nop
0x180002fab  jmp     loc_180003095
0x180002fb0  or      r13d, 0FFFFFFFFh
0x180002fb4  xor     edi, edi
0x180002fb6  lea     r15, WPP_GLOBAL_Control
0x180002fbd  mov     rsi, [rsp+1E8h+arg_0]
0x180002fc5  mov     r12d, [rsp+1E8h+arg_10]
0x180002fcd  mov     r14, [rsp+1E8h+arg_8]
0x180002fd5  mov     rcx, [rsp+1E8h+var_108]
0x180002fdd  mov     r9, [rsp+1E8h+var_100]
0x180002fe5  mov     byte ptr [rsp+1E8h+arg_18], dil
0x180002fed  mov     rbx, [rsp+1E8h+var_158]
0x180002ff5  mov     r8, [rsp+1E8h+var_178]
0x180002ffa  jmp     loc_1800030B0
0x180002fff  mov     rcx, [rax]
0x180003002  lea     r8, [rax+8]
0x180003006  mov     [rsp+1E8h+var_168], r8
0x18000300e  lea     rax, [rsi+88h]
0x180003015  mov     rdx, [rax]
0x180003018  lea     r9, [rax+8]
0x18000301c  mov     [rsp+1E8h+var_160], r9
0x180003024  mov     [rsp+1E8h+var_198], rcx
0x180003029  mov     rax, [r8]
0x18000302c  sub     rax, rcx
0x18000302f  sar     rax, 1
0x180003032  mov     [rsp+1E8h+var_190], rax
0x180003037  mov     [rsp+1E8h+var_1A8], rdx
0x18000303c  mov     rax, [r9]
0x18000303f  sub     rax, rdx
0x180003042  sar     rax, 1
0x180003045  mov     [rsp+1E8h+var_1A0], rax
0x18000304a  mov     r9, [rsp+1E8h+var_188]
0x18000304f  lea     r8, [rsp+1E8h+var_198]
0x180003054  lea     rdx, [rsp+1E8h+var_1A8]
0x180003059  lea     rcx, [rsp+1E8h+var_158]
0x180003061  call    ?OpenLogWithRetry@Channel@@CA?AV?$AutoRef@VFile@@@wmi@@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@0_K@Z; Channel::OpenLogWithRetry(tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>,unsigned __int64)
0x180003066  mov     [rsp+1E8h+var_178], rax
0x18000306b  lea     rbx, [rsi+1C8h]
0x180003072  mov     rcx, rbx
0x180003075  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x18000307a  mov     rax, [rsp+1E8h+var_178]
0x18000307f  mov     rcx, [rax]
0x180003082  mov     [rbx], rcx
0x180003085  mov     [rax], rdi
0x180003088  lea     rcx, [rsp+1E8h+var_158]
0x180003090  call    ?Release@?$AutoRef@VFile@@@wmi@@QEAAXXZ; wmi::AutoRef<File>::Release(void)
0x180003095  mov     r9, [rsp+1E8h+var_160]
0x18000309d  mov     r8, [rsp+1E8h+var_168]
0x1800030a5  lea     rbx, [rsi+88h]
0x1800030ac  lea     rcx, [rsi+68h]
0x1800030b0  mov     rax, [rcx]
0x1800030b3  mov     rdx, [rbx]
0x1800030b6  mov     [rsp+1E8h+var_198], rax
0x1800030bb  mov     rcx, [r8]
0x1800030be  sub     rcx, rax
0x1800030c1  sar     rcx, 1
  ... truncated ...
```
