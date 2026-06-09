# CSxWindowsUpdateEnumerator::_LoadHiveForCBS(ushort const *,ushort const *,ushort const *,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)

- ea: `0x18000572c`
- end: `0x180005c65`
- name: `?_LoadHiveForCBS@CSxWindowsUpdateEnumerator@@CAJPEBG00P6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1PEAU_CBS_LOADED_HIVE_INFORMATION@1@@Z`
- size: `1337`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int64 (__fastcall *)(void *, __int64), void *, struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800055a4`

## callees

- `0x180003ce0`
- `0x18000572c`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dd64`
- `0x18000e330`
- `0x18000f154`
- `0x180014ec8`
- `0x180014f38`
- `0x18001528c`
- `0x180015760`
- `0x1800157be`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005825`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005adf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005bce`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005825`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005adf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005bce`
- `KERNEL32!CopyFileW` at `0x180005aa9`
- `KERNEL32!CopyFileW` at `0x180005aa9`
- `ADVAPI32!RegUnLoadKeyW` at `0x180005973`
- `ADVAPI32!RegUnLoadKeyW` at `0x180005973`
- `ADVAPI32!RegLoadKeyW` at `0x180005b9e`
- `ADVAPI32!RegLoadKeyW` at `0x180005b9e`
- `ole32!CoCreateGuid` at `0x18000597d`
- `ole32!CoCreateGuid` at `0x18000597d`
- `ServicingCommon!GetLoadedHiveKeyName` at `0x180005912`
- `ServicingCommon!GetLoadedHiveKeyName` at `0x180005912`

## string_xrefs

- `0x1800057a8`: `CSxWindowsUpdateEnumerator::_LoadHiveForCBS`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::_LoadHiveForCBS(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 (__fastcall *a4)(void *, __int64),
        void *a5,
        struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *a6)
{
  __int16 v10; // ax
  int LoadedHiveKeyName; // ebx
  __int64 v12; // rax
  __int64 v13; // rax
  LPCWSTR v14; // rax
  LSTATUS KeyW; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v18; // [rsp+24h] [rbp-DCh]
  __int16 v19; // [rsp+26h] [rbp-DAh]
  LPCWSTR lpNewFileName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v25[2]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v26[2]; // [rsp+98h] [rbp-68h] BYREF
  GUID pguid; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v17,
    "CSxWindowsUpdateEnumerator::_LoadHiveForCBS",
    0x77u,
    (unsigned __int16)a4);
  memset_0(SubKey, 0, 0x208u);
  v24 = 0;
  lpExistingFileName = (LPCWSTR)qword_18001A620;
  lpNewFileName = (LPCWSTR)qword_18001A620;
  v26[0] = (unsigned __int16 *)qword_18001A620;
  v25[0] = (unsigned __int16 *)qword_18001A620;
  SystemTimeAsFileTime[1] = 0;
  v21 = 0;
  pguid = GUID_NULL;
  v26[1] = 0;
  v25[1] = 0;
  SystemTimeAsFileTime[0] = 0;
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  v10 = 130;
  if ( !a3 || (v18 = 130, v10 = 131, !a1) || (v18 = 131, v10 = 132, !a2) || (v18 = 132, v10 = 133, !a6) )
  {
    v17 = -2147024809;
LABEL_6:
    v19 = v10;
LABEL_45:
    SxDeleteFile(lpNewFileName);
    LoadedHiveKeyName = v17;
    goto LABEL_46;
  }
  v18 = 133;
  v17 = 0;
  *(_OWORD *)a6 = 0;
  *((_QWORD *)a6 + 2) = 0;
  LoadedHiveKeyName = CBsString::Append((CBsString *)&lpExistingFileName, a1);
  v17 = LoadedHiveKeyName;
  v10 = 137;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 137;
  if ( (_DWORD)v24 )
  {
    v12 = (unsigned int)(v24 - 1);
    if ( lpExistingFileName[v12] == 92 && (unsigned int)v12 <= HIDWORD(v24) )
    {
      LODWORD(v24) = v24 - 1;
      lpExistingFileName[(unsigned int)v12] = 0;
    }
  }
  LoadedHiveKeyName = CBsString::Append((CBsString *)&lpExistingFileName, L"\\", a3);
  v17 = LoadedHiveKeyName;
  v10 = 139;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 139;
  LoadedHiveKeyName = GetLoadedHiveKeyName(lpExistingFileName, SubKey, 260);
  v17 = LoadedHiveKeyName;
  v10 = 141;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 141;
  LoadedHiveKeyName = a4(a5, 1);
  v17 = LoadedHiveKeyName;
  v10 = 143;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 143;
  if ( LoadedHiveKeyName == 1 )
  {
LABEL_20:
    v17 = -2147467260;
    goto LABEL_6;
  }
  RegUnLoadKeyW(HKEY_LOCAL_MACHINE, SubKey);
  LoadedHiveKeyName = CoCreateGuid(&pguid);
  v17 = LoadedHiveKeyName;
  v10 = 147;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 147;
  LoadedHiveKeyName = CBsString::Set((CBsString *)v26, &pguid);
  v17 = LoadedHiveKeyName;
  v10 = 148;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 148;
  LoadedHiveKeyName = CBsString::Append((CBsString *)v25, L"{cd42efe1-f6f1-427c-b004-033192c625a4}", v26[0]);
  v17 = LoadedHiveKeyName;
  v10 = 149;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 149;
  LoadedHiveKeyName = CBsString::Append((CBsString *)&lpNewFileName, a2);
  v17 = LoadedHiveKeyName;
  v10 = 151;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 151;
  if ( (_DWORD)v21 )
  {
    v13 = (unsigned int)(v21 - 1);
    if ( lpNewFileName[v13] == 92 && (unsigned int)v13 <= HIDWORD(v21) )
    {
      LODWORD(v21) = v21 - 1;
      lpNewFileName[(unsigned int)v13] = 0;
    }
  }
  LoadedHiveKeyName = CBsString::Append((CBsString *)&lpNewFileName, L"\\", v25[0]);
  v17 = LoadedHiveKeyName;
  v10 = 153;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 153;
  LoadedHiveKeyName = a4(a5, 1);
  v17 = LoadedHiveKeyName;
  v10 = 155;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 155;
  if ( LoadedHiveKeyName == 1 )
    goto LABEL_20;
  if ( !CopyFileW(lpExistingFileName, lpNewFileName, 0) )
  {
    LoadedHiveKeyName = GetLastFailureAsHRESULT();
    v17 = LoadedHiveKeyName;
    v10 = 162;
LABEL_11:
    v19 = v10;
    goto LABEL_44;
  }
  v17 = 0;
  v18 = 162;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  v14 = 0;
  v21 = 0;
  xmmword_18001D980 = *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime;
  if ( lpNewFileName != (LPCWSTR)qword_18001A620 )
    v14 = lpNewFileName;
  *(_QWORD *)a6 = v14;
  lpNewFileName = (LPCWSTR)qword_18001A620;
  LoadedHiveKeyName = SxCopyString(a3, (unsigned __int16 **)a6 + 2);
  v17 = LoadedHiveKeyName;
  v10 = 168;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 168;
  LoadedHiveKeyName = SxCopyString(SubKey, (unsigned __int16 **)a6 + 1);
  v17 = LoadedHiveKeyName;
  v10 = 169;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 169;
  LoadedHiveKeyName = ((__int64 (__fastcall *)(void *, __int64, _QWORD))a4)(a5, 1, 0);
  v17 = LoadedHiveKeyName;
  v10 = 171;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 171;
  if ( LoadedHiveKeyName == 1 )
    goto LABEL_20;
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, SubKey, *(LPCWSTR *)a6);
  LoadedHiveKeyName = KeyW;
  if ( KeyW > 0 )
    LoadedHiveKeyName = (unsigned __int16)KeyW | 0x80070000;
  v17 = LoadedHiveKeyName;
  v10 = 172;
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_11;
  v18 = 172;
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  LoadedHiveKeyName = v17;
  *(struct _FILETIME *)&xmmword_18001D980 = SystemTimeAsFileTime[1];
  *((struct _FILETIME *)&xmmword_18001D980 + 1) = SystemTimeAsFileTime[0];
LABEL_44:
  if ( LoadedHiveKeyName < 0 )
    goto LABEL_45;
LABEL_46:
  CBsString::_Release((CBsString *)v25);
  CBsString::_Release((CBsString *)v26);
  CBsString::_Release((CBsString *)&lpNewFileName);
  CBsString::_Release((CBsString *)&lpExistingFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)LoadedHiveKeyName;
}

```

## disassembly

```asm
0x18000572c  push    rbp
0x18000572e  push    rbx
0x18000572f  push    rsi
0x180005730  push    rdi
0x180005731  push    r12
0x180005733  push    r14
0x180005735  push    r15
0x180005737  lea     rbp, [rsp-1E0h]
0x18000573f  sub     rsp, 2E0h
0x180005746  mov     rax, cs:__security_cookie
0x18000574d  xor     rax, rsp
0x180005750  mov     [rbp+210h+var_40], rax
0x180005757  mov     rdi, [rbp+210h+arg_28]
0x18000575e  mov     r15, r9
0x180005761  mov     r12, [rbp+210h+arg_20]
0x180005768  mov     r14, r8
0x18000576b  mov     rsi, rdx
0x18000576e  mov     rbx, rcx
0x180005771  mov     rcx, cs:WPP_GLOBAL_Control
0x180005778  lea     rax, WPP_GLOBAL_Control
0x18000577f  cmp     rcx, rax
0x180005782  jz      short loc_1800057A2
0x180005784  test    dword ptr [rcx+1Ch], 20000000h
0x18000578b  jz      short loc_1800057A2
0x18000578d  mov     rcx, [rcx+10h]
0x180005791  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180005798  mov     edx, 0Ah
0x18000579d  call    WPP_SF_
0x1800057a2  mov     r8d, 77h ; 'w'; unsigned __int16
0x1800057a8  lea     rdx, aCsxwindowsupda_5; "CSxWindowsUpdateEnumerator::_LoadHiveFo"...
0x1800057af  lea     rcx, [rsp+310h+var_2F0]; this
0x1800057b4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800057b9  xor     edx, edx; Val
0x1800057bb  lea     rcx, [rbp+210h+SubKey]; void *
0x1800057bf  mov     r8d, 208h; Size
0x1800057c5  call    memset_0
0x1800057ca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800057d1  lea     rax, qword_18001A620
0x1800057d8  mov     [rbp+210h+var_290], 0
0x1800057e0  mov     [rsp+310h+lpExistingFileName], rax
0x1800057e5  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800057ea  mov     [rsp+310h+lpNewFileName], rax
0x1800057ef  mov     [rbp+210h+var_278], rax
0x1800057f3  mov     [rbp+210h+var_288], rax
0x1800057f7  xor     eax, eax
0x1800057f9  mov     qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x1800057fe  mov     [rsp+310h+var_2B0], 0
0x180005807  movdqu  xmmword ptr [rbp+210h+pguid.Data1], xmm0
0x18000580c  mov     [rbp+210h+var_270], 0
0x180005814  mov     [rbp+210h+var_280], 0
0x18000581c  mov     qword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005825  call    cs:__imp_GetSystemTimeAsFileTime
0x18000582b  mov     eax, 82h
0x180005830  test    r14, r14
0x180005833  jnz     short loc_180005847
0x180005835  mov     [rsp+310h+var_2F0], 80070057h
0x18000583d  mov     [rsp+310h+var_2EA], ax
0x180005842  jmp     loc_180005C04
0x180005847  mov     [rsp+310h+var_2EC], ax
0x18000584c  mov     eax, 83h
0x180005851  test    rbx, rbx
0x180005854  jz      short loc_180005835
0x180005856  mov     [rsp+310h+var_2EC], ax
0x18000585b  mov     eax, 84h
0x180005860  test    rsi, rsi
0x180005863  jz      short loc_180005835
0x180005865  mov     [rsp+310h+var_2EC], ax
0x18000586a  mov     eax, 85h
0x18000586f  test    rdi, rdi
0x180005872  jz      short loc_180005835
0x180005874  mov     [rsp+310h+var_2EC], ax
0x180005879  xorps   xmm0, xmm0
0x18000587c  xor     eax, eax
0x18000587e  mov     [rsp+310h+var_2F0], 0
0x180005886  movups  xmmword ptr [rdi], xmm0
0x180005889  mov     [rdi+10h], rax
0x18000588d  mov     rdx, rbx; unsigned __int16 *
0x180005890  lea     rcx, [rsp+310h+lpExistingFileName]; this
0x180005895  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000589a  mov     ebx, eax
0x18000589c  mov     [rsp+310h+var_2F0], eax
0x1800058a0  test    eax, eax
0x1800058a2  mov     eax, 89h
0x1800058a7  jns     short loc_1800058B3
0x1800058a9  mov     [rsp+310h+var_2EA], ax
0x1800058ae  jmp     loc_180005C00
0x1800058b3  mov     [rsp+310h+var_2EC], ax
0x1800058b8  mov     eax, dword ptr [rbp+210h+var_290]
0x1800058bb  test    eax, eax
0x1800058bd  jz      short loc_1800058DD
0x1800058bf  mov     rdx, [rsp+310h+lpExistingFileName]
0x1800058c4  dec     eax
0x1800058c6  mov     ecx, eax
0x1800058c8  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x1800058cd  jnz     short loc_1800058DD
0x1800058cf  cmp     eax, dword ptr [rbp+210h+var_290+4]
0x1800058d2  ja      short loc_1800058DD
0x1800058d4  mov     dword ptr [rbp+210h+var_290], eax
0x1800058d7  xor     eax, eax
0x1800058d9  mov     [rdx+rcx*2], ax
0x1800058dd  mov     r8, r14; unsigned __int16 *
0x1800058e0  lea     rdx, asc_1800180A8; "\\"
0x1800058e7  lea     rcx, [rsp+310h+lpExistingFileName]; this
0x1800058ec  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x1800058f1  mov     ebx, eax
0x1800058f3  mov     [rsp+310h+var_2F0], eax
0x1800058f7  test    eax, eax
0x1800058f9  mov     eax, 8Bh
0x1800058fe  js      short loc_1800058A9
0x180005900  mov     rcx, [rsp+310h+lpExistingFileName]
0x180005905  lea     r8d, [rax+79h]
0x180005909  lea     rdx, [rbp+210h+SubKey]
0x18000590d  mov     [rsp+310h+var_2EC], ax
0x180005912  call    cs:__imp_GetLoadedHiveKeyName
0x180005918  mov     ebx, eax
0x18000591a  mov     [rsp+310h+var_2F0], eax
0x18000591e  test    eax, eax
0x180005920  mov     eax, 8Dh
0x180005925  js      short loc_1800058A9
0x180005927  xor     r8d, r8d
0x18000592a  mov     [rsp+310h+var_2EC], ax
0x18000592f  mov     rcx, r12
0x180005932  mov     rax, r15
0x180005935  lea     edx, [r8+1]
0x180005939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593e  mov     ebx, eax
0x180005940  mov     [rsp+310h+var_2F0], eax
0x180005944  test    eax, eax
0x180005946  mov     eax, 8Fh
0x18000594b  js      loc_1800058A9
0x180005951  mov     [rsp+310h+var_2EC], ax
0x180005956  cmp     ebx, 1
0x180005959  jnz     short loc_180005968
0x18000595b  mov     [rsp+310h+var_2F0], 80004004h
0x180005963  jmp     loc_18000583D
0x180005968  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x18000596c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005973  call    cs:__imp_RegUnLoadKeyW
0x180005979  lea     rcx, [rbp+210h+pguid]; pguid
0x18000597d  call    cs:__imp_CoCreateGuid
0x180005983  mov     ebx, eax
0x180005985  mov     [rsp+310h+var_2F0], eax
0x180005989  test    eax, eax
0x18000598b  mov     eax, 93h
0x180005990  js      loc_1800058A9
0x180005996  lea     rdx, [rbp+210h+pguid]; struct _GUID *
0x18000599a  mov     [rsp+310h+var_2EC], ax
0x18000599f  lea     rcx, [rbp+210h+var_278]; this
0x1800059a3  call    ?Set@CBsString@@QEAAJAEBU_GUID@@@Z; CBsString::Set(_GUID const &)
0x1800059a8  mov     ebx, eax
0x1800059aa  mov     [rsp+310h+var_2F0], eax
0x1800059ae  test    eax, eax
0x1800059b0  mov     eax, 94h
0x1800059b5  js      loc_1800058A9
0x1800059bb  mov     [rsp+310h+var_2EC], ax
0x1800059c0  mov     r8, [rbp+210h+var_278]; unsigned __int16 *
0x1800059c4  lea     rdx, aCd42efe1F6f142; "{cd42efe1-f6f1-427c-b004-033192c625a4}"
0x1800059cb  lea     rcx, [rbp+210h+var_288]; this
0x1800059cf  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x1800059d4  mov     ebx, eax
0x1800059d6  mov     [rsp+310h+var_2F0], eax
0x1800059da  test    eax, eax
0x1800059dc  mov     eax, 95h
0x1800059e1  js      loc_1800058A9
0x1800059e7  mov     [rsp+310h+var_2EC], ax
0x1800059ec  mov     rdx, rsi; unsigned __int16 *
0x1800059ef  lea     rcx, [rsp+310h+lpNewFileName]; this
0x1800059f4  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x1800059f9  mov     ebx, eax
0x1800059fb  mov     [rsp+310h+var_2F0], eax
0x1800059ff  test    eax, eax
0x180005a01  mov     eax, 97h
0x180005a06  js      loc_1800058A9
0x180005a0c  mov     [rsp+310h+var_2EC], ax
0x180005a11  mov     eax, dword ptr [rsp+310h+var_2B0]
0x180005a15  test    eax, eax
0x180005a17  jz      short loc_180005A3B
0x180005a19  mov     r8, [rsp+310h+lpNewFileName]
0x180005a1e  dec     eax
0x180005a20  mov     ecx, eax
0x180005a22  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x180005a28  jnz     short loc_180005A3B
0x180005a2a  cmp     eax, dword ptr [rsp+310h+var_2B0+4]
0x180005a2e  ja      short loc_180005A3B
0x180005a30  mov     dword ptr [rsp+310h+var_2B0], eax
0x180005a34  xor     eax, eax
0x180005a36  mov     [r8+rcx*2], ax
0x180005a3b  mov     r8, [rbp+210h+var_288]; unsigned __int16 *
0x180005a3f  lea     rdx, asc_1800180A8; "\\"
0x180005a46  lea     rcx, [rsp+310h+lpNewFileName]; this
0x180005a4b  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x180005a50  mov     ebx, eax
0x180005a52  mov     [rsp+310h+var_2F0], eax
0x180005a56  test    eax, eax
0x180005a58  mov     eax, 99h
0x180005a5d  js      loc_1800058A9
0x180005a63  xor     r8d, r8d
0x180005a66  mov     [rsp+310h+var_2EC], ax
0x180005a6b  mov     rcx, r12
0x180005a6e  mov     rax, r15
0x180005a71  lea     esi, [r8+1]
0x180005a75  mov     edx, esi
0x180005a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a7c  mov     ebx, eax
0x180005a7e  mov     [rsp+310h+var_2F0], eax
0x180005a82  test    eax, eax
0x180005a84  mov     eax, 9Bh
0x180005a89  js      loc_1800058A9
0x180005a8f  mov     [rsp+310h+var_2EC], ax
0x180005a94  cmp     ebx, esi
0x180005a96  jz      loc_18000595B
0x180005a9c  mov     rdx, [rsp+310h+lpNewFileName]; lpNewFileName
0x180005aa1  xor     r8d, r8d; bFailIfExists
0x180005aa4  mov     rcx, [rsp+310h+lpExistingFileName]; lpExistingFileName
0x180005aa9  call    cs:__imp_CopyFileW
0x180005aaf  test    eax, eax
0x180005ab1  jnz     short loc_180005AC8
0x180005ab3  call    GetLastFailureAsHRESULT
0x180005ab8  mov     ebx, eax
0x180005aba  mov     [rsp+310h+var_2F0], eax
0x180005abe  mov     eax, 0A2h
0x180005ac3  jmp     loc_1800058A9
0x180005ac8  mov     eax, 0A2h
0x180005acd  mov     [rsp+310h+var_2F0], 0
0x180005ad5  lea     rcx, [rsp+310h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x180005ada  mov     [rsp+310h+var_2EC], ax
0x180005adf  call    cs:__imp_GetSystemTimeAsFileTime
0x180005ae5  movups  xmm0, xmmword ptr [rsp+310h+SystemTimeAsFileTime.dwLowDateTime]
0x180005aea  xor     eax, eax
0x180005aec  mov     [rsp+310h+var_2B0], 0
0x180005af5  lea     rcx, qword_18001A620
0x180005afc  cmp     [rsp+310h+lpNewFileName], rcx
0x180005b01  movdqu  cs:xmmword_18001D980, xmm0
0x180005b09  cmovnz  rax, [rsp+310h+lpNewFileName]
0x180005b0f  mov     [rdi], rax
0x180005b12  mov     [rsp+310h+lpNewFileName], rcx
0x180005b17  lea     rdx, [rdi+10h]; unsigned __int16 **
0x180005b1b  mov     rcx, r14; Src
0x180005b1e  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180005b23  mov     ebx, eax
0x180005b25  mov     [rsp+310h+var_2F0], eax
0x180005b29  test    eax, eax
0x180005b2b  mov     eax, 0A8h
0x180005b30  js      loc_1800058A9
0x180005b36  lea     rdx, [rdi+8]; unsigned __int16 **
0x180005b3a  mov     [rsp+310h+var_2EC], ax
0x180005b3f  lea     rcx, [rbp+210h+SubKey]; Src
0x180005b43  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180005b48  mov     ebx, eax
0x180005b4a  mov     [rsp+310h+var_2F0], eax
0x180005b4e  test    eax, eax
0x180005b50  mov     eax, 0A9h
0x180005b55  js      loc_1800058A9
0x180005b5b  mov     [rsp+310h+var_2EC], ax
0x180005b60  xor     r8d, r8d
0x180005b63  mov     rax, r15
0x180005b66  mov     edx, esi
0x180005b68  mov     rcx, r12
0x180005b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b70  mov     ebx, eax
0x180005b72  mov     [rsp+310h+var_2F0], eax
0x180005b76  test    eax, eax
0x180005b78  mov     eax, 0ABh
0x180005b7d  js      loc_1800058A9
0x180005b83  mov     [rsp+310h+var_2EC], ax
0x180005b88  cmp     ebx, esi
0x180005b8a  jz      loc_18000595B
0x180005b90  mov     r8, [rdi]; lpFile
0x180005b93  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x180005b97  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005b9e  call    cs:__imp_RegLoadKeyW
0x180005ba4  mov     ebx, eax
0x180005ba6  test    eax, eax
0x180005ba8  jle     short loc_180005BB3
0x180005baa  movzx   ebx, ax
0x180005bad  or      ebx, 80070000h
0x180005bb3  mov     [rsp+310h+var_2F0], ebx
0x180005bb7  mov     eax, 0ACh
0x180005bbc  test    ebx, ebx
0x180005bbe  js      loc_1800058A9
0x180005bc4  lea     rcx, [rsp+310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005bc9  mov     [rsp+310h+var_2EC], ax
0x180005bce  call    cs:__imp_GetSystemTimeAsFileTime
0x180005bd4  mov     eax, [rsp+310h+SystemTimeAsFileTime.dwLowDateTime+8]
0x180005bd8  mov     ebx, [rsp+310h+var_2F0]
0x180005bdc  mov     dword ptr cs:xmmword_18001D980, eax
0x180005be2  mov     eax, [rsp+310h+SystemTimeAsFileTime.dwHighDateTime+8]
0x180005be6  mov     dword ptr cs:xmmword_18001D980+4, eax
0x180005bec  mov     eax, [rsp+310h+SystemTimeAsFileTime.dwLowDateTime]
0x180005bf0  mov     dword ptr cs:xmmword_18001D980+8, eax
0x180005bf6  mov     eax, [rsp+310h+SystemTimeAsFileTime.dwHighDateTime]
0x180005bfa  mov     dword ptr cs:xmmword_18001D980+0Ch, eax
0x180005c00  test    ebx, ebx
0x180005c02  jns     short loc_180005C12
0x180005c04  mov     rcx, [rsp+310h+lpNewFileName]; lpFileName
0x180005c09  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x180005c0e  mov     ebx, [rsp+310h+var_2F0]
0x180005c12  lea     rcx, [rbp+210h+var_288]; this
0x180005c16  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005c1b  lea     rcx, [rbp+210h+var_278]; this
  ... truncated ...
```
