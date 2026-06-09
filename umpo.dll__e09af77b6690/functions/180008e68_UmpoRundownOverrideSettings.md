# UmpoRundownOverrideSettings

- ea: `0x180008e68`
- end: `0x180008fe0`
- name: `UmpoRundownOverrideSettings`
- size: `376`
- prototype: `void __fastcall(char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008c80`
- `0x18000e360`

## callees

- `0x180008e68`
- `0x18000f3dc`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180008eaa`
- `ntdll!EtwEventEnabled` at `0x180008eaa`
- `ntdll!EtwEventWrite` at `0x180008f8d`
- `ntdll!EtwEventWrite` at `0x180008f8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008fb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008fb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ecc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008ecc`

## pseudocode

```c
void __fastcall UmpoRundownOverrideSettings(char a1)
{
  __int64 *v1; // rbx
  unsigned int i; // edi
  char *v3; // rdx
  int v4; // ecx
  int v5; // [rsp+20h] [rbp-69h] BYREF
  _QWORD v6[13]; // [rsp+30h] [rbp-59h] BYREF
  int v7; // [rsp+98h] [rbp+Fh]
  int v8; // [rsp+9Ch] [rbp+13h]
  char *v9; // [rsp+A0h] [rbp+17h]
  __int64 v10; // [rsp+A8h] [rbp+1Fh]

  v5 = 0;
  v1 = UMPO_EVT_RUNDOWN_OVERRIDE_POWER_SETTING;
  if ( !a1 )
    v1 = UMPO_EVT_OVERRIDE_DLL_POWER_SETTING;
  if ( (unsigned __int8)EtwEventEnabled(UmpoProviderHandle, v1) )
  {
    if ( byte_1800248C8 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    EnterCriticalSection(&UmpoPowerSettingOverrideLock);
    for ( i = 0; i < UmpoPowerSettingOverrideCount; ++i )
    {
      v5 = 0;
      v3 = (char *)UmpoPowerSettingOverride + 88 * i;
      if ( v3[64] )
        v5 = 2;
      v6[0] = (char *)UmpoPowerSettingOverride + 88 * i;
      v6[10] = v3 + 72;
      v6[2] = v3 + 16;
      v6[1] = 16;
      v6[4] = v3 + 48;
      v6[3] = 16;
      v6[6] = &v5;
      v6[8] = v3 + 68;
      v6[5] = 16;
      v6[7] = 4;
      v6[9] = 4;
      v6[11] = 4;
      v4 = *((_DWORD *)v3 + 18);
      v6[12] = *((_QWORD *)v3 + 10);
      v7 = v4;
      v9 = v3 + 32;
      v8 = 0;
      v10 = 16;
      EtwEventWrite(UmpoProviderHandle, v1, 8, v6);
    }
    if ( byte_1800248C8 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    LeaveCriticalSection(&UmpoPowerSettingOverrideLock);
  }
}

```

## disassembly

```asm
0x180008e68  push    rbp
0x180008e6a  push    rbx
0x180008e6b  push    rsi
0x180008e6c  push    rdi
0x180008e6d  lea     rbp, [rsp-3Fh]
0x180008e72  sub     rsp, 0C8h
0x180008e79  mov     rax, cs:__security_cookie
0x180008e80  xor     rax, rsp
0x180008e83  mov     [rbp+57h+var_30], rax
0x180008e87  xor     esi, esi
0x180008e89  lea     rax, UMPO_EVT_OVERRIDE_DLL_POWER_SETTING
0x180008e90  test    cl, cl
0x180008e92  mov     [rbp+57h+var_C0], esi
0x180008e95  mov     rcx, cs:UmpoProviderHandle
0x180008e9c  lea     rbx, UMPO_EVT_RUNDOWN_OVERRIDE_POWER_SETTING
0x180008ea3  cmovz   rbx, rax
0x180008ea7  mov     rdx, rbx
0x180008eaa  call    cs:__imp_EtwEventEnabled
0x180008eb0  test    al, al
0x180008eb2  jz      loc_180008FB7
0x180008eb8  cmp     cs:byte_1800248C8, 1
0x180008ebf  jnz     loc_180008FD6
0x180008ec5  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x180008ecc  call    cs:__imp_EnterCriticalSection
0x180008ed2  cmp     cs:UmpoPowerSettingOverrideCount, esi
0x180008ed8  mov     edi, esi
0x180008eda  jbe     loc_180008FA1
0x180008ee0  mov     eax, edi
0x180008ee2  imul    rdx, rax, 58h ; 'X'
0x180008ee6  mov     [rbp+57h+var_C0], esi
0x180008ee9  add     rdx, cs:UmpoPowerSettingOverride
0x180008ef0  cmp     [rdx+40h], sil
0x180008ef4  jz      short loc_180008EFD
0x180008ef6  mov     [rbp+57h+var_C0], 2
0x180008efd  lea     rcx, [rdx+48h]
0x180008f01  mov     [rbp+57h+var_B0], rdx
0x180008f05  lea     rax, [rdx+10h]
0x180008f09  mov     [rbp+57h+var_60], rcx
0x180008f0d  mov     [rbp+57h+var_A0], rax
0x180008f11  lea     r9, [rbp+57h+var_B0]
0x180008f15  lea     rax, [rdx+30h]
0x180008f19  mov     [rbp+57h+var_A8], 10h
0x180008f21  mov     [rbp+57h+var_90], rax
0x180008f25  mov     r8d, 8
0x180008f2b  mov     [rbp+57h+var_98], 10h
0x180008f33  lea     rax, [rbp+57h+var_C0]
0x180008f37  mov     [rbp+57h+var_80], rax
0x180008f3b  lea     rax, [rdx+44h]
0x180008f3f  mov     [rbp+57h+var_70], rax
0x180008f43  mov     [rbp+57h+var_88], 10h
0x180008f4b  mov     [rbp+57h+var_78], 4
0x180008f53  mov     [rbp+57h+var_68], 4
0x180008f5b  mov     [rbp+57h+var_58], 4
0x180008f63  mov     rax, [rdx+50h]
0x180008f67  mov     ecx, [rcx]
0x180008f69  mov     [rbp+57h+var_50], rax
0x180008f6d  lea     rax, [rdx+20h]
0x180008f71  mov     [rbp+57h+var_48], ecx
0x180008f74  mov     rdx, rbx
0x180008f77  mov     rcx, cs:UmpoProviderHandle
0x180008f7e  mov     [rbp+57h+var_40], rax
0x180008f82  mov     [rbp+57h+var_44], esi
0x180008f85  mov     [rbp+57h+var_38], 10h
0x180008f8d  call    cs:__imp_EtwEventWrite
0x180008f93  inc     edi
0x180008f95  cmp     edi, cs:UmpoPowerSettingOverrideCount
0x180008f9b  jb      loc_180008EE0
0x180008fa1  cmp     cs:byte_1800248C8, 1
0x180008fa8  jnz     short loc_180008FCF
0x180008faa  lea     rcx, UmpoPowerSettingOverrideLock; lpCriticalSection
0x180008fb1  call    cs:__imp_LeaveCriticalSection
0x180008fb7  mov     rcx, [rbp+57h+var_30]
0x180008fbb  xor     rcx, rsp; StackCookie
0x180008fbe  call    __security_check_cookie
0x180008fc3  add     rsp, 0C8h
0x180008fca  pop     rdi
0x180008fcb  pop     rsi
0x180008fcc  pop     rbx
0x180008fcd  pop     rbp
0x180008fce  retn
0x180008fcf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008fd4  jmp     short loc_180008FAA
0x180008fd6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008fdb  jmp     loc_180008EC5
```
