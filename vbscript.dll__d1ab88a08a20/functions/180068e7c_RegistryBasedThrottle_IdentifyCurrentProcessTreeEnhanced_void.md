# RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)

- ea: `0x180068e7c`
- end: `0x1800691d6`
- name: `?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ`
- size: `858`
- prototype: `void __fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180055fe4`

## callees

- `0x1800685d4`
- `0x1800687e8`
- `0x180068e7c`
- `0x180079436`
- `0x180079490`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x18006908f`
- `msvcrt!_snprintf_s` at `0x1800690e9`
- `msvcrt!_snprintf_s` at `0x18006908f`
- `msvcrt!_snprintf_s` at `0x1800690e9`
- `msvcrt!_mbsicmp` at `0x180069016`
- `msvcrt!_mbsicmp` at `0x180069016`
- `msvcrt!strcat_s` at `0x180068f90`
- `msvcrt!strcat_s` at `0x180068fa7`
- `msvcrt!strcat_s` at `0x18006913a`
- `msvcrt!strcat_s` at `0x180069153`
- `msvcrt!strcat_s` at `0x180068f90`
- `msvcrt!strcat_s` at `0x180068fa7`
- `msvcrt!strcat_s` at `0x18006913a`
- `msvcrt!strcat_s` at `0x180069153`
- `KERNEL32!Process32Next` at `0x180068f35`
- `KERNEL32!Process32Next` at `0x180068f35`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180068ef5`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180068ef5`
- `KERNEL32!OpenProcess` at `0x180068fd8`
- `KERNEL32!OpenProcess` at `0x180068fd8`
- `KERNEL32!Process32First` at `0x180068f19`
- `KERNEL32!Process32First` at `0x180068f19`
- `KERNEL32!GetCurrentProcessId` at `0x180068eac`
- `KERNEL32!GetCurrentProcessId` at `0x180068eac`
- `KERNEL32!CloseHandle` at `0x180068ffe`
- `KERNEL32!CloseHandle` at `0x180069169`
- `KERNEL32!CloseHandle` at `0x180069187`
- `KERNEL32!CloseHandle` at `0x180068ffe`
- `KERNEL32!CloseHandle` at `0x180069169`
- `KERNEL32!CloseHandle` at `0x180069187`

## pseudocode

```c
void __fastcall RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(RegistryBasedThrottle *this)
{
  DWORD CurrentProcessId; // esi
  _BYTE *v3; // r15
  _BYTE *v4; // r14
  HANDLE Toolhelp32Snapshot; // rax
  void *v6; // r12
  char v7; // di
  BOOL i; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  HANDLE v11; // rax
  void *v12; // rdi
  const char *v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  PROCESSENTRY32 pe; // [rsp+40h] [rbp-C0h] BYREF
  char v17; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v18[255]; // [rsp+171h] [rbp+71h] BYREF
  char Destination; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v20[511]; // [rsp+271h] [rbp+171h] BYREF
  char Buffer[768]; // [rsp+470h] [rbp+370h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  memset_0(&pe.cntUsage, 0, 0x12Cu);
  pe.dwSize = 304;
  v3 = (char *)this + 568;
  v4 = (char *)this + 828;
  *((_BYTE *)this + 568) = 0;
  *((_BYTE *)this + 828) = 0;
  do
  {
    if ( !CurrentProcessId )
      break;
    Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
    v6 = Toolhelp32Snapshot;
    if ( Toolhelp32Snapshot == (HANDLE)-1LL )
      break;
    v7 = 0;
    for ( i = Process32First(Toolhelp32Snapshot, &pe); i; i = Process32Next(v6, &pe) )
    {
      if ( pe.th32ProcessID == CurrentProcessId )
      {
        v9 = -1;
        do
          ++v9;
        while ( pe.szExeFile[v9] );
        v10 = -1;
        do
          ++v10;
        while ( v3[v10] );
        if ( (unsigned __int64)(v9 + v10 + 1) >= 0x104 )
        {
          CloseHandle(v6);
          goto LABEL_38;
        }
        if ( *v3 )
          strcat_s((char *)this + 568, 0x104u, ";");
        strcat_s((char *)this + 568, 0x104u, pe.szExeFile);
        Destination = 0;
        memset_0(v20, 0, sizeof(v20));
        v11 = OpenProcess(0x410u, 0, CurrentProcessId);
        v12 = v11;
        if ( v11 )
        {
          GetProcessCommandLine(v11, &Destination);
          CloseHandle(v12);
        }
        if ( _mbsicmp((const unsigned __int8 *)pe.szExeFile, "svchost.exe")
          || (v17 = 0, memset_0(v18, 0, sizeof(v18)), GetServiceInfoForSvchost(CurrentProcessId, &v17), !v17) )
        {
          v13 = "%s(\"%s\")";
          if ( !Destination )
            v13 = "%s";
          _snprintf_s(Buffer, 0x300u, 0xFFFFFFFFFFFFFFFFuLL, v13, pe.szExeFile, &Destination);
        }
        else if ( Destination )
        {
          _snprintf_s(Buffer, 0x300u, 0xFFFFFFFFFFFFFFFFuLL, "%s(\"%s | %s\")", pe.szExeFile, &v17, &Destination);
        }
        else
        {
          _snprintf_s(Buffer, 0x300u, 0xFFFFFFFFFFFFFFFFuLL, "%s(\"%s\")", pe.szExeFile, &v17);
        }
        v14 = -1;
        do
          ++v14;
        while ( Buffer[v14] );
        v15 = -1;
        do
          ++v15;
        while ( v4[v15] );
        if ( (unsigned __int64)(v14 + v15 + 2) < 0x1000 )
        {
          if ( *v4 )
            strcat_s((char *)this + 828, 0x1000u, ";");
          strcat_s((char *)this + 828, 0x1000u, Buffer);
        }
        CurrentProcessId = pe.th32ParentProcessID;
        v7 = 1;
        break;
      }
    }
    CloseHandle(v6);
  }
  while ( v7 );
LABEL_38:
  *((_QWORD *)this + 873) = v3;
  *((_QWORD *)this + 874) = v4;
  *((_DWORD *)this + 1753) = 1;
  *((_DWORD *)this + 1754) = 1;
}

```

## disassembly

```asm
0x180068e7c  push    rbp
0x180068e7e  push    rbx
0x180068e7f  push    rsi
0x180068e80  push    rdi
0x180068e81  push    r12
0x180068e83  push    r13
0x180068e85  push    r14
0x180068e87  push    r15
0x180068e89  lea     rbp, [rsp-688h]
0x180068e91  sub     rsp, 788h
0x180068e98  mov     rax, cs:__security_cookie
0x180068e9f  xor     rax, rsp
0x180068ea2  mov     [rbp+6C0h+var_50], rax
0x180068ea9  mov     rbx, rcx
0x180068eac  call    cs:__imp_GetCurrentProcessId
0x180068eb3  nop     dword ptr [rax+rax+00h]
0x180068eb8  xor     edx, edx; Val
0x180068eba  lea     rcx, [rsp+7C0h+pe.cntUsage]; void *
0x180068ebf  mov     r8d, 12Ch; Size
0x180068ec5  mov     esi, eax
0x180068ec7  call    memset_0
0x180068ecc  xor     r13d, r13d
0x180068ecf  mov     [rsp+7C0h+pe.dwSize], 130h
0x180068ed7  lea     r15, [rbx+238h]
0x180068ede  lea     r14, [rbx+33Ch]
0x180068ee5  mov     [r15], r13b
0x180068ee8  mov     [r14], r13b
0x180068eeb  jmp     loc_18006917A
0x180068ef0  xor     edx, edx; th32ProcessID
0x180068ef2  lea     ecx, [rdx+2]; dwFlags
0x180068ef5  call    cs:__imp_CreateToolhelp32Snapshot
0x180068efc  nop     dword ptr [rax+rax+00h]
0x180068f01  mov     r12, rax
0x180068f04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180068f08  jz      loc_180069193
0x180068f0e  lea     rdx, [rsp+7C0h+pe]; lppe
0x180068f13  mov     rcx, rax; hSnapshot
0x180068f16  mov     dil, r13b
0x180068f19  call    cs:__imp_Process32First
0x180068f20  nop     dword ptr [rax+rax+00h]
0x180068f25  jmp     short loc_180068F41
0x180068f27  cmp     [rsp+7C0h+pe.th32ProcessID], esi
0x180068f2b  jz      short loc_180068F4A
0x180068f2d  lea     rdx, [rsp+7C0h+pe]; lppe
0x180068f32  mov     rcx, r12; hSnapshot
0x180068f35  call    cs:__imp_Process32Next
0x180068f3c  nop     dword ptr [rax+rax+00h]
0x180068f41  test    eax, eax
0x180068f43  jnz     short loc_180068F27
0x180068f45  jmp     loc_180069166
0x180068f4a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180068f4e  lea     rax, [rsp+7C0h+pe.szExeFile]
0x180068f53  mov     rcx, rdx
0x180068f56  inc     rcx
0x180068f59  cmp     [rax+rcx], r13b
0x180068f5d  jnz     short loc_180068F56
0x180068f5f  mov     rax, rdx
0x180068f62  inc     rax
0x180068f65  cmp     [r15+rax], r13b
0x180068f69  jnz     short loc_180068F62
0x180068f6b  inc     rax
0x180068f6e  mov     edi, 104h
0x180068f73  add     rax, rcx
0x180068f76  cmp     rax, rdi
0x180068f79  jnb     loc_180069184
0x180068f7f  cmp     [r15], r13b
0x180068f82  jz      short loc_180068F9C
0x180068f84  lea     r8, asc_180084074; ";"
0x180068f8b  mov     edx, edi; SizeInBytes
0x180068f8d  mov     rcx, r15; Destination
0x180068f90  call    cs:__imp_strcat_s
0x180068f97  nop     dword ptr [rax+rax+00h]
0x180068f9c  lea     r8, [rsp+7C0h+pe.szExeFile]; Source
0x180068fa1  mov     rdx, rdi; SizeInBytes
0x180068fa4  mov     rcx, r15; Destination
0x180068fa7  call    cs:__imp_strcat_s
0x180068fae  nop     dword ptr [rax+rax+00h]
0x180068fb3  xor     edx, edx; Val
0x180068fb5  mov     [rbp+6C0h+Destination], r13b
0x180068fbc  mov     r8d, 1FFh; Size
0x180068fc2  lea     rcx, [rbp+6C0h+var_54F]; void *
0x180068fc9  call    memset_0
0x180068fce  mov     r8d, esi; dwProcessId
0x180068fd1  xor     edx, edx; bInheritHandle
0x180068fd3  mov     ecx, 410h; dwDesiredAccess
0x180068fd8  call    cs:__imp_OpenProcess
0x180068fdf  nop     dword ptr [rax+rax+00h]
0x180068fe4  mov     rdi, rax
0x180068fe7  test    rax, rax
0x180068fea  jz      short loc_18006900A
0x180068fec  lea     rdx, [rbp+6C0h+Destination]; Destination
0x180068ff3  mov     rcx, rax; hProcess
0x180068ff6  call    GetProcessCommandLine
0x180068ffb  mov     rcx, rdi; hObject
0x180068ffe  call    cs:__imp_CloseHandle
0x180069005  nop     dword ptr [rax+rax+00h]
0x18006900a  lea     rdx, Str2; "svchost.exe"
0x180069011  lea     rcx, [rsp+7C0h+pe.szExeFile]; Str1
0x180069016  call    cs:__imp__mbsicmp
0x18006901d  nop     dword ptr [rax+rax+00h]
0x180069022  test    eax, eax
0x180069024  jnz     loc_1800690AA
0x18006902a  xor     edx, edx; Val
0x18006902c  mov     [rbp+6C0h+var_650], r13b
0x180069030  mov     r8d, 0FFh; Size
0x180069036  lea     rcx, [rbp+6C0h+var_64F]; void *
0x18006903a  call    memset_0
0x18006903f  lea     rdx, [rbp+6C0h+var_650]
0x180069043  mov     ecx, esi
0x180069045  call    GetServiceInfoForSvchost
0x18006904a  cmp     [rbp+6C0h+var_650], r13b
0x18006904e  jz      short loc_1800690AA
0x180069050  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180069054  lea     rcx, [rbp+6C0h+Buffer]; Buffer
0x18006905b  mov     edx, 300h; BufferCount
0x180069060  cmp     [rbp+6C0h+Destination], r13b
0x180069067  jz      short loc_18006909D
0x180069069  lea     rax, [rbp+6C0h+Destination]
0x180069070  mov     [rsp+7C0h+var_790], rax
0x180069075  lea     r9, aSSS; "%s(\"%s | %s\")"
0x18006907c  lea     rax, [rbp+6C0h+var_650]
0x180069080  mov     [rsp+7C0h+var_798], rax
0x180069085  lea     rax, [rsp+7C0h+pe.szExeFile]
0x18006908a  mov     [rsp+7C0h+var_7A0], rax
0x18006908f  call    cs:__imp__snprintf_s
0x180069096  nop     dword ptr [rax+rax+00h]
0x18006909b  jmp     short loc_1800690F5
0x18006909d  lea     rax, [rbp+6C0h+var_650]
0x1800690a1  lea     r9, aSS_2; "%s(\"%s\")"
0x1800690a8  jmp     short loc_1800690DA
0x1800690aa  cmp     [rbp+6C0h+Destination], r13b
0x1800690b1  lea     rax, aS_0; "%s"
0x1800690b8  lea     r9, aSS_2; "%s(\"%s\")"
0x1800690bf  mov     edx, 300h; BufferCount
0x1800690c4  cmovz   r9, rax; Format
0x1800690c8  lea     rcx, [rbp+6C0h+Buffer]; Buffer
0x1800690cf  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800690d3  lea     rax, [rbp+6C0h+Destination]
0x1800690da  mov     [rsp+7C0h+var_798], rax
0x1800690df  lea     rax, [rsp+7C0h+pe.szExeFile]
0x1800690e4  mov     [rsp+7C0h+var_7A0], rax
0x1800690e9  call    cs:__imp__snprintf_s
0x1800690f0  nop     dword ptr [rax+rax+00h]
0x1800690f5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800690f9  lea     rax, [rbp+6C0h+Buffer]
0x180069100  mov     rcx, rdx
0x180069103  inc     rcx
0x180069106  cmp     [rax+rcx], r13b
0x18006910a  jnz     short loc_180069103
0x18006910c  mov     rax, rdx
0x18006910f  inc     rax
0x180069112  cmp     [r14+rax], r13b
0x180069116  jnz     short loc_18006910F
0x180069118  add     rax, 2
0x18006911c  mov     edi, 1000h
0x180069121  add     rax, rcx
0x180069124  cmp     rax, rdi
0x180069127  jnb     short loc_18006915F
0x180069129  cmp     [r14], r13b
0x18006912c  jz      short loc_180069146
0x18006912e  lea     r8, asc_180084074; ";"
0x180069135  mov     edx, edi; SizeInBytes
0x180069137  mov     rcx, r14; Destination
0x18006913a  call    cs:__imp_strcat_s
0x180069141  nop     dword ptr [rax+rax+00h]
0x180069146  lea     r8, [rbp+6C0h+Buffer]; Source
0x18006914d  mov     rdx, rdi; SizeInBytes
0x180069150  mov     rcx, r14; Destination
0x180069153  call    cs:__imp_strcat_s
0x18006915a  nop     dword ptr [rax+rax+00h]
0x18006915f  mov     esi, [rsp+7C0h+pe.th32ParentProcessID]
0x180069163  mov     dil, 1
0x180069166  mov     rcx, r12; hObject
0x180069169  call    cs:__imp_CloseHandle
0x180069170  nop     dword ptr [rax+rax+00h]
0x180069175  test    dil, dil
0x180069178  jz      short loc_180069193
0x18006917a  test    esi, esi
0x18006917c  jnz     loc_180068EF0
0x180069182  jmp     short loc_180069193
0x180069184  mov     rcx, r12; hObject
0x180069187  call    cs:__imp_CloseHandle
0x18006918e  nop     dword ptr [rax+rax+00h]
0x180069193  mov     [rbx+1B48h], r15
0x18006919a  mov     esi, 1
0x18006919f  mov     [rbx+1B50h], r14
0x1800691a6  mov     [rbx+1B64h], esi
0x1800691ac  mov     [rbx+1B68h], esi
0x1800691b2  mov     rcx, [rbp+6C0h+var_50]
0x1800691b9  xor     rcx, rsp; StackCookie
0x1800691bc  call    __security_check_cookie
0x1800691c1  add     rsp, 788h
0x1800691c8  pop     r15
0x1800691ca  pop     r14
0x1800691cc  pop     r13
0x1800691ce  pop     r12
0x1800691d0  pop     rdi
0x1800691d1  pop     rsi
0x1800691d2  pop     rbx
0x1800691d3  pop     rbp
0x1800691d4  retn
```
