# CHost::SetSaferLevel(ushort *)

- ea: `0x14000b5d0`
- end: `0x14000b8c0`
- name: `?SetSaferLevel@CHost@@IEAAJPEAG@Z`
- size: `752`
- prototype: `__int64 __fastcall(CHost *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000757c`

## callees

- `0x14000b184`
- `0x14000b4c8`
- `0x14000b5d0`
- `0x14001755a`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000b6ff`
- `msvcrt!wcsrchr` at `0x14000b6ff`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b856`
- `OLEAUT32!__imp_SysFreeString` at `0x14000b856`
- `OLEAUT32!__imp_SysStringLen` at `0x14000b6eb`
- `OLEAUT32!__imp_SysStringLen` at `0x14000b6eb`
- `KERNEL32!GetLastError` at `0x14000b7e7`
- `KERNEL32!GetLastError` at `0x14000b839`
- `KERNEL32!GetLastError` at `0x14000b7e7`
- `KERNEL32!GetLastError` at `0x14000b839`
- `KERNEL32!CloseHandle` at `0x14000b866`
- `KERNEL32!CloseHandle` at `0x14000b866`
- `KERNEL32!GetProcAddress` at `0x14000b693`
- `KERNEL32!GetProcAddress` at `0x14000b6b7`
- `KERNEL32!GetProcAddress` at `0x14000b6d3`
- `KERNEL32!GetProcAddress` at `0x14000b808`
- `KERNEL32!GetProcAddress` at `0x14000b693`
- `KERNEL32!GetProcAddress` at `0x14000b6b7`
- `KERNEL32!GetProcAddress` at `0x14000b6d3`
- `KERNEL32!GetProcAddress` at `0x14000b808`
- `KERNEL32!FreeLibrary` at `0x14000b890`
- `KERNEL32!FreeLibrary` at `0x14000b890`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14000b82f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14000b82f`

## string_xrefs

- `0x14000b66c`: `advapi32.dll`
- `0x14000b6b0`: `SaferComputeTokenFromLevel`

## pseudocode

```c
__int64 __fastcall CHost::SetSaferLevel(CHost *this, unsigned __int16 *a2)
{
  __int64 v3; // rbx
  OLECHAR *v4; // rsi
  BSTR v6; // r12
  void (*v7)(void); // r15
  unsigned int v8; // ebx
  FARPROC ProcAddress; // r13
  UINT v10; // ebx
  wchar_t *v11; // rax
  int v12; // eax
  signed int LastError; // eax
  FARPROC v14; // rax
  signed int v15; // eax
  HMODULE hModule; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hToken; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp-A8h]
  FARPROC v22; // [rsp+60h] [rbp-A0h]
  _DWORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  BSTR v24; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  _BYTE v27[64]; // [rsp+8Ch] [rbp-74h] BYREF
  int v28; // [rsp+CCh] [rbp-34h]
  __int64 v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  __int128 v31; // [rsp+E0h] [rbp-20h]
  int v32; // [rsp+F0h] [rbp-10h]

  pbstr = a2;
  hModule = 0;
  hToken = 0;
  memset_0(v23, 0, 0xB0u);
  v3 = 0;
  v17 = 0;
  v4 = 0;
  v20 = 0;
  bstrString = 0;
  if ( *((_DWORD *)this + 2) == 1 )
    return 2147946951LL;
  if ( !*((_BYTE *)this + 74) )
    return 1;
  v6 = (BSTR)*((_QWORD *)this + 76);
  v7 = 0;
  if ( (int)SafeLoadLibrary("advapi32.dll", &hModule) >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "SaferIdentifyLevel");
    if ( !ProcAddress
      || (v22 = GetProcAddress(hModule, "SaferComputeTokenFromLevel")) == 0
      || (v7 = (void (*)(void))GetProcAddress(hModule, "SaferCloseLevel")) == 0 )
    {
      v8 = 1;
      goto LABEL_29;
    }
    if ( *((_BYTE *)this + 75) )
    {
      v10 = SysStringLen(pbstr);
      v11 = wcsrchr(*((const wchar_t **)this + 76), 0x2Eu);
      v12 = SafeCreateTempFile(v11, pbstr, v10, &v20, (CHAR *)&bstrString);
      v4 = bstrString;
      v8 = v12;
      if ( v12 < 0 )
        goto LABEL_27;
      v3 = v20;
      v6 = bstrString;
    }
    memset_0(v23, 0, 0xB0u);
    v25 = v3;
    v8 = 0;
    v23[0] = 176;
    v23[1] = 13;
    v24 = v6;
    v26 = 0;
    memset_0(v27, 0, sizeof(v27));
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    if ( *((_DWORD *)this + 19) != 1 || (v32 = 1, *((_BYTE *)this + 68)) )
      v32 = 2;
    if ( !((unsigned int (__fastcall *)(__int64, _DWORD *, __int64 *, const wchar_t *))ProcAddress)(
            1,
            v23,
            &v17,
            L"SCRIPT") )
      goto LABEL_25;
    if ( !((unsigned int (__fastcall *)(__int64, _QWORD, HANDLE *, __int64, _QWORD))v22)(v17, 0, &hToken, 1, 0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v14 = GetProcAddress(hModule, "SaferRecordEventLogEntry");
      if ( v14 )
        ((void (__fastcall *)(__int64, BSTR, _QWORD))v14)(v17, v6, 0);
      goto LABEL_27;
    }
    if ( hToken && !ImpersonateLoggedOnUser(hToken) )
    {
LABEL_25:
      v15 = GetLastError();
      v8 = v15;
      if ( v15 > 0 )
        v8 = (unsigned __int16)v15 | 0x80070000;
    }
LABEL_27:
    if ( v4 )
      SysFreeString(v4);
    goto LABEL_29;
  }
  v8 = 1;
LABEL_29:
  if ( hToken )
    CloseHandle(hToken);
  if ( v17 && v7 )
    v7();
  if ( hModule )
    FreeLibrary(hModule);
  return v8;
}

```

## disassembly

```asm
0x14000b5d0  mov     [rsp-8+arg_10], rbx
0x14000b5d5  mov     [rsp-8+arg_18], rsi
0x14000b5da  push    rbp
0x14000b5db  push    rdi
0x14000b5dc  push    r12
0x14000b5de  push    r13
0x14000b5e0  push    r15
0x14000b5e2  lea     rbp, [rsp-30h]
0x14000b5e7  sub     rsp, 130h
0x14000b5ee  mov     rax, cs:__security_cookie
0x14000b5f5  xor     rax, rsp
0x14000b5f8  mov     [rbp+50h+var_30], rax
0x14000b5fc  mov     [rsp+150h+pbstr], rdx
0x14000b601  mov     rdi, rcx
0x14000b604  xor     edx, edx; Val
0x14000b606  mov     [rsp+150h+hModule], 0
0x14000b60f  lea     rcx, [rsp+150h+var_E0]; void *
0x14000b614  mov     [rsp+150h+hToken], 0
0x14000b61d  mov     r8d, 0B0h; Size
0x14000b623  call    memset_0
0x14000b628  xor     ebx, ebx
0x14000b62a  mov     [rsp+150h+var_118], 0
0x14000b633  xor     esi, esi
0x14000b635  mov     [rsp+150h+var_100], rbx
0x14000b63a  mov     [rsp+150h+bstrString], rsi
0x14000b63f  lea     r13d, [rbx+1]
0x14000b643  cmp     [rdi+8], r13d
0x14000b647  jnz     short loc_14000B653
0x14000b649  mov     eax, 800711C7h
0x14000b64e  jmp     loc_14000B898
0x14000b653  cmp     [rdi+4Ah], bl
0x14000b656  jnz     short loc_14000B660
0x14000b658  mov     eax, r13d
0x14000b65b  jmp     loc_14000B898
0x14000b660  mov     r12, [rdi+260h]
0x14000b667  lea     rdx, [rsp+150h+hModule]
0x14000b66c  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x14000b673  xor     r15d, r15d
0x14000b676  call    SafeLoadLibrary
0x14000b67b  test    eax, eax
0x14000b67d  jns     short loc_14000B687
0x14000b67f  mov     ebx, r13d
0x14000b682  jmp     loc_14000B85C
0x14000b687  mov     rcx, [rsp+150h+hModule]; hModule
0x14000b68c  lea     rdx, aSaferidentifyl; "SaferIdentifyLevel"
0x14000b693  call    cs:__imp_GetProcAddress
0x14000b699  mov     r13, rax
0x14000b69c  test    rax, rax
0x14000b69f  jnz     short loc_14000B6AB
0x14000b6a1  mov     ebx, 1
0x14000b6a6  jmp     loc_14000B85C
0x14000b6ab  mov     rcx, [rsp+150h+hModule]; hModule
0x14000b6b0  lea     rdx, aSafercomputeto; "SaferComputeTokenFromLevel"
0x14000b6b7  call    cs:__imp_GetProcAddress
0x14000b6bd  mov     [rsp+150h+var_F0], rax
0x14000b6c2  test    rax, rax
0x14000b6c5  jz      short loc_14000B6A1
0x14000b6c7  mov     rcx, [rsp+150h+hModule]; hModule
0x14000b6cc  lea     rdx, aSafercloseleve; "SaferCloseLevel"
0x14000b6d3  call    cs:__imp_GetProcAddress
0x14000b6d9  mov     r15, rax
0x14000b6dc  test    rax, rax
0x14000b6df  jz      short loc_14000B6A1
0x14000b6e1  cmp     [rdi+4Bh], bl
0x14000b6e4  jz      short loc_14000B73B
0x14000b6e6  mov     rcx, [rsp+150h+pbstr]; pbstr
0x14000b6eb  call    cs:__imp_SysStringLen
0x14000b6f1  mov     rcx, [rdi+260h]; Str
0x14000b6f8  mov     edx, 2Eh ; '.'; Ch
0x14000b6fd  mov     ebx, eax
0x14000b6ff  call    cs:__imp_wcsrchr
0x14000b705  mov     rdx, [rsp+150h+pbstr]; lpBuffer
0x14000b70a  lea     rcx, [rsp+150h+bstrString]
0x14000b70f  mov     [rsp+150h+lpPathName], rcx; lpPathName
0x14000b714  lea     r9, [rsp+150h+var_100]
0x14000b719  mov     rcx, rax; lpWideCharStr
0x14000b71c  mov     r8d, ebx
0x14000b71f  call    SafeCreateTempFile
0x14000b724  mov     rsi, [rsp+150h+bstrString]
0x14000b729  mov     ebx, eax
0x14000b72b  test    eax, eax
0x14000b72d  js      loc_14000B84E
0x14000b733  mov     rbx, [rsp+150h+var_100]
0x14000b738  mov     r12, rsi
0x14000b73b  xor     edx, edx; Val
0x14000b73d  lea     rcx, [rsp+150h+var_E0]; void *
0x14000b742  mov     r8d, 0B0h; Size
0x14000b748  call    memset_0
0x14000b74d  mov     [rbp+50h+var_D0], rbx
0x14000b751  lea     rcx, [rbp+50h+var_C4]; void *
0x14000b755  xor     ebx, ebx
0x14000b757  mov     [rsp+150h+var_E0], 0B0h
0x14000b75f  xor     edx, edx; Val
0x14000b761  mov     [rsp+150h+var_DC], 0Dh
0x14000b769  mov     [rsp+150h+var_D8], r12
0x14000b76e  mov     [rbp+50h+var_C8], ebx
0x14000b771  lea     r8d, [rbx+40h]; Size
0x14000b775  call    memset_0
0x14000b77a  lea     eax, [rbx+1]
0x14000b77d  mov     [rbp+50h+var_84], ebx
0x14000b780  xorps   xmm0, xmm0
0x14000b783  mov     [rbp+50h+var_80], rbx
0x14000b787  mov     [rbp+50h+var_78], ebx
0x14000b78a  movdqa  [rbp+50h+var_70], xmm0
0x14000b78f  cmp     [rdi+4Ch], eax
0x14000b792  jnz     short loc_14000B79C
0x14000b794  mov     [rbp+50h+var_60], eax
0x14000b797  cmp     [rdi+44h], bl
0x14000b79a  jz      short loc_14000B7A3
0x14000b79c  mov     [rbp+50h+var_60], 2
0x14000b7a3  mov     ecx, eax
0x14000b7a5  lea     r9, aScript; "SCRIPT"
0x14000b7ac  mov     rax, r13
0x14000b7af  lea     r8, [rsp+150h+var_118]
0x14000b7b4  lea     rdx, [rsp+150h+var_E0]
0x14000b7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7be  test    eax, eax
0x14000b7c0  jz      short loc_14000B839
0x14000b7c2  mov     rcx, [rsp+150h+var_118]
0x14000b7c7  lea     r8, [rsp+150h+hToken]
0x14000b7cc  mov     rax, [rsp+150h+var_F0]
0x14000b7d1  mov     r9d, 1
0x14000b7d7  xor     edx, edx
0x14000b7d9  mov     [rsp+150h+lpPathName], rbx
0x14000b7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7e3  test    eax, eax
0x14000b7e5  jnz     short loc_14000B825
0x14000b7e7  call    cs:__imp_GetLastError
0x14000b7ed  mov     ebx, eax
0x14000b7ef  test    eax, eax
0x14000b7f1  jle     short loc_14000B7FC
0x14000b7f3  movzx   ebx, ax
0x14000b7f6  or      ebx, 80070000h
0x14000b7fc  mov     rcx, [rsp+150h+hModule]; hModule
0x14000b801  lea     rdx, aSaferrecordeve; "SaferRecordEventLogEntry"
0x14000b808  call    cs:__imp_GetProcAddress
0x14000b80e  test    rax, rax
0x14000b811  jz      short loc_14000B84E
0x14000b813  mov     rcx, [rsp+150h+var_118]
0x14000b818  xor     r8d, r8d
0x14000b81b  mov     rdx, r12
0x14000b81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b823  jmp     short loc_14000B84E
0x14000b825  mov     rcx, [rsp+150h+hToken]; hToken
0x14000b82a  test    rcx, rcx
0x14000b82d  jz      short loc_14000B84E
0x14000b82f  call    cs:__imp_ImpersonateLoggedOnUser
0x14000b835  test    eax, eax
0x14000b837  jnz     short loc_14000B84E
0x14000b839  call    cs:__imp_GetLastError
0x14000b83f  mov     ebx, eax
0x14000b841  test    eax, eax
0x14000b843  jle     short loc_14000B84E
0x14000b845  movzx   ebx, ax
0x14000b848  or      ebx, 80070000h
0x14000b84e  test    rsi, rsi
0x14000b851  jz      short loc_14000B85C
0x14000b853  mov     rcx, rsi; bstrString
0x14000b856  call    cs:__imp_SysFreeString
0x14000b85c  mov     rcx, [rsp+150h+hToken]; hObject
0x14000b861  test    rcx, rcx
0x14000b864  jz      short loc_14000B86C
0x14000b866  call    cs:__imp_CloseHandle
0x14000b86c  mov     rcx, [rsp+150h+var_118]
0x14000b871  test    rcx, rcx
0x14000b874  jz      short loc_14000B883
0x14000b876  test    r15, r15
0x14000b879  jz      short loc_14000B883
0x14000b87b  mov     rax, r15
0x14000b87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b883  cmp     [rsp+150h+hModule], 0
0x14000b889  jz      short loc_14000B896
0x14000b88b  mov     rcx, [rsp+150h+hModule]; hLibModule
0x14000b890  call    cs:__imp_FreeLibrary
0x14000b896  mov     eax, ebx
0x14000b898  mov     rcx, [rbp+50h+var_30]
0x14000b89c  xor     rcx, rsp; StackCookie
0x14000b89f  call    __security_check_cookie
0x14000b8a4  lea     r11, [rsp+150h+var_20]
0x14000b8ac  mov     rbx, [r11+40h]
0x14000b8b0  mov     rsi, [r11+48h]
0x14000b8b4  mov     rsp, r11
0x14000b8b7  pop     r15
0x14000b8b9  pop     r13
0x14000b8bb  pop     r12
0x14000b8bd  pop     rdi
0x14000b8be  pop     rbp
0x14000b8bf  retn
```
