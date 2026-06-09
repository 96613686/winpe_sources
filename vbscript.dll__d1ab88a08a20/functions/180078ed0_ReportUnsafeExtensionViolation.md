# ReportUnsafeExtensionViolation

- ea: `0x180078ed0`
- end: `0x180079123`
- name: `ReportUnsafeExtensionViolation`
- size: `595`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800265a8`
- `0x1800402a0`
- `0x180057c90`

## callees

- `0x180044cf0`
- `0x180047442`
- `0x180047600`
- `0x180047630`
- `0x180047714`
- `0x18004784d`
- `0x180078d68`
- `0x180078ed0`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `KERNEL32!WerGetFlags` at `0x1800790a9`
- `KERNEL32!WerGetFlags` at `0x1800790a9`
- `KERNEL32!WerSetFlags` at `0x1800790c3`
- `KERNEL32!WerSetFlags` at `0x1800790e6`
- `KERNEL32!WerSetFlags` at `0x1800790c3`
- `KERNEL32!WerSetFlags` at `0x1800790e6`
- `ADVAPI32!RegGetValueW` at `0x180078fb6`
- `ADVAPI32!RegGetValueW` at `0x180078fb6`

## string_xrefs

- `0x180078f9c`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180078f87`: `LastUnsafeExtensionReportTime`
- `0x180079029`: `FAULTREP.DLL`

## pseudocode

```c
int __fastcall ReportUnsafeExtensionViolation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE Library; // rax
  LSTATUS ValueW; // eax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // r8
  __int64 v13; // r9
  bool v14; // sf
  HMODULE v15; // rbx
  EFaultRepRetVal (__stdcall *ReportFault)(LPEXCEPTION_POINTERS, DWORD); // rdi
  HANDLE CurrentProcess_0; // rax
  DWORD pdwFlags; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int pvData[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v24[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  __int64 v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]

  v23 = 0;
  LODWORD(Library) = (unsigned int)memset_0(v24, 0, 0x98u);
  pdwFlags = 0;
  *(_QWORD *)pvData = 0;
  SystemTimeAsFileTime = 0;
  if ( dword_180093810 < 1 )
  {
    LODWORD(Library) = _InterlockedIncrement(&dword_180093810);
    if ( (int)Library <= 1 )
    {
      LODWORD(Library) = IsJITDebuggerPresent();
      if ( !(_DWORD)Library )
      {
        GetSystemTimeAsFileTime_0(&SystemTimeAsFileTime);
        pcbData[0] = 8;
        ValueW = RegGetValueW(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
                   L"LastUnsafeExtensionReportTime",
                   8u,
                   0,
                   pvData,
                   pcbData);
        v14 = ValueW < 0;
        if ( ValueW > 0 )
          v14 = 1;
        if ( v14 || pcbData[0] != 8 )
        {
          *(_QWORD *)pvData = 0;
        }
        else
        {
          *(_QWORD *)pcbData = *(_QWORD *)pvData;
          if ( *(unsigned __int64 *)&SystemTimeAsFileTime > *(_QWORD *)pvData )
          {
            LODWORD(Library) = SystemTimeAsFileTime.dwLowDateTime - pcbData[0];
            v11 = 604800000000000LL;
            if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)pcbData < 0x2260FF9290000uLL )
              return (int)Library;
          }
        }
        _RegSetKeyValueWithSDDL((HKEY)v11, v10, v12, v13, (BYTE *)&SystemTimeAsFileTime);
        Library = LoadLibraryExW_0(L"FAULTREP.DLL", 0, 0x800u);
        v15 = Library;
        if ( Library )
        {
          ReportFault = (EFaultRepRetVal (__stdcall *)(LPEXCEPTION_POINTERS, DWORD))GetProcAddress_0(
                                                                                      Library,
                                                                                      "ReportFault");
          if ( ReportFault )
          {
            v24[0] = -1073740791;
            *(_QWORD *)&v23 = v24;
            v25 = 0;
            v26 = 4;
            v27 = 26;
            v28 = a2;
            v29 = a3;
            v30 = a4;
            *((_QWORD *)&v23 + 1) = a1;
            CurrentProcess_0 = GetCurrentProcess_0();
            if ( WerGetFlags(CurrentProcess_0, &pdwFlags) >= 0 && WerSetFlags(pdwFlags & 0xFFFFFFCB | 0x24) >= 0 )
            {
              ((void (__fastcall *)(__int128 *, _QWORD))ReportFault)(&v23, 0);
              WerSetFlags(pdwFlags);
            }
          }
          LODWORD(Library) = FreeLibrary_0(v15);
        }
      }
    }
  }
  return (int)Library;
}

```

## disassembly

```asm
0x180078ed0  mov     [rsp-8+arg_8], rbx
0x180078ed5  mov     [rsp-8+arg_10], rsi
0x180078eda  push    rbp
0x180078edb  push    rdi
0x180078edc  push    r12
0x180078ede  push    r14
0x180078ee0  push    r15
0x180078ee2  lea     rbp, [rsp-20h]
0x180078ee7  sub     rsp, 120h
0x180078eee  mov     rax, cs:__security_cookie
0x180078ef5  xor     rax, rsp
0x180078ef8  mov     [rbp+40h+var_30], rax
0x180078efc  mov     r14, r8
0x180078eff  mov     r15, rdx
0x180078f02  mov     r12, rcx
0x180078f05  xorps   xmm0, xmm0
0x180078f08  xor     edx, edx; Val
0x180078f0a  lea     rcx, [rsp+140h+var_D0]; void *
0x180078f0f  mov     r8d, 98h; Size
0x180078f15  mov     rsi, r9
0x180078f18  movups  [rsp+140h+var_E0], xmm0
0x180078f1d  call    memset_0
0x180078f22  mov     ecx, 1
0x180078f27  mov     [rsp+140h+pdwFlags], 0
0x180078f2f  cmp     cs:dword_180093810, ecx
0x180078f35  mov     qword ptr [rsp+140h+var_F0], 0
0x180078f3e  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180078f47  jge     loc_1800790FA
0x180078f4d  mov     eax, ecx
0x180078f4f  lock xadd cs:dword_180093810, eax
0x180078f57  add     eax, ecx
0x180078f59  cmp     eax, ecx
0x180078f5b  jg      loc_1800790FA
0x180078f61  call    IsJITDebuggerPresent
0x180078f66  test    eax, eax
0x180078f68  jnz     loc_1800790FA
0x180078f6e  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180078f73  call    GetSystemTimeAsFileTime_0
0x180078f78  lea     rax, [rsp+140h+var_F8]
0x180078f7d  mov     ebx, 8
0x180078f82  mov     [rsp+140h+pcbData], rax; struct _SECURITY_ATTRIBUTES *
0x180078f87  lea     r8, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x180078f8e  lea     rax, [rsp+140h+var_F0]
0x180078f93  mov     [rsp+140h+var_F8], ebx
0x180078f97  mov     [rsp+140h+pvData], rax; unsigned int
0x180078f9c  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Internet Explorer"...
0x180078fa3  mov     r9d, ebx; dwFlags
0x180078fa6  mov     [rsp+140h+pdwType], 0; pdwType
0x180078faf  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180078fb6  call    cs:__imp_RegGetValueW
0x180078fbd  nop     dword ptr [rax+rax+00h]
0x180078fc2  test    eax, eax
0x180078fc4  jle     short loc_180078FD0
0x180078fc6  movzx   eax, ax
0x180078fc9  or      eax, 80070000h
0x180078fce  test    eax, eax
0x180078fd0  js      short loc_18007900F
0x180078fd2  cmp     [rsp+140h+var_F8], ebx
0x180078fd6  jnz     short loc_18007900F
0x180078fd8  mov     rax, qword ptr [rsp+140h+var_F0]
0x180078fdd  mov     [rsp+140h+var_F8], eax
0x180078fe1  shr     rax, 20h
0x180078fe5  mov     [rsp+140h+var_F8+4], eax
0x180078fe9  mov     rax, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180078fee  cmp     rax, qword ptr [rsp+140h+var_F8]
0x180078ff3  jbe     short loc_180079018
0x180078ff5  sub     rax, qword ptr [rsp+140h+var_F8]
0x180078ffa  mov     rcx, 2260FF9290000h
0x180079004  cmp     rax, rcx
0x180079007  jb      loc_1800790FA
0x18007900d  jmp     short loc_180079018
0x18007900f  mov     qword ptr [rsp+140h+var_F0], 0
0x180079018  lea     rax, [rsp+140h+SystemTimeAsFileTime]
0x18007901d  mov     [rsp+140h+pdwType], rax; lpData
0x180079022  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x180079027  xor     edx, edx; hFile
0x180079029  lea     rcx, aFaultrepDll; "FAULTREP.DLL"
0x180079030  mov     r8d, 800h; dwFlags
0x180079036  call    LoadLibraryExW_0
0x18007903b  mov     rbx, rax
0x18007903e  test    rax, rax
0x180079041  jz      loc_1800790FA
0x180079047  lea     rdx, aReportfault; "ReportFault"
0x18007904e  mov     rcx, rax; hModule
0x180079051  call    GetProcAddress_0
0x180079056  mov     rdi, rax
0x180079059  test    rax, rax
0x18007905c  jz      loc_1800790F2
0x180079062  lea     rax, [rsp+140h+var_D0]
0x180079067  mov     [rsp+140h+var_D0], 0C0000409h
0x18007906f  mov     qword ptr [rsp+140h+var_E0], rax
0x180079074  mov     [rbp+40h+var_C0], 0
0x18007907c  mov     [rbp+40h+var_B8], 4
0x180079083  mov     [rbp+40h+var_B0], 1Ah
0x18007908b  mov     [rbp+40h+var_A8], r15
0x18007908f  mov     [rbp+40h+var_A0], r14
0x180079093  mov     [rbp+40h+var_98], rsi
0x180079097  mov     qword ptr [rsp+140h+var_E0+8], r12
0x18007909c  call    GetCurrentProcess_0
0x1800790a1  mov     rcx, rax; hProcess
0x1800790a4  lea     rdx, [rsp+140h+pdwFlags]; pdwFlags
0x1800790a9  call    cs:__imp_WerGetFlags
0x1800790b0  nop     dword ptr [rax+rax+00h]
0x1800790b5  test    eax, eax
0x1800790b7  js      short loc_1800790F2
0x1800790b9  mov     ecx, [rsp+140h+pdwFlags]
0x1800790bd  and     ecx, 0FFFFFFEFh
0x1800790c0  or      ecx, 24h; dwFlags
0x1800790c3  call    cs:__imp_WerSetFlags
0x1800790ca  nop     dword ptr [rax+rax+00h]
0x1800790cf  test    eax, eax
0x1800790d1  js      short loc_1800790F2
0x1800790d3  xor     edx, edx
0x1800790d5  lea     rcx, [rsp+140h+var_E0]
0x1800790da  mov     rax, rdi
0x1800790dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790e2  mov     ecx, [rsp+140h+pdwFlags]; dwFlags
0x1800790e6  call    cs:__imp_WerSetFlags
0x1800790ed  nop     dword ptr [rax+rax+00h]
0x1800790f2  mov     rcx, rbx; hLibModule
0x1800790f5  call    FreeLibrary_0
0x1800790fa  mov     rcx, [rbp+40h+var_30]
0x1800790fe  xor     rcx, rsp; StackCookie
0x180079101  call    __security_check_cookie
0x180079106  lea     r11, [rsp+140h+var_20]
0x18007910e  mov     rbx, [r11+38h]
0x180079112  mov     rsi, [r11+40h]
0x180079116  mov     rsp, r11
0x180079119  pop     r15
0x18007911b  pop     r14
0x18007911d  pop     r12
0x18007911f  pop     rdi
0x180079120  pop     rbp
0x180079121  retn
```
