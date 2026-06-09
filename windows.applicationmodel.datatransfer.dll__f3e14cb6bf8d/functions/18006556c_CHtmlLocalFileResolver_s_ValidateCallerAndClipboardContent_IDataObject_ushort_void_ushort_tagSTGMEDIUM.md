# CHtmlLocalFileResolver::s_ValidateCallerAndClipboardContent(IDataObject *,ushort,void * *,ushort * *,tagSTGMEDIUM *)

- ea: `0x18006556c`
- end: `0x18006588d`
- name: `?s_ValidateCallerAndClipboardContent@CHtmlLocalFileResolver@@CAJPEAUIDataObject@@GPEAPEAXPEAPEAGPEAUtagSTGMEDIUM@@@Z`
- size: `801`
- prototype: `__int64 __fastcall(struct IDataObject *, unsigned __int16, void **, unsigned __int16 **, struct tagSTGMEDIUM *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180061e40`
- `0x1800621e0`

## callees

- `0x180002ad0`
- `0x180043b6c`
- `0x1800652a0`
- `0x18006556c`
- `0x18007bd20`
- `0x18007bec4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800655e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800655e8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006582d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006582d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800656cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006578b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800656cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006578b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180065781`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180065781`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065803`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065622`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180065622`
- `ntdll!RtlFreeHeap` at `0x18006575a`
- `ntdll!RtlFreeHeap` at `0x18006575a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800657f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006581c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800657f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006581c`
- `api-ms-win-rtcore-ole32-clipboard-l1-1-0!OleGetClipboard` at `0x18006565e`
- `api-ms-win-rtcore-ole32-clipboard-l1-1-0!OleGetClipboard` at `0x18006565e`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180065856`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x180065856`
- `ext-ms-win-ntuser-private-l1-1-1!GetClipboardAccessToken` at `0x1800656c3`
- `ext-ms-win-ntuser-private-l1-1-1!GetClipboardAccessToken` at `0x1800656c3`

## pseudocode

```c
__int64 __fastcall CHtmlLocalFileResolver::s_ValidateCallerAndClipboardContent(
        struct IDataObject *a1,
        unsigned __int16 a2,
        void **a3,
        unsigned __int16 **a4,
        struct tagSTGMEDIUM *a5)
{
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  HRESULT Clipboard; // ebx
  LPDATAOBJECT v13; // rcx
  unsigned __int16 *Reserved1; // rdi
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v15; // r9
  signed int v16; // eax
  signed int v17; // ebx
  int v18; // eax
  unsigned __int16 **v19; // r8
  bool v20; // sf
  signed int LastError; // eax
  char *v22; // rcx
  unsigned __int16 *v23; // rax
  LPDATAOBJECT v24; // rcx
  __int64 v25; // rcx
  bool *TokenType; // [rsp+20h] [rbp-61h]
  _BYTE v28[8]; // [rsp+30h] [rbp-51h] BYREF
  LPDATAOBJECT ppDataObj; // [rsp+38h] [rbp-49h] BYREF
  __int64 v30; // [rsp+40h] [rbp-41h] BYREF
  void *phNewToken; // [rsp+48h] [rbp-39h] BYREF
  STGMEDIUM v32; // [rsp+50h] [rbp-31h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-9h] BYREF
  HSTRING string; // [rsp+90h] [rbp+Fh] BYREF

  *a3 = 0;
  *a4 = 0;
  if ( a5 )
  {
    *(_OWORD *)&a5->tymed = 0;
    a5->pUnkForRelease = 0;
  }
  v32.tymed = 0;
  *(_OWORD *)&v32.hBitmap = 0;
  v30 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Internal.DataTransfer.ClipboardPolicy",
         0x3Eu,
         &hstringHeader,
         &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x18006588CLL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_821c538a_ce59_5728_b89f_4353b3dc93b4, &v30) < 0 )
    goto LABEL_41;
  v28[0] = 0;
  if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v30 + 48LL))(v30, v28) < 0 )
    goto LABEL_41;
  if ( v28[0] )
  {
    ppDataObj = 0;
    Clipboard = OleGetClipboard(&ppDataObj);
    if ( Clipboard >= 0 )
      Clipboard = CHtmlLocalFileResolver::s_ValidateAndGetContent(a1, ppDataObj, a2, &v32);
    v13 = ppDataObj;
    if ( ppDataObj )
    {
      ppDataObj = 0;
      ((void (__fastcall *)(LPDATAOBJECT))v13->lpVtbl->Release)(v13);
    }
  }
  else
  {
    Clipboard = -2147024891;
  }
  if ( Clipboard < 0 )
    goto LABEL_41;
  ppDataObj = 0;
  Reserved1 = 0;
  *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = 0u;
  if ( (unsigned int)GetClipboardAccessToken(&ppDataObj, 14) )
  {
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = -1;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = -1;
    Reserved1 = 0;
    hstringHeader.Reserved.Reserved1 = 0;
    *(_OWORD *)P = 0;
    v18 = ARI::ProcessToken::SysAppId::Open(
            ppDataObj,
            P,
            (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **)&P[1],
            v15,
            TokenType);
    v20 = v18 < 0;
    if ( v18 > 0 )
      v20 = 1;
    if ( !v20 )
    {
      CallerIdentity::GetPackageIdFromAppId(
        (CallerIdentity *)P,
        (struct ARI::ProcessToken::AutoSysAppId *)&hstringHeader,
        v19);
      Reserved1 = (unsigned __int16 *)hstringHeader.Reserved.Reserved1;
    }
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    phNewToken = 0;
    if ( DuplicateTokenEx(ppDataObj, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      v22 = 0;
      *a3 = phNewToken;
      v23 = Reserved1;
      Reserved1 = 0;
      *a4 = v23;
      v17 = 0;
      if ( a5 )
      {
        *a5 = v32;
        v32.tymed = 0;
        *(_OWORD *)&v32.hBitmap = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      if ( v17 >= 0 )
        v17 = -2147467259;
      v22 = (char *)phNewToken;
    }
    phNewToken = 0;
    if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v22);
  }
  else
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( v17 >= 0 )
      v17 = -2147467259;
  }
  if ( Reserved1 )
    CoTaskMemFree(Reserved1);
  v24 = ppDataObj;
  ppDataObj = 0;
  if ( (unsigned __int64)&v24[-1].lpVtbl + 7 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v24);
  if ( v17 < 0 )
  {
LABEL_41:
    RoOriginateError(2147942405LL, 0);
    v17 = -2147024891;
  }
  v25 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  ReleaseStgMedium(&v32);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18006556c  mov     [rsp-8+arg_8], rbx
0x180065571  push    rbp
0x180065572  push    rsi
0x180065573  push    rdi
0x180065574  push    r12
0x180065576  push    r13
0x180065578  push    r14
0x18006557a  push    r15
0x18006557c  lea     rbp, [rsp-1Fh]
0x180065581  sub     rsp, 0A0h
0x180065588  mov     rax, cs:__security_cookie
0x18006558f  xor     rax, rsp
0x180065592  mov     [rbp+4Fh+var_38], rax
0x180065596  mov     r12, r9
0x180065599  mov     r15, r8
0x18006559c  movzx   edi, dx
0x18006559f  mov     r14, rcx
0x1800655a2  mov     rsi, [rbp+4Fh+arg_20]
0x1800655a6  xor     r13d, r13d
0x1800655a9  mov     [r8], r13
0x1800655ac  mov     [r9], r13
0x1800655af  test    rsi, rsi
0x1800655b2  jz      short loc_1800655C0
0x1800655b4  xorps   xmm0, xmm0
0x1800655b7  xor     eax, eax
0x1800655b9  movups  xmmword ptr [rsi], xmm0
0x1800655bc  mov     [rsi+10h], rax
0x1800655c0  mov     [rbp+4Fh+var_80.tymed], r13d
0x1800655c4  xorps   xmm0, xmm0
0x1800655c7  movdqu  xmmword ptr [rbp+4Fh+var_80.8], xmm0
0x1800655cc  mov     [rbp+4Fh+var_90], r13
0x1800655d0  mov     [rbp+4Fh+string], r13
0x1800655d4  lea     r9, [rbp+4Fh+string]; string
0x1800655d8  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800655dc  mov     edx, 3Eh ; '>'; length
0x1800655e1  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Internal_DataTransfer_ClipboardPolicy@@3QBGB; "Windows.ApplicationModel.Internal.DataT"...
0x1800655e8  call    cs:__imp_WindowsCreateStringReference
0x1800655ee  test    eax, eax
0x1800655f0  js      loc_180065885
0x1800655f6  mov     rbx, [rbp+4Fh+string]
0x1800655fa  mov     rcx, [rbp+4Fh+var_90]
0x1800655fe  test    rcx, rcx
0x180065601  jz      short loc_180065614
0x180065603  mov     [rbp+4Fh+var_90], r13
0x180065607  mov     rax, [rcx]
0x18006560a  mov     rax, [rax+10h]
0x18006560e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065613  nop
0x180065614  lea     r8, [rbp+4Fh+var_90]
0x180065618  lea     rdx, _GUID_821c538a_ce59_5728_b89f_4353b3dc93b4
0x18006561f  mov     rcx, rbx
0x180065622  call    cs:__imp_RoGetActivationFactory
0x180065628  test    eax, eax
0x18006562a  js      loc_180065826
0x180065630  mov     [rbp+4Fh+var_A0], r13b
0x180065634  mov     rcx, [rbp+4Fh+var_90]
0x180065638  mov     rax, [rcx]
0x18006563b  lea     rdx, [rbp+4Fh+var_A0]
0x18006563f  mov     rax, [rax+30h]
0x180065643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065648  test    eax, eax
0x18006564a  js      loc_180065826
0x180065650  cmp     [rbp+4Fh+var_A0], r13b
0x180065654  jz      short loc_18006569C
0x180065656  mov     [rbp+4Fh+ppDataObj], r13
0x18006565a  lea     rcx, [rbp+4Fh+ppDataObj]; ppDataObj
0x18006565e  call    cs:__imp_OleGetClipboard
0x180065664  mov     ebx, eax
0x180065666  test    eax, eax
0x180065668  js      short loc_180065680
0x18006566a  lea     r9, [rbp+4Fh+var_80]; struct tagSTGMEDIUM *
0x18006566e  movzx   r8d, di; unsigned __int16
0x180065672  mov     rdx, [rbp+4Fh+ppDataObj]; struct IDataObject *
0x180065676  mov     rcx, r14; struct IDataObject *
0x180065679  call    ?s_ValidateAndGetContent@CHtmlLocalFileResolver@@CAJPEAUIDataObject@@0GPEAUtagSTGMEDIUM@@@Z; CHtmlLocalFileResolver::s_ValidateAndGetContent(IDataObject *,IDataObject *,ushort,tagSTGMEDIUM *)
0x18006567e  mov     ebx, eax
0x180065680  mov     rcx, [rbp+4Fh+ppDataObj]
0x180065684  test    rcx, rcx
0x180065687  jz      short loc_18006569A
0x180065689  mov     [rbp+4Fh+ppDataObj], r13
0x18006568d  mov     rax, [rcx]
0x180065690  mov     rax, [rax+10h]
0x180065694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065699  nop
0x18006569a  jmp     short loc_1800656A1
0x18006569c  mov     ebx, 80070005h
0x1800656a1  test    ebx, ebx
0x1800656a3  js      loc_180065826
0x1800656a9  mov     [rbp+4Fh+ppDataObj], r13
0x1800656ad  mov     rdi, r13
0x1800656b0  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], r13
0x1800656b4  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+10h], r13
0x1800656b8  mov     ebx, 0Eh
0x1800656bd  mov     edx, ebx
0x1800656bf  lea     rcx, [rbp+4Fh+ppDataObj]
0x1800656c3  call    cs:__imp_GetClipboardAccessToken
0x1800656c9  test    eax, eax
0x1800656cb  jnz     short loc_1800656F1
0x1800656cd  call    cs:__imp_GetLastError
0x1800656d3  mov     ebx, eax
0x1800656d5  test    eax, eax
0x1800656d7  jle     short loc_1800656E2
0x1800656d9  movzx   ebx, ax
0x1800656dc  or      ebx, 80070000h
0x1800656e2  mov     eax, 80004005h
0x1800656e7  test    ebx, ebx
0x1800656e9  cmovns  ebx, eax
0x1800656ec  jmp     loc_1800657FB
0x1800656f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800656f5  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+8], rax
0x1800656f9  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved+10h], rax
0x1800656fd  mov     rdi, r13
0x180065700  mov     qword ptr [rbp+4Fh+hstringHeader.Reserved], r13
0x180065704  xorps   xmm0, xmm0
0x180065707  movdqu  xmmword ptr [rbp+4Fh+P], xmm0
0x18006570c  lea     r8, [rbp+4Fh+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x180065710  lea     rdx, [rbp+4Fh+P]; void *
0x180065714  mov     rcx, [rbp+4Fh+ppDataObj]; TokenHandle
0x180065718  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x18006571d  mov     r14d, 80070000h
0x180065723  test    eax, eax
0x180065725  jle     short loc_18006572F
0x180065727  movzx   eax, ax
0x18006572a  or      eax, r14d
0x18006572d  test    eax, eax
0x18006572f  js      short loc_180065742
0x180065731  lea     rdx, [rbp+4Fh+hstringHeader]; struct ARI::ProcessToken::AutoSysAppId *
0x180065735  lea     rcx, [rbp+4Fh+P]; this
0x180065739  call    ?GetPackageIdFromAppId@CallerIdentity@@YAJPEAVAutoSysAppId@ProcessToken@ARI@@PEAPEAG@Z; CallerIdentity::GetPackageIdFromAppId(ARI::ProcessToken::AutoSysAppId *,ushort * *)
0x18006573e  mov     rdi, qword ptr [rbp+4Fh+hstringHeader.Reserved]
0x180065742  mov     r8, [rbp+4Fh+P]; P
0x180065746  test    r8, r8
0x180065749  jz      short loc_180065760
0x18006574b  mov     rcx, gs:60h
0x180065754  xor     edx, edx; Flags
0x180065756  mov     rcx, [rcx+30h]; HeapHandle
0x18006575a  call    cs:__imp_RtlFreeHeap
0x180065760  mov     [rbp+4Fh+var_88], r13
0x180065764  lea     rax, [rbp+4Fh+var_88]
0x180065768  mov     [rsp+0D0h+phNewToken], rax; phNewToken
0x18006576d  mov     r9d, 2; ImpersonationLevel
0x180065773  mov     dword ptr [rsp+0D0h+TokenType], r9d; TokenType
0x180065778  xor     r8d, r8d; lpTokenAttributes
0x18006577b  mov     edx, ebx; dwDesiredAccess
0x18006577d  mov     rcx, [rbp+4Fh+ppDataObj]; hExistingToken
0x180065781  call    cs:__imp_DuplicateTokenEx
0x180065787  test    eax, eax
0x180065789  jnz     short loc_1800657AD
0x18006578b  call    cs:__imp_GetLastError
0x180065791  mov     ebx, eax
0x180065793  test    eax, eax
0x180065795  jle     short loc_18006579D
0x180065797  movzx   ebx, ax
0x18006579a  or      ebx, r14d
0x18006579d  mov     eax, 80004005h
0x1800657a2  test    ebx, ebx
0x1800657a4  cmovns  ebx, eax
0x1800657a7  mov     rcx, [rbp+4Fh+var_88]
0x1800657ab  jmp     short loc_1800657E6
0x1800657ad  mov     rax, [rbp+4Fh+var_88]
0x1800657b1  mov     rcx, r13; hObject
0x1800657b4  mov     [r15], rax
0x1800657b7  mov     rax, rdi
0x1800657ba  mov     rdi, r13
0x1800657bd  mov     [r12], rax
0x1800657c1  mov     ebx, r13d
0x1800657c4  test    rsi, rsi
0x1800657c7  jz      short loc_1800657E6
0x1800657c9  movups  xmm0, xmmword ptr [rbp+4Fh+var_80.tymed]
0x1800657cd  movups  xmmword ptr [rsi], xmm0
0x1800657d0  movsd   xmm1, [rbp+4Fh+var_80.pUnkForRelease]
0x1800657d5  movsd   qword ptr [rsi+10h], xmm1
0x1800657da  mov     [rbp+4Fh+var_80.tymed], r13d
0x1800657de  xorps   xmm0, xmm0
0x1800657e1  movdqu  xmmword ptr [rbp+4Fh+var_80.8], xmm0
0x1800657e6  mov     [rbp+4Fh+var_88], r13
0x1800657ea  lea     rax, [rcx-1]
0x1800657ee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800657f2  ja      short loc_1800657FB
0x1800657f4  call    cs:__imp_CloseHandle
0x1800657fa  nop
0x1800657fb  test    rdi, rdi
0x1800657fe  jz      short loc_18006580A
0x180065800  mov     rcx, rdi; pv
0x180065803  call    cs:__imp_CoTaskMemFree
0x180065809  nop
0x18006580a  mov     rcx, [rbp+4Fh+ppDataObj]; hObject
0x18006580e  mov     [rbp+4Fh+ppDataObj], r13
0x180065812  lea     rax, [rcx-1]
0x180065816  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006581a  ja      short loc_180065822
0x18006581c  call    cs:__imp_CloseHandle
0x180065822  test    ebx, ebx
0x180065824  jns     short loc_180065838
0x180065826  xor     edx, edx
0x180065828  mov     ecx, 80070005h
0x18006582d  call    cs:__imp_RoOriginateError
0x180065833  mov     ebx, 80070005h
0x180065838  mov     rcx, [rbp+4Fh+var_90]
0x18006583c  test    rcx, rcx
0x18006583f  jz      short loc_180065852
0x180065841  mov     [rbp+4Fh+var_90], r13
0x180065845  mov     rdx, [rcx]
0x180065848  mov     rax, [rdx+10h]
0x18006584c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065851  nop
0x180065852  lea     rcx, [rbp+4Fh+var_80]; LPSTGMEDIUM
0x180065856  call    cs:__imp_ReleaseStgMedium
0x18006585c  mov     eax, ebx
0x18006585e  mov     rcx, [rbp+4Fh+var_38]
0x180065862  xor     rcx, rsp; StackCookie
0x180065865  call    __security_check_cookie
0x18006586a  mov     rbx, [rsp+0D0h+arg_8]
0x180065872  add     rsp, 0A0h
0x180065879  pop     r15
0x18006587b  pop     r14
0x18006587d  pop     r13
0x18006587f  pop     r12
0x180065881  pop     rdi
0x180065882  pop     rsi
0x180065883  pop     rbp
0x180065884  retn
0x180065885  mov     ecx, eax; this
0x180065887  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
