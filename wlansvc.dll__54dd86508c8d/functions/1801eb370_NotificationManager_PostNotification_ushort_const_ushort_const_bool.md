# NotificationManager::PostNotification(ushort const *,ushort const *,bool *)

- ea: `0x1801eb370`
- end: `0x1801eb8e7`
- name: `?PostNotification@NotificationManager@@QEAAKPEBG0PEA_N@Z`
- size: `1399`
- prototype: `unsigned int __fastcall(NotificationManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801e9b98`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180019bd0`
- `0x18007d684`
- `0x1800c9f88`
- `0x180106340`
- `0x180107330`
- `0x1801eae3c`
- `0x1801eaf54`
- `0x1801eb370`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801eb79f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801eb79f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb810`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801eb427`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801eb427`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1801eb435`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1801eb435`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb413`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb506`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb51c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb527`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb413`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb506`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb51c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801eb527`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eb485`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eb485`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801eb88c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801eb88c`

## string_xrefs

- `0x1801eb5e2`: `<toast><visual><binding template="ToastText02"><text id="1">%s</text><text id="2">%s</text></binding></visual></toast>`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NotificationManager::PostNotification(
        NotificationManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  struct IUnknown *v8; // rbx
  unsigned int v9; // esi
  DWORD v10; // edi
  HRESULT v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  PVOID *v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // r12d
  struct IUnknown **v19; // rax
  struct IUnknown *v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  int v23; // ecx
  int v24; // ecx
  DWORD v25; // eax
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  DWORD LastError; // eax
  LPVOID ppv; // [rsp+90h] [rbp-80h] BYREF
  struct IUnknown *v31; // [rsp+98h] [rbp-78h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-68h] BYREF
  int v34; // [rsp+B0h] [rbp-60h] BYREF
  struct _FILETIME FileTime; // [rsp+B8h] [rbp-58h] BYREF
  bool *v36; // [rsp+C0h] [rbp-50h] BYREF
  int v37; // [rsp+C8h] [rbp-48h]
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-40h] BYREF
  unsigned __int16 v39[512]; // [rsp+E0h] [rbp-30h] BYREF

  v36 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_SSq(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      10,
      (unsigned int)&WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids,
      (_DWORD)a2,
      (__int64)a3,
      (char)a4);
  }
  memset_0(v39, 0, sizeof(v39));
  v8 = 0;
  v34 = 0;
  SystemTime = 0;
  FileTime = 0;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    v9 = 0;
    goto LABEL_7;
  }
  if ( (CoInitializeEx(0, 0) & 0x1FFF0000) == 0x70000 )
    v9 = (unsigned __int16)CoInitializeEx(0, 0);
  else
    v9 = CoInitializeEx(0, 0);
  if ( !v9 )
  {
LABEL_7:
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, &FileTime);
    ppv = (LPVOID)FileTime;
    v10 = FileTime.dwLowDateTime + 50000000;
    if ( (char *)ppv + 50000000 < ppv )
    {
      v9 = 534;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, &WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids, 534);
      }
      goto LABEL_79;
    }
    v33 = *(_QWORD *)&FileTime + 50000000LL;
    ppv = 0;
    v32 = 0;
    v31 = 0;
    v11 = CoCreateInstance(
            (const IID *const)((char *)this + 8),
            0,
            4u,
            &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
            &ppv);
    if ( v11 < 0 )
    {
      v9 = (unsigned __int16)v11;
      if ( (v11 & 0x1FFF0000) != 0x70000 )
        v9 = v11;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_17;
      }
      v13 = 13;
      goto LABEL_15;
    }
    v16 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v32);
    if ( v16 < 0 )
    {
      v9 = (unsigned __int16)v16;
      if ( (v16 & 0x1FFF0000) != 0x70000 )
        v9 = v16;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_17;
      }
      v13 = 14;
      goto LABEL_15;
    }
    v17 = StringCchPrintfW(
            v39,
            0x200u,
            L"<toast><visual><binding template=\"ToastText02\"><text id=\"1\">%s</text><text id=\"2\">%s</text></binding><"
             "/visual></toast>",
            a2,
            a3);
    if ( v17 < 0 )
    {
      v9 = (unsigned __int16)v17;
      if ( (v17 & 0x1FFF0000) != 0x70000 )
        v9 = v17;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_17;
      }
      v13 = 15;
      goto LABEL_15;
    }
    v18 = HIDWORD(v33);
    if ( a4 )
    {
      *a4 = 0;
      v19 = (struct IUnknown **)Microsoft::WRL::Details::Make<ToastFeedback,void * &,bool * &>(
                                  &v33,
                                  (__int64 *)this + 3,
                                  (__int64 *)&v36);
      v20 = *v19;
      *v19 = 0;
      if ( v20 )
      {
        ATL::AtlComPtrAssign(&v31, v20);
        v8 = v31;
      }
      v21 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    LODWORD(v36) = 1;
    HIDWORD(v36) = v10;
    v37 = v18;
    v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, _DWORD, unsigned __int16 *, _QWORD, _QWORD, bool **, _DWORD, _DWORD, _QWORD, struct IUnknown *, _QWORD, _DWORD, int *))(*(_QWORD *)v32 + 64LL))(
            v32,
            L"System",
            L"Windows.SystemToast.NfpAppAcquire",
            0,
            0,
            v39,
            0,
            0,
            &v36,
            0,
            0,
            0,
            v8,
            0,
            0,
            &v34);
    if ( v22 < 0 )
    {
      v9 = (unsigned __int16)v22;
      if ( (v22 & 0x1FFF0000) != 0x70000 )
        v9 = v22;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_17;
      }
      v13 = 16;
LABEL_15:
      v14 = v9;
LABEL_16:
      WPP_SF_d(v12[12], v13, &WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids, v14);
LABEL_17:
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>(&v31);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>(&v32);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>(&ppv);
LABEL_79:
      CoUninitialize();
      goto LABEL_80;
    }
    if ( !a4 )
      goto LABEL_17;
    v23 = *((_DWORD *)this + 8);
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        if ( v24 == 1 )
          *a4 = 0;
      }
      else
      {
        *a4 = 1;
      }
      goto LABEL_17;
    }
    v25 = WaitForSingleObject(*((HANDLE *)this + 3), 0x2710u);
    if ( v25 )
    {
      if ( v25 != 258 )
      {
        LastError = GetLastError();
        v9 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_17;
        }
        v13 = 19;
        v14 = LastError;
        goto LABEL_16;
      }
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
LABEL_70:
        v9 = 0;
        goto LABEL_17;
      }
      v27 = 18;
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 105) < 3u
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_70;
      }
      v27 = 17;
    }
    WPP_SF_(v26[12], v27, &WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids);
    goto LABEL_70;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, &WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids, v9);
LABEL_80:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && *((_BYTE *)v15 + 105) >= 3u && (*((_BYTE *)v15 + 108) & 1) != 0 )
    WPP_SF_d(v15[12], 20, &WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1801eb370  push    rbp
0x1801eb372  push    rbx
0x1801eb373  push    rsi
0x1801eb374  push    rdi
0x1801eb375  push    r12
0x1801eb377  push    r13
0x1801eb379  push    r14
0x1801eb37b  push    r15
0x1801eb37d  lea     rbp, [rsp-3E8h]
0x1801eb385  sub     rsp, 4F8h
0x1801eb38c  mov     rax, cs:__security_cookie
0x1801eb393  xor     rax, rsp
0x1801eb396  mov     [rbp+420h+var_50], rax
0x1801eb39d  mov     r14, r9
0x1801eb3a0  mov     r13, r8
0x1801eb3a3  mov     r12, rdx
0x1801eb3a6  mov     r15, rcx
0x1801eb3a9  mov     [rbp+420h+var_470], r9
0x1801eb3ad  lea     rdi, WPP_GLOBAL_Control
0x1801eb3b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb3bb  cmp     rcx, rdi
0x1801eb3be  jz      short loc_1801EB3EE
0x1801eb3c0  cmp     byte ptr [rcx+69h], 3
0x1801eb3c4  jb      short loc_1801EB3EE
0x1801eb3c6  test    byte ptr [rcx+6Ch], 1
0x1801eb3ca  jz      short loc_1801EB3EE
0x1801eb3cc  mov     edx, 0Ah
0x1801eb3d1  mov     [rsp+530h+var_508], r9
0x1801eb3d6  mov     [rsp+530h+ppv], r8
0x1801eb3db  mov     r9, r12
0x1801eb3de  lea     r8, WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids
0x1801eb3e5  mov     rcx, [rcx+60h]
0x1801eb3e9  call    WPP_SF_SSq
0x1801eb3ee  xor     edx, edx; Val
0x1801eb3f0  mov     r8d, 400h; Size
0x1801eb3f6  lea     rcx, [rbp+420h+var_450]; void *
0x1801eb3fa  call    memset_0
0x1801eb3ff  xor     ebx, ebx
0x1801eb401  mov     [rbp+420h+var_480], ebx
0x1801eb404  xorps   xmm0, xmm0
0x1801eb407  movups  xmmword ptr [rbp+420h+SystemTime.wYear], xmm0
0x1801eb40b  mov     qword ptr [rbp+420h+FileTime.dwLowDateTime], rbx
0x1801eb40f  xor     edx, edx; dwCoInit
0x1801eb411  xor     ecx, ecx; pvReserved
0x1801eb413  call    cs:__imp_CoInitializeEx
0x1801eb419  test    eax, eax
0x1801eb41b  js      loc_1801EB502
0x1801eb421  mov     esi, ebx
0x1801eb423  lea     rcx, [rbp+420h+SystemTime]; lpSystemTime
0x1801eb427  call    cs:__imp_GetSystemTime
0x1801eb42d  lea     rdx, [rbp+420h+FileTime]; lpFileTime
0x1801eb431  lea     rcx, [rbp+420h+SystemTime]; lpSystemTime
0x1801eb435  call    cs:__imp_SystemTimeToFileTime
0x1801eb43b  mov     eax, [rbp+420h+FileTime.dwHighDateTime]
0x1801eb43e  mov     dword ptr [rbp+420h+var_4A0+4], eax
0x1801eb441  mov     eax, [rbp+420h+FileTime.dwLowDateTime]
0x1801eb444  mov     dword ptr [rbp+420h+var_4A0], eax
0x1801eb447  mov     rax, [rbp+420h+var_4A0]
0x1801eb44b  lea     rdi, [rax+2FAF080h]
0x1801eb452  cmp     rdi, rax
0x1801eb455  jb      loc_1801EB850
0x1801eb45b  mov     [rbp+420h+var_488], rdi
0x1801eb45f  mov     [rbp+420h+var_4A0], rbx
0x1801eb463  mov     [rbp+420h+var_490], rbx
0x1801eb467  mov     [rbp+420h+var_498], rbx
0x1801eb46b  lea     rcx, [r15+8]; rclsid
0x1801eb46f  lea     rax, [rbp+420h+var_4A0]
0x1801eb473  mov     [rsp+530h+ppv], rax; ppv
0x1801eb478  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x1801eb47f  xor     edx, edx; pUnkOuter
0x1801eb481  lea     r8d, [rdx+4]; dwClsContext
0x1801eb485  call    cs:__imp_CoCreateInstance
0x1801eb48b  test    eax, eax
0x1801eb48d  jns     loc_1801EB578
0x1801eb493  mov     ecx, eax
0x1801eb495  and     ecx, 1FFF0000h
0x1801eb49b  cmp     ecx, 70000h
0x1801eb4a1  movzx   esi, ax
0x1801eb4a4  jz      short loc_1801EB4A8
0x1801eb4a6  mov     esi, eax
0x1801eb4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb4af  lea     rdi, WPP_GLOBAL_Control
0x1801eb4b6  cmp     rcx, rdi
0x1801eb4b9  jz      short loc_1801EB4E0
0x1801eb4bb  cmp     byte ptr [rcx+69h], 1
0x1801eb4bf  jb      short loc_1801EB4E0
0x1801eb4c1  test    byte ptr [rcx+6Ch], 1
0x1801eb4c5  jz      short loc_1801EB4E0
0x1801eb4c7  mov     edx, 0Dh
0x1801eb4cc  mov     r9d, esi
0x1801eb4cf  lea     r8, WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids
0x1801eb4d6  mov     rcx, [rcx+60h]
0x1801eb4da  call    WPP_SF_d
0x1801eb4df  nop
0x1801eb4e0  lea     rcx, [rbp+420h+var_498]
0x1801eb4e4  call    ??1?$com_ptr_t@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>(void)
0x1801eb4e9  nop
0x1801eb4ea  lea     rcx, [rbp+420h+var_490]
0x1801eb4ee  call    ??1?$com_ptr_t@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>(void)
0x1801eb4f3  nop
0x1801eb4f4  lea     rcx, [rbp+420h+var_4A0]
0x1801eb4f8  call    ??1?$com_ptr_t@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics,wil::err_exception_policy>(void)
0x1801eb4fd  jmp     loc_1801EB88C
0x1801eb502  xor     edx, edx; dwCoInit
0x1801eb504  xor     ecx, ecx; pvReserved
0x1801eb506  call    cs:__imp_CoInitializeEx
0x1801eb50c  and     eax, 1FFF0000h
0x1801eb511  xor     edx, edx; dwCoInit
0x1801eb513  xor     ecx, ecx; pvReserved
0x1801eb515  cmp     eax, 70000h
0x1801eb51a  jnz     short loc_1801EB527
0x1801eb51c  call    cs:__imp_CoInitializeEx
0x1801eb522  movzx   esi, ax
0x1801eb525  jmp     short loc_1801EB52F
0x1801eb527  call    cs:__imp_CoInitializeEx
0x1801eb52d  mov     esi, eax
0x1801eb52f  test    esi, esi
0x1801eb531  jz      loc_1801EB423
0x1801eb537  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb53e  cmp     rcx, rdi
0x1801eb541  jz      loc_1801EB8C2
0x1801eb547  cmp     byte ptr [rcx+69h], 1
0x1801eb54b  jb      loc_1801EB899
0x1801eb551  test    byte ptr [rcx+6Ch], 1
0x1801eb555  jz      loc_1801EB899
0x1801eb55b  mov     edx, 0Bh
0x1801eb560  mov     r9d, esi
0x1801eb563  lea     r8, WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids
0x1801eb56a  mov     rcx, [rcx+60h]
0x1801eb56e  call    WPP_SF_d
0x1801eb573  jmp     loc_1801EB892
0x1801eb578  mov     rcx, [rbp+420h+var_4A0]
0x1801eb57c  mov     rax, [rcx]
0x1801eb57f  lea     rdx, [rbp+420h+var_490]
0x1801eb583  mov     rax, [rax+18h]
0x1801eb587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb58c  test    eax, eax
0x1801eb58e  jns     short loc_1801EB5DA
0x1801eb590  mov     ecx, eax
0x1801eb592  and     ecx, 1FFF0000h
0x1801eb598  cmp     ecx, 70000h
0x1801eb59e  movzx   esi, ax
0x1801eb5a1  jz      short loc_1801EB5A5
0x1801eb5a3  mov     esi, eax
0x1801eb5a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb5ac  lea     rdi, WPP_GLOBAL_Control
0x1801eb5b3  cmp     rcx, rdi
0x1801eb5b6  jz      loc_1801EB4E0
0x1801eb5bc  cmp     byte ptr [rcx+69h], 1
0x1801eb5c0  jb      loc_1801EB4E0
0x1801eb5c6  test    byte ptr [rcx+6Ch], 1
0x1801eb5ca  jz      loc_1801EB4E0
0x1801eb5d0  mov     edx, 0Eh
0x1801eb5d5  jmp     loc_1801EB4CC
0x1801eb5da  mov     [rsp+530h+ppv], r13
0x1801eb5df  mov     r9, r12
0x1801eb5e2  lea     r8, aToastVisualBin; "<toast><visual><binding template=\"Toas"...
0x1801eb5e9  mov     edx, 200h; unsigned __int64
0x1801eb5ee  lea     rcx, [rbp+420h+var_450]; unsigned __int16 *
0x1801eb5f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801eb5f7  xor     r13d, r13d
0x1801eb5fa  test    eax, eax
0x1801eb5fc  jns     short loc_1801EB648
0x1801eb5fe  mov     ecx, eax
0x1801eb600  and     ecx, 1FFF0000h
0x1801eb606  cmp     ecx, 70000h
0x1801eb60c  movzx   esi, ax
0x1801eb60f  jz      short loc_1801EB613
0x1801eb611  mov     esi, eax
0x1801eb613  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb61a  lea     rdi, WPP_GLOBAL_Control
0x1801eb621  cmp     rcx, rdi
0x1801eb624  jz      loc_1801EB4E0
0x1801eb62a  cmp     byte ptr [rcx+69h], 1
0x1801eb62e  jb      loc_1801EB4E0
0x1801eb634  test    byte ptr [rcx+6Ch], 1
0x1801eb638  jz      loc_1801EB4E0
0x1801eb63e  mov     edx, 0Fh
0x1801eb643  jmp     loc_1801EB4CC
0x1801eb648  mov     r12d, dword ptr [rbp+420h+var_488+4]
0x1801eb64c  test    r14, r14
0x1801eb64f  jz      short loc_1801EB697
0x1801eb651  mov     [r14], r13b
0x1801eb654  lea     rdx, [r15+18h]
0x1801eb658  lea     r8, [rbp+420h+var_470]
0x1801eb65c  lea     rcx, [rbp+420h+var_488]
0x1801eb660  call    ??$Make@VToastFeedback@@AEAPEAXAEAPEA_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VToastFeedback@@@12@AEAPEAXAEAPEA_N@Z; Microsoft::WRL::Details::Make<ToastFeedback,void * &,bool * &>(void * &,bool * &)
0x1801eb665  mov     rdx, [rax]; struct IUnknown *
0x1801eb668  mov     [rax], r13
0x1801eb66b  test    rdx, rdx
0x1801eb66e  jz      short loc_1801EB67D
0x1801eb670  lea     rcx, [rbp+420h+var_498]; struct IUnknown **
0x1801eb674  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1801eb679  mov     rbx, [rbp+420h+var_498]
0x1801eb67d  mov     rcx, [rbp+420h+var_488]
0x1801eb681  test    rcx, rcx
0x1801eb684  jz      short loc_1801EB697
0x1801eb686  mov     [rbp+420h+var_488], r13
0x1801eb68a  mov     rax, [rcx]
0x1801eb68d  mov     rax, [rax+10h]
0x1801eb691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb696  nop
0x1801eb697  mov     rcx, [rbp+420h+var_490]
0x1801eb69b  mov     dword ptr [rbp+420h+var_470], 1
0x1801eb6a2  mov     dword ptr [rbp+420h+var_470+4], edi
0x1801eb6a5  mov     [rbp+420h+var_468], r12d
0x1801eb6a9  mov     rax, [rcx]
0x1801eb6ac  lea     rdx, [rbp+420h+var_480]
0x1801eb6b0  mov     [rsp+530h+var_4B8], rdx
0x1801eb6b5  mov     [rsp+530h+var_4C0], r13d
0x1801eb6ba  mov     [rsp+530h+var_4C8], r13
0x1801eb6bf  mov     [rsp+530h+var_4D0], rbx
0x1801eb6c4  mov     [rsp+530h+var_4D8], r13
0x1801eb6c9  mov     [rsp+530h+var_4E0], r13d
0x1801eb6ce  mov     [rsp+530h+var_4E8], r13d
0x1801eb6d3  lea     rdx, [rbp+420h+var_470]
0x1801eb6d7  mov     [rsp+530h+var_4F0], rdx
0x1801eb6dc  mov     [rsp+530h+var_4F8], r13
0x1801eb6e1  mov     [rsp+530h+var_500], r13
0x1801eb6e6  lea     rdx, [rbp+420h+var_450]
0x1801eb6ea  mov     [rsp+530h+var_508], rdx
0x1801eb6ef  mov     dword ptr [rsp+530h+ppv], r13d
0x1801eb6f4  xor     r9d, r9d
0x1801eb6f7  lea     r8, aWindowsSystemt; "Windows.SystemToast.NfpAppAcquire"
0x1801eb6fe  lea     rdx, aSystem; "System"
0x1801eb705  mov     rax, [rax+40h]
0x1801eb709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb70e  test    eax, eax
0x1801eb710  jns     short loc_1801EB75C
0x1801eb712  mov     ecx, eax
0x1801eb714  and     ecx, 1FFF0000h
0x1801eb71a  cmp     ecx, 70000h
0x1801eb720  movzx   esi, ax
0x1801eb723  jz      short loc_1801EB727
0x1801eb725  mov     esi, eax
0x1801eb727  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb72e  lea     rdi, WPP_GLOBAL_Control
0x1801eb735  cmp     rcx, rdi
0x1801eb738  jz      loc_1801EB4E0
0x1801eb73e  cmp     byte ptr [rcx+69h], 1
0x1801eb742  jb      loc_1801EB4E0
0x1801eb748  test    byte ptr [rcx+6Ch], 1
0x1801eb74c  jz      loc_1801EB4E0
0x1801eb752  mov     edx, 10h
0x1801eb757  jmp     loc_1801EB4CC
0x1801eb75c  test    r14, r14
0x1801eb75f  jz      short loc_1801EB78A
0x1801eb761  mov     ecx, [r15+20h]
0x1801eb765  test    ecx, ecx
0x1801eb767  jz      short loc_1801EB796
0x1801eb769  sub     ecx, 1
0x1801eb76c  jz      short loc_1801EB786
0x1801eb76e  lea     rdi, WPP_GLOBAL_Control
0x1801eb775  cmp     ecx, 1
0x1801eb778  jnz     loc_1801EB4E0
0x1801eb77e  mov     [r14], r13b
0x1801eb781  jmp     loc_1801EB4E0
0x1801eb786  mov     byte ptr [r14], 1
0x1801eb78a  lea     rdi, WPP_GLOBAL_Control
0x1801eb791  jmp     loc_1801EB4E0
0x1801eb796  mov     edx, 2710h; dwMilliseconds
0x1801eb79b  mov     rcx, [r15+18h]; hHandle
0x1801eb79f  call    cs:__imp_WaitForSingleObject
0x1801eb7a5  test    eax, eax
0x1801eb7a7  jnz     short loc_1801EB7CD
0x1801eb7a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb7b0  lea     rdi, WPP_GLOBAL_Control
0x1801eb7b7  cmp     rcx, rdi
0x1801eb7ba  jz      short loc_1801EB808
0x1801eb7bc  cmp     byte ptr [rcx+69h], 3
0x1801eb7c0  jb      short loc_1801EB808
0x1801eb7c2  test    byte ptr [rcx+6Ch], 1
0x1801eb7c6  jz      short loc_1801EB808
0x1801eb7c8  lea     edx, [rax+11h]
0x1801eb7cb  jmp     short loc_1801EB7F8
0x1801eb7cd  cmp     eax, 102h
0x1801eb7d2  jnz     short loc_1801EB810
0x1801eb7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb7db  lea     rdi, WPP_GLOBAL_Control
0x1801eb7e2  cmp     rcx, rdi
0x1801eb7e5  jz      short loc_1801EB808
0x1801eb7e7  cmp     byte ptr [rcx+69h], 1
0x1801eb7eb  jb      short loc_1801EB808
0x1801eb7ed  test    byte ptr [rcx+6Ch], 1
0x1801eb7f1  jz      short loc_1801EB808
0x1801eb7f3  mov     edx, 12h
0x1801eb7f8  lea     r8, WPP_ab1458062d2a33c91f306082e8c2afe2_Traceguids
0x1801eb7ff  mov     rcx, [rcx+60h]
0x1801eb803  call    WPP_SF_
0x1801eb808  mov     esi, r13d
0x1801eb80b  jmp     loc_1801EB4E0
0x1801eb810  call    cs:__imp_GetLastError
0x1801eb816  mov     esi, eax
0x1801eb818  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eb81f  lea     rdi, WPP_GLOBAL_Control
0x1801eb826  cmp     rcx, rdi
0x1801eb829  jz      loc_1801EB4E0
0x1801eb82f  cmp     byte ptr [rcx+69h], 1
0x1801eb833  jb      loc_1801EB4E0
0x1801eb839  test    byte ptr [rcx+6Ch], 1
  ... truncated ...
```
