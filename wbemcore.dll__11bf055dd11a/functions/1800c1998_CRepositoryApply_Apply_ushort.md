# CRepositoryApply::Apply(ushort *)

- ea: `0x1800c1998`
- end: `0x1800c1f87`
- name: `?Apply@CRepositoryApply@@QEAAJPEAG@Z`
- size: `1519`
- prototype: `__int64 __fastcall(CRepositoryApply *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a8a18`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18000e8c0`
- `0x18007d990`
- `0x1800c1998`
- `0x1800c2fbc`
- `0x1800c338c`
- `0x1800c38b4`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c19f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c19f2`
- `wbemcomn!?CreateInst@CWbemCallSecurity@@SAPEAVIWbemCallSecurity@@K@Z` at `0x1800c1a2c`
- `wbemcomn!?CreateInst@CWbemCallSecurity@@SAPEAVIWbemCallSecurity@@K@Z` at `0x1800c1a2c`
- `wbemcomn!GetMemLogObject` at `0x1800c1a9e`
- `wbemcomn!GetMemLogObject` at `0x1800c1b87`
- `wbemcomn!GetMemLogObject` at `0x1800c1c70`
- `wbemcomn!GetMemLogObject` at `0x1800c1d3a`
- `wbemcomn!GetMemLogObject` at `0x1800c1a9e`
- `wbemcomn!GetMemLogObject` at `0x1800c1b87`
- `wbemcomn!GetMemLogObject` at `0x1800c1c70`
- `wbemcomn!GetMemLogObject` at `0x1800c1d3a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1aae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1b93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1c7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1d46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1aae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1b93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1c7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800c1d46`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1b18`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1cba`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1cce`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1d84`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1e62`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1f21`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1f40`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1b18`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1cba`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1cce`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1d84`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1e62`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1f21`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800c1f40`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c1db6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c1db6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c1a11`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800c1a11`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c1af2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c1bd4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c1f52`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c1af2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c1bd4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c1f52`

## string_xrefs

- `0x1800c1e31`: `onecore\admin\wmi\wbem\winmgmt\coredll\apply.cpp`
- `0x1800c1ef0`: `onecore\admin\wmi\wbem\winmgmt\coredll\apply.cpp`
- `0x1800c1c1a`: `CloneThreadContext failed with hr = %x`
- `0x1800c1dca`: `CoCreateInstance failed with hr = %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepositoryApply::Apply(CRepositoryApply *this, LPCWSTR lpFileName)
{
  CFileLogger *v3; // rcx
  HANDLE FileW; // rbx
  CFileLogger *v5; // rcx
  HRESULT v6; // ebx
  IUnknown *Inst; // rdi
  unsigned int v8; // ecx
  CMemoryLog *MemLogObject; // rax
  HRESULT v10; // eax
  unsigned int v11; // r14d
  unsigned int v12; // ecx
  CMemoryLog *v13; // rax
  IUnknown *v14; // r15
  int v15; // eax
  unsigned int v16; // ecx
  CMemoryLog *v17; // rax
  HRESULT v18; // eax
  unsigned int v19; // ecx
  CMemoryLog *v20; // rax
  HRESULT v21; // eax
  unsigned int v22; // ecx
  int v23; // eax
  unsigned int v24; // ecx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  IUnknown *v28; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *v29; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *ppOldObject[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v32[328]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v33[332]; // [rsp+300h] [rbp+200h] BYREF

  if ( lpFileName )
  {
    FileW = CreateFileW(lpFileName, 4u, 0, 0, 4u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      CFileLogger::Close(v3);
      g_hLogFile = FileW;
    }
  }
  v6 = CoInitializeEx(0, 0);
  if ( v6 >= 0 )
  {
    Inst = (IUnknown *)CWbemCallSecurity::CreateInst(0);
    v28 = Inst;
    if ( !Inst )
    {
      StringCchPrintfW(v32, 0x144u, L"Unable to get pCallSec");
      v8 = (unsigned int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v32);
      }
      LogMsg(v8, v32);
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, 2147749894LL);
      }
      _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v28);
      CoUninitialize();
      v6 = -2147217402;
      goto LABEL_58;
    }
    ppOldObject[0] = 0;
    v29 = 0;
    v10 = CoSwitchCallContext(0, ppOldObject);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v14 = ppOldObject[0];
      ppOldObject[1] = ppOldObject[0];
      ppOldObject[2] = (IUnknown *)&v29;
      v15 = ((__int64 (__fastcall *)(IUnknown *, __int64))Inst->lpVtbl[3].QueryInterface)(Inst, 1);
      v11 = v15;
      if ( v15 >= 0 )
      {
        v18 = CoSwitchCallContext(Inst, &v29);
        v11 = v18;
        if ( v18 >= 0 )
        {
          ppv = 0;
          v21 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &ppv);
          v11 = v21;
          if ( v21 >= 0 )
          {
            v23 = CRepositoryApply::PutObjects(this, (struct IWbemLocator *)ppv);
            v11 = v23;
            if ( v23 >= 0 )
            {
              _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&ppv);
              CoSwitchCallContext(v14, &v29);
              _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v28);
              CoUninitialize();
              v6 = 0;
              goto LABEL_58;
            }
            StringCchPrintfW(v32, 0x144u, L"PutObjects failed with hr = %x", (unsigned int)v23);
            v24 = (unsigned int)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v32);
            }
            LogMsg(v24, v32);
            LODWORD(dwFlagsAndAttributes) = v11;
            dwCreationDisposition[0] = 424;
            StringCchPrintfW(
              v33,
              0x144u,
              L"%S@%d, HRESULT: 0x%x",
              "onecore\\admin\\wmi\\wbem\\winmgmt\\coredll\\apply.cpp",
              *(_QWORD *)dwCreationDisposition,
              dwFlagsAndAttributes);
            _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&ppv);
            CoSwitchCallContext(v14, &v29);
          }
          else
          {
            StringCchPrintfW(v32, 0x144u, L"CoCreateInstance failed with hr = %x", (unsigned int)v21);
            v22 = (unsigned int)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v32);
            }
            LogMsg(v22, v32);
            LODWORD(dwFlagsAndAttributes) = v11;
            dwCreationDisposition[0] = 413;
            StringCchPrintfW(
              v33,
              0x144u,
              L"%S@%d, HRESULT: 0x%x",
              "onecore\\admin\\wmi\\wbem\\winmgmt\\coredll\\apply.cpp",
              *(_QWORD *)dwCreationDisposition,
              dwFlagsAndAttributes);
            _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&ppv);
            CoSwitchCallContext(v14, &v29);
          }
          goto LABEL_24;
        }
        StringCchPrintfW(v32, 0x144u, L"Adding Call context failed with hr = %x", (unsigned int)v18);
        v19 = (unsigned int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v32);
        }
        LogMsg(v19, v32);
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, v11);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v11);
        }
      }
      else
      {
        StringCchPrintfW(v32, 0x144u, L"CloneThreadContext failed with hr = %x", (unsigned int)v15);
        v16 = (unsigned int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v32);
        }
        LogMsg(v16, v32);
        v17 = GetMemLogObject();
        CMemoryLog::Write(v17, v11);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v11);
        }
      }
      CoSwitchCallContext(v14, &v29);
    }
    else
    {
      StringCchPrintfW(v32, 0x144u, L"Getting call context failed with hr = %x", (unsigned int)v10);
      v12 = (unsigned int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v32);
      }
      LogMsg(v12, v32);
      v13 = GetMemLogObject();
      CMemoryLog::Write(v13, v11);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids, v11);
      }
    }
LABEL_24:
    _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(&v28);
    CoUninitialize();
    v6 = v11;
  }
LABEL_58:
  CFileLogger::Close(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c1998  mov     [rsp-8+arg_10], rbx
0x1800c199d  push    rbp
0x1800c199e  push    rsi
0x1800c199f  push    rdi
0x1800c19a0  push    r14
0x1800c19a2  push    r15
0x1800c19a4  lea     rbp, [rsp-4A0h]
0x1800c19ac  sub     rsp, 5A0h
0x1800c19b3  mov     rax, cs:__security_cookie
0x1800c19ba  xor     rax, rsp
0x1800c19bd  mov     [rbp+4C0h+var_28], rax
0x1800c19c4  mov     rax, rdx
0x1800c19c7  mov     rsi, rcx
0x1800c19ca  test    rdx, rdx
0x1800c19cd  jz      short loc_1800C1A0D
0x1800c19cf  mov     [rsp+5C0h+hTemplateFile], 0; hTemplateFile
0x1800c19d8  mov     dword ptr [rsp+5C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c19e0  mov     edx, 4; dwDesiredAccess
0x1800c19e5  mov     [rsp+5C0h+dwCreationDisposition], edx; dwCreationDisposition
0x1800c19e9  xor     r9d, r9d; lpSecurityAttributes
0x1800c19ec  xor     r8d, r8d; dwShareMode
0x1800c19ef  mov     rcx, rax; lpFileName
0x1800c19f2  call    cs:__imp_CreateFileW
0x1800c19f8  mov     rbx, rax
0x1800c19fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c19ff  jz      short loc_1800C1A0D
0x1800c1a01  call    ?Close@CFileLogger@@QEAAXXZ; CFileLogger::Close(void)
0x1800c1a06  mov     cs:?g_hLogFile@@3PEAXEA, rbx; void * g_hLogFile
0x1800c1a0d  xor     edx, edx; dwCoInit
0x1800c1a0f  xor     ecx, ecx; pvReserved
0x1800c1a11  call    cs:__imp_CoInitializeEx
0x1800c1a17  mov     ebx, eax
0x1800c1a19  test    eax, eax
0x1800c1a1b  js      loc_1800C1F5A
0x1800c1a21  mov     [rsp+5C0h+var_580], 0
0x1800c1a2a  xor     ecx, ecx
0x1800c1a2c  call    cs:__imp_?CreateInst@CWbemCallSecurity@@SAPEAVIWbemCallSecurity@@K@Z; CWbemCallSecurity::CreateInst(ulong)
0x1800c1a32  mov     rdi, rax
0x1800c1a35  mov     [rsp+5C0h+var_580], rax
0x1800c1a3a  test    rax, rax
0x1800c1a3d  jnz     loc_1800C1AFF
0x1800c1a43  lea     r8, aUnableToGetPca; "Unable to get pCallSec"
0x1800c1a4a  mov     edx, 144h; unsigned __int64
0x1800c1a4f  lea     rcx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1a54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1a59  lea     rdi, WPP_GLOBAL_Control
0x1800c1a60  mov     ebx, 1
0x1800c1a65  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1a6c  cmp     rcx, rdi
0x1800c1a6f  jz      short loc_1800C1A94
0x1800c1a71  test    [rcx+1Ch], bl
0x1800c1a74  jz      short loc_1800C1A94
0x1800c1a76  cmp     byte ptr [rcx+19h], 5
0x1800c1a7a  jb      short loc_1800C1A94
0x1800c1a7c  lea     edx, [rbx+13h]
0x1800c1a7f  lea     r9, [rsp+5C0h+var_550]
0x1800c1a84  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1a8b  mov     rcx, [rcx+10h]
0x1800c1a8f  call    WPP_SF_S
0x1800c1a94  lea     rdx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1a99  call    ?LogMsg@@YAXIPEAG@Z; LogMsg(uint,ushort *)
0x1800c1a9e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800c1aa4  mov     esi, 80041006h
0x1800c1aa9  mov     edx, esi
0x1800c1aab  mov     rcx, rax
0x1800c1aae  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800c1ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1abb  cmp     rcx, rdi
0x1800c1abe  jz      short loc_1800C1AE7
0x1800c1ac0  test    [rcx+1Ch], bl
0x1800c1ac3  jz      short loc_1800C1AE7
0x1800c1ac5  cmp     byte ptr [rcx+19h], 2
0x1800c1ac9  jb      short loc_1800C1AE7
0x1800c1acb  mov     edx, 15h
0x1800c1ad0  mov     r9d, 80041006h
0x1800c1ad6  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1add  mov     rcx, [rcx+10h]
0x1800c1ae1  call    WPP_SF_d
0x1800c1ae6  nop
0x1800c1ae7  lea     rcx, [rsp+5C0h+var_580]
0x1800c1aec  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x1800c1af1  nop
0x1800c1af2  call    cs:__imp_CoUninitialize
0x1800c1af8  mov     ebx, esi
0x1800c1afa  jmp     loc_1800C1F5A
0x1800c1aff  mov     [rsp+5C0h+ppOldObject], 0
0x1800c1b08  mov     [rsp+5C0h+var_578], 0
0x1800c1b11  lea     rdx, [rsp+5C0h+ppOldObject]; ppOldObject
0x1800c1b16  xor     ecx, ecx; pNewObject
0x1800c1b18  call    cs:__imp_CoSwitchCallContext
0x1800c1b1e  mov     r14d, eax
0x1800c1b21  test    eax, eax
0x1800c1b23  jns     loc_1800C1BE2
0x1800c1b29  mov     r9d, eax
0x1800c1b2c  lea     r8, aGettingCallCon; "Getting call context failed with hr = %"...
0x1800c1b33  mov     edx, 144h; unsigned __int64
0x1800c1b38  lea     rcx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1b3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1b42  lea     rdi, WPP_GLOBAL_Control
0x1800c1b49  mov     ebx, 1
0x1800c1b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1b55  cmp     rcx, rdi
0x1800c1b58  jz      short loc_1800C1B7D
0x1800c1b5a  test    [rcx+1Ch], bl
0x1800c1b5d  jz      short loc_1800C1B7D
0x1800c1b5f  cmp     byte ptr [rcx+19h], 5
0x1800c1b63  jb      short loc_1800C1B7D
0x1800c1b65  lea     edx, [rbx+15h]
0x1800c1b68  lea     r9, [rsp+5C0h+var_550]
0x1800c1b6d  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1b74  mov     rcx, [rcx+10h]
0x1800c1b78  call    WPP_SF_S
0x1800c1b7d  lea     rdx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1b82  call    ?LogMsg@@YAXIPEAG@Z; LogMsg(uint,ushort *)
0x1800c1b87  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800c1b8d  mov     edx, r14d
0x1800c1b90  mov     rcx, rax
0x1800c1b93  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800c1b99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1ba0  cmp     rcx, rdi
0x1800c1ba3  jz      short loc_1800C1BC9
0x1800c1ba5  test    [rcx+1Ch], bl
0x1800c1ba8  jz      short loc_1800C1BC9
0x1800c1baa  cmp     byte ptr [rcx+19h], 2
0x1800c1bae  jb      short loc_1800C1BC9
0x1800c1bb0  mov     edx, 17h
0x1800c1bb5  mov     r9d, r14d
0x1800c1bb8  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1bbf  mov     rcx, [rcx+10h]
0x1800c1bc3  call    WPP_SF_d
0x1800c1bc8  nop
0x1800c1bc9  lea     rcx, [rsp+5C0h+var_580]
0x1800c1bce  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x1800c1bd3  nop
0x1800c1bd4  call    cs:__imp_CoUninitialize
0x1800c1bda  mov     ebx, r14d
0x1800c1bdd  jmp     loc_1800C1F5A
0x1800c1be2  mov     r15, [rsp+5C0h+ppOldObject]
0x1800c1be7  mov     [rsp+5C0h+var_560], r15
0x1800c1bec  lea     rax, [rsp+5C0h+var_578]
0x1800c1bf1  mov     [rsp+5C0h+var_558], rax
0x1800c1bf6  mov     rax, [rdi]
0x1800c1bf9  mov     ebx, 1
0x1800c1bfe  mov     edx, ebx
0x1800c1c00  mov     rcx, rdi
0x1800c1c03  mov     rax, [rax+48h]
0x1800c1c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1c0c  mov     r14d, eax
0x1800c1c0f  test    eax, eax
0x1800c1c11  jns     loc_1800C1CC6
0x1800c1c17  mov     r9d, eax
0x1800c1c1a  lea     r8, aClonethreadcon; "CloneThreadContext failed with hr = %x"
0x1800c1c21  mov     edx, 144h; unsigned __int64
0x1800c1c26  lea     rcx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1c2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1c30  lea     rdi, WPP_GLOBAL_Control
0x1800c1c37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1c3e  cmp     rcx, rdi
0x1800c1c41  jz      short loc_1800C1C66
0x1800c1c43  test    [rcx+1Ch], bl
0x1800c1c46  jz      short loc_1800C1C66
0x1800c1c48  cmp     byte ptr [rcx+19h], 5
0x1800c1c4c  jb      short loc_1800C1C66
0x1800c1c4e  lea     edx, [rbx+17h]
0x1800c1c51  lea     r9, [rsp+5C0h+var_550]
0x1800c1c56  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1c5d  mov     rcx, [rcx+10h]
0x1800c1c61  call    WPP_SF_S
0x1800c1c66  lea     rdx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1c6b  call    ?LogMsg@@YAXIPEAG@Z; LogMsg(uint,ushort *)
0x1800c1c70  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800c1c76  mov     edx, r14d
0x1800c1c79  mov     rcx, rax
0x1800c1c7c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800c1c82  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1c89  cmp     rcx, rdi
0x1800c1c8c  jz      short loc_1800C1CB2
0x1800c1c8e  test    [rcx+1Ch], bl
0x1800c1c91  jz      short loc_1800C1CB2
0x1800c1c93  cmp     byte ptr [rcx+19h], 2
0x1800c1c97  jb      short loc_1800C1CB2
0x1800c1c99  mov     edx, 19h
0x1800c1c9e  mov     r9d, r14d
0x1800c1ca1  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1ca8  mov     rcx, [rcx+10h]
0x1800c1cac  call    WPP_SF_d
0x1800c1cb1  nop
0x1800c1cb2  lea     rdx, [rsp+5C0h+var_578]; ppOldObject
0x1800c1cb7  mov     rcx, r15; pNewObject
0x1800c1cba  call    cs:__imp_CoSwitchCallContext
0x1800c1cc0  nop
0x1800c1cc1  jmp     loc_1800C1BC9
0x1800c1cc6  lea     rdx, [rsp+5C0h+var_578]; ppOldObject
0x1800c1ccb  mov     rcx, rdi; pNewObject
0x1800c1cce  call    cs:__imp_CoSwitchCallContext
0x1800c1cd4  mov     r14d, eax
0x1800c1cd7  test    eax, eax
0x1800c1cd9  jns     loc_1800C1D90
0x1800c1cdf  mov     r9d, eax
0x1800c1ce2  lea     r8, aAddingCallCont; "Adding Call context failed with hr = %x"
0x1800c1ce9  mov     edx, 144h; unsigned __int64
0x1800c1cee  lea     rcx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1cf3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1cf8  lea     rdi, WPP_GLOBAL_Control
0x1800c1cff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1d06  cmp     rcx, rdi
0x1800c1d09  jz      short loc_1800C1D30
0x1800c1d0b  test    [rcx+1Ch], bl
0x1800c1d0e  jz      short loc_1800C1D30
0x1800c1d10  cmp     byte ptr [rcx+19h], 5
0x1800c1d14  jb      short loc_1800C1D30
0x1800c1d16  mov     edx, 1Ah
0x1800c1d1b  lea     r9, [rsp+5C0h+var_550]
0x1800c1d20  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1d27  mov     rcx, [rcx+10h]
0x1800c1d2b  call    WPP_SF_S
0x1800c1d30  lea     rdx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1d35  call    ?LogMsg@@YAXIPEAG@Z; LogMsg(uint,ushort *)
0x1800c1d3a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800c1d40  mov     edx, r14d
0x1800c1d43  mov     rcx, rax
0x1800c1d46  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800c1d4c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1d53  cmp     rcx, rdi
0x1800c1d56  jz      short loc_1800C1D7C
0x1800c1d58  test    [rcx+1Ch], bl
0x1800c1d5b  jz      short loc_1800C1D7C
0x1800c1d5d  cmp     byte ptr [rcx+19h], 2
0x1800c1d61  jb      short loc_1800C1D7C
0x1800c1d63  mov     edx, 1Bh
0x1800c1d68  mov     r9d, r14d
0x1800c1d6b  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1d72  mov     rcx, [rcx+10h]
0x1800c1d76  call    WPP_SF_d
0x1800c1d7b  nop
0x1800c1d7c  lea     rdx, [rsp+5C0h+var_578]; ppOldObject
0x1800c1d81  mov     rcx, r15; pNewObject
0x1800c1d84  call    cs:__imp_CoSwitchCallContext
0x1800c1d8a  nop
0x1800c1d8b  jmp     loc_1800C1BC9
0x1800c1d90  mov     [rsp+5C0h+ppv], 0
0x1800c1d99  lea     rax, [rsp+5C0h+ppv]
0x1800c1d9e  mov     qword ptr [rsp+5C0h+dwCreationDisposition], rax; ppv
0x1800c1da3  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x1800c1daa  mov     r8d, ebx; dwClsContext
0x1800c1dad  xor     edx, edx; pUnkOuter
0x1800c1daf  lea     rcx, CLSID_WbemLocator; rclsid
0x1800c1db6  call    cs:__imp_CoCreateInstance
0x1800c1dbc  mov     r14d, eax
0x1800c1dbf  test    eax, eax
0x1800c1dc1  jns     loc_1800C1E6E
0x1800c1dc7  mov     r9d, eax
0x1800c1dca  lea     r8, aCocreateinstan_0; "CoCreateInstance failed with hr = %x"
0x1800c1dd1  mov     esi, 144h
0x1800c1dd6  mov     edx, esi; unsigned __int64
0x1800c1dd8  lea     rcx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1ddd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1de2  lea     rdi, WPP_GLOBAL_Control
0x1800c1de9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c1df0  cmp     rcx, rdi
0x1800c1df3  jz      short loc_1800C1E1A
0x1800c1df5  test    [rcx+1Ch], bl
0x1800c1df8  jz      short loc_1800C1E1A
0x1800c1dfa  cmp     byte ptr [rcx+19h], 5
0x1800c1dfe  jb      short loc_1800C1E1A
0x1800c1e00  mov     edx, 1Ch
0x1800c1e05  lea     r9, [rsp+5C0h+var_550]
0x1800c1e0a  lea     r8, WPP_5408b06df5623370e14f3985ecb7b765_Traceguids
0x1800c1e11  mov     rcx, [rcx+10h]
0x1800c1e15  call    WPP_SF_S
0x1800c1e1a  lea     rdx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1e1f  call    ?LogMsg@@YAXIPEAG@Z; LogMsg(uint,ushort *)
0x1800c1e24  mov     dword ptr [rsp+5C0h+dwFlagsAndAttributes], r14d
0x1800c1e29  mov     [rsp+5C0h+dwCreationDisposition], 19Dh
0x1800c1e31  lea     r9, aOnecoreAdminWm_3; "onecore\\admin\\wmi\\wbem\\winmgmt\\cor"...
0x1800c1e38  lea     r8, aSDHresult0xX; "%S@%d, HRESULT: 0x%x"
0x1800c1e3f  mov     rdx, rsi; unsigned __int64
0x1800c1e42  lea     rcx, [rbp+4C0h+var_2C0]; unsigned __int16 *
0x1800c1e49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1e4e  nop
0x1800c1e4f  lea     rcx, [rsp+5C0h+ppv]
0x1800c1e54  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIWbemClassObject@@$1?_GUID_dc12a681_737f_11cf_884d_00aa004b2e24@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IWbemClassObject,&__s_GUID const _GUID_dc12a681_737f_11cf_884d_00aa004b2e24>>::_Release(void)
0x1800c1e59  nop
0x1800c1e5a  lea     rdx, [rsp+5C0h+var_578]; ppOldObject
0x1800c1e5f  mov     rcx, r15; pNewObject
0x1800c1e62  call    cs:__imp_CoSwitchCallContext
0x1800c1e68  nop
0x1800c1e69  jmp     loc_1800C1BC9
0x1800c1e6e  mov     rdx, [rsp+5C0h+ppv]; struct IWbemLocator *
0x1800c1e73  mov     rcx, rsi; this
0x1800c1e76  call    ?PutObjects@CRepositoryApply@@AEAAJPEAUIWbemLocator@@@Z; CRepositoryApply::PutObjects(IWbemLocator *)
0x1800c1e7b  mov     r14d, eax
0x1800c1e7e  test    eax, eax
0x1800c1e80  jns     loc_1800C1F2D
0x1800c1e86  mov     r9d, eax
0x1800c1e89  lea     r8, aPutobjectsFail; "PutObjects failed with hr = %x"
0x1800c1e90  mov     esi, 144h
0x1800c1e95  mov     edx, esi; unsigned __int64
0x1800c1e97  lea     rcx, [rsp+5C0h+var_550]; unsigned __int16 *
0x1800c1e9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
  ... truncated ...
```
