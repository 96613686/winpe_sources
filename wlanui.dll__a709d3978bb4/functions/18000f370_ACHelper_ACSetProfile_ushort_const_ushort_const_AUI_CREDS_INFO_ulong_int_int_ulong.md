# ACHelper::ACSetProfile(ushort const *,ushort const *,_AUI_CREDS_INFO *,ulong,int,int *,ulong *)

- ea: `0x18000f370`
- end: `0x18000f6ad`
- name: `?ACSetProfile@ACHelper@@QEAAKPEBG0PEAU_AUI_CREDS_INFO@@KHPEAHPEAK@Z`
- size: `829`
- prototype: `__int64 __fastcall(ACHelper *this, const unsigned __int16 *, const unsigned __int16 *, struct _AUI_CREDS_INFO *, DWORD dwFlags, int, int *, unsigned int *pdwReasonCode)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180010870`

## callees

- `0x18000637c`
- `0x180006758`
- `0x1800070e8`
- `0x18000f330`
- `0x18000f370`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f3c3`
- `KERNEL32!GetLastError` at `0x18000f48f`
- `KERNEL32!GetLastError` at `0x18000f3c3`
- `KERNEL32!GetLastError` at `0x18000f48f`
- `KERNEL32!GlobalAlloc` at `0x18000f481`
- `KERNEL32!GlobalAlloc` at `0x18000f481`
- `KERNEL32!GlobalFree` at `0x18000f5f2`
- `KERNEL32!GlobalFree` at `0x18000f5f2`
- `ole32!CoSetProxyBlanket` at `0x18000f529`
- `ole32!CoSetProxyBlanket` at `0x18000f58b`
- `ole32!CoSetProxyBlanket` at `0x18000f529`
- `ole32!CoSetProxyBlanket` at `0x18000f58b`
- `ole32!CreateStreamOnHGlobal` at `0x18000f4a8`
- `ole32!CreateStreamOnHGlobal` at `0x18000f4a8`
- `wlanapi!WlanSetProfile` at `0x18000f62e`
- `wlanapi!WlanSetProfile` at `0x18000f62e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f3b5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f3b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f5e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f5e4`

## pseudocode

```c
__int64 __fastcall ACHelper::ACSetProfile(
        ACHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _AUI_CREDS_INFO *a4,
        DWORD dwFlags,
        int a6,
        int *a7,
        unsigned int *pdwReasonCode)
{
  unsigned int LastError; // ebx
  const struct _GUID *v13; // rdx
  HWND v14; // rcx
  const struct _GUID *v15; // r8
  OLECHAR *v16; // r12
  HGLOBAL v17; // r15
  HRESULT v18; // eax
  int v19; // eax
  int v20; // esi
  HRESULT v21; // eax
  int v22; // eax
  HRESULT v23; // eax
  int v24; // eax
  void *v25; // rcx
  LPSTREAM ppstm; // [rsp+40h] [rbp-20h] BYREF
  void *v28; // [rsp+48h] [rbp-18h] BYREF
  GUID pInterfaceGuid; // [rsp+50h] [rbp-10h] BYREF

  v28 = 0;
  ppstm = 0;
  if ( a6 )
  {
    LastError = 0;
    v16 = SysAllocString(a2);
    if ( v16 || (LastError = GetLastError()) == 0 )
    {
      v17 = 0;
      v18 = CoCreateInstanceAsAdmin(v14, v13, v15, &v28);
      if ( v18 >= 0 )
        goto LABEL_8;
      LastError = (unsigned __int16)v18;
      if ( (v18 & 0x1FFF0000) != 0x70000 )
        LastError = v18;
      if ( !LastError )
      {
LABEL_8:
        v19 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, OLECHAR *, _QWORD, int, unsigned int *))(*(_QWORD *)v28 + 24LL))(
                v28,
                *((_QWORD *)this + 2),
                dwFlags,
                v16,
                0,
                1,
                pdwReasonCode);
        v20 = v19;
        if ( v19 >= 0 )
          goto LABEL_19;
        LastError = (unsigned __int16)v19;
        if ( (v19 & 0x1FFF0000) != 0x70000 )
          LastError = v19;
        if ( !LastError )
        {
LABEL_19:
          if ( a4 )
          {
            if ( *((_DWORD *)a4 + 1) )
            {
              v17 = GlobalAlloc(2u, (int)(*((_DWORD *)a4 + 6) + 72 + ((2580 * *((_DWORD *)a4 + 10)) & 0xFFFFFFF0)));
              if ( v17 || (LastError = GetLastError(), v20 >= 0) )
              {
                v21 = CreateStreamOnHGlobal(v17, 0, &ppstm);
                if ( v21 >= 0 )
                  goto LABEL_20;
                LastError = (unsigned __int16)v21;
                if ( (v21 & 0x1FFF0000) != 0x70000 )
                  LastError = v21;
                if ( !LastError )
                {
LABEL_20:
                  v22 = WriteCredsInfoToStream(ppstm, a4);
                  if ( v22 >= 0 )
                    goto LABEL_24;
                  LastError = (unsigned __int16)v22;
                  if ( (v22 & 0x1FFF0000) != 0x70000 )
                    LastError = v22;
                  if ( !LastError )
                  {
LABEL_24:
                    v23 = CoSetProxyBlanket(
                            (IUnknown *)ppstm,
                            0xFFFFFFFF,
                            0,
                            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                            0,
                            3u,
                            0,
                            0x20u);
                    if ( !v23 || v23 == -2147467262 )
                    {
                      *(_QWORD *)&pInterfaceGuid.Data1 = 0;
                      if ( (**(int (__fastcall ***)(LPSTREAM, GUID *, GUID *))ppstm)(
                             ppstm,
                             &GUID_00000000_0000_0000_c000_000000000046,
                             &pInterfaceGuid) >= 0 )
                      {
                        CoSetProxyBlanket(
                          (IUnknown *)ppstm,
                          0xFFFFFFFF,
                          0,
                          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                          0,
                          3u,
                          0,
                          0x20u);
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pInterfaceGuid.Data1 + 16LL))(*(_QWORD *)&pInterfaceGuid.Data1);
                      }
                    }
                    v24 = (*(__int64 (__fastcall **)(void *, _QWORD, LPSTREAM, const unsigned __int16 *))(*(_QWORD *)v28 + 40LL))(
                            v28,
                            *((_QWORD *)this + 2),
                            ppstm,
                            a3);
                    if ( v24 < 0 )
                    {
                      LastError = (unsigned __int16)v24;
                      if ( (v24 & 0x1FFF0000) != 0x70000 )
                        LastError = v24;
                      *a7 = 1;
                    }
                  }
                }
              }
            }
          }
        }
      }
      if ( v16 )
        SysFreeString(v16);
      if ( v17 )
        GlobalFree(v17);
    }
  }
  else
  {
    LastError = ACHelper::ACOpenHandle((PHANDLE)this);
    if ( !LastError )
    {
      LastError = WlanSetProfile(*(HANDLE *)this, *((const GUID **)this + 2), dwFlags, a2, 0, 1, 0, pdwReasonCode);
      if ( !LastError )
      {
        v25 = *(void **)this;
        pInterfaceGuid = *(GUID *)*((_QWORD *)this + 2);
        LastError = SaveCreds(v25, &pInterfaceGuid, a3, a4);
        if ( LastError )
          *a7 = 1;
      }
    }
  }
  if ( ppstm )
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  if ( v28 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
  return LastError;
}

```

## disassembly

```asm
0x18000f370  mov     [rsp-28h+arg_0], rbx
0x18000f375  mov     [rsp-28h+arg_8], rsi
0x18000f37a  mov     [rsp-28h+arg_10], r8
0x18000f37f  push    rbp
0x18000f380  push    rdi
0x18000f381  push    r12
0x18000f383  push    r14
0x18000f385  push    r15
0x18000f387  mov     rbp, rsp
0x18000f38a  sub     rsp, 60h
0x18000f38e  xor     r12d, r12d
0x18000f391  mov     rdi, r9
0x18000f394  mov     r15, r8
0x18000f397  mov     rsi, rdx
0x18000f39a  mov     r14, rcx
0x18000f39d  mov     [rbp+var_18], r12
0x18000f3a1  mov     [rbp+ppstm], r12
0x18000f3a5  cmp     [rbp+arg_28], r12d
0x18000f3a9  jz      loc_18000F5FA
0x18000f3af  mov     rcx, rdx; psz
0x18000f3b2  mov     ebx, r12d
0x18000f3b5  call    cs:__imp_SysAllocString
0x18000f3bb  mov     r12, rax
0x18000f3be  test    rax, rax
0x18000f3c1  jnz     short loc_18000F3D3
0x18000f3c3  call    cs:__imp_GetLastError
0x18000f3c9  mov     ebx, eax
0x18000f3cb  test    eax, eax
0x18000f3cd  jnz     loc_18000F668
0x18000f3d3  lea     r9, [rbp+var_18]; void **
0x18000f3d7  xor     r15d, r15d
0x18000f3da  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x18000f3df  test    eax, eax
0x18000f3e1  jns     short loc_18000F400
0x18000f3e3  mov     ecx, eax
0x18000f3e5  movzx   ebx, ax
0x18000f3e8  and     ecx, 1FFF0000h
0x18000f3ee  cmp     ecx, 70000h
0x18000f3f4  jz      short loc_18000F3F8
0x18000f3f6  mov     ebx, eax
0x18000f3f8  test    ebx, ebx
0x18000f3fa  jnz     loc_18000F5DC
0x18000f400  mov     rcx, [rbp+var_18]
0x18000f404  mov     r9, r12
0x18000f407  mov     rdx, [rbp+pdwReasonCode]
0x18000f40b  mov     r8d, [rbp+dwFlags]
0x18000f40f  mov     [rsp+60h+pAuthInfo], rdx
0x18000f414  mov     rax, [rcx]
0x18000f417  mov     rdx, [r14+10h]
0x18000f41b  mov     [rsp+60h+dwImpLevel], 1
0x18000f423  mov     qword ptr [rsp+60h+dwAuthnLevel], r15
0x18000f428  mov     rax, [rax+18h]
0x18000f42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f431  mov     esi, eax
0x18000f433  test    eax, eax
0x18000f435  jns     short loc_18000F454
0x18000f437  mov     ecx, eax
0x18000f439  movzx   ebx, si
0x18000f43c  and     ecx, 1FFF0000h
0x18000f442  cmp     ecx, 70000h
0x18000f448  jz      short loc_18000F44C
0x18000f44a  mov     ebx, eax
0x18000f44c  test    ebx, ebx
0x18000f44e  jnz     loc_18000F5DC
0x18000f454  test    rdi, rdi
0x18000f457  jz      loc_18000F5DC
0x18000f45d  cmp     [rdi+4], r15d
0x18000f461  jz      loc_18000F5DC
0x18000f467  imul    ecx, [rdi+28h], 0A14h
0x18000f46e  mov     eax, [rdi+18h]
0x18000f471  add     eax, 48h ; 'H'
0x18000f474  and     ecx, 0FFFFFFF0h
0x18000f477  add     ecx, eax
0x18000f479  movsxd  rdx, ecx; dwBytes
0x18000f47c  mov     ecx, 2; uFlags
0x18000f481  call    cs:__imp_GlobalAlloc
0x18000f487  mov     r15, rax
0x18000f48a  test    rax, rax
0x18000f48d  jnz     short loc_18000F49F
0x18000f48f  call    cs:__imp_GetLastError
0x18000f495  mov     ebx, eax
0x18000f497  test    esi, esi
0x18000f499  js      loc_18000F5DC
0x18000f49f  lea     r8, [rbp+ppstm]; ppstm
0x18000f4a3  xor     edx, edx; fDeleteOnRelease
0x18000f4a5  mov     rcx, r15; hGlobal
0x18000f4a8  call    cs:__imp_CreateStreamOnHGlobal
0x18000f4ae  mov     esi, 1FFF0000h
0x18000f4b3  test    eax, eax
0x18000f4b5  jns     short loc_18000F4D0
0x18000f4b7  mov     ecx, eax
0x18000f4b9  movzx   ebx, ax
0x18000f4bc  and     ecx, esi
0x18000f4be  cmp     ecx, 70000h
0x18000f4c4  jz      short loc_18000F4C8
0x18000f4c6  mov     ebx, eax
0x18000f4c8  test    ebx, ebx
0x18000f4ca  jnz     loc_18000F5DC
0x18000f4d0  mov     rcx, [rbp+ppstm]; struct IStream *
0x18000f4d4  mov     rdx, rdi; struct _AUI_CREDS_INFO *
0x18000f4d7  call    ?WriteCredsInfoToStream@@YAJPEAUIStream@@PEAU_AUI_CREDS_INFO@@@Z; WriteCredsInfoToStream(IStream *,_AUI_CREDS_INFO *)
0x18000f4dc  test    eax, eax
0x18000f4de  jns     short loc_18000F4F9
0x18000f4e0  mov     ecx, eax
0x18000f4e2  movzx   ebx, ax
0x18000f4e5  and     ecx, esi
0x18000f4e7  cmp     ecx, 70000h
0x18000f4ed  jz      short loc_18000F4F1
0x18000f4ef  mov     ebx, eax
0x18000f4f1  test    ebx, ebx
0x18000f4f3  jnz     loc_18000F5DC
0x18000f4f9  mov     rcx, [rbp+ppstm]; pProxy
0x18000f4fd  mov     edi, 20h ; ' '
0x18000f502  mov     [rsp+60h+dwCapabilities], edi; dwCapabilities
0x18000f506  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18000f50a  mov     [rsp+60h+pAuthInfo], 0; pAuthInfo
0x18000f513  xor     r8d, r8d; dwAuthzSvc
0x18000f516  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x18000f51e  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000f521  mov     [rsp+60h+dwAuthnLevel], 0; dwAuthnLevel
0x18000f529  call    cs:__imp_CoSetProxyBlanket
0x18000f52f  test    eax, eax
0x18000f531  jz      short loc_18000F53A
0x18000f533  cmp     eax, 80004002h
0x18000f538  jnz     short loc_18000F5A1
0x18000f53a  mov     rcx, [rbp+ppstm]
0x18000f53e  lea     r8, [rbp+pInterfaceGuid]
0x18000f542  mov     qword ptr [rbp+pInterfaceGuid.Data1], 0
0x18000f54a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000f551  mov     rax, [rcx]
0x18000f554  mov     rax, [rax]
0x18000f557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f55c  test    eax, eax
0x18000f55e  js      short loc_18000F5A1
0x18000f560  mov     rcx, [rbp+ppstm]; pProxy
0x18000f564  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18000f568  mov     [rsp+60h+dwCapabilities], edi; dwCapabilities
0x18000f56c  xor     r8d, r8d; dwAuthzSvc
0x18000f56f  mov     [rsp+60h+pAuthInfo], 0; pAuthInfo
0x18000f578  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000f57b  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x18000f583  mov     [rsp+60h+dwAuthnLevel], 0; dwAuthnLevel
0x18000f58b  call    cs:__imp_CoSetProxyBlanket
0x18000f591  mov     rcx, qword ptr [rbp+pInterfaceGuid.Data1]
0x18000f595  mov     rax, [rcx]
0x18000f598  mov     rax, [rax+10h]
0x18000f59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5a1  mov     rcx, [rbp+var_18]
0x18000f5a5  mov     r9, [rbp+arg_10]
0x18000f5a9  mov     r8, [rbp+ppstm]
0x18000f5ad  mov     rdx, [r14+10h]
0x18000f5b1  mov     rax, [rcx]
0x18000f5b4  mov     rax, [rax+28h]
0x18000f5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5bd  test    eax, eax
0x18000f5bf  jns     short loc_18000F5DC
0x18000f5c1  mov     ecx, eax
0x18000f5c3  movzx   ebx, ax
0x18000f5c6  and     ecx, esi
0x18000f5c8  cmp     ecx, 70000h
0x18000f5ce  jz      short loc_18000F5D2
0x18000f5d0  mov     ebx, eax
0x18000f5d2  mov     rax, [rbp+arg_30]
0x18000f5d6  mov     dword ptr [rax], 1
0x18000f5dc  test    r12, r12
0x18000f5df  jz      short loc_18000F5EA
0x18000f5e1  mov     rcx, r12; bstrString
0x18000f5e4  call    cs:__imp_SysFreeString
0x18000f5ea  test    r15, r15
0x18000f5ed  jz      short loc_18000F668
0x18000f5ef  mov     rcx, r15; hMem
0x18000f5f2  call    cs:__imp_GlobalFree
0x18000f5f8  jmp     short loc_18000F668
0x18000f5fa  call    ?ACOpenHandle@ACHelper@@QEAAKXZ; ACHelper::ACOpenHandle(void)
0x18000f5ff  mov     ebx, eax
0x18000f601  test    eax, eax
0x18000f603  jnz     short loc_18000F668
0x18000f605  mov     rax, [rbp+pdwReasonCode]
0x18000f609  mov     r9, rsi; strProfileXml
0x18000f60c  mov     r8d, [rbp+dwFlags]; dwFlags
0x18000f610  mov     rdx, [r14+10h]; pInterfaceGuid
0x18000f614  mov     rcx, [r14]; hClientHandle
0x18000f617  mov     qword ptr [rsp+60h+dwCapabilities], rax; pdwReasonCode
0x18000f61c  mov     [rsp+60h+pAuthInfo], r12; pReserved
0x18000f621  mov     [rsp+60h+dwImpLevel], 1; bOverwrite
0x18000f629  mov     qword ptr [rsp+60h+dwAuthnLevel], r12; strAllUserProfileSecurity
0x18000f62e  call    cs:__imp_WlanSetProfile
0x18000f634  mov     ebx, eax
0x18000f636  test    eax, eax
0x18000f638  jnz     short loc_18000F668
0x18000f63a  mov     rax, [r14+10h]
0x18000f63e  lea     rdx, [rbp+pInterfaceGuid]; pInterfaceGuid
0x18000f642  mov     rcx, [r14]; hClientHandle
0x18000f645  mov     r9, rdi; struct _AUI_CREDS_INFO *
0x18000f648  mov     r8, r15; strProfileName
0x18000f64b  movups  xmm0, xmmword ptr [rax]
0x18000f64e  movdqu  xmmword ptr [rbp+pInterfaceGuid.Data1], xmm0
0x18000f653  call    ?SaveCreds@@YAKPEAXU_GUID@@PEBGPEAU_AUI_CREDS_INFO@@@Z; SaveCreds(void *,_GUID,ushort const *,_AUI_CREDS_INFO *)
0x18000f658  mov     ebx, eax
0x18000f65a  test    eax, eax
0x18000f65c  jz      short loc_18000F668
0x18000f65e  mov     rax, [rbp+arg_30]
0x18000f662  mov     dword ptr [rax], 1
0x18000f668  mov     rcx, [rbp+ppstm]
0x18000f66c  test    rcx, rcx
0x18000f66f  jz      short loc_18000F67D
0x18000f671  mov     rax, [rcx]
0x18000f674  mov     rax, [rax+10h]
0x18000f678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f67d  mov     rcx, [rbp+var_18]
0x18000f681  test    rcx, rcx
0x18000f684  jz      short loc_18000F692
0x18000f686  mov     rax, [rcx]
0x18000f689  mov     rax, [rax+10h]
0x18000f68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f692  lea     r11, [rsp+60h+var_s0]
0x18000f697  mov     eax, ebx
0x18000f699  mov     rbx, [r11+30h]
0x18000f69d  mov     rsi, [r11+38h]
0x18000f6a1  mov     rsp, r11
0x18000f6a4  pop     r15
0x18000f6a6  pop     r14
0x18000f6a8  pop     r12
0x18000f6aa  pop     rdi
0x18000f6ab  pop     rbp
0x18000f6ac  retn
```
