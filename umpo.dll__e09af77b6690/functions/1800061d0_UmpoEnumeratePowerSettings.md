# UmpoEnumeratePowerSettings

- ea: `0x1800061d0`
- end: `0x180006565`
- name: `UmpoEnumeratePowerSettings`
- size: `917`
- prototype: `__int64 __fastcall(UUID *, __int64 (__fastcall *)(UUID *, UUID *, __int64), __int64)`
- caller_count: `8`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800012a0`
- `0x180002420`
- `0x1800027d4`
- `0x180002bc0`
- `0x1800061d0`
- `0x180008c80`
- `0x18000eca0`
- `0x18000f61c`

## callees

- `0x180005480`
- `0x1800061d0`
- `0x1800066b0`
- `0x18000681c`
- `0x180007f70`
- `0x18000f3dc`
- `0x180010070`
- `0x180010946`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800062db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180006507`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800062db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180006507`
- `RPCRT4!UuidFromStringW` at `0x1800062f1`
- `RPCRT4!UuidFromStringW` at `0x18000651d`
- `RPCRT4!UuidFromStringW` at `0x1800062f1`
- `RPCRT4!UuidFromStringW` at `0x18000651d`
- `RPCRT4!UuidEqual` at `0x18000625b`
- `RPCRT4!UuidEqual` at `0x18000625b`

## pseudocode

```c
__int64 __fastcall UmpoEnumeratePowerSettings(UUID *a1, __int64 (__fastcall *a2)(UUID *, UUID *, __int64), __int64 a3)
{
  HKEY v3; // r14
  DWORD i; // ebx
  int v8; // eax
  unsigned int v9; // edi
  int v11; // eax
  DWORD j; // ebx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v14; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v15[2]; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  RPC_STATUS Status; // [rsp+78h] [rbp-88h] BYREF
  UUID Uuid; // [rsp+80h] [rbp-80h] BYREF
  UUID v19; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[64]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = UmpoSystemPowerRootKey;
  Status = 0;
  cchName = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Uuid = 0;
  v19 = 0;
  if ( UmpoSystemPowerRootKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a1 )
  {
    if ( UuidEqual(a1, (UUID *)&NO_SUBGROUP_GUID, &Status) )
      goto LABEL_7;
    if ( !(unsigned int)UmpoInternalOpenGUIDSubKey(v3, a1, &phkResult, 0x20019u, 1, (__int64)&UmpoPowerSubGroupCache) )
    {
      v3 = phkResult;
LABEL_7:
      for ( i = 0; ; ++i )
      {
        memset_0(Name, 0, sizeof(Name));
        cchName = 64;
        if ( RegEnumKeyExW(v3, i, Name, &cchName, 0, 0, 0, 0) )
          break;
        if ( !UuidFromStringW(Name, &Uuid) )
        {
          if ( (v15[1] = 0,
                v15[0] = 0,
                v14 = 4,
                !(unsigned int)UmpoReadFromSystemPowerKey(0, a1, 0, 9, 0, 0, (__int64)v15, &v14, 0))
            && (v15[0] = 0, v14 = 4,
                            !(unsigned int)UmpoReadFromSystemPowerKey(0, a1, 0, 10, 0, 0, (__int64)v15, &v14, 0))
            || (v8 = UmpoReadFromSystemPowerKey(0, a1, 0, 4, 0, 0, 0, &v15[1], 0), v8 == 234)
            || !v8
            || (v11 = UmpoReadFromSystemPowerKey((__int64)&GUID_TYPICAL_POWER_SAVINGS, a1, 0, 7, 0, 0, 0, &v15[1], 0),
                v11 == 234)
            || !v11 )
          {
            v9 = a2(a1, &Uuid, a3);
            if ( v9 )
              goto LABEL_16;
          }
        }
      }
    }
  }
  else
  {
    v9 = UmpoEnumeratePowerSettings(&NO_SUBGROUP_GUID, a2, a3);
    if ( v9 )
      goto LABEL_16;
    for ( j = 0; ; ++j )
    {
      phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      memset_0(Name, 0, sizeof(Name));
      cchName = 64;
      if ( RegEnumKeyExW(v3, j, Name, &cchName, 0, 0, 0, 0) )
        break;
      if ( !UuidFromStringW(Name, &v19) && !(unsigned __int8)UmpoInternalIsSinglePowerSetting((UUID *)&NO_SUBGROUP_GUID) )
      {
        v9 = UmpoEnumeratePowerSettings(&v19, a2, a3);
        if ( v9 )
          goto LABEL_16;
      }
    }
  }
  v9 = 0;
LABEL_16:
  UmpoInternalRegCloseKey(&UmpoPowerSubGroupCache, phkResult);
  return v9;
}

```

## disassembly

```asm
0x1800061d0  push    rbp
0x1800061d2  push    rsi
0x1800061d3  push    rdi
0x1800061d4  push    r12
0x1800061d6  push    r13
0x1800061d8  push    r14
0x1800061da  push    r15
0x1800061dc  lea     rbp, [rsp-30h]
0x1800061e1  sub     rsp, 130h
0x1800061e8  mov     rax, cs:__security_cookie
0x1800061ef  xor     rax, rsp
0x1800061f2  mov     [rbp+60h+var_40], rax
0x1800061f6  mov     r14, cs:UmpoSystemPowerRootKey
0x1800061fd  xor     r13d, r13d
0x180006200  mov     [rsp+160h+Status], r13d
0x180006205  xorps   xmm0, xmm0
0x180006208  mov     [rsp+160h+cchName], r13d
0x18000620d  xorps   xmm1, xmm1
0x180006210  mov     [rsp+160h+phkResult], 0FFFFFFFFFFFFFFFFh
0x180006219  mov     r12, r8
0x18000621c  mov     r15, rdx
0x18000621f  mov     rsi, rcx
0x180006222  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x180006226  movups  xmmword ptr [rbp+60h+var_D0.Data1], xmm1
0x18000622a  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000622e  jz      loc_18000655B
0x180006234  mov     [rsp+160h+arg_18], rbx
0x18000623c  lea     rdi, UmpoPowerSubGroupCache
0x180006243  test    rsi, rsi
0x180006246  jz      loc_1800064A4
0x18000624c  lea     r8, [rsp+160h+Status]; Status
0x180006251  mov     rcx, rsi; Uuid1
0x180006254  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x18000625b  call    cs:__imp_UuidEqual
0x180006261  test    eax, eax
0x180006263  jnz     short loc_180006292
0x180006265  mov     [rsp+160h+lpClass], rdi; __int64
0x18000626a  lea     r8, [rsp+160h+phkResult]; phkResult
0x18000626f  mov     r9d, 20019h; samDesired
0x180006275  mov     byte ptr [rsp+160h+lpReserved], 1; char
0x18000627a  mov     rdx, rsi; Uuid2
0x18000627d  mov     rcx, r14; hKey
0x180006280  call    UmpoInternalOpenGUIDSubKey
0x180006285  test    eax, eax
0x180006287  jnz     loc_18000640A
0x18000628d  mov     r14, [rsp+160h+phkResult]
0x180006292  mov     ebx, r13d
0x180006295  nop     word ptr [rax+rax+00000000h]
0x1800062a0  xor     edx, edx; Val
0x1800062a2  lea     rcx, [rbp+60h+Name]; void *
0x1800062a6  mov     r8d, 80h; Size
0x1800062ac  call    memset_0
0x1800062b1  mov     [rsp+160h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800062b6  lea     r9, [rsp+160h+cchName]; lpcchName
0x1800062bb  mov     [rsp+160h+lpcchClass], r13; lpcchClass
0x1800062c0  lea     r8, [rbp+60h+Name]; lpName
0x1800062c4  mov     [rsp+160h+lpClass], r13; lpClass
0x1800062c9  mov     edx, ebx; dwIndex
0x1800062cb  mov     rcx, r14; hKey
0x1800062ce  mov     [rsp+160h+lpReserved], r13; lpReserved
0x1800062d3  mov     [rsp+160h+cchName], 40h ; '@'
0x1800062db  call    cs:__imp_RegEnumKeyExW
0x1800062e1  test    eax, eax
0x1800062e3  jnz     loc_18000640A
0x1800062e9  lea     rdx, [rbp+60h+Uuid]; Uuid
0x1800062ed  lea     rcx, [rbp+60h+Name]; StringUuid
0x1800062f1  call    cs:__imp_UuidFromStringW
0x1800062f7  test    eax, eax
0x1800062f9  jnz     loc_180006403
0x1800062ff  mov     [rsp+160h+var_110], r13; __int64
0x180006304  lea     rax, [rsp+160h+var_FC]
0x180006309  mov     [rsp+160h+var_118], rax; LPDWORD
0x18000630e  lea     r9, [rbp+60h+Uuid]
0x180006312  lea     rax, [rsp+160h+var_F8]
0x180006317  mov     [rsp+160h+var_F8+4], r13d
0x18000631c  mov     [rsp+160h+var_120], rax; __int64
0x180006321  xor     r8d, r8d
0x180006324  mov     dword ptr [rsp+160h+lpftLastWriteTime], r13d; int
0x180006329  mov     rdx, rsi; Uuid1
0x18000632c  mov     [rsp+160h+lpcchClass], r13; __int64
0x180006331  xor     ecx, ecx; __int64
0x180006333  mov     dword ptr [rsp+160h+lpClass], 9; int
0x18000633b  mov     byte ptr [rsp+160h+lpReserved], r13b; char
0x180006340  mov     [rsp+160h+var_F8], r13d
0x180006345  mov     [rsp+160h+var_FC], 4
0x18000634d  call    UmpoReadFromSystemPowerKey
0x180006352  test    eax, eax
0x180006354  jnz     short loc_1800063A8
0x180006356  mov     [rsp+160h+var_110], r13; __int64
0x18000635b  lea     rax, [rsp+160h+var_FC]
0x180006360  mov     [rsp+160h+var_118], rax; LPDWORD
0x180006365  lea     r9, [rbp+60h+Uuid]
0x180006369  lea     rax, [rsp+160h+var_F8]
0x18000636e  mov     [rsp+160h+var_F8], r13d
0x180006373  mov     [rsp+160h+var_120], rax; __int64
0x180006378  xor     r8d, r8d
0x18000637b  mov     dword ptr [rsp+160h+lpftLastWriteTime], r13d; int
0x180006380  mov     rdx, rsi; Uuid1
0x180006383  mov     [rsp+160h+lpcchClass], r13; __int64
0x180006388  xor     ecx, ecx; __int64
0x18000638a  mov     dword ptr [rsp+160h+lpClass], 0Ah; int
0x180006392  mov     byte ptr [rsp+160h+lpReserved], r13b; char
0x180006397  mov     [rsp+160h+var_FC], 4
0x18000639f  call    UmpoReadFromSystemPowerKey
0x1800063a4  test    eax, eax
0x1800063a6  jz      short loc_1800063EB
0x1800063a8  mov     [rsp+160h+var_110], r13; __int64
0x1800063ad  lea     rax, [rsp+160h+var_F8+4]
0x1800063b2  mov     [rsp+160h+var_118], rax; LPDWORD
0x1800063b7  lea     r9, [rbp+60h+Uuid]
0x1800063bb  mov     [rsp+160h+var_120], r13; __int64
0x1800063c0  xor     r8d, r8d
0x1800063c3  mov     dword ptr [rsp+160h+lpftLastWriteTime], r13d; int
0x1800063c8  mov     rdx, rsi; Uuid1
0x1800063cb  mov     [rsp+160h+lpcchClass], r13; __int64
0x1800063d0  xor     ecx, ecx; __int64
0x1800063d2  mov     dword ptr [rsp+160h+lpClass], 4; int
0x1800063da  mov     byte ptr [rsp+160h+lpReserved], r13b; char
0x1800063df  call    UmpoReadFromSystemPowerKey
0x1800063e4  cmp     eax, 0EAh
0x1800063e9  jnz     short loc_180006447
0x1800063eb  mov     r8, r12
0x1800063ee  lea     rdx, [rbp+60h+Uuid]
0x1800063f2  mov     rcx, rsi
0x1800063f5  mov     rax, r15
0x1800063f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063fd  mov     edi, eax
0x1800063ff  test    eax, eax
0x180006401  jnz     short loc_18000640D
0x180006403  inc     ebx
0x180006405  jmp     loc_1800062A0
0x18000640a  mov     edi, r13d
0x18000640d  mov     rdx, [rsp+160h+phkResult]
0x180006412  lea     rcx, UmpoPowerSubGroupCache
0x180006419  call    UmpoInternalRegCloseKey
0x18000641e  mov     rbx, [rsp+160h+arg_18]
0x180006426  mov     eax, edi
0x180006428  mov     rcx, [rbp+60h+var_40]
0x18000642c  xor     rcx, rsp; StackCookie
0x18000642f  call    __security_check_cookie
0x180006434  add     rsp, 130h
0x18000643b  pop     r15
0x18000643d  pop     r14
0x18000643f  pop     r13
0x180006441  pop     r12
0x180006443  pop     rdi
0x180006444  pop     rsi
0x180006445  pop     rbp
0x180006446  retn
0x180006447  test    eax, eax
0x180006449  jz      short loc_1800063EB
0x18000644b  mov     [rsp+160h+var_110], r13; __int64
0x180006450  lea     rax, [rsp+160h+var_F8+4]
0x180006455  mov     [rsp+160h+var_118], rax; LPDWORD
0x18000645a  lea     r9, [rbp+60h+Uuid]
0x18000645e  mov     [rsp+160h+var_120], r13; __int64
0x180006463  lea     rcx, GUID_TYPICAL_POWER_SAVINGS; __int64
0x18000646a  mov     dword ptr [rsp+160h+lpftLastWriteTime], r13d; int
0x18000646f  xor     r8d, r8d
0x180006472  mov     [rsp+160h+lpcchClass], r13; __int64
0x180006477  mov     rdx, rsi; Uuid1
0x18000647a  mov     dword ptr [rsp+160h+lpClass], 7; int
0x180006482  mov     byte ptr [rsp+160h+lpReserved], r13b; char
0x180006487  call    UmpoReadFromSystemPowerKey
0x18000648c  cmp     eax, 0EAh
0x180006491  jz      loc_1800063EB
0x180006497  test    eax, eax
0x180006499  jnz     loc_180006403
0x18000649f  jmp     loc_1800063EB
0x1800064a4  mov     r8, r12
0x1800064a7  lea     rcx, NO_SUBGROUP_GUID
0x1800064ae  mov     rdx, r15
0x1800064b1  call    UmpoEnumeratePowerSettings
0x1800064b6  mov     edi, eax
0x1800064b8  test    eax, eax
0x1800064ba  jnz     loc_18000640D
0x1800064c0  mov     ebx, r13d
0x1800064c3  xor     edx, edx; Val
0x1800064c5  mov     [rsp+160h+phkResult], 0FFFFFFFFFFFFFFFFh
0x1800064ce  mov     r8d, 80h; Size
0x1800064d4  lea     rcx, [rbp+60h+Name]; void *
0x1800064d8  call    memset_0
0x1800064dd  mov     [rsp+160h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800064e2  lea     r9, [rsp+160h+cchName]; lpcchName
0x1800064e7  mov     [rsp+160h+lpcchClass], r13; lpcchClass
0x1800064ec  lea     r8, [rbp+60h+Name]; lpName
0x1800064f0  mov     [rsp+160h+lpClass], r13; lpClass
0x1800064f5  mov     edx, ebx; dwIndex
0x1800064f7  mov     rcx, r14; hKey
0x1800064fa  mov     [rsp+160h+lpReserved], r13; lpReserved
0x1800064ff  mov     [rsp+160h+cchName], 40h ; '@'
0x180006507  call    cs:__imp_RegEnumKeyExW
0x18000650d  test    eax, eax
0x18000650f  jnz     loc_18000640A
0x180006515  lea     rdx, [rbp+60h+var_D0]; Uuid
0x180006519  lea     rcx, [rbp+60h+Name]; StringUuid
0x18000651d  call    cs:__imp_UuidFromStringW
0x180006523  test    eax, eax
0x180006525  jnz     short loc_180006554
0x180006527  lea     rdx, [rbp+60h+var_D0]
0x18000652b  lea     rcx, NO_SUBGROUP_GUID
0x180006532  call    UmpoInternalIsSinglePowerSetting
0x180006537  test    al, al
0x180006539  jnz     short loc_180006554
0x18000653b  mov     r8, r12
0x18000653e  lea     rcx, [rbp+60h+var_D0]
0x180006542  mov     rdx, r15
0x180006545  call    UmpoEnumeratePowerSettings
0x18000654a  mov     edi, eax
0x18000654c  test    eax, eax
0x18000654e  jnz     loc_18000640D
0x180006554  inc     ebx
0x180006556  jmp     loc_1800064C3
0x18000655b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006560  jmp     loc_180006234
```
