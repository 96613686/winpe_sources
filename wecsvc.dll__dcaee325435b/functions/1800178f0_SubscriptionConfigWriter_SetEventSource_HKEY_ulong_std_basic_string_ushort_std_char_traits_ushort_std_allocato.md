# SubscriptionConfigWriter::SetEventSource(HKEY__ *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *)

- ea: `0x1800178f0`
- end: `0x180017b86`
- name: `?SetEventSource@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N1PEBG@Z`
- size: `662`
- prototype: `void __fastcall(__int64, HKEY, char, __int64, unsigned __int8, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001718c`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003810`
- `0x180003e6c`
- `0x1800062d4`
- `0x1800129f0`
- `0x180012b94`
- `0x1800159e0`
- `0x180017510`
- `0x1800178f0`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a36`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a58`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a69`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a9c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017aca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a36`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a58`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a69`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017a9c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180017aca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017979`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017979`

## pseudocode

```c
void __fastcall SubscriptionConfigWriter::SetEventSource(
        __int64 a1,
        HKEY a2,
        char a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  const WCHAR *v7; // rax
  const unsigned __int16 *v9; // rbx
  SubscriptionConfigWriter *v10; // rcx
  unsigned int v11; // edi
  unsigned __int16 *v12; // rdx
  __int64 v13; // rdx
  HKEY hKey; // [rsp+50h] [rbp-21h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-19h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-11h] BYREF
  char v17; // [rsp+68h] [rbp-9h]
  const char *v18; // [rsp+70h] [rbp-1h]
  __int64 v19; // [rsp+78h] [rbp+7h]
  __int64 v20; // [rsp+80h] [rbp+Fh]
  unsigned int v21; // [rsp+88h] [rbp+17h]
  int v22; // [rsp+8Ch] [rbp+1Bh]
  int v23; // [rsp+90h] [rbp+1Fh]

  v7 = (const WCHAR *)a4;
  v9 = a6;
  hKey = 0;
  dwDisposition = 0;
  if ( *(_QWORD *)(a4 + 24) >= 8u )
    v7 = *(const WCHAR **)a4;
  v11 = RegCreateKeyExW(a2, v7, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids, v11);
    }
    v17 = 0;
    v18 = "admin\\wmi\\events\\forwarding\\collector\\store\\store.cpp";
    v19 = 0;
    v20 = 0;
    v21 = v11;
    v22 = -1;
    v23 = 770;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  if ( (a3 & 2) != 0 )
  {
    RegWriteDWORDValue(hKey, L"Enabled", a5);
    RegDeleteValueW(hKey, L"LastError");
    RegDeleteValueW(hKey, L"LastErrorTime");
    RegDeleteValueW(hKey, L"LastErrorCount");
    RegDeleteValueW(hKey, L"LastFaultMessage");
    RegDeleteValueW(hKey, L"LastHeartbeatTime");
    RegDeleteValueW(hKey, L"BatchEventsDropped");
    RegDeleteValueW(hKey, L"BatchEventsProcessed");
  }
  if ( (a3 & 4) != 0 )
  {
    if ( !*((_QWORD *)a6 + 2) )
    {
      SubscriptionConfigWriter::DeletePassword(hKey, L"TargetId");
      RegDeleteValueW(hKey, L"UserName");
      goto LABEL_25;
    }
    if ( *((_QWORD *)a6 + 3) < 8u )
      v12 = a6;
    else
      v12 = *(unsigned __int16 **)a6;
    std::wstring::wstring(&pExceptionObject, v12);
    RegWriteStringValue(hKey, L"UserName", &pExceptionObject);
    LOBYTE(v13) = 1;
    std::wstring::_Tidy(&pExceptionObject, v13, 0);
  }
  if ( (a3 & 8) != 0 )
  {
    if ( a7 && *a7 )
    {
      if ( *((_QWORD *)a6 + 3) >= 8u )
        v9 = *(const unsigned __int16 **)a6;
      SubscriptionConfigWriter::SavePassword(v10, hKey, v9, L"TargetId", a7);
    }
    else
    {
      SubscriptionConfigWriter::DeletePassword(hKey, L"TargetId");
    }
  }
LABEL_25:
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
}

```

## disassembly

```asm
0x1800178f0  mov     [rsp-8+arg_0], rbx
0x1800178f5  mov     [rsp-8+arg_10], rsi
0x1800178fa  push    rbp
0x1800178fb  push    rdi
0x1800178fc  push    r14
0x1800178fe  lea     rbp, [rsp-2Fh]
0x180017903  sub     rsp, 0A0h
0x18001790a  mov     rax, cs:__security_cookie
0x180017911  xor     rax, rsp
0x180017914  mov     [rbp+3Fh+var_18], rax
0x180017918  mov     rax, r9
0x18001791b  mov     esi, r8d
0x18001791e  mov     r10, rdx
0x180017921  mov     rbx, [rbp+3Fh+arg_28]
0x180017925  mov     r14, [rbp+3Fh+arg_30]
0x180017929  mov     [rbp+3Fh+hKey], 0
0x180017931  mov     [rbp+3Fh+dwDisposition], 0
0x180017938  cmp     qword ptr [r9+18h], 8
0x18001793d  jb      short loc_180017942
0x18001793f  mov     rax, [r9]
0x180017942  lea     rcx, [rbp+3Fh+dwDisposition]
0x180017946  mov     [rsp+0B0h+lpdwDisposition], rcx; lpdwDisposition
0x18001794b  lea     rcx, [rbp+3Fh+hKey]
0x18001794f  mov     [rsp+0B0h+phkResult], rcx; phkResult
0x180017954  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001795d  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x180017965  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18001796d  xor     r9d, r9d; lpClass
0x180017970  xor     r8d, r8d; Reserved
0x180017973  mov     rdx, rax; lpSubKey
0x180017976  mov     rcx, r10; hKey
0x180017979  call    cs:__imp_RegCreateKeyExW
0x18001797f  mov     edi, eax
0x180017981  test    eax, eax
0x180017983  jz      loc_180017A0C
0x180017989  lea     rax, WPP_GLOBAL_Control
0x180017990  mov     rcx, cs:WPP_GLOBAL_Control
0x180017997  cmp     rcx, rax
0x18001799a  jz      short loc_1800179C0
0x18001799c  test    byte ptr [rcx+1Ch], 40h
0x1800179a0  jz      short loc_1800179C0
0x1800179a2  cmp     byte ptr [rcx+19h], 2
0x1800179a6  jb      short loc_1800179C0
0x1800179a8  mov     edx, 1Bh
0x1800179ad  mov     r9d, edi
0x1800179b0  lea     r8, WPP_995d7fc7f38b34c45f7188ba39a91f1d_Traceguids
0x1800179b7  mov     rcx, [rcx+10h]
0x1800179bb  call    WPP_SF_D
0x1800179c0  mov     [rbp+3Fh+var_48], 0
0x1800179c4  lea     rax, aAdminWmiEvents_6; "admin\\wmi\\events\\forwarding\\collect"...
0x1800179cb  mov     [rbp+3Fh+var_40], rax
0x1800179cf  mov     [rbp+3Fh+var_38], 0
0x1800179d7  mov     [rbp+3Fh+var_30], 0
0x1800179df  mov     [rbp+3Fh+var_28], edi
0x1800179e2  mov     [rbp+3Fh+var_24], 0FFFFFFFFh
0x1800179e9  mov     [rbp+3Fh+var_20], 302h
0x1800179f0  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800179f7  mov     [rbp+3Fh+pExceptionObject], rax
0x1800179fb  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180017a02  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180017a06  call    _CxxThrowException_0
0x180017a0c  test    sil, 2
0x180017a10  jz      loc_180017AA2
0x180017a16  movzx   r8d, [rbp+3Fh+arg_20]; unsigned int
0x180017a1b  lea     rdx, aEnabled; "Enabled"
0x180017a22  mov     rcx, [rbp+3Fh+hKey]; HKEY
0x180017a26  call    ?RegWriteDWORDValue@@YAXPEAUHKEY__@@PEBGK@Z; RegWriteDWORDValue(HKEY__ *,ushort const *,ulong)
0x180017a2b  lea     rdx, aLasterror; "LastError"
0x180017a32  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017a36  call    cs:__imp_RegDeleteValueW
0x180017a3c  lea     rdx, aLasterrortime; "LastErrorTime"
0x180017a43  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017a47  call    cs:__imp_RegDeleteValueW
0x180017a4d  lea     rdx, aLasterrorcount; "LastErrorCount"
0x180017a54  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017a58  call    cs:__imp_RegDeleteValueW
0x180017a5e  lea     rdx, aLastfaultmessa; "LastFaultMessage"
0x180017a65  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017a69  call    cs:__imp_RegDeleteValueW
0x180017a6f  lea     rdx, aLastheartbeatt; "LastHeartbeatTime"
0x180017a76  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017a7a  call    cs:__imp_RegDeleteValueW
0x180017a80  lea     rdx, aBatcheventsdro; "BatchEventsDropped"
0x180017a87  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017a8b  call    cs:__imp_RegDeleteValueW
0x180017a91  lea     rdx, aBatcheventspro; "BatchEventsProcessed"
0x180017a98  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017a9c  call    cs:__imp_RegDeleteValueW
0x180017aa2  test    sil, 4
0x180017aa6  jz      short loc_180017B11
0x180017aa8  cmp     qword ptr [rbx+10h], 0
0x180017aad  jnz     short loc_180017AD5
0x180017aaf  lea     rdx, aTargetid; "TargetId"
0x180017ab6  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017aba  call    ?DeletePassword@SubscriptionConfigWriter@@CAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::DeletePassword(HKEY__ *,ushort const *)
0x180017abf  lea     rdx, aUsername; "UserName"
0x180017ac6  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017aca  call    cs:__imp_RegDeleteValueW
0x180017ad0  jmp     loc_180017B59
0x180017ad5  cmp     qword ptr [rbx+18h], 8
0x180017ada  jb      short loc_180017AE1
0x180017adc  mov     rdx, [rbx]
0x180017adf  jmp     short loc_180017AE4
0x180017ae1  mov     rdx, rbx
0x180017ae4  lea     rcx, [rbp+3Fh+pExceptionObject]
0x180017ae8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180017aed  nop
0x180017aee  lea     r8, [rbp+3Fh+pExceptionObject]
0x180017af2  lea     rdx, aUsername; "UserName"
0x180017af9  mov     rcx, [rbp+3Fh+hKey]
0x180017afd  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x180017b02  nop
0x180017b03  xor     r8d, r8d
0x180017b06  mov     dl, 1
0x180017b08  lea     rcx, [rbp+3Fh+pExceptionObject]
0x180017b0c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180017b11  test    sil, 8
0x180017b15  jz      short loc_180017B59
0x180017b17  test    r14, r14
0x180017b1a  jz      short loc_180017B48
0x180017b1c  xor     eax, eax
0x180017b1e  cmp     ax, [r14]
0x180017b22  jz      short loc_180017B48
0x180017b24  cmp     qword ptr [rbx+18h], 8
0x180017b29  jb      short loc_180017B2E
0x180017b2b  mov     rbx, [rbx]
0x180017b2e  mov     qword ptr [rsp+0B0h+dwOptions], r14; unsigned __int16 *
0x180017b33  lea     r9, aTargetid; "TargetId"
0x180017b3a  mov     r8, rbx; unsigned __int16 *
0x180017b3d  mov     rdx, [rbp+3Fh+hKey]; HKEY
0x180017b41  call    ?SavePassword@SubscriptionConfigWriter@@AEAAXPEAUHKEY__@@PEBG11@Z; SubscriptionConfigWriter::SavePassword(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180017b46  jmp     short loc_180017B59
0x180017b48  lea     rdx, aTargetid; "TargetId"
0x180017b4f  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180017b53  call    ?DeletePassword@SubscriptionConfigWriter@@CAXPEAUHKEY__@@PEBG@Z; SubscriptionConfigWriter::DeletePassword(HKEY__ *,ushort const *)
0x180017b58  nop
0x180017b59  lea     rcx, [rbp+3Fh+hKey]; this
0x180017b5d  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180017b62  mov     rcx, [rbp+3Fh+var_18]
0x180017b66  xor     rcx, rsp; StackCookie
0x180017b69  call    __security_check_cookie
0x180017b6e  lea     r11, [rsp+0B0h+var_10]
0x180017b76  mov     rbx, [r11+20h]
0x180017b7a  mov     rsi, [r11+30h]
0x180017b7e  mov     rsp, r11
0x180017b81  pop     r14
0x180017b83  pop     rdi
0x180017b84  pop     rbp
0x180017b85  retn
```
