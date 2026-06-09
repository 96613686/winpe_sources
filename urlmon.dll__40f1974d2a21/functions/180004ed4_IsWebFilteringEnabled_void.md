# IsWebFilteringEnabled(void)

- ea: `0x180004ed4`
- end: `0x180005199`
- name: `?IsWebFilteringEnabled@@YA_NXZ`
- size: `709`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005798`
- `0x1800062c4`

## callees

- `0x180004e84`
- `0x180004ed4`
- `0x18001054c`
- `0x1800150e0`
- `0x180030880`
- `0x180085568`

## import_xrefs

- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x180004f59`
- `iertutil!__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z` at `0x180004f59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005173`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005173`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005069`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005129`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005069`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005129`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000515a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000515a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004f2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004f2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004f3c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004f3c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004f13`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004f13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000509a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000509a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005090`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005090`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004f73`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004f73`

## pseudocode

```c
char IsWebFilteringEnabled(void)
{
  HANDLE CurrentProcess; // rax
  signed int v2; // ebx
  LPWSTR v3; // rdx
  LPWSTR v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 v7; // rsi
  void *v8; // rdi
  unsigned __int64 v9; // rsi
  const WCHAR *v10; // rdx
  PSID Sid; // [rsp+30h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  LPWSTR StringSid; // [rsp+88h] [rbp+48h] BYREF

  if ( !byte_18015E5E3 )
  {
    InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
    if ( byte_18015DE34 && !IsOs_PhoneNT() )
      goto LABEL_20;
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_20;
    v2 = 0;
    Sid = 0;
    if ( GetUserSid(TokenHandle, &Sid) )
    {
LABEL_19:
      CloseHandle(TokenHandle);
      if ( v2 < 0 )
        return byte_18015E5E2;
LABEL_20:
      byte_18015E5E3 = 1;
      return byte_18015E5E2;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    {
LABEL_18:
      LocalFree(Sid);
      goto LABEL_19;
    }
    v3 = StringSid;
    if ( !StringSid )
    {
      v2 = -2147024809;
      goto LABEL_17;
    }
    v4 = StringSid;
    v5 = 0x7FFFFFFF;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v2 = v5 == 0 ? 0x80070057 : 0;
    v6 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
    if ( !v5 )
      goto LABEL_17;
    hKey = 0;
    Data = 0;
    cbData = 4;
    if ( IsOs_Win8OrGreater() )
    {
      v7 = v6 + 72;
      v8 = operator new(saturated_mul(v6 + 73, 2u));
      if ( !v8
        || (v2 = StringCchPrintfW(
                   (unsigned __int16 *)v8,
                   v7,
                   L"%s%s%s",
                   L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Parental Controls\\users\\",
                   StringSid,
                   L"\\Web"),
            v2 < 0)
        || RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v8, 0, 0x101u, &hKey) )
      {
LABEL_16:
        operator delete(v8);
        v3 = StringSid;
LABEL_17:
        LocalFree(v3);
        goto LABEL_18;
      }
      v10 = L"Filter On";
    }
    else
    {
      v9 = v6 + 67;
      v8 = operator new(saturated_mul(v6 + 68, 2u));
      if ( !v8 )
        goto LABEL_16;
      v2 = StringCchPrintfW(
             (unsigned __int16 *)v8,
             v9,
             L"%s%s",
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Parental Controls\\users\\",
             StringSid);
      if ( v2 < 0 || RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v8, 0, 0x101u, &hKey) )
        goto LABEL_16;
      v10 = L"Parental Controls On";
    }
    if ( !RegQueryValueExW(hKey, v10, 0, 0, (LPBYTE)&Data, &cbData) )
      byte_18015E5E2 = Data != 0;
    RegCloseKey(hKey);
    goto LABEL_16;
  }
  return byte_18015E5E2;
}

```

## disassembly

```asm
0x180004ed4  push    rbp
0x180004ed6  push    rbx
0x180004ed7  push    rsi
0x180004ed8  push    rdi
0x180004ed9  push    r14
0x180004edb  mov     rbp, rsp
0x180004ede  sub     rsp, 40h
0x180004ee2  xor     r14d, r14d
0x180004ee5  cmp     cs:byte_18015E5E3, r14b
0x180004eec  jz      short loc_180004EFF
0x180004eee  mov     al, cs:byte_18015E5E2
0x180004ef4  add     rsp, 40h
0x180004ef8  pop     r14
0x180004efa  pop     rdi
0x180004efb  pop     rsi
0x180004efc  pop     rbx
0x180004efd  pop     rbp
0x180004efe  retn
0x180004eff  xor     r9d, r9d; Context
0x180004f02  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004f09  xor     r8d, r8d; Parameter
0x180004f0c  lea     rcx, stru_18015EA38; InitOnce
0x180004f13  call    cs:__imp_InitOnceExecuteOnce
0x180004f19  cmp     cs:byte_18015DE34, r14b
0x180004f20  jnz     loc_18000517E
0x180004f26  mov     [rbp+TokenHandle], r14
0x180004f2a  call    cs:__imp_GetCurrentProcess
0x180004f30  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180004f34  mov     edx, 8; DesiredAccess
0x180004f39  mov     rcx, rax; ProcessHandle
0x180004f3c  call    cs:__imp_OpenProcessToken
0x180004f42  test    eax, eax
0x180004f44  jz      loc_1800050A8
0x180004f4a  mov     rcx, [rbp+TokenHandle]
0x180004f4e  lea     rdx, [rbp+Sid]
0x180004f52  mov     ebx, r14d
0x180004f55  mov     [rbp+Sid], r14
0x180004f59  call    cs:__imp_?GetUserSid@@YAKPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180004f5f  test    eax, eax
0x180004f61  jnz     loc_180005096
0x180004f67  mov     rcx, [rbp+Sid]; Sid
0x180004f6b  lea     rdx, [rbp+StringSid]; StringSid
0x180004f6f  mov     [rbp+StringSid], r14
0x180004f73  call    cs:__imp_ConvertSidToStringSidW
0x180004f79  test    eax, eax
0x180004f7b  jz      loc_18000508C
0x180004f81  mov     rdx, [rbp+StringSid]
0x180004f85  test    rdx, rdx
0x180004f88  jz      loc_1800050B4
0x180004f8e  mov     r8d, 7FFFFFFFh
0x180004f94  mov     rax, rdx
0x180004f97  mov     ecx, r8d
0x180004f9a  cmp     [rax], r14w
0x180004f9e  jz      short loc_180004FAA
0x180004fa0  add     rax, 2
0x180004fa4  sub     rcx, 1
0x180004fa8  jnz     short loc_180004F9A
0x180004faa  mov     rax, rcx
0x180004fad  neg     rax
0x180004fb0  mov     rax, rcx
0x180004fb3  sbb     ebx, ebx
0x180004fb5  sub     r8, rcx
0x180004fb8  not     ebx
0x180004fba  and     ebx, 80070057h
0x180004fc0  neg     rax
0x180004fc3  sbb     rdi, rdi
0x180004fc6  and     rdi, r8
0x180004fc9  test    rcx, rcx
0x180004fcc  jz      loc_180005083
0x180004fd2  mov     [rbp+hKey], r14
0x180004fd6  mov     [rbp+Data], r14d
0x180004fda  mov     [rbp+cbData], 4
0x180004fe1  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x180004fe6  test    al, al
0x180004fe8  mov     eax, 2
0x180004fed  jz      loc_1800050BB
0x180004ff3  lea     rsi, [rdi+48h]
0x180004ff7  lea     rcx, [rsi+1]
0x180004ffb  mul     rcx
0x180004ffe  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005005  cmovb   rax, rcx
0x180005009  mov     rcx, rax; Size
0x18000500c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005011  mov     rdi, rax
0x180005014  test    rax, rax
0x180005017  jz      short loc_180005077
0x180005019  mov     rcx, [rbp+StringSid]
0x18000501d  lea     rax, aWeb; "\\Web"
0x180005024  mov     [rsp+40h+lpcbData], rax
0x180005029  lea     r9, aSoftwareMicros_104; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180005030  mov     [rsp+40h+phkResult], rcx
0x180005035  lea     r8, aSSS; "%s%s%s"
0x18000503c  mov     rcx, rdi; unsigned __int16 *
0x18000503f  mov     rdx, rsi; unsigned __int64
0x180005042  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005047  mov     ebx, eax
0x180005049  test    eax, eax
0x18000504b  js      short loc_180005077
0x18000504d  lea     rax, [rbp+hKey]
0x180005051  mov     r9d, 101h; samDesired
0x180005057  xor     r8d, r8d; ulOptions
0x18000505a  mov     [rsp+40h+phkResult], rax; phkResult
0x18000505f  mov     rdx, rdi; lpSubKey
0x180005062  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005069  call    cs:__imp_RegOpenKeyExW
0x18000506f  test    eax, eax
0x180005071  jz      loc_180005190
0x180005077  mov     rcx, rdi; void *
0x18000507a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000507f  mov     rdx, [rbp+StringSid]
0x180005083  mov     rcx, rdx; hMem
0x180005086  call    cs:__imp_LocalFree
0x18000508c  mov     rcx, [rbp+Sid]; hMem
0x180005090  call    cs:__imp_LocalFree
0x180005096  mov     rcx, [rbp+TokenHandle]; hObject
0x18000509a  call    cs:__imp_CloseHandle
0x1800050a0  test    ebx, ebx
0x1800050a2  js      loc_180004EEE
0x1800050a8  mov     cs:byte_18015E5E3, 1
0x1800050af  jmp     loc_180004EEE
0x1800050b4  mov     ebx, 80070057h
0x1800050b9  jmp     short loc_180005083
0x1800050bb  lea     rsi, [rdi+43h]
0x1800050bf  lea     rcx, [rsi+1]
0x1800050c3  mul     rcx
0x1800050c6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800050cd  cmovb   rax, rcx
0x1800050d1  mov     rcx, rax; Size
0x1800050d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800050d9  mov     rdi, rax
0x1800050dc  test    rax, rax
0x1800050df  jz      short loc_180005077
0x1800050e1  mov     rax, [rbp+StringSid]
0x1800050e5  lea     r9, aSoftwareMicros_104; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800050ec  lea     r8, aSS_3; "%s%s"
0x1800050f3  mov     [rsp+40h+phkResult], rax
0x1800050f8  mov     rdx, rsi; unsigned __int64
0x1800050fb  mov     rcx, rdi; unsigned __int16 *
0x1800050fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005103  mov     ebx, eax
0x180005105  test    eax, eax
0x180005107  js      loc_180005077
0x18000510d  lea     rax, [rbp+hKey]
0x180005111  mov     r9d, 101h; samDesired
0x180005117  xor     r8d, r8d; ulOptions
0x18000511a  mov     [rsp+40h+phkResult], rax; phkResult
0x18000511f  mov     rdx, rdi; lpSubKey
0x180005122  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005129  call    cs:__imp_RegOpenKeyExW
0x18000512f  test    eax, eax
0x180005131  jnz     loc_180005077
0x180005137  lea     rdx, aParentalContro; "Parental Controls On"
0x18000513e  mov     rcx, [rbp+hKey]; hKey
0x180005142  lea     rax, [rbp+cbData]
0x180005146  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000514b  xor     r9d, r9d; lpType
0x18000514e  lea     rax, [rbp+Data]
0x180005152  xor     r8d, r8d; lpReserved
0x180005155  mov     [rsp+40h+phkResult], rax; lpData
0x18000515a  call    cs:__imp_RegQueryValueExW
0x180005160  test    eax, eax
0x180005162  jnz     short loc_18000516F
0x180005164  cmp     [rbp+Data], r14d
0x180005168  setnz   cs:byte_18015E5E2
0x18000516f  mov     rcx, [rbp+hKey]; hKey
0x180005173  call    cs:__imp_RegCloseKey
0x180005179  jmp     loc_180005077
0x18000517e  call    ?IsOs_PhoneNT@@YA_NXZ; IsOs_PhoneNT(void)
0x180005183  test    al, al
0x180005185  jz      loc_1800050A8
0x18000518b  jmp     loc_180004F26
0x180005190  lea     rdx, aFilterOn; "Filter On"
0x180005197  jmp     short loc_18000513E
```
