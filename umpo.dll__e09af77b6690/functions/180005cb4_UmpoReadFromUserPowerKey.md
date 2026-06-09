# UmpoReadFromUserPowerKey

- ea: `0x180005cb4`
- end: `0x1800061c3`
- name: `UmpoReadFromUserPowerKey`
- size: `1295`
- prototype: `__int64 __fastcall(UUID *Uuid2, UUID *, UUID *, char, char, unsigned int, LPDWORD lpType, BYTE *lpData, LPDWORD lpcbData, int *)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180004420`
- `0x180004830`
- `0x180004c48`
- `0x1800059c0`
- `0x180008044`

## callees

- `0x180003370`
- `0x180003560`
- `0x1800051e0`
- `0x180005480`
- `0x1800059c0`
- `0x180005cb4`
- `0x18000681c`
- `0x18000ab60`
- `0x180010070`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000612d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000612d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006194`
- `RPCRT4!UuidEqual` at `0x180005fb0`
- `RPCRT4!UuidEqual` at `0x1800060c1`
- `RPCRT4!UuidEqual` at `0x180005fb0`
- `RPCRT4!UuidEqual` at `0x1800060c1`

## pseudocode

```c
__int64 __fastcall UmpoReadFromUserPowerKey(
        UUID *Uuid2,
        UUID *a2,
        UUID *a3,
        char a4,
        char a5,
        unsigned int a6,
        LPDWORD lpType,
        BYTE *lpData,
        LPDWORD lpcbData,
        int *a10)
{
  unsigned int SettingFromUserStore; // ebx
  HKEY v13; // rbx
  HKEY v14; // r12
  unsigned int Value; // eax
  HKEY v16; // rbx
  const WCHAR *v17; // rdx
  DWORD v20; // [rsp+64h] [rbp-5Dh]
  int v22; // [rsp+78h] [rbp-49h] BYREF
  RPC_STATUS Status; // [rsp+7Ch] [rbp-45h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-41h] BYREF
  HKEY v25; // [rsp+88h] [rbp-39h] BYREF
  __int64 v26; // [rsp+90h] [rbp-31h]
  HKEY phkResult; // [rsp+98h] [rbp-29h] BYREF
  __int64 v28[2]; // [rsp+A0h] [rbp-21h] BYREF

  v26 = (__int64)lpType;
  v22 = 0;
  Status = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( UmpoFullPowerPlanSupportDisabled
    && Uuid2
    && (*(_QWORD *)&Uuid2->Data1 != *(_QWORD *)&GUID_TYPICAL_POWER_SAVINGS.Data1
     || *(_QWORD *)Uuid2->Data4 != *(_QWORD *)GUID_TYPICAL_POWER_SAVINGS.Data4) )
  {
    SettingFromUserStore = 50;
    goto LABEL_59;
  }
  if ( !lpcbData || !a4 && a5 )
    return 87;
  if ( a10 && a6 > 1 )
    return 87;
  if ( a4
    && Uuid2
    && *(_QWORD *)&Uuid2->Data1 == *(_QWORD *)&GUID_POWER_MODE_NONE.Data1
    && *(_QWORD *)Uuid2->Data4 == *(_QWORD *)GUID_POWER_MODE_NONE.Data4 )
  {
    return 87;
  }
  v20 = *lpcbData;
  if ( a6 <= 1 && (!Uuid2 || !a3 || *lpcbData != 4) )
    return 87;
  SettingFromUserStore = UmpoInternalOpenUserPowerKey(&phkResult, 131097, 1);
  if ( SettingFromUserStore )
    goto LABEL_59;
  v13 = phkResult;
  v25 = phkResult;
  if ( a6 - 2 <= 1 || a6 == 13 )
  {
    if ( Uuid2 )
    {
      if ( !a3 && (!a2 || UuidEqual(a2, (UUID *)&NO_SUBGROUP_GUID, &Status)) )
      {
        SettingFromUserStore = UmpoInternalOpenGUIDSubKey(v13, Uuid2, &hKey, 0x20019u, 1, 0);
        if ( SettingFromUserStore )
          goto LABEL_59;
        v16 = hKey;
        v17 = (const WCHAR *)UmpoInternalDataAccessorToString(a6);
        if ( v17 )
        {
          *lpcbData = v20;
          Value = RegQueryValueExW(v16, v17, 0, lpType, lpData, lpcbData);
          goto LABEL_58;
        }
LABEL_53:
        SettingFromUserStore = 87;
        goto LABEL_59;
      }
    }
    else if ( !a3 && !a2 )
    {
      goto LABEL_53;
    }
    *lpcbData = v20;
    Value = UmpoReadFromSystemPowerKey(0, a2, 0, a3, 0, a6, lpType, 0, lpData, lpcbData, 0);
    goto LABEL_58;
  }
  if ( a6 > 1 )
    goto LABEL_53;
  v22 = 0;
  if ( !a5 )
  {
    if ( qword_1800246B0 )
    {
      SettingFromUserStore = qword_1800246B0(a3, a6, &v22);
      if ( !SettingFromUserStore )
      {
        if ( lpType )
          *lpType = 4;
        if ( *lpcbData >= 4 )
        {
          if ( a10 )
            *a10 = 0;
          if ( lpData )
          {
            *(_DWORD *)lpData = v22;
            *lpcbData = 4;
          }
        }
        else
        {
          *lpcbData = 4;
          SettingFromUserStore = 234;
        }
        goto LABEL_59;
      }
    }
  }
  if ( UmpoStateSeparationEnabled
    && (SettingFromUserStore = UmpoInternalReadSettingFromUserStore(
                                 UmpoUserPowerStateSepRootKey,
                                 Uuid2,
                                 a2,
                                 a3,
                                 a6,
                                 lpType,
                                 lpData,
                                 lpcbData)) == 0
    || (*lpcbData = v20,
        v14 = v25,
        (SettingFromUserStore = UmpoInternalReadSettingFromUserStore(v25, Uuid2, a2, a3, a6, lpType, lpData, lpcbData)) == 0) )
  {
    if ( a10 )
      *a10 = 1;
    goto LABEL_59;
  }
  SettingFromUserStore = UmpoInternalOpenGUIDSubKey(v14, Uuid2, &hKey, 0x20019u, 1, 0);
  if ( !SettingFromUserStore )
  {
    *lpcbData = v20;
    SettingFromUserStore = UmpoReadFromSystemPowerKey(
                             Uuid2,
                             a2,
                             0,
                             a3,
                             a4,
                             (unsigned int)(a6 != 0) + 7,
                             (DWORD *)v26,
                             0,
                             lpData,
                             lpcbData,
                             a10);
    if ( SettingFromUserStore )
    {
      if ( a4 )
      {
        SettingFromUserStore = 2;
        goto LABEL_59;
      }
      if ( UuidEqual(&GUID_POWERSCHEME_PERSONALITY, a3, &Status)
        || (LODWORD(v25) = 16,
            *(_OWORD *)v28 = 0,
            (unsigned int)UmpoInternalReadxCValue(
                            0,
                            Uuid2,
                            (UUID *)&NO_SUBGROUP_GUID,
                            0,
                            (__int64)&GUID_POWERSCHEME_PERSONALITY,
                            a6 == 0,
                            0,
                            (__int64)v28,
                            (LPDWORD)&v25))
        || (*lpcbData = v20,
            (SettingFromUserStore = UmpoReadFromSystemPowerKey(
                                      (UUID *)v28,
                                      a2,
                                      0,
                                      a3,
                                      0,
                                      (unsigned int)(a6 != 0) + 7,
                                      (DWORD *)v26,
                                      0,
                                      lpData,
                                      lpcbData,
                                      a10)) != 0) )
      {
        *lpcbData = v20;
        Value = UmpoReadFromSystemPowerKey(
                  &GUID_TYPICAL_POWER_SAVINGS,
                  a2,
                  0,
                  a3,
                  0,
                  (unsigned int)(a6 != 0) + 7,
                  (DWORD *)v26,
                  0,
                  lpData,
                  lpcbData,
                  a10);
LABEL_58:
        SettingFromUserStore = Value;
      }
    }
  }
LABEL_59:
  UmpoInternalCloseUserPowerKey(phkResult);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return SettingFromUserStore;
}

```

## disassembly

```asm
0x180005cb4  push    rbp
0x180005cb6  push    rbx
0x180005cb7  push    rsi
0x180005cb8  push    rdi
0x180005cb9  push    r12
0x180005cbb  push    r13
0x180005cbd  push    r14
0x180005cbf  push    r15
0x180005cc1  lea     rbp, [rsp-7]
0x180005cc6  sub     rsp, 0C8h
0x180005ccd  mov     rax, cs:__security_cookie
0x180005cd4  xor     rax, rsp
0x180005cd7  mov     [rbp+3Fh+var_50], rax
0x180005cdb  mov     rax, [rbp+3Fh+arg_38]
0x180005ce2  mov     r14, rcx
0x180005ce5  mov     r12, [rbp+3Fh+lpType]
0x180005ce9  xor     ecx, ecx
0x180005ceb  mov     r13d, [rbp+3Fh+arg_28]
0x180005cef  mov     r15, r8
0x180005cf2  mov     rdi, [rbp+3Fh+arg_40]
0x180005cf9  mov     rsi, [rbp+3Fh+arg_48]
0x180005d00  mov     [rbp+3Fh+var_98], rax
0x180005d04  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005d08  cmp     cs:UmpoFullPowerPlanSupportDisabled, cl
0x180005d0e  mov     [rbp+3Fh+var_A0], r9b
0x180005d12  mov     [rbp+3Fh+Uuid1], rdx
0x180005d16  mov     [rbp+3Fh+var_70], r12
0x180005d1a  mov     [rbp+3Fh+var_88], ecx
0x180005d1d  mov     [rbp+3Fh+Status], ecx
0x180005d20  mov     [rbp+3Fh+hKey], rax
0x180005d24  mov     [rbp+3Fh+phkResult], rax
0x180005d28  jz      short loc_180005D52
0x180005d2a  test    r14, r14
0x180005d2d  jz      short loc_180005D52
0x180005d2f  mov     rax, [r14]
0x180005d32  cmp     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data1
0x180005d39  jnz     short loc_180005D48
0x180005d3b  mov     rax, [r14+8]
0x180005d3f  cmp     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data4
0x180005d46  jz      short loc_180005D52
0x180005d48  mov     ebx, 32h ; '2'
0x180005d4d  jmp     loc_18000617D
0x180005d52  test    rdi, rdi
0x180005d55  jz      loc_18000619E
0x180005d5b  test    r9b, r9b
0x180005d5e  jnz     short loc_180005D69
0x180005d60  cmp     [rbp+3Fh+arg_20], cl
0x180005d63  jnz     loc_18000619E
0x180005d69  test    rsi, rsi
0x180005d6c  jz      short loc_180005D78
0x180005d6e  cmp     r13d, 1
0x180005d72  ja      loc_18000619E
0x180005d78  test    r9b, r9b
0x180005d7b  jz      short loc_180005D9F
0x180005d7d  test    r14, r14
0x180005d80  jz      short loc_180005D9F
0x180005d82  mov     rax, [r14]
0x180005d85  cmp     rax, qword ptr cs:GUID_POWER_MODE_NONE.Data1
0x180005d8c  jnz     short loc_180005D9F
0x180005d8e  mov     rax, [r14+8]
0x180005d92  cmp     rax, qword ptr cs:GUID_POWER_MODE_NONE.Data4
0x180005d99  jz      loc_18000619E
0x180005d9f  mov     eax, [rdi]
0x180005da1  mov     [rbp+3Fh+var_9C], eax
0x180005da4  cmp     r13d, 1
0x180005da8  ja      short loc_180005DC5
0x180005daa  test    r14, r14
0x180005dad  jz      loc_18000619E
0x180005db3  test    r15, r15
0x180005db6  jz      loc_18000619E
0x180005dbc  cmp     eax, 4
0x180005dbf  jnz     loc_18000619E
0x180005dc5  mov     edx, 20019h; samDesired
0x180005dca  lea     rcx, [rbp+3Fh+phkResult]; phkResult
0x180005dce  mov     r8d, 1
0x180005dd4  call    UmpoInternalOpenUserPowerKey
0x180005dd9  xor     edx, edx
0x180005ddb  mov     ebx, eax
0x180005ddd  test    eax, eax
0x180005ddf  jnz     loc_18000617D
0x180005de5  mov     rbx, [rbp+3Fh+phkResult]
0x180005de9  lea     eax, [r13-2]
0x180005ded  mov     [rbp+3Fh+var_78], rbx
0x180005df1  cmp     eax, 1
0x180005df4  jbe     loc_180006098
0x180005dfa  cmp     r13d, 0Dh
0x180005dfe  jz      loc_180006098
0x180005e04  cmp     r13d, 1
0x180005e08  ja      loc_18000610A
0x180005e0e  mov     [rbp+3Fh+var_88], edx
0x180005e11  cmp     [rbp+3Fh+arg_20], dl
0x180005e14  jnz     short loc_180005E7F
0x180005e16  mov     rax, cs:qword_1800246B0
0x180005e1d  test    rax, rax
0x180005e20  jz      short loc_180005E7F
0x180005e22  lea     r8, [rbp+3Fh+var_88]
0x180005e26  mov     edx, r13d
0x180005e29  mov     rcx, r15
0x180005e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e31  xor     edx, edx
0x180005e33  mov     ebx, eax
0x180005e35  test    eax, eax
0x180005e37  jnz     short loc_180005E7F
0x180005e39  test    r12, r12
0x180005e3c  jz      short loc_180005E46
0x180005e3e  mov     dword ptr [r12], 4
0x180005e46  cmp     dword ptr [rdi], 4
0x180005e49  jnb     short loc_180005E5B
0x180005e4b  mov     dword ptr [rdi], 4
0x180005e51  mov     ebx, 0EAh
0x180005e56  jmp     loc_18000617D
0x180005e5b  test    rsi, rsi
0x180005e5e  jz      short loc_180005E62
0x180005e60  mov     [rsi], edx
0x180005e62  mov     rcx, [rbp+3Fh+var_98]
0x180005e66  test    rcx, rcx
0x180005e69  jz      loc_18000617D
0x180005e6f  mov     eax, [rbp+3Fh+var_88]
0x180005e72  mov     [rcx], eax
0x180005e74  mov     dword ptr [rdi], 4
0x180005e7a  jmp     loc_18000617D
0x180005e7f  cmp     cs:UmpoStateSeparationEnabled, dl
0x180005e85  jz      short loc_180005ECF
0x180005e87  mov     rax, [rbp+3Fh+var_98]
0x180005e8b  mov     r9, r15
0x180005e8e  mov     r8, [rbp+3Fh+Uuid1]
0x180005e92  mov     rdx, r14
0x180005e95  mov     rcx, cs:UmpoUserPowerStateSepRootKey
0x180005e9c  mov     qword ptr [rsp+100h+var_C8], rdi
0x180005ea1  mov     [rsp+100h+var_D0], rax
0x180005ea6  mov     [rsp+100h+lpcbData], r12
0x180005eab  mov     dword ptr [rsp+100h+lpData], r13d
0x180005eb0  call    UmpoInternalReadSettingFromUserStore
0x180005eb5  mov     ebx, eax
0x180005eb7  test    eax, eax
0x180005eb9  jnz     short loc_180005ECF
0x180005ebb  test    rsi, rsi
0x180005ebe  jz      loc_18000617D
0x180005ec4  mov     dword ptr [rsi], 1
0x180005eca  jmp     loc_18000617D
0x180005ecf  mov     eax, [rbp+3Fh+var_9C]
0x180005ed2  mov     r9, r15
0x180005ed5  mov     r8, [rbp+3Fh+Uuid1]
0x180005ed9  mov     rdx, r14
0x180005edc  mov     qword ptr [rsp+100h+var_C8], rdi
0x180005ee1  mov     [rdi], eax
0x180005ee3  mov     rax, [rbp+3Fh+var_98]
0x180005ee7  mov     [rsp+100h+var_D0], rax
0x180005eec  mov     [rsp+100h+lpcbData], r12
0x180005ef1  mov     r12, [rbp+3Fh+var_78]
0x180005ef5  mov     rcx, r12
0x180005ef8  mov     dword ptr [rsp+100h+lpData], r13d
0x180005efd  call    UmpoInternalReadSettingFromUserStore
0x180005f02  mov     ebx, eax
0x180005f04  test    eax, eax
0x180005f06  jz      short loc_180005EBB
0x180005f08  mov     [rsp+100h+lpcbData], 0; __int64
0x180005f11  lea     r8, [rbp+3Fh+hKey]; phkResult
0x180005f15  mov     r9d, 20019h; samDesired
0x180005f1b  mov     byte ptr [rsp+100h+lpData], 1; char
0x180005f20  mov     rdx, r14; Uuid2
0x180005f23  mov     rcx, r12; hKey
0x180005f26  call    UmpoInternalOpenGUIDSubKey
0x180005f2b  mov     ebx, eax
0x180005f2d  test    eax, eax
0x180005f2f  jnz     loc_18000617D
0x180005f35  mov     eax, [rbp+3Fh+var_9C]
0x180005f38  mov     r9, r15
0x180005f3b  mov     rdx, [rbp+3Fh+Uuid1]; Uuid1
0x180005f3f  mov     rcx, r14; __int64
0x180005f42  mov     [rdi], eax
0x180005f44  mov     eax, r13d
0x180005f47  mov     [rsp+100h+var_B0], rsi; __int64
0x180005f4c  neg     eax
0x180005f4e  mov     rax, [rbp+3Fh+var_98]
0x180005f52  mov     [rsp+100h+var_B8], rdi; LPDWORD
0x180005f57  sbb     r12d, r12d
0x180005f5a  mov     [rsp+100h+var_C0], rax; __int64
0x180005f5f  neg     r12d
0x180005f62  mov     rax, [rbp+3Fh+var_70]
0x180005f66  add     r12d, 7
0x180005f6a  mov     [rsp+100h+var_C8], ebx; int
0x180005f6e  xor     r8d, r8d
0x180005f71  mov     [rsp+100h+var_D0], rax; __int64
0x180005f76  mov     al, [rbp+3Fh+var_A0]
0x180005f79  mov     dword ptr [rsp+100h+lpcbData], r12d; int
0x180005f7e  mov     byte ptr [rsp+100h+lpData], al; char
0x180005f82  call    UmpoReadFromSystemPowerKey
0x180005f87  mov     ebx, eax
0x180005f89  test    eax, eax
0x180005f8b  jz      loc_18000617D
0x180005f91  xor     ebx, ebx
0x180005f93  cmp     [rbp+3Fh+var_A0], bl
0x180005f96  jz      short loc_180005FA2
0x180005f98  mov     ebx, 2
0x180005f9d  jmp     loc_18000617D
0x180005fa2  lea     r8, [rbp+3Fh+Status]; Status
0x180005fa6  mov     rdx, r15; Uuid2
0x180005fa9  lea     rcx, GUID_POWERSCHEME_PERSONALITY; Uuid1
0x180005fb0  call    cs:__imp_UuidEqual
0x180005fb6  test    eax, eax
0x180005fb8  jnz     loc_18000605E
0x180005fbe  lea     rcx, [rbp+3Fh+var_78]
0x180005fc2  mov     dword ptr [rbp+3Fh+var_78], 10h
0x180005fc9  mov     [rsp+100h+var_C0], rcx
0x180005fce  lea     r8, NO_SUBGROUP_GUID
0x180005fd5  lea     rcx, [rbp+3Fh+var_60]
0x180005fd9  xorps   xmm0, xmm0
0x180005fdc  mov     qword ptr [rsp+100h+var_C8], rcx
0x180005fe1  test    r13d, r13d
0x180005fe4  mov     [rsp+100h+var_D0], rbx
0x180005fe9  mov     rdx, r14
0x180005fec  setz    al
0x180005fef  xor     r9d, r9d
0x180005ff2  mov     byte ptr [rsp+100h+lpcbData], al
0x180005ff6  xor     ecx, ecx
0x180005ff8  lea     rax, GUID_POWERSCHEME_PERSONALITY
0x180005fff  mov     [rsp+100h+lpData], rax
0x180006004  movups  xmmword ptr [rbp+3Fh+var_60], xmm0
0x180006008  call    UmpoInternalReadxCValue
0x18000600d  test    eax, eax
0x18000600f  jnz     short loc_18000605E
0x180006011  mov     eax, [rbp+3Fh+var_9C]
0x180006014  lea     rcx, [rbp+3Fh+var_60]; __int64
0x180006018  mov     rdx, [rbp+3Fh+Uuid1]; Uuid1
0x18000601c  mov     r9, r15
0x18000601f  mov     [rsp+100h+var_B0], rsi; __int64
0x180006024  xor     r8d, r8d
0x180006027  mov     [rsp+100h+var_B8], rdi; LPDWORD
0x18000602c  mov     [rdi], eax
0x18000602e  mov     rax, [rbp+3Fh+var_98]
0x180006032  mov     [rsp+100h+var_C0], rax; __int64
0x180006037  mov     rax, [rbp+3Fh+var_70]
0x18000603b  mov     [rsp+100h+var_C8], ebx; int
0x18000603f  mov     [rsp+100h+var_D0], rax; __int64
0x180006044  mov     dword ptr [rsp+100h+lpcbData], r12d; int
0x180006049  mov     byte ptr [rsp+100h+lpData], bl; char
0x18000604d  call    UmpoReadFromSystemPowerKey
0x180006052  mov     ebx, eax
0x180006054  test    eax, eax
0x180006056  jz      loc_18000617D
0x18000605c  xor     ebx, ebx
0x18000605e  mov     eax, [rbp+3Fh+var_9C]
0x180006061  lea     rcx, GUID_TYPICAL_POWER_SAVINGS
0x180006068  mov     [rsp+100h+var_B0], rsi
0x18000606d  mov     [rsp+100h+var_B8], rdi
0x180006072  mov     [rdi], eax
0x180006074  mov     rax, [rbp+3Fh+var_98]
0x180006078  mov     [rsp+100h+var_C0], rax
0x18000607d  mov     rax, [rbp+3Fh+var_70]
0x180006081  mov     [rsp+100h+var_C8], ebx
0x180006085  mov     [rsp+100h+var_D0], rax
0x18000608a  mov     dword ptr [rsp+100h+lpcbData], r12d
0x18000608f  mov     byte ptr [rsp+100h+lpData], bl
0x180006093  jmp     loc_18000616C
0x180006098  test    r14, r14
0x18000609b  jz      loc_180006135
0x1800060a1  test    r15, r15
0x1800060a4  jnz     loc_180006140
0x1800060aa  mov     rax, [rbp+3Fh+Uuid1]
0x1800060ae  test    rax, rax
0x1800060b1  jz      short loc_1800060CD
0x1800060b3  lea     r8, [rbp+3Fh+Status]; Status
0x1800060b7  mov     rcx, rax; Uuid1
0x1800060ba  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x1800060c1  call    cs:__imp_UuidEqual
0x1800060c7  xor     edx, edx
0x1800060c9  test    eax, eax
0x1800060cb  jz      short loc_180006140
0x1800060cd  mov     [rsp+100h+lpcbData], rdx; __int64
0x1800060d2  lea     r8, [rbp+3Fh+hKey]; phkResult
0x1800060d6  mov     rdx, r14; Uuid2
0x1800060d9  mov     byte ptr [rsp+100h+lpData], 1; char
0x1800060de  mov     r9d, 20019h; samDesired
0x1800060e4  mov     rcx, rbx; hKey
0x1800060e7  call    UmpoInternalOpenGUIDSubKey
0x1800060ec  mov     ebx, eax
0x1800060ee  test    eax, eax
0x1800060f0  jnz     loc_18000617D
0x1800060f6  mov     rbx, [rbp+3Fh+hKey]
0x1800060fa  mov     ecx, r13d
0x1800060fd  call    UmpoInternalDataAccessorToString
0x180006102  mov     rdx, rax; lpValueName
0x180006105  test    rax, rax
0x180006108  jnz     short loc_180006111
0x18000610a  mov     ebx, 57h ; 'W'
0x18000610f  jmp     short loc_18000617D
0x180006111  mov     eax, [rbp+3Fh+var_9C]
0x180006114  mov     r9, r12; lpType
0x180006117  mov     [rdi], eax
0x180006119  xor     r8d, r8d; lpReserved
0x18000611c  mov     rax, [rbp+3Fh+var_98]
0x180006120  mov     rcx, rbx; hKey
0x180006123  mov     [rsp+100h+lpcbData], rdi; lpcbData
0x180006128  mov     [rsp+100h+lpData], rax; lpData
0x18000612d  call    cs:__imp_RegQueryValueExW
0x180006133  jmp     short loc_18000617B
0x180006135  test    r15, r15
0x180006138  jnz     short loc_180006140
0x18000613a  cmp     [rbp+3Fh+Uuid1], rdx
  ... truncated ...
```
