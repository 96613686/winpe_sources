# ScGetFullLogPath(ushort const *,ushort const *,ushort *)

- ea: `0x140031ac0`
- end: `0x140031caf`
- name: `?ScGetFullLogPath@@YAKPEBG0PEAG@Z`
- size: `495`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140031618`
- `0x140087070`

## callees

- `0x14001df34`
- `0x140031ac0`
- `0x1400575b0`
- `0x140057860`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031b79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140031b79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140031b39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140031b39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031c80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031c80`
- `ntdll!RtlNtStatusToDosError` at `0x140031c23`
- `ntdll!RtlNtStatusToDosError` at `0x140031c23`
- `ntdll!RtlExpandEnvironmentStrings` at `0x140031c6a`
- `ntdll!RtlExpandEnvironmentStrings` at `0x140031c6a`
- `ntdll!RtlGetPersistedStateLocation` at `0x140031c17`
- `ntdll!RtlGetPersistedStateLocation` at `0x140031c17`

## string_xrefs

- `0x140031bf9`: `%windir%\system32\LogFiles\Scm\`
- `0x140031b72`: `TracingPath`

## pseudocode

```c
__int64 __fastcall ScGetFullLogPath(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax
  ULONG v7; // ebx
  NTSTATUS PersistedStateLocation; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 Data[264]; // [rsp+60h] [rbp-A0h] BYREF

  cbData = 0;
  Type = 0;
  v13 = 0;
  memset(Data, 0, 0x208u);
  hKey[0] = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\SCM\\Regular",
         0,
         0x20019u,
         hKey)
    || (cbData = 520, RegQueryValueExW(hKey[0], L"TracingPath", 0, &Type, (LPBYTE)Data, &cbData))
    || Type != 1
    || cbData + 16 > 0x104 )
  {
    LODWORD(lpcbData) = 520;
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"DefaultScmLogFolder",
                               0,
                               L"%windir%\\system32\\LogFiles\\Scm\\",
                               1,
                               Data,
                               lpcbData,
                               &v13);
    if ( PersistedStateLocation < 0 )
    {
LABEL_14:
      v7 = RtlNtStatusToDosError(PersistedStateLocation);
      goto LABEL_19;
    }
  }
  else
  {
    v4 = cbData & 0xFFFFFFFE;
    if ( v4 >= 0x208 )
      _report_rangecheckfailure();
    *(unsigned __int16 *)((char *)Data + v4) = 0;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( Data[v6] );
  if ( *((_WORD *)&hKey[1] + v6 + 3) != 92 && (unsigned int)StringCchCatW(Data, 0x104u, L"\\")
    || (unsigned int)StringCchCatW(Data, 0x104u, L"SCM.EVM") )
  {
    v7 = 122;
    goto LABEL_19;
  }
  do
    ++v5;
  while ( Data[v5] );
  PersistedStateLocation = RtlExpandEnvironmentStrings(0, Data, v5, a3, 260, 0);
  if ( PersistedStateLocation < 0 )
    goto LABEL_14;
  v7 = 0;
LABEL_19:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v7;
}

```

## disassembly

```asm
0x140031ac0  mov     [rsp-8+arg_0], rbx
0x140031ac5  mov     [rsp-8+arg_8], rsi
0x140031aca  push    rbp
0x140031acb  push    rdi
0x140031acc  push    r14
0x140031ace  lea     rbp, [rsp-180h]
0x140031ad6  sub     rsp, 280h
0x140031add  mov     rax, cs:__security_cookie
0x140031ae4  xor     rax, rsp
0x140031ae7  mov     [rbp+190h+var_20], rax
0x140031aee  xor     esi, esi
0x140031af0  lea     rcx, [rsp+290h+Data]; void *
0x140031af5  mov     rdi, r8
0x140031af8  mov     [rsp+290h+cbData], esi
0x140031afc  mov     ebx, 208h
0x140031b01  mov     [rsp+290h+Type], esi
0x140031b05  mov     r8d, ebx; Size
0x140031b08  mov     [rsp+290h+var_248], esi
0x140031b0c  xor     edx, edx; Val
0x140031b0e  call    memset
0x140031b13  lea     rax, [rsp+290h+hKey]
0x140031b18  mov     [rsp+290h+hKey], rsi
0x140031b1d  mov     r9d, 20019h; samDesired
0x140031b23  mov     [rsp+290h+phkResult], rax; phkResult
0x140031b28  xor     r8d, r8d; ulOptions
0x140031b2b  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x140031b32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140031b39  call    cs:__imp_RegOpenKeyExW
0x140031b3f  mov     r14d, 104h
0x140031b45  test    eax, eax
0x140031b47  jnz     loc_140031BE9
0x140031b4d  mov     rcx, [rsp+290h+hKey]; hKey
0x140031b52  lea     rax, [rsp+290h+cbData]
0x140031b57  mov     [rsp+290h+lpcbData], rax; lpcbData
0x140031b5c  lea     r9, [rsp+290h+Type]; lpType
0x140031b61  lea     rax, [rsp+290h+Data]
0x140031b66  mov     [rsp+290h+cbData], ebx
0x140031b6a  xor     r8d, r8d; lpReserved
0x140031b6d  mov     [rsp+290h+phkResult], rax; lpData
0x140031b72  lea     rdx, aTracingpath; "TracingPath"
0x140031b79  call    cs:__imp_RegQueryValueExW
0x140031b7f  test    eax, eax
0x140031b81  jnz     short loc_140031BE9
0x140031b83  cmp     [rsp+290h+Type], 1
0x140031b88  jnz     short loc_140031BE9
0x140031b8a  mov     ecx, [rsp+290h+cbData]
0x140031b8e  lea     eax, [rcx+10h]
0x140031b91  cmp     eax, r14d
0x140031b94  ja      short loc_140031BE9
0x140031b96  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140031b9a  cmp     rcx, rbx
0x140031b9d  jnb     short loc_140031BE3
0x140031b9f  mov     [rsp+rcx+290h+Data], si
0x140031ba4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140031ba8  lea     rcx, [rsp+290h+Data]
0x140031bad  mov     rax, rbx
0x140031bb0  inc     rax
0x140031bb3  cmp     [rcx+rax*2], si
0x140031bb7  jnz     short loc_140031BB0
0x140031bb9  cmp     [rsp+rax*2+290h+var_232], 5Ch ; '\'
0x140031bbf  jz      short loc_140031C2D
0x140031bc1  lea     r8, SubBlock; "\\"
0x140031bc8  mov     rdx, r14; unsigned __int64
0x140031bcb  lea     rcx, [rsp+290h+Data]; unsigned __int16 *
0x140031bd0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140031bd5  test    eax, eax
0x140031bd7  jz      short loc_140031C2D
0x140031bd9  mov     ebx, 7Ah ; 'z'
0x140031bde  jmp     loc_140031C76
0x140031be3  call    __report_rangecheckfailure
0x140031be9  lea     rax, [rsp+290h+var_248]
0x140031bee  mov     r9d, 1
0x140031bf4  mov     [rsp+290h+var_260], rax
0x140031bf9  lea     r8, aWindirSystem32; "%windir%\\system32\\LogFiles\\Scm\\"
0x140031c00  lea     rax, [rsp+290h+Data]
0x140031c05  mov     dword ptr [rsp+290h+lpcbData], ebx
0x140031c09  xor     edx, edx
0x140031c0b  mov     [rsp+290h+phkResult], rax
0x140031c10  lea     rcx, aDefaultscmlogf; "DefaultScmLogFolder"
0x140031c17  call    cs:__imp_RtlGetPersistedStateLocation
0x140031c1d  test    eax, eax
0x140031c1f  jns     short loc_140031BA4
0x140031c21  mov     ecx, eax; Status
0x140031c23  call    cs:__imp_RtlNtStatusToDosError
0x140031c29  mov     ebx, eax
0x140031c2b  jmp     short loc_140031C76
0x140031c2d  lea     r8, aScmEvm; "SCM.EVM"
0x140031c34  mov     rdx, r14; unsigned __int64
0x140031c37  lea     rcx, [rsp+290h+Data]; unsigned __int16 *
0x140031c3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140031c41  test    eax, eax
0x140031c43  jnz     short loc_140031BD9
0x140031c45  lea     rax, [rsp+290h+Data]
0x140031c4a  inc     rbx
0x140031c4d  cmp     [rax+rbx*2], si
0x140031c51  jnz     short loc_140031C4A
0x140031c53  mov     [rsp+290h+lpcbData], rsi
0x140031c58  lea     rdx, [rsp+290h+Data]
0x140031c5d  mov     r9, rdi
0x140031c60  mov     [rsp+290h+phkResult], r14
0x140031c65  mov     r8, rbx
0x140031c68  xor     ecx, ecx
0x140031c6a  call    cs:__imp_RtlExpandEnvironmentStrings
0x140031c70  test    eax, eax
0x140031c72  js      short loc_140031C21
0x140031c74  mov     ebx, esi
0x140031c76  mov     rcx, [rsp+290h+hKey]; hKey
0x140031c7b  test    rcx, rcx
0x140031c7e  jz      short loc_140031C86
0x140031c80  call    cs:__imp_RegCloseKey
0x140031c86  mov     eax, ebx
0x140031c88  mov     rcx, [rbp+190h+var_20]
0x140031c8f  xor     rcx, rsp; StackCookie
0x140031c92  call    __security_check_cookie
0x140031c97  lea     r11, [rsp+290h+var_10]
0x140031c9f  mov     rbx, [r11+20h]
0x140031ca3  mov     rsi, [r11+28h]
0x140031ca7  mov     rsp, r11
0x140031caa  pop     r14
0x140031cac  pop     rdi
0x140031cad  pop     rbp
0x140031cae  retn
```
