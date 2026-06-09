# CSdWhcNotifier::Notify(_SD_WHC_STATE_TYPE)

- ea: `0x18003ec00`
- end: `0x18003f0d1`
- name: `?Notify@CSdWhcNotifier@@UEAAJW4_SD_WHC_STATE_TYPE@@@Z`
- size: `1233`
- prototype: `int __high(enum _SD_WHC_STATE_TYPE)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003ec00`
- `0x180044df8`
- `0x180044e58`
- `0x180072e08`
- `0x180072f14`
- `0x18008c0c4`
- `0x180098a5c`
- `0x180099064`
- `0x1800991c8`
- `0x18009cd54`
- `0x18009e234`
- `0x18009f560`
- `0x1800cf5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eea9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eec5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003efb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003efda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eea9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eec5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003efb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003efda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f089`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003edab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eef9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f00e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003edab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eef9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f00e`

## pseudocode

```c
__int64 __fastcall CSdWhcNotifier::Notify(__int64 a1, signed int a2)
{
  unsigned int v3; // edi
  unsigned int v4; // ebx
  int v5; // esi
  int v6; // eax
  bool v7; // sf
  __int16 v8; // ax
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // rcx
  signed int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  HKEY v15; // rcx
  int v16; // eax
  unsigned int v17; // edx
  unsigned int v18; // r8d
  signed int v19; // eax
  HKEY v20; // rcx
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // ebx
  HKEY hKey; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-51h] BYREF
  int ULONGLONG; // [rsp+40h] [rbp-49h] BYREF
  __int16 v29; // [rsp+44h] [rbp-45h]
  __int16 v30; // [rsp+46h] [rbp-43h]
  struct _FILETIME v31; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v33[16]; // [rsp+90h] [rbp+7h] BYREF
  unsigned int *v34; // [rsp+A0h] [rbp+17h]
  __int64 v35; // [rsp+A8h] [rbp+1Fh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&ULONGLONG, "CSdWhcNotifier::Notify", 0x10B4u, 1u);
  hKey = 0;
  v31 = 0;
  v3 = 0x7FFFFFFF;
  v4 = 0x7FFFFFFF;
  v32[0] = qword_1800EE510;
  v32[1] = 0;
  v5 = 0;
  v27 = 0;
  if ( a2 > 10 )
  {
    if ( a2 == 11 )
    {
      v4 = 10;
      v3 = 2;
      goto LABEL_43;
    }
    if ( a2 != 12 )
    {
      if ( a2 != 13 )
      {
        switch ( a2 )
        {
          case 14:
            v4 = 15;
            goto LABEL_43;
          case 15:
            v4 = 17;
            break;
          case 16:
            v4 = 18;
            break;
          case 17:
            v4 = 19;
            break;
          case 18:
            v4 = 20;
            break;
          case 19:
            v4 = 21;
            break;
          default:
            goto LABEL_43;
        }
        v3 = 0;
        goto LABEL_43;
      }
      v4 = 14;
      goto LABEL_14;
    }
    v4 = 11;
LABEL_13:
    v3 = 0;
LABEL_14:
    v5 = 1;
    goto LABEL_43;
  }
  switch ( a2 )
  {
    case 10:
      v4 = 16;
      v3 = 1;
      break;
    case 1:
      v4 = 2;
      goto LABEL_13;
    case 2:
      v4 = 3;
      break;
    case 3:
      v4 = 4;
      goto LABEL_13;
    case 4:
      v4 = 5;
      goto LABEL_13;
    case 5:
      v4 = 6;
      goto LABEL_13;
    case 6:
      v4 = 7;
      break;
    case 7:
      v4 = 8;
      goto LABEL_13;
    case 8:
      v4 = 9;
      goto LABEL_13;
    case 9:
      v4 = 13;
      goto LABEL_13;
  }
LABEL_43:
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x20019u,
         &hKey);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  ULONGLONG = v6;
  v7 = v6 < 0;
  v8 = 4402;
  if ( v7 )
    goto LABEL_46;
  v29 = 4402;
  v9 = SxRegReadDWORD(hKey, L"DisableMonitoring", &v27, 1);
  v11 = (unsigned int)v9;
  ULONGLONG = v9;
  v7 = v9 < 0;
  v8 = 4403;
  if ( v7 )
    goto LABEL_46;
  v29 = 4403;
  if ( (_DWORD)v11 || !v27 || a2 == 14 )
  {
    if ( v3 != 0x7FFFFFFF )
    {
      if ( (Microsoft_Windows_WindowsBackupEnableBits & 1) != 0 )
      {
        v27 = v3;
        v34 = &v27;
        v35 = 4;
        v12 = McGenEventWrite_EventWriteTransfer(v11, "e", v10, 2, v33);
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
      }
      else
      {
        v12 = 0;
      }
      ULONGLONG = v12;
      v7 = v12 < 0;
      v8 = 4414;
      if ( v7 )
        goto LABEL_46;
      v29 = 4414;
    }
    if ( v4 != 0x7FFFFFFF )
    {
      CBsString::Empty((CBsString *)v32);
      if ( v5 )
      {
        v15 = hKey;
        if ( hKey )
        {
          if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
          {
            RegCloseKey(hKey);
            v15 = 0;
            hKey = 0;
          }
          if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            RegCloseKey(v15);
            hKey = 0;
          }
        }
        v16 = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\Status",
                0,
                0x20019u,
                &hKey);
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        ULONGLONG = v16;
        v7 = v16 < 0;
        v8 = 4424;
        if ( v7 )
          goto LABEL_46;
        v29 = 4424;
        ULONGLONG = SxRegReadULONGLONG(hKey, L"LastResultTime", (unsigned __int64 *)&v31, 1);
        v8 = 4425;
        if ( ULONGLONG < 0 )
          goto LABEL_46;
        v29 = 4425;
        ULONGLONG = SxUTCFileTimeToString(v31, v17, v18, (struct CBsString *)v32);
        v8 = 4426;
        if ( ULONGLONG < 0 )
          goto LABEL_46;
        v29 = 4426;
      }
      if ( (Microsoft_Windows_WindowsBackupEnableBits & 1) != 0 )
      {
        v19 = McTemplateU0qz_EventWriteTransfer(v14, v13, v4, v32[0]);
        if ( v19 > 0 )
          v19 = (unsigned __int16)v19 | 0x80070000;
      }
      else
      {
        v19 = 0;
      }
      ULONGLONG = v19;
      v7 = v19 < 0;
      v8 = 4430;
      if ( v7 )
        goto LABEL_46;
      v29 = 4430;
    }
  }
  v20 = hKey;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    v20 = 0;
    hKey = 0;
  }
  if ( a2 == 14 )
    goto LABEL_87;
  if ( (unsigned __int64)v20 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v20);
    hKey = 0;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\Status",
         0,
         0x2001Fu,
         &hKey) )
  {
    goto LABEL_87;
  }
  ULONGLONG = SetRegKeyVirtualization(hKey, v21, v22, v23);
  v8 = 4441;
  if ( ULONGLONG < 0 )
  {
LABEL_46:
    v30 = v8;
    goto LABEL_87;
  }
  v29 = 4441;
  ULONGLONG = SxRegWriteDWORD(hKey, L"ActionCenterState", a2);
  if ( ULONGLONG < 0 )
  {
    v8 = 4442;
    goto LABEL_46;
  }
  ULONGLONG = 0;
  v29 = 4443;
LABEL_87:
  v24 = ULONGLONG;
  CBsString::_Release((CBsString *)v32);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&ULONGLONG);
  return v24;
}

```

## disassembly

```asm
0x18003ec00  mov     [rsp-8+arg_0], rbx
0x18003ec05  mov     [rsp-8+arg_10], rsi
0x18003ec0a  push    rbp
0x18003ec0b  push    rdi
0x18003ec0c  push    r12
0x18003ec0e  push    r13
0x18003ec10  push    r14
0x18003ec12  lea     rbp, [rsp-37h]
0x18003ec17  sub     rsp, 0C0h
0x18003ec1e  mov     rax, cs:__security_cookie
0x18003ec25  xor     rax, rsp
0x18003ec28  mov     [rbp+57h+var_30], rax
0x18003ec2c  mov     r14d, edx
0x18003ec2f  mov     r12d, 1
0x18003ec35  mov     r9d, r12d; unsigned __int16
0x18003ec38  mov     r8d, 10B4h; unsigned __int16
0x18003ec3e  lea     rdx, aCsdwhcnotifier; "CSdWhcNotifier::Notify"
0x18003ec45  lea     rcx, [rbp+57h+var_A0]; this
0x18003ec49  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003ec4e  mov     [rbp+57h+hKey], 0
0x18003ec56  mov     qword ptr [rbp+57h+var_68.dwLowDateTime], 0
0x18003ec5e  mov     eax, 7FFFFFFFh
0x18003ec63  mov     edi, eax
0x18003ec65  mov     ebx, eax
0x18003ec67  lea     rax, qword_1800EE510
0x18003ec6e  mov     [rbp+57h+var_60], rax
0x18003ec72  mov     [rbp+57h+var_58], 0
0x18003ec7a  xor     esi, esi
0x18003ec7c  mov     [rbp+57h+var_A8], esi
0x18003ec7f  lea     edx, [rsi+2]
0x18003ec82  cmp     r14d, 0Ah
0x18003ec86  jg      loc_18003ED14
0x18003ec8c  jz      short loc_18003ED0A
0x18003ec8e  mov     ecx, r14d
0x18003ec91  sub     ecx, r12d
0x18003ec94  jz      short loc_18003ED06
0x18003ec96  sub     ecx, r12d
0x18003ec99  jz      short loc_18003ECFC
0x18003ec9b  sub     ecx, r12d
0x18003ec9e  jz      short loc_18003ECF5
0x18003eca0  sub     ecx, r12d
0x18003eca3  jz      short loc_18003ECEE
0x18003eca5  sub     ecx, r12d
0x18003eca8  jz      short loc_18003ECE7
0x18003ecaa  sub     ecx, r12d
0x18003ecad  jz      short loc_18003ECDD
0x18003ecaf  sub     ecx, r12d
0x18003ecb2  jz      short loc_18003ECD6
0x18003ecb4  sub     ecx, r12d
0x18003ecb7  jz      short loc_18003ECCF
0x18003ecb9  cmp     ecx, r12d
0x18003ecbc  jnz     loc_18003ED8B
0x18003ecc2  lea     ebx, [rsi+0Dh]
0x18003ecc5  xor     edi, edi
0x18003ecc7  mov     esi, r12d
0x18003ecca  jmp     loc_18003ED8B
0x18003eccf  mov     ebx, 9
0x18003ecd4  jmp     short loc_18003ECC5
0x18003ecd6  mov     ebx, 8
0x18003ecdb  jmp     short loc_18003ECC5
0x18003ecdd  mov     ebx, 7
0x18003ece2  jmp     loc_18003ED8B
0x18003ece7  mov     ebx, 6
0x18003ecec  jmp     short loc_18003ECC5
0x18003ecee  mov     ebx, 5
0x18003ecf3  jmp     short loc_18003ECC5
0x18003ecf5  mov     ebx, 4
0x18003ecfa  jmp     short loc_18003ECC5
0x18003ecfc  mov     ebx, 3
0x18003ed01  jmp     loc_18003ED8B
0x18003ed06  mov     ebx, edx
0x18003ed08  jmp     short loc_18003ECC5
0x18003ed0a  mov     ebx, 10h
0x18003ed0f  mov     edi, r12d
0x18003ed12  jmp     short loc_18003ED8B
0x18003ed14  mov     ecx, r14d
0x18003ed17  sub     ecx, 0Bh
0x18003ed1a  jz      short loc_18003ED84
0x18003ed1c  sub     ecx, r12d
0x18003ed1f  jz      short loc_18003ED7A
0x18003ed21  sub     ecx, r12d
0x18003ed24  jz      short loc_18003ED70
0x18003ed26  sub     ecx, r12d
0x18003ed29  jz      short loc_18003ED69
0x18003ed2b  sub     ecx, r12d
0x18003ed2e  jz      short loc_18003ED62
0x18003ed30  sub     ecx, r12d
0x18003ed33  jz      short loc_18003ED5B
0x18003ed35  sub     ecx, r12d
0x18003ed38  jz      short loc_18003ED54
0x18003ed3a  sub     ecx, r12d
0x18003ed3d  jz      short loc_18003ED4D
0x18003ed3f  cmp     ecx, r12d
0x18003ed42  jnz     short loc_18003ED8B
0x18003ed44  mov     ebx, 15h
0x18003ed49  xor     edi, edi
0x18003ed4b  jmp     short loc_18003ED8B
0x18003ed4d  mov     ebx, 14h
0x18003ed52  jmp     short loc_18003ED49
0x18003ed54  mov     ebx, 13h
0x18003ed59  jmp     short loc_18003ED49
0x18003ed5b  mov     ebx, 12h
0x18003ed60  jmp     short loc_18003ED49
0x18003ed62  mov     ebx, 11h
0x18003ed67  jmp     short loc_18003ED49
0x18003ed69  mov     ebx, 0Fh
0x18003ed6e  jmp     short loc_18003ED8B
0x18003ed70  mov     ebx, 0Eh
0x18003ed75  jmp     loc_18003ECC7
0x18003ed7a  mov     ebx, 0Bh
0x18003ed7f  jmp     loc_18003ECC5
0x18003ed84  mov     ebx, 0Ah
0x18003ed89  mov     edi, edx
0x18003ed8b  lea     rax, [rbp+57h+hKey]
0x18003ed8f  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003ed94  mov     r9d, 20019h; samDesired
0x18003ed9a  xor     r8d, r8d; ulOptions
0x18003ed9d  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003eda4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003edab  call    cs:__imp_RegOpenKeyExW
0x18003edb2  nop     dword ptr [rax+rax+00h]
0x18003edb7  mov     r13d, 80070000h
0x18003edbd  test    eax, eax
0x18003edbf  jle     short loc_18003EDC7
0x18003edc1  movzx   eax, ax
0x18003edc4  or      eax, r13d
0x18003edc7  mov     [rbp+57h+var_A0], eax
0x18003edca  test    eax, eax
0x18003edcc  mov     eax, 1132h
0x18003edd1  jns     short loc_18003EDDC
0x18003edd3  mov     [rbp+57h+var_9A], ax
0x18003edd7  jmp     loc_18003F06F
0x18003eddc  mov     [rbp+57h+var_9C], ax
0x18003ede0  mov     r9d, r12d; int
0x18003ede3  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x18003ede7  lea     rdx, c_wszSafedocsDisableMonitoring; "DisableMonitoring"
0x18003edee  mov     rcx, [rbp+57h+hKey]; hKey
0x18003edf2  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18003edf7  mov     ecx, eax
0x18003edf9  mov     [rbp+57h+var_A0], eax
0x18003edfc  test    eax, eax
0x18003edfe  mov     eax, 1133h
0x18003ee03  js      short loc_18003EDD3
0x18003ee05  mov     [rbp+57h+var_9C], ax
0x18003ee09  test    ecx, ecx
0x18003ee0b  jnz     short loc_18003EE1C
0x18003ee0d  cmp     [rbp+57h+var_A8], ecx
0x18003ee10  jz      short loc_18003EE1C
0x18003ee12  cmp     r14d, 0Eh
0x18003ee16  jnz     loc_18003EFA6
0x18003ee1c  cmp     edi, 7FFFFFFFh
0x18003ee22  jz      short loc_18003EE7D
0x18003ee24  test    cs:Microsoft_Windows_WindowsBackupEnableBits, r12b
0x18003ee2b  jz      short loc_18003EE67
0x18003ee2d  mov     [rbp+57h+var_A8], edi
0x18003ee30  lea     rax, [rbp+57h+var_A8]
0x18003ee34  mov     [rbp+57h+var_40], rax
0x18003ee38  mov     [rbp+57h+var_38], 4
0x18003ee40  lea     rax, [rbp+57h+var_50]
0x18003ee44  mov     [rsp+0E0h+phkResult], rax
0x18003ee49  mov     r9d, 2
0x18003ee4f  lea     rdx, HCEVENT_HIDDEN; "e"
0x18003ee56  call    McGenEventWrite_EventWriteTransfer
0x18003ee5b  test    eax, eax
0x18003ee5d  jle     short loc_18003EE69
0x18003ee5f  movzx   eax, ax
0x18003ee62  or      eax, r13d
0x18003ee65  jmp     short loc_18003EE69
0x18003ee67  xor     eax, eax
0x18003ee69  mov     [rbp+57h+var_A0], eax
0x18003ee6c  test    eax, eax
0x18003ee6e  mov     eax, 113Eh
0x18003ee73  js      loc_18003EDD3
0x18003ee79  mov     [rbp+57h+var_9C], ax
0x18003ee7d  cmp     ebx, 7FFFFFFFh
0x18003ee83  jz      loc_18003EFA6
0x18003ee89  lea     rcx, [rbp+57h+var_60]; this
0x18003ee8d  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18003ee92  test    esi, esi
0x18003ee94  jz      loc_18003EF6F
0x18003ee9a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ee9e  test    rcx, rcx
0x18003eea1  jz      short loc_18003EED9
0x18003eea3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003eea7  jz      short loc_18003EEBB
0x18003eea9  call    cs:__imp_RegCloseKey
0x18003eeb0  nop     dword ptr [rax+rax+00h]
0x18003eeb5  xor     ecx, ecx; hKey
0x18003eeb7  mov     [rbp+57h+hKey], rcx
0x18003eebb  lea     rax, [rcx-1]
0x18003eebf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003eec3  ja      short loc_18003EED9
0x18003eec5  call    cs:__imp_RegCloseKey
0x18003eecc  nop     dword ptr [rax+rax+00h]
0x18003eed1  mov     [rbp+57h+hKey], 0
0x18003eed9  lea     rax, [rbp+57h+hKey]
0x18003eedd  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003eee2  mov     r9d, 20019h; samDesired
0x18003eee8  xor     r8d, r8d; ulOptions
0x18003eeeb  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003eef2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003eef9  call    cs:__imp_RegOpenKeyExW
0x18003ef00  nop     dword ptr [rax+rax+00h]
0x18003ef05  test    eax, eax
0x18003ef07  jle     short loc_18003EF0F
0x18003ef09  movzx   eax, ax
0x18003ef0c  or      eax, r13d
0x18003ef0f  mov     [rbp+57h+var_A0], eax
0x18003ef12  test    eax, eax
0x18003ef14  mov     eax, 1148h
0x18003ef19  js      loc_18003EDD3
0x18003ef1f  mov     [rbp+57h+var_9C], ax
0x18003ef23  mov     r9d, r12d; int
0x18003ef26  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x18003ef2a  lea     rdx, c_wszSafedocsScheduleLastResultTime; "LastResultTime"
0x18003ef31  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ef35  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18003ef3a  mov     [rbp+57h+var_A0], eax
0x18003ef3d  test    eax, eax
0x18003ef3f  mov     eax, 1149h
0x18003ef44  js      loc_18003EDD3
0x18003ef4a  mov     [rbp+57h+var_9C], ax
0x18003ef4e  lea     r9, [rbp+57h+var_60]; struct CBsString *
0x18003ef52  mov     rcx, qword ptr [rbp+57h+var_68.dwLowDateTime]; struct _FILETIME
0x18003ef56  call    ?SxUTCFileTimeToString@@YAJU_FILETIME@@KKPEAVCBsString@@@Z; SxUTCFileTimeToString(_FILETIME,ulong,ulong,CBsString *)
0x18003ef5b  mov     [rbp+57h+var_A0], eax
0x18003ef5e  test    eax, eax
0x18003ef60  mov     eax, 114Ah
0x18003ef65  js      loc_18003EDD3
0x18003ef6b  mov     [rbp+57h+var_9C], ax
0x18003ef6f  test    cs:Microsoft_Windows_WindowsBackupEnableBits, r12b
0x18003ef76  jz      short loc_18003EF90
0x18003ef78  mov     r9, [rbp+57h+var_60]
0x18003ef7c  mov     r8d, ebx
0x18003ef7f  call    McTemplateU0qz_EventWriteTransfer
0x18003ef84  test    eax, eax
0x18003ef86  jle     short loc_18003EF92
0x18003ef88  movzx   eax, ax
0x18003ef8b  or      eax, r13d
0x18003ef8e  jmp     short loc_18003EF92
0x18003ef90  xor     eax, eax
0x18003ef92  mov     [rbp+57h+var_A0], eax
0x18003ef95  test    eax, eax
0x18003ef97  mov     eax, 114Eh
0x18003ef9c  js      loc_18003EDD3
0x18003efa2  mov     [rbp+57h+var_9C], ax
0x18003efa6  mov     rcx, [rbp+57h+hKey]; hKey
0x18003efaa  lea     rax, [rcx-1]
0x18003efae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003efb2  ja      short loc_18003EFC6
0x18003efb4  call    cs:__imp_RegCloseKey
0x18003efbb  nop     dword ptr [rax+rax+00h]
0x18003efc0  xor     ecx, ecx; hKey
0x18003efc2  mov     [rbp+57h+hKey], rcx
0x18003efc6  cmp     r14d, 0Eh
0x18003efca  jz      loc_18003F06F
0x18003efd0  lea     rax, [rcx-1]
0x18003efd4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003efd8  ja      short loc_18003EFEE
0x18003efda  call    cs:__imp_RegCloseKey
0x18003efe1  nop     dword ptr [rax+rax+00h]
0x18003efe6  mov     [rbp+57h+hKey], 0
0x18003efee  lea     rax, [rbp+57h+hKey]
0x18003eff2  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003eff7  mov     r9d, 2001Fh; samDesired
0x18003effd  xor     r8d, r8d; ulOptions
0x18003f000  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003f007  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f00e  call    cs:__imp_RegOpenKeyExW
0x18003f015  nop     dword ptr [rax+rax+00h]
0x18003f01a  test    eax, eax
0x18003f01c  jnz     short loc_18003F06F
0x18003f01e  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18003f022  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18003f027  mov     [rbp+57h+var_A0], eax
0x18003f02a  test    eax, eax
0x18003f02c  mov     eax, 1159h
0x18003f031  js      loc_18003EDD3
0x18003f037  mov     [rbp+57h+var_9C], ax
0x18003f03b  mov     r8d, r14d; unsigned int
0x18003f03e  lea     rdx, c_wszSafedocsScheduleActionCenterstate; "ActionCenterState"
0x18003f045  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f049  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18003f04e  mov     [rbp+57h+var_A0], eax
0x18003f051  test    eax, eax
0x18003f053  jns     short loc_18003F05F
0x18003f055  mov     eax, 115Ah
0x18003f05a  jmp     loc_18003EDD3
0x18003f05f  mov     [rbp+57h+var_A0], 0
0x18003f066  mov     eax, 115Bh
0x18003f06b  mov     [rbp+57h+var_9C], ax
0x18003f06f  mov     ebx, [rbp+57h+var_A0]
0x18003f072  lea     rcx, [rbp+57h+var_60]; this
0x18003f076  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003f07b  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f07f  lea     rdx, [rcx-1]
0x18003f083  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003f087  ja      short loc_18003F09D
0x18003f089  call    cs:__imp_RegCloseKey
0x18003f090  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
