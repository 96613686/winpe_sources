# AdjustPrivIfLocalSystem(void *)

- ea: `0x180015d30`
- end: `0x180015ff4`
- name: `?AdjustPrivIfLocalSystem@@YAXPEAX@Z`
- size: `708`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180015a00`

## callees

- `0x180015d30`
- `0x18001d19c`
- `0x1800442c7`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015fb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015fb6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015e32`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ee8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f99`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015f99`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015fd8`
- `ntdll!RtlLengthSid` at `0x180015db3`
- `ntdll!RtlLengthSid` at `0x180015dc0`
- `ntdll!RtlLengthSid` at `0x180015db3`
- `ntdll!RtlLengthSid` at `0x180015dc0`

## string_xrefs

- `0x180015fca`: `AdjustTokenPrivileges`
- `0x180015f1d`: `GetTokenInformation`
- `0x180015f58`: `GetTokenInformation`
- `0x180015f8b`: `GetTokenInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AdjustPrivIfLocalSystem(void *a1)
{
  FARPROC ProcAddress; // rax
  PSID v3; // rbx
  ULONG v4; // edi
  FARPROC v5; // rax
  unsigned int *v6; // rax
  unsigned int *v7; // rbx
  unsigned int v8; // edi
  FARPROC v9; // rax
  int v10; // r8d
  unsigned int v11; // eax
  unsigned int *v12; // rdx
  FARPROC v13; // rax
  DWORD SecurityDll; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  unsigned int uBytes; // [rsp+40h] [rbp-C8h] BYREF
  int uBytes_4; // [rsp+44h] [rbp-C4h] BYREF
  unsigned int *v19; // [rsp+50h] [rbp-B8h]
  _DWORD Buf1[6]; // [rsp+58h] [rbp-B0h] BYREF
  PSID Sid[12]; // [rsp+70h] [rbp-98h] BYREF

  uBytes_4 = 88;
  ProcAddress = (FARPROC)qword_180070310;
  if ( qword_180070310 )
    goto LABEL_37;
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
    return;
  }
  ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetTokenInformation");
  qword_180070310 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_37:
    if ( ((unsigned int (__fastcall *)(void *, __int64, PSID *, __int64, int *))ProcAddress)(a1, 1, Sid, 88, &uBytes_4) )
    {
      Buf1[0] = 257;
      Buf1[1] = 83886080;
      Buf1[2] = 18;
      v3 = Sid[0];
      v4 = RtlLengthSid(Sid[0]);
      if ( v4 == RtlLengthSid(Buf1) && !memcmp_0(Buf1, v3, v4) )
      {
        uBytes = 0;
        v5 = (FARPROC)qword_180070310;
        if ( qword_180070310 )
          goto LABEL_6;
        v15 = DLpLoadSecurityDll();
        if ( v15 )
        {
          SetLastError(v15);
        }
        else
        {
          v5 = GetProcAddress(g_hInstSecurityDLL, "GetTokenInformation");
          qword_180070310 = (__int64)v5;
          if ( v5 )
          {
LABEL_6:
            if ( ((unsigned int (__fastcall *)(void *, __int64, _QWORD, _QWORD, unsigned int *))v5)(
                   a1,
                   3,
                   0,
                   0,
                   &uBytes) )
            {
              goto LABEL_8;
            }
          }
        }
        if ( GetLastError() != 122 )
          return;
LABEL_8:
        v6 = (unsigned int *)LocalAlloc(0, uBytes);
        v7 = v6;
        if ( !v6 )
          return;
        v19 = v6;
        v8 = uBytes;
        v9 = (FARPROC)qword_180070310;
        if ( !qword_180070310 )
        {
          v16 = DLpLoadSecurityDll();
          if ( v16 )
            goto LABEL_31;
          v9 = GetProcAddress(g_hInstSecurityDLL, "GetTokenInformation");
          qword_180070310 = (__int64)v9;
          if ( !v9 )
            goto LABEL_18;
        }
        if ( !((unsigned int (__fastcall *)(void *, __int64, unsigned int *, _QWORD, unsigned int *))v9)(
                a1,
                3,
                v7,
                v8,
                &uBytes) )
          goto LABEL_18;
        v10 = 0;
        v11 = 0;
        if ( !*v7 )
          goto LABEL_18;
        do
        {
          v12 = &v7[3 * v11 + 3];
          if ( (*v12 & 2) == 0 )
          {
            v10 = 1;
            *v12 |= 2u;
          }
          ++v11;
        }
        while ( v11 < *v7 );
        if ( !v10 )
          goto LABEL_18;
        v13 = (FARPROC)qword_180070380;
        if ( qword_180070380 )
        {
LABEL_17:
          ((void (__fastcall *)(void *, _QWORD, unsigned int *, _QWORD, _QWORD, _QWORD))v13)(a1, 0, v7, 0, 0, 0);
LABEL_18:
          LocalFree(v7);
          return;
        }
        v16 = DLpLoadSecurityDll();
        if ( !v16 )
        {
          v13 = GetProcAddress(g_hInstSecurityDLL, "AdjustTokenPrivileges");
          qword_180070380 = (__int64)v13;
          if ( !v13 )
            goto LABEL_18;
          goto LABEL_17;
        }
LABEL_31:
        SetLastError(v16);
        goto LABEL_18;
      }
    }
  }
}

```

## disassembly

```asm
0x180015d30  push    rbx
0x180015d32  push    rbp
0x180015d33  push    rsi
0x180015d34  push    rdi
0x180015d35  sub     rsp, 0E8h
0x180015d3c  mov     rax, cs:__security_cookie
0x180015d43  xor     rax, rsp
0x180015d46  mov     [rsp+108h+var_38], rax
0x180015d4e  mov     rsi, rcx
0x180015d51  mov     [rsp+108h+uBytes+4], 58h ; 'X'
0x180015d59  mov     rax, cs:qword_180070310
0x180015d60  test    rax, rax
0x180015d63  jz      loc_180015F0A
0x180015d69  lea     rcx, [rsp+108h+uBytes+4]
0x180015d6e  mov     [rsp+108h+var_E8], rcx
0x180015d73  mov     r9d, 58h ; 'X'
0x180015d79  lea     r8, [rsp+108h+Sid]
0x180015d7e  mov     edx, 1
0x180015d83  mov     rcx, rsi
0x180015d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d8b  test    eax, eax
0x180015d8d  jz      loc_180015EEE
0x180015d93  mov     [rsp+108h+Buf1], 101h
0x180015d9b  mov     [rsp+108h+var_AC], 5000000h
0x180015da3  mov     [rsp+108h+var_A8], 12h
0x180015dab  mov     rbx, [rsp+108h+Sid]
0x180015db0  mov     rcx, rbx; Sid
0x180015db3  call    cs:__imp_RtlLengthSid
0x180015db9  mov     edi, eax
0x180015dbb  lea     rcx, [rsp+108h+Buf1]; Sid
0x180015dc0  call    cs:__imp_RtlLengthSid
0x180015dc6  cmp     edi, eax
0x180015dc8  jnz     loc_180015EEE
0x180015dce  mov     r8d, edi; Size
0x180015dd1  mov     rdx, rbx; Buf2
0x180015dd4  lea     rcx, [rsp+108h+Buf1]; Buf1
0x180015dd9  call    memcmp_0
0x180015dde  test    eax, eax
0x180015de0  jnz     loc_180015EEE
0x180015de6  xor     ebp, ebp
0x180015de8  mov     [rsp+108h+uBytes], ebp
0x180015dec  mov     rax, cs:qword_180070310
0x180015df3  test    rax, rax
0x180015df6  jz      loc_180015F42
0x180015dfc  lea     rcx, [rsp+108h+uBytes]
0x180015e01  mov     [rsp+108h+var_E8], rcx
0x180015e06  xor     r9d, r9d
0x180015e09  xor     r8d, r8d
0x180015e0c  mov     edx, 3
0x180015e11  mov     rcx, rsi
0x180015e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e19  test    eax, eax
0x180015e1b  jnz     short loc_180015E2C
0x180015e1d  call    cs:__imp_GetLastError
0x180015e23  cmp     eax, 7Ah ; 'z'
0x180015e26  jnz     loc_180015EEE
0x180015e2c  mov     edx, [rsp+108h+uBytes]; uBytes
0x180015e30  xor     ecx, ecx; uFlags
0x180015e32  call    cs:__imp_LocalAlloc
0x180015e38  mov     rbx, rax
0x180015e3b  test    rax, rax
0x180015e3e  jz      loc_180015EEE
0x180015e44  mov     [rsp+108h+var_B8], rax
0x180015e49  mov     edi, [rsp+108h+uBytes]
0x180015e4d  mov     rax, cs:qword_180070310
0x180015e54  test    rax, rax
0x180015e57  jz      loc_180015F81
0x180015e5d  lea     rcx, [rsp+108h+uBytes]
0x180015e62  mov     [rsp+108h+var_E8], rcx
0x180015e67  mov     r9d, edi
0x180015e6a  mov     r8, rbx
0x180015e6d  mov     edx, 3
0x180015e72  mov     rcx, rsi
0x180015e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e7a  test    eax, eax
0x180015e7c  jz      short loc_180015EE5
0x180015e7e  mov     r8d, ebp
0x180015e81  mov     eax, ebp
0x180015e83  cmp     [rbx], ebp
0x180015e85  jbe     short loc_180015EE5
0x180015e87  nop     word ptr [rax+rax+00000000h]
0x180015e90  mov     ecx, eax
0x180015e92  inc     rcx
0x180015e95  lea     rcx, [rcx+rcx*2]
0x180015e99  lea     rdx, [rbx+rcx*4]
0x180015e9d  mov     ecx, [rdx]
0x180015e9f  test    cl, 2
0x180015ea2  jnz     short loc_180015EAF
0x180015ea4  mov     r8d, 1
0x180015eaa  or      ecx, 2
0x180015ead  mov     [rdx], ecx
0x180015eaf  inc     eax
0x180015eb1  cmp     eax, [rbx]
0x180015eb3  jb      short loc_180015E90
0x180015eb5  test    r8d, r8d
0x180015eb8  jz      short loc_180015EE5
0x180015eba  mov     rax, cs:qword_180070380
0x180015ec1  test    rax, rax
0x180015ec4  jz      loc_180015FC1
0x180015eca  mov     [rsp+108h+var_E0], rbp
0x180015ecf  mov     [rsp+108h+var_E8], rbp
0x180015ed4  xor     r9d, r9d
0x180015ed7  mov     r8, rbx
0x180015eda  xor     edx, edx
0x180015edc  mov     rcx, rsi
0x180015edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ee4  nop
0x180015ee5  mov     rcx, rbx; hMem
0x180015ee8  call    cs:__imp_LocalFree
0x180015eee  mov     rcx, [rsp+108h+var_38]
0x180015ef6  xor     rcx, rsp; StackCookie
0x180015ef9  call    __security_check_cookie
0x180015efe  add     rsp, 0E8h
0x180015f05  pop     rdi
0x180015f06  pop     rsi
0x180015f07  pop     rbp
0x180015f08  pop     rbx
0x180015f09  retn
0x180015f0a  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180015f0f  test    eax, eax
0x180015f11  jz      short loc_180015F1D
0x180015f13  mov     ecx, eax; dwErrCode
0x180015f15  call    cs:__imp_SetLastError
0x180015f1b  jmp     short loc_180015EEE
0x180015f1d  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180015f24  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015f2b  call    cs:__imp_GetProcAddress
0x180015f31  mov     cs:qword_180070310, rax
0x180015f38  test    rax, rax
0x180015f3b  jz      short loc_180015EEE
0x180015f3d  jmp     loc_180015D69
0x180015f42  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180015f47  test    eax, eax
0x180015f49  jz      short loc_180015F58
0x180015f4b  mov     ecx, eax; dwErrCode
0x180015f4d  call    cs:__imp_SetLastError
0x180015f53  jmp     loc_180015E1D
0x180015f58  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180015f5f  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015f66  call    cs:__imp_GetProcAddress
0x180015f6c  mov     cs:qword_180070310, rax
0x180015f73  test    rax, rax
0x180015f76  jz      loc_180015E1D
0x180015f7c  jmp     loc_180015DFC
0x180015f81  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180015f86  nop
0x180015f87  test    eax, eax
0x180015f89  jnz     short loc_180015FB4
0x180015f8b  lea     rdx, aGettokeninform; "GetTokenInformation"
0x180015f92  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015f99  call    cs:__imp_GetProcAddress
0x180015f9f  mov     cs:qword_180070310, rax
0x180015fa6  test    rax, rax
0x180015fa9  jz      loc_180015EE5
0x180015faf  jmp     loc_180015E5D
0x180015fb4  mov     ecx, eax; dwErrCode
0x180015fb6  call    cs:__imp_SetLastError
0x180015fbc  jmp     loc_180015EE5
0x180015fc1  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180015fc6  test    eax, eax
0x180015fc8  jnz     short loc_180015FB4
0x180015fca  lea     rdx, aAdjusttokenpri; "AdjustTokenPrivileges"
0x180015fd1  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180015fd8  call    cs:__imp_GetProcAddress
0x180015fde  mov     cs:qword_180070380, rax
0x180015fe5  test    rax, rax
0x180015fe8  jz      loc_180015EE5
0x180015fee  jmp     loc_180015ECA
```
