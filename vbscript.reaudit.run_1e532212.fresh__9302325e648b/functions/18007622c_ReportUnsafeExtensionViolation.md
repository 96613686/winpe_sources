# ReportUnsafeExtensionViolation

- ea: `0x18007622c`
- end: `0x180076462`
- name: `ReportUnsafeExtensionViolation`
- size: `566`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800396a0`
- `0x18003eb00`
- `0x1800562f0`

## callees

- `0x180043ae0`
- `0x180046032`
- `0x1800461f0`
- `0x180046220`
- `0x180046304`
- `0x18004643d`
- `0x1800760d4`
- `0x18007622c`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `KERNEL32!WerGetFlags` at `0x1800763fb`
- `KERNEL32!WerGetFlags` at `0x1800763fb`
- `KERNEL32!WerSetFlags` at `0x18007640f`
- `KERNEL32!WerSetFlags` at `0x18007642c`
- `KERNEL32!WerSetFlags` at `0x18007640f`
- `KERNEL32!WerSetFlags` at `0x18007642c`
- `ADVAPI32!RegGetValueW` at `0x180076312`
- `ADVAPI32!RegGetValueW` at `0x180076312`

## string_xrefs

- `0x1800762f8`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1800762e3`: `LastUnsafeExtensionReportTime`
- `0x18007637f`: `FAULTREP.DLL`

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
  if ( dword_180090810 < 1 )
  {
    LODWORD(Library) = _InterlockedIncrement(&dword_180090810);
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
0x18007622c  mov     [rsp-8+arg_8], rbx
0x180076231  mov     [rsp-8+arg_10], rsi
0x180076236  push    rbp
0x180076237  push    rdi
0x180076238  push    r12
0x18007623a  push    r14
0x18007623c  push    r15
0x18007623e  lea     rbp, [rsp-20h]
0x180076243  sub     rsp, 120h
0x18007624a  mov     rax, cs:__security_cookie
0x180076251  xor     rax, rsp
0x180076254  mov     [rbp+40h+var_30], rax
0x180076258  mov     r14, r8
0x18007625b  mov     r15, rdx
0x18007625e  mov     r12, rcx
0x180076261  xorps   xmm0, xmm0
0x180076264  xor     edx, edx; Val
0x180076266  lea     rcx, [rsp+140h+var_D0]; void *
0x18007626b  mov     r8d, 98h; Size
0x180076271  mov     rsi, r9
0x180076274  movups  [rsp+140h+var_E0], xmm0
0x180076279  call    memset_0
0x18007627e  mov     ecx, 1
0x180076283  mov     [rsp+140h+pdwFlags], 0
0x18007628b  cmp     cs:dword_180090810, ecx
0x180076291  mov     qword ptr [rsp+140h+var_F0], 0
0x18007629a  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800762a3  jge     loc_18007643A
0x1800762a9  mov     eax, ecx
0x1800762ab  lock xadd cs:dword_180090810, eax
0x1800762b3  add     eax, ecx
0x1800762b5  cmp     eax, ecx
0x1800762b7  jg      loc_18007643A
0x1800762bd  call    IsJITDebuggerPresent
0x1800762c2  test    eax, eax
0x1800762c4  jnz     loc_18007643A
0x1800762ca  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800762cf  call    GetSystemTimeAsFileTime_0
0x1800762d4  lea     rax, [rsp+140h+var_F8]
0x1800762d9  mov     ebx, 8
0x1800762de  mov     [rsp+140h+pcbData], rax; struct _SECURITY_ATTRIBUTES *
0x1800762e3  lea     r8, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x1800762ea  lea     rax, [rsp+140h+var_F0]
0x1800762ef  mov     [rsp+140h+var_F8], ebx
0x1800762f3  mov     [rsp+140h+pvData], rax; unsigned int
0x1800762f8  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Internet Explorer"...
0x1800762ff  mov     r9d, ebx; dwFlags
0x180076302  mov     [rsp+140h+pdwType], 0; pdwType
0x18007630b  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180076312  call    cs:__imp_RegGetValueW
0x180076318  test    eax, eax
0x18007631a  jle     short loc_180076326
0x18007631c  movzx   eax, ax
0x18007631f  or      eax, 80070000h
0x180076324  test    eax, eax
0x180076326  js      short loc_180076365
0x180076328  cmp     [rsp+140h+var_F8], ebx
0x18007632c  jnz     short loc_180076365
0x18007632e  mov     rax, qword ptr [rsp+140h+var_F0]
0x180076333  mov     [rsp+140h+var_F8], eax
0x180076337  shr     rax, 20h
0x18007633b  mov     [rsp+140h+var_F8+4], eax
0x18007633f  mov     rax, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180076344  cmp     rax, qword ptr [rsp+140h+var_F8]
0x180076349  jbe     short loc_18007636E
0x18007634b  sub     rax, qword ptr [rsp+140h+var_F8]
0x180076350  mov     rcx, 2260FF9290000h
0x18007635a  cmp     rax, rcx
0x18007635d  jb      loc_18007643A
0x180076363  jmp     short loc_18007636E
0x180076365  mov     qword ptr [rsp+140h+var_F0], 0
0x18007636e  lea     rax, [rsp+140h+SystemTimeAsFileTime]
0x180076373  mov     [rsp+140h+pdwType], rax; lpData
0x180076378  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x18007637d  xor     edx, edx; hFile
0x18007637f  lea     rcx, aFaultrepDll; "FAULTREP.DLL"
0x180076386  mov     r8d, 800h; dwFlags
0x18007638c  call    LoadLibraryExW_0
0x180076391  mov     rbx, rax
0x180076394  test    rax, rax
0x180076397  jz      loc_18007643A
0x18007639d  lea     rdx, aReportfault; "ReportFault"
0x1800763a4  mov     rcx, rax; hModule
0x1800763a7  call    GetProcAddress_0
0x1800763ac  mov     rdi, rax
0x1800763af  test    rax, rax
0x1800763b2  jz      short loc_180076432
0x1800763b4  lea     rax, [rsp+140h+var_D0]
0x1800763b9  mov     [rsp+140h+var_D0], 0C0000409h
0x1800763c1  mov     qword ptr [rsp+140h+var_E0], rax
0x1800763c6  mov     [rbp+40h+var_C0], 0
0x1800763ce  mov     [rbp+40h+var_B8], 4
0x1800763d5  mov     [rbp+40h+var_B0], 1Ah
0x1800763dd  mov     [rbp+40h+var_A8], r15
0x1800763e1  mov     [rbp+40h+var_A0], r14
0x1800763e5  mov     [rbp+40h+var_98], rsi
0x1800763e9  mov     qword ptr [rsp+140h+var_E0+8], r12
0x1800763ee  call    GetCurrentProcess_0
0x1800763f3  mov     rcx, rax; hProcess
0x1800763f6  lea     rdx, [rsp+140h+pdwFlags]; pdwFlags
0x1800763fb  call    cs:__imp_WerGetFlags
0x180076401  test    eax, eax
0x180076403  js      short loc_180076432
0x180076405  mov     ecx, [rsp+140h+pdwFlags]
0x180076409  and     ecx, 0FFFFFFEFh
0x18007640c  or      ecx, 24h; dwFlags
0x18007640f  call    cs:__imp_WerSetFlags
0x180076415  test    eax, eax
0x180076417  js      short loc_180076432
0x180076419  xor     edx, edx
0x18007641b  lea     rcx, [rsp+140h+var_E0]
0x180076420  mov     rax, rdi
0x180076423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076428  mov     ecx, [rsp+140h+pdwFlags]; dwFlags
0x18007642c  call    cs:__imp_WerSetFlags
0x180076432  mov     rcx, rbx; hLibModule
0x180076435  call    FreeLibrary_0
0x18007643a  mov     rcx, [rbp+40h+var_30]
0x18007643e  xor     rcx, rsp; StackCookie
0x180076441  call    __security_check_cookie
0x180076446  lea     r11, [rsp+140h+var_20]
0x18007644e  mov     rbx, [r11+38h]
0x180076452  mov     rsi, [r11+40h]
0x180076456  mov     rsp, r11
0x180076459  pop     r15
0x18007645b  pop     r14
0x18007645d  pop     r12
0x18007645f  pop     rdi
0x180076460  pop     rbp
0x180076461  retn
```
