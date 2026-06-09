# CServerListEntry::CallServer(ACTIVATION_PARAMS *,int,long *)

- ea: `0x18002d440`
- end: `0x18002e361`
- name: `?CallServer@CServerListEntry@@QEAAHPEAUACTIVATION_PARAMS@@HPEAJ@Z`
- size: `3873`
- prototype: `__int64 __fastcall(CServerListEntry *__hidden this, struct ACTIVATION_PARAMS *, int, int *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009054`

## callees

- `0x180003194`
- `0x180003840`
- `0x180005b40`
- `0x18000b398`
- `0x1800210f8`
- `0x180021120`
- `0x1800250ac`
- `0x18002c408`
- `0x18002c81c`
- `0x18002c9b0`
- `0x18002d0ec`
- `0x18002d14c`
- `0x18002d1a0`
- `0x18002d3e0`
- `0x18002d440`
- `0x18002e370`
- `0x18002efd4`
- `0x18002f094`
- `0x18002f0ec`
- `0x18002f5a0`
- `0x18002f670`
- `0x180031a78`
- `0x18005ac00`
- `0x18006313c`
- `0x180087cd0`
- `0x180095c0c`
- `0x1800968fc`
- `0x18009e160`
- `0x18009e1f4`
- `0x1800a6b6c`
- `0x1800a6e50`
- `0x1800b7ac0`
- `0x180114010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002d6a0`
- `RPCRT4!UuidCreate` at `0x18002d6a0`
- `RPCRT4!I_RpcExceptionFilter` at `0x180112f16`
- `RPCRT4!I_RpcExceptionFilter` at `0x180112f38`
- `RPCRT4!I_RpcExceptionFilter` at `0x180112f16`
- `RPCRT4!I_RpcExceptionFilter` at `0x180112f38`
- `RPCRT4!NdrClientCall2` at `0x18002dba4`
- `RPCRT4!NdrClientCall2` at `0x18002dcf3`
- `RPCRT4!NdrClientCall2` at `0x18002dba4`
- `RPCRT4!NdrClientCall2` at `0x18002dcf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002df64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002df64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d932`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002da2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d932`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002da2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d73a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d99b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d73a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d99b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e258`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d4de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002d4de`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d4c0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d4c0`

## string_xrefs

- `0x18002d883`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002d8e4`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002dafb`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002dc20`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002dc5a`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002de15`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002de73`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002e0d9`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002e1df`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002e2c5`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002e2f1`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002e34b`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002dd9d`: `Failed call into server. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002dd89`: `Server returned failure. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002dc42`: `onecore\com\combase\inc\ComGuid.hpp`
- `0x18002dfc8`: `onecore\com\combase\rpcss\objex\soxid.hxx`
- `0x18002e09f`: `Server process died. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002e045`: `Server TCP port not open. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002e198`: `Failed to copy ROT data. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002e116`: `Failed to get binding handle. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002df16`: `Call security blocked activation: ACID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002e287`: `Transforming call failure from %#x: CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002e313`: `Call security blocked activation call: CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002e2e0`: `Server stopping: CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`

## pseudocode

```c
__int64 __fastcall CServerListEntry::CallServer(
        CServerListEntry *this,
        struct ACTIVATION_PARAMS *a2,
        int a3,
        unsigned int *a4)
{
  const char *v7; // r9
  __int64 v8; // r12
  unsigned int v9; // ebx
  int v10; // r13d
  const WCHAR *v11; // r12
  __int64 v12; // rcx
  int v13; // r14d
  __int64 v14; // rax
  int Interface; // eax
  unsigned int v16; // r9d
  int v17; // eax
  int v18; // eax
  CActivationState *v19; // rcx
  struct CActivationState *v20; // rax
  int v21; // ecx
  __int64 v22; // rcx
  const char *v23; // rax
  char *v24; // rcx
  __int64 v25; // rdx
  const char *v26; // r8
  CActivationStateList *v27; // rcx
  int v28; // eax
  ActivationPropertiesOut *v29; // rax
  ActivationProperties *v30; // rax
  const char *v31; // r9
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int v40; // edx
  int v41; // eax
  int v42; // esi
  int v43; // eax
  int v44; // esi
  int ProcessHandle; // eax
  int v46; // esi
  int v47; // eax
  int v48; // esi
  bool v49; // zf
  __int64 v50; // rdx
  const char *v51; // rax
  const char *v52; // r8
  __int64 v53; // rdx
  const char *v54; // rax
  const char *v55; // r8
  struct tagInterfaceData *v56; // rcx
  struct tagInterfaceData *v57; // rdx
  int v58; // [rsp+20h] [rbp-228h]
  int v59; // [rsp+20h] [rbp-228h]
  __int64 v60; // [rsp+30h] [rbp-218h]
  __int64 v61; // [rsp+30h] [rbp-218h]
  __int64 v62; // [rsp+30h] [rbp-218h]
  __int64 v63; // [rsp+40h] [rbp-208h]
  __int64 v64; // [rsp+40h] [rbp-208h]
  __int64 v65; // [rsp+40h] [rbp-208h]
  unsigned int v66; // [rsp+64h] [rbp-1E4h]
  char *v68; // [rsp+70h] [rbp-1D8h] BYREF
  int v69; // [rsp+78h] [rbp-1D0h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v71; // [rsp+88h] [rbp-1C0h]
  int v72; // [rsp+90h] [rbp-1B8h]
  struct _GUID v73; // [rsp+A0h] [rbp-1A8h] BYREF
  char *StringRawBuffer; // [rsp+B0h] [rbp-198h]
  int v75; // [rsp+B8h] [rbp-190h]
  __int64 v76; // [rsp+C0h] [rbp-188h]
  __int64 v77; // [rsp+C8h] [rbp-180h]
  LPVOID lpMem; // [rsp+D0h] [rbp-178h] BYREF
  struct tagInterfaceData *v79; // [rsp+D8h] [rbp-170h] BYREF
  int v80; // [rsp+E0h] [rbp-168h]
  int v81; // [rsp+E4h] [rbp-164h]
  void *v82[2]; // [rsp+E8h] [rbp-160h] BYREF
  CServerListEntry *v83; // [rsp+F8h] [rbp-150h]
  struct CActivationState *v84; // [rsp+100h] [rbp-148h]
  int v85; // [rsp+108h] [rbp-140h]
  __int128 v86; // [rsp+110h] [rbp-138h] BYREF
  __int64 v87; // [rsp+120h] [rbp-128h]
  unsigned int *v88; // [rsp+128h] [rbp-120h]
  CServerListEntry *v89; // [rsp+130h] [rbp-118h]
  struct ACTIVATION_PARAMS *v90; // [rsp+138h] [rbp-110h]
  unsigned int *v91; // [rsp+140h] [rbp-108h]
  char *v92; // [rsp+148h] [rbp-100h]
  __int64 v93; // [rsp+150h] [rbp-F8h]
  __int64 v94; // [rsp+158h] [rbp-F0h]
  __int64 v95; // [rsp+160h] [rbp-E8h]
  const WCHAR *v96; // [rsp+168h] [rbp-E0h]
  const WCHAR *v97; // [rsp+170h] [rbp-D8h]
  CToken **v98; // [rsp+178h] [rbp-D0h]
  _BYTE v99[48]; // [rsp+180h] [rbp-C8h] BYREF
  OLECHAR sz[40]; // [rsp+1B0h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  hObject = a4;
  v83 = this;
  v88 = a4;
  v89 = this;
  v90 = a2;
  v91 = a4;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 60), sz, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\com\\combase\\inc\\ComGuid.hpp",
      v7);
  StringRawBuffer = (char *)WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
  v8 = *((_QWORD *)a2 + 1);
  v9 = 0;
  if ( v8 )
    v10 = *(_DWORD *)(v8 + 88);
  else
    v10 = 0;
  v72 = v10;
  if ( v8 )
    v11 = *(const WCHAR **)(v8 + 384);
  else
    v11 = &Class;
  v82[1] = (void *)v11;
  v12 = *((_QWORD *)this + 12);
  v13 = *(_DWORD *)(v12 + 88);
  v14 = *(_QWORD *)(v12 + 384);
  v71 = v14;
  if ( *((_BYTE *)a2 + 188) )
  {
    if ( *((_DWORD *)a2 + 97) )
    {
      v49 = !CProcess::ServerTCPPortOpen((CProcess *)v12, *(void **)a2);
      v14 = v71;
      if ( v49 )
      {
        _InterlockedAdd((volatile signed __int32 *)this + 37, 1u);
        *a4 = -2147023174;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x54D,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
          (const char *)0x800706BALL,
          (int)"Server TCP port not open. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)",
          (const char *)sz,
          v10,
          v11,
          v13,
          v14);
        return 1;
      }
    }
  }
  v77 = v14;
  if ( (unsigned int)CServerListEntry::EnsureRpcHandle(this, a3) )
  {
    v76 = *(_QWORD *)(*((_QWORD *)this + 13) + 16LL);
    *(_DWORD *)(*((_QWORD *)a2 + 19) + 4LL) |= 8u;
    if ( (*((_BYTE *)this + 128) & 4) != 0 )
      *(_DWORD *)(*((_QWORD *)a2 + 45) + 56LL) = 1;
    if ( *((_DWORD *)a2 + 14) == 2 )
    {
      v56 = (struct tagInterfaceData *)*((_QWORD *)a2 + 29);
      if ( v56 )
      {
        v57 = AllocateAndCopy(v56);
        if ( !v57 )
        {
          *a4 = -2147024882;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0x591,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
            (const char *)0x8007000ELL,
            (int)"Failed to copy ROT data. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)",
            (const char *)sz,
            v10,
            v11,
            v13,
            v71);
          return 1;
        }
        (*(void (__fastcall **)(_QWORD, struct tagInterfaceData *))(**((_QWORD **)a2 + 46) + 72LL))(
          *((_QWORD *)a2 + 46),
          v57);
      }
    }
    *(_OWORD *)(*((_QWORD *)a2 + 45) + 32LL) = *(_OWORD *)((char *)a2 + 60);
    v82[0] = 0;
    Interface = ActivationPropertiesIn::QueryInterface(
                  *((ActivationPropertiesIn **)a2 + 43),
                  &IID_ISpecialSystemProperties,
                  v82);
    *a4 = Interface;
    if ( Interface < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5A0,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
        (const char *)(unsigned int)Interface,
        v58);
      MicrosoftTelemetryAssertTriggeredNoArgs(v36);
      return 1;
    }
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v82[0] + 168LL))(v82[0], *((unsigned int *)this + 38));
    (*(void (__fastcall **)(void *))(*(_QWORD *)v82[0] + 16LL))(v82[0]);
    if ( !*((_BYTE *)a2 + 189) )
    {
LABEL_13:
      v80 = v10;
      v96 = v11;
      v85 = v13;
      v95 = v71;
      v68 = StringRawBuffer;
      v81 = v10;
      v97 = v11;
      v94 = v76;
      v75 = 0;
      UuidCreate((UUID *)(*((_QWORD *)a2 + 20) + 24LL));
      lpMem = 0;
      v79 = 0;
      v69 = 0;
      v17 = ActPropsMarshalHelper(
              *((struct IActivationProperties **)a2 + 43),
              &IID_IActivationPropertiesIn,
              0,
              v16,
              (struct tagMInterfacePointer **)&lpMem);
      *a4 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5D8,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
          (const char *)(unsigned int)v17,
          v59);
      }
      else
      {
        v98 = (CToken **)((char *)a2 + 16);
        v18 = CToken::Impersonate(*((CToken **)a2 + 2), 1, &v69);
        *a4 = v18;
        if ( v18 >= 0 )
        {
          v19 = (CActivationState *)HeapAlloc(g_hHeap, 0, 0x48u);
          if ( v19 )
          {
            v73 = *(struct _GUID *)((char *)a2 + 60);
            v20 = CActivationState::CActivationState(
                    v19,
                    &v73,
                    *(_DWORD *)(*((_QWORD *)v83 + 12) + 88LL),
                    *((_DWORD *)a2 + 60),
                    0);
          }
          else
          {
            v20 = 0;
          }
          v84 = v20;
          if ( v20 )
            CActivationStateList::Insert(v19, v20);
          SaveRestoreProtocolVersionForCallToLocalServer::SaveRestoreProtocolVersionForCallToLocalServer(
            (SaveRestoreProtocolVersionForCallToLocalServer *)&v86,
            a2);
          v21 = *((_DWORD *)a2 + 14);
          if ( v21 )
          {
            v22 = (unsigned int)(v21 - 1);
            if ( (unsigned int)v22 < 2 )
            {
              v37 = *((_QWORD *)a2 + 22);
              v38 = *((_QWORD *)a2 + 21);
              v39 = *((_QWORD *)a2 + 20);
              *(_QWORD *)&v73.Data1 = 0;
              *(CLIENT_CALL_RETURN *)&v73.Data1 = NdrClientCall2(
                                                    &stru_1801178F0,
                                                    &byte_180123AD0,
                                                    v76,
                                                    *((_QWORD *)a2 + 19),
                                                    v39,
                                                    v38,
                                                    v37,
                                                    0,
                                                    lpMem,
                                                    &v79);
              *a4 = v73.Data1;
            }
            else
            {
              *a4 = -2147418113;
            }
          }
          else
          {
            v33 = *((_QWORD *)a2 + 22);
            v34 = *((_QWORD *)a2 + 21);
            v35 = *((_QWORD *)a2 + 20);
            *(_QWORD *)&v73.Data1 = 0;
            *(CLIENT_CALL_RETURN *)&v73.Data1 = NdrClientCall2(
                                                  &stru_1801178F0,
                                                  &byte_180123A88,
                                                  v76,
                                                  *((_QWORD *)a2 + 19),
                                                  v35,
                                                  v34,
                                                  v33,
                                                  lpMem,
                                                  &v79);
            *a4 = v73.Data1;
          }
          if ( **((_QWORD **)a2 + 22) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v22);
          if ( *(_QWORD *)(*((_QWORD *)a2 + 22) + 16LL) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v22);
          *(_QWORD *)&v73.Data1 = retaddr;
          if ( *((_BYTE *)a2 + 432) )
          {
            v66 = 1594;
            v23 = "Server returned failure. ACID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
            v24 = v68;
            v25 = 1592;
            v26 = "Failed call into server. ACID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
          }
          else
          {
            v66 = 1601;
            v23 = "Server returned failure. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
            v24 = (char *)sz;
            v25 = 1599;
            v26 = "Failed call into server. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
          }
          v92 = v24;
          v93 = (__int64)v23;
          LODWORD(v63) = v85;
          LODWORD(v60) = v80;
          wil::details::in1diag3::Log_IfWin32ErrorMsg(
            retaddr,
            (void *)v25,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
            0,
            (unsigned int)v26,
            v24,
            v60,
            v96,
            v63,
            v95);
          LODWORD(v64) = v13;
          LODWORD(v61) = v81;
          wil::details::in1diag3::Log_IfFailedMsg(
            *(wil::details::in1diag3 **)&v73.Data1,
            (void *)v66,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
            (const char *)*(unsigned int *)hObject,
            v93,
            v92,
            v61,
            v97,
            v64,
            v77);
          if ( v84 )
          {
            CActivationStateList::Remove(v27, v84);
            CActivationState::`scalar deleting destructor'(v84, v40);
          }
          CToken::Revert(*v98, v69);
          HeapFree(g_hHeap, 0, lpMem);
          if ( !*a4 )
          {
            *(_QWORD *)&v73.Data1 = 0;
            v28 = ValidateAndDoFixups(v79, (struct tagInterfaceData **)&v73);
            *a4 = v28;
            if ( v28 >= 0 )
            {
              GenericStream::GenericStream((GenericStream *)v99, *(struct tagInterfaceData **)&v73.Data1);
              v29 = (ActivationPropertiesOut *)HeapAlloc(g_hHeap, 0, 0x3C0u);
              if ( v29 )
                v30 = ActivationPropertiesOut::ActivationPropertiesOut(v29, 0);
              else
                v30 = 0;
              *((_QWORD *)a2 + 44) = v30;
              if ( v30 )
              {
                *(_QWORD *)&v73.Data1 = 0;
                v69 = ActivationProperties::UnmarshalInterface(
                        v30,
                        (struct IStream *)v99,
                        &IID_IActivationPropertiesOut,
                        (void **)&v73);
                if ( v69 < 0 )
                {
                  ActivationPropertiesOut::Release(*((ActivationPropertiesOut **)a2 + 44));
                  *((_QWORD *)a2 + 44) = 0;
                  *a4 = v69;
                }
                else
                {
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v73.Data1 + 16LL))(*(_QWORD *)&v73.Data1);
                }
              }
              else
              {
                *a4 = -2147024882;
              }
              GenericStream::~GenericStream((GenericStream *)v99);
            }
            HeapFree(g_hHeap, 0, v79);
          }
          **(_DWORD **)(v86 + 152) = DWORD2(v86);
          if ( *a4 != -2146959352 )
            return 1;
          v31 = (const char *)*a4;
          LODWORD(v65) = v13;
          LODWORD(v62) = v10;
          if ( *((_BYTE *)a2 + 432) )
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x6BD,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
              v31,
              (int)"Server stopping: ACID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)",
              StringRawBuffer,
              v62,
              v11,
              v65,
              v71);
          else
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x6C2,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
              v31,
              (int)"Server stopping: CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)",
              (const char *)sz,
              v62,
              v11,
              v65,
              v71);
          LOBYTE(v9) = *a4 == -2147417856;
          return v9;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5E2,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
          (const char *)(unsigned int)v18,
          v59);
      }
      return 1;
    }
    v86 = 0;
    v87 = 0;
    v47 = NegotiateContainerVersion(
            *((const struct CONTAINERVERSION_FOR_NEGOTIATION **)a2 + 76),
            (const struct CONTAINERVERSION *)(*(_QWORD *)(*((_QWORD *)this + 12) + 568LL) + 72LL),
            (struct CONTAINERVERSION *)&v86);
    v48 = v47;
    if ( v47 >= 0 )
      v48 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\soxid.hxx",
        (const char *)(unsigned int)v47,
        v58);
    *a4 = v48;
    if ( v48 >= 0 )
    {
      v68 = 0;
      v41 = ActivationPropertiesIn::QueryInterface(
              *((ActivationPropertiesIn **)a2 + 43),
              &GUID_9fc104cb_0379_43b5_a1a0_ce1260700e0a,
              (void **)&v68);
      v42 = v41;
      *a4 = v41;
      if ( v41 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5B9,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
          (const char *)(unsigned int)v41,
          v58);
      if ( v42 >= 0 )
      {
        v43 = (*(__int64 (__fastcall **)(char *, __int128 *))(*(_QWORD *)v68 + 88LL))(v68, &v86);
        v44 = v43;
        *a4 = v43;
        if ( v43 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x5BF,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
            (const char *)(unsigned int)v43,
            v58);
        if ( v44 >= 0 )
        {
          wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v68);
          ClearContainerVersion((struct CONTAINERVERSION *)&v86);
          goto LABEL_13;
        }
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v68);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B2,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
        (const char *)(unsigned int)v48,
        v58);
    }
    ClearContainerVersion((struct CONTAINERVERSION *)&v86);
    return 1;
  }
  hObject = 0;
  ProcessHandle = CProcess::GetProcessHandle(*((CProcess **)this + 12), 0x100000u, &hObject);
  if ( ProcessHandle < 0 )
  {
    v46 = ProcessHandle == -2147024809;
  }
  else
  {
    v46 = IsProcessTerminated(hObject);
    CloseHandle(hObject);
  }
  if ( !v46 )
  {
    *a4 = -2147024882;
    if ( *((_BYTE *)a2 + 432) )
    {
      v53 = 1389;
      v54 = "Failed to get binding handle. ACID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
      v55 = StringRawBuffer;
    }
    else
    {
      v53 = 1394;
      v54 = "Failed to get binding handle. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
      v55 = (const char *)sz;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v53,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
      (const char *)0x8007000ELL,
      (int)v54,
      v55,
      v10,
      v11,
      v13,
      v77);
    return 1;
  }
  *a4 = -2147023174;
  if ( *((_BYTE *)a2 + 432) )
  {
    v50 = 1374;
    v51 = "Server process died. ACID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
    v52 = StringRawBuffer;
  }
  else
  {
    v50 = 1379;
    v51 = "Server process died. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)";
    v52 = (const char *)sz;
  }
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)v50,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\servers.cxx",
    (const char *)0x800706BALL,
    (int)v51,
    v52,
    v10,
    v11,
    v13,
    v77);
  return 0;
}

```

## disassembly

```asm
0x18002d440  push    rbx
0x18002d442  push    rsi
0x18002d443  push    rdi
0x18002d444  push    r12
0x18002d446  push    r13
0x18002d448  push    r14
0x18002d44a  push    r15
0x18002d44c  sub     rsp, 210h
0x18002d453  mov     rax, cs:__security_cookie
0x18002d45a  xor     rax, rsp
0x18002d45d  mov     [rsp+248h+var_48], rax
0x18002d465  mov     rax, r9
0x18002d468  mov     [rsp+248h+hObject], rax
0x18002d470  mov     dword ptr [rsp+248h+var_1E4+4], r8d
0x18002d475  mov     rdi, rdx
0x18002d478  mov     rsi, rcx
0x18002d47b  mov     [rsp+248h+var_150], rcx
0x18002d483  mov     [rsp+248h+var_120], rax
0x18002d48b  mov     [rsp+248h+var_118], rcx
0x18002d493  mov     [rsp+248h+var_110], rdx
0x18002d49b  mov     r15, r9
0x18002d49e  mov     [rsp+248h+var_108], r9
0x18002d4a6  mov     rbx, [rsp+248h]
0x18002d4ae  lea     rcx, [rdx+3Ch]; rguid
0x18002d4b2  mov     r8d, 27h ; '''; cchMax
0x18002d4b8  lea     rdx, [rsp+248h+sz]; lpsz
0x18002d4c0  call    cs:__imp_StringFromGUID2
0x18002d4c7  nop     dword ptr [rax+rax+00h]
0x18002d4cc  cmp     eax, 27h ; '''
0x18002d4cf  jnz     loc_18002DC42
0x18002d4d5  xor     edx, edx; length
0x18002d4d7  mov     rcx, [rdi+1B8h]; string
0x18002d4de  call    cs:__imp_WindowsGetStringRawBuffer
0x18002d4e5  nop     dword ptr [rax+rax+00h]
0x18002d4ea  mov     [rsp+248h+var_198], rax
0x18002d4f2  mov     r12, [rdi+8]
0x18002d4f6  xor     ebx, ebx
0x18002d4f8  test    r12, r12
0x18002d4fb  jz      loc_18002DDD0
0x18002d501  mov     r13d, [r12+58h]
0x18002d506  mov     [rsp+248h+var_1B8], r13d
0x18002d50e  test    r12, r12
0x18002d511  jz      loc_18002DDD8
0x18002d517  mov     r12, [r12+180h]
0x18002d51f  mov     [rsp+248h+var_158], r12
0x18002d527  mov     rcx, [rsi+60h]; this
0x18002d52b  mov     r14d, [rcx+58h]
0x18002d52f  mov     [rsp+248h+var_1E8], r14d
0x18002d534  mov     rax, [rcx+180h]
0x18002d53b  mov     [rsp+248h+var_1C0], rax
0x18002d543  cmp     [rdi+0BCh], bl
0x18002d549  jnz     loc_18002DFDE
0x18002d54f  mov     [rsp+248h+var_1DC], r14d
0x18002d554  mov     [rsp+248h+var_180], rax
0x18002d55c  mov     edx, dword ptr [rsp+248h+var_1E4+4]; int
0x18002d560  mov     rcx, rsi; this
0x18002d563  call    ?EnsureRpcHandle@CServerListEntry@@QEAAHH@Z; CServerListEntry::EnsureRpcHandle(int)
0x18002d568  test    eax, eax
0x18002d56a  jz      loc_18002DF27
0x18002d570  mov     rax, [rsi+68h]
0x18002d574  mov     rax, [rax+10h]
0x18002d578  mov     [rsp+248h+var_188], rax
0x18002d580  mov     rax, [rdi+98h]
0x18002d587  or      dword ptr [rax+4], 8
0x18002d58b  mov     al, [rsi+80h]
0x18002d591  mov     r14d, 1
0x18002d597  test    al, 4
0x18002d599  jnz     loc_18002E130
0x18002d59f  cmp     dword ptr [rdi+38h], 2
0x18002d5a3  jz      loc_18002E140
0x18002d5a9  mov     rax, [rdi+168h]
0x18002d5b0  movups  xmm0, xmmword ptr [rdi+3Ch]
0x18002d5b4  movdqu  xmmword ptr [rax+20h], xmm0
0x18002d5b9  mov     [rsp+248h+var_160], rbx
0x18002d5c1  lea     r8, [rsp+248h+var_160]; void **
0x18002d5c9  lea     rdx, IID_ISpecialSystemProperties; struct _GUID *
0x18002d5d0  mov     rcx, [rdi+158h]; this
0x18002d5d7  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x18002d5dc  mov     dword ptr [rsp+248h+var_1E4+4], eax
0x18002d5e0  mov     [r15], eax
0x18002d5e3  mov     rcx, [rsp+248h]; this
0x18002d5eb  test    eax, eax
0x18002d5ed  js      loc_18002DC57
0x18002d5f3  mov     rcx, [rsp+248h+var_160]
0x18002d5fb  mov     rax, [rcx]
0x18002d5fe  mov     edx, [rsi+98h]
0x18002d604  mov     rax, [rax+0A8h]
0x18002d60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d610  mov     rcx, [rsp+248h+var_160]
0x18002d618  mov     rax, [rcx]
0x18002d61b  mov     rax, [rax+10h]
0x18002d61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d624  cmp     [rdi+0BDh], bl
0x18002d62a  jnz     loc_18002DF7B
0x18002d630  mov     [rsp+248h+var_168], r13d
0x18002d638  mov     [rsp+248h+var_E0], r12
0x18002d640  mov     eax, [rsp+248h+var_1E8]
0x18002d644  mov     [rsp+248h+var_140], eax
0x18002d64b  mov     rax, [rsp+248h+var_1C0]
0x18002d653  mov     [rsp+248h+var_E8], rax
0x18002d65b  mov     r8, [rsp+248h+var_198]
0x18002d663  mov     [rsp+248h+var_1D8], r8
0x18002d668  mov     esi, ebx
0x18002d66a  mov     [rsp+248h+var_164], r13d
0x18002d672  mov     [rsp+248h+var_D8], r12
0x18002d67a  mov     rax, [rsp+248h+var_188]
0x18002d682  mov     [rsp+248h+var_F0], rax
0x18002d68a  mov     [rsp+248h+var_190], ebx
0x18002d691  mov     dword ptr [rsp+248h+var_1E4+4], ebx
0x18002d695  mov     rcx, [rdi+0A0h]
0x18002d69c  add     rcx, 18h; Uuid
0x18002d6a0  call    cs:__imp_UuidCreate
0x18002d6a7  nop     dword ptr [rax+rax+00h]
0x18002d6ac  mov     [rsp+248h+lpMem], rbx
0x18002d6b4  mov     [rsp+248h+var_170], rbx
0x18002d6bc  mov     [rsp+248h+var_1D0], ebx
0x18002d6c0  lea     rax, [rsp+248h+lpMem]
0x18002d6c8  mov     [rsp+248h+var_228], rax; int
0x18002d6cd  xor     r8d, r8d; unsigned int
0x18002d6d0  lea     rdx, IID_IActivationPropertiesIn; struct _GUID *
0x18002d6d7  mov     rcx, [rdi+158h]; struct IActivationProperties *
0x18002d6de  call    ?ActPropsMarshalHelper@@YAJPEAUIActivationProperties@@AEBU_GUID@@KKPEAPEAUtagMInterfacePointer@@@Z; ActPropsMarshalHelper(IActivationProperties *,_GUID const &,ulong,ulong,tagMInterfacePointer * *)
0x18002d6e3  mov     dword ptr [rsp+248h+var_1E4], eax
0x18002d6e7  mov     [r15], eax
0x18002d6ea  mov     rcx, [rsp+248h]; this
0x18002d6f2  test    eax, eax
0x18002d6f4  js      loc_18002DAF8
0x18002d6fa  lea     rax, [rdi+10h]
0x18002d6fe  mov     [rsp+248h+var_D0], rax
0x18002d706  lea     r8, [rsp+248h+var_1D0]; int *
0x18002d70b  mov     edx, r14d; int
0x18002d70e  mov     rcx, [rax]; this
0x18002d711  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x18002d716  mov     dword ptr [rsp+248h+var_1E4], eax
0x18002d71a  mov     [r15], eax
0x18002d71d  mov     rcx, [rsp+248h]; this
0x18002d725  test    eax, eax
0x18002d727  js      loc_18002DC1D
0x18002d72d  xor     edx, edx; dwFlags
0x18002d72f  lea     r8d, [rdx+48h]; dwBytes
0x18002d733  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002d73a  call    cs:__imp_HeapAlloc
0x18002d741  nop     dword ptr [rax+rax+00h]
0x18002d746  mov     rcx, rax; this
0x18002d749  test    rax, rax
0x18002d74c  jz      loc_18002DDA9
0x18002d752  movups  xmm0, xmmword ptr [rdi+3Ch]
0x18002d756  movdqu  xmmword ptr [rsp+248h+var_1A8.Data1], xmm0
0x18002d75f  mov     rax, [rsp+248h+var_150]
0x18002d767  mov     r8, [rax+60h]
0x18002d76b  mov     [rsp+248h+var_228], rbx; void *
0x18002d770  mov     r9d, [rdi+0F0h]; unsigned int
0x18002d777  mov     r8d, [r8+58h]; unsigned int
0x18002d77b  lea     rdx, [rsp+248h+var_1A8]; struct _GUID *
0x18002d783  call    ??0CActivationState@@QEAA@U_GUID@@KKPEAX@Z; CActivationState::CActivationState(_GUID,ulong,ulong,void *)
0x18002d788  mov     [rsp+248h+var_148], rax
0x18002d790  test    rax, rax
0x18002d793  jz      short loc_18002D79D
0x18002d795  mov     rdx, rax; struct CActivationState *
0x18002d798  call    ?Insert@CActivationStateList@@QEAAXPEAVCActivationState@@@Z; CActivationStateList::Insert(CActivationState *)
0x18002d79d  mov     rdx, rdi; struct ACTIVATION_PARAMS *
0x18002d7a0  lea     rcx, [rsp+248h+var_138]; this
0x18002d7a8  call    ??0SaveRestoreProtocolVersionForCallToLocalServer@@QEAA@PEAUACTIVATION_PARAMS@@@Z; SaveRestoreProtocolVersionForCallToLocalServer::SaveRestoreProtocolVersionForCallToLocalServer(ACTIVATION_PARAMS *)
0x18002d7ad  mov     ecx, [rdi+38h]
0x18002d7b0  test    ecx, ecx
0x18002d7b2  jz      loc_18002DB3F
0x18002d7b8  sub     ecx, 1
0x18002d7bb  jz      loc_18002DC89
0x18002d7c1  cmp     ecx, 1
0x18002d7c4  jz      loc_18002DC89
0x18002d7ca  mov     dword ptr [r15], 8000FFFFh
0x18002d7d1  mov     rax, [rdi+0B0h]
0x18002d7d8  cmp     [rax], rbx
0x18002d7db  jnz     loc_18002E1FD
0x18002d7e1  mov     rax, [rdi+0B0h]
0x18002d7e8  cmp     [rax+10h], rbx
0x18002d7ec  jnz     loc_18002E207
0x18002d7f2  mov     rax, [rsp+248h]
0x18002d7fa  mov     r9d, esi; char *
0x18002d7fd  mov     qword ptr [rsp+248h+var_1A8.Data1], rax
0x18002d805  mov     r10, [rsp+248h]
0x18002d80d  cmp     [rdi+1B0h], bl
0x18002d813  jz      loc_18002DD81
0x18002d819  mov     dword ptr [rsp+248h+var_1E4], 63Ah
0x18002d821  lea     rax, aServerReturned; "Server returned failure. ACID:%ls, Clie"...
0x18002d828  mov     rcx, [rsp+248h+var_1D8]
0x18002d82d  mov     edx, 638h; void *
0x18002d832  lea     r8, aFailedCallInto_0; "Failed call into server. ACID:%ls, Clie"...
0x18002d839  mov     [rsp+248h+var_100], rcx
0x18002d841  mov     [rsp+248h+var_F8], rax
0x18002d849  mov     rax, [rsp+248h+var_E8]
0x18002d851  mov     [rsp+248h+var_200], rax
0x18002d856  mov     eax, [rsp+248h+var_140]
0x18002d85d  mov     dword ptr [rsp+248h+var_208], eax
0x18002d861  mov     rax, [rsp+248h+var_E0]
0x18002d869  mov     [rsp+248h+var_210], rax
0x18002d86e  mov     eax, [rsp+248h+var_168]
0x18002d875  mov     dword ptr [rsp+248h+var_218], eax
0x18002d879  mov     [rsp+248h+var_220], rcx; char *
0x18002d87e  mov     [rsp+248h+var_228], r8; unsigned int
0x18002d883  lea     r8, aOnecoreComComb_24; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18002d88a  mov     rcx, r10; this
0x18002d88d  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002d892  mov     rax, [rsp+248h+var_180]
0x18002d89a  mov     [rsp+248h+var_200], rax
0x18002d89f  mov     eax, [rsp+248h+var_1DC]
0x18002d8a3  mov     dword ptr [rsp+248h+var_208], eax
0x18002d8a7  mov     rax, [rsp+248h+var_D8]
0x18002d8af  mov     [rsp+248h+var_210], rax
0x18002d8b4  mov     eax, [rsp+248h+var_164]
0x18002d8bb  mov     dword ptr [rsp+248h+var_218], eax
0x18002d8bf  mov     rax, [rsp+248h+var_100]
0x18002d8c7  mov     [rsp+248h+var_220], rax; char *
0x18002d8cc  mov     rax, [rsp+248h+var_F8]
0x18002d8d4  mov     [rsp+248h+var_228], rax; __int64
0x18002d8d9  mov     rax, [rsp+248h+hObject]
0x18002d8e1  mov     r9d, [rax]; char *
0x18002d8e4  lea     r8, aOnecoreComComb_24; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x18002d8eb  mov     edx, dword ptr [rsp+248h+var_1E4]; void *
0x18002d8ef  mov     rcx, qword ptr [rsp+248h+var_1A8.Data1]; this
0x18002d8f7  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002d8fc  mov     rax, [rsp+248h+var_148]
0x18002d904  test    rax, rax
0x18002d907  jnz     loc_18002DD67
0x18002d90d  mov     edx, [rsp+248h+var_1D0]; int
0x18002d911  mov     rcx, [rsp+248h+var_D0]
0x18002d919  mov     rcx, [rcx]; this
0x18002d91c  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x18002d921  mov     r8, [rsp+248h+lpMem]; lpMem
0x18002d929  xor     edx, edx; dwFlags
0x18002d92b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002d932  call    cs:__imp_HeapFree
0x18002d939  nop     dword ptr [rax+rax+00h]
0x18002d93e  cmp     [r15], ebx
0x18002d941  jnz     loc_18002DA3B
0x18002d947  test    esi, esi
0x18002d949  jnz     loc_18002DA3B
0x18002d94f  mov     qword ptr [rsp+248h+var_1A8.Data1], rbx
0x18002d957  lea     rdx, [rsp+248h+var_1A8]; struct tagInterfaceData **
0x18002d95f  mov     rcx, [rsp+248h+var_170]; struct tagInterfaceData *
0x18002d967  call    ?ValidateAndDoFixups@@YAJPEAUtagInterfaceData@@PEAPEAU1@@Z; ValidateAndDoFixups(tagInterfaceData *,tagInterfaceData * *)
0x18002d96c  mov     [r15], eax
0x18002d96f  test    eax, eax
0x18002d971  js      loc_18002DA1E
0x18002d977  mov     rdx, qword ptr [rsp+248h+var_1A8.Data1]; struct tagInterfaceData *
0x18002d97f  lea     rcx, [rsp+248h+var_C8]; this
0x18002d987  call    ??0GenericStream@@QEAA@PEAUtagInterfaceData@@@Z; GenericStream::GenericStream(tagInterfaceData *)
0x18002d98c  xor     edx, edx; dwFlags
0x18002d98e  mov     r8d, 3C0h; dwBytes
0x18002d994  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002d99b  call    cs:__imp_HeapAlloc
0x18002d9a2  nop     dword ptr [rax+rax+00h]
0x18002d9a7  test    rax, rax
0x18002d9aa  jz      loc_18002DC81
0x18002d9b0  xor     edx, edx; int
0x18002d9b2  mov     rcx, rax; this
0x18002d9b5  call    ??0ActivationPropertiesOut@@QEAA@H@Z; ActivationPropertiesOut::ActivationPropertiesOut(int)
0x18002d9ba  mov     [rdi+160h], rax
0x18002d9c1  test    rax, rax
0x18002d9c4  jz      loc_18002E211
0x18002d9ca  mov     qword ptr [rsp+248h+var_1A8.Data1], rbx
0x18002d9d2  lea     r9, [rsp+248h+var_1A8]; void **
0x18002d9da  lea     r8, IID_IActivationPropertiesOut; struct _GUID *
0x18002d9e1  lea     rdx, [rsp+248h+var_C8]; struct IStream *
0x18002d9e9  mov     rcx, rax; this
0x18002d9ec  call    ?UnmarshalInterface@ActivationProperties@@UEAAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; ActivationProperties::UnmarshalInterface(IStream *,_GUID const &,void * *)
0x18002d9f1  mov     [rsp+248h+var_1D0], eax
0x18002d9f5  test    eax, eax
0x18002d9f7  js      loc_18002DDB1
0x18002d9fd  mov     rcx, qword ptr [rsp+248h+var_1A8.Data1]
0x18002da05  mov     rax, [rcx]
0x18002da08  mov     rax, [rax+10h]
0x18002da0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da11  lea     rcx, [rsp+248h+var_C8]; this
0x18002da19  call    ??1GenericStream@@UEAA@XZ; GenericStream::~GenericStream(void)
0x18002da1e  mov     r8, [rsp+248h+var_170]; lpMem
0x18002da26  xor     edx, edx; dwFlags
0x18002da28  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002da2f  call    cs:__imp_HeapFree
0x18002da36  nop     dword ptr [rax+rax+00h]
0x18002da3b  cmp     esi, 6BBh
0x18002da41  jz      loc_18002E21D
0x18002da47  mov     edx, r14d
0x18002da4a  cmp     esi, 80010001h
0x18002da50  jz      loc_18002E23D
0x18002da56  mov     rax, qword ptr [rsp+248h+var_138]
0x18002da5e  mov     rcx, [rax+98h]
0x18002da65  mov     eax, dword ptr [rsp+248h+var_138+8]
0x18002da6c  mov     [rcx], eax
0x18002da6e  test    edx, edx
0x18002da70  jz      loc_18002D6AC
0x18002da76  cmp     esi, 5
0x18002da79  jz      loc_18002DEED
0x18002da7f  cmp     esi, 80070005h
0x18002da85  jz      loc_18002DEED
0x18002da8b  test    esi, esi
0x18002da8d  jnz     loc_18002E26B
0x18002da93  cmp     dword ptr [r15], 80080008h
0x18002da9a  jnz     short loc_18002DB18
0x18002da9c  test    esi, esi
  ... truncated ...
```
