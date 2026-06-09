# CW32System::SkipObjectData(void)

- ea: `0x180093320`
- end: `0x180093663`
- name: `?SkipObjectData@CW32System@@SAHXZ`
- size: `835`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002740`

## callees

- `0x180026a80`
- `0x180038730`
- `0x1800426c8`
- `0x18004d518`
- `0x180093320`
- `0x180093c00`

## import_xrefs

- `ADVAPI32!RegEnumKeyExA` at `0x18009348d`
- `ADVAPI32!RegEnumKeyExA` at `0x18009348d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800933f2`
- `ADVAPI32!RegOpenKeyExW` at `0x18009354c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800933f2`
- `ADVAPI32!RegOpenKeyExW` at `0x18009354c`
- `ADVAPI32!RegOpenKeyExA` at `0x180093407`
- `ADVAPI32!RegOpenKeyExA` at `0x18009355f`
- `ADVAPI32!RegOpenKeyExA` at `0x180093407`
- `ADVAPI32!RegOpenKeyExA` at `0x18009355f`
- `ADVAPI32!RegEnumKeyExW` at `0x18009345c`
- `ADVAPI32!RegEnumKeyExW` at `0x18009345c`
- `ADVAPI32!RegQueryValueExA` at `0x1800935c7`
- `ADVAPI32!RegQueryValueExA` at `0x1800935c7`
- `ADVAPI32!RegCloseKey` at `0x1800935ed`
- `ADVAPI32!RegCloseKey` at `0x180093601`
- `ADVAPI32!RegCloseKey` at `0x1800935ed`
- `ADVAPI32!RegCloseKey` at `0x180093601`
- `ADVAPI32!RegQueryValueExW` at `0x1800935b2`
- `ADVAPI32!RegQueryValueExW` at `0x1800935b2`

## pseudocode

```c
__int64 __fastcall CW32System::SkipObjectData(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned __int8 v3; // bl
  unsigned int ModuleFileName; // eax
  int v5; // esi
  unsigned __int16 *v6; // rdi
  int v8; // r15d
  DWORD i; // r14d
  DWORD v10; // ecx
  unsigned int v11; // edx
  LSTATUS v12; // eax
  DWORD v15; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  CHAR SubKey[272]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v23[264]; // [rsp+380h] [rbp+280h] BYREF

  if ( CW32System::_fCheckExe )
    return CW32System::_fSkipObjectData;
  v3 = 1;
  CW32System::_fSkipObjectData = 0;
  CW32System::_fCheckExe = 1;
  ModuleFileName = CW32System::GetModuleFileName(0, v23, a3);
  if ( !ModuleFileName )
    return CW32System::_fSkipObjectData;
  v5 = 1;
  v6 = &v23[ModuleFileName];
  if ( 2LL * ModuleFileName )
  {
    while ( *v6 != 92 )
    {
      --v6;
      ++v5;
      if ( v6 == v23 )
        goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    if ( *v6 != 92 )
      goto LABEL_8;
  }
  --v5;
  ++v6;
LABEL_8:
  if ( !v5 )
    return CW32System::_fSkipObjectData;
  hKey = 0;
  if ( !(CW32System::_dwPlatformId == 2
       ? RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RtfStreamIn\\ObjectBlocking", 0, 9u, &hKey)
       : RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\RtfStreamIn\\ObjectBlocking", 0, 9u, &hKey)) )
  {
    v8 = 0;
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      Name[0] = 0;
      if ( CW32System::_dwPlatformId == 2 )
      {
        if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
          break;
        v10 = cchName;
      }
      else
      {
        v15 = 260;
        SubKey[0] = 0;
        if ( RegEnumKeyExA(hKey, i, SubKey, &v15, 0, 0, 0, 0) )
          break;
        v10 = CW32System::MBTWC(0, v11, SubKey, v15, Name, 260, 0);
        cchName = v10;
      }
      if ( !v10 )
        break;
      if ( v10 >= 0x103 )
      {
        v10 = 259;
        cchName = 259;
      }
      if ( 2 * (unsigned __int64)v10 >= 0x208 )
        _report_rangecheckfailure();
      Name[v10] = 0;
      if ( v10 + 1 == v5 && !(unsigned int)CW32System::lstrcmpi(v6, Name) )
      {
        phkResult = 0;
        CW32System::_fSkipObjectData = 1;
        if ( CW32System::_dwPlatformId == 2 )
          v12 = RegOpenKeyExW(hKey, Name, 0, 1u, &phkResult);
        else
          v12 = RegOpenKeyExA(hKey, SubKey, 0, 1u, &phkResult);
        if ( !v12 )
        {
          Type = 0;
          v15 = 0;
          cbData = 4;
          if ( !(CW32System::_dwPlatformId == 2
               ? RegQueryValueExW(phkResult, L"SkipObjects", 0, &Type, (LPBYTE)&v15, &cbData)
               : RegQueryValueExA(phkResult, "SkipObjects", 0, &Type, (LPBYTE)&v15, &cbData)) )
            CW32System::_fSkipObjectData = v15 & 1;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        v8 = 1;
        break;
      }
    }
    RegCloseKey(hKey);
    if ( v8 )
      return CW32System::_fSkipObjectData;
  }
  if ( v5 != 12 || (unsigned int)CW32System::lstrcmpi(v6, L"OUTLOOK.EXE") )
    return CW32System::_fSkipObjectData;
  CW32System::_fSkipObjectData = 1;
  return v3;
}

```

## disassembly

```asm
0x180093320  push    rbp
0x180093322  push    rbx
0x180093323  push    rsi
0x180093324  push    rdi
0x180093325  push    r12
0x180093327  push    r14
0x180093329  push    r15
0x18009332b  lea     rbp, [rsp-4A0h]
0x180093333  sub     rsp, 5A0h
0x18009333a  mov     rax, cs:__security_cookie
0x180093341  xor     rax, rsp
0x180093344  mov     [rbp+4D0h+var_40], rax
0x18009334b  xor     r12d, r12d
0x18009334e  cmp     cs:?_fCheckExe@CW32System@@2EA, r12b; uchar CW32System::_fCheckExe
0x180093355  jnz     loc_180093638
0x18009335b  lea     ebx, [r12+1]
0x180093360  mov     cs:?_fSkipObjectData@CW32System@@2EA, r12b; uchar CW32System::_fSkipObjectData
0x180093367  lea     rdx, [rbp+4D0h+var_250]; unsigned __int16 *
0x18009336e  mov     cs:?_fCheckExe@CW32System@@2EA, bl; uchar CW32System::_fCheckExe
0x180093374  xor     ecx, ecx; hModule
0x180093376  call    ?GetModuleFileName@CW32System@@SAKPEAUHINSTANCE__@@PEAGK@Z; CW32System::GetModuleFileName(HINSTANCE__ *,ushort *,ulong)
0x18009337b  test    eax, eax
0x18009337d  jz      loc_180093638
0x180093383  mov     eax, eax
0x180093385  lea     rdi, [rbp+4D0h+var_250]
0x18009338c  add     rax, rax
0x18009338f  mov     esi, ebx
0x180093391  lea     rdi, [rdi+rax]
0x180093395  jz      short loc_1800933AF
0x180093397  cmp     word ptr [rdi], 5Ch ; '\'
0x18009339b  jz      short loc_1800933B5
0x18009339d  sub     rdi, 2
0x1800933a1  lea     rax, [rbp+4D0h+var_250]
0x1800933a8  add     esi, ebx
0x1800933aa  cmp     rdi, rax
0x1800933ad  jnz     short loc_180093397
0x1800933af  cmp     word ptr [rdi], 5Ch ; '\'
0x1800933b3  jnz     short loc_1800933BB
0x1800933b5  dec     esi
0x1800933b7  add     rdi, 2
0x1800933bb  test    esi, esi
0x1800933bd  jz      loc_180093638
0x1800933c3  xor     r8d, r8d; ulOptions
0x1800933c6  mov     [rsp+5D0h+hKey], r12
0x1800933cb  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x1800933d2  lea     rax, [rsp+5D0h+hKey]
0x1800933d7  mov     r9d, 9; samDesired
0x1800933dd  mov     [rsp+5D0h+phkResult], rax; phkResult
0x1800933e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800933e9  jnz     short loc_180093400
0x1800933eb  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RtfStreamIn\\Objec"...
0x1800933f2  call    cs:__imp_RegOpenKeyExW
0x1800933f9  nop     dword ptr [rax+rax+00h]
0x1800933fe  jmp     short loc_180093413
0x180093400  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RtfStreamIn\\Objec"...
0x180093407  call    cs:__imp_RegOpenKeyExA
0x18009340e  nop     dword ptr [rax+rax+00h]
0x180093413  test    eax, eax
0x180093415  jnz     loc_180093612
0x18009341b  mov     r15d, r12d
0x18009341e  mov     r14d, r12d
0x180093421  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x180093428  mov     edx, r14d; dwIndex
0x18009342b  mov     rcx, [rsp+5D0h+hKey]; hKey
0x180093430  mov     [rsp+5D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180093435  mov     [rsp+5D0h+lpcchClass], r12; lpcchClass
0x18009343a  mov     [rsp+5D0h+lpClass], r12; lpClass
0x18009343f  mov     [rsp+5D0h+phkResult], r12; lpReserved
0x180093444  mov     [rsp+5D0h+cchName], 104h
0x18009344c  mov     [rbp+4D0h+Name], r12w
0x180093451  jnz     short loc_180093476
0x180093453  lea     r9, [rsp+5D0h+cchName]; lpcchName
0x180093458  lea     r8, [rbp+4D0h+Name]; lpName
0x18009345c  call    cs:__imp_RegEnumKeyExW
0x180093463  nop     dword ptr [rax+rax+00h]
0x180093468  test    eax, eax
0x18009346a  jnz     loc_1800935FC
0x180093470  mov     ecx, [rsp+5D0h+cchName]
0x180093474  jmp     short loc_1800934CE
0x180093476  lea     r9, [rsp+5D0h+var_590]; lpcchName
0x18009347b  mov     [rsp+5D0h+var_590], 104h
0x180093483  lea     r8, [rsp+5D0h+SubKey]; lpName
0x180093488  mov     [rsp+5D0h+SubKey], r12b
0x18009348d  call    cs:__imp_RegEnumKeyExA
0x180093494  nop     dword ptr [rax+rax+00h]
0x180093499  test    eax, eax
0x18009349b  jnz     loc_1800935FC
0x1800934a1  mov     r9d, [rsp+5D0h+var_590]; int
0x1800934a6  lea     rax, [rbp+4D0h+Name]
0x1800934aa  mov     [rsp+5D0h+lpcchClass], r12; int *
0x1800934af  lea     r8, [rsp+5D0h+SubKey]; char *
0x1800934b4  mov     dword ptr [rsp+5D0h+lpClass], 104h; int
0x1800934bc  xor     ecx, ecx; int
0x1800934be  mov     [rsp+5D0h+phkResult], rax; LPWSTR
0x1800934c3  call    ?MBTWC@CW32System@@SAHHKPEBDHPEAGHPEAH@Z; CW32System::MBTWC(int,ulong,char const *,int,ushort *,int,int *)
0x1800934c8  mov     ecx, eax
0x1800934ca  mov     [rsp+5D0h+cchName], eax
0x1800934ce  test    ecx, ecx
0x1800934d0  jz      loc_1800935FC
0x1800934d6  cmp     ecx, 103h
0x1800934dc  jb      short loc_1800934E7
0x1800934de  mov     ecx, 103h
0x1800934e3  mov     [rsp+5D0h+cchName], ecx
0x1800934e7  mov     eax, ecx
0x1800934e9  lea     rdx, [rax+rax]
0x1800934ed  cmp     rdx, 208h
0x1800934f4  jnb     loc_180093632
0x1800934fa  lea     eax, [rcx+1]
0x1800934fd  mov     [rbp+rdx+4D0h+Name], r12w
0x180093503  cmp     eax, esi
0x180093505  jnz     short loc_180093517
0x180093507  lea     rdx, [rbp+4D0h+Name]; unsigned __int16 *
0x18009350b  mov     rcx, rdi; unsigned __int16 *
0x18009350e  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180093513  test    eax, eax
0x180093515  jz      short loc_18009351F
0x180093517  add     r14d, ebx
0x18009351a  jmp     loc_180093421
0x18009351f  mov     rcx, [rsp+5D0h+hKey]; hKey
0x180093524  lea     rax, [rsp+5D0h+var_578]
0x180093529  xor     r8d, r8d; ulOptions
0x18009352c  mov     [rsp+5D0h+var_578], r12
0x180093531  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x180093538  mov     r9d, ebx; samDesired
0x18009353b  mov     cs:?_fSkipObjectData@CW32System@@2EA, bl; uchar CW32System::_fSkipObjectData
0x180093541  mov     [rsp+5D0h+phkResult], rax; phkResult
0x180093546  jnz     short loc_18009355A
0x180093548  lea     rdx, [rbp+4D0h+Name]; lpSubKey
0x18009354c  call    cs:__imp_RegOpenKeyExW
0x180093553  nop     dword ptr [rax+rax+00h]
0x180093558  jmp     short loc_18009356B
0x18009355a  lea     rdx, [rsp+5D0h+SubKey]; lpSubKey
0x18009355f  call    cs:__imp_RegOpenKeyExA
0x180093566  nop     dword ptr [rax+rax+00h]
0x18009356b  test    eax, eax
0x18009356d  jnz     short loc_1800935E3
0x18009356f  mov     rcx, [rsp+5D0h+var_578]; hKey
0x180093574  lea     rax, [rsp+5D0h+cbData]
0x180093579  mov     [rsp+5D0h+lpClass], rax; lpcbData
0x18009357e  lea     r9, [rsp+5D0h+Type]; lpType
0x180093583  xor     r8d, r8d; lpReserved
0x180093586  mov     [rsp+5D0h+Type], r12d
0x18009358b  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x180093592  lea     rax, [rsp+5D0h+var_590]
0x180093597  mov     [rsp+5D0h+phkResult], rax; lpData
0x18009359c  mov     [rsp+5D0h+var_590], r12d
0x1800935a1  mov     [rsp+5D0h+cbData], 4
0x1800935a9  jnz     short loc_1800935C0
0x1800935ab  lea     rdx, aSkipobjects_0; "SkipObjects"
0x1800935b2  call    cs:__imp_RegQueryValueExW
0x1800935b9  nop     dword ptr [rax+rax+00h]
0x1800935be  jmp     short loc_1800935D3
0x1800935c0  lea     rdx, aSkipobjects; "SkipObjects"
0x1800935c7  call    cs:__imp_RegQueryValueExA
0x1800935ce  nop     dword ptr [rax+rax+00h]
0x1800935d3  test    eax, eax
0x1800935d5  jnz     short loc_1800935E3
0x1800935d7  mov     al, byte ptr [rsp+5D0h+var_590]
0x1800935db  and     al, bl
0x1800935dd  mov     cs:?_fSkipObjectData@CW32System@@2EA, al; uchar CW32System::_fSkipObjectData
0x1800935e3  mov     rcx, [rsp+5D0h+var_578]; hKey
0x1800935e8  test    rcx, rcx
0x1800935eb  jz      short loc_1800935F9
0x1800935ed  call    cs:__imp_RegCloseKey
0x1800935f4  nop     dword ptr [rax+rax+00h]
0x1800935f9  mov     r15d, ebx
0x1800935fc  mov     rcx, [rsp+5D0h+hKey]; hKey
0x180093601  call    cs:__imp_RegCloseKey
0x180093608  nop     dword ptr [rax+rax+00h]
0x18009360d  test    r15d, r15d
0x180093610  jnz     short loc_180093638
0x180093612  cmp     esi, 0Ch
0x180093615  jnz     short loc_180093638
0x180093617  lea     rdx, aOutlookExe; "OUTLOOK.EXE"
0x18009361e  mov     rcx, rdi; unsigned __int16 *
0x180093621  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180093626  test    eax, eax
0x180093628  jnz     short loc_180093638
0x18009362a  mov     cs:?_fSkipObjectData@CW32System@@2EA, bl; uchar CW32System::_fSkipObjectData
0x180093630  jmp     short loc_18009363E
0x180093632  call    __report_rangecheckfailure
0x180093638  mov     bl, cs:?_fSkipObjectData@CW32System@@2EA; uchar CW32System::_fSkipObjectData
0x18009363e  movzx   eax, bl
0x180093641  mov     rcx, [rbp+4D0h+var_40]
0x180093648  xor     rcx, rsp; StackCookie
0x18009364b  call    __security_check_cookie
0x180093650  add     rsp, 5A0h
0x180093657  pop     r15
0x180093659  pop     r14
0x18009365b  pop     r12
0x18009365d  pop     rdi
0x18009365e  pop     rsi
0x18009365f  pop     rbx
0x180093660  pop     rbp
0x180093661  retn
```
