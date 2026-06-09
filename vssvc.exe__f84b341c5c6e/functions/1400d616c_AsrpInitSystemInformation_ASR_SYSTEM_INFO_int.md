# AsrpInitSystemInformation(_ASR_SYSTEM_INFO *,int)

- ea: `0x1400d616c`
- end: `0x1400d6699`
- name: `?AsrpInitSystemInformation@@YAHPEAU_ASR_SYSTEM_INFO@@H@Z`
- size: `1325`
- prototype: `__int64 __fastcall(struct _ASR_SYSTEM_INFO *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400768c4`

## callees

- `0x140021ca0`
- `0x1400227a0`
- `0x1400235a8`
- `0x1400242a0`
- `0x140025abc`
- `0x14005646c`
- `0x140091560`
- `0x1400921dc`
- `0x1400d257c`
- `0x1400d616c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6669`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d6669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d61f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d621f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d62ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d642f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d647a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d64a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d650b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d657a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d65a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d61f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d621f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d62ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d642f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d647a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d64a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d650b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d6534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d657a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d65a3`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1400d626e`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1400d626e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400d63b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1400d63b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400d6401`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400d6401`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400d62f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400d62f3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1400d61ea`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1400d61ea`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1400d646d`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x1400d646d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d63d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d6383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400d63d3`

## string_xrefs

- `0x1400d65de`: `pSystemInfo->BootWinDirectory`
- `0x1400d656f`: `pSystemInfo->BootSysDirectory`
- `0x1400d64f8`: `pSystemInfo->SystemPath`

## pseudocode

```c
__int64 __fastcall AsrpInitSystemInformation(LPVOID *a1)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  DWORD v4; // eax
  int v5; // edx
  WCHAR *v6; // rax
  DWORD EnvironmentVariableW; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v8; // rax
  int v9; // edx
  const char *v10; // rcx
  enum _FIRMWARE_TYPE FirmwareType; // eax
  UINT v12; // ebp
  UINT v13; // esi
  WCHAR *v14; // rax
  __int64 v15; // r14
  UINT SystemWindowsDirectoryW; // eax
  WCHAR *v17; // rax
  __int64 v18; // rsi
  UINT SystemDirectoryW; // eax
  unsigned int v20; // edx
  unsigned __int16 *v21; // rax
  int v22; // r9d
  const char *v23; // rcx
  const char *v25; // [rsp+20h] [rbp-248h]
  unsigned __int16 v26; // [rsp+30h] [rbp-238h] BYREF
  _BYTE v27[526]; // [rsp+32h] [rbp-236h] BYREF

  TraceFunctionEnter(L"AsrpInitSystemInformation");
  v26 = 0;
  memset_0(v27, 0, 0x206u);
  if ( !a1 )
  {
    v2 = 0;
    LastError = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_67;
    }
    v25 = "pSystemInfo";
    v9 = 58;
    goto LABEL_65;
  }
  memset_0(a1, 0, 0x220u);
  v2 = 1;
  *((_DWORD *)a1 + 13) = 16;
  *((_DWORD *)a1 + 12) = 1;
  if ( !GetComputerNameW((LPWSTR)a1 + 28, (LPDWORD)a1 + 13) )
  {
    v2 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v4 = GetLastError();
      v5 = 59;
LABEL_6:
      WPP_SF_Ds(
        *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
        v5,
        (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
        v4,
        "GetLastError( )");
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  v6 = (WCHAR *)ASR_ALLOC(0xCu);
  a1[3] = v6;
  if ( !v6 )
  {
    v2 = 0;
    v22 = 14;
    LastError = 14;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_67;
    }
    v9 = 60;
    v23 = "pSystemInfo->Platform";
LABEL_46:
    v25 = v23;
LABEL_66:
    WPP_SF_Ds(
      *(_QWORD *)v8->Gpt.DiskId.Data4,
      v9,
      (unsigned int)WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids,
      v22,
      v25);
    goto LABEL_67;
  }
  EnvironmentVariableW = GetEnvironmentVariableW(L"PROCESSOR_ARCHITECTURE", v6, 6u);
  if ( !EnvironmentVariableW )
  {
    v2 = 0;
    LastError = 10;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_67;
    }
    v9 = 61;
    v10 = "ERROR_BAD_ENVIRONMENT";
LABEL_12:
    v25 = v10;
LABEL_65:
    v22 = LastError;
    goto LABEL_66;
  }
  if ( EnvironmentVariableW > 6 )
  {
    v2 = 0;
    LastError = 50;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_67;
    }
    v9 = 62;
    v10 = "ERROR_NOT_SUPPORTED";
    goto LABEL_12;
  }
  *((_DWORD *)a1 + 22) = 284;
  if ( GetVersionExW((LPOSVERSIONINFOW)(a1 + 11)) )
  {
    FirmwareType = SystemGetFirmwareType();
    *((_DWORD *)a1 + 8) = FirmwareType;
    if ( FirmwareType )
    {
      v12 = 260;
      v13 = 260;
      while ( 1 )
      {
        CoTaskMemFree(*a1);
        *a1 = 0;
        v14 = (WCHAR *)ASR_ALLOC(2 * v13 + 2);
        *a1 = v14;
        if ( !v14 )
          break;
        v15 = v13;
        SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v14, v13);
        v13 = SystemWindowsDirectoryW;
        if ( !SystemWindowsDirectoryW )
        {
          v2 = 0;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v4 = GetLastError();
            v5 = 66;
            goto LABEL_6;
          }
          goto LABEL_67;
        }
        if ( SystemWindowsDirectoryW <= (unsigned int)v15 )
        {
          *((_WORD *)*a1 + v15) = 0;
          while ( 1 )
          {
            CoTaskMemFree(a1[1]);
            a1[1] = 0;
            v17 = (WCHAR *)ASR_ALLOC(2 * v12 + 2);
            a1[1] = v17;
            if ( !v17 )
              break;
            v18 = v12;
            SystemDirectoryW = GetSystemDirectoryW(v17, v12);
            v12 = SystemDirectoryW;
            if ( !SystemDirectoryW )
            {
              v2 = 0;
              LastError = GetLastError();
              if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
              {
                v4 = GetLastError();
                v5 = 68;
                goto LABEL_6;
              }
              goto LABEL_67;
            }
            if ( SystemDirectoryW <= (unsigned int)v18 )
            {
              *((_WORD *)a1[1] + v18) = 0;
              if ( (unsigned int)AsrGetSystemVolumeDevPath(&v26, v20) )
              {
                if ( GetTimeZoneInformation((LPTIME_ZONE_INFORMATION)((char *)a1 + 372)) == -1 )
                {
                  v2 = 0;
                  LastError = GetLastError();
                  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
                  {
                    v4 = GetLastError();
                    v5 = 70;
                    goto LABEL_6;
                  }
                }
                else
                {
                  v21 = SafeStrClone(&v26);
                  a1[2] = v21;
                  if ( v21 )
                  {
                    LastError = 0;
                    goto LABEL_67;
                  }
                  v2 = 0;
                  v22 = 14;
                  LastError = 14;
                  v8 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
                  {
                    v9 = 71;
                    v23 = "pSystemInfo->SystemPath";
                    goto LABEL_46;
                  }
                }
              }
              else
              {
                v2 = 0;
                LastError = GetLastError();
                if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
                {
                  v4 = GetLastError();
                  v5 = 69;
                  goto LABEL_6;
                }
              }
              goto LABEL_67;
            }
          }
          v2 = 0;
          v22 = 14;
          LastError = 14;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v9 = 67;
            v23 = "pSystemInfo->BootSysDirectory";
            goto LABEL_46;
          }
          goto LABEL_67;
        }
      }
      v2 = 0;
      v22 = 14;
      LastError = 14;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v9 = 65;
        v23 = "pSystemInfo->BootWinDirectory";
        goto LABEL_46;
      }
      goto LABEL_67;
    }
    v2 = 0;
    LastError = 1630;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_67;
    }
    v9 = 64;
    v10 = "ERROR_UNSUPPORTED_TYPE";
    goto LABEL_12;
  }
  v2 = 0;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v4 = GetLastError();
    v5 = 63;
    goto LABEL_6;
  }
LABEL_67:
  TraceFunctionExit(L"AsrpInitSystemInformation");
  SetLastError(LastError);
  return v2;
}

```

## disassembly

```asm
0x1400d616c  mov     [rsp+arg_8], rbx
0x1400d6171  mov     [rsp+arg_10], rbp
0x1400d6176  push    rsi
0x1400d6177  push    rdi
0x1400d6178  push    r14
0x1400d617a  sub     rsp, 250h
0x1400d6181  mov     rax, cs:__security_cookie
0x1400d6188  xor     rax, rsp
0x1400d618b  mov     [rsp+268h+var_28], rax
0x1400d6193  mov     rbx, rcx
0x1400d6196  lea     rcx, aAsrpinitsystem_0; "AsrpInitSystemInformation"
0x1400d619d  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400d61a2  xor     eax, eax
0x1400d61a4  lea     rcx, [rsp+268h+var_236]; void *
0x1400d61a9  xor     edx, edx; Val
0x1400d61ab  mov     [rsp+268h+var_238], ax
0x1400d61b0  mov     r8d, 206h; Size
0x1400d61b6  call    memset_0
0x1400d61bb  test    rbx, rbx
0x1400d61be  jz      loc_1400D661B
0x1400d61c4  xor     edx, edx; Val
0x1400d61c6  mov     r8d, 220h; Size
0x1400d61cc  mov     rcx, rbx; void *
0x1400d61cf  call    memset_0
0x1400d61d4  lea     rdx, [rbx+34h]; nSize
0x1400d61d8  mov     edi, 1
0x1400d61dd  lea     rcx, [rbx+38h]; lpBuffer
0x1400d61e1  mov     dword ptr [rdx], 10h
0x1400d61e7  mov     [rbx+30h], edi
0x1400d61ea  call    cs:__imp_GetComputerNameW
0x1400d61f0  test    eax, eax
0x1400d61f2  jnz     short loc_1400D6247
0x1400d61f4  xor     edi, edi
0x1400d61f6  call    cs:__imp_GetLastError
0x1400d61fc  mov     ebx, eax
0x1400d61fe  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6205  lea     rcx, WPP_GLOBAL_Control
0x1400d620c  cmp     rax, rcx
0x1400d620f  jz      loc_1400D665B
0x1400d6215  test    byte ptr [rax+1Ch], 8
0x1400d6219  jz      loc_1400D665B
0x1400d621f  call    cs:__imp_GetLastError
0x1400d6225  lea     edx, [rdi+3Bh]
0x1400d6228  lea     rcx, aGetlasterror; "GetLastError( )"
0x1400d622f  mov     r9d, eax
0x1400d6232  mov     [rsp+268h+var_248], rcx
0x1400d6237  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d623e  mov     rcx, [rcx+10h]
0x1400d6242  jmp     loc_1400D664F
0x1400d6247  mov     ecx, 0Ch; Size
0x1400d624c  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x1400d6251  mov     [rbx+18h], rax
0x1400d6255  test    rax, rax
0x1400d6258  jz      loc_1400D65EA
0x1400d625e  mov     r8d, 6; nSize
0x1400d6264  lea     rcx, Name; "PROCESSOR_ARCHITECTURE"
0x1400d626b  mov     rdx, rax; lpBuffer
0x1400d626e  call    cs:__imp_GetEnvironmentVariableW
0x1400d6274  test    eax, eax
0x1400d6276  jnz     short loc_1400D62B2
0x1400d6278  xor     edi, edi
0x1400d627a  lea     ebx, [rax+0Ah]
0x1400d627d  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6284  lea     rcx, WPP_GLOBAL_Control
0x1400d628b  cmp     rax, rcx
0x1400d628e  jz      loc_1400D665B
0x1400d6294  test    byte ptr [rax+1Ch], 8
0x1400d6298  jz      loc_1400D665B
0x1400d629e  lea     edx, [rdi+3Dh]
0x1400d62a1  lea     rcx, aErrorBadEnviro; "ERROR_BAD_ENVIRONMENT"
0x1400d62a8  mov     [rsp+268h+var_248], rcx
0x1400d62ad  jmp     loc_1400D6648
0x1400d62b2  cmp     eax, 6
0x1400d62b5  jbe     short loc_1400D62E9
0x1400d62b7  xor     edi, edi
0x1400d62b9  lea     ebx, [rdi+32h]
0x1400d62bc  mov     rax, cs:WPP_GLOBAL_Control
0x1400d62c3  lea     rcx, WPP_GLOBAL_Control
0x1400d62ca  cmp     rax, rcx
0x1400d62cd  jz      loc_1400D665B
0x1400d62d3  test    byte ptr [rax+1Ch], 8
0x1400d62d7  jz      loc_1400D665B
0x1400d62dd  lea     edx, [rdi+3Eh]
0x1400d62e0  lea     rcx, aErrorNotSuppor; "ERROR_NOT_SUPPORTED"
0x1400d62e7  jmp     short loc_1400D62A8
0x1400d62e9  lea     rcx, [rbx+58h]; lpVersionInformation
0x1400d62ed  mov     dword ptr [rcx], 11Ch
0x1400d62f3  call    cs:__imp_GetVersionExW
0x1400d62f9  test    eax, eax
0x1400d62fb  jnz     short loc_1400D6336
0x1400d62fd  xor     edi, edi
0x1400d62ff  call    cs:__imp_GetLastError
0x1400d6305  mov     ebx, eax
0x1400d6307  mov     rax, cs:WPP_GLOBAL_Control
0x1400d630e  lea     rcx, WPP_GLOBAL_Control
0x1400d6315  cmp     rax, rcx
0x1400d6318  jz      loc_1400D665B
0x1400d631e  test    byte ptr [rax+1Ch], 8
0x1400d6322  jz      loc_1400D665B
0x1400d6328  call    cs:__imp_GetLastError
0x1400d632e  lea     edx, [rdi+3Fh]
0x1400d6331  jmp     loc_1400D6228
0x1400d6336  call    ?SystemGetFirmwareType@@YA?AW4_FIRMWARE_TYPE@@XZ; SystemGetFirmwareType(void)
0x1400d633b  mov     [rbx+20h], eax
0x1400d633e  test    eax, eax
0x1400d6340  jnz     short loc_1400D6379
0x1400d6342  xor     edi, edi
0x1400d6344  mov     ebx, 65Eh
0x1400d6349  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6350  lea     rcx, WPP_GLOBAL_Control
0x1400d6357  cmp     rax, rcx
0x1400d635a  jz      loc_1400D665B
0x1400d6360  test    byte ptr [rax+1Ch], 8
0x1400d6364  jz      loc_1400D665B
0x1400d636a  lea     edx, [rdi+40h]
0x1400d636d  lea     rcx, aErrorUnsupport; "ERROR_UNSUPPORTED_TYPE"
0x1400d6374  jmp     loc_1400D62A8
0x1400d6379  mov     ebp, 104h
0x1400d637e  mov     esi, ebp
0x1400d6380  mov     rcx, [rbx]; pv
0x1400d6383  call    cs:__imp_CoTaskMemFree
0x1400d6389  lea     ecx, ds:2[rsi*2]; Size
0x1400d6390  mov     qword ptr [rbx], 0
0x1400d6397  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x1400d639c  mov     [rbx], rax
0x1400d639f  test    rax, rax
0x1400d63a2  jz      loc_1400D65B1
0x1400d63a8  mov     edx, esi; uSize
0x1400d63aa  mov     r14d, esi
0x1400d63ad  mov     rcx, rax; lpBuffer
0x1400d63b0  call    cs:__imp_GetSystemWindowsDirectoryW
0x1400d63b6  mov     esi, eax
0x1400d63b8  test    eax, eax
0x1400d63ba  jz      loc_1400D6578
0x1400d63c0  cmp     eax, r14d
0x1400d63c3  ja      short loc_1400D6380
0x1400d63c5  mov     rcx, [rbx]
0x1400d63c8  xor     eax, eax
0x1400d63ca  mov     [rcx+r14*2], ax
0x1400d63cf  mov     rcx, [rbx+8]; pv
0x1400d63d3  call    cs:__imp_CoTaskMemFree
0x1400d63d9  lea     ecx, ds:2[rbp*2]; Size
0x1400d63e0  mov     qword ptr [rbx+8], 0
0x1400d63e8  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x1400d63ed  mov     [rbx+8], rax
0x1400d63f1  test    rax, rax
0x1400d63f4  jz      loc_1400D6542
0x1400d63fa  mov     edx, ebp; uSize
0x1400d63fc  mov     esi, ebp
0x1400d63fe  mov     rcx, rax; lpBuffer
0x1400d6401  call    cs:__imp_GetSystemDirectoryW
0x1400d6407  mov     ebp, eax
0x1400d6409  test    eax, eax
0x1400d640b  jz      loc_1400D6509
0x1400d6411  cmp     eax, esi
0x1400d6413  ja      short loc_1400D63CF
0x1400d6415  mov     rcx, [rbx+8]
0x1400d6419  xor     eax, eax
0x1400d641b  mov     [rcx+rsi*2], ax
0x1400d641f  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x1400d6424  call    ?AsrGetSystemVolumeDevPath@@YAHPEAGK@Z; AsrGetSystemVolumeDevPath(ushort *,ulong)
0x1400d6429  test    eax, eax
0x1400d642b  jnz     short loc_1400D6466
0x1400d642d  xor     edi, edi
0x1400d642f  call    cs:__imp_GetLastError
0x1400d6435  mov     ebx, eax
0x1400d6437  mov     rax, cs:WPP_GLOBAL_Control
0x1400d643e  lea     rcx, WPP_GLOBAL_Control
0x1400d6445  cmp     rax, rcx
0x1400d6448  jz      loc_1400D665B
0x1400d644e  test    byte ptr [rax+1Ch], 8
0x1400d6452  jz      loc_1400D665B
0x1400d6458  call    cs:__imp_GetLastError
0x1400d645e  lea     edx, [rdi+45h]
0x1400d6461  jmp     loc_1400D6228
0x1400d6466  lea     rcx, [rbx+174h]; lpTimeZoneInformation
0x1400d646d  call    cs:__imp_GetTimeZoneInformation
0x1400d6473  cmp     eax, 0FFFFFFFFh
0x1400d6476  jnz     short loc_1400D64B1
0x1400d6478  xor     edi, edi
0x1400d647a  call    cs:__imp_GetLastError
0x1400d6480  mov     ebx, eax
0x1400d6482  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6489  lea     rcx, WPP_GLOBAL_Control
0x1400d6490  cmp     rax, rcx
0x1400d6493  jz      loc_1400D665B
0x1400d6499  test    byte ptr [rax+1Ch], 8
0x1400d649d  jz      loc_1400D665B
0x1400d64a3  call    cs:__imp_GetLastError
0x1400d64a9  lea     edx, [rdi+46h]
0x1400d64ac  jmp     loc_1400D6228
0x1400d64b1  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x1400d64b6  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x1400d64bb  mov     [rbx+10h], rax
0x1400d64bf  test    rax, rax
0x1400d64c2  jz      short loc_1400D64CB
0x1400d64c4  xor     ebx, ebx
0x1400d64c6  jmp     loc_1400D665B
0x1400d64cb  xor     edi, edi
0x1400d64cd  lea     r9d, [rdi+0Eh]
0x1400d64d1  mov     ebx, r9d
0x1400d64d4  mov     rax, cs:WPP_GLOBAL_Control
0x1400d64db  lea     rcx, WPP_GLOBAL_Control
0x1400d64e2  cmp     rax, rcx
0x1400d64e5  jz      loc_1400D665B
0x1400d64eb  test    byte ptr [rax+1Ch], 8
0x1400d64ef  jz      loc_1400D665B
0x1400d64f5  lea     edx, [rdi+47h]
0x1400d64f8  lea     rcx, aPsysteminfoSys; "pSystemInfo->SystemPath"
0x1400d64ff  mov     [rsp+268h+var_248], rcx
0x1400d6504  jmp     loc_1400D664B
0x1400d6509  xor     edi, edi
0x1400d650b  call    cs:__imp_GetLastError
0x1400d6511  mov     ebx, eax
0x1400d6513  mov     rax, cs:WPP_GLOBAL_Control
0x1400d651a  lea     rcx, WPP_GLOBAL_Control
0x1400d6521  cmp     rax, rcx
0x1400d6524  jz      loc_1400D665B
0x1400d652a  test    byte ptr [rax+1Ch], 8
0x1400d652e  jz      loc_1400D665B
0x1400d6534  call    cs:__imp_GetLastError
0x1400d653a  lea     edx, [rdi+44h]
0x1400d653d  jmp     loc_1400D6228
0x1400d6542  xor     edi, edi
0x1400d6544  lea     r9d, [rdi+0Eh]
0x1400d6548  mov     ebx, r9d
0x1400d654b  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6552  lea     rcx, WPP_GLOBAL_Control
0x1400d6559  cmp     rax, rcx
0x1400d655c  jz      loc_1400D665B
0x1400d6562  test    byte ptr [rax+1Ch], 8
0x1400d6566  jz      loc_1400D665B
0x1400d656c  lea     edx, [rdi+43h]
0x1400d656f  lea     rcx, aPsysteminfoBoo_0; "pSystemInfo->BootSysDirectory"
0x1400d6576  jmp     short loc_1400D64FF
0x1400d6578  xor     edi, edi
0x1400d657a  call    cs:__imp_GetLastError
0x1400d6580  mov     ebx, eax
0x1400d6582  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6589  lea     rcx, WPP_GLOBAL_Control
0x1400d6590  cmp     rax, rcx
0x1400d6593  jz      loc_1400D665B
0x1400d6599  test    byte ptr [rax+1Ch], 8
0x1400d659d  jz      loc_1400D665B
0x1400d65a3  call    cs:__imp_GetLastError
0x1400d65a9  lea     edx, [rdi+42h]
0x1400d65ac  jmp     loc_1400D6228
0x1400d65b1  xor     edi, edi
0x1400d65b3  lea     r9d, [rdi+0Eh]
0x1400d65b7  mov     ebx, r9d
0x1400d65ba  mov     rax, cs:WPP_GLOBAL_Control
0x1400d65c1  lea     rcx, WPP_GLOBAL_Control
0x1400d65c8  cmp     rax, rcx
0x1400d65cb  jz      loc_1400D665B
0x1400d65d1  test    byte ptr [rax+1Ch], 8
0x1400d65d5  jz      loc_1400D665B
0x1400d65db  lea     edx, [rdi+41h]
0x1400d65de  lea     rcx, aPsysteminfoBoo; "pSystemInfo->BootWinDirectory"
0x1400d65e5  jmp     loc_1400D64FF
0x1400d65ea  xor     edi, edi
0x1400d65ec  lea     r9d, [rdi+0Eh]
0x1400d65f0  mov     ebx, r9d
0x1400d65f3  mov     rax, cs:WPP_GLOBAL_Control
0x1400d65fa  lea     rcx, WPP_GLOBAL_Control
0x1400d6601  cmp     rax, rcx
0x1400d6604  jz      short loc_1400D665B
0x1400d6606  test    byte ptr [rax+1Ch], 8
0x1400d660a  jz      short loc_1400D665B
0x1400d660c  lea     edx, [rdi+3Ch]
0x1400d660f  lea     rcx, aPsysteminfoPla; "pSystemInfo->Platform"
0x1400d6616  jmp     loc_1400D64FF
0x1400d661b  xor     edi, edi
0x1400d661d  lea     ebx, [rdi+57h]
0x1400d6620  mov     rax, cs:WPP_GLOBAL_Control
0x1400d6627  lea     rcx, WPP_GLOBAL_Control
0x1400d662e  cmp     rax, rcx
0x1400d6631  jz      short loc_1400D665B
0x1400d6633  test    byte ptr [rax+1Ch], 8
0x1400d6637  jz      short loc_1400D665B
0x1400d6639  lea     r8, aPsysteminfo; "pSystemInfo"
0x1400d6640  mov     [rsp+268h+var_248], r8
0x1400d6645  lea     edx, [rdi+3Ah]
0x1400d6648  mov     r9d, ebx
0x1400d664b  mov     rcx, [rax+10h]
0x1400d664f  lea     r8, WPP_bbfff7ea0df63369e2e67d0c2acae35a_Traceguids
0x1400d6656  call    WPP_SF_Ds
0x1400d665b  lea     rcx, aAsrpinitsystem_0; "AsrpInitSystemInformation"
0x1400d6662  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400d6667  mov     ecx, ebx; dwErrCode
0x1400d6669  call    cs:__imp_SetLastError
0x1400d666f  mov     eax, edi
0x1400d6671  mov     rcx, [rsp+268h+var_28]
0x1400d6679  xor     rcx, rsp; StackCookie
0x1400d667c  call    __security_check_cookie
0x1400d6681  lea     r11, [rsp+268h+var_18]
0x1400d6689  mov     rbx, [r11+28h]
0x1400d668d  mov     rbp, [r11+30h]
0x1400d6691  mov     rsp, r11
0x1400d6694  pop     r14
0x1400d6696  pop     rdi
  ... truncated ...
```
