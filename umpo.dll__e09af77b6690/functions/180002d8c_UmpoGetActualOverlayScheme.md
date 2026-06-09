# UmpoGetActualOverlayScheme

- ea: `0x180002d8c`
- end: `0x180002e7f`
- name: `UmpoGetActualOverlayScheme`
- size: `243`
- prototype: `__int64 __fastcall(UUID *Uuid, __int64)`
- caller_count: `10`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001580`
- `0x1800027d4`
- `0x180002bc0`
- `0x18000a990`
- `0x18000d7c0`
- `0x18000d9f0`
- `0x18000e6e4`
- `0x18000ebf0`
- `0x18001337c`

## callees

- `0x180002d8c`
- `0x180003270`
- `0x180003440`
- `0x180003560`
- `0x1800035c0`
- `0x18000f3dc`

## pseudocode

```c
__int64 __fastcall UmpoGetActualOverlayScheme(UUID *Uuid, __int64 a2)
{
  char v2; // bp
  HKEY v4; // rdi
  const WCHAR *v5; // rdx
  unsigned int KeyValueGuid; // ebx
  const WCHAR *v7; // rdx

  v2 = a2;
  if ( !Uuid )
  {
    v4 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
LABEL_13:
    KeyValueGuid = 87;
    goto LABEL_14;
  }
  AcquireUserPowerLockShared((__int64)Uuid, a2);
  v4 = UmpoUserPowerRootKey;
  if ( (unsigned __int64)UmpoUserPowerRootKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v4 = 0;
    MicrosoftTelemetryAssertTriggeredNoArgs();
    ReleaseUserPowerLock();
    goto LABEL_13;
  }
  v5 = L"ActiveOverlayAcPowerScheme";
  if ( !v2 )
    v5 = L"ActiveOverlayDcPowerScheme";
  KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoUserPowerRootKey, v5, Uuid);
  if ( KeyValueGuid == 2 )
  {
    KeyValueGuid = UmpoInternalGetKeyValueGuid(v4, L"ActiveOverlayPowerScheme", Uuid);
    if ( KeyValueGuid == 2 )
    {
      v7 = L"DefaultOverlayAcPowerScheme";
      if ( !v2 )
        v7 = L"DefaultOverlayDcPowerScheme";
      KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoPowerControlKey, v7, Uuid);
      if ( KeyValueGuid == 2 )
      {
        KeyValueGuid = UmpoInternalGetKeyValueGuid(UmpoPowerControlKey, L"DefaultOverlayPowerScheme", Uuid);
        if ( KeyValueGuid == 2 )
        {
          KeyValueGuid = 0;
          *Uuid = GUID_POWER_MODE_NONE;
        }
      }
    }
  }
LABEL_14:
  UmpoInternalCloseUserPowerKey(v4);
  return KeyValueGuid;
}

```

## disassembly

```asm
0x180002d8c  push    rbx
0x180002d8e  push    rbp
0x180002d8f  push    rsi
0x180002d90  push    rdi
0x180002d91  sub     rsp, 28h
0x180002d95  mov     bpl, dl
0x180002d98  mov     rsi, rcx
0x180002d9b  test    rcx, rcx
0x180002d9e  jz      loc_180002E55
0x180002da4  call    AcquireUserPowerLockShared
0x180002da9  mov     rdi, cs:UmpoUserPowerRootKey
0x180002db0  lea     rax, [rdi-1]
0x180002db4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002db8  ja      loc_180002E71
0x180002dbe  lea     rax, aActiveoverlayd; "ActiveOverlayDcPowerScheme"
0x180002dc5  test    bpl, bpl
0x180002dc8  lea     rdx, aActiveoverlaya; "ActiveOverlayAcPowerScheme"
0x180002dcf  mov     r8, rsi; Uuid
0x180002dd2  cmovz   rdx, rax; lpValueName
0x180002dd6  mov     rcx, rdi; hKey
0x180002dd9  call    UmpoInternalGetKeyValueGuid
0x180002dde  mov     ebx, eax
0x180002de0  cmp     eax, 2
0x180002de3  jnz     short loc_180002E5E
0x180002de5  mov     r8, rsi; Uuid
0x180002de8  lea     rdx, aActiveoverlayp; "ActiveOverlayPowerScheme"
0x180002def  mov     rcx, rdi; hKey
0x180002df2  call    UmpoInternalGetKeyValueGuid
0x180002df7  mov     ebx, eax
0x180002df9  cmp     eax, 2
0x180002dfc  jnz     short loc_180002E5E
0x180002dfe  mov     rcx, cs:UmpoPowerControlKey; hKey
0x180002e05  lea     rax, aDefaultoverlay_1; "DefaultOverlayDcPowerScheme"
0x180002e0c  test    bpl, bpl
0x180002e0f  lea     rdx, aDefaultoverlay; "DefaultOverlayAcPowerScheme"
0x180002e16  mov     r8, rsi; Uuid
0x180002e19  cmovz   rdx, rax; lpValueName
0x180002e1d  call    UmpoInternalGetKeyValueGuid
0x180002e22  mov     ebx, eax
0x180002e24  cmp     eax, 2
0x180002e27  jnz     short loc_180002E5E
0x180002e29  mov     rcx, cs:UmpoPowerControlKey; hKey
0x180002e30  lea     rdx, aDefaultoverlay_0; "DefaultOverlayPowerScheme"
0x180002e37  mov     r8, rsi; Uuid
0x180002e3a  call    UmpoInternalGetKeyValueGuid
0x180002e3f  mov     ebx, eax
0x180002e41  cmp     eax, 2
0x180002e44  jnz     short loc_180002E5E
0x180002e46  movups  xmm0, xmmword ptr cs:GUID_POWER_MODE_NONE.Data1
0x180002e4d  xor     ebx, ebx
0x180002e4f  movdqu  xmmword ptr [rsi], xmm0
0x180002e53  jmp     short loc_180002E5E
0x180002e55  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002e59  mov     ebx, 57h ; 'W'
0x180002e5e  mov     rcx, rdi
0x180002e61  call    UmpoInternalCloseUserPowerKey
0x180002e66  mov     eax, ebx
0x180002e68  add     rsp, 28h
0x180002e6c  pop     rdi
0x180002e6d  pop     rsi
0x180002e6e  pop     rbp
0x180002e6f  pop     rbx
0x180002e70  retn
0x180002e71  xor     edi, edi
0x180002e73  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180002e78  call    ReleaseUserPowerLock
0x180002e7d  jmp     short loc_180002E59
```
