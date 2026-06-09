# Sm::LoadInstapiIfNeeded(void)

- ea: `0x38388ee10`
- end: `0x38388f0a5`
- name: `?LoadInstapiIfNeeded@Sm@@SAKXZ`
- size: `661`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x38388ffe0`

## callees

- `0x3838434c0`
- `0x383846430`
- `0x383881430`
- `0x38388ee10`
- `0x38391ac20`
- `0x38391ac40`
- `0x38391ae80`
- `0x383ab0c30`
- `0x383adb7a0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x38388f03f`
- `KERNEL32!FreeLibrary` at `0x38388f03f`
- `KERNEL32!GetLastError` at `0x383902f56`
- `KERNEL32!GetLastError` at `0x383902f9b`
- `KERNEL32!GetLastError` at `0x383902fe0`
- `KERNEL32!GetLastError` at `0x383902f56`
- `KERNEL32!GetLastError` at `0x383902f9b`
- `KERNEL32!GetLastError` at `0x383902fe0`
- `KERNEL32!GetProcAddress` at `0x38388eff6`
- `KERNEL32!GetProcAddress` at `0x38388f013`
- `KERNEL32!GetProcAddress` at `0x38388eff6`
- `KERNEL32!GetProcAddress` at `0x38388f013`
- `KERNEL32!LoadLibraryA` at `0x38388efda`
- `KERNEL32!LoadLibraryA` at `0x38388efda`
- `ADVAPI32!RegOpenKeyExA` at `0x38388ef06`
- `ADVAPI32!RegOpenKeyExA` at `0x38388ef06`
- `ADVAPI32!RegQueryValueExA` at `0x38388ef45`
- `ADVAPI32!RegQueryValueExA` at `0x38388ef45`
- `ADVAPI32!RegCloseKey` at `0x38388ef52`
- `ADVAPI32!RegCloseKey` at `0x38388ef52`

## string_xrefs

- `0x38388ef80`: `instapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Sm::LoadInstapiIfNeeded(void)
{
  DWORD Value; // ebx
  _QWORD *v1; // rax
  signed __int64 v2; // rdi
  unsigned int v3; // eax
  HMODULE LibraryA; // rax
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax
  DWORD Type[2]; // [rsp+40h] [rbp-C8h] BYREF
  HKEY hKey[2]; // [rsp+48h] [rbp-C0h] BYREF
  char v10[16]; // [rsp+58h] [rbp-B0h] BYREF
  CHAR SubKey[48]; // [rsp+68h] [rbp-A0h] BYREF
  BYTE Data[272]; // [rsp+98h] [rbp-70h] BYREF
  CHAR LibFileName[288]; // [rsp+1A8h] [rbp+A0h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  Value = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48BF0[0] && bidID != -1 )
    off_383B15048();
  if ( _InterlockedCompareExchange64(&qword_383B23810, 0, 0) )
    goto LABEL_16;
  v1 = (_QWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 24);
  v2 = (signed __int64)v1;
  if ( !v1 )
  {
    Value = 14;
LABEL_41:
    if ( (bidGblFlags & 2) != 0 && off_383B47B90[0] )
    {
      SniErrorIdFromStringId(0xC3D8u);
      bidTraceA(off_383B45510[0], 345088, off_383B47B90[0], 4);
    }
    SNISetLastError(4, Value, 50136);
LABEL_16:
    if ( (bidGblFlags & 0x20002) == 0x20002 )
    {
      if ( off_383B47B88[0] )
        bidTraceA(off_383B45508[0], 347136, off_383B47B88[0], Value);
    }
    return Value;
  }
  *v1 = 0;
  strcpy(SubKey, "Software\\Microsoft\\Microsoft SQL Server\\90");
  v3 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, hKey);
  Value = v3;
  if ( v3 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B47BC0[0] )
      bidTraceA(off_383B45540[0], 237568, off_383B47BC0[0], v3);
LABEL_13:
    if ( *(_QWORD *)v2 )
      FreeLibrary(*(HMODULE *)v2);
    ((void (__fastcall *)(struct IMalloc *, signed __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v2);
    if ( !Value )
      goto LABEL_16;
    goto LABEL_41;
  }
  Type[0] = 260;
  Value = RegQueryValueExA(hKey[0], "SharedCode", 0, &Type[1], Data, Type);
  RegCloseKey(hKey[0]);
  if ( Value )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B47BB8[0] )
      bidTraceA(off_383B45538[0], 256000, off_383B47BB8[0], Value);
    goto LABEL_13;
  }
  if ( Type[1] != 1 )
  {
    Value = 13;
    goto LABEL_13;
  }
  if ( Type[0] >= 0x105uLL )
    _report_gsfailure(0);
  Data[Type[0]] = 0;
  strcpy(v10, "instapi.dll");
  if ( (int)StringCchPrintf_lA(LibFileName, 0x111u, "%s%s", 0, Data, v10) < 0 )
  {
    Value = 87;
    goto LABEL_13;
  }
  LibFileName[272] = 0;
  LibraryA = LoadLibraryA(LibFileName);
  *(_QWORD *)v2 = LibraryA;
  if ( !LibraryA )
  {
    Value = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B47BB0[0] )
      bidTraceA(off_383B45530[0], 288768, off_383B47BB0[0], Value);
    goto LABEL_13;
  }
  ProcAddress = GetProcAddress(LibraryA, "GetSvcInstanceIDFromName");
  *(_QWORD *)(v2 + 8) = ProcAddress;
  if ( !ProcAddress )
  {
    Value = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B47BA8[0] )
      bidTraceA(off_383B45528[0], 302080, off_383B47BA8[0], Value);
    goto LABEL_13;
  }
  v6 = GetProcAddress(*(HMODULE *)v2, "GetSQLInstanceRegStringByID");
  *(_QWORD *)(v2 + 16) = v6;
  if ( !v6 )
  {
    Value = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B47BA0[0] )
      bidTraceA(off_383B45520[0], 315392, off_383B47BA0[0], Value);
    goto LABEL_13;
  }
  if ( _InterlockedCompareExchange64(&qword_383B23810, v2, 0) )
    goto LABEL_13;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B47B98[0] )
    bidTraceA(off_383B45518[0], 330752, off_383B47B98[0], 0);
  return 0;
}

```

## disassembly

```asm
0x38388ee10  mov     rax, rsp
0x38388ee13  push    rbp
0x38388ee14  lea     rbp, [rax-1D8h]
0x38388ee1b  sub     rsp, 2D0h
0x38388ee22  mov     [rsp+2D0h+var_288], 0FFFFFFFFFFFFFFFEh
0x38388ee2b  mov     [rax+8], rbx
0x38388ee2f  mov     [rax+10h], rdi
0x38388ee33  mov     rax, cs:__security_cookie
0x38388ee3a  xor     rax, rsp
0x38388ee3d  mov     [rbp+1D0h+var_10], rax
0x38388ee44  xor     ebx, ebx
0x38388ee46  mov     qword ptr [rsp+2D0h+var_2A0], 0FFFFFFFFFFFFFFFFh
0x38388ee4f  mov     eax, cs:_bidGblFlags
0x38388ee55  and     eax, 20004h
0x38388ee5a  cmp     eax, 20004h
0x38388ee5f  jz      loc_383902E74
0x38388ee65  xor     eax, eax
0x38388ee67  lock cmpxchg cs:qword_383B23810, rbx
0x38388ee70  jnz     loc_38388F05D
0x38388ee76  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x38388ee7d  mov     rax, [rcx]
0x38388ee80  mov     edx, 18h
0x38388ee85  call    qword ptr [rax+58h]
0x38388ee88  mov     rdi, rax
0x38388ee8b  test    rax, rax
0x38388ee8e  jz      loc_383902EC0
0x38388ee94  mov     [rax], rbx
0x38388ee97  mov     rax, qword ptr cs:aSoftwareMicros_1; "Software\\Microsoft\\Microsoft SQL Serv"...
0x38388ee9e  mov     qword ptr [rsp+2D0h+SubKey], rax
0x38388eea3  mov     rax, qword ptr cs:aSoftwareMicros_1+8; "\\Microsoft\\Microsoft SQL Server\\90"
0x38388eeaa  mov     [rsp+2D0h+var_268], rax
0x38388eeaf  mov     rax, qword ptr cs:aSoftwareMicros_1+10h; "ft\\Microsoft SQL Server\\90"
0x38388eeb6  mov     [rsp+2D0h+var_260], rax
0x38388eebb  mov     rax, qword ptr cs:aSoftwareMicros_1+18h; "soft SQL Server\\90"
0x38388eec2  mov     [rsp+2D0h+var_258], rax
0x38388eec7  mov     rax, qword ptr cs:aSoftwareMicros_1+20h; " Server\\90"
0x38388eece  mov     [rbp+1D0h+var_250], rax
0x38388eed2  movzx   eax, word ptr cs:aSoftwareMicros_1+28h; "90"
0x38388eed9  mov     [rbp+1D0h+var_248], ax
0x38388eedd  movzx   eax, byte ptr cs:aSoftwareMicros_1+2Ah; ""
0x38388eee4  mov     [rbp+1D0h+var_246], al
0x38388eee7  lea     rax, [rsp+2D0h+hKey]
0x38388eeec  mov     [rsp+2D0h+phkResult], rax; phkResult
0x38388eef1  mov     r9d, 1; samDesired
0x38388eef7  xor     r8d, r8d; ulOptions
0x38388eefa  lea     rdx, [rsp+2D0h+SubKey]; lpSubKey
0x38388eeff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x38388ef06  call    cs:__imp_RegOpenKeyExA
0x38388ef0c  mov     ebx, eax
0x38388ef0e  test    eax, eax
0x38388ef10  jnz     loc_383902EC8
0x38388ef16  mov     [rsp+2D0h+Type], 104h
0x38388ef1e  lea     rax, [rsp+2D0h+Type]
0x38388ef23  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x38388ef28  lea     rax, [rbp+1D0h+Data]
0x38388ef2c  mov     [rsp+2D0h+phkResult], rax; lpData
0x38388ef31  lea     r9, [rsp+2D0h+Type+4]; lpType
0x38388ef36  xor     r8d, r8d; lpReserved
0x38388ef39  lea     rdx, ValueName; "SharedCode"
0x38388ef40  mov     rcx, [rsp+2D0h+hKey]; hKey
0x38388ef45  call    cs:__imp_RegQueryValueExA
0x38388ef4b  mov     ebx, eax
0x38388ef4d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x38388ef52  call    cs:__imp_RegCloseKey
0x38388ef58  test    ebx, ebx
0x38388ef5a  jnz     loc_383902F05
0x38388ef60  cmp     [rsp+2D0h+Type+4], 1
0x38388ef65  jnz     loc_383902F42
0x38388ef6b  mov     eax, [rsp+2D0h+Type]
0x38388ef6f  cmp     rax, 105h
0x38388ef75  jnb     loc_3839030E6
0x38388ef7b  mov     [rbp+rax+1D0h+Data], 0
0x38388ef80  mov     rax, qword ptr cs:aInstapiDll; "instapi.dll"
0x38388ef87  mov     qword ptr [rsp+2D0h+var_280], rax
0x38388ef8c  mov     eax, dword ptr cs:aInstapiDll+8; "dll"
0x38388ef92  mov     dword ptr [rsp+2D0h+var_280+8], eax
0x38388ef96  lea     rax, [rsp+2D0h+var_280]
0x38388ef9b  mov     [rsp+2D0h+lpcbData], rax
0x38388efa0  lea     rax, [rbp+1D0h+Data]
0x38388efa4  mov     [rsp+2D0h+phkResult], rax
0x38388efa9  xor     r9d, r9d; struct localeinfo_struct *
0x38388efac  lea     r8, aSS_16; "%s%s"
0x38388efb3  mov     edx, 111h; unsigned __int64
0x38388efb8  lea     rcx, [rbp+1D0h+LibFileName]; char *
0x38388efbf  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAUlocaleinfo_struct@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,localeinfo_struct *,...)
0x38388efc4  test    eax, eax
0x38388efc6  js      loc_383902F4C
0x38388efcc  mov     [rbp+1D0h+var_20], 0
0x38388efd3  lea     rcx, [rbp+1D0h+LibFileName]; lpLibFileName
0x38388efda  call    cs:__imp_LoadLibraryA
0x38388efe0  mov     [rdi], rax
0x38388efe3  test    rax, rax
0x38388efe6  jz      loc_383902F56
0x38388efec  lea     rdx, ProcName; "GetSvcInstanceIDFromName"
0x38388eff3  mov     rcx, rax; hModule
0x38388eff6  call    cs:__imp_GetProcAddress
0x38388effc  mov     [rdi+8], rax
0x38388f000  test    rax, rax
0x38388f003  jz      loc_383902F9B
0x38388f009  lea     rdx, aGetsqlinstance; "GetSQLInstanceRegStringByID"
0x38388f010  mov     rcx, [rdi]; hModule
0x38388f013  call    cs:__imp_GetProcAddress
0x38388f019  mov     [rdi+10h], rax
0x38388f01d  test    rax, rax
0x38388f020  jz      loc_383902FE0
0x38388f026  xor     eax, eax
0x38388f028  lock cmpxchg cs:qword_383B23810, rdi
0x38388f031  jz      loc_383895926
0x38388f037  mov     rcx, [rdi]; hLibModule
0x38388f03a  test    rcx, rcx
0x38388f03d  jz      short loc_38388F045
0x38388f03f  call    cs:__imp_FreeLibrary
0x38388f045  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x38388f04c  mov     rax, [rcx]
0x38388f04f  mov     rdx, rdi
0x38388f052  call    qword ptr [rax+68h]
0x38388f055  test    ebx, ebx
0x38388f057  jnz     loc_383903025
0x38388f05d  mov     eax, cs:_bidGblFlags
0x38388f063  and     eax, 20002h
0x38388f068  cmp     eax, 20002h
0x38388f06d  jz      loc_3839030EE
0x38388f073  cmp     qword ptr [rsp+2D0h+var_2A0], 0FFFFFFFFFFFFFFFFh
0x38388f079  jnz     loc_38390311F
0x38388f07f  mov     eax, ebx
0x38388f081  mov     rcx, [rbp+1D0h+var_10]
0x38388f088  xor     rcx, rsp; StackCookie
0x38388f08b  call    __security_check_cookie
0x38388f090  lea     r11, [rsp+2D0h+var_s0]
0x38388f098  mov     rbx, [r11+10h]
0x38388f09c  mov     rdi, [r11+18h]
0x38388f0a0  mov     rsp, r11
0x38388f0a3  pop     rbp
0x38388f0a4  retn
0x383895926  mov     eax, cs:_bidGblFlags
0x38389592c  and     eax, 20002h
0x383895931  cmp     eax, 20002h
0x383895936  jz      loc_383903081
0x38389593c  cmp     qword ptr [rsp+2D0h+var_2A0], 0FFFFFFFFFFFFFFFFh
0x383895942  jnz     loc_3839030B2
0x383895948  xor     eax, eax
0x38389594a  jmp     loc_38388F081
0x383902e74  mov     rax, cs:off_383B48BF0; "<Sm::LoadInstapiIfNeeded|API|SNI> \n"
0x383902e7b  test    rax, rax
0x383902e7e  jz      loc_38388EE65
0x383902e84  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383902e8c  jz      loc_38388EE65
0x383902e92  mov     [rsp+2D0h+lpcbData], rbx
0x383902e97  mov     rax, cs:off_383B48BF0; "<Sm::LoadInstapiIfNeeded|API|SNI> \n"
0x383902e9e  mov     [rsp+2D0h+phkResult], rax
0x383902ea3  lea     r9, [rsp+2D0h+var_2A0]
0x383902ea8  xor     r8d, r8d
0x383902eab  xor     edx, edx
0x383902ead  mov     rcx, cs:_bidID
0x383902eb4  call    cs:off_383B15048
0x383902eba  nop
0x383902ebb  jmp     loc_38388EE65
0x383902ec0  lea     ebx, [rax+0Eh]
0x383902ec3  jmp     loc_383903025
0x383902ec8  test    byte ptr cs:_bidGblFlags, 2
0x383902ecf  jz      loc_38388F037
0x383902ed5  mov     rcx, cs:off_383B47BC0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x383902edc  test    rcx, rcx
0x383902edf  jz      loc_38388F037
0x383902ee5  mov     r9d, eax
0x383902ee8  mov     r8, cs:off_383B47BC0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x383902eef  mov     edx, 3A000h
0x383902ef4  mov     rcx, cs:off_383B45540; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383902efb  call    _bidTraceA
0x383902f00  jmp     loc_38388F037
0x383902f05  test    byte ptr cs:_bidGblFlags, 2
0x383902f0c  jz      loc_38388F037
0x383902f12  mov     rax, cs:off_383B47BB8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x383902f19  test    rax, rax
0x383902f1c  jz      loc_38388F037
0x383902f22  mov     r9d, ebx
0x383902f25  mov     r8, cs:off_383B47BB8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Canno"...
0x383902f2c  mov     edx, 3E800h
0x383902f31  mov     rcx, cs:off_383B45538; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383902f38  call    _bidTraceA
0x383902f3d  jmp     loc_38388F037
0x383902f42  mov     ebx, 0Dh
0x383902f47  jmp     loc_38388F037
0x383902f4c  mov     ebx, 57h ; 'W'
0x383902f51  jmp     loc_38388F037
0x383902f56  call    cs:__imp_GetLastError
0x383902f5c  mov     ebx, eax
0x383902f5e  test    byte ptr cs:_bidGblFlags, 2
0x383902f65  jz      loc_38388F037
0x383902f6b  mov     rax, cs:off_383B47BB0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x383902f72  test    rax, rax
0x383902f75  jz      loc_38388F037
0x383902f7b  mov     r9d, ebx
0x383902f7e  mov     r8, cs:off_383B47BB0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x383902f85  mov     edx, 46800h
0x383902f8a  mov     rcx, cs:off_383B45530; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383902f91  call    _bidTraceA
0x383902f96  jmp     loc_38388F037
0x383902f9b  call    cs:__imp_GetLastError
0x383902fa1  mov     ebx, eax
0x383902fa3  test    byte ptr cs:_bidGblFlags, 2
0x383902faa  jz      loc_38388F037
0x383902fb0  mov     rax, cs:off_383B47BA8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x383902fb7  test    rax, rax
0x383902fba  jz      loc_38388F037
0x383902fc0  mov     r9d, ebx
0x383902fc3  mov     r8, cs:off_383B47BA8; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x383902fca  mov     edx, 49C00h
0x383902fcf  mov     rcx, cs:off_383B45528; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383902fd6  call    _bidTraceA
0x383902fdb  jmp     loc_38388F037
0x383902fe0  call    cs:__imp_GetLastError
0x383902fe6  mov     ebx, eax
0x383902fe8  test    byte ptr cs:_bidGblFlags, 2
0x383902fef  jz      loc_38388F037
0x383902ff5  mov     rax, cs:off_383B47BA0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x383902ffc  test    rax, rax
0x383902fff  jz      loc_38388F037
0x383903005  mov     r9d, ebx
0x383903008  mov     r8, cs:off_383B47BA0; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Faile"...
0x38390300f  mov     edx, 4D000h
0x383903014  mov     rcx, cs:off_383B45520; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x38390301b  call    _bidTraceA
0x383903020  jmp     loc_38388F037
0x383903025  test    byte ptr cs:_bidGblFlags, 2
0x38390302c  jz      short loc_38390306A
0x38390302e  mov     rax, cs:off_383B47B90; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Provi"...
0x383903035  test    rax, rax
0x383903038  jz      short loc_38390306A
0x38390303a  mov     ecx, 0C3D8h; unsigned int
0x38390303f  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383903044  mov     dword ptr [rsp+2D0h+lpcbData], ebx
0x383903048  mov     dword ptr [rsp+2D0h+phkResult], eax
0x38390304c  mov     r9d, 4
0x383903052  mov     r8, cs:off_383B47B90; "<Sm::LoadInstapiIfNeeded|ERR|SNI> Provi"...
0x383903059  mov     edx, 54400h
0x38390305e  mov     rcx, cs:off_383B45510; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383903065  call    _bidTraceA
0x38390306a  mov     r8d, 0C3D8h
0x383903070  mov     edx, ebx
0x383903072  mov     ecx, 4
0x383903077  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x38390307c  jmp     loc_38388F05D
0x383903081  mov     rax, cs:off_383B47B98; "<Sm::LoadInstapiIfNeeded|RET|SNI> Loade"...
0x383903088  test    rax, rax
0x38390308b  jz      loc_38389593C
0x383903091  xor     r9d, r9d
0x383903094  mov     r8, cs:off_383B47B98; "<Sm::LoadInstapiIfNeeded|RET|SNI> Loade"...
0x38390309b  mov     edx, 50C00h
0x3839030a0  mov     rcx, cs:off_383B45518; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3839030a7  call    _bidTraceA
0x3839030ac  nop
0x3839030ad  jmp     loc_38389593C
0x3839030b2  test    byte ptr cs:_bidGblFlags, 4
0x3839030b9  jz      loc_383895948
0x3839030bf  mov     rcx, cs:_bidID
0x3839030c6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3839030ca  jz      loc_383895948
0x3839030d0  lea     r9, [rsp+2D0h+var_2A0]
0x3839030d5  xor     r8d, r8d
0x3839030d8  xor     edx, edx
0x3839030da  call    cs:off_383B15058
0x3839030e0  nop
0x3839030e1  jmp     loc_383895948
0x3839030e6  xor     ecx, ecx; StackCookie
0x3839030e8  call    __report_gsfailure
0x3839030ee  mov     rax, cs:off_383B47B88; "<Sm::LoadInstapiIfNeeded|RET|SNI> %d{WI"...
0x3839030f5  test    rax, rax
0x3839030f8  jz      loc_38388F073
0x3839030fe  mov     r9d, ebx
0x383903101  mov     r8, cs:off_383B47B88; "<Sm::LoadInstapiIfNeeded|RET|SNI> %d{WI"...
0x383903108  mov     edx, 54C00h
0x38390310d  mov     rcx, cs:off_383B45508; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383903114  call    _bidTraceA
0x383903119  nop
0x38390311a  jmp     loc_38388F073
0x38390311f  test    byte ptr cs:_bidGblFlags, 4
0x383903126  jz      loc_38388F07F
0x38390312c  mov     rcx, cs:_bidID
0x383903133  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383903137  jz      loc_38388F07F
0x38390313d  lea     r9, [rsp+2D0h+var_2A0]
0x383903142  xor     r8d, r8d
0x383903145  xor     edx, edx
0x383903147  call    cs:off_383B15058
0x38390314d  nop
0x38390314e  jmp     loc_38388F07F
```
