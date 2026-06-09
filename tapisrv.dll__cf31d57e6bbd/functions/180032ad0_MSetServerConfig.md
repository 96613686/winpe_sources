# MSetServerConfig

- ea: `0x180032ad0`
- end: `0x180032f00`
- name: `MSetServerConfig`
- size: `1072`
- prototype: `void __fastcall(unsigned __int64, unsigned int *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180028100`

## callees

- `0x180007244`
- `0x1800072b0`
- `0x1800072e4`
- `0x180007394`
- `0x18001f494`
- `0x180031eec`
- `0x180031fd4`
- `0x180032ad0`
- `0x180034030`
- `0x180034154`
- `0x18003a9ec`
- `0x18003ca9c`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!WritePrivateProfileSectionW` at `0x180032e83`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180032e83`
- `KERNEL32!WritePrivateProfileStringW` at `0x180032eaf`
- `KERNEL32!WritePrivateProfileStringW` at `0x180032eaf`
- `KERNEL32!CloseHandle` at `0x180032d02`
- `KERNEL32!CloseHandle` at `0x180032d02`
- `KERNEL32!GetLastError` at `0x180032cd5`
- `KERNEL32!GetLastError` at `0x180032cd5`
- `KERNEL32!LeaveCriticalSection` at `0x180032b8a`
- `KERNEL32!LeaveCriticalSection` at `0x180032bcd`
- `KERNEL32!LeaveCriticalSection` at `0x180032c15`
- `KERNEL32!LeaveCriticalSection` at `0x180032c33`
- `KERNEL32!LeaveCriticalSection` at `0x180032dde`
- `KERNEL32!LeaveCriticalSection` at `0x180032b8a`
- `KERNEL32!LeaveCriticalSection` at `0x180032bcd`
- `KERNEL32!LeaveCriticalSection` at `0x180032c15`
- `KERNEL32!LeaveCriticalSection` at `0x180032c33`
- `KERNEL32!LeaveCriticalSection` at `0x180032dde`
- `KERNEL32!EnterCriticalSection` at `0x180032b66`
- `KERNEL32!EnterCriticalSection` at `0x180032c23`
- `KERNEL32!EnterCriticalSection` at `0x180032dbc`
- `KERNEL32!EnterCriticalSection` at `0x180032b66`
- `KERNEL32!EnterCriticalSection` at `0x180032c23`
- `KERNEL32!EnterCriticalSection` at `0x180032dbc`
- `ADVAPI32!LogonUserW` at `0x180032ccb`
- `ADVAPI32!LogonUserW` at `0x180032ccb`

## string_xrefs

- `0x180032b42`: `MSetServerConfig: sharing enabled: %d`
- `0x180032cdb`: `MSetServerConfig: LogonUser failed, err=%ld`
- `0x180032d3f`: `MSetServerConfig: Bad string param for setting account`
- `0x180032d6a`: `MSetServerConfig: enabling tapi server`
- `0x180032d27`: `MSetServerConfig: WriteServiceConfig failed, err=%ld`
- `0x180032da4`: `MSetServerConfig: disabling tapi server`
- `0x180032d89`: `MSetServerConfig: CreateTapiSCP failed, err=%ld`
- `0x180032e17`: `MSetServerConfig: WriteRegistryKeys failed, err=%ld`
- `0x180032ded`: `MSetServerConfig: RemoveTapiSCP failed, err=%ld`
- `0x180032ed5`: `MSetServerConfig: Bad administrators size/offset/string list`
- `0x180032dc9`: `CN=Telephony Service`

## pseudocode

```c
void __fastcall MSetServerConfig(unsigned __int64 a1, unsigned int *a2, unsigned int a3, __int64 a4)
{
  __int64 v8; // rsi
  __int64 v9; // rsi
  int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // rcx
  const WCHAR *v17; // rbx
  const WCHAR *v18; // r14
  DWORD LastError; // eax
  unsigned int v20; // eax
  unsigned int v21; // ebx
  unsigned int TapiSCP; // eax
  unsigned int v23; // ebx
  int v24; // eax
  __int64 v25; // rbx
  __int64 v26; // r8
  const WCHAR *v27; // rbx
  __int64 v28; // rax
  HANDLE hObject; // [rsp+80h] [rbp+8h] BYREF

  if ( !a1 || (*(_BYTE *)(a1 + 216) & 1) == 0 )
  {
    *a2 = -19;
    return;
  }
  v8 = a2[3];
  *a2 = 0;
  if ( (unsigned int)IsBadStructParam(a3, a4, (unsigned int)v8) || (v9 = a4 + v8, *(_DWORD *)v9 < 0x30u) )
  {
    *a2 = -1879048164;
    return;
  }
  if ( !(unsigned int)IsNTServer() )
    goto LABEL_26;
  v10 = IsSharingEnabled();
  TRACELogPrint(524290, "MSetServerConfig: sharing enabled: %d", v10);
  if ( (*(_BYTE *)(v9 + 12) & 0x20) != 0 )
  {
    EnterCriticalSection(&gMgmtCritSec);
    if ( gbLockMMCWrite )
      *a2 = -20;
    else
      gbLockMMCWrite = 1;
    LeaveCriticalSection(&gMgmtCritSec);
    if ( *a2 )
      return;
    if ( WaitForExclusiveClientAccess(a1) )
    {
      v13 = (unsigned int)gdwPointerToLockTableIndexBits;
      *(_DWORD *)(a1 + 216) |= 4u;
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + (v13 & (a1 >> 4)));
    }
  }
  if ( (*(_BYTE *)(v9 + 12) & 0x40) != 0 )
  {
    if ( WaitForExclusiveClientAccess(a1) )
    {
      v14 = *(_DWORD *)(a1 + 216);
      *(_DWORD *)(a1 + 216) = v14 & 0xFFFFFFFB;
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
      if ( (v14 & 4) != 0 )
      {
        EnterCriticalSection(&gMgmtCritSec);
        gbLockMMCWrite = 0;
        LeaveCriticalSection(&gMgmtCritSec);
      }
    }
  }
  if ( (*(_BYTE *)(v9 + 12) & 4) != 0 )
  {
    v15 = *(unsigned int *)(v9 + 28);
    v16 = a3 - a2[3];
    hObject = 0;
    if ( (unsigned int)IsBadStringParam(v16, v9, v15)
      || (unsigned int)IsBadStringParam(a3 - a2[3], v9, *(unsigned int *)(v9 + 20))
      || (unsigned int)IsBadStringParam(a3 - a2[3], v9, *(unsigned int *)(v9 + 36)) )
    {
      TRACELogPrint(65538, "MSetServerConfig: Bad string param for setting account");
      goto LABEL_26;
    }
    v17 = (const WCHAR *)(v9 + *(unsigned int *)(v9 + 28));
    v18 = (const WCHAR *)(v9 + *(unsigned int *)(v9 + 20));
    if ( !LogonUserW(v17, v18, (LPCWSTR)(v9 + *(unsigned int *)(v9 + 36)), 3u, 0, &hObject) )
    {
      LastError = GetLastError();
      TRACELogPrint(65538, "MSetServerConfig: LogonUser failed, err=%ld", LastError);
      *a2 = 1326;
      return;
    }
    CloseHandle(hObject);
    v20 = WriteServiceConfig(v18, v17);
    v21 = v20;
    if ( v20 )
    {
      TRACELogPrint(65538, "MSetServerConfig: WriteServiceConfig failed, err=%ld", v20);
      *a2 = v21;
      return;
    }
  }
  if ( (*(_BYTE *)(v9 + 12) & 2) != 0 )
  {
    if ( !v10 )
    {
      TRACELogPrint(524290, "MSetServerConfig: enabling tapi server");
      TapiSCP = CreateTapiSCP();
      *a2 = TapiSCP;
      if ( TapiSCP )
      {
        TRACELogPrint(65538, "MSetServerConfig: CreateTapiSCP failed, err=%ld", TapiSCP);
        return;
      }
    }
  }
  else if ( v10 )
  {
    TRACELogPrint(524290, "MSetServerConfig: disabling tapi server");
    EnterCriticalSection(&gSCPCritSec);
    v23 = RemoveSCP(L"CN=Telephony Service", L"TAPISRVSCPGUID");
    LeaveCriticalSection(&gSCPCritSec);
    *a2 = v23;
    if ( v23 )
    {
      TRACELogPrint(65538, "MSetServerConfig: RemoveTapiSCP failed, err=%ld", v23);
      return;
    }
    dword_180051900 &= ~2u;
  }
  v24 = WriteRegistryKeys(v12, v11, (*(_DWORD *)(v9 + 12) & 2) == 0);
  if ( v24 )
  {
    TRACELogPrint(65538, "MSetServerConfig: WriteRegistryKeys failed, err=%ld", v24);
    goto LABEL_26;
  }
  if ( (*(_BYTE *)(v9 + 12) & 8) == 0 )
    return;
  v25 = *(unsigned int *)(v9 + 44);
  if ( (unsigned int)IsBadSizeOffset(a3 - a2[3], 48, *(_DWORD *)(v9 + 40), *(_DWORD *)(v9 + 44), 2)
    || (v27 = (const WCHAR *)(v9 + v25), (unsigned int)IsBadStringListSize(v27, *(unsigned int *)(v9 + 40), v26)) )
  {
    TRACELogPrint(65538, "MSetServerConfig: Bad administrators size/offset/string list");
    goto LABEL_26;
  }
  if ( !WritePrivateProfileSectionW(gszTapiAdministrators, &String, gszFileName) )
  {
LABEL_26:
    *a2 = -2147483576;
    return;
  }
  while ( *v27 )
  {
    if ( !WritePrivateProfileStringW(gszTapiAdministrators, v27, L"1", gszFileName) )
      goto LABEL_26;
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    v27 += v28 + 1;
  }
}

```

## disassembly

```asm
0x180032ad0  push    rbx
0x180032ad2  push    rbp
0x180032ad3  push    rsi
0x180032ad4  push    rdi
0x180032ad5  push    r12
0x180032ad7  push    r13
0x180032ad9  push    r14
0x180032adb  push    r15
0x180032add  sub     rsp, 38h
0x180032ae1  xor     r13d, r13d
0x180032ae4  mov     rbx, r9
0x180032ae7  mov     ebp, r8d
0x180032aea  mov     rdi, rdx
0x180032aed  mov     r14, rcx
0x180032af0  test    rcx, rcx
0x180032af3  jz      loc_180032EE9
0x180032af9  test    byte ptr [rcx+0D8h], 1
0x180032b00  jz      loc_180032EE9
0x180032b06  mov     esi, [rdx+0Ch]
0x180032b09  mov     ecx, ebp
0x180032b0b  mov     [rdx], r13d
0x180032b0e  mov     r8d, esi
0x180032b11  mov     rdx, rbx
0x180032b14  call    IsBadStructParam
0x180032b19  test    eax, eax
0x180032b1b  jnz     loc_180032EE1
0x180032b21  add     rsi, rbx
0x180032b24  cmp     dword ptr [rsi], 30h ; '0'
0x180032b27  jb      loc_180032EE1
0x180032b2d  call    IsNTServer
0x180032b32  test    eax, eax
0x180032b34  jz      loc_180032D50
0x180032b3a  call    IsSharingEnabled
0x180032b3f  mov     r8d, eax
0x180032b42  lea     rdx, aMsetserverconf; "MSetServerConfig: sharing enabled: %d"
0x180032b49  mov     ecx, 80002h
0x180032b4e  mov     r15d, eax
0x180032b51  call    TRACELogPrint
0x180032b56  test    byte ptr [rsi+0Ch], 20h
0x180032b5a  lea     r12, gMgmtCritSec
0x180032b61  jz      short loc_180032BD3
0x180032b63  mov     rcx, r12; lpCriticalSection
0x180032b66  call    cs:__imp_EnterCriticalSection
0x180032b6c  cmp     cs:gbLockMMCWrite, r13d
0x180032b73  jz      short loc_180032B7D
0x180032b75  mov     dword ptr [rdi], 0FFFFFFECh
0x180032b7b  jmp     short loc_180032B87
0x180032b7d  mov     cs:gbLockMMCWrite, 1
0x180032b87  mov     rcx, r12; lpCriticalSection
0x180032b8a  call    cs:__imp_LeaveCriticalSection
0x180032b90  cmp     [rdi], r13d
0x180032b93  jnz     loc_180032EEF
0x180032b99  mov     rcx, r14
0x180032b9c  call    WaitForExclusiveClientAccess
0x180032ba1  test    rax, rax
0x180032ba4  jz      short loc_180032BD3
0x180032ba6  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180032bac  mov     rcx, r14
0x180032baf  or      dword ptr [r14+0D8h], 4
0x180032bb7  shr     rcx, 4
0x180032bbb  and     rcx, rax
0x180032bbe  mov     rax, cs:gLockTable
0x180032bc5  lea     rcx, [rcx+rcx*4]
0x180032bc9  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180032bcd  call    cs:__imp_LeaveCriticalSection
0x180032bd3  test    byte ptr [rsi+0Ch], 40h
0x180032bd7  jz      short loc_180032C39
0x180032bd9  mov     rcx, r14
0x180032bdc  call    WaitForExclusiveClientAccess
0x180032be1  test    rax, rax
0x180032be4  jz      short loc_180032C39
0x180032be6  mov     ebx, [r14+0D8h]
0x180032bed  mov     eax, ebx
0x180032bef  and     eax, 0FFFFFFFBh
0x180032bf2  mov     [r14+0D8h], eax
0x180032bf9  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180032bff  shr     r14, 4
0x180032c03  and     r14, rax
0x180032c06  mov     rax, cs:gLockTable
0x180032c0d  lea     rdx, [r14+r14*4]
0x180032c11  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x180032c15  call    cs:__imp_LeaveCriticalSection
0x180032c1b  test    bl, 4
0x180032c1e  jz      short loc_180032C39
0x180032c20  mov     rcx, r12; lpCriticalSection
0x180032c23  call    cs:__imp_EnterCriticalSection
0x180032c29  mov     rcx, r12; lpCriticalSection
0x180032c2c  mov     cs:gbLockMMCWrite, r13d
0x180032c33  call    cs:__imp_LeaveCriticalSection
0x180032c39  test    byte ptr [rsi+0Ch], 4
0x180032c3d  jz      loc_180032D5B
0x180032c43  mov     r8d, [rsi+1Ch]
0x180032c47  mov     ecx, ebp
0x180032c49  sub     ecx, [rdi+0Ch]
0x180032c4c  mov     rdx, rsi
0x180032c4f  mov     [rsp+78h+hObject], r13
0x180032c57  call    IsBadStringParam
0x180032c5c  test    eax, eax
0x180032c5e  jnz     loc_180032D3F
0x180032c64  mov     r8d, [rsi+14h]
0x180032c68  mov     ecx, ebp
0x180032c6a  sub     ecx, [rdi+0Ch]
0x180032c6d  mov     rdx, rsi
0x180032c70  call    IsBadStringParam
0x180032c75  test    eax, eax
0x180032c77  jnz     loc_180032D3F
0x180032c7d  mov     r8d, [rsi+24h]
0x180032c81  mov     ecx, ebp
0x180032c83  sub     ecx, [rdi+0Ch]
0x180032c86  mov     rdx, rsi
0x180032c89  call    IsBadStringParam
0x180032c8e  test    eax, eax
0x180032c90  jnz     loc_180032D3F
0x180032c96  mov     ebx, [rsi+1Ch]
0x180032c99  lea     rax, [rsp+78h+hObject]
0x180032ca1  mov     r14d, [rsi+14h]
0x180032ca5  add     rbx, rsi
0x180032ca8  mov     r12d, [rsi+24h]
0x180032cac  add     r14, rsi
0x180032caf  mov     [rsp+78h+phToken], rax; phToken
0x180032cb4  add     r12, rsi
0x180032cb7  mov     r8, r12; lpszPassword
0x180032cba  mov     [rsp+78h+dwLogonProvider], r13d; dwLogonProvider
0x180032cbf  mov     rdx, r14; lpszDomain
0x180032cc2  mov     rcx, rbx; lpszUsername
0x180032cc5  mov     r9d, 3; dwLogonType
0x180032ccb  call    cs:__imp_LogonUserW
0x180032cd1  test    eax, eax
0x180032cd3  jnz     short loc_180032CFA
0x180032cd5  call    cs:__imp_GetLastError
0x180032cdb  lea     rdx, aMsetserverconf_4; "MSetServerConfig: LogonUser failed, err"...
0x180032ce2  mov     ecx, 10002h
0x180032ce7  mov     r8d, eax
0x180032cea  call    TRACELogPrint
0x180032cef  mov     dword ptr [rdi], 52Eh
0x180032cf5  jmp     loc_180032EEF
0x180032cfa  mov     rcx, [rsp+78h+hObject]; hObject
0x180032d02  call    cs:__imp_CloseHandle
0x180032d08  mov     r9d, [rsi+0Ch]
0x180032d0c  mov     r8, r12
0x180032d0f  and     r9d, 2
0x180032d13  mov     rdx, rbx; STRSAFE_LPCWSTR
0x180032d16  mov     rcx, r14; pszSrc
0x180032d19  call    WriteServiceConfig
0x180032d1e  mov     ebx, eax
0x180032d20  test    eax, eax
0x180032d22  jz      short loc_180032D5B
0x180032d24  mov     r8d, eax
0x180032d27  lea     rdx, aMsetserverconf_1; "MSetServerConfig: WriteServiceConfig fa"...
0x180032d2e  mov     ecx, 10002h
0x180032d33  call    TRACELogPrint
0x180032d38  mov     [rdi], ebx
0x180032d3a  jmp     loc_180032EEF
0x180032d3f  lea     rdx, aMsetserverconf_8; "MSetServerConfig: Bad string param for "...
0x180032d46  mov     ecx, 10002h
0x180032d4b  call    TRACELogPrint
0x180032d50  mov     dword ptr [rdi], 80000048h
0x180032d56  jmp     loc_180032EEF
0x180032d5b  test    byte ptr [rsi+0Ch], 2
0x180032d5f  jz      short loc_180032D9F
0x180032d61  test    r15d, r15d
0x180032d64  jnz     loc_180032DFD
0x180032d6a  lea     rdx, aMsetserverconf_0; "MSetServerConfig: enabling tapi server"
0x180032d71  mov     ecx, 80002h
0x180032d76  call    TRACELogPrint
0x180032d7b  call    CreateTapiSCP
0x180032d80  mov     [rdi], eax
0x180032d82  test    eax, eax
0x180032d84  jz      short loc_180032DFD
0x180032d86  mov     r8d, eax
0x180032d89  lea     rdx, aMsetserverconf_7; "MSetServerConfig: CreateTapiSCP failed,"...
0x180032d90  mov     ecx, 10002h
0x180032d95  call    TRACELogPrint
0x180032d9a  jmp     loc_180032EEF
0x180032d9f  test    r15d, r15d
0x180032da2  jz      short loc_180032DFD
0x180032da4  lea     rdx, aMsetserverconf_5; "MSetServerConfig: disabling tapi server"
0x180032dab  mov     ecx, 80002h
0x180032db0  call    TRACELogPrint
0x180032db5  lea     rcx, gSCPCritSec; lpCriticalSection
0x180032dbc  call    cs:__imp_EnterCriticalSection
0x180032dc2  lea     rdx, gszRegTapisrvSCPGuid; "TAPISRVSCPGUID"
0x180032dc9  lea     rcx, aCnTelephonySer; "CN=Telephony Service"
0x180032dd0  call    ?RemoveSCP@@YAJPEAGPEBG@Z; RemoveSCP(ushort *,ushort const *)
0x180032dd5  lea     rcx, gSCPCritSec; lpCriticalSection
0x180032ddc  mov     ebx, eax
0x180032dde  call    cs:__imp_LeaveCriticalSection
0x180032de4  mov     [rdi], ebx
0x180032de6  test    ebx, ebx
0x180032de8  jz      short loc_180032DF6
0x180032dea  mov     r8d, ebx
0x180032ded  lea     rdx, aMsetserverconf_3; "MSetServerConfig: RemoveTapiSCP failed,"...
0x180032df4  jmp     short loc_180032D90
0x180032df6  and     cs:dword_180051900, 0FFFFFFFDh
0x180032dfd  mov     r8d, [rsi+0Ch]
0x180032e01  shr     r8d, 1
0x180032e04  not     r8d
0x180032e07  and     r8d, 1
0x180032e0b  call    WriteRegistryKeys
0x180032e10  test    eax, eax
0x180032e12  jz      short loc_180032E2D
0x180032e14  mov     r8d, eax
0x180032e17  lea     rdx, aMsetserverconf_2; "MSetServerConfig: WriteRegistryKeys fai"...
0x180032e1e  mov     ecx, 10002h
0x180032e23  call    TRACELogPrint
0x180032e28  jmp     loc_180032D50
0x180032e2d  test    byte ptr [rsi+0Ch], 8
0x180032e31  jz      loc_180032EEF
0x180032e37  mov     ebx, [rsi+2Ch]
0x180032e3a  mov     edx, 30h ; '0'
0x180032e3f  sub     ebp, [rdi+0Ch]
0x180032e42  mov     r9d, ebx
0x180032e45  mov     r8d, [rsi+28h]
0x180032e49  mov     ecx, ebp
0x180032e4b  mov     [rsp+78h+dwLogonProvider], 2
0x180032e53  call    IsBadSizeOffset
0x180032e58  test    eax, eax
0x180032e5a  jnz     short loc_180032ED5
0x180032e5c  mov     edx, [rsi+28h]
0x180032e5f  add     rbx, rsi
0x180032e62  mov     rcx, rbx
0x180032e65  call    IsBadStringListSize
0x180032e6a  test    eax, eax
0x180032e6c  jnz     short loc_180032ED5
0x180032e6e  lea     r8, gszFileName; "..\\TAPI\\tsec.ini"
0x180032e75  lea     rdx, String; lpString
0x180032e7c  lea     rcx, gszTapiAdministrators; "TapiAdministrators"
0x180032e83  call    cs:__imp_WritePrivateProfileSectionW
0x180032e89  test    eax, eax
0x180032e8b  jz      loc_180032D50
0x180032e91  cmp     [rbx], r13w
0x180032e95  jz      short loc_180032EEF
0x180032e97  lea     r9, gszFileName; "..\\TAPI\\tsec.ini"
0x180032e9e  mov     rdx, rbx; lpKeyName
0x180032ea1  lea     r8, a1; "1"
0x180032ea8  lea     rcx, gszTapiAdministrators; "TapiAdministrators"
0x180032eaf  call    cs:__imp_WritePrivateProfileStringW
0x180032eb5  test    eax, eax
0x180032eb7  jz      loc_180032D50
0x180032ebd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032ec1  inc     rax
0x180032ec4  cmp     [rbx+rax*2], r13w
0x180032ec9  jnz     short loc_180032EC1
0x180032ecb  lea     rbx, [rbx+rax*2]
0x180032ecf  add     rbx, 2
0x180032ed3  jmp     short loc_180032E91
0x180032ed5  lea     rdx, aMsetserverconf_6; "MSetServerConfig: Bad administrators si"...
0x180032edc  jmp     loc_180032D46
0x180032ee1  mov     dword ptr [rdi], 9000001Ch
0x180032ee7  jmp     short loc_180032EEF
0x180032ee9  mov     dword ptr [rdx], 0FFFFFFEDh
0x180032eef  add     rsp, 38h
0x180032ef3  pop     r15
0x180032ef5  pop     r14
0x180032ef7  pop     r13
0x180032ef9  pop     r12
0x180032efb  pop     rdi
0x180032efc  pop     rsi
0x180032efd  pop     rbp
0x180032efe  pop     rbx
0x180032eff  retn
```
