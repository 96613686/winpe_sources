# WcmPolicyManager::UpdatePolicy(IWcmConnectionMappingPolicyKey *,IWcmConnectionMappingPolicyData *)

- ea: `0x180008010`
- end: `0x1800085c2`
- name: `?UpdatePolicy@WcmPolicyManager@@UEAAJPEAUIWcmConnectionMappingPolicyKey@@PEAUIWcmConnectionMappingPolicyData@@@Z`
- size: `1458`
- prototype: `int(WcmPolicyManager *__hidden this, struct IWcmConnectionMappingPolicyKey *, struct IWcmConnectionMappingPolicyData *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180004d10`
- `0x1800060e8`
- `0x180006b4c`
- `0x1800075e8`
- `0x180007a70`
- `0x180008010`
- `0x1800085c8`
- `0x180008a90`
- `0x18000bd50`
- `0x18000c264`
- `0x1800111dc`
- `0x180015424`
- `0x18001728c`
- `0x1800172ec`
- `0x180017a60`
- `0x180017b50`
- `0x180017cb0`
- `0x180017dac`
- `0x180017ec8`
- `0x180018b14`
- `0x18001aa44`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000812e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000812e`

## string_xrefs

- `0x180008060`: `WcmPolicyManager::UpdatePolicy`
- `0x18000854e`: `WcmPolicyManager::UpdatePolicy`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall WcmPolicyManager::UpdatePolicy(
        WcmPolicyManager *this,
        struct IWcmConnectionMappingPolicyKey *a2,
        struct IWcmConnectionMappingPolicyData *a3)
{
  int v5; // eax
  signed int v6; // ebx
  WcmPolicyManager *v7; // rcx
  __int64 (__fastcall *v8)(struct IWcmConnectionMappingPolicyData *, LPVOID *); // rsi
  void *v9; // rbx
  int v10; // eax
  int PolicySourceRegKey; // eax
  unsigned __int16 *v12; // r9
  int v13; // esi
  int v14; // eax
  unsigned int v16; // [rsp+20h] [rbp-C8h]
  unsigned int v17; // [rsp+28h] [rbp-C0h]
  struct _SECURITY_ATTRIBUTES *v18; // [rsp+30h] [rbp-B8h]
  unsigned int *v19; // [rsp+38h] [rbp-B0h]
  int v20; // [rsp+40h] [rbp-A8h] BYREF
  int v21; // [rsp+48h] [rbp-A0h]
  HKEY hKey[2]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v23; // [rsp+60h] [rbp-88h]
  __int128 v24; // [rsp+68h] [rbp-80h] BYREF
  __int64 v25; // [rsp+78h] [rbp-70h]
  char v26[4]; // [rsp+80h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-60h] BYREF
  _BYTE v28[32]; // [rsp+90h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      "WcmPolicyManager::UpdatePolicy");
  }
  hKey[0] = 0;
  hKey[1] = 0;
  v23 = 0;
  v24 = 0u;
  v25 = 0;
  std::wstring::wstring(v28);
  v21 = 0;
  *(_DWORD *)v26 = 0;
  pv = 0;
  v5 = (*(__int64 (__fastcall **)(struct IWcmConnectionMappingPolicyData *, char *))(*(_QWORD *)a3 + 48LL))(a3, v26);
  v6 = v5;
  if ( v5 < 0 )
  {
    v20 = v5;
    v7 = WPP_GLOBAL_Control;
    goto LABEL_64;
  }
  if ( *(_DWORD *)v26 && *(int *)v26 < 7 )
  {
    v8 = *(__int64 (__fastcall **)(struct IWcmConnectionMappingPolicyData *, LPVOID *))(*(_QWORD *)a3 + 32LL);
    v9 = pv;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
      CoTaskMemFree(v9);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
    }
    pv = 0;
    v10 = v8(a3, &pv);
    v6 = v10;
    if ( v10 < 0 )
    {
      v20 = v10;
      v7 = WPP_GLOBAL_Control;
      goto LABEL_64;
    }
    if ( pv && *(_WORD *)pv )
    {
      if ( *((_QWORD *)a3 + 10) - *((_QWORD *)a3 + 9) < 0x10u )
      {
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids);
        }
        v6 = -2147024809;
        v20 = -2147024809;
        ReportApplicationError(-2147024809, 0x8Fu);
        v7 = WPP_GLOBAL_Control;
        goto LABEL_64;
      }
      PolicySourceRegKey = OpenOrCreatePolicySourceRegKey(*(unsigned int *)v26, hKey, 1);
      v6 = PolicySourceRegKey;
      if ( PolicySourceRegKey < 0 )
      {
        v20 = PolicySourceRegKey;
        v7 = WPP_GLOBAL_Control;
        goto LABEL_64;
      }
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)&v24, hKey[0], (LPCWSTR)pv, 0xF003Fu) )
      {
        v13 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, (const unsigned __int16 *)pv);
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25)
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)pv, v26[0]);
          }
          if ( v13 > 0 )
            v6 = (unsigned __int16)v13 | 0x80070000;
          else
            v6 = v13;
          v20 = v6;
          ReportApplicationError(v13, 0xADu);
          v7 = WPP_GLOBAL_Control;
          goto LABEL_64;
        }
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
            (_DWORD)pv,
            v26[0]);
        }
        v21 = 1;
      }
      v6 = ATL::CRegKey::Create((ATL::CRegKey *)&v24, hKey[0], (LPCWSTR)pv, v12, v16, v17, v18, v19);
      if ( v6 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)pv, v26[0]);
          v7 = WPP_GLOBAL_Control;
        }
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        v20 = v6;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
            (_DWORD)pv,
            v26[0]);
        }
        v21 = 1;
        v14 = WcmConnectionMappingPolicyKey::WriteToRegistry(a2, (struct ATL::CRegKey *)&v24);
        v6 = v14;
        if ( v14 >= 0 )
        {
          v6 = WcmConnectionMappingPolicyData::WriteToRegistry(a3, (struct ATL::CRegKey *)&v24);
          v20 = v6;
          if ( v6 >= 0 )
          {
LABEL_72:
            WcmPolicyManager::SignalPolicyChange(v7);
            v7 = WPP_GLOBAL_Control;
            goto LABEL_73;
          }
          v7 = WPP_GLOBAL_Control;
        }
        else
        {
          v20 = v14;
          v7 = WPP_GLOBAL_Control;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      v6 = -2147024809;
      v20 = -2147024809;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
        *(unsigned int *)v26);
      v7 = WPP_GLOBAL_Control;
    }
    v6 = -2147024809;
    v20 = -2147024809;
  }
LABEL_64:
  if ( pv && hKey[0] )
  {
    if ( v7 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) && (*((_BYTE *)v7 + 28) & 1) != 0 )
      WPP_SF_dS(*((_QWORD *)v7 + 2), (__int64)pv);
    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, (const unsigned __int16 *)pv);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v21 )
    goto LABEL_72;
LABEL_73:
  if ( v7 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 5u && (*((_BYTE *)v7 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v7 + 2),
      23,
      (unsigned int)&WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids,
      (unsigned int)"WcmPolicyManager::UpdatePolicy",
      v6);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
  std::wstring::_Tidy_deallocate(v28);
  ATL::CRegKey::Close((ATL::CRegKey *)&v24);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008010  mov     [rsp+arg_0], rbx
0x180008015  push    rsi
0x180008016  push    rdi
0x180008017  push    r12
0x180008019  push    r14
0x18000801b  push    r15
0x18000801d  sub     rsp, 0C0h
0x180008024  mov     rax, cs:__security_cookie
0x18000802b  xor     rax, rsp
0x18000802e  mov     [rsp+0E8h+var_38], rax
0x180008036  mov     r15, r8
0x180008039  mov     r12, rdx
0x18000803c  lea     r14, WPP_GLOBAL_Control
0x180008043  mov     rcx, cs:WPP_GLOBAL_Control
0x18000804a  cmp     rcx, r14
0x18000804d  jz      short loc_180008077
0x18000804f  cmp     byte ptr [rcx+19h], 5
0x180008053  jb      short loc_180008077
0x180008055  test    byte ptr [rcx+1Ch], 1
0x180008059  jz      short loc_180008077
0x18000805b  mov     edx, 0Eh
0x180008060  lea     r9, aWcmpolicymanag_3; "WcmPolicyManager::UpdatePolicy"
0x180008067  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x18000806e  mov     rcx, [rcx+10h]
0x180008072  call    WPP_SF_s
0x180008077  xorps   xmm0, xmm0
0x18000807a  movups  xmmword ptr [rsp+0E8h+hKey], xmm0
0x18000807f  xor     edi, edi
0x180008081  mov     [rsp+0E8h+hKey], rdi
0x180008086  mov     [rsp+0E8h+hKey+8], rdi
0x18000808b  mov     [rsp+0E8h+var_88], rdi
0x180008090  movups  [rsp+0E8h+var_80], xmm0
0x180008095  mov     qword ptr [rsp+0E8h+var_80], rdi
0x18000809a  mov     qword ptr [rsp+0E8h+var_80+8], rdi
0x18000809f  mov     [rsp+0E8h+var_70], rdi
0x1800080a4  lea     rcx, [rsp+0E8h+var_58]
0x1800080ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800080b1  nop
0x1800080b2  mov     [rsp+0E8h+var_A0], edi
0x1800080b6  mov     dword ptr [rsp+0E8h+var_68], edi
0x1800080bd  mov     [rsp+0E8h+pv], rdi
0x1800080c5  mov     rax, [r15]
0x1800080c8  lea     rdx, [rsp+0E8h+var_68]
0x1800080d0  mov     rcx, r15
0x1800080d3  mov     rax, [rax+30h]
0x1800080d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080dc  mov     ebx, eax
0x1800080de  test    eax, eax
0x1800080e0  jns     short loc_1800080F2
0x1800080e2  mov     [rsp+0E8h+var_A8], eax
0x1800080e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080ed  jmp     loc_1800084C2
0x1800080f2  mov     r9d, dword ptr [rsp+0E8h+var_68]
0x1800080fa  test    r9d, r9d
0x1800080fd  jz      loc_18000846D
0x180008103  cmp     r9d, 7
0x180008107  jge     loc_18000846D
0x18000810d  mov     rax, [r15]
0x180008110  mov     rsi, [rax+20h]
0x180008114  mov     rbx, [rsp+0E8h+pv]
0x18000811c  test    rbx, rbx
0x18000811f  jz      short loc_180008144
0x180008121  lea     rcx, [rsp+0E8h+var_A8]; this
0x180008126  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000812b  mov     rcx, rbx; pv
0x18000812e  call    cs:__imp_CoTaskMemFree
0x180008135  nop     dword ptr [rax+rax+00h]
0x18000813a  lea     rcx, [rsp+0E8h+var_A8]; this
0x18000813f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008144  mov     [rsp+0E8h+pv], rdi
0x18000814c  lea     rdx, [rsp+0E8h+pv]
0x180008154  mov     rcx, r15
0x180008157  mov     rax, rsi
0x18000815a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000815f  mov     ebx, eax
0x180008161  test    eax, eax
0x180008163  jns     short loc_180008175
0x180008165  mov     [rsp+0E8h+var_A8], eax
0x180008169  mov     rcx, cs:WPP_GLOBAL_Control
0x180008170  jmp     loc_1800084C2
0x180008175  mov     rax, [rsp+0E8h+pv]
0x18000817d  test    rax, rax
0x180008180  jz      loc_18000842E
0x180008186  cmp     [rax], di
0x180008189  jz      loc_18000842E
0x18000818f  mov     rax, [r15+50h]
0x180008193  sub     rax, [r15+48h]
0x180008197  cmp     rax, 10h
0x18000819b  jnb     short loc_1800081EC
0x18000819d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081a4  cmp     rcx, r14
0x1800081a7  jz      short loc_1800081CA
0x1800081a9  cmp     byte ptr [rcx+19h], 1
0x1800081ad  jb      short loc_1800081CA
0x1800081af  test    byte ptr [rcx+1Ch], 1
0x1800081b3  jz      short loc_1800081CA
0x1800081b5  mov     edx, 11h
0x1800081ba  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800081c1  mov     rcx, [rcx+10h]
0x1800081c5  call    WPP_SF_
0x1800081ca  mov     ebx, 80070057h
0x1800081cf  mov     [rsp+0E8h+var_A8], ebx
0x1800081d3  mov     edx, 8Fh; unsigned int
0x1800081d8  mov     ecx, ebx; int
0x1800081da  call    ?ReportApplicationError@@YAXJK@Z; ReportApplicationError(long,ulong)
0x1800081df  nop
0x1800081e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081e7  jmp     loc_1800084C2
0x1800081ec  mov     r8d, 1
0x1800081f2  lea     rdx, [rsp+0E8h+hKey]
0x1800081f7  mov     ecx, dword ptr [rsp+0E8h+var_68]
0x1800081fe  call    ?OpenOrCreatePolicySourceRegKey@@YAJW4WCM_POLICY_SOURCE@@AEAVCRegKey@ATL@@H@Z; OpenOrCreatePolicySourceRegKey(WCM_POLICY_SOURCE,ATL::CRegKey &,int)
0x180008203  mov     ebx, eax
0x180008205  test    eax, eax
0x180008207  jns     short loc_180008219
0x180008209  mov     [rsp+0E8h+var_A8], eax
0x18000820d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008214  jmp     loc_1800084C2
0x180008219  mov     r9d, 0F003Fh; unsigned int
0x18000821f  mov     r8, [rsp+0E8h+pv]; lpSubKey
0x180008227  mov     rdx, [rsp+0E8h+hKey]; hKey
0x18000822c  lea     rcx, [rsp+0E8h+var_80]; this
0x180008231  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008236  test    eax, eax
0x180008238  jnz     loc_180008311
0x18000823e  mov     rdx, [rsp+0E8h+pv]; unsigned __int16 *
0x180008246  lea     rcx, [rsp+0E8h+hKey]; this
0x18000824b  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008250  mov     esi, eax
0x180008252  test    eax, eax
0x180008254  jnz     short loc_18000829E
0x180008256  mov     rcx, cs:WPP_GLOBAL_Control
0x18000825d  cmp     rcx, r14
0x180008260  jz      short loc_180008294
0x180008262  cmp     byte ptr [rcx+19h], 4
0x180008266  jb      short loc_180008294
0x180008268  test    byte ptr [rcx+1Ch], 1
0x18000826c  jz      short loc_180008294
0x18000826e  lea     edx, [rax+12h]
0x180008271  mov     eax, dword ptr [rsp+0E8h+var_68]
0x180008278  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18000827c  mov     r9, [rsp+0E8h+pv]
0x180008284  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x18000828b  mov     rcx, [rcx+10h]
0x18000828f  call    WPP_SF_SD
0x180008294  mov     [rsp+0E8h+var_A0], 1
0x18000829c  jmp     short loc_180008311
0x18000829e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082a5  cmp     rcx, r14
0x1800082a8  jz      short loc_1800082E6
0x1800082aa  cmp     byte ptr [rcx+19h], 1
0x1800082ae  jb      short loc_1800082E6
0x1800082b0  test    byte ptr [rcx+1Ch], 1
0x1800082b4  jz      short loc_1800082E6
0x1800082b6  mov     edx, 13h
0x1800082bb  mov     eax, dword ptr [rsp+0E8h+var_68]
0x1800082c2  mov     dword ptr [rsp+0E8h+var_C0], eax; char
0x1800082c6  mov     rax, [rsp+0E8h+pv]
0x1800082ce  mov     [rsp+0E8h+var_C8], rax; __int64
0x1800082d3  mov     r9d, esi
0x1800082d6  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800082dd  mov     rcx, [rcx+10h]; LoggerHandle
0x1800082e1  call    WPP_SF_DSD
0x1800082e6  test    esi, esi
0x1800082e8  jg      short loc_1800082EE
0x1800082ea  mov     ebx, esi
0x1800082ec  jmp     short loc_1800082F7
0x1800082ee  movzx   ebx, si
0x1800082f1  or      ebx, 80070000h
0x1800082f7  mov     [rsp+0E8h+var_A8], ebx
0x1800082fb  mov     edx, 0ADh; unsigned int
0x180008300  mov     ecx, esi; int
0x180008302  call    ?ReportApplicationError@@YAXJK@Z; ReportApplicationError(long,ulong)
0x180008307  nop
0x180008308  mov     rcx, cs:WPP_GLOBAL_Control
0x18000830f  jmp     short loc_18000838E
0x180008311  mov     r8, [rsp+0E8h+pv]; lpSubKey
0x180008319  mov     rdx, [rsp+0E8h+hKey]; hKey
0x18000831e  lea     rcx, [rsp+0E8h+var_80]; this
0x180008323  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180008328  mov     ebx, eax
0x18000832a  test    eax, eax
0x18000832c  jz      short loc_18000839B
0x18000832e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008335  cmp     rcx, r14
0x180008338  jz      short loc_18000837D
0x18000833a  cmp     byte ptr [rcx+19h], 1
0x18000833e  jb      short loc_18000837D
0x180008340  test    byte ptr [rcx+1Ch], 1
0x180008344  jz      short loc_18000837D
0x180008346  mov     edx, 14h
0x18000834b  mov     eax, dword ptr [rsp+0E8h+var_68]
0x180008352  mov     dword ptr [rsp+0E8h+var_C0], eax; char
0x180008356  mov     rax, [rsp+0E8h+pv]
0x18000835e  mov     [rsp+0E8h+var_C8], rax; __int64
0x180008363  mov     r9d, ebx
0x180008366  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x18000836d  mov     rcx, [rcx+10h]; LoggerHandle
0x180008371  call    WPP_SF_DSD
0x180008376  mov     rcx, cs:WPP_GLOBAL_Control
0x18000837d  test    ebx, ebx
0x18000837f  jle     short loc_18000838A
0x180008381  movzx   ebx, bx
0x180008384  or      ebx, 80070000h
0x18000838a  mov     [rsp+0E8h+var_A8], ebx
0x18000838e  test    ebx, ebx
0x180008390  jns     loc_180008522
0x180008396  jmp     loc_1800084C2
0x18000839b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083a2  cmp     rcx, r14
0x1800083a5  jz      short loc_1800083DB
0x1800083a7  cmp     byte ptr [rcx+19h], 4
0x1800083ab  jb      short loc_1800083DB
0x1800083ad  test    byte ptr [rcx+1Ch], 1
0x1800083b1  jz      short loc_1800083DB
0x1800083b3  mov     edx, 15h
0x1800083b8  mov     eax, dword ptr [rsp+0E8h+var_68]
0x1800083bf  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800083c3  mov     r9, [rsp+0E8h+pv]
0x1800083cb  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x1800083d2  mov     rcx, [rcx+10h]
0x1800083d6  call    WPP_SF_SD
0x1800083db  mov     [rsp+0E8h+var_A0], 1
0x1800083e3  lea     rdx, [rsp+0E8h+var_80]; struct ATL::CRegKey *
0x1800083e8  mov     rcx, r12; this
0x1800083eb  call    ?WriteToRegistry@WcmConnectionMappingPolicyKey@@QEAAJAEAVCRegKey@ATL@@@Z; WcmConnectionMappingPolicyKey::WriteToRegistry(ATL::CRegKey &)
0x1800083f0  mov     ebx, eax
0x1800083f2  test    eax, eax
0x1800083f4  jns     short loc_180008406
0x1800083f6  mov     [rsp+0E8h+var_A8], eax
0x1800083fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180008401  jmp     loc_1800084C2
0x180008406  lea     rdx, [rsp+0E8h+var_80]; struct ATL::CRegKey *
0x18000840b  mov     rcx, r15; this
0x18000840e  call    ?WriteToRegistry@WcmConnectionMappingPolicyData@@QEAAJAEAVCRegKey@ATL@@@Z; WcmConnectionMappingPolicyData::WriteToRegistry(ATL::CRegKey &)
0x180008413  mov     ebx, eax
0x180008415  mov     [rsp+0E8h+var_A8], eax
0x180008419  test    eax, eax
0x18000841b  jns     short loc_180008429
0x18000841d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008424  jmp     loc_1800084C2
0x180008429  jmp     loc_180008528
0x18000842e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008435  cmp     rcx, r14
0x180008438  jz      short loc_180008462
0x18000843a  cmp     byte ptr [rcx+19h], 1
0x18000843e  jb      short loc_180008462
0x180008440  test    byte ptr [rcx+1Ch], 1
0x180008444  jz      short loc_180008462
0x180008446  mov     edx, 10h
0x18000844b  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180008452  mov     rcx, [rcx+10h]
0x180008456  call    WPP_SF_
0x18000845b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008462  mov     ebx, 80070057h
0x180008467  mov     [rsp+0E8h+var_A8], ebx
0x18000846b  jmp     short loc_1800084C2
0x18000846d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008474  cmp     rcx, r14
0x180008477  jz      short loc_1800084A1
0x180008479  cmp     byte ptr [rcx+19h], 1
0x18000847d  jb      short loc_1800084A1
0x18000847f  test    byte ptr [rcx+1Ch], 1
0x180008483  jz      short loc_1800084A1
0x180008485  mov     edx, 0Fh
0x18000848a  lea     r8, WPP_e361afbbe43e38e97487f8259bfc2794_Traceguids
0x180008491  mov     rcx, [rcx+10h]
0x180008495  call    WPP_SF_D
0x18000849a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084a1  mov     ebx, 80070057h
0x1800084a6  mov     [rsp+0E8h+var_A8], ebx
0x1800084aa  jmp     short loc_1800084C2
0x1800084ac  jmp     short $+2
0x1800084ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084b5  mov     ebx, [rsp+0E8h+var_A8]
0x1800084b9  xor     edi, edi
0x1800084bb  lea     r14, WPP_GLOBAL_Control
0x1800084c2  mov     rax, [rsp+0E8h+pv]
0x1800084ca  test    rax, rax
0x1800084cd  jz      short loc_180008522
0x1800084cf  cmp     [rsp+0E8h+hKey], rdi
0x1800084d4  jz      short loc_180008522
0x1800084d6  cmp     rcx, r14
0x1800084d9  jz      short loc_1800084F9
0x1800084db  cmp     byte ptr [rcx+19h], 1
0x1800084df  jb      short loc_1800084F9
0x1800084e1  test    byte ptr [rcx+1Ch], 1
0x1800084e5  jz      short loc_1800084F9
0x1800084e7  mov     [rsp+0E8h+var_C8], rax; __int64
0x1800084ec  mov     r9d, ebx
0x1800084ef  mov     rcx, [rcx+10h]; LoggerHandle
0x1800084f3  call    WPP_SF_dS
0x1800084f8  nop
0x1800084f9  mov     rdx, [rsp+0E8h+pv]; unsigned __int16 *
0x180008501  lea     rcx, [rsp+0E8h+hKey]; this
0x180008506  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000850b  nop
0x18000850c  jmp     short loc_18000851B
0x18000850e  lea     r14, WPP_GLOBAL_Control
0x180008515  xor     edi, edi
  ... truncated ...
```
