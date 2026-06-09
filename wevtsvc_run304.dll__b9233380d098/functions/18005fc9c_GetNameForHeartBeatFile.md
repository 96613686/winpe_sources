# GetNameForHeartBeatFile

- ea: `0x18005fc9c`
- end: `0x18005feee`
- name: `GetNameForHeartBeatFile`
- size: `594`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18005e984`
- `0x18005f634`
- `0x1800c27d4`

## callees

- `0x1800010c8`
- `0x18000137c`
- `0x180004980`
- `0x180017b60`
- `0x18002de9c`
- `0x18005fc9c`
- `0x180070c70`
- `0x180092008`
- `0x180092ee4`
- `0x1800c1da4`

## import_xrefs

- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18005fd02`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18005fd86`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18005fd02`
- `api-ms-win-service-core-l1-1-4!GetServiceDirectory` at `0x18005fd86`

## pseudocode

```c
__int64 __fastcall GetNameForHeartBeatFile(__int64 a1, unsigned int a2)
{
  int ServiceDirectory; // r8d
  __int64 v5; // r9
  unsigned __int64 v6; // rcx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int appended; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  _WORD *v16; // [rsp+38h] [rbp-28h] BYREF
  _WORD *v17; // [rsp+40h] [rbp-20h]
  _WORD v18[12]; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+20h] BYREF
  const wchar_t *v20; // [rsp+88h] [rbp+28h] BYREF

  if ( !g_bHeartBeatsDisabled )
  {
    v16 = v18;
    v17 = v18;
    v18[0] = 0;
    v19 = 0;
    ServiceDirectory = GetServiceDirectory(g_serviceControl, 0, 0, 0, &v19);
    if ( ServiceDirectory == 122 )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                               &v16,
                               v19) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
        }
        goto LABEL_27;
      }
      ServiceDirectory = GetServiceDirectory(g_serviceControl, 0, v16, v19, &v19);
      v6 = v19 - 1;
      if ( v6 > v17 - v16 )
        __int2c();
      v17 = &v16[v6];
      *v17 = 0;
    }
    if ( !ServiceDirectory )
      goto LABEL_21;
    if ( (unsigned int)dword_18010F088 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18010F088, 0x400000000000LL) )
    {
      v15 = 0x1000000;
      LODWORD(v20) = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)&unk_1800FD329,
        v8,
        v9,
        (__int64)&v20,
        (__int64)&v15);
    }
    v17 = v16;
    *v16 = 0;
    v20 = L"%LOCALAPPDATA%";
    appended = ____AppendFnImpl__WU__char_traits__W_utl__V__allocator__W_2_V_lambda_1___1_____AppendEnvVarImpl_V__basic_string__WU__char_traits__W_utl__V__allocator__W_2__utl___W_tlx__YAJAEAV__basic_string__WU__char_traits__W_utl__V__allocator__W_2__2_PEB_W_Z__tlx__YAJAEAV__basic_string__WU__char_traits__W_utl__V__allocator__W_2__utl____QEAV_lambda_1___1_____AppendEnvVarImpl_V__basic_string__WU__char_traits__W_utl__V__allocator__W_2__utl___W_0_YAJ0PEB_W_Z__Z(
                 &v16,
                 &v20);
    v5 = (unsigned int)appended;
    if ( appended < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_27;
      }
      v12 = 20;
    }
    else
    {
LABEL_21:
      v13 = tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              &v16,
              L"\\lastalive%d.dat",
              a2,
              v5);
      v5 = (unsigned int)v13;
      if ( v13 >= 0 )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          a1,
          &v16);
        goto LABEL_29;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_27:
        *(_QWORD *)a1 = a1 + 16;
        *(_QWORD *)(a1 + 8) = a1 + 16;
        *(_WORD *)(a1 + 16) = 0;
LABEL_29:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v16);
        return a1;
      }
      v12 = 21;
    }
    WPP_SF_d(v11[2], v12, &WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids, v5);
    goto LABEL_27;
  }
  *(_QWORD *)a1 = a1 + 16;
  *(_QWORD *)(a1 + 8) = a1 + 16;
  *(_WORD *)(a1 + 16) = 0;
  return a1;
}

```

## disassembly

```asm
0x18005fc9c  mov     [rsp-8+arg_0], rbx
0x18005fca1  mov     [rsp-8+arg_8], rdi
0x18005fca6  push    rbp
0x18005fca7  mov     rbp, rsp
0x18005fcaa  sub     rsp, 60h
0x18005fcae  cmp     cs:?g_bHeartBeatsDisabled@@3_NA, 0; bool g_bHeartBeatsDisabled
0x18005fcb5  mov     edi, edx
0x18005fcb7  mov     rbx, rcx
0x18005fcba  jz      short loc_18005FCD1
0x18005fcbc  lea     rdx, [rcx+10h]
0x18005fcc0  xor     eax, eax
0x18005fcc2  mov     [rcx], rdx
0x18005fcc5  mov     [rcx+8], rdx
0x18005fcc9  mov     [rdx], ax
0x18005fccc  jmp     loc_18005FEDB
0x18005fcd1  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_serviceControl
0x18005fcd8  lea     rax, [rbp+var_18]
0x18005fcdc  mov     [rbp+var_28], rax
0x18005fce0  xor     r9d, r9d
0x18005fce3  lea     rax, [rbp+var_18]
0x18005fce7  xor     r8d, r8d
0x18005fcea  mov     [rbp+var_20], rax
0x18005fcee  xor     edx, edx
0x18005fcf0  xor     eax, eax
0x18005fcf2  mov     [rbp+var_18], ax
0x18005fcf6  mov     [rbp+arg_10], eax
0x18005fcf9  lea     rax, [rbp+arg_10]
0x18005fcfd  mov     [rsp+60h+var_40], rax
0x18005fd02  call    cs:__imp_GetServiceDirectory
0x18005fd08  mov     r8d, eax
0x18005fd0b  cmp     eax, 7Ah ; 'z'
0x18005fd0e  jnz     loc_18005FDB6
0x18005fd14  mov     edx, [rbp+arg_10]
0x18005fd17  lea     rcx, [rbp+var_28]
0x18005fd1b  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18005fd20  test    al, al
0x18005fd22  jnz     short loc_18005FD6C
0x18005fd24  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fd2b  lea     rax, WPP_GLOBAL_Control
0x18005fd32  cmp     rcx, rax
0x18005fd35  jz      loc_18005FEB4
0x18005fd3b  test    dword ptr [rcx+1Ch], 4000h
0x18005fd42  jz      loc_18005FEB4
0x18005fd48  cmp     byte ptr [rcx+19h], 2
0x18005fd4c  jb      loc_18005FEB4
0x18005fd52  mov     rcx, [rcx+10h]
0x18005fd56  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005fd5d  mov     edx, 13h
0x18005fd62  call    WPP_SF_
0x18005fd67  jmp     loc_18005FEB4
0x18005fd6c  mov     r9d, [rbp+arg_10]
0x18005fd70  lea     rax, [rbp+arg_10]
0x18005fd74  mov     r8, [rbp+var_28]
0x18005fd78  xor     edx, edx
0x18005fd7a  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_serviceControl
0x18005fd81  mov     [rsp+60h+var_40], rax
0x18005fd86  call    cs:__imp_GetServiceDirectory
0x18005fd8c  mov     ecx, [rbp+arg_10]
0x18005fd8f  mov     r8d, eax
0x18005fd92  mov     rax, [rbp+var_20]
0x18005fd96  dec     ecx
0x18005fd98  mov     rdx, [rbp+var_28]
0x18005fd9c  sub     rax, rdx
0x18005fd9f  sar     rax, 1
0x18005fda2  cmp     rcx, rax
0x18005fda5  jbe     short loc_18005FDA9
0x18005fda7  int     2Ch; Windows NT - assertion failure
0x18005fda9  lea     rcx, [rdx+rcx*2]
0x18005fdad  xor     eax, eax
0x18005fdaf  mov     [rbp+var_20], rcx
0x18005fdb3  mov     [rcx], ax
0x18005fdb6  test    r8d, r8d
0x18005fdb9  jz      loc_18005FE63
0x18005fdbf  mov     eax, cs:dword_18010F088
0x18005fdc5  cmp     eax, 5
0x18005fdc8  jbe     short loc_18005FE0E
0x18005fdca  mov     rdx, 400000000000h
0x18005fdd4  lea     rcx, dword_18010F088
0x18005fddb  call    _tlgKeywordOn
0x18005fde0  test    al, al
0x18005fde2  jz      short loc_18005FE0E
0x18005fde4  lea     rax, [rbp+var_30]
0x18005fde8  mov     [rbp+var_30], 1000000h
0x18005fdf0  mov     [rsp+60h+var_38], rax
0x18005fdf5  lea     rdx, unk_1800FD329
0x18005fdfc  lea     rax, [rbp+arg_18]
0x18005fe00  mov     dword ptr [rbp+arg_18], r8d
0x18005fe04  mov     [rsp+60h+var_40], rax
0x18005fe09  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18005fe0e  mov     rcx, [rbp+var_28]
0x18005fe12  lea     rdx, [rbp+arg_18]
0x18005fe16  xor     eax, eax
0x18005fe18  mov     [rbp+var_20], rcx
0x18005fe1c  mov     [rcx], ax
0x18005fe1f  lea     rax, aLocalappdata; "%LOCALAPPDATA%"
0x18005fe26  lea     rcx, [rbp+var_28]
0x18005fe2a  mov     [rbp+arg_18], rax
0x18005fe2e  call    ??$_AppendFnImpl@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@V_lambda_1_@?1???$_AppendEnvVarImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_W@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@2@PEB_W@Z@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@$$QEAV_lambda_1_@?1???$_AppendEnvVarImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_W@0@YAJ0PEB_W@Z@@Z; tlx::_AppendFnImpl<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>,`tlx::_AppendEnvVarImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *)'::`2'::_lambda_1_>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,`tlx::_AppendEnvVarImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,wchar_t>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *)'::`2'::_lambda_1_ &&)
0x18005fe33  mov     r9d, eax
0x18005fe36  test    eax, eax
0x18005fe38  jns     short loc_18005FE63
0x18005fe3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe41  lea     rax, WPP_GLOBAL_Control
0x18005fe48  cmp     rcx, rax
0x18005fe4b  jz      short loc_18005FEB4
0x18005fe4d  test    dword ptr [rcx+1Ch], 4000h
0x18005fe54  jz      short loc_18005FEB4
0x18005fe56  cmp     byte ptr [rcx+19h], 2
0x18005fe5a  jb      short loc_18005FEB4
0x18005fe5c  mov     edx, 14h
0x18005fe61  jmp     short loc_18005FEA4
0x18005fe63  mov     r8d, edi
0x18005fe66  lea     rdx, aLastaliveDDat; "\\lastalive%d.dat"
0x18005fe6d  lea     rcx, [rbp+var_28]
0x18005fe71  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18005fe76  mov     r9d, eax
0x18005fe79  test    eax, eax
0x18005fe7b  jns     short loc_18005FEC6
0x18005fe7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe84  lea     rax, WPP_GLOBAL_Control
0x18005fe8b  cmp     rcx, rax
0x18005fe8e  jz      short loc_18005FEB4
0x18005fe90  test    dword ptr [rcx+1Ch], 4000h
0x18005fe97  jz      short loc_18005FEB4
0x18005fe99  cmp     byte ptr [rcx+19h], 2
0x18005fe9d  jb      short loc_18005FEB4
0x18005fe9f  mov     edx, 15h
0x18005fea4  mov     rcx, [rcx+10h]
0x18005fea8  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18005feaf  call    WPP_SF_d
0x18005feb4  lea     rcx, [rbx+10h]
0x18005feb8  xor     eax, eax
0x18005feba  mov     [rbx], rcx
0x18005febd  mov     [rbx+8], rcx
0x18005fec1  mov     [rcx], ax
0x18005fec4  jmp     short loc_18005FED2
0x18005fec6  lea     rdx, [rbp+var_28]
0x18005feca  mov     rcx, rbx
0x18005fecd  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18005fed2  lea     rcx, [rbp+var_28]; void *
0x18005fed6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18005fedb  mov     rdi, [rsp+60h+arg_8]
0x18005fee0  mov     rax, rbx
0x18005fee3  mov     rbx, [rsp+60h+arg_0]
0x18005fee8  add     rsp, 60h
0x18005feec  pop     rbp
0x18005feed  retn
```
