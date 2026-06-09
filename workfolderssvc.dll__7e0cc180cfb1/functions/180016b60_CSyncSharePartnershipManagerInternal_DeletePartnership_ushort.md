# CSyncSharePartnershipManagerInternal::DeletePartnership(ushort *)

- ea: `0x180016b60`
- end: `0x180016e0b`
- name: `?DeletePartnership@CSyncSharePartnershipManagerInternal@@UEAAJPEAG@Z`
- size: `683`
- prototype: `__int64 __fastcall(CSyncSharePartnershipManagerInternal *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007e10`
- `0x180007f1c`
- `0x1800084bc`
- `0x180008b60`
- `0x180009384`
- `0x180011314`
- `0x180016b60`
- `0x180018f84`
- `0x1800215e0`
- `0x1800217f4`
- `0x180023e64`
- `0x180024ba0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180016dbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180016dc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180016dd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180016dbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180016dc8`
- `OLEAUT32!__imp_SysFreeString` at `0x180016dd4`
- `OLEAUT32!__imp_SysStringLen` at `0x180016c15`
- `OLEAUT32!__imp_SysStringLen` at `0x180016c15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d2d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180016c50`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180016c50`

## string_xrefs

- `0x180016bea`: `CSyncSharePartnershipManagerInternal::DeletePartnership`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSyncSharePartnershipManagerInternal::DeletePartnership(
        CSyncStateManager **this,
        unsigned __int16 *a2)
{
  _BYTE *v4; // rax
  char v5; // al
  HRESULT v6; // eax
  CSyncStateManager *v7; // rax
  int v8; // ecx
  DWORD v9; // ebx
  __int64 v10; // rdx
  int v11; // ecx
  DWORD dwMessageId; // [rsp+40h] [rbp-8A8h] BYREF
  int v14; // [rsp+44h] [rbp-8A4h]
  char v15; // [rsp+48h] [rbp-8A0h]
  const char *v16; // [rsp+50h] [rbp-898h]
  __int64 v17; // [rsp+58h] [rbp-890h]
  BSTR bstrString; // [rsp+60h] [rbp-888h] BYREF
  BSTR v19; // [rsp+68h] [rbp-880h] BYREF
  BSTR v20; // [rsp+70h] [rbp-878h] BYREF
  int pExceptionObject; // [rsp+78h] [rbp-870h] BYREF
  HRESULT v22; // [rsp+7Ch] [rbp-86Ch] BYREF
  DWORD v23; // [rsp+80h] [rbp-868h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp-860h] BYREF
  char v25; // [rsp+90h] [rbp-858h]
  DWORD *v26; // [rsp+98h] [rbp-850h] BYREF
  _BYTE v27[32]; // [rsp+A0h] [rbp-848h] BYREF
  unsigned __int16 v28; // [rsp+C0h] [rbp-828h] BYREF
  _BYTE v29[2046]; // [rsp+C2h] [rbp-826h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) == 0 || v4[65] < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  dwMessageId = 0;
  v14 = 981;
  v15 = v5;
  v16 = "CSyncSharePartnershipManagerInternal::DeletePartnership";
  v17 = 0;
  v20 = 0;
  v19 = 0;
  bstrString = 0;
  try
  {
    if ( !SysStringLen(a2) )
    {
      dwMessageId = -2147024809;
      HIWORD(v14) = 989;
      pExceptionObject = -2147024809;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v14) = 989;
    v6 = CoImpersonateClient();
    dwMessageId = v6;
    if ( v6 < 0 )
    {
      HIWORD(v14) = 991;
      v22 = v6;
      throw (long *)&v22;
    }
    LOWORD(v14) = 991;
    CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, this + 27);
    CSyncStateManager::AddImpersonatingUser(this[18], (__int64)v27);
    std::wstring::~wstring(v27);
    CSyncSharePartnershipManagerInternal::GetPartnershipInformation(
      (CSyncSharePartnershipManagerInternal *)this,
      a2,
      &v20,
      &v19,
      &bstrString);
    v7 = (CSyncStateManager *)std::shared_ptr<CSyncEngineRunner>::operator-><CSyncEngineRunner,0>(this + 18);
    CSyncStateManager::DeletePartnership(v7, a2);
    if ( (Microsoft_Windows_WorkFoldersEnableBits & 1) != 0 )
      McTemplateU0zzz_EventWriteTransfer(
        v8,
        (unsigned int)ECSHOST_EVENT_PARTNERSHIP_DELETED,
        (_DWORD)v20,
        (_DWORD)v19,
        (__int64)bstrString);
    if ( v25 )
    {
      LeaveCriticalSection(lpCriticalSection);
      v25 = 0;
    }
  }
  catch ( long v23 )
  {
    dwMessageId = v23;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v14) = 1005;
    dwMessageId = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v14) = 1005;
    dwMessageId = -2147418113;
  }
  catch ( const ATL::CAtlException *v26 )
  {
    HIWORD(v14) = 1005;
    dwMessageId = *v26;
  }
  v9 = dwMessageId;
  if ( (dwMessageId & 0x80000000) != 0 && (Microsoft_Windows_WorkFoldersEnableBits & 2) != 0 )
  {
    v28 = 0;
    memset_0(v29, 0, sizeof(v29));
    CEcsFunctionTracer::GetErrorText(dwMessageId, v10, &v28);
    McTemplateU0zzzzd_EventWriteTransfer(
      v11,
      (unsigned int)ECSHOST_EVENT_PARTNERSHIP_DELETE_FAILED,
      (_DWORD)v20,
      (_DWORD)v19,
      (__int64)bstrString,
      (__int64)&v28,
      dwMessageId);
    v9 = dwMessageId;
  }
  SysFreeString(bstrString);
  SysFreeString(v19);
  SysFreeString(v20);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&dwMessageId);
  return v9;
}

```

## disassembly

```asm
0x180016b60  mov     [rsp+arg_10], rbx
0x180016b65  push    rsi
0x180016b66  push    rdi
0x180016b67  push    r14
0x180016b69  sub     rsp, 8D0h
0x180016b70  mov     rax, cs:__security_cookie
0x180016b77  xor     rax, rsp
0x180016b7a  mov     [rsp+8E8h+var_28], rax
0x180016b82  mov     rsi, rdx
0x180016b85  mov     r14, rcx
0x180016b88  lea     rcx, WPP_GLOBAL_Control
0x180016b8f  mov     rax, cs:WPP_GLOBAL_Control
0x180016b96  cmp     rax, rcx
0x180016b99  jz      short loc_180016BC3
0x180016b9b  test    byte ptr [rax+44h], 8
0x180016b9f  jz      short loc_180016BD5
0x180016ba1  cmp     byte ptr [rax+41h], 6
0x180016ba5  jb      short loc_180016BC3
0x180016ba7  mov     edx, 47h ; 'G'
0x180016bac  lea     r8, WPP_a07fd3f09ac63a890e6e371c1c9ab69c_Traceguids
0x180016bb3  mov     rcx, [rax+38h]
0x180016bb7  call    WPP_SF_
0x180016bbc  mov     rax, cs:WPP_GLOBAL_Control
0x180016bc3  test    byte ptr [rax+44h], 8
0x180016bc7  jz      short loc_180016BD5
0x180016bc9  cmp     byte ptr [rax+41h], 6
0x180016bcd  jb      short loc_180016BD5
0x180016bcf  mov     al, 1
0x180016bd1  xor     edi, edi
0x180016bd3  jmp     short loc_180016BDA
0x180016bd5  xor     edi, edi
0x180016bd7  mov     al, dil
0x180016bda  mov     [rsp+8E8h+dwMessageId], edi
0x180016bde  mov     [rsp+8E8h+var_8A4], 3D5h
0x180016be6  mov     [rsp+8E8h+var_8A0], al
0x180016bea  lea     rax, aCsyncsharepart_25; "CSyncSharePartnershipManagerInternal::D"...
0x180016bf1  mov     [rsp+8E8h+var_898], rax
0x180016bf6  mov     [rsp+8E8h+var_890], rdi
0x180016bfb  mov     [rsp+8E8h+var_878], rdi
0x180016c00  mov     [rsp+8E8h+var_880], rdi
0x180016c05  mov     [rsp+8E8h+bstrString], rdi
0x180016c0a  mov     eax, [rsp+8E8h+dwMessageId]
0x180016c0e  mov     [rsp+8E8h+dwMessageId], eax
0x180016c12  mov     rcx, rsi; pbstr
0x180016c15  call    cs:__imp_SysStringLen
0x180016c1b  test    eax, eax
0x180016c1d  mov     eax, 3DDh
0x180016c22  jnz     short loc_180016C47
0x180016c24  mov     ecx, 80070057h
0x180016c29  mov     [rsp+8E8h+dwMessageId], ecx
0x180016c2d  mov     word ptr [rsp+8E8h+var_8A4+2], ax
0x180016c32  mov     [rsp+8E8h+pExceptionObject], ecx
0x180016c36  lea     rdx, _TI1J; pThrowInfo
0x180016c3d  lea     rcx, [rsp+8E8h+pExceptionObject]; pExceptionObject
0x180016c42  call    _CxxThrowException_0
0x180016c47  mov     [rsp+8E8h+dwMessageId], edi
0x180016c4b  mov     word ptr [rsp+8E8h+var_8A4], ax
0x180016c50  call    cs:__imp_CoImpersonateClient
0x180016c56  mov     [rsp+8E8h+dwMessageId], eax
0x180016c5a  mov     [rsp+8E8h+dwMessageId], eax
0x180016c5e  mov     ecx, 3DFh
0x180016c63  test    eax, eax
0x180016c65  jns     short loc_180016C81
0x180016c67  mov     word ptr [rsp+8E8h+var_8A4+2], cx
0x180016c6c  mov     [rsp+8E8h+var_86C], eax
0x180016c70  lea     rdx, _TI1J; pThrowInfo
0x180016c77  lea     rcx, [rsp+8E8h+var_86C]; pExceptionObject
0x180016c7c  call    _CxxThrowException_0
0x180016c81  mov     word ptr [rsp+8E8h+var_8A4], cx
0x180016c86  lea     rdx, [r14+0D8h]
0x180016c8d  lea     rcx, [rsp+8E8h+lpCriticalSection]
0x180016c95  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x180016c9a  nop
0x180016c9b  lea     rbx, [r14+90h]
0x180016ca2  lea     rdx, [rsp+8E8h+var_848]
0x180016caa  mov     rcx, [rbx]; this
0x180016cad  call    ?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CSyncStateManager::AddImpersonatingUser(void)
0x180016cb2  lea     rcx, [rsp+8E8h+var_848]
0x180016cba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016cbf  lea     rax, [rsp+8E8h+bstrString]
0x180016cc4  mov     [rsp+8E8h+var_8C8], rax; unsigned __int16 **
0x180016cc9  lea     r9, [rsp+8E8h+var_880]; unsigned __int16 **
0x180016cce  lea     r8, [rsp+8E8h+var_878]; unsigned __int16 **
0x180016cd3  mov     rdx, rsi; unsigned __int16 *
0x180016cd6  mov     rcx, r14; this
0x180016cd9  call    ?GetPartnershipInformation@CSyncSharePartnershipManagerInternal@@AEAAXPEAGPEAPEAG11@Z; CSyncSharePartnershipManagerInternal::GetPartnershipInformation(ushort *,ushort * *,ushort * *,ushort * *)
0x180016cde  mov     rcx, rbx
0x180016ce1  call    ??$?CVCSyncEngineRunner@@$0A@@?$shared_ptr@VCSyncEngineRunner@@@std@@QEBAPEAVCSyncEngineRunner@@XZ; std::shared_ptr<CSyncEngineRunner>::operator-><CSyncEngineRunner,0>(void)
0x180016ce6  mov     rdx, rsi; unsigned __int16 *
0x180016ce9  mov     rcx, rax; this
0x180016cec  call    ?DeletePartnership@CSyncStateManager@@QEAAXPEBG@Z; CSyncStateManager::DeletePartnership(ushort const *)
0x180016cf1  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 1
0x180016cf8  jz      short loc_180016D1B
0x180016cfa  mov     rax, [rsp+8E8h+bstrString]
0x180016cff  mov     [rsp+8E8h+var_8C8], rax
0x180016d04  mov     r9, [rsp+8E8h+var_880]
0x180016d09  mov     r8, [rsp+8E8h+var_878]
0x180016d0e  lea     rdx, ECSHOST_EVENT_PARTNERSHIP_DELETED
0x180016d15  call    McTemplateU0zzz_EventWriteTransfer
0x180016d1a  nop
0x180016d1b  cmp     [rsp+8E8h+var_858], dil
0x180016d23  jz      short loc_180016D3B
0x180016d25  mov     rcx, [rsp+8E8h+lpCriticalSection]; lpCriticalSection
0x180016d2d  call    cs:__imp_LeaveCriticalSection
0x180016d33  mov     [rsp+8E8h+var_858], dil
0x180016d3b  jmp     short loc_180016D45
0x180016d3d  jmp     short loc_180016D43
0x180016d3f  jmp     short loc_180016D43
0x180016d41  jmp     short $+2
0x180016d43  xor     edi, edi
0x180016d45  mov     ebx, [rsp+8E8h+dwMessageId]
0x180016d49  test    ebx, ebx
0x180016d4b  jns     short loc_180016DB7
0x180016d4d  test    byte ptr cs:Microsoft_Windows_WorkFoldersEnableBits, 2
0x180016d54  jz      short loc_180016DB7
0x180016d56  mov     [rsp+8E8h+var_828], di
0x180016d5e  xor     edx, edx; Val
0x180016d60  mov     r8d, 7FEh; Size
0x180016d66  lea     rcx, [rsp+8E8h+var_826]; void *
0x180016d6e  call    memset_0
0x180016d73  lea     r8, [rsp+8E8h+var_828]; unsigned __int16 *
0x180016d7b  mov     ecx, ebx; dwMessageId
0x180016d7d  call    ?GetErrorText@CEcsFunctionTracer@@SAXJ_KPEAG@Z; CEcsFunctionTracer::GetErrorText(long,unsigned __int64,ushort *)
0x180016d82  mov     [rsp+8E8h+var_8B8], ebx
0x180016d86  lea     rax, [rsp+8E8h+var_828]
0x180016d8e  mov     [rsp+8E8h+var_8C0], rax
0x180016d93  mov     rax, [rsp+8E8h+bstrString]
0x180016d98  mov     [rsp+8E8h+var_8C8], rax
0x180016d9d  mov     r9, [rsp+8E8h+var_880]
0x180016da2  mov     r8, [rsp+8E8h+var_878]
0x180016da7  lea     rdx, ECSHOST_EVENT_PARTNERSHIP_DELETE_FAILED
0x180016dae  call    McTemplateU0zzzzd_EventWriteTransfer
0x180016db3  mov     ebx, [rsp+8E8h+dwMessageId]
0x180016db7  mov     rcx, [rsp+8E8h+bstrString]; bstrString
0x180016dbc  call    cs:__imp_SysFreeString
0x180016dc2  nop
0x180016dc3  mov     rcx, [rsp+8E8h+var_880]; bstrString
0x180016dc8  call    cs:__imp_SysFreeString
0x180016dce  nop
0x180016dcf  mov     rcx, [rsp+8E8h+var_878]; bstrString
0x180016dd4  call    cs:__imp_SysFreeString
0x180016dda  nop
0x180016ddb  lea     rcx, [rsp+8E8h+dwMessageId]; this
0x180016de0  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180016de5  mov     eax, ebx
0x180016de7  mov     rcx, [rsp+8E8h+var_28]
0x180016def  xor     rcx, rsp; StackCookie
0x180016df2  call    __security_check_cookie
0x180016df7  mov     rbx, [rsp+8E8h+arg_10]
0x180016dff  add     rsp, 8D0h
0x180016e06  pop     r14
0x180016e08  pop     rdi
0x180016e09  pop     rsi
0x180016e0a  retn
```
