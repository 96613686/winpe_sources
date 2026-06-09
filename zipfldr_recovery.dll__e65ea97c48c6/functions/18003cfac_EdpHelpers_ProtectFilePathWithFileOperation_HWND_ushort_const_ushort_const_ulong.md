# EdpHelpers::ProtectFilePathWithFileOperation(HWND__ *,ushort const *,ushort const *,ulong)

- ea: `0x18003cfac`
- end: `0x18003d14b`
- name: `?ProtectFilePathWithFileOperation@EdpHelpers@@YAJPEAUHWND__@@PEBG1K@Z`
- size: `415`
- prototype: `__int64 __fastcall(HWND this, HWND pszPath, struct IShellItemArray *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b430`
- `0x18001f284`

## callees

- `0x18001367c`
- `0x180031e94`
- `0x180036f50`
- `0x18003cfac`
- `0x18003d154`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18003cff2`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003cff2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d049`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d049`

## pseudocode

```c
__int64 __fastcall EdpHelpers::ProtectFilePathWithFileOperation(
        HWND this,
        const WCHAR *pszPath,
        struct IShellItemArray *a3,
        const unsigned __int16 *a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  HRESULT v9; // eax
  __int64 v10; // rdx
  LPVOID v11; // rbx
  __int64 (__fastcall *v12)(LPVOID, GUID *, HWND *); // rdi
  int v13; // eax
  const unsigned __int16 *v14; // r9
  __int64 v15; // rdx
  unsigned int v17; // [rsp+20h] [rbp-30h]
  LPVOID v18; // [rsp+30h] [rbp-20h] BYREF
  HWND v19; // [rsp+38h] [rbp-18h] BYREF
  void *ppv; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v7 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v18 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    v9 = CoCreateInstance(&CLSID_ShellItemArrayAsCollection, 0, 1u, &GUID_5632b1a4_e38a_400a_928a_d4cd63230295, &v18);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, void *))(*(_QWORD *)v18 + 40LL))(v18, ppv);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v11 = v18;
        v19 = 0;
        v12 = **(__int64 (__fastcall ***)(LPVOID, GUID *, HWND *))v18;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        v13 = v12(v11, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &v19);
        v8 = v13;
        if ( v13 >= 0 )
        {
          v13 = EdpHelpers::ProtectFilesWithFileOperation(this, v19, a3, v14, v17);
          v8 = v13;
          if ( v13 >= 0 )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
            v8 = 0;
            goto LABEL_15;
          }
          v15 = 592;
        }
        else
        {
          v15 = 591;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
          (const char *)(unsigned int)v13);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        goto LABEL_6;
      }
      v10 = 589;
    }
    else
    {
      v10 = 588;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
      (const char *)(unsigned int)v9);
LABEL_6:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24A,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\EdpHelpers.h",
    (const char *)(unsigned int)v7);
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return v8;
}

```

## disassembly

```asm
0x18003cfac  push    rbp
0x18003cfae  push    rbx
0x18003cfaf  push    rsi
0x18003cfb0  push    rdi
0x18003cfb1  push    r14
0x18003cfb3  mov     rbp, rsp
0x18003cfb6  sub     rsp, 50h
0x18003cfba  mov     rax, cs:__security_cookie
0x18003cfc1  xor     rax, rsp
0x18003cfc4  mov     [rbp+var_8], rax
0x18003cfc8  mov     rsi, rcx
0x18003cfcb  mov     [rbp+ppv], 0
0x18003cfd3  lea     rcx, [rbp+ppv]
0x18003cfd7  mov     r14, r8
0x18003cfda  mov     rbx, rdx
0x18003cfdd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003cfe2  lea     r9, [rbp+ppv]; ppv
0x18003cfe6  xor     edx, edx; pbc
0x18003cfe8  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003cfef  mov     rcx, rbx; pszPath
0x18003cff2  call    cs:__imp_SHCreateItemFromParsingName
0x18003cff8  mov     ebx, eax
0x18003cffa  test    eax, eax
0x18003cffc  jns     short loc_18003D01B
0x18003cffe  mov     rcx, [rbp+28h]
0x18003d002  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18003d009  mov     r9d, eax
0x18003d00c  mov     edx, 24Ah
0x18003d011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d016  jmp     loc_18003D129
0x18003d01b  lea     rcx, [rbp+var_20]
0x18003d01f  mov     [rbp+var_20], 0
0x18003d027  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d02c  xor     edx, edx; pUnkOuter
0x18003d02e  lea     rax, [rbp+var_20]
0x18003d032  lea     r9, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295; riid
0x18003d039  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x18003d03e  lea     rcx, CLSID_ShellItemArrayAsCollection; rclsid
0x18003d045  lea     r8d, [rdx+1]; dwClsContext
0x18003d049  call    cs:__imp_CoCreateInstance
0x18003d04f  mov     ebx, eax
0x18003d051  test    eax, eax
0x18003d053  jns     short loc_18003D07B
0x18003d055  mov     edx, 24Ch
0x18003d05a  mov     rcx, [rbp+28h]
0x18003d05e  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18003d065  mov     r9d, eax
0x18003d068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d06d  lea     rcx, [rbp+var_20]
0x18003d071  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d076  jmp     loc_18003D129
0x18003d07b  mov     rcx, [rbp+var_20]
0x18003d07f  mov     rdx, [rbp+ppv]
0x18003d083  mov     rax, [rcx]
0x18003d086  mov     rax, [rax+28h]
0x18003d08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d08f  mov     ebx, eax
0x18003d091  test    eax, eax
0x18003d093  jns     short loc_18003D09C
0x18003d095  mov     edx, 24Dh
0x18003d09a  jmp     short loc_18003D05A
0x18003d09c  mov     rbx, [rbp+var_20]
0x18003d0a0  lea     rcx, [rbp+var_18]
0x18003d0a4  mov     [rbp+var_18], 0
0x18003d0ac  mov     rax, [rbx]
0x18003d0af  mov     rdi, [rax]
0x18003d0b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d0b7  lea     r8, [rbp+var_18]
0x18003d0bb  mov     rcx, rbx
0x18003d0be  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18003d0c5  mov     rax, rdi
0x18003d0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0cd  mov     ebx, eax
0x18003d0cf  test    eax, eax
0x18003d0d1  jns     short loc_18003D0F9
0x18003d0d3  mov     edx, 24Fh
0x18003d0d8  mov     rcx, [rbp+28h]
0x18003d0dc  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18003d0e3  mov     r9d, eax
0x18003d0e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d0eb  lea     rcx, [rbp+var_18]
0x18003d0ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d0f4  jmp     loc_18003D06D
0x18003d0f9  mov     rdx, [rbp+var_18]; HWND
0x18003d0fd  mov     r8, r14; struct IShellItemArray *
0x18003d100  mov     rcx, rsi; this
0x18003d103  call    ?ProtectFilesWithFileOperation@EdpHelpers@@YAJPEAUHWND__@@PEAUIShellItemArray@@PEBGK@Z; EdpHelpers::ProtectFilesWithFileOperation(HWND__ *,IShellItemArray *,ushort const *,ulong)
0x18003d108  mov     ebx, eax
0x18003d10a  test    eax, eax
0x18003d10c  jns     short loc_18003D115
0x18003d10e  mov     edx, 250h
0x18003d113  jmp     short loc_18003D0D8
0x18003d115  lea     rcx, [rbp+var_18]
0x18003d119  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d11e  lea     rcx, [rbp+var_20]
0x18003d122  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d127  xor     ebx, ebx
0x18003d129  lea     rcx, [rbp+ppv]
0x18003d12d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d132  mov     eax, ebx
0x18003d134  mov     rcx, [rbp+var_8]
0x18003d138  xor     rcx, rsp; StackCookie
0x18003d13b  call    __security_check_cookie
0x18003d140  add     rsp, 50h
0x18003d144  pop     r14
0x18003d146  pop     rdi
0x18003d147  pop     rsi
0x18003d148  pop     rbx
0x18003d149  pop     rbp
0x18003d14a  retn
```
