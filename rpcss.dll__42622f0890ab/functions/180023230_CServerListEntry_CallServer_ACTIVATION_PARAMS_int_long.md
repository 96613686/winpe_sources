# CServerListEntry::CallServer(ACTIVATION_PARAMS *,int,long *)

- ea: `0x180023230`
- end: `0x18002410e`
- name: `?CallServer@CServerListEntry@@QEAAHPEAUACTIVATION_PARAMS@@HPEAJ@Z`
- size: `3806`
- prototype: `__int64 __fastcall(CServerListEntry *this, struct ACTIVATION_PARAMS *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000866c`

## callees

- `0x180003064`
- `0x1800051f0`
- `0x18001cad8`
- `0x1800220f4`
- `0x180022114`
- `0x180022138`
- `0x180022274`
- `0x180022678`
- `0x180022810`
- `0x180022ef0`
- `0x180022f4c`
- `0x180022fa0`
- `0x1800231e0`
- `0x180023230`
- `0x180024120`
- `0x180024cc4`
- `0x180024d80`
- `0x180024dd4`
- `0x180025250`
- `0x180025310`
- `0x18002ba28`
- `0x18002ba50`
- `0x18002f078`
- `0x180030240`
- `0x180059be4`
- `0x18008e98c`
- `0x18008f610`
- `0x180098b54`
- `0x180098be8`
- `0x1800a167c`
- `0x1800a18fc`
- `0x1800b27e0`
- `0x18010b010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180023484`
- `RPCRT4!UuidCreate` at `0x180023484`
- `RPCRT4!I_RpcExceptionFilter` at `0x18010a20e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18010a22a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18010a20e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18010a22a`
- `RPCRT4!NdrClientCall2` at `0x180023969`
- `RPCRT4!NdrClientCall2` at `0x180023ab2`
- `RPCRT4!NdrClientCall2` at `0x180023969`
- `RPCRT4!NdrClientCall2` at `0x180023ab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002370a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800237fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002370a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800237fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023518`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002376d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023518`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002376d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002400b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002400b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800232c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800232c8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800232b0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800232b0`

## string_xrefs

- `0x18002365b`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x1800236bc`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x1800238c1`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x1800239df`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x180023a19`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x180023bce`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x180023c2c`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x180023e8c`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x180023f92`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x180024072`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x18002409e`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x1800240f8`: `onecore\com\combase\rpcss\olescm\servers.cxx`
- `0x180023b56`: `Failed call into server. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x180023b42`: `Server returned failure. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x180023a01`: `onecore\com\combase\inc\ComGuid.hpp`
- `0x180023d7b`: `onecore\com\combase\rpcss\objex\soxid.hxx`
- `0x180023df8`: `Server TCP port not open. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x180023ec9`: `Failed to get binding handle. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x180023e52`: `Server process died. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x180023f4b`: `Failed to copy ROT data. CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x1800240c0`: `Call security blocked activation call: CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x180023ccf`: `Call security blocked activation: ACID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x18002408d`: `Server stopping: CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`
- `0x180024034`: `Transforming call failure from %#x: CLSID:%ls, Client PID (image):%x (%ls), Server PID (image): %#x (%ls)`

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
  __int64 v16; // r9
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
                                                    &stru_18010E910,
                                                    &byte_18011A9D0,
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
                                                  &stru_18010E910,
                                                  &byte_18011A988,
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
0x180023230  push    rbx
0x180023232  push    rsi
0x180023233  push    rdi
0x180023234  push    r12
0x180023236  push    r13
0x180023238  push    r14
0x18002323a  push    r15
0x18002323c  sub     rsp, 210h
0x180023243  mov     rax, cs:__security_cookie
0x18002324a  xor     rax, rsp
0x18002324d  mov     [rsp+248h+var_48], rax
0x180023255  mov     rax, r9
0x180023258  mov     [rsp+248h+hObject], rax
0x180023260  mov     dword ptr [rsp+248h+var_1E4+4], r8d
0x180023265  mov     rdi, rdx
0x180023268  mov     rsi, rcx
0x18002326b  mov     [rsp+248h+var_150], rcx
0x180023273  mov     [rsp+248h+var_120], rax
0x18002327b  mov     [rsp+248h+var_118], rcx
0x180023283  mov     [rsp+248h+var_110], rdx
0x18002328b  mov     r15, r9
0x18002328e  mov     [rsp+248h+var_108], r9
0x180023296  mov     rbx, [rsp+248h]
0x18002329e  lea     rcx, [rdx+3Ch]; rguid
0x1800232a2  mov     r8d, 27h ; '''; cchMax
0x1800232a8  lea     rdx, [rsp+248h+sz]; lpsz
0x1800232b0  call    cs:__imp_StringFromGUID2
0x1800232b6  cmp     eax, 27h ; '''
0x1800232b9  jnz     loc_180023A01
0x1800232bf  xor     edx, edx; length
0x1800232c1  mov     rcx, [rdi+1B8h]; string
0x1800232c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800232ce  mov     [rsp+248h+var_198], rax
0x1800232d6  mov     r12, [rdi+8]
0x1800232da  xor     ebx, ebx
0x1800232dc  test    r12, r12
0x1800232df  jz      loc_180023B89
0x1800232e5  mov     r13d, [r12+58h]
0x1800232ea  mov     [rsp+248h+var_1B8], r13d
0x1800232f2  test    r12, r12
0x1800232f5  jz      loc_180023B91
0x1800232fb  mov     r12, [r12+180h]
0x180023303  mov     [rsp+248h+var_158], r12
0x18002330b  mov     rcx, [rsi+60h]; this
0x18002330f  mov     r14d, [rcx+58h]
0x180023313  mov     [rsp+248h+var_1E8], r14d
0x180023318  mov     rax, [rcx+180h]
0x18002331f  mov     [rsp+248h+var_1C0], rax
0x180023327  cmp     [rdi+0BCh], bl
0x18002332d  jnz     loc_180023D91
0x180023333  mov     [rsp+248h+var_1DC], r14d
0x180023338  mov     [rsp+248h+var_180], rax
0x180023340  mov     edx, dword ptr [rsp+248h+var_1E4+4]; int
0x180023344  mov     rcx, rsi; this
0x180023347  call    ?EnsureRpcHandle@CServerListEntry@@QEAAHH@Z; CServerListEntry::EnsureRpcHandle(int)
0x18002334c  test    eax, eax
0x18002334e  jz      loc_180023CE0
0x180023354  mov     rax, [rsi+68h]
0x180023358  mov     rax, [rax+10h]
0x18002335c  mov     [rsp+248h+var_188], rax
0x180023364  mov     rax, [rdi+98h]
0x18002336b  or      dword ptr [rax+4], 8
0x18002336f  mov     al, [rsi+80h]
0x180023375  mov     r14d, 1
0x18002337b  test    al, 4
0x18002337d  jnz     loc_180023EE3
0x180023383  cmp     dword ptr [rdi+38h], 2
0x180023387  jz      loc_180023EF3
0x18002338d  mov     rax, [rdi+168h]
0x180023394  movups  xmm0, xmmword ptr [rdi+3Ch]
0x180023398  movdqu  xmmword ptr [rax+20h], xmm0
0x18002339d  mov     [rsp+248h+var_160], rbx
0x1800233a5  lea     r8, [rsp+248h+var_160]; void **
0x1800233ad  lea     rdx, IID_ISpecialSystemProperties; struct _GUID *
0x1800233b4  mov     rcx, [rdi+158h]; this
0x1800233bb  call    ?QueryInterface@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::QueryInterface(_GUID const &,void * *)
0x1800233c0  mov     dword ptr [rsp+248h+var_1E4+4], eax
0x1800233c4  mov     [r15], eax
0x1800233c7  mov     rcx, [rsp+248h]; this
0x1800233cf  test    eax, eax
0x1800233d1  js      loc_180023A16
0x1800233d7  mov     rcx, [rsp+248h+var_160]
0x1800233df  mov     rax, [rcx]
0x1800233e2  mov     edx, [rsi+98h]
0x1800233e8  mov     rax, [rax+0A8h]
0x1800233ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233f4  mov     rcx, [rsp+248h+var_160]
0x1800233fc  mov     rax, [rcx]
0x1800233ff  mov     rax, [rax+10h]
0x180023403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023408  cmp     [rdi+0BDh], bl
0x18002340e  jnz     loc_180023D2E
0x180023414  mov     [rsp+248h+var_168], r13d
0x18002341c  mov     [rsp+248h+var_E0], r12
0x180023424  mov     eax, [rsp+248h+var_1E8]
0x180023428  mov     [rsp+248h+var_140], eax
0x18002342f  mov     rax, [rsp+248h+var_1C0]
0x180023437  mov     [rsp+248h+var_E8], rax
0x18002343f  mov     r8, [rsp+248h+var_198]
0x180023447  mov     [rsp+248h+var_1D8], r8
0x18002344c  mov     esi, ebx
0x18002344e  mov     [rsp+248h+var_164], r13d
0x180023456  mov     [rsp+248h+var_D8], r12
0x18002345e  mov     rax, [rsp+248h+var_188]
0x180023466  mov     [rsp+248h+var_F0], rax
0x18002346e  mov     [rsp+248h+var_190], ebx
0x180023475  mov     dword ptr [rsp+248h+var_1E4+4], ebx
0x180023479  mov     rcx, [rdi+0A0h]
0x180023480  add     rcx, 18h; Uuid
0x180023484  call    cs:__imp_UuidCreate
0x18002348a  mov     [rsp+248h+lpMem], rbx
0x180023492  mov     [rsp+248h+var_170], rbx
0x18002349a  mov     [rsp+248h+var_1D0], ebx
0x18002349e  lea     rax, [rsp+248h+lpMem]
0x1800234a6  mov     [rsp+248h+var_228], rax; int
0x1800234ab  xor     r8d, r8d; unsigned int
0x1800234ae  lea     rdx, IID_IActivationPropertiesIn; struct _GUID *
0x1800234b5  mov     rcx, [rdi+158h]; struct IActivationProperties *
0x1800234bc  call    ?ActPropsMarshalHelper@@YAJPEAUIActivationProperties@@AEBU_GUID@@KKPEAPEAUtagMInterfacePointer@@@Z; ActPropsMarshalHelper(IActivationProperties *,_GUID const &,ulong,ulong,tagMInterfacePointer * *)
0x1800234c1  mov     dword ptr [rsp+248h+var_1E4], eax
0x1800234c5  mov     [r15], eax
0x1800234c8  mov     rcx, [rsp+248h]; this
0x1800234d0  test    eax, eax
0x1800234d2  js      loc_1800238BE
0x1800234d8  lea     rax, [rdi+10h]
0x1800234dc  mov     [rsp+248h+var_D0], rax
0x1800234e4  lea     r8, [rsp+248h+var_1D0]; int *
0x1800234e9  mov     edx, r14d; int
0x1800234ec  mov     rcx, [rax]; this
0x1800234ef  call    ?Impersonate@CToken@@UEAAJHPEAH@Z; CToken::Impersonate(int,int *)
0x1800234f4  mov     dword ptr [rsp+248h+var_1E4], eax
0x1800234f8  mov     [r15], eax
0x1800234fb  mov     rcx, [rsp+248h]; this
0x180023503  test    eax, eax
0x180023505  js      loc_1800239DC
0x18002350b  xor     edx, edx; dwFlags
0x18002350d  lea     r8d, [rdx+48h]; dwBytes
0x180023511  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180023518  call    cs:__imp_HeapAlloc
0x18002351e  mov     rcx, rax; this
0x180023521  test    rax, rax
0x180023524  jz      loc_180023B62
0x18002352a  movups  xmm0, xmmword ptr [rdi+3Ch]
0x18002352e  movdqu  xmmword ptr [rsp+248h+var_1A8.Data1], xmm0
0x180023537  mov     rax, [rsp+248h+var_150]
0x18002353f  mov     r8, [rax+60h]
0x180023543  mov     [rsp+248h+var_228], rbx; void *
0x180023548  mov     r9d, [rdi+0F0h]; unsigned int
0x18002354f  mov     r8d, [r8+58h]; unsigned int
0x180023553  lea     rdx, [rsp+248h+var_1A8]; struct _GUID *
0x18002355b  call    ??0CActivationState@@QEAA@U_GUID@@KKPEAX@Z; CActivationState::CActivationState(_GUID,ulong,ulong,void *)
0x180023560  mov     [rsp+248h+var_148], rax
0x180023568  test    rax, rax
0x18002356b  jz      short loc_180023575
0x18002356d  mov     rdx, rax; struct CActivationState *
0x180023570  call    ?Insert@CActivationStateList@@QEAAXPEAVCActivationState@@@Z; CActivationStateList::Insert(CActivationState *)
0x180023575  mov     rdx, rdi; struct ACTIVATION_PARAMS *
0x180023578  lea     rcx, [rsp+248h+var_138]; this
0x180023580  call    ??0SaveRestoreProtocolVersionForCallToLocalServer@@QEAA@PEAUACTIVATION_PARAMS@@@Z; SaveRestoreProtocolVersionForCallToLocalServer::SaveRestoreProtocolVersionForCallToLocalServer(ACTIVATION_PARAMS *)
0x180023585  mov     ecx, [rdi+38h]
0x180023588  test    ecx, ecx
0x18002358a  jz      loc_180023904
0x180023590  sub     ecx, 1
0x180023593  jz      loc_180023A48
0x180023599  cmp     ecx, 1
0x18002359c  jz      loc_180023A48
0x1800235a2  mov     dword ptr [r15], 8000FFFFh
0x1800235a9  mov     rax, [rdi+0B0h]
0x1800235b0  cmp     [rax], rbx
0x1800235b3  jnz     loc_180023FB0
0x1800235b9  mov     rax, [rdi+0B0h]
0x1800235c0  cmp     [rax+10h], rbx
0x1800235c4  jnz     loc_180023FBA
0x1800235ca  mov     rax, [rsp+248h]
0x1800235d2  mov     r9d, esi; char *
0x1800235d5  mov     qword ptr [rsp+248h+var_1A8.Data1], rax
0x1800235dd  mov     r10, [rsp+248h]
0x1800235e5  cmp     [rdi+1B0h], bl
0x1800235eb  jz      loc_180023B3A
0x1800235f1  mov     dword ptr [rsp+248h+var_1E4], 63Ah
0x1800235f9  lea     rax, aServerReturned; "Server returned failure. ACID:%ls, Clie"...
0x180023600  mov     rcx, [rsp+248h+var_1D8]
0x180023605  mov     edx, 638h; void *
0x18002360a  lea     r8, aFailedCallInto_0; "Failed call into server. ACID:%ls, Clie"...
0x180023611  mov     [rsp+248h+var_100], rcx
0x180023619  mov     [rsp+248h+var_F8], rax
0x180023621  mov     rax, [rsp+248h+var_E8]
0x180023629  mov     [rsp+248h+var_200], rax
0x18002362e  mov     eax, [rsp+248h+var_140]
0x180023635  mov     dword ptr [rsp+248h+var_208], eax
0x180023639  mov     rax, [rsp+248h+var_E0]
0x180023641  mov     [rsp+248h+var_210], rax
0x180023646  mov     eax, [rsp+248h+var_168]
0x18002364d  mov     dword ptr [rsp+248h+var_218], eax
0x180023651  mov     [rsp+248h+var_220], rcx; char *
0x180023656  mov     [rsp+248h+var_228], r8; unsigned int
0x18002365b  lea     r8, aOnecoreComComb_24; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x180023662  mov     rcx, r10; this
0x180023665  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002366a  mov     rax, [rsp+248h+var_180]
0x180023672  mov     [rsp+248h+var_200], rax
0x180023677  mov     eax, [rsp+248h+var_1DC]
0x18002367b  mov     dword ptr [rsp+248h+var_208], eax
0x18002367f  mov     rax, [rsp+248h+var_D8]
0x180023687  mov     [rsp+248h+var_210], rax
0x18002368c  mov     eax, [rsp+248h+var_164]
0x180023693  mov     dword ptr [rsp+248h+var_218], eax
0x180023697  mov     rax, [rsp+248h+var_100]
0x18002369f  mov     [rsp+248h+var_220], rax; char *
0x1800236a4  mov     rax, [rsp+248h+var_F8]
0x1800236ac  mov     [rsp+248h+var_228], rax; __int64
0x1800236b1  mov     rax, [rsp+248h+hObject]
0x1800236b9  mov     r9d, [rax]; char *
0x1800236bc  lea     r8, aOnecoreComComb_24; "onecore\\com\\combase\\rpcss\\olescm\\s"...
0x1800236c3  mov     edx, dword ptr [rsp+248h+var_1E4]; void *
0x1800236c7  mov     rcx, qword ptr [rsp+248h+var_1A8.Data1]; this
0x1800236cf  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800236d4  mov     rax, [rsp+248h+var_148]
0x1800236dc  test    rax, rax
0x1800236df  jnz     loc_180023B20
0x1800236e5  mov     edx, [rsp+248h+var_1D0]; int
0x1800236e9  mov     rcx, [rsp+248h+var_D0]
0x1800236f1  mov     rcx, [rcx]; this
0x1800236f4  call    ?Revert@CToken@@UEAAJH@Z; CToken::Revert(int)
0x1800236f9  mov     r8, [rsp+248h+lpMem]; lpMem
0x180023701  xor     edx, edx; dwFlags
0x180023703  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002370a  call    cs:__imp_HeapFree
0x180023710  cmp     [r15], ebx
0x180023713  jnz     loc_180023801
0x180023719  test    esi, esi
0x18002371b  jnz     loc_180023801
0x180023721  mov     qword ptr [rsp+248h+var_1A8.Data1], rbx
0x180023729  lea     rdx, [rsp+248h+var_1A8]; struct tagInterfaceData **
0x180023731  mov     rcx, [rsp+248h+var_170]; struct tagInterfaceData *
0x180023739  call    ?ValidateAndDoFixups@@YAJPEAUtagInterfaceData@@PEAPEAU1@@Z; ValidateAndDoFixups(tagInterfaceData *,tagInterfaceData * *)
0x18002373e  mov     [r15], eax
0x180023741  test    eax, eax
0x180023743  js      loc_1800237EA
0x180023749  mov     rdx, qword ptr [rsp+248h+var_1A8.Data1]; struct tagInterfaceData *
0x180023751  lea     rcx, [rsp+248h+var_C8]; this
0x180023759  call    ??0GenericStream@@QEAA@PEAUtagInterfaceData@@@Z; GenericStream::GenericStream(tagInterfaceData *)
0x18002375e  xor     edx, edx; dwFlags
0x180023760  mov     r8d, 3C0h; dwBytes
0x180023766  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18002376d  call    cs:__imp_HeapAlloc
0x180023773  test    rax, rax
0x180023776  jz      loc_180023A40
0x18002377c  xor     edx, edx; int
0x18002377e  mov     rcx, rax; this
0x180023781  call    ??0ActivationPropertiesOut@@QEAA@H@Z; ActivationPropertiesOut::ActivationPropertiesOut(int)
0x180023786  mov     [rdi+160h], rax
0x18002378d  test    rax, rax
0x180023790  jz      loc_180023FC4
0x180023796  mov     qword ptr [rsp+248h+var_1A8.Data1], rbx
0x18002379e  lea     r9, [rsp+248h+var_1A8]; void **
0x1800237a6  lea     r8, IID_IActivationPropertiesOut; struct _GUID *
0x1800237ad  lea     rdx, [rsp+248h+var_C8]; struct IStream *
0x1800237b5  mov     rcx, rax; this
0x1800237b8  call    ?UnmarshalInterface@ActivationProperties@@UEAAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z; ActivationProperties::UnmarshalInterface(IStream *,_GUID const &,void * *)
0x1800237bd  mov     [rsp+248h+var_1D0], eax
0x1800237c1  test    eax, eax
0x1800237c3  js      loc_180023B6A
0x1800237c9  mov     rcx, qword ptr [rsp+248h+var_1A8.Data1]
0x1800237d1  mov     rax, [rcx]
0x1800237d4  mov     rax, [rax+10h]
0x1800237d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237dd  lea     rcx, [rsp+248h+var_C8]; this
0x1800237e5  call    ??1GenericStream@@UEAA@XZ; GenericStream::~GenericStream(void)
0x1800237ea  mov     r8, [rsp+248h+var_170]; lpMem
0x1800237f2  xor     edx, edx; dwFlags
0x1800237f4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800237fb  call    cs:__imp_HeapFree
0x180023801  cmp     esi, 6BBh
0x180023807  jz      loc_180023FD0
0x18002380d  mov     edx, r14d
0x180023810  cmp     esi, 80010001h
0x180023816  jz      loc_180023FF0
0x18002381c  mov     rax, qword ptr [rsp+248h+var_138]
0x180023824  mov     rcx, [rax+98h]
0x18002382b  mov     eax, dword ptr [rsp+248h+var_138+8]
0x180023832  mov     [rcx], eax
0x180023834  test    edx, edx
0x180023836  jz      loc_18002348A
0x18002383c  cmp     esi, 5
0x18002383f  jz      loc_180023CA6
0x180023845  cmp     esi, 80070005h
0x18002384b  jz      loc_180023CA6
0x180023851  test    esi, esi
0x180023853  jnz     loc_180024018
0x180023859  cmp     dword ptr [r15], 80080008h
0x180023860  jnz     short loc_1800238DE
0x180023862  test    esi, esi
0x180023864  jnz     loc_180024018
0x18002386a  mov     rcx, [rsp+248h]; this
0x180023872  mov     rax, [rsp+248h+var_1C0]
0x18002387a  mov     r9d, [r15]; char *
0x18002387d  mov     [rsp+248h+var_200], rax
0x180023882  mov     eax, [rsp+248h+var_1E8]
0x180023886  mov     dword ptr [rsp+248h+var_208], eax
  ... truncated ...
```
