# WinStationGetUserCredentials

- ea: `0x180020c00`
- end: `0x180020f48`
- name: `WinStationGetUserCredentials`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180020c00`
- `0x180029988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c4c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020ea8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020ea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f22`
- `RPCRT4!NdrClientCall3` at `0x180020c86`
- `RPCRT4!NdrClientCall3` at `0x180020c86`

## string_xrefs

- `0x180020c3d`: `Failed to open binding`
- `0x180020e51`: `CSecurityUtils::DecryptPasswordInCredInfo`
- `0x180020dfe`: `CSecurityUtils::DecryptPINInCredInfo`
- `0x180020d94`: `CSecurityUtils::DecryptCertInCredInfo`

## pseudocode

```c
__int64 __fastcall WinStationGetUserCredentials(HLOCAL *a1)
{
  DWORD LastError; // eax
  unsigned int v3; // esi
  __int64 v4; // rax
  CLIENT_CALL_RETURN v5; // rbx
  unsigned __int64 v6; // r8
  int *v7; // rdx
  int v8; // ecx
  unsigned __int16 *v9; // r9
  int v10; // eax
  int v11; // ebx
  const char *v12; // r9
  _WORD *v13; // r9
  __int64 v14; // r10
  __int64 v15; // r11
  _WORD *v16; // r9
  __int64 v17; // r10
  __int64 v18; // r11
  HLOCAL v19; // rax
  HLOCAL v20; // rcx
  unsigned __int16 v22[24]; // [rsp+38h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+80h] [rbp+18h]

  hMem = 0;
  *a1 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v22, 0, 1);
  if ( !CSmartPublicBinding::operator void *(v22) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
LABEL_3:
    v3 = LastError;
    goto LABEL_43;
  }
  v4 = CSmartPublicBinding::operator void *(v22);
  v24.Simple = 0;
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032170, 1u, 0, v4, &hMem).Pointer;
  v24.Pointer = v5.Pointer;
  v3 = ConvertHRESULT2WIN32(v5.Simple);
  if ( SLODWORD(v5.Simple) < 0 )
  {
    _DbgPrintMessage(8, "RpcGetUserCredentials failed: 0x%x", LODWORD(v5.Pointer));
    goto LABEL_43;
  }
  if ( (*((_BYTE *)hMem + 16) & 1) == 0 )
    goto LABEL_40;
  v6 = *((unsigned int *)hMem + 1);
  if ( (unsigned int)v6 < 0x38 || (v7 = (int *)*((_QWORD *)hMem + 1)) == 0 )
  {
    _DbgPrintMessage(
      8,
      "RpcGetUserCredentials returned an invalid (not a KERB_INTERACTIVE_LOGON or Information is NULL) credential.");
    goto LABEL_19;
  }
  v8 = *v7;
  if ( *v7 != 2 && v8 != 7 )
  {
    if ( ((v8 - 13) & 0xFFFFFFFD) == 0 )
    {
      if ( (unsigned int)v6 >= 0x50 )
      {
        v13 = v7 + 10;
        v14 = *((_QWORD *)v7 + 6);
        if ( v14 )
        {
          if ( *v13 )
          {
            v15 = *((unsigned __int16 *)v7 + 21);
            if ( v6 >= v14 + v15 && *v13 <= (unsigned __int16)v15 )
            {
              v10 = CSecurityUtils::UnprotectString(
                      (unsigned __int16 *)((char *)v7 + v14),
                      (unsigned __int16 *)v7 + 20,
                      v15);
              v11 = v10;
              if ( v10 >= 0 )
                goto LABEL_37;
              v12 = "CSecurityUtils::DecryptPINInCredInfo";
              goto LABEL_35;
            }
          }
        }
      }
LABEL_28:
      v11 = -2147024883;
      goto LABEL_37;
    }
    if ( v8 == 513 )
    {
      if ( v7[3] )
      {
        v9 = (unsigned __int16 *)(v7 + 4);
        if ( *((_WORD *)v7 + 8) )
        {
          if ( v6 >= (unsigned __int64)*v9 + 48 )
          {
            v10 = CSecurityUtils::UnprotectString(
                    (unsigned __int16 *)((char *)v7 + (unsigned int)v7[3]),
                    (unsigned __int16 *)v7 + 8,
                    *v9);
            v11 = v10;
            if ( v10 >= 0 )
              goto LABEL_37;
            v12 = "CSecurityUtils::DecryptCertInCredInfo";
LABEL_35:
            _DbgPrintMessage(8, "UnprotectString failed: 0x%x in %s", v10, v12);
            goto LABEL_37;
          }
        }
      }
      goto LABEL_28;
    }
    _DbgPrintMessage(
      8,
      "RpcGetUserCredentials returned an invalid (does not look like a valid KERB_INTERACTIVE_LOGON or SEC_WINNT_AUTH_IDE"
      "NTITY_EX2) credential.");
LABEL_19:
    v3 = 13;
    goto LABEL_43;
  }
  if ( (unsigned int)v6 < 0x40 )
    goto LABEL_28;
  v16 = v7 + 10;
  v17 = *((_QWORD *)v7 + 6);
  if ( v17 && *v16 )
  {
    v18 = *((unsigned __int16 *)v7 + 21);
    if ( v6 >= v17 + v18 && *v16 <= (unsigned __int16)v18 )
    {
      v10 = CSecurityUtils::UnprotectString((unsigned __int16 *)((char *)v7 + v17), (unsigned __int16 *)v7 + 20, v18);
      v11 = v10;
      if ( v10 >= 0 )
        goto LABEL_37;
      v12 = "CSecurityUtils::DecryptPasswordInCredInfo";
      goto LABEL_35;
    }
    goto LABEL_28;
  }
  v11 = 0;
LABEL_37:
  if ( v11 < 0 )
  {
    _DbgPrintMessage(8, "Decrypting password or PIN failed: 0x%x", v11);
    LastError = ConvertHRESULT2WIN32(v11);
    goto LABEL_3;
  }
LABEL_40:
  v19 = LocalAlloc(0x40u, 0x18u);
  *a1 = v19;
  if ( v19 )
  {
    *((_DWORD *)v19 + 1) = *(_DWORD *)hMem;
    *(_DWORD *)*a1 = 0;
    *((_DWORD *)*a1 + 2) = *((_DWORD *)hMem + 1);
    *((_QWORD *)*a1 + 2) = *((_QWORD *)hMem + 1);
  }
  else
  {
    v3 = 8;
  }
LABEL_43:
  v20 = hMem;
  if ( hMem )
  {
    if ( v3 && *((_QWORD *)hMem + 1) )
    {
      LocalFree(*((HLOCAL *)hMem + 1));
      v20 = hMem;
    }
    LocalFree(v20);
  }
  if ( v3 && *a1 )
  {
    LocalFree(*a1);
    *a1 = 0;
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
  return v3;
}

```

## disassembly

```asm
0x180020c00  mov     rax, rsp
0x180020c03  mov     [rax+20h], rbx
0x180020c07  mov     [rax+8], rcx
0x180020c0b  push    rsi
0x180020c0c  push    rdi
0x180020c0d  push    r15
0x180020c0f  sub     rsp, 50h
0x180020c13  mov     r15, rcx
0x180020c16  xor     edi, edi
0x180020c18  mov     [rax+10h], rdi
0x180020c1c  mov     [rcx], rdi
0x180020c1f  xor     edx, edx; void *
0x180020c21  lea     r8d, [rdi+1]; int
0x180020c25  lea     rcx, [rax-30h]; this
0x180020c29  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180020c2e  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x180020c33  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180020c38  test    rax, rax
0x180020c3b  jnz     short loc_180020C59
0x180020c3d  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180020c44  lea     ecx, [rdi+8]; int
0x180020c47  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020c4c  call    cs:__imp_GetLastError
0x180020c52  mov     esi, eax
0x180020c54  jmp     loc_180020EEB
0x180020c59  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x180020c5e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180020c63  mov     [rsp+68h+arg_10], rdi
0x180020c6b  lea     rcx, [rsp+68h+hMem]
0x180020c70  mov     [rsp+68h+var_48], rcx
0x180020c75  mov     r9, rax
0x180020c78  xor     r8d, r8d; pReturnValue
0x180020c7b  lea     edx, [r8+1]; nProcNum
0x180020c7f  lea     rcx, stru_180032170; pProxyInfo
0x180020c86  call    cs:__imp_NdrClientCall3
0x180020c8c  mov     rbx, rax
0x180020c8f  mov     [rsp+68h+arg_10], rax
0x180020c97  mov     [rsp+68h+var_34], ebx
0x180020c9b  mov     ecx, eax; int
0x180020c9d  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180020ca2  mov     esi, eax
0x180020ca4  mov     [rsp+68h+var_38], eax
0x180020ca8  test    ebx, ebx
0x180020caa  jns     short loc_180020CC0
0x180020cac  mov     r8d, ebx
0x180020caf  lea     rdx, aRpcgetusercred_0; "RpcGetUserCredentials failed: 0x%x"
0x180020cb6  mov     ecx, 8; int
0x180020cbb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020cc0  jmp     short loc_180020CF8
0x180020cc2  mov     esi, eax
0x180020cc4  mov     [rsp+68h+var_38], eax
0x180020cc8  test    eax, eax
0x180020cca  jg      short loc_180020CD0
0x180020ccc  mov     ebx, eax
0x180020cce  jmp     short loc_180020CD9
0x180020cd0  movzx   ebx, ax
0x180020cd3  or      ebx, 80070000h
0x180020cd9  mov     [rsp+68h+var_34], ebx
0x180020cdd  mov     r8d, eax
0x180020ce0  lea     rdx, aRpcgetusercred_1; "RpcGetUserCredentials threw an exceptio"...
0x180020ce7  mov     ecx, 8; int
0x180020cec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020cf1  xor     edi, edi
0x180020cf3  mov     r15, [rsp+68h+arg_0]
0x180020cf8  test    ebx, ebx
0x180020cfa  js      loc_180020EEB
0x180020d00  mov     rdx, [rsp+68h+hMem]
0x180020d05  test    byte ptr [rdx+10h], 1
0x180020d09  jz      loc_180020EA0
0x180020d0f  mov     r8d, [rdx+4]
0x180020d13  cmp     r8d, 38h ; '8'
0x180020d17  jb      loc_180020E94
0x180020d1d  mov     rdx, [rdx+8]
0x180020d21  test    rdx, rdx
0x180020d24  jz      loc_180020E94
0x180020d2a  mov     ecx, [rdx]
0x180020d2c  cmp     ecx, 2
0x180020d2f  jz      loc_180020E07
0x180020d35  cmp     ecx, 7
0x180020d38  jz      loc_180020E07
0x180020d3e  lea     eax, [rcx-0Dh]
0x180020d41  test    eax, 0FFFFFFFDh
0x180020d46  jz      short loc_180020DBB
0x180020d48  cmp     ecx, 201h
0x180020d4e  jnz     short loc_180020DA0
0x180020d50  cmp     [rdx+0Ch], edi
0x180020d53  jz      loc_180020E0D
0x180020d59  lea     r9, [rdx+10h]
0x180020d5d  cmp     [r9], di
0x180020d61  jz      loc_180020E0D
0x180020d67  movzx   ecx, word ptr [r9]
0x180020d6b  add     rcx, 30h ; '0'
0x180020d6f  cmp     r8, rcx
0x180020d72  jb      loc_180020E0D
0x180020d78  mov     ecx, [rdx+0Ch]
0x180020d7b  add     rcx, rdx; unsigned __int16 *
0x180020d7e  movzx   r8d, word ptr [r9]; unsigned __int16
0x180020d82  mov     rdx, r9; unsigned __int16 *
0x180020d85  call    ?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z; CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)
0x180020d8a  mov     ebx, eax
0x180020d8c  test    eax, eax
0x180020d8e  jns     loc_180020E70
0x180020d94  lea     r9, aCsecurityutils_0; "CSecurityUtils::DecryptCertInCredInfo"
0x180020d9b  jmp     loc_180020E58
0x180020da0  lea     rdx, aRpcgetusercred; "RpcGetUserCredentials returned an inval"...
0x180020da7  mov     ecx, 8; int
0x180020dac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020db1  mov     esi, 0Dh
0x180020db6  jmp     loc_180020EEB
0x180020dbb  cmp     r8d, 50h ; 'P'
0x180020dbf  jb      short loc_180020E0D
0x180020dc1  lea     r9, [rdx+28h]
0x180020dc5  mov     r10, [r9+8]
0x180020dc9  test    r10, r10
0x180020dcc  jz      short loc_180020E0D
0x180020dce  cmp     [r9], di
0x180020dd2  jz      short loc_180020E0D
0x180020dd4  movzx   r11d, word ptr [rdx+2Ah]
0x180020dd9  lea     rcx, [r10+r11]
0x180020ddd  cmp     r8, rcx
0x180020de0  jb      short loc_180020E0D
0x180020de2  cmp     [r9], r11w
0x180020de6  ja      short loc_180020E0D
0x180020de8  lea     rcx, [r10+rdx]; unsigned __int16 *
0x180020dec  movzx   r8d, r11w; unsigned __int16
0x180020df0  mov     rdx, r9; unsigned __int16 *
0x180020df3  call    ?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z; CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)
0x180020df8  mov     ebx, eax
0x180020dfa  test    eax, eax
0x180020dfc  jns     short loc_180020E70
0x180020dfe  lea     r9, aCsecurityutils_1; "CSecurityUtils::DecryptPINInCredInfo"
0x180020e05  jmp     short loc_180020E58
0x180020e07  cmp     r8d, 40h ; '@'
0x180020e0b  jnb     short loc_180020E14
0x180020e0d  mov     ebx, 8007000Dh
0x180020e12  jmp     short loc_180020E70
0x180020e14  lea     r9, [rdx+28h]
0x180020e18  mov     r10, [r9+8]
0x180020e1c  test    r10, r10
0x180020e1f  jz      short loc_180020E6E
0x180020e21  cmp     [r9], di
0x180020e25  jz      short loc_180020E6E
0x180020e27  movzx   r11d, word ptr [rdx+2Ah]
0x180020e2c  lea     rcx, [r10+r11]
0x180020e30  cmp     r8, rcx
0x180020e33  jb      short loc_180020E0D
0x180020e35  cmp     [r9], r11w
0x180020e39  ja      short loc_180020E0D
0x180020e3b  lea     rcx, [r10+rdx]; unsigned __int16 *
0x180020e3f  movzx   r8d, r11w; unsigned __int16
0x180020e43  mov     rdx, r9; unsigned __int16 *
0x180020e46  call    ?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z; CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)
0x180020e4b  mov     ebx, eax
0x180020e4d  test    eax, eax
0x180020e4f  jns     short loc_180020E70
0x180020e51  lea     r9, aCsecurityutils; "CSecurityUtils::DecryptPasswordInCredIn"...
0x180020e58  mov     r8d, eax
0x180020e5b  lea     rdx, aUnprotectstrin; "UnprotectString failed: 0x%x in %s"
0x180020e62  mov     ecx, 8; int
0x180020e67  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020e6c  jmp     short loc_180020E70
0x180020e6e  mov     ebx, edi
0x180020e70  test    ebx, ebx
0x180020e72  jns     short loc_180020EA0
0x180020e74  mov     r8d, ebx
0x180020e77  lea     rdx, aDecryptingPass; "Decrypting password or PIN failed: 0x%x"
0x180020e7e  mov     ecx, 8; int
0x180020e83  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020e88  mov     ecx, ebx; int
0x180020e8a  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180020e8f  jmp     loc_180020C52
0x180020e94  lea     rdx, aRpcgetusercred_2; "RpcGetUserCredentials returned an inval"...
0x180020e9b  jmp     loc_180020DA7
0x180020ea0  mov     edx, 18h; uBytes
0x180020ea5  lea     ecx, [rdx+28h]; uFlags
0x180020ea8  call    cs:__imp_LocalAlloc
0x180020eae  mov     rdx, rax
0x180020eb1  mov     [r15], rax
0x180020eb4  test    rax, rax
0x180020eb7  jnz     short loc_180020EBE
0x180020eb9  lea     esi, [rax+8]
0x180020ebc  jmp     short loc_180020EEB
0x180020ebe  mov     rax, [rsp+68h+hMem]
0x180020ec3  mov     ecx, [rax]
0x180020ec5  mov     [rdx+4], ecx
0x180020ec8  mov     rax, [r15]
0x180020ecb  mov     [rax], edi
0x180020ecd  mov     rdx, [r15]
0x180020ed0  mov     rax, [rsp+68h+hMem]
0x180020ed5  mov     ecx, [rax+4]
0x180020ed8  mov     [rdx+8], ecx
0x180020edb  mov     rdx, [r15]
0x180020ede  mov     rax, [rsp+68h+hMem]
0x180020ee3  mov     rcx, [rax+8]
0x180020ee7  mov     [rdx+10h], rcx
0x180020eeb  mov     rcx, [rsp+68h+hMem]
0x180020ef0  test    rcx, rcx
0x180020ef3  jz      short loc_180020F16
0x180020ef5  test    esi, esi
0x180020ef7  jz      short loc_180020F10
0x180020ef9  mov     rax, [rcx+8]
0x180020efd  test    rax, rax
0x180020f00  jz      short loc_180020F10
0x180020f02  mov     rcx, rax; hMem
0x180020f05  call    cs:__imp_LocalFree
0x180020f0b  mov     rcx, [rsp+68h+hMem]; hMem
0x180020f10  call    cs:__imp_LocalFree
0x180020f16  test    esi, esi
0x180020f18  jz      short loc_180020F2B
0x180020f1a  cmp     [r15], rdi
0x180020f1d  jz      short loc_180020F2B
0x180020f1f  mov     rcx, [r15]; hMem
0x180020f22  call    cs:__imp_LocalFree
0x180020f28  mov     [r15], rdi
0x180020f2b  lea     rcx, [rsp+68h+var_30]; this
0x180020f30  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180020f35  mov     eax, esi
0x180020f37  mov     rbx, [rsp+68h+arg_18]
0x180020f3f  add     rsp, 50h
0x180020f43  pop     r15
0x180020f45  pop     rdi
0x180020f46  pop     rsi
0x180020f47  retn
0x180030851  push    rbp
0x180030853  sub     rsp, 30h
0x180030857  mov     rbp, rdx
0x18003085a  mov     rcx, [rcx]
0x18003085d  mov     ecx, [rcx]; ExceptionCode
0x18003085f  call    cs:__imp_I_RpcExceptionFilter
0x180030865  nop
0x180030866  add     rsp, 30h
0x18003086a  pop     rbp
0x18003086b  retn
```
