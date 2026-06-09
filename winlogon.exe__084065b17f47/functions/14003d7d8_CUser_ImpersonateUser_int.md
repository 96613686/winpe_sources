# CUser::ImpersonateUser(int)

- ea: `0x14003d7d8`
- end: `0x14003d95d`
- name: `?ImpersonateUser@CUser@@QEAAKH@Z`
- size: `389`
- prototype: `unsigned int __fastcall(CUser *__hidden this, int)`
- caller_count: `23`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140008a20`
- `0x1400106bc`
- `0x1400176f8`
- `0x14002d9a4`
- `0x1400402b8`
- `0x140047370`
- `0x14004c400`
- `0x14004ce68`
- `0x1400500f0`
- `0x140052c20`
- `0x14005c85c`
- `0x14005f4e8`
- `0x1400625d0`
- `0x140063660`
- `0x140063ba0`
- `0x1400640c0`
- `0x14006a184`
- `0x14006e220`
- `0x14006e950`
- `0x140071140`
- `0x1400714b0`
- `0x1400735b4`
- `0x14008a85c`

## callees

- `0x1400057f4`
- `0x14003d7d8`
- `0x140041c34`
- `0x14004f03c`
- `0x14009c5b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d910`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003d866`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003d906`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003d866`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14003d906`
- `ntdll!NtClose` at `0x14003d8b6`
- `ntdll!NtClose` at `0x14003d8b6`

## pseudocode

```c
__int64 __fastcall CUser::ImpersonateUser(CUser *this, int a2)
{
  HANDLE v2; // rdi
  DWORD v5; // esi
  __int64 v6; // r9
  __int64 v7; // r9
  DWORD LastError; // eax
  DWORD v9; // eax
  HANDLE Handle; // [rsp+40h] [rbp+8h] BYREF

  v2 = (HANDLE)*((_QWORD *)this + 17);
  v5 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
  {
    Handle = 0;
    if ( a2 && !(unsigned int)AicGetElevatedToken(*((void **)this + 17), &Handle) )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v7);
      }
      v2 = Handle;
    }
    if ( !ImpersonateLoggedOnUser(v2) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, LastError);
      }
    }
    if ( Handle )
      NtClose(Handle);
  }
  else
  {
    if ( a2 && *((_QWORD *)this + 18) )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v6);
      }
      v2 = (HANDLE)*((_QWORD *)this + 18);
    }
    if ( !ImpersonateLoggedOnUser(v2) )
    {
      v9 = GetLastError();
      v5 = v9;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v9);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14003d7d8  mov     [rsp+arg_8], rbx
0x14003d7dd  mov     [rsp+arg_10], rbp
0x14003d7e2  push    rsi
0x14003d7e3  push    rdi
0x14003d7e4  push    r14
0x14003d7e6  sub     rsp, 20h
0x14003d7ea  mov     rdi, [rcx+88h]
0x14003d7f1  mov     r14d, edx
0x14003d7f4  mov     rbp, rcx
0x14003d7f7  xor     esi, esi
0x14003d7f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x14003d800  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x14003d805  lea     rbx, WPP_GLOBAL_Control
0x14003d80c  test    al, al
0x14003d80e  jz      loc_14003D8C1
0x14003d814  mov     [rsp+38h+Handle], rsi
0x14003d819  test    r14d, r14d
0x14003d81c  jz      short loc_14003D863
0x14003d81e  mov     rcx, [rbp+88h]; void *
0x14003d825  lea     rdx, [rsp+38h+Handle]; void **
0x14003d82a  call    ?AicGetElevatedToken@@YAJPEAXPEAPEAX@Z; AicGetElevatedToken(void *,void * *)
0x14003d82f  test    eax, eax
0x14003d831  jnz     short loc_14003D863
0x14003d833  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d83a  cmp     rcx, rbx
0x14003d83d  jz      short loc_14003D85E
0x14003d83f  test    byte ptr [rcx+1Ch], 20h
0x14003d843  jz      short loc_14003D85E
0x14003d845  cmp     byte ptr [rcx+19h], 5
0x14003d849  jb      short loc_14003D85E
0x14003d84b  mov     rcx, [rcx+10h]
0x14003d84f  lea     edx, [rsi+18h]
0x14003d852  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003d859  call    WPP_SF_
0x14003d85e  mov     rdi, [rsp+38h+Handle]
0x14003d863  mov     rcx, rdi; hToken
0x14003d866  call    cs:__imp_ImpersonateLoggedOnUser
0x14003d86c  test    eax, eax
0x14003d86e  jnz     short loc_14003D8A8
0x14003d870  call    cs:__imp_GetLastError
0x14003d876  mov     esi, eax
0x14003d878  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d87f  cmp     rcx, rbx
0x14003d882  jz      short loc_14003D8A8
0x14003d884  test    byte ptr [rcx+1Ch], 20h
0x14003d888  jz      short loc_14003D8A8
0x14003d88a  cmp     byte ptr [rcx+19h], 2
0x14003d88e  jb      short loc_14003D8A8
0x14003d890  mov     rcx, [rcx+10h]
0x14003d894  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003d89b  mov     edx, 19h
0x14003d8a0  mov     r9d, eax
0x14003d8a3  call    WPP_SF_d
0x14003d8a8  mov     rcx, [rsp+38h+Handle]; Handle
0x14003d8ad  test    rcx, rcx
0x14003d8b0  jz      loc_14003D948
0x14003d8b6  call    cs:__imp_NtClose
0x14003d8bc  jmp     loc_14003D948
0x14003d8c1  test    r14d, r14d
0x14003d8c4  jz      short loc_14003D903
0x14003d8c6  cmp     [rbp+90h], rsi
0x14003d8cd  jz      short loc_14003D903
0x14003d8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d8d6  cmp     rcx, rbx
0x14003d8d9  jz      short loc_14003D8FC
0x14003d8db  test    byte ptr [rcx+1Ch], 20h
0x14003d8df  jz      short loc_14003D8FC
0x14003d8e1  cmp     byte ptr [rcx+19h], 5
0x14003d8e5  jb      short loc_14003D8FC
0x14003d8e7  mov     rcx, [rcx+10h]
0x14003d8eb  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003d8f2  mov     edx, 1Ah
0x14003d8f7  call    WPP_SF_
0x14003d8fc  mov     rdi, [rbp+90h]
0x14003d903  mov     rcx, rdi; hToken
0x14003d906  call    cs:__imp_ImpersonateLoggedOnUser
0x14003d90c  test    eax, eax
0x14003d90e  jnz     short loc_14003D948
0x14003d910  call    cs:__imp_GetLastError
0x14003d916  mov     esi, eax
0x14003d918  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d91f  cmp     rcx, rbx
0x14003d922  jz      short loc_14003D948
0x14003d924  test    byte ptr [rcx+1Ch], 20h
0x14003d928  jz      short loc_14003D948
0x14003d92a  cmp     byte ptr [rcx+19h], 2
0x14003d92e  jb      short loc_14003D948
0x14003d930  mov     rcx, [rcx+10h]
0x14003d934  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14003d93b  mov     edx, 1Bh
0x14003d940  mov     r9d, eax
0x14003d943  call    WPP_SF_d
0x14003d948  mov     rbx, [rsp+38h+arg_8]
0x14003d94d  mov     eax, esi
0x14003d94f  mov     rbp, [rsp+38h+arg_10]
0x14003d954  add     rsp, 20h
0x14003d958  pop     r14
0x14003d95a  pop     rdi
0x14003d95b  pop     rsi
0x14003d95c  retn
```
