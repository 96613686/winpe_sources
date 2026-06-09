# UmpoInternalRemoveSetting

- ea: `0x180013808`
- end: `0x180013932`
- name: `UmpoInternalRemoveSetting`
- size: `298`
- prototype: `__int64 __fastcall(UUID *Uuid2, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014d30`

## callees

- `0x180005480`
- `0x18000e030`
- `0x180010070`
- `0x180012864`
- `0x180013808`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800138d5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800138d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800138fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800138fe`
- `RPCRT4!UuidEqual` at `0x18001387b`
- `RPCRT4!UuidEqual` at `0x18001387b`

## pseudocode

```c
__int64 __fastcall UmpoInternalRemoveSetting(UUID *Uuid2, __int64 a2)
{
  unsigned int v4; // ebx
  HKEY v5; // rbx
  int v6; // edi
  HKEY hKey; // [rsp+30h] [rbp-78h] BYREF
  RPC_STATUS Status; // [rsp+38h] [rbp-70h] BYREF
  WCHAR SubKey[40]; // [rsp+40h] [rbp-68h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Status = 0;
  if ( UmpoFullPowerPlanSupportDisabled )
  {
    return 50;
  }
  else
  {
    if ( !Uuid2 || !a2 )
      return 87;
    v5 = UmpoSystemPowerRootKey;
    if ( UuidEqual(Uuid2, (UUID *)&NO_SUBGROUP_GUID, &Status) )
    {
      v6 = 0;
      hKey = v5;
    }
    else
    {
      v4 = UmpoInternalOpenGUIDSubKey(v5, Uuid2, &hKey, 0x20006u, 1, 0);
      if ( v4 )
        return v4;
      v5 = hKey;
      v6 = 1;
    }
    UmpoInternalConvertGuidToStringBuffer(a2, SubKey);
    v4 = RegDeleteTreeW(v5, SubKey);
    UmpoInternalClearPowerSubkeyCache((__int64)&UmpoPowerSettingCache);
    if ( v6 == 1 && hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL && hKey )
      RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180013808  mov     [rsp+arg_10], rbx
0x18001380d  mov     [rsp+arg_18], rsi
0x180013812  push    rdi
0x180013813  sub     rsp, 0A0h
0x18001381a  mov     rax, cs:__security_cookie
0x180013821  xor     rax, rsp
0x180013824  mov     [rsp+0A8h+var_18], rax
0x18001382c  cmp     cs:UmpoFullPowerPlanSupportDisabled, 0
0x180013833  mov     rsi, rdx
0x180013836  mov     rdi, rcx
0x180013839  mov     [rsp+0A8h+hKey], 0FFFFFFFFFFFFFFFFh
0x180013842  mov     [rsp+0A8h+Status], 0
0x18001384a  jz      short loc_180013856
0x18001384c  mov     ebx, 32h ; '2'
0x180013851  jmp     loc_18001390B
0x180013856  test    rdi, rdi
0x180013859  jz      loc_180013906
0x18001385f  test    rsi, rsi
0x180013862  jz      loc_180013906
0x180013868  mov     rbx, cs:UmpoSystemPowerRootKey
0x18001386f  lea     r8, [rsp+0A8h+Status]; Status
0x180013874  lea     rdx, NO_SUBGROUP_GUID; Uuid2
0x18001387b  call    cs:__imp_UuidEqual
0x180013881  test    eax, eax
0x180013883  jz      short loc_18001388E
0x180013885  xor     edi, edi
0x180013887  mov     [rsp+0A8h+hKey], rbx
0x18001388c  jmp     short loc_1800138C0
0x18001388e  mov     [rsp+0A8h+var_80], 0; __int64
0x180013897  lea     r8, [rsp+0A8h+hKey]; phkResult
0x18001389c  mov     r9d, 20006h; samDesired
0x1800138a2  mov     [rsp+0A8h+var_88], 1; char
0x1800138a7  mov     rdx, rdi; Uuid2
0x1800138aa  mov     rcx, rbx; hKey
0x1800138ad  call    UmpoInternalOpenGUIDSubKey
0x1800138b2  mov     ebx, eax
0x1800138b4  test    eax, eax
0x1800138b6  jnz     short loc_18001390B
0x1800138b8  mov     rbx, [rsp+0A8h+hKey]
0x1800138bd  lea     edi, [rax+1]
0x1800138c0  lea     rdx, [rsp+0A8h+SubKey]
0x1800138c5  mov     rcx, rsi
0x1800138c8  call    UmpoInternalConvertGuidToStringBuffer
0x1800138cd  mov     rcx, rbx; hKey
0x1800138d0  lea     rdx, [rsp+0A8h+SubKey]; lpSubKey
0x1800138d5  call    cs:__imp_RegDeleteTreeW
0x1800138db  lea     rcx, UmpoPowerSettingCache
0x1800138e2  mov     ebx, eax
0x1800138e4  call    UmpoInternalClearPowerSubkeyCache
0x1800138e9  cmp     edi, 1
0x1800138ec  jnz     short loc_18001390B
0x1800138ee  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800138f3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800138f7  jz      short loc_18001390B
0x1800138f9  test    rcx, rcx
0x1800138fc  jz      short loc_18001390B
0x1800138fe  call    cs:__imp_RegCloseKey
0x180013904  jmp     short loc_18001390B
0x180013906  mov     ebx, 57h ; 'W'
0x18001390b  mov     eax, ebx
0x18001390d  mov     rcx, [rsp+0A8h+var_18]
0x180013915  xor     rcx, rsp; StackCookie
0x180013918  call    __security_check_cookie
0x18001391d  lea     r11, [rsp+0A8h+var_8]
0x180013925  mov     rbx, [r11+20h]
0x180013929  mov     rsi, [r11+28h]
0x18001392d  mov     rsp, r11
0x180013930  pop     rdi
0x180013931  retn
```
