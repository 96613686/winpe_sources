# NotificationServiceImpl::OnCommandResponse(ulong,long,ulong,ulong,uchar *)

- ea: `0x18006f850`
- end: `0x1800702f0`
- name: `?OnCommandResponse@NotificationServiceImpl@@UEAAJKJKKPEAE@Z`
- size: `2720`
- prototype: `__int64 __fastcall(NotificationServiceImpl *this, __int64, __int64, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x1800455ec`
- `0x18006d890`
- `0x18006f850`
- `0x180072928`
- `0x180075dec`
- `0x180076e0c`
- `0x180078c40`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18006ffb2`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ffc2`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ffb2`
- `OLEAUT32!__imp_SysAllocString` at `0x18006ffc2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ff2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ff4e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800702a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800702a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ff2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ff4e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800702a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800702a9`

## string_xrefs

- `0x18006f9b5`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006fa48`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006fadd`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006fb9e`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::OnCommandResponse(
        NotificationServiceImpl *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  unsigned int v7; // edi
  __int64 v8; // r9
  char v10; // r13
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // r15d
  unsigned int v15; // ebx
  unsigned __int64 v16; // r12
  PVOID *v17; // rcx
  char v18; // si
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rdx
  struct WNPMessageParser *v24; // r8
  OLECHAR *v26; // r14
  BSTR v27; // rax
  OLECHAR *v28; // rsi
  int v29; // eax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-59h]
  int v33; // [rsp+20h] [rbp-59h]
  int v34; // [rsp+40h] [rbp-39h] BYREF
  struct IConnectionProviderEvents *v35; // [rsp+48h] [rbp-31h] BYREF
  __int64 v36; // [rsp+50h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-21h] BYREF
  BSTR v38; // [rsp+60h] [rbp-19h] BYREF
  struct WNPMessageParser *v39; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 v40; // [rsp+70h] [rbp-9h] BYREF
  __int64 v41; // [rsp+78h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]
  int v43; // [rsp+D0h] [rbp+57h] BYREF

  v7 = a3;
  v8 = (unsigned int)a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)a2,
      a3,
      a4);
  }
  v39 = 0;
  v36 = 0;
  v10 = 0;
  v35 = 0;
  v34 = 0;
  v40 = 0;
  bstrString = 0;
  v38 = 0;
  v43 = 0;
  v41 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35, a2, a3, v8);
  NotificationServiceImpl::GetConnectionProviderEvents((NotificationServiceImpl *)((char *)this - 8), &v35);
  v11 = NotificationServiceImpl::RemoveOutstandingRequest(
          (NotificationServiceImpl *)((char *)this - 8),
          (struct _LIST_ENTRY *)((char *)this + 152),
          a4,
          &v34,
          &v40,
          (enum _RequestTypes *)&v43);
  v14 = v34;
  v15 = v11;
  v16 = v40;
  if ( v11 < 0 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v11);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    v18 = 0;
    v15 = 0;
    goto LABEL_46;
  }
  v18 = 1;
  if ( (v7 & 0x80000000) == 0 )
  {
    v15 = WNPMessageParser::CreateInstance(a6, a5, &v39);
    if ( (v15 & 0x80000000) == 0 )
    {
      v15 = WNPMessageParser::ParseChannelRequest(v39, &bstrString, &v38, (double *)&v36);
      if ( (v15 & 0x80000000) == 0 )
      {
        v10 = 1;
        v33 = (int)v38;
        v41 = *((_QWORD *)v39 + 5);
        v15 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, BSTR))(*(_QWORD *)v35 + 32LL))(
                v35,
                v14,
                v16,
                bstrString);
        if ( (v15 & 0x80000000) == 0 )
        {
LABEL_45:
          v17 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_46;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v15);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3AC,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)v15,
          v33);
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_46;
        v19 = 67;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v15);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3A4,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
          (const char *)v15,
          v32);
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_46;
        v19 = 65;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v15);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v15,
        v32);
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_46;
      v19 = 63;
    }
    v20 = v15;
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v7);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x39B,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
    (const char *)v7,
    v32);
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v19 = 61;
    v20 = v7;
LABEL_44:
    WPP_SF_d(v17[2], v19, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v20);
    goto LABEL_45;
  }
LABEL_46:
  if ( (byte_1800AFD82 & 0x10) != 0 )
  {
    McTemplateU0qqxx_EventWriteTransfer((_DWORD)v17, v12, a4, v7, v41, v16);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v18 )
    goto LABEL_93;
  if ( v10 )
  {
    switch ( v43 )
    {
      case 1:
        v22 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, BSTR, BSTR, __int64, unsigned int))(*(_QWORD *)v35 + 40LL))(
                v35,
                v14,
                v16,
                bstrString,
                v38,
                v36,
                v7);
        v15 = v22;
        if ( v22 >= 0 )
          goto LABEL_92;
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v23 = 68;
        break;
      case 2:
        v22 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, BSTR, BSTR, __int64, unsigned int))(*(_QWORD *)v35 + 48LL))(
                v35,
                v14,
                v16,
                bstrString,
                v38,
                v36,
                v7);
        v15 = v22;
        if ( v22 >= 0 )
          goto LABEL_92;
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v23 = 69;
        break;
      case 3:
        v22 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, BSTR, BSTR, __int64, unsigned int))(*(_QWORD *)v35 + 56LL))(
                v35,
                v14,
                v16,
                bstrString,
                v38,
                v36,
                v7);
        v15 = v22;
        if ( v22 >= 0 )
          goto LABEL_92;
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v23 = 70;
        break;
      case 4:
        v22 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, _QWORD))(*(_QWORD *)v35 + 72LL))(
                v35,
                v14,
                v16,
                v7);
        v15 = v22;
        if ( v22 >= 0 )
          goto LABEL_92;
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v23 = 71;
        break;
      default:
        v12 = (unsigned int)(v43 - 5);
        if ( v43 != 5 )
        {
          if ( v43 != 6 )
          {
            if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 2) != 0 && *((_BYTE *)v17 + 25) >= 2u )
            {
              v21 = 74;
LABEL_60:
              WPP_SF_(v17[2], v21, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
LABEL_148:
              v17 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_93;
            }
            goto LABEL_93;
          }
          v22 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, _QWORD))(*(_QWORD *)v35 + 88LL))(
                  v35,
                  v14,
                  v7);
          v15 = v22;
          if ( v22 < 0 )
          {
            v17 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_93;
            }
            v23 = 73;
            break;
          }
LABEL_92:
          v17 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_93;
        }
        v22 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, _QWORD))(*(_QWORD *)v35 + 80LL))(
                v35,
                v14,
                v16,
                v7);
        v15 = v22;
        if ( v22 >= 0 )
          goto LABEL_92;
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_93;
        }
        v23 = 72;
        break;
    }
    WPP_SF_d(v17[2], v23, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, (unsigned int)v22);
    goto LABEL_148;
  }
  v26 = SysAllocString(&psz);
  v27 = SysAllocString(&psz);
  v28 = v27;
  if ( v26 && v27 )
  {
    switch ( v43 )
    {
      case 1:
        v29 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, OLECHAR *, BSTR, __int64, unsigned int))(*(_QWORD *)v35 + 40LL))(
                v35,
                v14,
                v16,
                v26,
                v27,
                v36,
                v7);
        v15 = v29;
        if ( v29 >= 0 )
          goto LABEL_147;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_147;
        }
        v31 = 75;
        break;
      case 2:
        v29 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, OLECHAR *, BSTR, __int64, unsigned int))(*(_QWORD *)v35 + 48LL))(
                v35,
                v14,
                v16,
                v26,
                v27,
                v36,
                v7);
        v15 = v29;
        if ( v29 >= 0 )
          goto LABEL_147;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_147;
        }
        v31 = 76;
        break;
      case 3:
        v29 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, OLECHAR *, BSTR, __int64, unsigned int))(*(_QWORD *)v35 + 56LL))(
                v35,
                v14,
                v16,
                v26,
                v27,
                v36,
                v7);
        v15 = v29;
        if ( v29 >= 0 )
          goto LABEL_147;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_147;
        }
        v31 = 77;
        break;
      case 4:
        v29 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, _QWORD))(*(_QWORD *)v35 + 72LL))(
                v35,
                v14,
                v16,
                v7);
        v15 = v29;
        if ( v29 >= 0 )
          goto LABEL_147;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_147;
        }
        v31 = 78;
        break;
      case 5:
        v29 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, unsigned __int64, _QWORD))(*(_QWORD *)v35 + 80LL))(
                v35,
                v14,
                v16,
                v7);
        v15 = v29;
        if ( v29 >= 0 )
          goto LABEL_147;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_147;
        }
        v31 = 79;
        break;
      case 6:
        v29 = (*(__int64 (__fastcall **)(struct IConnectionProviderEvents *, _QWORD, _QWORD))(*(_QWORD *)v35 + 88LL))(
                v35,
                v14,
                v7);
        v15 = v29;
        if ( v29 >= 0
          || (v30 = WPP_GLOBAL_Control, WPP_GLOBAL_Control == &WPP_GLOBAL_Control)
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_147:
          SysFreeString(v26);
          SysFreeString(v28);
          goto LABEL_148;
        }
        v31 = 80;
        break;
      default:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
        }
        goto LABEL_147;
    }
    WPP_SF_d(v30[2], v31, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, (unsigned int)v29);
    goto LABEL_147;
  }
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = 82;
    goto LABEL_60;
  }
LABEL_93:
  v24 = v39;
  if ( v39 )
  {
    (**(void (__fastcall ***)(struct WNPMessageParser *, __int64))v39)(v39, 1);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    v17 = (PVOID *)WPP_GLOBAL_Control;
    bstrString = 0;
  }
  if ( v38 )
  {
    SysFreeString(v38);
    v17 = (PVOID *)WPP_GLOBAL_Control;
    v38 = 0;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 2) != 0 && *((_BYTE *)v17 + 25) >= 6u )
    WPP_SF_d(v17[2], 83, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35, v12, v24, v13);
  return v15;
}

```

## disassembly

```asm
0x18006f850  push    rbp
0x18006f852  push    rbx
0x18006f853  push    rsi
0x18006f854  push    rdi
0x18006f855  push    r12
0x18006f857  push    r13
0x18006f859  push    r14
0x18006f85b  push    r15
0x18006f85d  lea     rbp, [rsp-0Fh]
0x18006f862  sub     rsp, 88h
0x18006f869  mov     r14d, r9d
0x18006f86c  mov     edi, r8d
0x18006f86f  mov     r9d, edx
0x18006f872  mov     rsi, rcx
0x18006f875  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f87c  lea     rax, WPP_GLOBAL_Control
0x18006f883  cmp     rcx, rax
0x18006f886  jz      short loc_18006F8B3
0x18006f888  test    byte ptr [rcx+1Ch], 2
0x18006f88c  jz      short loc_18006F8B3
0x18006f88e  cmp     byte ptr [rcx+19h], 6
0x18006f892  jb      short loc_18006F8B3
0x18006f894  mov     rcx, [rcx+10h]
0x18006f898  mov     edx, 39h ; '9'
0x18006f89d  mov     dword ptr [rsp+0C0h+var_98], r14d
0x18006f8a2  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x18006f8a7  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f8ae  call    WPP_SF_ddd
0x18006f8b3  xor     eax, eax
0x18006f8b5  lea     rcx, [rbp+47h+var_78]
0x18006f8b9  xorps   xmm0, xmm0
0x18006f8bc  mov     [rbp+47h+var_58], rax
0x18006f8c0  movsd   [rbp+47h+var_70], xmm0
0x18006f8c5  mov     r13b, al
0x18006f8c8  mov     [rbp+47h+var_78], rax
0x18006f8cc  mov     [rbp+47h+var_80], eax
0x18006f8cf  mov     [rbp+47h+var_50], rax
0x18006f8d3  mov     [rbp+47h+bstrString], rax
0x18006f8d7  mov     [rbp+47h+var_60], rax
0x18006f8db  mov     [rbp+47h+arg_0], eax
0x18006f8de  mov     [rbp+47h+var_48], rax
0x18006f8e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006f8e7  lea     rdx, [rbp+47h+var_78]; struct IConnectionProviderEvents **
0x18006f8eb  lea     rcx, [rsi-8]; this
0x18006f8ef  call    ?GetConnectionProviderEvents@NotificationServiceImpl@@AEAAXPEAPEAUIConnectionProviderEvents@@@Z; NotificationServiceImpl::GetConnectionProviderEvents(IConnectionProviderEvents * *)
0x18006f8f4  lea     rax, [rbp+47h+arg_0]
0x18006f8f8  mov     r8d, r14d; unsigned int
0x18006f8fb  mov     [rsp+0C0h+var_98], rax; enum _RequestTypes *
0x18006f900  lea     rdx, [rsi+98h]; struct _LIST_ENTRY *
0x18006f907  lea     rax, [rbp+47h+var_50]
0x18006f90b  lea     r9, [rbp+47h+var_80]; int *
0x18006f90f  mov     [rsp+0C0h+var_A0], rax; int
0x18006f914  lea     rcx, [rsi-8]; this
0x18006f918  call    ?RemoveOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@KPEAJPEA_KPEAW4_RequestTypes@@@Z; NotificationServiceImpl::RemoveOutstandingRequest(_LIST_ENTRY *,ulong,long *,unsigned __int64 *,_RequestTypes *)
0x18006f91d  mov     r15d, [rbp+47h+var_80]
0x18006f921  mov     ebx, eax
0x18006f923  mov     r12, [rbp+47h+var_50]
0x18006f927  test    eax, eax
0x18006f929  jns     short loc_18006F973
0x18006f92b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f932  lea     rax, WPP_GLOBAL_Control
0x18006f939  cmp     rcx, rax
0x18006f93c  jz      short loc_18006F969
0x18006f93e  test    byte ptr [rcx+1Ch], 2
0x18006f942  jz      short loc_18006F969
0x18006f944  cmp     byte ptr [rcx+19h], 2
0x18006f948  jb      short loc_18006F969
0x18006f94a  mov     rcx, [rcx+10h]
0x18006f94e  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f955  mov     edx, 3Ah ; ':'
0x18006f95a  mov     r9d, ebx
0x18006f95d  call    WPP_SF_d
0x18006f962  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f969  xor     sil, sil
0x18006f96c  xor     ebx, ebx
0x18006f96e  jmp     loc_18006FBEA
0x18006f973  mov     sil, 1
0x18006f976  test    edi, edi
0x18006f978  jns     short loc_18006F9F7
0x18006f97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f981  lea     rax, WPP_GLOBAL_Control
0x18006f988  cmp     rcx, rax
0x18006f98b  jz      short loc_18006F9B1
0x18006f98d  test    byte ptr [rcx+1Ch], 2
0x18006f991  jz      short loc_18006F9B1
0x18006f993  cmp     byte ptr [rcx+19h], 2
0x18006f997  jb      short loc_18006F9B1
0x18006f999  mov     rcx, [rcx+10h]
0x18006f99d  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006f9a4  mov     edx, 3Ch ; '<'
0x18006f9a9  mov     r9d, edi
0x18006f9ac  call    WPP_SF_d
0x18006f9b1  mov     rcx, [rbp+4Fh]; this
0x18006f9b5  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006f9bc  mov     r9d, edi; char *
0x18006f9bf  mov     edx, 39Bh; void *
0x18006f9c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f9d0  lea     rax, WPP_GLOBAL_Control
0x18006f9d7  cmp     rcx, rax
0x18006f9da  jz      loc_18006FBEA
0x18006f9e0  test    byte ptr [rcx+1Ch], 80h
0x18006f9e4  jz      loc_18006FBEA
0x18006f9ea  mov     edx, 3Dh ; '='
0x18006f9ef  mov     r9d, edi
0x18006f9f2  jmp     loc_18006FBD3
0x18006f9f7  mov     edx, [rbp+47h+arg_20]; unsigned int
0x18006f9fa  lea     r8, [rbp+47h+var_58]; struct WNPMessageParser **
0x18006f9fe  mov     rcx, [rbp+47h+arg_28]; unsigned __int8 *
0x18006fa02  call    ?CreateInstance@WNPMessageParser@@SAJPEAEKPEAPEAV1@@Z; WNPMessageParser::CreateInstance(uchar *,ulong,WNPMessageParser * *)
0x18006fa07  mov     ebx, eax
0x18006fa09  test    eax, eax
0x18006fa0b  jns     short loc_18006FA87
0x18006fa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fa14  lea     rax, WPP_GLOBAL_Control
0x18006fa1b  cmp     rcx, rax
0x18006fa1e  jz      short loc_18006FA44
0x18006fa20  test    byte ptr [rcx+1Ch], 2
0x18006fa24  jz      short loc_18006FA44
0x18006fa26  cmp     byte ptr [rcx+19h], 2
0x18006fa2a  jb      short loc_18006FA44
0x18006fa2c  mov     rcx, [rcx+10h]
0x18006fa30  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006fa37  mov     edx, 3Eh ; '>'
0x18006fa3c  mov     r9d, ebx
0x18006fa3f  call    WPP_SF_d
0x18006fa44  mov     rcx, [rbp+4Fh]; this
0x18006fa48  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006fa4f  mov     r9d, ebx; char *
0x18006fa52  mov     edx, 3A0h; void *
0x18006fa57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006fa5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fa63  lea     rax, WPP_GLOBAL_Control
0x18006fa6a  cmp     rcx, rax
0x18006fa6d  jz      loc_18006FBEA
0x18006fa73  test    byte ptr [rcx+1Ch], 80h
0x18006fa77  jz      loc_18006FBEA
0x18006fa7d  mov     edx, 3Fh ; '?'
0x18006fa82  jmp     loc_18006FBD0
0x18006fa87  mov     rcx, [rbp+47h+var_58]; this
0x18006fa8b  lea     r9, [rbp+47h+var_70]; double *
0x18006fa8f  lea     r8, [rbp+47h+var_60]; unsigned __int16 **
0x18006fa93  lea     rdx, [rbp+47h+bstrString]; unsigned __int16 **
0x18006fa97  call    ?ParseChannelRequest@WNPMessageParser@@QEAAJPEAPEAG0PEAN@Z; WNPMessageParser::ParseChannelRequest(ushort * *,ushort * *,double *)
0x18006fa9c  mov     ebx, eax
0x18006fa9e  test    eax, eax
0x18006faa0  jns     short loc_18006FB1C
0x18006faa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006faa9  lea     rax, WPP_GLOBAL_Control
0x18006fab0  cmp     rcx, rax
0x18006fab3  jz      short loc_18006FAD9
0x18006fab5  test    byte ptr [rcx+1Ch], 2
0x18006fab9  jz      short loc_18006FAD9
0x18006fabb  cmp     byte ptr [rcx+19h], 2
0x18006fabf  jb      short loc_18006FAD9
0x18006fac1  mov     rcx, [rcx+10h]
0x18006fac5  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006facc  mov     edx, 40h ; '@'
0x18006fad1  mov     r9d, ebx
0x18006fad4  call    WPP_SF_d
0x18006fad9  mov     rcx, [rbp+4Fh]; this
0x18006fadd  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006fae4  mov     r9d, ebx; char *
0x18006fae7  mov     edx, 3A4h; void *
0x18006faec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006faf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006faf8  lea     rax, WPP_GLOBAL_Control
0x18006faff  cmp     rcx, rax
0x18006fb02  jz      loc_18006FBEA
0x18006fb08  test    byte ptr [rcx+1Ch], 80h
0x18006fb0c  jz      loc_18006FBEA
0x18006fb12  mov     edx, 41h ; 'A'
0x18006fb17  jmp     loc_18006FBD0
0x18006fb1c  mov     rdx, [rbp+47h+var_60]
0x18006fb20  mov     r8, r12
0x18006fb23  mov     rcx, [rbp+47h+var_78]
0x18006fb27  mov     r13b, sil
0x18006fb2a  movsd   xmm0, [rbp+47h+var_70]
0x18006fb2f  mov     rax, [rbp+47h+var_58]
0x18006fb33  mov     r9, [rbp+47h+bstrString]
0x18006fb37  movsd   [rsp+0C0h+var_98], xmm0
0x18006fb3d  mov     [rsp+0C0h+var_A0], rdx; int
0x18006fb42  mov     edx, r15d
0x18006fb45  mov     rax, [rax+28h]
0x18006fb49  mov     [rbp+47h+var_48], rax
0x18006fb4d  mov     rax, [rcx]
0x18006fb50  mov     rax, [rax+20h]
0x18006fb54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb59  mov     ebx, eax
0x18006fb5b  test    eax, eax
0x18006fb5d  jns     loc_18006FBE3
0x18006fb63  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fb6a  lea     rax, WPP_GLOBAL_Control
0x18006fb71  cmp     rcx, rax
0x18006fb74  jz      short loc_18006FB9A
0x18006fb76  test    byte ptr [rcx+1Ch], 2
0x18006fb7a  jz      short loc_18006FB9A
0x18006fb7c  cmp     byte ptr [rcx+19h], 2
0x18006fb80  jb      short loc_18006FB9A
0x18006fb82  mov     rcx, [rcx+10h]
0x18006fb86  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006fb8d  mov     edx, 42h ; 'B'
0x18006fb92  mov     r9d, ebx
0x18006fb95  call    WPP_SF_d
0x18006fb9a  mov     rcx, [rbp+4Fh]; this
0x18006fb9e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006fba5  mov     r9d, ebx; char *
0x18006fba8  mov     edx, 3ACh; void *
0x18006fbad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006fbb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fbb9  lea     rax, WPP_GLOBAL_Control
0x18006fbc0  cmp     rcx, rax
0x18006fbc3  jz      short loc_18006FBEA
0x18006fbc5  test    byte ptr [rcx+1Ch], 80h
0x18006fbc9  jz      short loc_18006FBEA
0x18006fbcb  mov     edx, 43h ; 'C'
0x18006fbd0  mov     r9d, ebx
0x18006fbd3  mov     rcx, [rcx+10h]
0x18006fbd7  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006fbde  call    WPP_SF_d
0x18006fbe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fbea  test    cs:byte_1800AFD82, 10h
0x18006fbf1  jz      short loc_18006FC13
0x18006fbf3  mov     rax, [rbp+47h+var_48]
0x18006fbf7  mov     r9d, edi
0x18006fbfa  mov     [rsp+0C0h+var_98], r12
0x18006fbff  mov     r8d, r14d
0x18006fc02  mov     [rsp+0C0h+var_A0], rax
0x18006fc07  call    McTemplateU0qqxx_EventWriteTransfer
0x18006fc0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fc13  test    sil, sil
0x18006fc16  jz      loc_18006FEF7
0x18006fc1c  test    r13b, r13b
0x18006fc1f  jz      loc_18006FFAB
0x18006fc25  mov     edx, [rbp+47h+arg_0]
0x18006fc28  sub     edx, 1
0x18006fc2b  jz      loc_18006FE7C
0x18006fc31  sub     edx, 1
0x18006fc34  jz      loc_18006FE0E
0x18006fc3a  sub     edx, 1
0x18006fc3d  jz      loc_18006FD9D
0x18006fc43  sub     edx, 1
0x18006fc46  jz      loc_18006FD45
0x18006fc4c  sub     edx, 1
0x18006fc4f  jz      loc_18006FCED
0x18006fc55  cmp     edx, 1
0x18006fc58  jz      short loc_18006FC98
0x18006fc5a  lea     rdi, WPP_GLOBAL_Control
0x18006fc61  cmp     rcx, rdi
0x18006fc64  jz      loc_18006FEFE
0x18006fc6a  test    byte ptr [rcx+1Ch], 2
0x18006fc6e  jz      loc_18006FEFE
0x18006fc74  cmp     byte ptr [rcx+19h], 2
0x18006fc78  jb      loc_18006FEFE
0x18006fc7e  mov     edx, 4Ah ; 'J'
0x18006fc83  mov     rcx, [rcx+10h]
0x18006fc87  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006fc8e  call    WPP_SF_
0x18006fc93  jmp     loc_1800702AF
0x18006fc98  mov     rcx, [rbp+47h+var_78]
0x18006fc9c  mov     r8d, edi
0x18006fc9f  mov     edx, r15d
0x18006fca2  mov     rax, [rcx]
0x18006fca5  mov     rax, [rax+58h]
0x18006fca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcae  mov     ebx, eax
0x18006fcb0  test    eax, eax
0x18006fcb2  jns     loc_18006FEF0
0x18006fcb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fcbf  lea     rdi, WPP_GLOBAL_Control
0x18006fcc6  cmp     rcx, rdi
0x18006fcc9  jz      loc_18006FEFE
0x18006fccf  test    byte ptr [rcx+1Ch], 2
0x18006fcd3  jz      loc_18006FEFE
0x18006fcd9  cmp     byte ptr [rcx+19h], 2
0x18006fcdd  jb      loc_18006FEFE
0x18006fce3  mov     edx, 49h ; 'I'
0x18006fce8  jmp     loc_18006FED8
0x18006fced  mov     rcx, [rbp+47h+var_78]
0x18006fcf1  mov     r9d, edi
0x18006fcf4  mov     r8, r12
0x18006fcf7  mov     edx, r15d
0x18006fcfa  mov     rax, [rcx]
0x18006fcfd  mov     rax, [rax+50h]
0x18006fd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fd06  mov     ebx, eax
0x18006fd08  test    eax, eax
0x18006fd0a  jns     loc_18006FEF0
0x18006fd10  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fd17  lea     rdi, WPP_GLOBAL_Control
0x18006fd1e  cmp     rcx, rdi
0x18006fd21  jz      loc_18006FEFE
0x18006fd27  test    byte ptr [rcx+1Ch], 2
0x18006fd2b  jz      loc_18006FEFE
0x18006fd31  cmp     byte ptr [rcx+19h], 2
0x18006fd35  jb      loc_18006FEFE
0x18006fd3b  mov     edx, 48h ; 'H'
0x18006fd40  jmp     loc_18006FED8
0x18006fd45  mov     rcx, [rbp+47h+var_78]
0x18006fd49  mov     r9d, edi
  ... truncated ...
```
