# CHGSHealthReportHelper::InitializeWMI(IWbemServices * *)

- ea: `0x100839ae0`
- end: `0x100839d9e`
- name: `?InitializeWMI@CHGSHealthReportHelper@@CAJPEAPEAUIWbemServices@@@Z`
- size: `702`
- prototype: `__int64 __fastcall(struct IWbemServices **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x100839db0`

## callees

- `0x100839ae0`
- `0x10083e310`

## import_xrefs

- `ole32!CoInitializeEx` at `0x100839afb`
- `ole32!CoInitializeEx` at `0x100839afb`
- `ole32!CoCreateInstance` at `0x100839bc6`
- `ole32!CoCreateInstance` at `0x100839bc6`
- `ole32!CoInitializeSecurity` at `0x100839b5b`
- `ole32!CoInitializeSecurity` at `0x100839b5b`
- `ole32!CoSetProxyBlanket` at `0x100839d28`
- `ole32!CoSetProxyBlanket` at `0x100839d28`
- `OLEAUT32!__imp_SysAllocString` at `0x100839c28`
- `OLEAUT32!__imp_SysAllocString` at `0x100839c28`
- `OLEAUT32!__imp_SysFreeString` at `0x100839c93`
- `OLEAUT32!__imp_SysFreeString` at `0x100839c93`
- `sqldk!??2@YAPEAX_K@Z` at `0x100839c00`
- `sqldk!??2@YAPEAX_K@Z` at `0x100839c00`
- `sqldk!??_V@YAXPEAX@Z` at `0x100839ca5`
- `sqldk!??_V@YAXPEAX@Z` at `0x100839ca5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100839cb7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x100839cb7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839b2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839b97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839bf5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839cfc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839d72`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839b2a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839b97`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839bf5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839cfc`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100839d72`

## string_xrefs

- `0x100839b0c`: `Initialize COM library`
- `0x100839b7b`: `Initialize security`
- `0x100839bd7`: `CoCreateInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHGSHealthReportHelper::InitializeWMI(struct IWbemServices **a1)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  HRESULT v4; // eax
  volatile signed __int32 *v5; // rax
  volatile signed __int32 *v6; // rbx
  BSTR v7; // rax
  int v8; // edi
  void *v9; // rcx
  HRESULT v10; // ebx
  __int64 dwImpLevel; // [rsp+28h] [rbp-60h]
  __int64 dwImpLevela; // [rsp+28h] [rbp-60h]
  __int64 dwImpLevelb; // [rsp+28h] [rbp-60h]
  LPVOID ppv; // [rsp+A0h] [rbp+18h] BYREF
  volatile signed __int32 *v16; // [rsp+A8h] [rbp+20h]

  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
  {
    _mm_lfence();
    ex_raise(373, 14, 16, 9, L"Initialize COM library", v2);
  }
  v3 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147417831 )
  {
    _mm_lfence();
    LODWORD(dwImpLevel) = v3;
    ex_raise(373, 14, 16, 10, L"Initialize security", dwImpLevel);
  }
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  if ( v4 < 0 )
  {
    _mm_lfence();
    LODWORD(dwImpLevel) = v4;
    ex_raise(373, 14, 16, 11, L"CoCreateInstance", dwImpLevel);
  }
  v5 = (volatile signed __int32 *)operator new(0x18u);
  v6 = v5;
  v16 = v5;
  if ( v5 )
  {
    *((_QWORD *)v5 + 1) = 0;
    *((_DWORD *)v5 + 4) = 1;
    v7 = SysAllocString(L"ROOT\\Microsoft\\Windows\\Attestation");
    *(_QWORD *)v6 = v7;
    if ( !v7 )
      goto LABEL_25;
  }
  else
  {
    v6 = 0;
  }
  if ( !v6 )
  {
    _com_issue_error(-2147024882);
LABEL_25:
    _com_issue_error(-2147024882);
    __debugbreak();
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, struct IWbemServices **))(*(_QWORD *)ppv + 24LL))(
         ppv,
         *(_QWORD *)v6,
         0,
         0,
         0,
         0,
         0,
         0,
         a1);
  if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) == 1 )
  {
    if ( *(_QWORD *)v6 )
    {
      SysFreeString(*(BSTR *)v6);
      *(_QWORD *)v6 = 0;
    }
    v9 = (void *)*((_QWORD *)v6 + 1);
    if ( v9 )
    {
      operator delete[](v9);
      *((_QWORD *)v6 + 1) = 0;
    }
    operator delete((void *)v6, 0x18u);
  }
  if ( v8 < 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    LODWORD(dwImpLevela) = v8;
    ex_raise(373, 14, 16, 12, L"Connect HGS", dwImpLevela);
  }
  v10 = CoSetProxyBlanket((IUnknown *)*a1, 0xAu, 0, 0, 3u, 3u, 0, 0);
  if ( v10 < 0 )
  {
    _mm_lfence();
    ((void (__fastcall *)(_QWORD))(*a1)->lpVtbl->Release)(*a1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    LODWORD(dwImpLevelb) = v10;
    ex_raise(373, 14, 16, 13, L"Set proxy blanket", dwImpLevelb);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x100839ae0  push    rbx
0x100839ae2  push    rbp
0x100839ae3  push    rsi
0x100839ae4  push    rdi
0x100839ae5  push    r14
0x100839ae7  sub     rsp, 60h
0x100839aeb  mov     [rsp+88h+var_38], 0FFFFFFFFFFFFFFFEh
0x100839af4  mov     r14, rcx
0x100839af7  xor     edx, edx; dwCoInit
0x100839af9  xor     ecx, ecx; pvReserved
0x100839afb  call    cs:__imp_CoInitializeEx
0x100839b01  test    eax, eax
0x100839b03  jns     short loc_100839B30
0x100839b05  lfence
0x100839b08  mov     dword ptr [rsp+88h+dwImpLevel], eax
0x100839b0c  lea     rax, aInitializeComL; "Initialize COM library"
0x100839b13  mov     qword ptr [rsp+88h+dwAuthnLevel], rax
0x100839b18  mov     edx, 0Eh
0x100839b1d  mov     ecx, 175h
0x100839b22  lea     r9d, [rdx-5]
0x100839b26  lea     r8d, [rdx+2]
0x100839b2a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839b30  xor     ebp, ebp
0x100839b32  mov     [rsp+88h+pReserved3], rbp; pReserved3
0x100839b37  mov     [rsp+88h+dwCapabilities], ebp; dwCapabilities
0x100839b3b  mov     [rsp+88h+pAuthList], rbp; pAuthList
0x100839b40  mov     dword ptr [rsp+88h+dwImpLevel], 3; dwImpLevel
0x100839b48  mov     [rsp+88h+dwAuthnLevel], ebp; dwAuthnLevel
0x100839b4c  xor     r9d, r9d; pReserved1
0x100839b4f  xor     r8d, r8d; asAuthSvc
0x100839b52  mov     esi, 0FFFFFFFFh
0x100839b57  mov     edx, esi; cAuthSvc
0x100839b59  xor     ecx, ecx; pSecDesc
0x100839b5b  call    cs:__imp_CoInitializeSecurity
0x100839b61  mov     edx, 80000000h
0x100839b66  lea     ecx, [rax+rdx]
0x100839b69  test    edx, ecx
0x100839b6b  jnz     short loc_100839B9D
0x100839b6d  cmp     eax, 80010119h
0x100839b72  jz      short loc_100839B9D
0x100839b74  lfence
0x100839b77  mov     dword ptr [rsp+88h+dwImpLevel], eax
0x100839b7b  lea     rax, aInitializeSecu; "Initialize security"
0x100839b82  mov     qword ptr [rsp+88h+dwAuthnLevel], rax
0x100839b87  lea     edx, [rbp+0Eh]
0x100839b8a  mov     ecx, 175h
0x100839b8f  lea     r9d, [rbp+0Ah]
0x100839b93  lea     r8d, [rbp+10h]
0x100839b97  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839b9d  mov     [rsp+88h+ppv], rbp
0x100839ba5  lea     rax, [rsp+88h+ppv]
0x100839bad  mov     qword ptr [rsp+88h+dwAuthnLevel], rax; ppv
0x100839bb2  lea     r9, IID_IWbemLocator; riid
0x100839bb9  xor     edx, edx; pUnkOuter
0x100839bbb  lea     r8d, [rdx+1]; dwClsContext
0x100839bbf  lea     rcx, CLSID_WbemLocator; rclsid
0x100839bc6  call    cs:__imp_CoCreateInstance
0x100839bcc  test    eax, eax
0x100839bce  jns     short loc_100839BFB
0x100839bd0  lfence
0x100839bd3  mov     dword ptr [rsp+88h+dwImpLevel], eax
0x100839bd7  lea     rax, aCocreateinstan; "CoCreateInstance"
0x100839bde  mov     qword ptr [rsp+88h+dwAuthnLevel], rax
0x100839be3  mov     edx, 0Eh
0x100839be8  mov     ecx, 175h
0x100839bed  lea     r9d, [rdx-3]
0x100839bf1  lea     r8d, [rdx+2]
0x100839bf5  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839bfb  mov     ecx, 18h
0x100839c00  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x100839c06  mov     rbx, rax
0x100839c09  mov     [rsp+88h+arg_18], rax
0x100839c11  test    rax, rax
0x100839c14  jz      short loc_100839C3C
0x100839c16  mov     [rax+8], rbp
0x100839c1a  mov     dword ptr [rax+10h], 1
0x100839c21  lea     rcx, aRootMicrosoftW; "ROOT\\Microsoft\\Windows\\Attestation"
0x100839c28  call    cs:__imp_SysAllocString
0x100839c2e  mov     [rbx], rax
0x100839c31  test    rax, rax
0x100839c34  jz      loc_100839D93
0x100839c3a  jmp     short loc_100839C3F
0x100839c3c  mov     rbx, rbp
0x100839c3f  mov     [rsp+88h+arg_8], rbx
0x100839c47  test    rbx, rbx
0x100839c4a  jz      loc_100839D85
0x100839c50  mov     rcx, [rsp+88h+ppv]
0x100839c58  mov     rax, [rcx]
0x100839c5b  mov     [rsp+88h+pReserved3], r14
0x100839c60  mov     qword ptr [rsp+88h+dwCapabilities], rbp
0x100839c65  mov     [rsp+88h+pAuthList], rbp
0x100839c6a  mov     dword ptr [rsp+88h+dwImpLevel], ebp
0x100839c6e  mov     qword ptr [rsp+88h+dwAuthnLevel], rbp
0x100839c73  xor     r9d, r9d
0x100839c76  xor     r8d, r8d
0x100839c79  mov     rdx, [rbx]
0x100839c7c  call    qword ptr [rax+18h]
0x100839c7f  mov     edi, eax
0x100839c81  lock xadd [rbx+10h], esi
0x100839c86  cmp     esi, 1
0x100839c89  jnz     short loc_100839CBD
0x100839c8b  mov     rcx, [rbx]; bstrString
0x100839c8e  test    rcx, rcx
0x100839c91  jz      short loc_100839C9C
0x100839c93  call    cs:__imp_SysFreeString
0x100839c99  mov     [rbx], rbp
0x100839c9c  mov     rcx, [rbx+8]
0x100839ca0  test    rcx, rcx
0x100839ca3  jz      short loc_100839CAF
0x100839ca5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100839cab  mov     [rbx+8], rbp
0x100839caf  mov     edx, 18h
0x100839cb4  mov     rcx, rbx
0x100839cb7  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100839cbd  mov     [rsp+88h+arg_8], rbp
0x100839cc5  test    edi, edi
0x100839cc7  jns     short loc_100839D02
0x100839cc9  lfence
0x100839ccc  mov     rcx, [rsp+88h+ppv]
0x100839cd4  mov     rax, [rcx]
0x100839cd7  call    qword ptr [rax+10h]
0x100839cda  mov     dword ptr [rsp+88h+dwImpLevel], edi
0x100839cde  lea     rax, aConnectHgs; "Connect HGS"
0x100839ce5  mov     qword ptr [rsp+88h+dwAuthnLevel], rax
0x100839cea  mov     edx, 0Eh
0x100839cef  mov     ecx, 175h
0x100839cf4  lea     r9d, [rdx-2]
0x100839cf8  lea     r8d, [rdx+2]
0x100839cfc  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839d02  mov     [rsp+88h+dwCapabilities], ebp; dwCapabilities
0x100839d06  mov     [rsp+88h+pAuthList], rbp; pAuthInfo
0x100839d0b  mov     dword ptr [rsp+88h+dwImpLevel], 3; dwImpLevel
0x100839d13  mov     [rsp+88h+dwAuthnLevel], 3; dwAuthnLevel
0x100839d1b  xor     r9d, r9d; pServerPrincName
0x100839d1e  xor     r8d, r8d; dwAuthzSvc
0x100839d21  lea     edx, [r9+0Ah]; dwAuthnSvc
0x100839d25  mov     rcx, [r14]; pProxy
0x100839d28  call    cs:__imp_CoSetProxyBlanket
0x100839d2e  mov     ebx, eax
0x100839d30  test    eax, eax
0x100839d32  jns     short loc_100839D78
0x100839d34  lfence
0x100839d37  mov     rcx, [r14]
0x100839d3a  mov     r9, [rcx]
0x100839d3d  call    qword ptr [r9+10h]
0x100839d41  mov     rcx, [rsp+88h+ppv]
0x100839d49  mov     r9, [rcx]
0x100839d4c  call    qword ptr [r9+10h]
0x100839d50  mov     dword ptr [rsp+88h+dwImpLevel], ebx
0x100839d54  lea     rax, aSetProxyBlanke; "Set proxy blanket"
0x100839d5b  mov     qword ptr [rsp+88h+dwAuthnLevel], rax
0x100839d60  mov     edx, 0Eh
0x100839d65  mov     ecx, 175h
0x100839d6a  lea     r9d, [rdx-1]
0x100839d6e  lea     r8d, [rdx+2]
0x100839d72  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100839d78  mov     eax, ebx
0x100839d7a  add     rsp, 60h
0x100839d7e  pop     r14
0x100839d80  pop     rdi
0x100839d81  pop     rsi
0x100839d82  pop     rbp
0x100839d83  pop     rbx
0x100839d84  retn
0x100839d85  mov     ecx, 8007000Eh; int
0x100839d8a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x100839d8f  nop
0x100839d90  jmp     short $+2
0x100839d92  nop
0x100839d93  mov     ecx, 8007000Eh; int
0x100839d98  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x100839d9d  int     3; Trap to Debugger
```
