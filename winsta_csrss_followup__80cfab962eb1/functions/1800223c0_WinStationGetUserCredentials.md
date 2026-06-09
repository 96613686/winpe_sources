# WinStationGetUserCredentials

- ea: `0x1800223c0`
- end: `0x18002272d`
- name: `WinStationGetUserCredentials`
- size: `877`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x1800223c0`
- `0x18002b5cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002240c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002240c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022674`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800226e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022700`
- `RPCRT4!NdrClientCall3` at `0x18002244c`
- `RPCRT4!NdrClientCall3` at `0x18002244c`

## string_xrefs

- `0x1800223fd`: `Failed to open binding`
- `0x18002261d`: `CSecurityUtils::DecryptPasswordInCredInfo`
- `0x1800225ca`: `CSecurityUtils::DecryptPINInCredInfo`
- `0x180022560`: `CSecurityUtils::DecryptCertInCredInfo`

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
  v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 1u, 0, v4, &hMem).Pointer;
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
0x1800223c0  mov     rax, rsp
0x1800223c3  mov     [rax+20h], rbx
0x1800223c7  mov     [rax+8], rcx
0x1800223cb  push    rsi
0x1800223cc  push    rdi
0x1800223cd  push    r15
0x1800223cf  sub     rsp, 50h
0x1800223d3  mov     r15, rcx
0x1800223d6  xor     edi, edi
0x1800223d8  mov     [rax+10h], rdi
0x1800223dc  mov     [rcx], rdi
0x1800223df  xor     edx, edx; void *
0x1800223e1  lea     r8d, [rdi+1]; int
0x1800223e5  lea     rcx, [rax-30h]; this
0x1800223e9  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800223ee  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x1800223f3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800223f8  test    rax, rax
0x1800223fb  jnz     short loc_18002241F
0x1800223fd  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180022404  lea     ecx, [rdi+8]; int
0x180022407  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002240c  call    cs:__imp_GetLastError
0x180022413  nop     dword ptr [rax+rax+00h]
0x180022418  mov     esi, eax
0x18002241a  jmp     loc_1800226BD
0x18002241f  lea     rcx, [rsp+68h+var_30]; unsigned __int16 *
0x180022424  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022429  mov     [rsp+68h+arg_10], rdi
0x180022431  lea     rcx, [rsp+68h+hMem]
0x180022436  mov     [rsp+68h+var_48], rcx
0x18002243b  mov     r9, rax
0x18002243e  xor     r8d, r8d; pReturnValue
0x180022441  lea     edx, [r8+1]; nProcNum
0x180022445  lea     rcx, stru_1800351A0; pProxyInfo
0x18002244c  call    cs:__imp_NdrClientCall3
0x180022453  nop     dword ptr [rax+rax+00h]
0x180022458  mov     rbx, rax
0x18002245b  mov     [rsp+68h+arg_10], rax
0x180022463  mov     [rsp+68h+var_34], ebx
0x180022467  mov     ecx, eax; int
0x180022469  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002246e  mov     esi, eax
0x180022470  mov     [rsp+68h+var_38], eax
0x180022474  test    ebx, ebx
0x180022476  jns     short loc_18002248C
0x180022478  mov     r8d, ebx
0x18002247b  lea     rdx, aRpcgetusercred_0; "RpcGetUserCredentials failed: 0x%x"
0x180022482  mov     ecx, 8; int
0x180022487  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002248c  jmp     short loc_1800224C4
0x18002248e  mov     esi, eax
0x180022490  mov     [rsp+68h+var_38], eax
0x180022494  test    eax, eax
0x180022496  jg      short loc_18002249C
0x180022498  mov     ebx, eax
0x18002249a  jmp     short loc_1800224A5
0x18002249c  movzx   ebx, ax
0x18002249f  or      ebx, 80070000h
0x1800224a5  mov     [rsp+68h+var_34], ebx
0x1800224a9  mov     r8d, eax
0x1800224ac  lea     rdx, aRpcgetusercred_1; "RpcGetUserCredentials threw an exceptio"...
0x1800224b3  mov     ecx, 8; int
0x1800224b8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800224bd  xor     edi, edi
0x1800224bf  mov     r15, [rsp+68h+arg_0]
0x1800224c4  test    ebx, ebx
0x1800224c6  js      loc_1800226BD
0x1800224cc  mov     rdx, [rsp+68h+hMem]
0x1800224d1  test    byte ptr [rdx+10h], 1
0x1800224d5  jz      loc_18002266C
0x1800224db  mov     r8d, [rdx+4]
0x1800224df  cmp     r8d, 38h ; '8'
0x1800224e3  jb      loc_180022660
0x1800224e9  mov     rdx, [rdx+8]
0x1800224ed  test    rdx, rdx
0x1800224f0  jz      loc_180022660
0x1800224f6  mov     ecx, [rdx]
0x1800224f8  cmp     ecx, 2
0x1800224fb  jz      loc_1800225D3
0x180022501  cmp     ecx, 7
0x180022504  jz      loc_1800225D3
0x18002250a  lea     eax, [rcx-0Dh]
0x18002250d  test    eax, 0FFFFFFFDh
0x180022512  jz      short loc_180022587
0x180022514  cmp     ecx, 201h
0x18002251a  jnz     short loc_18002256C
0x18002251c  cmp     [rdx+0Ch], edi
0x18002251f  jz      loc_1800225D9
0x180022525  lea     r9, [rdx+10h]
0x180022529  cmp     [r9], di
0x18002252d  jz      loc_1800225D9
0x180022533  movzx   ecx, word ptr [r9]
0x180022537  add     rcx, 30h ; '0'
0x18002253b  cmp     r8, rcx
0x18002253e  jb      loc_1800225D9
0x180022544  mov     ecx, [rdx+0Ch]
0x180022547  add     rcx, rdx; unsigned __int16 *
0x18002254a  movzx   r8d, word ptr [r9]; unsigned __int16
0x18002254e  mov     rdx, r9; unsigned __int16 *
0x180022551  call    ?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z; CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)
0x180022556  mov     ebx, eax
0x180022558  test    eax, eax
0x18002255a  jns     loc_18002263C
0x180022560  lea     r9, aCsecurityutils_0; "CSecurityUtils::DecryptCertInCredInfo"
0x180022567  jmp     loc_180022624
0x18002256c  lea     rdx, aRpcgetusercred; "RpcGetUserCredentials returned an inval"...
0x180022573  mov     ecx, 8; int
0x180022578  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002257d  mov     esi, 0Dh
0x180022582  jmp     loc_1800226BD
0x180022587  cmp     r8d, 50h ; 'P'
0x18002258b  jb      short loc_1800225D9
0x18002258d  lea     r9, [rdx+28h]
0x180022591  mov     r10, [r9+8]
0x180022595  test    r10, r10
0x180022598  jz      short loc_1800225D9
0x18002259a  cmp     [r9], di
0x18002259e  jz      short loc_1800225D9
0x1800225a0  movzx   r11d, word ptr [rdx+2Ah]
0x1800225a5  lea     rcx, [r10+r11]
0x1800225a9  cmp     r8, rcx
0x1800225ac  jb      short loc_1800225D9
0x1800225ae  cmp     [r9], r11w
0x1800225b2  ja      short loc_1800225D9
0x1800225b4  lea     rcx, [r10+rdx]; unsigned __int16 *
0x1800225b8  movzx   r8d, r11w; unsigned __int16
0x1800225bc  mov     rdx, r9; unsigned __int16 *
0x1800225bf  call    ?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z; CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)
0x1800225c4  mov     ebx, eax
0x1800225c6  test    eax, eax
0x1800225c8  jns     short loc_18002263C
0x1800225ca  lea     r9, aCsecurityutils_1; "CSecurityUtils::DecryptPINInCredInfo"
0x1800225d1  jmp     short loc_180022624
0x1800225d3  cmp     r8d, 40h ; '@'
0x1800225d7  jnb     short loc_1800225E0
0x1800225d9  mov     ebx, 8007000Dh
0x1800225de  jmp     short loc_18002263C
0x1800225e0  lea     r9, [rdx+28h]
0x1800225e4  mov     r10, [r9+8]
0x1800225e8  test    r10, r10
0x1800225eb  jz      short loc_18002263A
0x1800225ed  cmp     [r9], di
0x1800225f1  jz      short loc_18002263A
0x1800225f3  movzx   r11d, word ptr [rdx+2Ah]
0x1800225f8  lea     rcx, [r10+r11]
0x1800225fc  cmp     r8, rcx
0x1800225ff  jb      short loc_1800225D9
0x180022601  cmp     [r9], r11w
0x180022605  ja      short loc_1800225D9
0x180022607  lea     rcx, [r10+rdx]; unsigned __int16 *
0x18002260b  movzx   r8d, r11w; unsigned __int16
0x18002260f  mov     rdx, r9; unsigned __int16 *
0x180022612  call    ?UnprotectString@CSecurityUtils@@CAJPEAG0G@Z; CSecurityUtils::UnprotectString(ushort *,ushort *,ushort)
0x180022617  mov     ebx, eax
0x180022619  test    eax, eax
0x18002261b  jns     short loc_18002263C
0x18002261d  lea     r9, aCsecurityutils; "CSecurityUtils::DecryptPasswordInCredIn"...
0x180022624  mov     r8d, eax
0x180022627  lea     rdx, aUnprotectstrin; "UnprotectString failed: 0x%x in %s"
0x18002262e  mov     ecx, 8; int
0x180022633  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022638  jmp     short loc_18002263C
0x18002263a  mov     ebx, edi
0x18002263c  test    ebx, ebx
0x18002263e  jns     short loc_18002266C
0x180022640  mov     r8d, ebx
0x180022643  lea     rdx, aDecryptingPass; "Decrypting password or PIN failed: 0x%x"
0x18002264a  mov     ecx, 8; int
0x18002264f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022654  mov     ecx, ebx; int
0x180022656  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18002265b  jmp     loc_180022418
0x180022660  lea     rdx, aRpcgetusercred_2; "RpcGetUserCredentials returned an inval"...
0x180022667  jmp     loc_180022573
0x18002266c  mov     edx, 18h; uBytes
0x180022671  lea     ecx, [rdx+28h]; uFlags
0x180022674  call    cs:__imp_LocalAlloc
0x18002267b  nop     dword ptr [rax+rax+00h]
0x180022680  mov     rdx, rax
0x180022683  mov     [r15], rax
0x180022686  test    rax, rax
0x180022689  jnz     short loc_180022690
0x18002268b  lea     esi, [rax+8]
0x18002268e  jmp     short loc_1800226BD
0x180022690  mov     rax, [rsp+68h+hMem]
0x180022695  mov     ecx, [rax]
0x180022697  mov     [rdx+4], ecx
0x18002269a  mov     rax, [r15]
0x18002269d  mov     [rax], edi
0x18002269f  mov     rdx, [r15]
0x1800226a2  mov     rax, [rsp+68h+hMem]
0x1800226a7  mov     ecx, [rax+4]
0x1800226aa  mov     [rdx+8], ecx
0x1800226ad  mov     rdx, [r15]
0x1800226b0  mov     rax, [rsp+68h+hMem]
0x1800226b5  mov     rcx, [rax+8]
0x1800226b9  mov     [rdx+10h], rcx
0x1800226bd  mov     rcx, [rsp+68h+hMem]
0x1800226c2  test    rcx, rcx
0x1800226c5  jz      short loc_1800226F4
0x1800226c7  test    esi, esi
0x1800226c9  jz      short loc_1800226E8
0x1800226cb  mov     rax, [rcx+8]
0x1800226cf  test    rax, rax
0x1800226d2  jz      short loc_1800226E8
0x1800226d4  mov     rcx, rax; hMem
0x1800226d7  call    cs:__imp_LocalFree
0x1800226de  nop     dword ptr [rax+rax+00h]
0x1800226e3  mov     rcx, [rsp+68h+hMem]; hMem
0x1800226e8  call    cs:__imp_LocalFree
0x1800226ef  nop     dword ptr [rax+rax+00h]
0x1800226f4  test    esi, esi
0x1800226f6  jz      short loc_18002270F
0x1800226f8  cmp     [r15], rdi
0x1800226fb  jz      short loc_18002270F
0x1800226fd  mov     rcx, [r15]; hMem
0x180022700  call    cs:__imp_LocalFree
0x180022707  nop     dword ptr [rax+rax+00h]
0x18002270c  mov     [r15], rdi
0x18002270f  lea     rcx, [rsp+68h+var_30]; this
0x180022714  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180022719  mov     eax, esi
0x18002271b  mov     rbx, [rsp+68h+arg_18]
0x180022723  add     rsp, 50h
0x180022727  pop     r15
0x180022729  pop     rdi
0x18002272a  pop     rsi
0x18002272b  retn
0x180033757  push    rbp
0x180033759  sub     rsp, 30h
0x18003375d  mov     rbp, rdx
0x180033760  mov     rcx, [rcx]
0x180033763  mov     ecx, [rcx]; ExceptionCode
0x180033765  call    cs:__imp_I_RpcExceptionFilter
0x18003376c  nop     dword ptr [rax+rax+00h]
0x180033771  nop
0x180033772  add     rsp, 30h
0x180033776  pop     rbp
0x180033777  retn
```
