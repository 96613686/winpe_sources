# LaunchContainerShareUtilProcess(IMemObj *)

- ea: `0x10043ffc0`
- end: `0x100440193`
- name: `?LaunchContainerShareUtilProcess@@YAJPEAVIMemObj@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(struct IMemObj *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x100412470`

## callees

- `0x100401580`
- `0x100404a30`
- `0x10043f6a0`
- `0x10043ffc0`
- `0x1004404f0`

## import_xrefs

- `KERNEL32!SetEnvironmentVariableW` at `0x1004400a8`
- `KERNEL32!SetEnvironmentVariableW` at `0x1004400a8`
- `KERNEL32!GetLastError` at `0x1004400b2`
- `KERNEL32!GetLastError` at `0x1004400b2`
- `sqlfabric!?Get@XDBWinFabGlobals@@SAPEAU1@XZ` at `0x10043fff8`
- `sqlfabric!?Get@XDBWinFabGlobals@@SAPEAU1@XZ` at `0x10044002e`
- `sqlfabric!?Get@XDBWinFabGlobals@@SAPEAU1@XZ` at `0x10043fff8`
- `sqlfabric!?Get@XDBWinFabGlobals@@SAPEAU1@XZ` at `0x10044002e`

## string_xrefs

- `0x100440084`: `Fabric_DataDirectory_%s`
- `0x100440063`: `[%hs] ERROR: StoreDataDirectoryInEnvVariable failed. (HRESULT 0x%x)`
- `0x1004400db`: `[%hs] ERROR: StoreDataDirectoryInEnvVariable failed. (HRESULT 0x%x)`
- `0x100440146`: `ContainerShareUtilHost.exe ContainerShare.Data ContainerShareUtil.exe -runAsWcowSidecar:ContainerShare.Sidecar -m container`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LaunchContainerShareUtilProcess(struct IMemObj *a1)
{
  __int64 v2; // rax
  int v3; // ebx
  const wchar_t *v4; // rcx
  __int64 v5; // rax
  const WCHAR *v6; // rdi
  signed int LastError; // eax
  __int64 v8; // rax
  __int64 v10; // [rsp+20h] [rbp-458h] BYREF
  _QWORD v11[3]; // [rsp+28h] [rbp-450h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-438h] BYREF
  wchar_t Buffer[264]; // [rsp+250h] [rbp-228h] BYREF

  v11[1] = -2;
  v11[0] = 0;
  v2 = XDBWinFabGlobals::Get();
  v3 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD *))(**(_QWORD **)(v2 + 24) + 136LL))(
         *(_QWORD *)(v2 + 24),
         L"ContainerShare.Code",
         v11);
  if ( v3 < 0 )
  {
    v4 = L"[%hs] ERROR: Failed to get code package ContainerShare.Code (HRESULT 0x%x)";
LABEL_18:
    _mm_lfence();
    log_unlocalized(v4, "LaunchContainerShareUtilProcess", (unsigned int)v3);
    goto LABEL_20;
  }
  v10 = 0;
  v5 = XDBWinFabGlobals::Get();
  v3 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 *))(**(_QWORD **)(v5 + 24) + 152LL))(
         *(_QWORD *)(v5 + 24),
         L"ContainerShare.Data",
         &v10);
  if ( v3 < 0
    || (v6 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10),
        v3 = StringCchPrintfW(Name, 261, L"Fabric_DataDirectory_%s", L"ContainerShare.Data"),
        v3 < 0) )
  {
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v4 = L"[%hs] ERROR: StoreDataDirectoryInEnvVariable failed. (HRESULT 0x%x)";
      goto LABEL_18;
    }
LABEL_13:
    v4 = L"[%hs] ERROR: StoreDataDirectoryInEnvVariable failed. (HRESULT 0x%x)";
    goto LABEL_18;
  }
  if ( SetEnvironmentVariableW(Name, v6) )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v3 < 0 )
      goto LABEL_13;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 32LL))(v11[0]);
  v3 = StringCchPrintfW(Buffer, 261, L"%s\\ContainerShareUtilHost.exe", v8);
  if ( v3 < 0 )
  {
    v4 = L"[%hs] ERROR: StringCchPrintfW of message failed. (HRESULT 0x%x)";
    goto LABEL_18;
  }
  v3 = BootAndKeepProcessAliveInWcow(
         Buffer,
         L"ContainerShareUtilHost.exe ContainerShare.Data ContainerShareUtil.exe -runAsWcowSidecar:ContainerShare.Sidecar -m container",
         L"ContainerShareUtil",
         a1);
LABEL_20:
  if ( v11[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x10043ffc0  mov     rax, rsp
0x10043ffc3  push    rdi
0x10043ffc4  sub     rsp, 470h
0x10043ffcb  mov     [rsp+478h+var_448], 0FFFFFFFFFFFFFFFEh
0x10043ffd4  mov     [rax+10h], rbx
0x10043ffd8  mov     [rax+18h], rsi
0x10043ffdc  mov     rax, cs:__security_cookie
0x10043ffe3  xor     rax, rsp
0x10043ffe6  mov     [rsp+478h+var_18], rax
0x10043ffee  mov     rsi, rcx
0x10043fff1  xor     edi, edi
0x10043fff3  mov     [rsp+478h+var_450], rdi
0x10043fff8  call    cs:__imp_?Get@XDBWinFabGlobals@@SAPEAU1@XZ; XDBWinFabGlobals::Get(void)
0x10043fffe  mov     rcx, [rax+18h]
0x100440002  mov     rax, [rcx]
0x100440005  lea     r8, [rsp+478h+var_450]
0x10044000a  lea     rdx, aContainershare_1; "ContainerShare.Code"
0x100440011  call    qword ptr [rax+88h]
0x100440017  mov     ebx, eax
0x100440019  test    eax, eax
0x10044001b  jns     short loc_100440029
0x10044001d  lea     rcx, aHsErrorFailedT_1; "[%hs] ERROR: Failed to get code package"...
0x100440024  jmp     loc_100440128
0x100440029  mov     [rsp+478h+var_458], rdi
0x10044002e  call    cs:__imp_?Get@XDBWinFabGlobals@@SAPEAU1@XZ; XDBWinFabGlobals::Get(void)
0x100440034  mov     rcx, [rax+18h]
0x100440038  mov     rax, [rcx]
0x10044003b  lea     r8, [rsp+478h+var_458]
0x100440040  lea     rdx, aContainershare; "ContainerShare.Data"
0x100440047  call    qword ptr [rax+98h]
0x10044004d  mov     ebx, eax
0x10044004f  test    eax, eax
0x100440051  jns     short loc_10044006F
0x100440053  mov     rcx, [rsp+478h+var_458]
0x100440058  test    rcx, rcx
0x10044005b  jz      short loc_1004400DB
0x10044005d  mov     rax, [rcx]
0x100440060  call    qword ptr [rax+10h]
0x100440063  lea     rcx, aHsErrorStoreda; "[%hs] ERROR: StoreDataDirectoryInEnvVar"...
0x10044006a  jmp     loc_100440128
0x10044006f  mov     rcx, [rsp+478h+var_458]
0x100440074  mov     rax, [rcx]
0x100440077  call    qword ptr [rax+20h]
0x10044007a  mov     rdi, rax
0x10044007d  lea     r9, aContainershare; "ContainerShare.Data"
0x100440084  lea     r8, aFabricDatadire; "Fabric_DataDirectory_%s"
0x10044008b  mov     edx, 105h; unsigned __int64
0x100440090  lea     rcx, [rsp+478h+Name]; Buffer
0x100440095  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10044009a  mov     ebx, eax
0x10044009c  test    eax, eax
0x10044009e  js      short loc_100440053
0x1004400a0  mov     rdx, rdi; lpValue
0x1004400a3  lea     rcx, [rsp+478h+Name]; lpName
0x1004400a8  call    cs:__imp_SetEnvironmentVariableW
0x1004400ae  test    eax, eax
0x1004400b0  jnz     short loc_1004400E4
0x1004400b2  call    cs:__imp_GetLastError
0x1004400b8  mov     ebx, eax
0x1004400ba  test    eax, eax
0x1004400bc  jle     short loc_1004400C7
0x1004400be  movzx   ebx, ax
0x1004400c1  or      ebx, 80070000h
0x1004400c7  mov     rcx, [rsp+478h+var_458]
0x1004400cc  test    rcx, rcx
0x1004400cf  jz      short loc_1004400D7
0x1004400d1  mov     rax, [rcx]
0x1004400d4  call    qword ptr [rax+10h]
0x1004400d7  test    ebx, ebx
0x1004400d9  jns     short loc_1004400F4
0x1004400db  lea     rcx, aHsErrorStoreda; "[%hs] ERROR: StoreDataDirectoryInEnvVar"...
0x1004400e2  jmp     short loc_100440128
0x1004400e4  mov     rcx, [rsp+478h+var_458]
0x1004400e9  test    rcx, rcx
0x1004400ec  jz      short loc_1004400F4
0x1004400ee  mov     rax, [rcx]
0x1004400f1  call    qword ptr [rax+10h]
0x1004400f4  mov     rcx, [rsp+478h+var_450]
0x1004400f9  mov     rax, [rcx]
0x1004400fc  call    qword ptr [rax+20h]
0x1004400ff  mov     r9, rax
0x100440102  lea     r8, aSContainershar; "%s\\ContainerShareUtilHost.exe"
0x100440109  mov     edx, 105h; unsigned __int64
0x10044010e  lea     rcx, [rsp+478h+Buffer]; Buffer
0x100440116  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10044011b  mov     ebx, eax
0x10044011d  test    eax, eax
0x10044011f  jns     short loc_10044013C
0x100440121  lea     rcx, aHsErrorStringc; "[%hs] ERROR: StringCchPrintfW of messag"...
0x100440128  lfence
0x10044012b  mov     r8d, ebx
0x10044012e  lea     rdx, aLaunchcontaine_0; "LaunchContainerShareUtilProcess"
0x100440135  call    ?log_unlocalized@@YAXPEB_WZZ; log_unlocalized(wchar_t const *,...)
0x10044013a  jmp     short loc_10044015C
0x10044013c  mov     r9, rsi; struct IMemObj *
0x10044013f  lea     r8, aContainershare_0; "ContainerShareUtil"
0x100440146  lea     rdx, aContainershare_2; "ContainerShareUtilHost.exe ContainerSha"...
0x10044014d  lea     rcx, [rsp+478h+Buffer]; wchar_t *
0x100440155  call    ?BootAndKeepProcessAliveInWcow@@YAJPEB_W00PEAVIMemObj@@@Z; BootAndKeepProcessAliveInWcow(wchar_t const *,wchar_t const *,wchar_t const *,IMemObj *)
0x10044015a  mov     ebx, eax
0x10044015c  mov     rcx, [rsp+478h+var_450]
0x100440161  test    rcx, rcx
0x100440164  jz      short loc_10044016C
0x100440166  mov     rdx, [rcx]
0x100440169  call    qword ptr [rdx+10h]
0x10044016c  mov     eax, ebx
0x10044016e  mov     rcx, [rsp+478h+var_18]
0x100440176  xor     rcx, rsp; StackCookie
0x100440179  call    __security_check_cookie
0x10044017e  lea     r11, [rsp+478h+var_8]
0x100440186  mov     rbx, [r11+18h]
0x10044018a  mov     rsi, [r11+20h]
0x10044018e  mov     rsp, r11
0x100440191  pop     rdi
0x100440192  retn
```
