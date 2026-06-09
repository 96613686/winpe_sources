# UmpoSetActiveOverlayScheme

- ea: `0x180014300`
- end: `0x180014439`
- name: `UmpoSetActiveOverlayScheme`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD *, char, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d9f0`

## callees

- `0x180003370`
- `0x180003560`
- `0x18000b540`
- `0x180010070`
- `0x180012864`
- `0x180014300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800143e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800143e9`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800143ff`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800143ff`

## pseudocode

```c
__int64 __fastcall UmpoSetActiveOverlayScheme(_QWORD *a1, char a2, char a3)
{
  __int64 v3; // rdi
  __int64 v6; // r11
  unsigned int v7; // ebx
  const WCHAR *v8; // rdx
  _BYTE v10[8]; // [rsp+30h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-80h] BYREF
  _WORD Data[40]; // [rsp+40h] [rbp-78h] BYREF

  v3 = -1;
  v10[0] = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = (__int64)a1;
  if ( a1
    && (*(_QWORD *)&GUID_POWER_MODE_NONE.Data1 == *a1 && *(_QWORD *)GUID_POWER_MODE_NONE.Data4 == a1[1]
     || (UmpoInternalIsOverlayPowerScheme(a1, v10), v10[0])) )
  {
    UmpoInternalConvertGuidToStringBuffer(v6, Data);
    v7 = UmpoInternalOpenUserPowerKey(&hKey, 131079, 1);
    if ( !v7 )
    {
      v8 = L"ActiveOverlayAcPowerScheme";
      if ( !a3 )
        v8 = L"ActiveOverlayDcPowerScheme";
      do
        ++v3;
      while ( Data[v3] );
      v7 = RegSetValueExW(hKey, v8, 0, 1u, (const BYTE *)Data, 2 * v3 + 2);
      if ( !v7 && a2 )
        RegFlushKey(hKey);
    }
  }
  else
  {
    v7 = 87;
  }
  UmpoInternalCloseUserPowerKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180014300  mov     [rsp+arg_8], rbx
0x180014305  mov     [rsp+arg_10], rbp
0x18001430a  push    rsi
0x18001430b  push    rdi
0x18001430c  push    r14
0x18001430e  sub     rsp, 0A0h
0x180014315  mov     rax, cs:__security_cookie
0x18001431c  xor     rax, rsp
0x18001431f  mov     [rsp+0B8h+var_28], rax
0x180014327  xor     r14d, r14d
0x18001432a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001432e  mov     [rsp+0B8h+var_88], r14b
0x180014333  mov     bpl, r8b
0x180014336  mov     [rsp+0B8h+hKey], rdi
0x18001433b  mov     sil, dl
0x18001433e  mov     r11, rcx
0x180014341  test    rcx, rcx
0x180014344  jnz     short loc_180014350
0x180014346  mov     ebx, 57h ; 'W'
0x18001434b  jmp     loc_180014405
0x180014350  mov     rax, qword ptr cs:GUID_POWER_MODE_NONE.Data1
0x180014357  cmp     rax, [rcx]
0x18001435a  jnz     short loc_180014369
0x18001435c  mov     rax, qword ptr cs:GUID_POWER_MODE_NONE.Data4
0x180014363  cmp     rax, [rcx+8]
0x180014367  jz      short loc_18001437A
0x180014369  lea     rdx, [rsp+0B8h+var_88]
0x18001436e  call    UmpoInternalIsOverlayPowerScheme
0x180014373  cmp     [rsp+0B8h+var_88], r14b
0x180014378  jz      short loc_180014346
0x18001437a  lea     rdx, [rsp+0B8h+Data]
0x18001437f  mov     rcx, r11
0x180014382  call    UmpoInternalConvertGuidToStringBuffer
0x180014387  mov     r8d, 1
0x18001438d  lea     rcx, [rsp+0B8h+hKey]; phkResult
0x180014392  mov     edx, 20007h; samDesired
0x180014397  call    UmpoInternalOpenUserPowerKey
0x18001439c  mov     ebx, eax
0x18001439e  test    eax, eax
0x1800143a0  jnz     short loc_180014405
0x1800143a2  lea     rax, aActiveoverlayd; "ActiveOverlayDcPowerScheme"
0x1800143a9  test    bpl, bpl
0x1800143ac  lea     rdx, aActiveoverlaya; "ActiveOverlayAcPowerScheme"
0x1800143b3  cmovz   rdx, rax; lpValueName
0x1800143b7  lea     rax, [rsp+0B8h+Data]
0x1800143bc  inc     rdi
0x1800143bf  cmp     [rax+rdi*2], r14w
0x1800143c4  jnz     short loc_1800143BC
0x1800143c6  mov     rcx, [rsp+0B8h+hKey]; hKey
0x1800143cb  lea     eax, ds:2[rdi*2]
0x1800143d2  mov     [rsp+0B8h+cbData], eax; cbData
0x1800143d6  mov     r9d, 1; dwType
0x1800143dc  lea     rax, [rsp+0B8h+Data]
0x1800143e1  xor     r8d, r8d; Reserved
0x1800143e4  mov     [rsp+0B8h+lpData], rax; lpData
0x1800143e9  call    cs:__imp_RegSetValueExW
0x1800143ef  mov     ebx, eax
0x1800143f1  test    eax, eax
0x1800143f3  jnz     short loc_180014405
0x1800143f5  test    sil, sil
0x1800143f8  jz      short loc_180014405
0x1800143fa  mov     rcx, [rsp+0B8h+hKey]; hKey
0x1800143ff  call    cs:__imp_RegFlushKey
0x180014405  mov     rcx, [rsp+0B8h+hKey]
0x18001440a  call    UmpoInternalCloseUserPowerKey
0x18001440f  mov     eax, ebx
0x180014411  mov     rcx, [rsp+0B8h+var_28]
0x180014419  xor     rcx, rsp; StackCookie
0x18001441c  call    __security_check_cookie
0x180014421  lea     r11, [rsp+0B8h+var_18]
0x180014429  mov     rbx, [r11+28h]
0x18001442d  mov     rbp, [r11+30h]
0x180014431  mov     rsp, r11
0x180014434  pop     r14
0x180014436  pop     rdi
0x180014437  pop     rsi
0x180014438  retn
```
