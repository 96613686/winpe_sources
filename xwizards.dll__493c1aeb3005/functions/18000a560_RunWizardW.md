# RunWizardW

- ea: `0x18000a560`
- end: `0x18000add6`
- name: `RunWizardW`
- size: `2166`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a380`
- `0x18000a4b0`

## callees

- `0x180004370`
- `0x180005ce8`
- `0x180005e30`
- `0x1800095d0`
- `0x18000a560`
- `0x18000ae04`
- `0x18000ae44`
- `0x18000ae90`
- `0x18000af08`
- `0x18000e560`
- `0x18000e638`
- `0x18000e87c`
- `0x18000e8dc`
- `0x1800329f6`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a7da`
- `msvcrt!_wcsicmp` at `0x18000a7f7`
- `msvcrt!_wcsicmp` at `0x18000a817`
- `msvcrt!_wcsicmp` at `0x18000a838`
- `msvcrt!_wcsicmp` at `0x18000a858`
- `msvcrt!_wcsicmp` at `0x18000a7da`
- `msvcrt!_wcsicmp` at `0x18000a7f7`
- `msvcrt!_wcsicmp` at `0x18000a817`
- `msvcrt!_wcsicmp` at `0x18000a838`
- `msvcrt!_wcsicmp` at `0x18000a858`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a66c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a8c6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a66c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000a8c6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aa8c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000aa8c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000aa4a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000aa4a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ab78`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ab78`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000abc1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ac2a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000acc3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000abc1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ac2a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000acc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000acfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000acfe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad81`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000a5bc`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000a5bc`
- `USER32!MessageBoxW` at `0x18000ad37`
- `USER32!MessageBoxW` at `0x18000ad37`
- `USER32!SetProcessDPIAware` at `0x18000a617`
- `USER32!SetProcessDPIAware` at `0x18000a617`

## pseudocode

```c
__int64 __fastcall RunWizardW(va_list hWnd, __int64 a2, const WCHAR *a3)
{
  HWND v3; // r15
  const unsigned __int16 *v4; // rdi
  unsigned __int16 **v5; // rsi
  HRESULT LastErrorHRESULT; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // r14d
  PVOID *v10; // rcx
  unsigned __int16 *v12; // r8
  HRESULT v13; // eax
  __int64 v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rdi
  const wchar_t *v17; // rdi
  int v18; // eax
  int v19; // edx
  HRESULT v20; // eax
  HRESULT v21; // edi
  __int64 v22; // r15
  unsigned int v23; // edi
  int v24; // esi
  __int64 (__fastcall *v25)(__int64, va_list, GUID *, GUID *, int, int, unsigned __int16 *, _QWORD, unsigned int); // r14
  GUID *p_pclsid; // rbx
  int v27; // eax
  GUID *p_Buf1; // r8
  int v29; // edi
  unsigned int v30; // eax
  PVOID *v31; // rcx
  unsigned int v32; // eax
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned int v37; // [rsp+40h] [rbp-79h]
  WCHAR v38[4]; // [rsp+50h] [rbp-69h] BYREF
  int v39; // [rsp+58h] [rbp-61h]
  int pNumArgs; // [rsp+5Ch] [rbp-5Dh] BYREF
  WCHAR Buffer[4]; // [rsp+60h] [rbp-59h] BYREF
  WCHAR v42[4]; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v43; // [rsp+70h] [rbp-49h] BYREF
  int v44; // [rsp+74h] [rbp-45h]
  va_list Arguments[2]; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int16 *v46; // [rsp+88h] [rbp-31h]
  HLOCAL hMem; // [rsp+90h] [rbp-29h]
  GUID pclsid; // [rsp+98h] [rbp-21h] BYREF
  GUID Buf1; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int16 v50[16]; // [rsp+B8h] [rbp-1h] BYREF

  Arguments[0] = hWnd;
  v3 = (HWND)hWnd;
  *(_DWORD *)v42 = 0;
  v43 = 0;
  pNumArgs = 0;
  *(_QWORD *)v38 = a3;
  v4 = a3;
  Buf1 = 0;
  pclsid = 0;
  hMem = CommandLineToArgvW(a3, &pNumArgs);
  v5 = (unsigned __int16 **)hMem;
  if ( !hMem )
  {
    LastErrorHRESULT = GetLastErrorHRESULT();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v8 = 50;
      goto LABEL_121;
    }
    return (unsigned int)LastErrorHRESULT;
  }
  LastErrorHRESULT = 0;
  v44 = 0;
  v9 = 0;
  v39 = 0;
  v46 = 0;
  SetProcessDPIAware();
  v10 = (PVOID *)WPP_GLOBAL_Control;
  while ( pNumArgs-- )
  {
    v12 = *v5;
    if ( ((**v5 - 45) & 0xFFFD) != 0 )
    {
      if ( !(unsigned int)IsValidGUIDString(*v5) )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            59,
            (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
            (unsigned int)*v5,
            LastErrorHRESULT);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
        LastErrorHRESULT = -2147024809;
        goto LABEL_71;
      }
      v13 = CLSIDFromString(*v5, &pclsid);
      LastErrorHRESULT = v13;
      if ( v13 >= 0 )
        goto LABEL_69;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v14 = 58;
        goto LABEL_13;
      }
    }
    else
    {
      switch ( v12[1] )
      {
        case '?':
          LastErrorHRESULT = 1;
          DisplayUsage(v3, 0xBu, (v9 != 0) + 13);
          goto LABEL_118;
        case 'c':
          v18 = HrStringToDWORD(v12 + 2, &v43);
          LastErrorHRESULT = v18;
          if ( v18 >= 0 )
            goto LABEL_69;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v19 = 53;
LABEL_68:
            WPP_SF_SD(
              (unsigned int)v10[2],
              v19,
              (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
              *(_DWORD *)v5 + 4,
              v18);
LABEL_69:
            v10 = (PVOID *)WPP_GLOBAL_Control;
          }
          break;
        case 'f':
          v18 = HrStringToDWORD(v12 + 2, (unsigned int *)v42);
          LastErrorHRESULT = v18;
          if ( v18 >= 0 )
            goto LABEL_69;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v19 = 54;
            goto LABEL_68;
          }
          break;
        case 'p':
          if ( (unsigned int)IsValidGUIDString(v12 + 2) )
          {
            v13 = CLSIDFromString(*v5 + 2, &Buf1);
            LastErrorHRESULT = v13;
            if ( v13 >= 0 )
              goto LABEL_69;
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v14 = 55;
LABEL_13:
              WPP_SF_d(v10[2], v14, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v13);
              goto LABEL_69;
            }
          }
          else
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                56,
                (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
                *(_DWORD *)v5 + 4,
                LastErrorHRESULT);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            LastErrorHRESULT = -2147024809;
          }
          break;
        default:
          switch ( v12[1] )
          {
            case 't':
              v17 = v12 + 2;
              if ( v12 == (unsigned __int16 *)-4LL )
              {
                LastErrorHRESULT = -2147024809;
                if ( v10 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v10 + 28) & 0x10) != 0 )
                  {
                    WPP_SF_d(v10[2], 51, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, 2147942487LL);
LABEL_28:
                    v10 = (PVOID *)WPP_GLOBAL_Control;
                  }
LABEL_71:
                  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
                    WPP_SF_SD(
                      (unsigned int)v10[2],
                      60,
                      (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
                      (unsigned int)*v5,
                      87);
                }
LABEL_74:
                v4 = *(const unsigned __int16 **)v38;
LABEL_75:
                DisplayInvalidOption(v3, 0xCu, *v5);
                DisplayUsage(v3, 0xBu, (v9 != 0) + 13);
                v10 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_76;
              }
              if ( _wcsicmp(L"dui", v12 + 2) )
              {
                if ( _wcsicmp(L"moderndui", v17) )
                {
                  if ( _wcsicmp(L"propertysheet97", v17) )
                  {
                    if ( _wcsicmp(L"wizard97", v17) )
                    {
                      if ( _wcsicmp(L"aero", v17) )
                      {
                        LastErrorHRESULT = -2147024809;
                        v10 = (PVOID *)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                          goto LABEL_74;
                        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
                          goto LABEL_71;
                        WPP_SF_SD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          52,
                          (unsigned int)WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
                          (_DWORD)v17,
                          87);
                      }
                      else
                      {
                        v39 = 32;
                      }
                    }
                    else
                    {
                      v39 = 2;
                    }
                  }
                  else
                  {
                    v9 = 1;
                    v39 = 1;
                  }
                }
                else
                {
                  v39 = 1024;
                }
              }
              else
              {
                v39 = 512;
              }
              break;
            case 'u':
              v44 = 1;
              goto LABEL_70;
            case 'z':
              pNumArgs = 0;
              v15 = wcsistr(v4, *v5);
              v16 = v15 + 2;
              if ( !v15 )
                v16 = 0;
              v46 = v16;
              break;
            default:
              LastErrorHRESULT = -2147024809;
              if ( v10 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v10 + 28) & 0x10) != 0 )
                {
                  WPP_SF_hD(v10[2], 57, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v12[1], -2147024809);
                  goto LABEL_28;
                }
                goto LABEL_71;
              }
              goto LABEL_75;
          }
          v4 = *(const unsigned __int16 **)v38;
          goto LABEL_69;
      }
    }
LABEL_70:
    if ( LastErrorHRESULT == -2147024809 )
      goto LABEL_71;
LABEL_76:
    ++v5;
    if ( LastErrorHRESULT )
      goto LABEL_118;
  }
  v20 = CoInitializeEx(0, 6u);
  *(_DWORD *)v38 = v20;
  LastErrorHRESULT = 0;
  v21 = v20;
  if ( v20 != -2147417850 )
    LastErrorHRESULT = v20;
  if ( LastErrorHRESULT < 0 )
    goto LABEL_93;
  *(_QWORD *)Buffer = 0;
  LastErrorHRESULT = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, (LPVOID *)Buffer);
  if ( LastErrorHRESULT >= 0 )
  {
    LastErrorHRESULT = (*(__int64 (__fastcall **)(_QWORD, __int64, HWND))(**(_QWORD **)Buffer + 216LL))(
                         *(_QWORD *)Buffer,
                         1,
                         v3);
    if ( LastErrorHRESULT >= 0 )
    {
      v22 = *(_QWORD *)Buffer;
      v23 = v43;
      v24 = *(_DWORD *)v42;
      v25 = *(__int64 (__fastcall **)(__int64, va_list, GUID *, GUID *, int, int, unsigned __int16 *, _QWORD, unsigned int))(**(_QWORD **)Buffer + 176LL);
      p_pclsid = &pclsid;
      if ( !memcmp_0(&pclsid, &GUID_NULL, 0x10u) )
        p_pclsid = 0;
      v27 = memcmp_0(&Buf1, &GUID_NULL, 0x10u);
      v37 = v23;
      p_Buf1 = &Buf1;
      if ( !v27 )
        p_Buf1 = 0;
      v21 = *(_DWORD *)v38;
      LastErrorHRESULT = v25(v22, Arguments[0], p_Buf1, p_pclsid, v39, v24, v46, 0, v37);
      v3 = (HWND)Arguments[0];
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Buffer + 16LL))(*(_QWORD *)Buffer);
  }
  if ( v21 != -2147417850 )
    CoUninitialize();
  if ( LastErrorHRESULT < 0 )
  {
LABEL_93:
    if ( LastErrorHRESULT != -2147023673 )
    {
      v29 = 0;
      *(_QWORD *)Buffer = 0;
      *(_QWORD *)v38 = 0;
      if ( FormatMessageW(0x900u, lpSource, 0xCu, 0, Buffer, 0, 0) )
        goto LABEL_99;
      v30 = GetLastErrorHRESULT();
      v29 = v30;
      v31 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v30);
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v29 >= 0 )
      {
LABEL_99:
        *(_QWORD *)v42 = 0;
        if ( !FormatMessageW(0x1100u, 0, LastErrorHRESULT, 0, v42, 0, 0) )
        {
          v32 = GetLastErrorHRESULT();
          v29 = v32;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v32);
        }
        if ( v29 >= 0 )
        {
          *(_OWORD *)Arguments = 0;
          swprintf_sfn(v50, 0xDu, L"%#X", (unsigned int)LastErrorHRESULT);
          Arguments[0] = (va_list)v50;
          Arguments[1] = *(va_list *)v42;
          if ( !FormatMessageW(0x2900u, lpSource, 0xC000000F, 0, v38, 0, Arguments) )
          {
            v33 = GetLastErrorHRESULT();
            v29 = v33;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, v33);
          }
        }
        LocalFree(*(HLOCAL *)v42);
        if ( v29 >= 0 )
        {
          if ( v44 )
          {
            if ( (Microsoft_Windows_XWizardsEnableBits & 4) != 0 )
              McTemplateU0zz_EventWriteTransfer(v35, v34, *(_QWORD *)Buffer, *(_QWORD *)v38);
          }
          else
          {
            MessageBoxW(v3, *(LPCWSTR *)v38, *(LPCWSTR *)Buffer, 0x10u);
          }
          goto LABEL_117;
        }
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 4) != 0 )
        WPP_SF_DD(v31[2], 64, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v29, LastErrorHRESULT);
LABEL_117:
      LocalFree(*(HLOCAL *)Buffer);
      LocalFree(*(HLOCAL *)v38);
    }
  }
LABEL_118:
  LocalFree(hMem);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v8 = 65;
LABEL_121:
    WPP_SF_d(v7[2], v8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)LastErrorHRESULT);
  }
  return (unsigned int)LastErrorHRESULT;
}

```

## disassembly

```asm
0x18000a560  mov     [rsp-8+arg_8], rbx
0x18000a565  push    rbp
0x18000a566  push    rsi
0x18000a567  push    rdi
0x18000a568  push    r12
0x18000a56a  push    r13
0x18000a56c  push    r14
0x18000a56e  push    r15
0x18000a570  lea     rbp, [rsp-27h]
0x18000a575  sub     rsp, 0E0h
0x18000a57c  mov     rax, cs:__security_cookie
0x18000a583  xor     rax, rsp
0x18000a586  mov     [rbp+57h+var_38], rax
0x18000a58a  xor     r12d, r12d
0x18000a58d  mov     [rbp+57h+var_98], rcx
0x18000a591  mov     r15, rcx
0x18000a594  mov     dword ptr [rbp+57h+var_A8], r12d
0x18000a598  xorps   xmm0, xmm0
0x18000a59b  mov     [rbp+57h+var_A0], r12d
0x18000a59f  xorps   xmm1, xmm1
0x18000a5a2  mov     [rbp+57h+pNumArgs], r12d
0x18000a5a6  mov     rcx, r8; lpCmdLine
0x18000a5a9  mov     qword ptr [rbp+57h+var_C0], r8
0x18000a5ad  lea     rdx, [rbp+57h+pNumArgs]; pNumArgs
0x18000a5b1  mov     rdi, r8
0x18000a5b4  movups  xmmword ptr [rbp+57h+Buf1.Data1], xmm0
0x18000a5b8  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm1
0x18000a5bc  call    cs:__imp_CommandLineToArgvW
0x18000a5c2  mov     [rbp+57h+hMem], rax
0x18000a5c6  mov     rsi, rax
0x18000a5c9  test    rax, rax
0x18000a5cc  jnz     short loc_18000A605
0x18000a5ce  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18000a5d3  mov     ebx, eax
0x18000a5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5dc  lea     r12, WPP_GLOBAL_Control
0x18000a5e3  cmp     rcx, r12
0x18000a5e6  jz      loc_18000ADAD
0x18000a5ec  test    byte ptr [rcx+1Ch], 4
0x18000a5f0  jz      loc_18000ADAD
0x18000a5f6  lea     edx, [rsi+32h]
0x18000a5f9  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000a600  jmp     loc_18000ADA1
0x18000a605  mov     ebx, r12d
0x18000a608  mov     [rbp+57h+var_9C], r12d
0x18000a60c  mov     r14d, r12d
0x18000a60f  mov     [rbp+57h+var_B8], r12d
0x18000a613  mov     [rbp+57h+var_88], r12
0x18000a617  call    cs:__imp_SetProcessDPIAware
0x18000a61d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a624  lea     r12, WPP_GLOBAL_Control
0x18000a62b  lea     r13, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000a632  mov     eax, [rbp+57h+pNumArgs]
0x18000a635  dec     [rbp+57h+pNumArgs]
0x18000a638  test    eax, eax
0x18000a63a  jz      loc_18000AA43
0x18000a640  mov     r8, [rsi]
0x18000a643  mov     edx, 0FFFDh
0x18000a648  movzx   eax, word ptr [r8]
0x18000a64c  sub     ax, 2Dh ; '-'
0x18000a650  test    dx, ax
0x18000a653  jz      loc_18000A6EA
0x18000a659  mov     rcx, r8; unsigned __int16 *
0x18000a65c  call    ?IsValidGUIDString@@YAHPEAG@Z; IsValidGUIDString(ushort *)
0x18000a661  test    eax, eax
0x18000a663  jz      short loc_18000A6AF
0x18000a665  mov     rcx, [rsi]; lpsz
0x18000a668  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18000a66c  call    cs:__imp_CLSIDFromString
0x18000a672  mov     ebx, eax
0x18000a674  test    eax, eax
0x18000a676  jns     loc_18000A9A3
0x18000a67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a683  cmp     rcx, r12
0x18000a686  jz      loc_18000A9AA
0x18000a68c  test    byte ptr [rcx+1Ch], 4
0x18000a690  jz      loc_18000A9AA
0x18000a696  mov     edx, 3Ah ; ':'
0x18000a69b  mov     rcx, [rcx+10h]
0x18000a69f  mov     r9d, eax
0x18000a6a2  mov     r8, r13
0x18000a6a5  call    WPP_SF_d
0x18000a6aa  jmp     loc_18000A9A3
0x18000a6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6b6  cmp     rcx, r12
0x18000a6b9  jz      short loc_18000A6E0
0x18000a6bb  test    byte ptr [rcx+1Ch], 10h
0x18000a6bf  jz      short loc_18000A6E0
0x18000a6c1  mov     r9, [rsi]
0x18000a6c4  mov     edx, 3Bh ; ';'
0x18000a6c9  mov     rcx, [rcx+10h]
0x18000a6cd  mov     r8, r13
0x18000a6d0  mov     dword ptr [rsp+110h+ppv], ebx
0x18000a6d4  call    WPP_SF_SD
0x18000a6d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6e0  mov     ebx, 80070057h
0x18000a6e5  jmp     loc_18000A9B2
0x18000a6ea  movzx   r9d, word ptr [r8+2]
0x18000a6ef  mov     edx, r9d
0x18000a6f2  sub     edx, 3Fh ; '?'
0x18000a6f5  jz      loc_18000AA21
0x18000a6fb  sub     edx, 24h ; '$'
0x18000a6fe  jz      loc_18000A962
0x18000a704  sub     edx, 3
0x18000a707  jz      loc_18000A936
0x18000a70d  sub     edx, 0Ah
0x18000a710  jz      loc_18000A8AE
0x18000a716  sub     edx, 4
0x18000a719  jz      short loc_18000A798
0x18000a71b  sub     edx, 1
0x18000a71e  jz      short loc_18000A78C
0x18000a720  cmp     edx, 5
0x18000a723  jz      short loc_18000A762
0x18000a725  mov     ebx, 80070057h
0x18000a72a  cmp     rcx, r12
0x18000a72d  jz      loc_18000A9DD
0x18000a733  test    byte ptr [rcx+1Ch], 10h
0x18000a737  jz      loc_18000A9B2
0x18000a73d  mov     rcx, [rcx+10h]
0x18000a741  mov     edx, 39h ; '9'
0x18000a746  mov     r8, r13
0x18000a749  mov     dword ptr [rsp+110h+ppv], 80070057h
0x18000a751  call    WPP_SF_hD
0x18000a756  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a75d  jmp     loc_18000A9B2
0x18000a762  mov     [rbp+57h+pNumArgs], 0
0x18000a769  mov     rcx, rdi; unsigned __int16 *
0x18000a76c  mov     rdx, [rsi]; unsigned __int16 *
0x18000a76f  call    ?wcsistr@@YAPEAGPEBG0@Z; wcsistr(ushort const *,ushort const *)
0x18000a774  test    rax, rax
0x18000a777  lea     rdi, [rax+4]
0x18000a77b  cmovz   rdi, rax
0x18000a77f  mov     [rbp+57h+var_88], rdi
0x18000a783  mov     rdi, qword ptr [rbp+57h+var_C0]
0x18000a787  jmp     loc_18000A9A3
0x18000a78c  mov     [rbp+57h+var_9C], 1
0x18000a793  jmp     loc_18000A9AA
0x18000a798  lea     rdi, [r8+4]
0x18000a79c  test    rdi, rdi
0x18000a79f  jnz     short loc_18000A7D0
0x18000a7a1  mov     ebx, 80070057h
0x18000a7a6  cmp     rcx, r12
0x18000a7a9  jz      loc_18000A9D9
0x18000a7af  test    byte ptr [rcx+1Ch], 10h
0x18000a7b3  jz      loc_18000A9B2
0x18000a7b9  mov     rcx, [rcx+10h]
0x18000a7bd  lea     edx, [rdi+33h]
0x18000a7c0  mov     r9d, 80070057h
0x18000a7c6  mov     r8, r13
0x18000a7c9  call    WPP_SF_d
0x18000a7ce  jmp     short loc_18000A756
0x18000a7d0  mov     rdx, rdi; String2
0x18000a7d3  lea     rcx, aDui; "dui"
0x18000a7da  call    cs:__imp__wcsicmp
0x18000a7e0  test    eax, eax
0x18000a7e2  jnz     short loc_18000A7ED
0x18000a7e4  mov     [rbp+57h+var_B8], 200h
0x18000a7eb  jmp     short loc_18000A783
0x18000a7ed  mov     rdx, rdi; String2
0x18000a7f0  lea     rcx, aModerndui; "moderndui"
0x18000a7f7  call    cs:__imp__wcsicmp
0x18000a7fd  test    eax, eax
0x18000a7ff  jnz     short loc_18000A80D
0x18000a801  mov     [rbp+57h+var_B8], 400h
0x18000a808  jmp     loc_18000A783
0x18000a80d  mov     rdx, rdi; String2
0x18000a810  lea     rcx, aPropertysheet9; "propertysheet97"
0x18000a817  call    cs:__imp__wcsicmp
0x18000a81d  test    eax, eax
0x18000a81f  jnz     short loc_18000A82E
0x18000a821  lea     r14d, [rax+1]
0x18000a825  mov     [rbp+57h+var_B8], r14d
0x18000a829  jmp     loc_18000A783
0x18000a82e  mov     rdx, rdi; String2
0x18000a831  lea     rcx, aWizard97; "wizard97"
0x18000a838  call    cs:__imp__wcsicmp
0x18000a83e  test    eax, eax
0x18000a840  jnz     short loc_18000A84E
0x18000a842  mov     [rbp+57h+var_B8], 2
0x18000a849  jmp     loc_18000A783
0x18000a84e  mov     rdx, rdi; String2
0x18000a851  lea     rcx, aAero; "aero"
0x18000a858  call    cs:__imp__wcsicmp
0x18000a85e  test    eax, eax
0x18000a860  jnz     short loc_18000A86E
0x18000a862  mov     [rbp+57h+var_B8], 20h ; ' '
0x18000a869  jmp     loc_18000A783
0x18000a86e  mov     ebx, 80070057h
0x18000a873  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a87a  cmp     rcx, r12
0x18000a87d  jz      loc_18000A9D9
0x18000a883  test    byte ptr [rcx+1Ch], 10h
0x18000a887  jz      loc_18000A9B2
0x18000a88d  mov     rcx, [rcx+10h]
0x18000a891  mov     edx, 34h ; '4'
0x18000a896  mov     r9, rdi
0x18000a899  mov     dword ptr [rsp+110h+ppv], 80070057h
0x18000a8a1  mov     r8, r13
0x18000a8a4  call    WPP_SF_SD
0x18000a8a9  jmp     loc_18000A783
0x18000a8ae  lea     rcx, [r8+4]; unsigned __int16 *
0x18000a8b2  call    ?IsValidGUIDString@@YAHPEAG@Z; IsValidGUIDString(ushort *)
0x18000a8b7  test    eax, eax
0x18000a8b9  jz      short loc_18000A8FA
0x18000a8bb  mov     rcx, [rsi]
0x18000a8be  lea     rdx, [rbp+57h+Buf1]; pclsid
0x18000a8c2  add     rcx, 4; lpsz
0x18000a8c6  call    cs:__imp_CLSIDFromString
0x18000a8cc  mov     ebx, eax
0x18000a8ce  test    eax, eax
0x18000a8d0  jns     loc_18000A9A3
0x18000a8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8dd  cmp     rcx, r12
0x18000a8e0  jz      loc_18000A9AA
0x18000a8e6  test    byte ptr [rcx+1Ch], 4
0x18000a8ea  jz      loc_18000A9AA
0x18000a8f0  mov     edx, 37h ; '7'
0x18000a8f5  jmp     loc_18000A69B
0x18000a8fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a901  cmp     rcx, r12
0x18000a904  jz      short loc_18000A92F
0x18000a906  test    byte ptr [rcx+1Ch], 10h
0x18000a90a  jz      short loc_18000A92F
0x18000a90c  mov     r9, [rsi]
0x18000a90f  mov     edx, 38h ; '8'
0x18000a914  mov     rcx, [rcx+10h]
0x18000a918  add     r9, 4
0x18000a91c  mov     r8, r13
0x18000a91f  mov     dword ptr [rsp+110h+ppv], ebx
0x18000a923  call    WPP_SF_SD
0x18000a928  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a92f  mov     ebx, 80070057h
0x18000a934  jmp     short loc_18000A9AA
0x18000a936  lea     rcx, [r8+4]; unsigned __int16 *
0x18000a93a  lea     rdx, [rbp+57h+var_A8]; unsigned int *
0x18000a93e  call    ?HrStringToDWORD@@YAJPEAGPEAK@Z; HrStringToDWORD(ushort *,ulong *)
0x18000a943  mov     ebx, eax
0x18000a945  test    eax, eax
0x18000a947  jns     short loc_18000A9A3
0x18000a949  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a950  cmp     rcx, r12
0x18000a953  jz      short loc_18000A9AA
0x18000a955  test    byte ptr [rcx+1Ch], 4
0x18000a959  jz      short loc_18000A9AA
0x18000a95b  mov     edx, 36h ; '6'
0x18000a960  jmp     short loc_18000A98C
0x18000a962  lea     rcx, [r8+4]; unsigned __int16 *
0x18000a966  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x18000a96a  call    ?HrStringToDWORD@@YAJPEAGPEAK@Z; HrStringToDWORD(ushort *,ulong *)
0x18000a96f  mov     ebx, eax
0x18000a971  test    eax, eax
0x18000a973  jns     short loc_18000A9A3
0x18000a975  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a97c  cmp     rcx, r12
0x18000a97f  jz      short loc_18000A9AA
0x18000a981  test    byte ptr [rcx+1Ch], 4
0x18000a985  jz      short loc_18000A9AA
0x18000a987  mov     edx, 35h ; '5'
0x18000a98c  mov     r9, [rsi]
0x18000a98f  mov     r8, r13
0x18000a992  mov     rcx, [rcx+10h]
0x18000a996  add     r9, 4
0x18000a99a  mov     dword ptr [rsp+110h+ppv], eax
0x18000a99e  call    WPP_SF_SD
0x18000a9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9aa  cmp     ebx, 80070057h
0x18000a9b0  jnz     short loc_18000AA10
0x18000a9b2  cmp     rcx, r12
0x18000a9b5  jz      short loc_18000A9D9
0x18000a9b7  test    byte ptr [rcx+1Ch], 10h
0x18000a9bb  jz      short loc_18000A9D9
0x18000a9bd  mov     r9, [rsi]
0x18000a9c0  mov     edx, 3Ch ; '<'
0x18000a9c5  mov     rcx, [rcx+10h]
0x18000a9c9  mov     r8, r13
0x18000a9cc  mov     dword ptr [rsp+110h+ppv], 80070057h
0x18000a9d4  call    WPP_SF_SD
0x18000a9d9  mov     rdi, qword ptr [rbp+57h+var_C0]
0x18000a9dd  mov     r8, [rsi]; unsigned __int16 *
0x18000a9e0  mov     edx, 0Ch; dwMessageId
0x18000a9e5  mov     rcx, r15; hWnd
0x18000a9e8  call    ?DisplayInvalidOption@@YAXPEAUHWND__@@KPEAG@Z; DisplayInvalidOption(HWND__ *,ulong,ushort *)
0x18000a9ed  mov     eax, r14d
0x18000a9f0  mov     edx, 0Bh; dwMessageId
0x18000a9f5  neg     eax
0x18000a9f7  mov     rcx, r15; hWnd
0x18000a9fa  sbb     r8d, r8d
0x18000a9fd  neg     r8d
0x18000aa00  add     r8d, 0Dh; DWORD
0x18000aa04  call    ?DisplayUsage@@YAXPEAUHWND__@@KK@Z; DisplayUsage(HWND__ *,ulong,ulong)
0x18000aa09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa10  add     rsi, 8
0x18000aa14  test    ebx, ebx
0x18000aa16  jz      loc_18000A632
0x18000aa1c  jmp     loc_18000AD7D
0x18000aa21  neg     r14d
0x18000aa24  mov     ebx, 1
0x18000aa29  mov     rcx, r15; hWnd
0x18000aa2c  sbb     r8d, r8d
0x18000aa2f  neg     r8d
  ... truncated ...
```
