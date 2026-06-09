# RestrictedToken::CreateToken(void)

- ea: `0x1800c551c`
- end: `0x1800c5827`
- name: `?CreateToken@RestrictedToken@@AEAAJXZ`
- size: `779`
- prototype: `__int64 __fastcall(RestrictedToken *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180092f60`

## callees

- `0x18001b480`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c50e4`
- `0x1800c5434`
- `0x1800c551c`
- `0x1800c5b2c`
- `0x1800c5c40`
- `0x1800c5d08`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c572e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c572e`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800c5690`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x1800c5690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c569a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c569a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c55b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c57ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c57fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c55b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c57ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c57fe`

## pseudocode

```c
__int64 __fastcall RestrictedToken::CreateToken(RestrictedToken *this)
{
  unsigned int v1; // edx
  RestrictedToken *v2; // rcx
  int v3; // eax
  RestrictedToken *v4; // rcx
  __int64 v5; // r9
  unsigned int v6; // edi
  RestrictedToken *v7; // rcx
  RestrictedToken *v8; // rcx
  signed int v9; // eax
  RestrictedToken *v10; // rcx
  signed int LastError; // eax
  DWORD DeletePrivilegeCount[2]; // [rsp+20h] [rbp-E0h]
  DWORD DisableSidCount; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh]
  DWORD RestrictedSidCount; // [rsp+58h] [rbp-A8h] BYREF
  struct _TOKEN_DEFAULT_DACL *v17; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+68h] [rbp-98h] BYREF
  PSID_AND_ATTRIBUTES SidsToDisable; // [rsp+70h] [rbp-90h] BYREF
  struct _TOKEN_GROUPS *v20; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h] BYREF
  struct _SID_AND_ATTRIBUTES SidsToRestrict; // [rsp+90h] [rbp-70h] BYREF
  struct _SID pSourceSid[6]; // [rsp+E0h] [rbp-20h] BYREF

  v15 = 0;
  hObject = 0;
  ExistingTokenHandle = 0;
  DisableSidCount = 0;
  memset_0(&SidsToRestrict, 0, 0x50u);
  v20 = 0;
  SidsToDisable = 0;
  v17 = 0;
  memset_0(pSourceSid, 0, 0x44u);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 12, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids);
  v2 = (RestrictedToken *)::hObject;
  if ( ::hObject )
  {
    CloseHandle(::hObject);
    ::hObject = 0;
  }
  if ( qword_180108038 )
    WxFreeHeapEx(&qword_180108038);
  v3 = RestrictedToken::OpenCurrentProcToken(v2, v1, &ExistingTokenHandle);
  v5 = (unsigned int)v3;
  if ( v3 < 0 )
  {
    v15 = 85;
LABEL_9:
    v6 = v3;
    goto LABEL_33;
  }
  v3 = RestrictedToken::PopulateSidsToDisable(
         v4,
         ExistingTokenHandle,
         &pSourceSid[0].Revision,
         &v20,
         &DisableSidCount,
         &SidsToDisable);
  v5 = (unsigned int)v3;
  if ( v3 < 0 )
  {
    v15 = 91;
    goto LABEL_9;
  }
  RestrictedSidCount = 5;
  v3 = RestrictedToken::PopulateRestrictSidsList(v7, pSourceSid, &RestrictedSidCount, &SidsToRestrict);
  v5 = (unsigned int)v3;
  if ( v3 < 0 )
  {
    v15 = 97;
    goto LABEL_9;
  }
  if ( CreateRestrictedToken(
         ExistingTokenHandle,
         8u,
         DisableSidCount,
         SidsToDisable,
         0,
         0,
         RestrictedSidCount,
         &SidsToRestrict,
         &hObject) )
  {
    v3 = RestrictedToken::AdjustDefaultTokenDacl(v8, hObject, pSourceSid, &v17);
    v5 = (unsigned int)v3;
    if ( v3 < 0 )
    {
      v15 = 111;
      goto LABEL_9;
    }
    v3 = RestrictedToken::AdjustTokenLowIntegrity(v10, hObject);
    v5 = (unsigned int)v3;
    if ( v3 < 0 )
    {
      v15 = 113;
      goto LABEL_9;
    }
    memset_0(PacWorkerClient::s_RestrictedToken, 0, 0x44u);
    if ( CopySid(0x44u, PacWorkerClient::s_RestrictedToken, pSourceSid) )
    {
      v5 = 0;
      ::hObject = hObject;
      v6 = 0;
      qword_180108038 = (__int64)v17;
      hObject = 0;
      v17 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = (unsigned int)LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (int)v5 < 0 )
      {
        v6 = v5;
      }
      else
      {
        v6 = -2147418113;
        v5 = 2147549183LL;
      }
      v15 = 120;
    }
  }
  else
  {
    v9 = GetLastError();
    v5 = (unsigned int)v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    if ( (int)v5 < 0 )
    {
      v6 = v5;
    }
    else
    {
      v6 = -2147418113;
      v5 = 2147549183LL;
    }
    v15 = 107;
  }
LABEL_33:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 13, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids, v5, *(_QWORD *)DeletePrivilegeCount);
  if ( v17 )
    WxFreeHeapEx(&v17);
  if ( SidsToDisable )
    WxFreeHeapEx(&SidsToDisable);
  if ( v20 )
    WxFreeHeapEx(&v20);
  if ( ExistingTokenHandle )
    CloseHandle(ExistingTokenHandle);
  if ( hObject )
    CloseHandle(hObject);
  return v6;
}

```

## disassembly

```asm
0x1800c551c  mov     [rsp-8+arg_0], rsi
0x1800c5521  mov     [rsp-8+arg_8], rdi
0x1800c5526  push    rbp
0x1800c5527  lea     rbp, [rsp-40h]
0x1800c552c  sub     rsp, 140h
0x1800c5533  mov     rax, cs:__security_cookie
0x1800c553a  xor     rax, rsp
0x1800c553d  mov     [rbp+40h+var_10], rax
0x1800c5541  xor     esi, esi
0x1800c5543  lea     rcx, [rbp+40h+var_B0]; void *
0x1800c5547  xor     edx, edx; Val
0x1800c5549  mov     [rsp+140h+var_EC], esi
0x1800c554d  mov     [rbp+40h+hObject], rsi
0x1800c5551  mov     [rsp+140h+ExistingTokenHandle], rsi
0x1800c5556  lea     r8d, [rsi+50h]; Size
0x1800c555a  mov     [rsp+140h+DisableSidCount], esi
0x1800c555e  call    memset_0
0x1800c5563  xor     edx, edx; Val
0x1800c5565  mov     [rsp+140h+var_C8], rsi
0x1800c556a  lea     r8d, [rsi+44h]; Size
0x1800c556e  mov     [rsp+140h+SidsToDisable], rsi
0x1800c5573  lea     rcx, [rbp+40h+pSourceSid]; void *
0x1800c5577  mov     [rsp+140h+var_E0], rsi
0x1800c557c  call    memset_0
0x1800c5581  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5588  lea     rdi, ?s_RestrictedToken@PacWorkerClient@@0VRestrictedToken@@A; RestrictedToken PacWorkerClient::s_RestrictedToken
0x1800c558f  jz      short loc_1800C55A8
0x1800c5591  lea     edx, [rsi+0Ch]
0x1800c5594  mov     ecx, 405h
0x1800c5599  mov     r9, rdi
0x1800c559c  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c55a3  call    WPP_SF_q
0x1800c55a8  mov     rcx, cs:hObject; hObject
0x1800c55af  test    rcx, rcx
0x1800c55b2  jz      short loc_1800C55C1
0x1800c55b4  call    cs:__imp_CloseHandle
0x1800c55ba  mov     cs:hObject, rsi
0x1800c55c1  cmp     cs:qword_180108038, rsi
0x1800c55c8  jz      short loc_1800C55D6
0x1800c55ca  lea     rcx, qword_180108038
0x1800c55d1  call    WxFreeHeapEx
0x1800c55d6  lea     r8, [rsp+140h+ExistingTokenHandle]; void **
0x1800c55db  call    ?OpenCurrentProcToken@RestrictedToken@@AEAAJKPEAPEAX@Z; RestrictedToken::OpenCurrentProcToken(ulong,void * *)
0x1800c55e0  mov     r9d, eax
0x1800c55e3  test    eax, eax
0x1800c55e5  jns     short loc_1800C55F6
0x1800c55e7  mov     [rsp+140h+var_EC], 55h ; 'U'
0x1800c55ef  mov     edi, eax
0x1800c55f1  jmp     loc_1800C5791
0x1800c55f6  mov     rdx, [rsp+140h+ExistingTokenHandle]; void *
0x1800c55fb  lea     rax, [rsp+140h+SidsToDisable]
0x1800c5600  mov     [rsp+140h+PrivilegesToDelete], rax; struct _SID_AND_ATTRIBUTES **
0x1800c5605  lea     r9, [rsp+140h+var_C8]; struct _TOKEN_GROUPS **
0x1800c560a  lea     rax, [rsp+140h+DisableSidCount]
0x1800c560f  lea     r8, [rbp+40h+pSourceSid]; unsigned __int8 *
0x1800c5613  mov     qword ptr [rsp+140h+DeletePrivilegeCount], rax; unsigned int *
0x1800c5618  call    ?PopulateSidsToDisable@RestrictedToken@@AEAAJPEAXPEAEPEAPEAU_TOKEN_GROUPS@@PEAKPEAPEAU_SID_AND_ATTRIBUTES@@@Z; RestrictedToken::PopulateSidsToDisable(void *,uchar *,_TOKEN_GROUPS * *,ulong *,_SID_AND_ATTRIBUTES * *)
0x1800c561d  mov     r9d, eax
0x1800c5620  test    eax, eax
0x1800c5622  jns     short loc_1800C562E
0x1800c5624  mov     [rsp+140h+var_EC], 5Bh ; '['
0x1800c562c  jmp     short loc_1800C55EF
0x1800c562e  lea     r9, [rbp+40h+var_B0]; struct _SID_AND_ATTRIBUTES *
0x1800c5632  mov     [rsp+140h+var_E8], 5
0x1800c563a  lea     r8, [rsp+140h+var_E8]; unsigned int *
0x1800c563f  lea     rdx, [rbp+40h+pSourceSid]; struct _SID *
0x1800c5643  call    ?PopulateRestrictSidsList@RestrictedToken@@AEAAJPEAU_SID@@PEAKPEAU_SID_AND_ATTRIBUTES@@@Z; RestrictedToken::PopulateRestrictSidsList(_SID *,ulong *,_SID_AND_ATTRIBUTES *)
0x1800c5648  mov     r9d, eax
0x1800c564b  test    eax, eax
0x1800c564d  jns     short loc_1800C5659
0x1800c564f  mov     [rsp+140h+var_EC], 61h ; 'a'
0x1800c5657  jmp     short loc_1800C55EF
0x1800c5659  mov     r9, [rsp+140h+SidsToDisable]; SidsToDisable
0x1800c565e  lea     rax, [rbp+40h+hObject]
0x1800c5662  mov     r8d, [rsp+140h+DisableSidCount]; DisableSidCount
0x1800c5667  mov     edx, 8; Flags
0x1800c566c  mov     rcx, [rsp+140h+ExistingTokenHandle]; ExistingTokenHandle
0x1800c5671  mov     [rsp+140h+NewTokenHandle], rax; NewTokenHandle
0x1800c5676  lea     rax, [rbp+40h+var_B0]
0x1800c567a  mov     [rsp+140h+SidsToRestrict], rax; SidsToRestrict
0x1800c567f  mov     eax, [rsp+140h+var_E8]
0x1800c5683  mov     [rsp+140h+RestrictedSidCount], eax; RestrictedSidCount
0x1800c5687  mov     [rsp+140h+PrivilegesToDelete], rsi; PrivilegesToDelete
0x1800c568c  mov     [rsp+140h+DeletePrivilegeCount], esi; DeletePrivilegeCount
0x1800c5690  call    cs:__imp_CreateRestrictedToken
0x1800c5696  test    eax, eax
0x1800c5698  jnz     short loc_1800C56D1
0x1800c569a  call    cs:__imp_GetLastError
0x1800c56a0  mov     r9d, eax
0x1800c56a3  test    eax, eax
0x1800c56a5  jle     short loc_1800C56B2
0x1800c56a7  movzx   r9d, ax
0x1800c56ab  or      r9d, 80070000h
0x1800c56b2  test    r9d, r9d
0x1800c56b5  js      short loc_1800C56C1
0x1800c56b7  mov     edi, 8000FFFFh
0x1800c56bc  mov     r9d, edi
0x1800c56bf  jmp     short loc_1800C56C4
0x1800c56c1  mov     edi, r9d
0x1800c56c4  mov     [rsp+140h+var_EC], 6Bh ; 'k'
0x1800c56cc  jmp     loc_1800C5791
0x1800c56d1  mov     rdx, [rbp+40h+hObject]; void *
0x1800c56d5  lea     r9, [rsp+140h+var_E0]; struct _TOKEN_DEFAULT_DACL **
0x1800c56da  lea     r8, [rbp+40h+pSourceSid]; struct _SID *
0x1800c56de  call    ?AdjustDefaultTokenDacl@RestrictedToken@@AEAAJPEAXPEAU_SID@@PEAPEAU_TOKEN_DEFAULT_DACL@@@Z; RestrictedToken::AdjustDefaultTokenDacl(void *,_SID *,_TOKEN_DEFAULT_DACL * *)
0x1800c56e3  mov     r9d, eax
0x1800c56e6  test    eax, eax
0x1800c56e8  jns     short loc_1800C56F7
0x1800c56ea  mov     [rsp+140h+var_EC], 6Fh ; 'o'
0x1800c56f2  jmp     loc_1800C55EF
0x1800c56f7  mov     rdx, [rbp+40h+hObject]; void *
0x1800c56fb  call    ?AdjustTokenLowIntegrity@RestrictedToken@@AEAAJPEAX@Z; RestrictedToken::AdjustTokenLowIntegrity(void *)
0x1800c5700  mov     r9d, eax
0x1800c5703  test    eax, eax
0x1800c5705  jns     short loc_1800C5714
0x1800c5707  mov     [rsp+140h+var_EC], 71h ; 'q'
0x1800c570f  jmp     loc_1800C55EF
0x1800c5714  xor     edx, edx; Val
0x1800c5716  mov     rcx, rdi; void *
0x1800c5719  lea     r8d, [rdx+44h]; Size
0x1800c571d  call    memset_0
0x1800c5722  lea     r8, [rbp+40h+pSourceSid]; pSourceSid
0x1800c5726  mov     rdx, rdi; pDestinationSid
0x1800c5729  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800c572e  call    cs:__imp_CopySid
0x1800c5734  test    eax, eax
0x1800c5736  jnz     short loc_1800C576C
0x1800c5738  call    cs:__imp_GetLastError
0x1800c573e  mov     r9d, eax
0x1800c5741  test    eax, eax
0x1800c5743  jle     short loc_1800C5750
0x1800c5745  movzx   r9d, ax
0x1800c5749  or      r9d, 80070000h
0x1800c5750  test    r9d, r9d
0x1800c5753  js      short loc_1800C575F
0x1800c5755  mov     edi, 8000FFFFh
0x1800c575a  mov     r9d, edi
0x1800c575d  jmp     short loc_1800C5762
0x1800c575f  mov     edi, r9d
0x1800c5762  mov     [rsp+140h+var_EC], 78h ; 'x'
0x1800c576a  jmp     short loc_1800C5791
0x1800c576c  mov     rax, [rbp+40h+hObject]
0x1800c5770  mov     r9d, esi
0x1800c5773  mov     cs:hObject, rax
0x1800c577a  mov     edi, esi
0x1800c577c  mov     rax, [rsp+140h+var_E0]
0x1800c5781  mov     cs:qword_180108038, rax
0x1800c5788  mov     [rbp+40h+hObject], rsi
0x1800c578c  mov     [rsp+140h+var_E0], rsi
0x1800c5791  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c5798  jz      short loc_1800C57B0
0x1800c579a  mov     edx, 0Dh
0x1800c579f  lea     r8, WPP_b2d3439b2da8312dd5fe5cee5a4ad0c0_Traceguids
0x1800c57a6  mov     ecx, 405h
0x1800c57ab  call    WPP_SF_d
0x1800c57b0  cmp     [rsp+140h+var_E0], rsi
0x1800c57b5  jz      short loc_1800C57C1
0x1800c57b7  lea     rcx, [rsp+140h+var_E0]
0x1800c57bc  call    WxFreeHeapEx
0x1800c57c1  cmp     [rsp+140h+SidsToDisable], rsi
0x1800c57c6  jz      short loc_1800C57D2
0x1800c57c8  lea     rcx, [rsp+140h+SidsToDisable]
0x1800c57cd  call    WxFreeHeapEx
0x1800c57d2  cmp     [rsp+140h+var_C8], rsi
0x1800c57d7  jz      short loc_1800C57E3
0x1800c57d9  lea     rcx, [rsp+140h+var_C8]
0x1800c57de  call    WxFreeHeapEx
0x1800c57e3  cmp     [rsp+140h+ExistingTokenHandle], rsi
0x1800c57e8  jz      short loc_1800C57F5
0x1800c57ea  mov     rcx, [rsp+140h+ExistingTokenHandle]; hObject
0x1800c57ef  call    cs:__imp_CloseHandle
0x1800c57f5  mov     rcx, [rbp+40h+hObject]; hObject
0x1800c57f9  test    rcx, rcx
0x1800c57fc  jz      short loc_1800C5804
0x1800c57fe  call    cs:__imp_CloseHandle
0x1800c5804  mov     eax, edi
0x1800c5806  mov     rcx, [rbp+40h+var_10]
0x1800c580a  xor     rcx, rsp; StackCookie
0x1800c580d  call    __security_check_cookie
0x1800c5812  lea     r11, [rsp+140h+var_s0]
0x1800c581a  mov     rsi, [r11+10h]
0x1800c581e  mov     rdi, [r11+18h]
0x1800c5822  mov     rsp, r11
0x1800c5825  pop     rbp
0x1800c5826  retn
```
