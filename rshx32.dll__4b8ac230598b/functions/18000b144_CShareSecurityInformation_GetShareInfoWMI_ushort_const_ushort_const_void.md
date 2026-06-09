# CShareSecurityInformation::GetShareInfoWMI(ushort const *,ushort const *,void * *)

- ea: `0x18000b144`
- end: `0x18000b6ad`
- name: `?GetShareInfoWMI@CShareSecurityInformation@@CAJPEBG0PEAPEAX@Z`
- size: `1385`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b0b0`

## callees

- `0x18000b144`
- `0x18001d370`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000b5b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000b5b6`
- `mi!MI_Application_InitializeV1` at `0x18000b1dd`
- `mi!MI_Application_InitializeV1` at `0x18000b1dd`

## string_xrefs

- `0x18000b238`: `__MI_DESTINATIONOPTIONS_IMPERSONATION_TYPE`
- `0x18000b304`: `ScopeName`
- `0x18000b34a`: `ShareName`
- `0x18000b390`: `GetAclNonAdmin`
- `0x18000b590`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::GetShareInfoWMI(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        void **a3)
{
  unsigned int v6; // ebx
  signed int LastError; // eax
  MI_Result v9; // [rsp+60h] [rbp-A0h] BYREF
  int v10; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v11; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR v12; // [rsp+70h] [rbp-90h] BYREF
  MI_Application application; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v14[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v15[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v16[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v17; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v19; // [rsp+F0h] [rbp-10h]
  __int64 v20; // [rsp+100h] [rbp+0h]

  v10 = -1;
  memset(&application, 0, sizeof(application));
  memset(v14, 0, sizeof(v14));
  memset(v16, 0, sizeof(v16));
  memset(v15, 0, sizeof(v15));
  v11 = 0;
  v12 = 0;
  v17 = 0;
  v20 = 0;
  v6 = 0;
  *(_OWORD *)StringSecurityDescriptor = 0;
  v19 = 0;
  v9 = MI_Application_InitializeV1(0, L"MICROSOFT/WINDOWS/SMB", 0, &application);
  if ( v9 )
    goto LABEL_52;
  if ( !application.ft )
  {
    memset(v14, 0, sizeof(v14));
    goto LABEL_51;
  }
  v9 = ((unsigned int (__fastcall *)(MI_Application *, _BYTE *))application.ft->NewDestinationOptions)(
         &application,
         v14);
  if ( v9 )
    goto LABEL_52;
  if ( !*(_QWORD *)&v14[16] )
    goto LABEL_51;
  v9 = (*(unsigned int (__fastcall **)(_BYTE *, const wchar_t *, __int64, _QWORD))(*(_QWORD *)&v14[16] + 16LL))(
         v14,
         L"__MI_DESTINATIONOPTIONS_IMPERSONATION_TYPE",
         2,
         0);
  if ( v9 )
    goto LABEL_52;
  if ( !application.ft )
  {
    memset(v16, 0, sizeof(v16));
    goto LABEL_51;
  }
  v9 = ((unsigned int (__fastcall *)(MI_Application *, const wchar_t *, const unsigned __int16 *, _BYTE *, _QWORD, _QWORD, _BYTE *))application.ft->NewSession)(
         &application,
         L"WinRM",
         a1,
         v14,
         0,
         0,
         v16);
  if ( v9 )
    goto LABEL_52;
  if ( !application.ft )
  {
    v11 = 0;
    goto LABEL_51;
  }
  v9 = ((unsigned int (__fastcall *)(MI_Application *, const wchar_t *, _QWORD, __int64 *))application.ft->NewInstance)(
         &application,
         L"Parameters",
         0,
         &v11);
  if ( v9 )
    goto LABEL_52;
  StringSecurityDescriptor[0] = a1;
  if ( !v11 || !*(_QWORD *)v11 )
    goto LABEL_51;
  v9 = (*(unsigned int (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, __int64, _DWORD))(*(_QWORD *)v11 + 64LL))(
         v11,
         L"ScopeName",
         StringSecurityDescriptor,
         13,
         0);
  if ( v9 )
    goto LABEL_52;
  StringSecurityDescriptor[0] = a2;
  if ( !v11 || !*(_QWORD *)v11 )
    goto LABEL_51;
  v9 = (*(unsigned int (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, __int64, _DWORD))(*(_QWORD *)v11 + 64LL))(
         v11,
         L"ShareName",
         StringSecurityDescriptor,
         13,
         0);
  if ( v9 )
    goto LABEL_52;
  LOBYTE(StringSecurityDescriptor[0]) = 1;
  if ( !v11 || !*(_QWORD *)v11 )
  {
LABEL_51:
    v9 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_52;
  }
  v9 = (*(unsigned int (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, _QWORD, _DWORD))(*(_QWORD *)v11 + 64LL))(
         v11,
         L"GetAclNonAdmin",
         StringSecurityDescriptor,
         0,
         0);
  if ( v9 )
    goto LABEL_52;
  if ( *(_QWORD *)&v16[16] )
    (*(void (__fastcall **)(_BYTE *, _QWORD, _QWORD, const wchar_t *, const wchar_t *, const wchar_t *, _QWORD, __int64, _QWORD, _BYTE *))(*(_QWORD *)&v16[16] + 48LL))(
      v16,
      0,
      0,
      L"ROOT\\MICROSOFT\\WINDOWS\\SMB",
      L"MSFT_SmbShare",
      L"GetShare",
      0,
      v11,
      0,
      v15);
  else
    memset(v15, 0, sizeof(v15));
  if ( *(_QWORD *)&v15[16] )
    (*(void (__fastcall **)(_BYTE *, LPCWSTR *, _QWORD, MI_Result *, __int64 *, _QWORD))(*(_QWORD *)&v15[16] + 24LL))(
      v15,
      &v12,
      0,
      &v9,
      &v17,
      0);
  else
    v9 = MI_RESULT_INVALID_PARAMETER;
  if ( v9 )
    goto LABEL_52;
  if ( !v12 || !*(_QWORD *)v12 )
    goto LABEL_46;
  v9 = (*(unsigned int (__fastcall **)(LPCWSTR, const wchar_t *, LPCWSTR *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 88LL))(
         v12,
         L"Output",
         StringSecurityDescriptor,
         &v10,
         0,
         0);
  if ( v9 || v10 != 15 || !StringSecurityDescriptor[0] )
    goto LABEL_47;
  v12 = StringSecurityDescriptor[0];
  if ( !*(_QWORD *)StringSecurityDescriptor[0] )
    goto LABEL_46;
  v9 = (*(unsigned int (__fastcall **)(LPCWSTR, const wchar_t *, LPCWSTR *, int *, _QWORD, _QWORD))(*(_QWORD *)StringSecurityDescriptor[0]
                                                                                                  + 88LL))(
         StringSecurityDescriptor[0],
         L"ShareType",
         StringSecurityDescriptor,
         &v10,
         0,
         0);
  if ( v9 || v10 != 5 || LODWORD(StringSecurityDescriptor[0]) )
    goto LABEL_47;
  if ( !v12 || !*(_QWORD *)v12 )
  {
LABEL_46:
    v9 = MI_RESULT_INVALID_PARAMETER;
LABEL_47:
    v6 = -2147418113;
    goto LABEL_52;
  }
  v9 = (*(unsigned int (__fastcall **)(LPCWSTR, const wchar_t *, LPCWSTR *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 88LL))(
         v12,
         L"Special",
         StringSecurityDescriptor,
         &v10,
         0,
         0);
  if ( v9 || v10 || LOBYTE(StringSecurityDescriptor[0]) )
    goto LABEL_47;
  if ( !v12 || !*(_QWORD *)v12 )
    goto LABEL_51;
  v9 = (*(unsigned int (__fastcall **)(LPCWSTR, const wchar_t *, LPCWSTR *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 88LL))(
         v12,
         L"SecurityDescriptor",
         StringSecurityDescriptor,
         &v10,
         0,
         0);
  if ( v9 == MI_RESULT_OK
    && !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor[0], 1u, a3, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_52:
  if ( v11 && *(_QWORD *)v11 )
    (*(void (**)(void))(*(_QWORD *)v11 + 16LL))();
  if ( *(_QWORD *)&v15[16] )
    (**(void (__fastcall ***)(_BYTE *))&v15[16])(v15);
  if ( *(_QWORD *)&v14[16] )
    (**(void (__fastcall ***)(_BYTE *))&v14[16])(v14);
  if ( *(_QWORD *)&v16[16] )
    (**(void (__fastcall ***)(_BYTE *, _QWORD, _QWORD))&v16[16])(v16, 0, 0);
  if ( application.ft )
    ((void (__fastcall *)(MI_Application *))application.ft->Close)(&application);
  if ( v9 )
    return (unsigned int)-2147418113;
  return v6;
}

```

## disassembly

```asm
0x18000b144  push    rbp
0x18000b146  push    rbx
0x18000b147  push    rsi
0x18000b148  push    rdi
0x18000b149  push    r12
0x18000b14b  push    r14
0x18000b14d  push    r15
0x18000b14f  lea     rbp, [rsp-10h]
0x18000b154  sub     rsp, 110h
0x18000b15b  mov     rax, cs:__security_cookie
0x18000b162  xor     rax, rsp
0x18000b165  mov     [rbp+40h+var_38], rax
0x18000b169  xor     r15d, r15d
0x18000b16c  mov     [rsp+140h+var_DC], 0FFFFFFFFh
0x18000b174  xorps   xmm0, xmm0
0x18000b177  mov     [rsp+140h+var_E0], r15d
0x18000b17c  xorps   xmm1, xmm1
0x18000b17f  mov     [rsp+140h+application.reserved1], r15
0x18000b184  mov     r14, r8
0x18000b187  mov     qword ptr [rbp+40h+var_B0], r15
0x18000b18b  mov     rsi, rdx
0x18000b18e  mov     qword ptr [rbp+40h+var_80], r15
0x18000b192  mov     rdi, rcx
0x18000b195  mov     qword ptr [rbp+40h+var_98], r15
0x18000b199  xor     eax, eax
0x18000b19b  mov     [rsp+140h+var_D8], r15
0x18000b1a0  xor     r8d, r8d; extendedError
0x18000b1a3  mov     [rsp+140h+var_D0], r15
0x18000b1a8  lea     rdx, applicationID; "MICROSOFT/WINDOWS/SMB"
0x18000b1af  mov     [rbp+40h+var_68], r15
0x18000b1b3  xor     ecx, ecx; flags
0x18000b1b5  mov     [rbp+40h+var_40], rax
0x18000b1b9  lea     r9, [rsp+140h+application]; application
0x18000b1be  mov     ebx, r15d
0x18000b1c1  movdqu  xmmword ptr [rbp+40h+application.reserved2], xmm0
0x18000b1c6  movdqu  [rbp+40h+var_B0+8], xmm1
0x18000b1cb  movdqu  [rbp+40h+var_80+8], xmm0
0x18000b1d0  movdqu  [rbp+40h+var_98+8], xmm1
0x18000b1d5  movups  xmmword ptr [rbp+40h+StringSecurityDescriptor], xmm0
0x18000b1d9  movups  [rbp+40h+var_50], xmm0
0x18000b1dd  call    cs:__imp_MI_Application_InitializeV1
0x18000b1e3  mov     [rsp+140h+var_E0], eax
0x18000b1e7  mov     r12d, 8000FFFFh
0x18000b1ed  test    eax, eax
0x18000b1ef  jnz     loc_18000B60F
0x18000b1f5  mov     rax, [rbp+40h+application.ft]
0x18000b1f9  test    rax, rax
0x18000b1fc  jz      loc_18000B5FA
0x18000b202  mov     rax, [rax+20h]
0x18000b206  lea     rdx, [rbp+40h+var_B0]
0x18000b20a  lea     rcx, [rsp+140h+application]
0x18000b20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b214  mov     [rsp+140h+var_E0], eax
0x18000b218  test    eax, eax
0x18000b21a  jnz     loc_18000B60F
0x18000b220  mov     rax, [rbp+40h+var_A0]
0x18000b224  test    rax, rax
0x18000b227  jz      loc_18000B607
0x18000b22d  mov     rax, [rax+10h]
0x18000b231  lea     r8d, [r15+2]
0x18000b235  xor     r9d, r9d
0x18000b238  lea     rdx, aMiDestinationo; "__MI_DESTINATIONOPTIONS_IMPERSONATION_T"...
0x18000b23f  lea     rcx, [rbp+40h+var_B0]
0x18000b243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b248  mov     [rsp+140h+var_E0], eax
0x18000b24c  test    eax, eax
0x18000b24e  jnz     loc_18000B60F
0x18000b254  mov     rax, [rbp+40h+application.ft]
0x18000b258  test    rax, rax
0x18000b25b  jz      loc_18000B5EB
0x18000b261  mov     rax, [rax+8]
0x18000b265  lea     rcx, [rbp+40h+var_80]
0x18000b269  mov     [rsp+140h+var_110], rcx
0x18000b26e  lea     r9, [rbp+40h+var_B0]
0x18000b272  mov     [rsp+140h+var_118], r15
0x18000b277  lea     rcx, [rsp+140h+application]
0x18000b27c  mov     r8, rdi
0x18000b27f  mov     [rsp+140h+var_120], r15
0x18000b284  lea     rdx, aWinrm; "WinRM"
0x18000b28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b290  mov     [rsp+140h+var_E0], eax
0x18000b294  test    eax, eax
0x18000b296  jnz     loc_18000B60F
0x18000b29c  mov     rax, [rbp+40h+application.ft]
0x18000b2a0  test    rax, rax
0x18000b2a3  jz      loc_18000B5E4
0x18000b2a9  mov     rax, [rax+18h]
0x18000b2ad  lea     r9, [rsp+140h+var_D8]
0x18000b2b2  xor     r8d, r8d
0x18000b2b5  lea     rdx, aParameters; "Parameters"
0x18000b2bc  lea     rcx, [rsp+140h+application]
0x18000b2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c6  mov     [rsp+140h+var_E0], eax
0x18000b2ca  test    eax, eax
0x18000b2cc  jnz     loc_18000B60F
0x18000b2d2  mov     rcx, [rsp+140h+var_D8]
0x18000b2d7  mov     [rbp+40h+StringSecurityDescriptor], rdi
0x18000b2db  test    rcx, rcx
0x18000b2de  jz      loc_18000B607
0x18000b2e4  mov     rax, [rcx]
0x18000b2e7  test    rax, rax
0x18000b2ea  jz      loc_18000B607
0x18000b2f0  mov     rax, [rax+40h]
0x18000b2f4  lea     edi, [r15+0Dh]
0x18000b2f8  mov     r9d, edi
0x18000b2fb  mov     dword ptr [rsp+140h+var_120], r15d
0x18000b300  lea     r8, [rbp+40h+StringSecurityDescriptor]
0x18000b304  lea     rdx, aScopename; "ScopeName"
0x18000b30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b310  mov     [rsp+140h+var_E0], eax
0x18000b314  test    eax, eax
0x18000b316  jnz     loc_18000B60F
0x18000b31c  mov     rcx, [rsp+140h+var_D8]
0x18000b321  mov     [rbp+40h+StringSecurityDescriptor], rsi
0x18000b325  test    rcx, rcx
0x18000b328  jz      loc_18000B607
0x18000b32e  mov     rax, [rcx]
0x18000b331  test    rax, rax
0x18000b334  jz      loc_18000B607
0x18000b33a  mov     rax, [rax+40h]
0x18000b33e  lea     r8, [rbp+40h+StringSecurityDescriptor]
0x18000b342  mov     r9d, edi
0x18000b345  mov     dword ptr [rsp+140h+var_120], r15d
0x18000b34a  lea     rdx, aSharename; "ShareName"
0x18000b351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b356  mov     [rsp+140h+var_E0], eax
0x18000b35a  test    eax, eax
0x18000b35c  jnz     loc_18000B60F
0x18000b362  mov     rcx, [rsp+140h+var_D8]
0x18000b367  mov     byte ptr [rbp+40h+StringSecurityDescriptor], 1
0x18000b36b  test    rcx, rcx
0x18000b36e  jz      loc_18000B607
0x18000b374  mov     rax, [rcx]
0x18000b377  test    rax, rax
0x18000b37a  jz      loc_18000B607
0x18000b380  mov     rax, [rax+40h]
0x18000b384  lea     r8, [rbp+40h+StringSecurityDescriptor]
0x18000b388  xor     r9d, r9d
0x18000b38b  mov     dword ptr [rsp+140h+var_120], r15d
0x18000b390  lea     rdx, aGetaclnonadmin; "GetAclNonAdmin"
0x18000b397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b39c  mov     [rsp+140h+var_E0], eax
0x18000b3a0  test    eax, eax
0x18000b3a2  jnz     loc_18000B60F
0x18000b3a8  mov     rax, [rbp+40h+var_70]
0x18000b3ac  test    rax, rax
0x18000b3af  jz      short loc_18000B401
0x18000b3b1  mov     rax, [rax+30h]
0x18000b3b5  lea     rcx, [rbp+40h+var_98]
0x18000b3b9  mov     [rsp+140h+var_F8], rcx
0x18000b3be  lea     r9, aRootMicrosoftW; "ROOT\\MICROSOFT\\WINDOWS\\SMB"
0x18000b3c5  mov     rcx, [rsp+140h+var_D8]
0x18000b3ca  xor     r8d, r8d
0x18000b3cd  mov     [rsp+140h+var_100], r15
0x18000b3d2  xor     edx, edx
0x18000b3d4  mov     [rsp+140h+var_108], rcx
0x18000b3d9  lea     rcx, aGetshare; "GetShare"
0x18000b3e0  mov     [rsp+140h+var_110], r15
0x18000b3e5  mov     [rsp+140h+var_118], rcx
0x18000b3ea  lea     rcx, aMsftSmbshare; "MSFT_SmbShare"
0x18000b3f1  mov     [rsp+140h+var_120], rcx
0x18000b3f6  lea     rcx, [rbp+40h+var_80]
0x18000b3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ff  jmp     short loc_18000B40E
0x18000b401  xorps   xmm0, xmm0
0x18000b404  xor     eax, eax
0x18000b406  movups  [rbp+40h+var_98], xmm0
0x18000b40a  mov     [rbp+40h+var_88], rax
0x18000b40e  mov     rax, [rbp+40h+var_88]
0x18000b412  test    rax, rax
0x18000b415  jz      short loc_18000B441
0x18000b417  mov     rax, [rax+18h]
0x18000b41b  lea     rcx, [rbp+40h+var_68]
0x18000b41f  mov     [rsp+140h+var_118], r15
0x18000b424  lea     r9, [rsp+140h+var_E0]
0x18000b429  mov     [rsp+140h+var_120], rcx
0x18000b42e  lea     rdx, [rsp+140h+var_D0]
0x18000b433  lea     rcx, [rbp+40h+var_98]
0x18000b437  xor     r8d, r8d
0x18000b43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b43f  jmp     short loc_18000B449
0x18000b441  mov     [rsp+140h+var_E0], 4
0x18000b449  cmp     [rsp+140h+var_E0], r15d
0x18000b44e  jnz     loc_18000B60F
0x18000b454  mov     rcx, [rsp+140h+var_D0]
0x18000b459  test    rcx, rcx
0x18000b45c  jz      loc_18000B5D7
0x18000b462  mov     rax, [rcx]
0x18000b465  test    rax, rax
0x18000b468  jz      loc_18000B5D7
0x18000b46e  mov     rax, [rax+58h]
0x18000b472  lea     r9, [rsp+140h+var_DC]
0x18000b477  mov     [rsp+140h+var_118], r15
0x18000b47c  lea     r8, [rbp+40h+StringSecurityDescriptor]
0x18000b480  lea     rdx, aOutput; "Output"
0x18000b487  mov     [rsp+140h+var_120], r15
0x18000b48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b491  mov     [rsp+140h+var_E0], eax
0x18000b495  test    eax, eax
0x18000b497  jnz     loc_18000B5DF
0x18000b49d  cmp     [rsp+140h+var_DC], 0Fh
0x18000b4a2  jnz     loc_18000B5DF
0x18000b4a8  mov     rcx, [rbp+40h+StringSecurityDescriptor]
0x18000b4ac  test    rcx, rcx
0x18000b4af  jz      loc_18000B5DF
0x18000b4b5  mov     [rsp+140h+var_D0], rcx
0x18000b4ba  mov     rax, [rcx]
0x18000b4bd  test    rax, rax
0x18000b4c0  jz      loc_18000B5D7
0x18000b4c6  mov     rax, [rax+58h]
0x18000b4ca  lea     r9, [rsp+140h+var_DC]
0x18000b4cf  mov     [rsp+140h+var_118], r15
0x18000b4d4  lea     r8, [rbp+40h+StringSecurityDescriptor]
0x18000b4d8  lea     rdx, aSharetype; "ShareType"
0x18000b4df  mov     [rsp+140h+var_120], r15
0x18000b4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4e9  mov     [rsp+140h+var_E0], eax
0x18000b4ed  test    eax, eax
0x18000b4ef  jnz     loc_18000B5DF
0x18000b4f5  cmp     [rsp+140h+var_DC], 5
0x18000b4fa  jnz     loc_18000B5DF
0x18000b500  cmp     dword ptr [rbp+40h+StringSecurityDescriptor], r15d
0x18000b504  jnz     loc_18000B5DF
0x18000b50a  mov     rcx, [rsp+140h+var_D0]
0x18000b50f  test    rcx, rcx
0x18000b512  jz      loc_18000B5D7
0x18000b518  mov     rax, [rcx]
0x18000b51b  test    rax, rax
0x18000b51e  jz      loc_18000B5D7
0x18000b524  mov     rax, [rax+58h]
0x18000b528  lea     r9, [rsp+140h+var_DC]
0x18000b52d  mov     [rsp+140h+var_118], r15
0x18000b532  lea     r8, [rbp+40h+StringSecurityDescriptor]
0x18000b536  lea     rdx, aSpecial; "Special"
0x18000b53d  mov     [rsp+140h+var_120], r15
0x18000b542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b547  mov     [rsp+140h+var_E0], eax
0x18000b54b  test    eax, eax
0x18000b54d  jnz     loc_18000B5DF
0x18000b553  cmp     [rsp+140h+var_DC], r15d
0x18000b558  jnz     loc_18000B5DF
0x18000b55e  cmp     byte ptr [rbp+40h+StringSecurityDescriptor], r15b
0x18000b562  jnz     short loc_18000B5DF
0x18000b564  mov     rcx, [rsp+140h+var_D0]
0x18000b569  test    rcx, rcx
0x18000b56c  jz      loc_18000B607
0x18000b572  mov     rax, [rcx]
0x18000b575  test    rax, rax
0x18000b578  jz      loc_18000B607
0x18000b57e  mov     rax, [rax+58h]
0x18000b582  lea     r9, [rsp+140h+var_DC]
0x18000b587  mov     [rsp+140h+var_118], r15
0x18000b58c  lea     r8, [rbp+40h+StringSecurityDescriptor]
0x18000b590  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x18000b597  mov     [rsp+140h+var_120], r15
0x18000b59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a1  mov     [rsp+140h+var_E0], eax
0x18000b5a5  test    eax, eax
0x18000b5a7  jnz     short loc_18000B60F
0x18000b5a9  mov     rcx, [rbp+40h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000b5ad  lea     edx, [rax+1]; StringSDRevision
0x18000b5b0  xor     r9d, r9d; SecurityDescriptorSize
0x18000b5b3  mov     r8, r14; SecurityDescriptor
0x18000b5b6  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000b5bc  test    eax, eax
0x18000b5be  jnz     short loc_18000B60F
0x18000b5c0  call    cs:__imp_GetLastError
0x18000b5c6  mov     ebx, eax
0x18000b5c8  test    eax, eax
0x18000b5ca  jle     short loc_18000B60F
0x18000b5cc  movzx   ebx, ax
0x18000b5cf  or      ebx, 80070000h
0x18000b5d5  jmp     short loc_18000B60F
0x18000b5d7  mov     [rsp+140h+var_E0], 4
0x18000b5df  mov     ebx, r12d
0x18000b5e2  jmp     short loc_18000B60F
0x18000b5e4  mov     [rsp+140h+var_D8], r15
0x18000b5e9  jmp     short loc_18000B607
0x18000b5eb  xorps   xmm0, xmm0
0x18000b5ee  xor     eax, eax
0x18000b5f0  movups  [rbp+40h+var_80], xmm0
0x18000b5f4  mov     [rbp+40h+var_70], rax
0x18000b5f8  jmp     short loc_18000B607
0x18000b5fa  xorps   xmm0, xmm0
0x18000b5fd  xor     eax, eax
0x18000b5ff  movups  [rbp+40h+var_B0], xmm0
0x18000b603  mov     [rbp+40h+var_A0], rax
0x18000b607  mov     [rsp+140h+var_E0], 4
0x18000b60f  mov     rcx, [rsp+140h+var_D8]
0x18000b614  test    rcx, rcx
0x18000b617  jz      short loc_18000B62A
0x18000b619  mov     rax, [rcx]
0x18000b61c  test    rax, rax
0x18000b61f  jz      short loc_18000B62A
0x18000b621  mov     rax, [rax+10h]
0x18000b625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b62a  mov     rax, [rbp+40h+var_88]
0x18000b62e  test    rax, rax
0x18000b631  jz      short loc_18000B63F
0x18000b633  mov     rax, [rax]
  ... truncated ...
```
