# RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)

- ea: `0x180066ec4`
- end: `0x1800671bf`
- name: `?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ`
- size: `763`
- prototype: `void __fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800546d4`

## callees

- `0x1800666e4`
- `0x1800668d4`
- `0x180066ec4`
- `0x180076746`
- `0x1800767a0`

## import_xrefs

- `msvcrt!_snprintf_s` at `0x18006709d`
- `msvcrt!_snprintf_s` at `0x1800670f1`
- `msvcrt!_snprintf_s` at `0x18006709d`
- `msvcrt!_snprintf_s` at `0x1800670f1`
- `msvcrt!_mbsicmp` at `0x18006702e`
- `msvcrt!_mbsicmp` at `0x18006702e`
- `msvcrt!strcat_s` at `0x180066fc0`
- `msvcrt!strcat_s` at `0x180066fd1`
- `msvcrt!strcat_s` at `0x18006713c`
- `msvcrt!strcat_s` at `0x18006714f`
- `msvcrt!strcat_s` at `0x180066fc0`
- `msvcrt!strcat_s` at `0x180066fd1`
- `msvcrt!strcat_s` at `0x18006713c`
- `msvcrt!strcat_s` at `0x18006714f`
- `KERNEL32!Process32Next` at `0x180066f6b`
- `KERNEL32!Process32Next` at `0x180066f6b`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180066f37`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x180066f37`
- `KERNEL32!OpenProcess` at `0x180066ffc`
- `KERNEL32!OpenProcess` at `0x180066ffc`
- `KERNEL32!Process32First` at `0x180066f55`
- `KERNEL32!Process32First` at `0x180066f55`
- `KERNEL32!GetCurrentProcessId` at `0x180066ef4`
- `KERNEL32!GetCurrentProcessId` at `0x180066ef4`
- `KERNEL32!CloseHandle` at `0x18006701c`
- `KERNEL32!CloseHandle` at `0x18006715f`
- `KERNEL32!CloseHandle` at `0x180067177`
- `KERNEL32!CloseHandle` at `0x18006701c`
- `KERNEL32!CloseHandle` at `0x18006715f`
- `KERNEL32!CloseHandle` at `0x180067177`

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
0x180066ec4  push    rbp
0x180066ec6  push    rbx
0x180066ec7  push    rsi
0x180066ec8  push    rdi
0x180066ec9  push    r12
0x180066ecb  push    r13
0x180066ecd  push    r14
0x180066ecf  push    r15
0x180066ed1  lea     rbp, [rsp-688h]
0x180066ed9  sub     rsp, 788h
0x180066ee0  mov     rax, cs:__security_cookie
0x180066ee7  xor     rax, rsp
0x180066eea  mov     [rbp+6C0h+var_50], rax
0x180066ef1  mov     rbx, rcx
0x180066ef4  call    cs:__imp_GetCurrentProcessId
0x180066efa  xor     edx, edx; Val
0x180066efc  lea     rcx, [rsp+7C0h+pe.cntUsage]; void *
0x180066f01  mov     r8d, 12Ch; Size
0x180066f07  mov     esi, eax
0x180066f09  call    memset_0
0x180066f0e  xor     r13d, r13d
0x180066f11  mov     [rsp+7C0h+pe.dwSize], 130h
0x180066f19  lea     r15, [rbx+238h]
0x180066f20  lea     r14, [rbx+33Ch]
0x180066f27  mov     [r15], r13b
0x180066f2a  mov     [r14], r13b
0x180066f2d  jmp     loc_18006716A
0x180066f32  xor     edx, edx; th32ProcessID
0x180066f34  lea     ecx, [rdx+2]; dwFlags
0x180066f37  call    cs:__imp_CreateToolhelp32Snapshot
0x180066f3d  mov     r12, rax
0x180066f40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180066f44  jz      loc_18006717D
0x180066f4a  lea     rdx, [rsp+7C0h+pe]; lppe
0x180066f4f  mov     rcx, rax; hSnapshot
0x180066f52  mov     dil, r13b
0x180066f55  call    cs:__imp_Process32First
0x180066f5b  jmp     short loc_180066F71
0x180066f5d  cmp     [rsp+7C0h+pe.th32ProcessID], esi
0x180066f61  jz      short loc_180066F7A
0x180066f63  lea     rdx, [rsp+7C0h+pe]; lppe
0x180066f68  mov     rcx, r12; hSnapshot
0x180066f6b  call    cs:__imp_Process32Next
0x180066f71  test    eax, eax
0x180066f73  jnz     short loc_180066F5D
0x180066f75  jmp     loc_18006715C
0x180066f7a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180066f7e  lea     rax, [rsp+7C0h+pe.szExeFile]
0x180066f83  mov     rcx, rdx
0x180066f86  inc     rcx
0x180066f89  cmp     [rax+rcx], r13b
0x180066f8d  jnz     short loc_180066F86
0x180066f8f  mov     rax, rdx
0x180066f92  inc     rax
0x180066f95  cmp     [r15+rax], r13b
0x180066f99  jnz     short loc_180066F92
0x180066f9b  inc     rax
0x180066f9e  mov     edi, 104h
0x180066fa3  add     rax, rcx
0x180066fa6  cmp     rax, rdi
0x180066fa9  jnb     loc_180067174
0x180066faf  cmp     [r15], r13b
0x180066fb2  jz      short loc_180066FC6
0x180066fb4  lea     r8, asc_180080FFC; ";"
0x180066fbb  mov     edx, edi; SizeInBytes
0x180066fbd  mov     rcx, r15; Destination
0x180066fc0  call    cs:__imp_strcat_s
0x180066fc6  lea     r8, [rsp+7C0h+pe.szExeFile]; Source
0x180066fcb  mov     rdx, rdi; SizeInBytes
0x180066fce  mov     rcx, r15; Destination
0x180066fd1  call    cs:__imp_strcat_s
0x180066fd7  xor     edx, edx; Val
0x180066fd9  mov     [rbp+6C0h+Destination], r13b
0x180066fe0  mov     r8d, 1FFh; Size
0x180066fe6  lea     rcx, [rbp+6C0h+var_54F]; void *
0x180066fed  call    memset_0
0x180066ff2  mov     r8d, esi; dwProcessId
0x180066ff5  xor     edx, edx; bInheritHandle
0x180066ff7  mov     ecx, 410h; dwDesiredAccess
0x180066ffc  call    cs:__imp_OpenProcess
0x180067002  mov     rdi, rax
0x180067005  test    rax, rax
0x180067008  jz      short loc_180067022
0x18006700a  lea     rdx, [rbp+6C0h+Destination]; Destination
0x180067011  mov     rcx, rax; hProcess
0x180067014  call    GetProcessCommandLine
0x180067019  mov     rcx, rdi; hObject
0x18006701c  call    cs:__imp_CloseHandle
0x180067022  lea     rdx, Str2; "svchost.exe"
0x180067029  lea     rcx, [rsp+7C0h+pe.szExeFile]; Str1
0x18006702e  call    cs:__imp__mbsicmp
0x180067034  test    eax, eax
0x180067036  jnz     short loc_1800670B2
0x180067038  xor     edx, edx; Val
0x18006703a  mov     [rbp+6C0h+var_650], r13b
0x18006703e  mov     r8d, 0FFh; Size
0x180067044  lea     rcx, [rbp+6C0h+var_64F]; void *
0x180067048  call    memset_0
0x18006704d  lea     rdx, [rbp+6C0h+var_650]
0x180067051  mov     ecx, esi
0x180067053  call    GetServiceInfoForSvchost
0x180067058  cmp     [rbp+6C0h+var_650], r13b
0x18006705c  jz      short loc_1800670B2
0x18006705e  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180067062  lea     rcx, [rbp+6C0h+Buffer]; Buffer
0x180067069  mov     edx, 300h; BufferCount
0x18006706e  cmp     [rbp+6C0h+Destination], r13b
0x180067075  jz      short loc_1800670A5
0x180067077  lea     rax, [rbp+6C0h+Destination]
0x18006707e  mov     [rsp+7C0h+var_790], rax
0x180067083  lea     r9, aSSS; "%s(\"%s | %s\")"
0x18006708a  lea     rax, [rbp+6C0h+var_650]
0x18006708e  mov     [rsp+7C0h+var_798], rax
0x180067093  lea     rax, [rsp+7C0h+pe.szExeFile]
0x180067098  mov     [rsp+7C0h+var_7A0], rax
0x18006709d  call    cs:__imp__snprintf_s
0x1800670a3  jmp     short loc_1800670F7
0x1800670a5  lea     rax, [rbp+6C0h+var_650]
0x1800670a9  lea     r9, aSS_2; "%s(\"%s\")"
0x1800670b0  jmp     short loc_1800670E2
0x1800670b2  cmp     [rbp+6C0h+Destination], r13b
0x1800670b9  lea     rax, aS_0; "%s"
0x1800670c0  lea     r9, aSS_2; "%s(\"%s\")"
0x1800670c7  mov     edx, 300h; BufferCount
0x1800670cc  cmovz   r9, rax; Format
0x1800670d0  lea     rcx, [rbp+6C0h+Buffer]; Buffer
0x1800670d7  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800670db  lea     rax, [rbp+6C0h+Destination]
0x1800670e2  mov     [rsp+7C0h+var_798], rax
0x1800670e7  lea     rax, [rsp+7C0h+pe.szExeFile]
0x1800670ec  mov     [rsp+7C0h+var_7A0], rax
0x1800670f1  call    cs:__imp__snprintf_s
0x1800670f7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800670fb  lea     rax, [rbp+6C0h+Buffer]
0x180067102  mov     rcx, rdx
0x180067105  inc     rcx
0x180067108  cmp     [rax+rcx], r13b
0x18006710c  jnz     short loc_180067105
0x18006710e  mov     rax, rdx
0x180067111  inc     rax
0x180067114  cmp     [r14+rax], r13b
0x180067118  jnz     short loc_180067111
0x18006711a  add     rax, 2
0x18006711e  mov     edi, 1000h
0x180067123  add     rax, rcx
0x180067126  cmp     rax, rdi
0x180067129  jnb     short loc_180067155
0x18006712b  cmp     [r14], r13b
0x18006712e  jz      short loc_180067142
0x180067130  lea     r8, asc_180080FFC; ";"
0x180067137  mov     edx, edi; SizeInBytes
0x180067139  mov     rcx, r14; Destination
0x18006713c  call    cs:__imp_strcat_s
0x180067142  lea     r8, [rbp+6C0h+Buffer]; Source
0x180067149  mov     rdx, rdi; SizeInBytes
0x18006714c  mov     rcx, r14; Destination
0x18006714f  call    cs:__imp_strcat_s
0x180067155  mov     esi, [rsp+7C0h+pe.th32ParentProcessID]
0x180067159  mov     dil, 1
0x18006715c  mov     rcx, r12; hObject
0x18006715f  call    cs:__imp_CloseHandle
0x180067165  test    dil, dil
0x180067168  jz      short loc_18006717D
0x18006716a  test    esi, esi
0x18006716c  jnz     loc_180066F32
0x180067172  jmp     short loc_18006717D
0x180067174  mov     rcx, r12; hObject
0x180067177  call    cs:__imp_CloseHandle
0x18006717d  mov     [rbx+1B48h], r15
0x180067184  mov     esi, 1
0x180067189  mov     [rbx+1B50h], r14
0x180067190  mov     [rbx+1B64h], esi
0x180067196  mov     [rbx+1B68h], esi
0x18006719c  mov     rcx, [rbp+6C0h+var_50]
0x1800671a3  xor     rcx, rsp; StackCookie
0x1800671a6  call    __security_check_cookie
0x1800671ab  add     rsp, 788h
0x1800671b2  pop     r15
0x1800671b4  pop     r14
0x1800671b6  pop     r13
0x1800671b8  pop     r12
0x1800671ba  pop     rdi
0x1800671bb  pop     rsi
0x1800671bc  pop     rbx
0x1800671bd  pop     rbp
0x1800671be  retn
```
