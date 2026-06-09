# CSdWhcNotifier::Notify(_SD_WHC_STATE_TYPE)

- ea: `0x18003d520`
- end: `0x18003d9c0`
- name: `?Notify@CSdWhcNotifier@@UEAAJW4_SD_WHC_STATE_TYPE@@@Z`
- size: `1184`
- prototype: `int __high(enum _SD_WHC_STATE_TYPE)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003d520`
- `0x18004351c`
- `0x180043574`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088640`
- `0x180094758`
- `0x180094d2c`
- `0x180094e88`
- `0x180098838`
- `0x180099bdc`
- `0x18009ae34`
- `0x1800c9830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d8bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d8dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d97f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d7d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d8bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d8dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d97f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d6cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d807`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d90a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d6cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d807`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d90a`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&ULONGLONG, "CSdWhcNotifier::Notify", 4276, 1);
  hKey = 0;
  v31 = 0;
  v3 = 0x7FFFFFFF;
  v4 = 0x7FFFFFFF;
  v32[0] = qword_1800E8530;
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
0x18003d520  mov     [rsp-8+arg_0], rbx
0x18003d525  mov     [rsp-8+arg_10], rsi
0x18003d52a  push    rbp
0x18003d52b  push    rdi
0x18003d52c  push    r12
0x18003d52e  push    r13
0x18003d530  push    r14
0x18003d532  lea     rbp, [rsp-37h]
0x18003d537  sub     rsp, 0C0h
0x18003d53e  mov     rax, cs:__security_cookie
0x18003d545  xor     rax, rsp
0x18003d548  mov     [rbp+57h+var_30], rax
0x18003d54c  mov     r14d, edx
0x18003d54f  mov     r12d, 1
0x18003d555  mov     r9d, r12d; unsigned __int16
0x18003d558  mov     r8d, 10B4h; unsigned __int16
0x18003d55e  lea     rdx, aCsdwhcnotifier; "CSdWhcNotifier::Notify"
0x18003d565  lea     rcx, [rbp+57h+var_A0]; this
0x18003d569  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003d56e  mov     [rbp+57h+hKey], 0
0x18003d576  mov     qword ptr [rbp+57h+var_68.dwLowDateTime], 0
0x18003d57e  mov     eax, 7FFFFFFFh
0x18003d583  mov     edi, eax
0x18003d585  mov     ebx, eax
0x18003d587  lea     rax, qword_1800E8530
0x18003d58e  mov     [rbp+57h+var_60], rax
0x18003d592  mov     [rbp+57h+var_58], 0
0x18003d59a  xor     esi, esi
0x18003d59c  mov     [rbp+57h+var_A8], esi
0x18003d59f  lea     edx, [rsi+2]
0x18003d5a2  cmp     r14d, 0Ah
0x18003d5a6  jg      loc_18003D634
0x18003d5ac  jz      short loc_18003D62A
0x18003d5ae  mov     ecx, r14d
0x18003d5b1  sub     ecx, r12d
0x18003d5b4  jz      short loc_18003D626
0x18003d5b6  sub     ecx, r12d
0x18003d5b9  jz      short loc_18003D61C
0x18003d5bb  sub     ecx, r12d
0x18003d5be  jz      short loc_18003D615
0x18003d5c0  sub     ecx, r12d
0x18003d5c3  jz      short loc_18003D60E
0x18003d5c5  sub     ecx, r12d
0x18003d5c8  jz      short loc_18003D607
0x18003d5ca  sub     ecx, r12d
0x18003d5cd  jz      short loc_18003D5FD
0x18003d5cf  sub     ecx, r12d
0x18003d5d2  jz      short loc_18003D5F6
0x18003d5d4  sub     ecx, r12d
0x18003d5d7  jz      short loc_18003D5EF
0x18003d5d9  cmp     ecx, r12d
0x18003d5dc  jnz     loc_18003D6AB
0x18003d5e2  lea     ebx, [rsi+0Dh]
0x18003d5e5  xor     edi, edi
0x18003d5e7  mov     esi, r12d
0x18003d5ea  jmp     loc_18003D6AB
0x18003d5ef  mov     ebx, 9
0x18003d5f4  jmp     short loc_18003D5E5
0x18003d5f6  mov     ebx, 8
0x18003d5fb  jmp     short loc_18003D5E5
0x18003d5fd  mov     ebx, 7
0x18003d602  jmp     loc_18003D6AB
0x18003d607  mov     ebx, 6
0x18003d60c  jmp     short loc_18003D5E5
0x18003d60e  mov     ebx, 5
0x18003d613  jmp     short loc_18003D5E5
0x18003d615  mov     ebx, 4
0x18003d61a  jmp     short loc_18003D5E5
0x18003d61c  mov     ebx, 3
0x18003d621  jmp     loc_18003D6AB
0x18003d626  mov     ebx, edx
0x18003d628  jmp     short loc_18003D5E5
0x18003d62a  mov     ebx, 10h
0x18003d62f  mov     edi, r12d
0x18003d632  jmp     short loc_18003D6AB
0x18003d634  mov     ecx, r14d
0x18003d637  sub     ecx, 0Bh
0x18003d63a  jz      short loc_18003D6A4
0x18003d63c  sub     ecx, r12d
0x18003d63f  jz      short loc_18003D69A
0x18003d641  sub     ecx, r12d
0x18003d644  jz      short loc_18003D690
0x18003d646  sub     ecx, r12d
0x18003d649  jz      short loc_18003D689
0x18003d64b  sub     ecx, r12d
0x18003d64e  jz      short loc_18003D682
0x18003d650  sub     ecx, r12d
0x18003d653  jz      short loc_18003D67B
0x18003d655  sub     ecx, r12d
0x18003d658  jz      short loc_18003D674
0x18003d65a  sub     ecx, r12d
0x18003d65d  jz      short loc_18003D66D
0x18003d65f  cmp     ecx, r12d
0x18003d662  jnz     short loc_18003D6AB
0x18003d664  mov     ebx, 15h
0x18003d669  xor     edi, edi
0x18003d66b  jmp     short loc_18003D6AB
0x18003d66d  mov     ebx, 14h
0x18003d672  jmp     short loc_18003D669
0x18003d674  mov     ebx, 13h
0x18003d679  jmp     short loc_18003D669
0x18003d67b  mov     ebx, 12h
0x18003d680  jmp     short loc_18003D669
0x18003d682  mov     ebx, 11h
0x18003d687  jmp     short loc_18003D669
0x18003d689  mov     ebx, 0Fh
0x18003d68e  jmp     short loc_18003D6AB
0x18003d690  mov     ebx, 0Eh
0x18003d695  jmp     loc_18003D5E7
0x18003d69a  mov     ebx, 0Bh
0x18003d69f  jmp     loc_18003D5E5
0x18003d6a4  mov     ebx, 0Ah
0x18003d6a9  mov     edi, edx
0x18003d6ab  lea     rax, [rbp+57h+hKey]
0x18003d6af  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003d6b4  mov     r9d, 20019h; samDesired
0x18003d6ba  xor     r8d, r8d; ulOptions
0x18003d6bd  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003d6c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d6cb  call    cs:__imp_RegOpenKeyExW
0x18003d6d1  mov     r13d, 80070000h
0x18003d6d7  test    eax, eax
0x18003d6d9  jle     short loc_18003D6E1
0x18003d6db  movzx   eax, ax
0x18003d6de  or      eax, r13d
0x18003d6e1  mov     [rbp+57h+var_A0], eax
0x18003d6e4  test    eax, eax
0x18003d6e6  mov     eax, 1132h
0x18003d6eb  jns     short loc_18003D6F6
0x18003d6ed  mov     [rbp+57h+var_9A], ax
0x18003d6f1  jmp     loc_18003D965
0x18003d6f6  mov     [rbp+57h+var_9C], ax
0x18003d6fa  mov     r9d, r12d; int
0x18003d6fd  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x18003d701  lea     rdx, c_wszSafedocsDisableMonitoring; "DisableMonitoring"
0x18003d708  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d70c  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18003d711  mov     ecx, eax
0x18003d713  mov     [rbp+57h+var_A0], eax
0x18003d716  test    eax, eax
0x18003d718  mov     eax, 1133h
0x18003d71d  js      short loc_18003D6ED
0x18003d71f  mov     [rbp+57h+var_9C], ax
0x18003d723  test    ecx, ecx
0x18003d725  jnz     short loc_18003D736
0x18003d727  cmp     [rbp+57h+var_A8], ecx
0x18003d72a  jz      short loc_18003D736
0x18003d72c  cmp     r14d, 0Eh
0x18003d730  jnz     loc_18003D8AE
0x18003d736  cmp     edi, 7FFFFFFFh
0x18003d73c  jz      short loc_18003D797
0x18003d73e  test    cs:Microsoft_Windows_WindowsBackupEnableBits, r12b
0x18003d745  jz      short loc_18003D781
0x18003d747  mov     [rbp+57h+var_A8], edi
0x18003d74a  lea     rax, [rbp+57h+var_A8]
0x18003d74e  mov     [rbp+57h+var_40], rax
0x18003d752  mov     [rbp+57h+var_38], 4
0x18003d75a  lea     rax, [rbp+57h+var_50]
0x18003d75e  mov     [rsp+0E0h+phkResult], rax
0x18003d763  mov     r9d, 2
0x18003d769  lea     rdx, HCEVENT_HIDDEN; "e"
0x18003d770  call    McGenEventWrite_EventWriteTransfer
0x18003d775  test    eax, eax
0x18003d777  jle     short loc_18003D783
0x18003d779  movzx   eax, ax
0x18003d77c  or      eax, r13d
0x18003d77f  jmp     short loc_18003D783
0x18003d781  xor     eax, eax
0x18003d783  mov     [rbp+57h+var_A0], eax
0x18003d786  test    eax, eax
0x18003d788  mov     eax, 113Eh
0x18003d78d  js      loc_18003D6ED
0x18003d793  mov     [rbp+57h+var_9C], ax
0x18003d797  cmp     ebx, 7FFFFFFFh
0x18003d79d  jz      loc_18003D8AE
0x18003d7a3  lea     rcx, [rbp+57h+var_60]; this
0x18003d7a7  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18003d7ac  test    esi, esi
0x18003d7ae  jz      loc_18003D877
0x18003d7b4  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d7b8  test    rcx, rcx
0x18003d7bb  jz      short loc_18003D7E7
0x18003d7bd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003d7c1  jz      short loc_18003D7CF
0x18003d7c3  call    cs:__imp_RegCloseKey
0x18003d7c9  xor     ecx, ecx; hKey
0x18003d7cb  mov     [rbp+57h+hKey], rcx
0x18003d7cf  lea     rax, [rcx-1]
0x18003d7d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d7d7  ja      short loc_18003D7E7
0x18003d7d9  call    cs:__imp_RegCloseKey
0x18003d7df  mov     [rbp+57h+hKey], 0
0x18003d7e7  lea     rax, [rbp+57h+hKey]
0x18003d7eb  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003d7f0  mov     r9d, 20019h; samDesired
0x18003d7f6  xor     r8d, r8d; ulOptions
0x18003d7f9  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003d800  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d807  call    cs:__imp_RegOpenKeyExW
0x18003d80d  test    eax, eax
0x18003d80f  jle     short loc_18003D817
0x18003d811  movzx   eax, ax
0x18003d814  or      eax, r13d
0x18003d817  mov     [rbp+57h+var_A0], eax
0x18003d81a  test    eax, eax
0x18003d81c  mov     eax, 1148h
0x18003d821  js      loc_18003D6ED
0x18003d827  mov     [rbp+57h+var_9C], ax
0x18003d82b  mov     r9d, r12d; int
0x18003d82e  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x18003d832  lea     rdx, c_wszSafedocsScheduleLastResultTime; "LastResultTime"
0x18003d839  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d83d  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18003d842  mov     [rbp+57h+var_A0], eax
0x18003d845  test    eax, eax
0x18003d847  mov     eax, 1149h
0x18003d84c  js      loc_18003D6ED
0x18003d852  mov     [rbp+57h+var_9C], ax
0x18003d856  lea     r9, [rbp+57h+var_60]; struct CBsString *
0x18003d85a  mov     rcx, qword ptr [rbp+57h+var_68.dwLowDateTime]; struct _FILETIME
0x18003d85e  call    ?SxUTCFileTimeToString@@YAJU_FILETIME@@KKPEAVCBsString@@@Z; SxUTCFileTimeToString(_FILETIME,ulong,ulong,CBsString *)
0x18003d863  mov     [rbp+57h+var_A0], eax
0x18003d866  test    eax, eax
0x18003d868  mov     eax, 114Ah
0x18003d86d  js      loc_18003D6ED
0x18003d873  mov     [rbp+57h+var_9C], ax
0x18003d877  test    cs:Microsoft_Windows_WindowsBackupEnableBits, r12b
0x18003d87e  jz      short loc_18003D898
0x18003d880  mov     r9, [rbp+57h+var_60]
0x18003d884  mov     r8d, ebx
0x18003d887  call    McTemplateU0qz_EventWriteTransfer
0x18003d88c  test    eax, eax
0x18003d88e  jle     short loc_18003D89A
0x18003d890  movzx   eax, ax
0x18003d893  or      eax, r13d
0x18003d896  jmp     short loc_18003D89A
0x18003d898  xor     eax, eax
0x18003d89a  mov     [rbp+57h+var_A0], eax
0x18003d89d  test    eax, eax
0x18003d89f  mov     eax, 114Eh
0x18003d8a4  js      loc_18003D6ED
0x18003d8aa  mov     [rbp+57h+var_9C], ax
0x18003d8ae  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d8b2  lea     rax, [rcx-1]
0x18003d8b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d8ba  ja      short loc_18003D8C8
0x18003d8bc  call    cs:__imp_RegCloseKey
0x18003d8c2  xor     ecx, ecx; hKey
0x18003d8c4  mov     [rbp+57h+hKey], rcx
0x18003d8c8  cmp     r14d, 0Eh
0x18003d8cc  jz      loc_18003D965
0x18003d8d2  lea     rax, [rcx-1]
0x18003d8d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003d8da  ja      short loc_18003D8EA
0x18003d8dc  call    cs:__imp_RegCloseKey
0x18003d8e2  mov     [rbp+57h+hKey], 0
0x18003d8ea  lea     rax, [rbp+57h+hKey]
0x18003d8ee  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18003d8f3  mov     r9d, 2001Fh; samDesired
0x18003d8f9  xor     r8d, r8d; ulOptions
0x18003d8fc  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003d903  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d90a  call    cs:__imp_RegOpenKeyExW
0x18003d910  test    eax, eax
0x18003d912  jnz     short loc_18003D965
0x18003d914  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18003d918  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18003d91d  mov     [rbp+57h+var_A0], eax
0x18003d920  test    eax, eax
0x18003d922  mov     eax, 1159h
0x18003d927  js      loc_18003D6ED
0x18003d92d  mov     [rbp+57h+var_9C], ax
0x18003d931  mov     r8d, r14d; unsigned int
0x18003d934  lea     rdx, c_wszSafedocsScheduleActionCenterstate; "ActionCenterState"
0x18003d93b  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d93f  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18003d944  mov     [rbp+57h+var_A0], eax
0x18003d947  test    eax, eax
0x18003d949  jns     short loc_18003D955
0x18003d94b  mov     eax, 115Ah
0x18003d950  jmp     loc_18003D6ED
0x18003d955  mov     [rbp+57h+var_A0], 0
0x18003d95c  mov     eax, 115Bh
0x18003d961  mov     [rbp+57h+var_9C], ax
0x18003d965  mov     ebx, [rbp+57h+var_A0]
0x18003d968  lea     rcx, [rbp+57h+var_60]; this
0x18003d96c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003d971  mov     rcx, [rbp+57h+hKey]; hKey
0x18003d975  lea     rdx, [rcx-1]
0x18003d979  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003d97d  ja      short loc_18003D98D
0x18003d97f  call    cs:__imp_RegCloseKey
0x18003d985  mov     [rbp+57h+hKey], 0
0x18003d98d  lea     rcx, [rbp+57h+var_A0]; this
0x18003d991  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003d996  mov     eax, ebx
0x18003d998  mov     rcx, [rbp+57h+var_30]
0x18003d99c  xor     rcx, rsp; StackCookie
0x18003d99f  call    __security_check_cookie
0x18003d9a4  lea     r11, [rsp+0E0h+var_20]
  ... truncated ...
```
