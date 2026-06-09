# IsRedirectToBrokerNeededInternal(ushort const *,tagRedirectionPolicyFlags const *)

- ea: `0x18011b300`
- end: `0x18011b516`
- name: `?IsRedirectToBrokerNeededInternal@@YAJPEBGPEBUtagRedirectionPolicyFlags@@@Z`
- size: `534`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, const struct tagRedirectionPolicyFlags *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180082fa0`

## callees

- `0x180090024`
- `0x1800a1830`
- `0x1800af5b0`
- `0x180113b00`
- `0x18011adac`
- `0x18011b300`
- `0x18011bb30`
- `0x180126edc`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b34b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b369`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b3d3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b409`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b41e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b450`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b34b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b369`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b3d3`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b409`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b41e`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18011b450`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011b318`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011b49b`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011b318`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18011b49b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18011b4cf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18011b4cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18011b4f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18011b4f9`

## pseudocode

```c
_BOOL8 __fastcall IsRedirectToBrokerNeededInternal(WCHAR *a1, const struct tagRedirectionPolicyFlags *a2)
{
  BOOL v4; // ebx
  unsigned int v5; // edx
  int v6; // eax
  OLECHAR *v7; // rdi
  char Bool; // al
  unsigned int v9; // ebx
  bool v10; // zf
  char *CurrentEnterpriseID; // rax
  signed __int64 v12; // r8
  int v13; // edx
  int v14; // ecx
  bool v15; // zf
  BrowserUtilEdp *v16; // rcx
  unsigned int CurrentProcessManager; // ebx
  int v19; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v21; // [rsp+70h] [rbp+18h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+20h] BYREF

  if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      133,
      (__int64)"onecoreuap\\inetcore\\urlmon\\urlpolicy\\lcieurlpolicy.cpp",
      (const char *)0x80004001LL,
      v19);
  if ( (unsigned __int8)IEConfiguration_GetBool(268435482)
    || (v4 = 1, (unsigned __int8)IEConfiguration_GetBool(268435481)) )
  {
    v5 = *(unsigned __int8 *)a2;
    bstrString = 0;
    v21 = 0;
    v6 = LCIEGetRedirectionPolicyForURLInternal(a1, v5, 1u, 45056, &v21, 0, &bstrString);
    v7 = bstrString;
    v4 = v6;
    if ( v6 < 0 )
    {
LABEL_28:
      SysFreeString(v7);
      return v4;
    }
    Bool = IEConfiguration_GetBool(268435526);
    v9 = v21;
    if ( Bool || (((unsigned __int8)v9 ^ (unsigned __int8)IsoGetIntegrity(1u)) & 0x7F) == 0 )
    {
      if ( (v9 & 0x300000) == 0
        || (unsigned __int8)IEConfiguration_GetBool(536870913)
        || (unsigned __int8)IEConfiguration_GetBool(536870923)
        || (!IsOs_Wow6432() ? (v10 = (v9 & 0x100000) == 0) : (v10 = (v9 & 0x200000) == 0), v10) )
      {
        if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
        {
LABEL_26:
          CurrentProcessManager = IsoGetCurrentProcessManager();
          InitOnceExecuteOnce(&g_InitOnce, (PINIT_ONCE_FN)LoadIsoDll, 0, 0);
          v4 = ((__int64 (__fastcall *)(_QWORD, __int64))qword_1801810E0)(CurrentProcessManager, 1) != 0;
          goto LABEL_28;
        }
        CurrentEnterpriseID = (char *)GetCurrentEnterpriseID();
        if ( v7 )
        {
          if ( !CurrentEnterpriseID )
            goto LABEL_27;
          v12 = (char *)v7 - CurrentEnterpriseID;
          do
          {
            v13 = *(unsigned __int16 *)&CurrentEnterpriseID[v12];
            v14 = *(unsigned __int16 *)CurrentEnterpriseID - v13;
            if ( v14 )
              break;
            CurrentEnterpriseID += 2;
          }
          while ( v13 );
          v15 = v14 == 0;
        }
        else
        {
          v15 = CurrentEnterpriseID == 0;
        }
        if ( v15 && (!(unsigned int)IEConfiguration_GetDWORD(536870929) || BrowserUtilEdp::IsEdpEnforcementEnabled(v16)) )
          goto LABEL_26;
      }
    }
LABEL_27:
    v4 = 0;
    goto LABEL_28;
  }
  return v4;
}

```

## disassembly

```asm
0x18011b300  mov     [rsp+arg_0], rbx
0x18011b305  push    rsi
0x18011b306  push    rdi
0x18011b307  push    r14
0x18011b309  sub     rsp, 40h
0x18011b30d  mov     rsi, rcx
0x18011b310  mov     rdi, rdx
0x18011b313  mov     ecx, 1000002Dh
0x18011b318  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18011b31f  nop     dword ptr [rax+rax+00h]
0x18011b324  cmp     eax, 2
0x18011b327  jnz     short loc_18011B346
0x18011b329  mov     rcx, [rsp+58h]; this
0x18011b32e  lea     r8, aOnecoreuapInet_2; "onecoreuap\\inetcore\\urlmon\\urlpolicy"...
0x18011b335  mov     r9d, 80004001h; char *
0x18011b33b  mov     edx, 85h; void *
0x18011b340  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18011b346  mov     ecx, 1000001Ah
0x18011b34b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011b352  nop     dword ptr [rax+rax+00h]
0x18011b357  mov     r14d, 1
0x18011b35d  test    al, al
0x18011b35f  jnz     short loc_18011B37D
0x18011b361  mov     ecx, 10000019h
0x18011b366  mov     ebx, r14d
0x18011b369  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011b370  nop     dword ptr [rax+rax+00h]
0x18011b375  test    al, al
0x18011b377  jz      loc_18011B505
0x18011b37d  movzx   edx, byte ptr [rdi]; int
0x18011b380  lea     rax, [rsp+58h+bstrString]
0x18011b385  mov     [rsp+58h+var_28], rax; unsigned __int16 **
0x18011b38a  mov     r9d, 0B000h; unsigned int
0x18011b390  lea     rax, [rsp+58h+arg_10]
0x18011b395  mov     [rsp+58h+var_30], 0; int *
0x18011b39e  mov     r8d, r14d; int
0x18011b3a1  mov     [rsp+58h+var_38], rax; unsigned int *
0x18011b3a6  mov     rcx, rsi; pwzURI
0x18011b3a9  mov     [rsp+58h+bstrString], 0
0x18011b3b2  mov     [rsp+58h+arg_10], 0
0x18011b3ba  call    ?LCIEGetRedirectionPolicyForURLInternal@@YAJPEBGHHKPEAKPEAHPEAPEAG@Z; LCIEGetRedirectionPolicyForURLInternal(ushort const *,int,int,ulong,ulong *,int *,ushort * *)
0x18011b3bf  mov     rdi, [rsp+58h+bstrString]
0x18011b3c4  mov     ebx, eax
0x18011b3c6  test    eax, eax
0x18011b3c8  js      loc_18011B4F6
0x18011b3ce  mov     ecx, 10000046h
0x18011b3d3  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011b3da  nop     dword ptr [rax+rax+00h]
0x18011b3df  mov     ebx, [rsp+58h+arg_10]
0x18011b3e3  test    al, al
0x18011b3e5  jnz     short loc_18011B3F9
0x18011b3e7  mov     ecx, r14d
0x18011b3ea  call    ?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x18011b3ef  xor     eax, ebx
0x18011b3f1  test    al, 7Fh
0x18011b3f3  jnz     loc_18011B4F4
0x18011b3f9  mov     esi, r14d
0x18011b3fc  test    ebx, 300000h
0x18011b402  jz      short loc_18011B44B
0x18011b404  mov     ecx, 20000001h
0x18011b409  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011b410  nop     dword ptr [rax+rax+00h]
0x18011b415  test    al, al
0x18011b417  jnz     short loc_18011B44B
0x18011b419  mov     ecx, 2000000Bh
0x18011b41e  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011b425  nop     dword ptr [rax+rax+00h]
0x18011b42a  test    al, al
0x18011b42c  jnz     short loc_18011B44B
0x18011b42e  call    ?IsOs_Wow6432@@YA_NXZ; IsOs_Wow6432(void)
0x18011b433  test    al, al
0x18011b435  jz      short loc_18011B43F
0x18011b437  test    ebx, 200000h
0x18011b43d  jmp     short loc_18011B445
0x18011b43f  test    ebx, 100000h
0x18011b445  jnz     loc_18011B4F4
0x18011b44b  mov     ecx, 20000001h
0x18011b450  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18011b457  nop     dword ptr [rax+rax+00h]
0x18011b45c  test    al, al
0x18011b45e  jnz     short loc_18011B4B4
0x18011b460  call    GetCurrentEnterpriseID
0x18011b465  test    rdi, rdi
0x18011b468  jz      short loc_18011B491
0x18011b46a  test    rax, rax
0x18011b46d  jz      loc_18011B4F4
0x18011b473  mov     r8, rdi
0x18011b476  sub     r8, rax
0x18011b479  movzx   ecx, word ptr [rax]
0x18011b47c  movzx   edx, word ptr [rax+r8]
0x18011b481  sub     ecx, edx
0x18011b483  jnz     short loc_18011B48D
0x18011b485  add     rax, 2
0x18011b489  test    edx, edx
0x18011b48b  jnz     short loc_18011B479
0x18011b48d  test    ecx, ecx
0x18011b48f  jmp     short loc_18011B494
0x18011b491  test    rax, rax
0x18011b494  jnz     short loc_18011B4F4
0x18011b496  mov     ecx, 20000011h
0x18011b49b  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18011b4a2  nop     dword ptr [rax+rax+00h]
0x18011b4a7  test    eax, eax
0x18011b4a9  jz      short loc_18011B4B4
0x18011b4ab  call    ?IsEdpEnforcementEnabled@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpEnforcementEnabled(void)
0x18011b4b0  test    al, al
0x18011b4b2  jz      short loc_18011B4F4
0x18011b4b4  call    ?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x18011b4b9  xor     r9d, r9d; Context
0x18011b4bc  lea     rdx, ?LoadIsoDll@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18011b4c3  xor     r8d, r8d; Parameter
0x18011b4c6  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18011b4cd  mov     ebx, eax
0x18011b4cf  call    cs:__imp_InitOnceExecuteOnce
0x18011b4d6  nop     dword ptr [rax+rax+00h]
0x18011b4db  mov     rax, cs:qword_1801810E0
0x18011b4e2  mov     edx, r14d
0x18011b4e5  mov     ecx, ebx
0x18011b4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011b4ec  neg     eax
0x18011b4ee  sbb     ebx, ebx
0x18011b4f0  and     ebx, esi
0x18011b4f2  jmp     short loc_18011B4F6
0x18011b4f4  xor     ebx, ebx
0x18011b4f6  mov     rcx, rdi; bstrString
0x18011b4f9  call    cs:__imp_SysFreeString
0x18011b500  nop     dword ptr [rax+rax+00h]
0x18011b505  mov     eax, ebx
0x18011b507  mov     rbx, [rsp+58h+arg_0]
0x18011b50c  add     rsp, 40h
0x18011b510  pop     r14
0x18011b512  pop     rdi
0x18011b513  pop     rsi
0x18011b514  retn
```
