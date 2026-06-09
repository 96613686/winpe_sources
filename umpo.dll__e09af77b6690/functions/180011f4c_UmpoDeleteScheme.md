# UmpoDeleteScheme

- ea: `0x180011f4c`
- end: `0x180012073`
- name: `UmpoDeleteScheme`
- size: `295`
- prototype: `__int64 __fastcall(UUID *Uuid1)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147b0`

## callees

- `0x180003370`
- `0x1800034c0`
- `0x180003560`
- `0x18000e030`
- `0x18000f3dc`
- `0x180010070`
- `0x180011f4c`
- `0x180012864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012040`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011faf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011faf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001200b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001200b`
- `RPCRT4!UuidEqual` at `0x180011fd2`
- `RPCRT4!UuidEqual` at `0x180011fd2`

## pseudocode

```c
__int64 __fastcall UmpoDeleteScheme(UUID *Uuid1)
{
  unsigned int ActiveScheme; // ebx
  RPC_STATUS Status; // [rsp+20h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-80h] BYREF
  UUID Uuid2; // [rsp+30h] [rbp-78h] BYREF
  WCHAR SubKey[40]; // [rsp+40h] [rbp-68h] BYREF

  Uuid2 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  Status = 0;
  if ( UmpoFullPowerPlanSupportDisabled )
    goto LABEL_2;
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoSchemeLock);
  ActiveScheme = UmpoGetActiveScheme(&Uuid2);
  if ( !ActiveScheme )
  {
    if ( UuidEqual(Uuid1, &Uuid2, &Status) )
    {
LABEL_2:
      ActiveScheme = 50;
      goto LABEL_9;
    }
    ActiveScheme = UmpoInternalOpenUserPowerKey(&hKey, 0x20006u);
    if ( !ActiveScheme )
    {
      UmpoInternalConvertGuidToStringBuffer(Uuid1, SubKey);
      ActiveScheme = RegDeleteTreeW(hKey, SubKey);
      UmpoInternalClearPowerSubkeyCache(&UmpoPowerSubGroupCache);
      UmpoInternalClearPowerSubkeyCache(&UmpoPowerSettingCache);
    }
  }
LABEL_9:
  if ( byte_180024FA8 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoSchemeLock);
  UmpoInternalCloseUserPowerKey(hKey);
  return ActiveScheme;
}

```

## disassembly

```asm
0x180011f4c  mov     [rsp+arg_8], rbx
0x180011f51  push    rdi
0x180011f52  sub     rsp, 0A0h
0x180011f59  mov     rax, cs:__security_cookie
0x180011f60  xor     rax, rsp
0x180011f63  mov     [rsp+0A8h+var_18], rax
0x180011f6b  cmp     cs:UmpoFullPowerPlanSupportDisabled, 0
0x180011f72  xorps   xmm0, xmm0
0x180011f75  movups  xmmword ptr [rsp+0A8h+Uuid2.Data1], xmm0
0x180011f7a  mov     rdi, rcx
0x180011f7d  mov     [rsp+0A8h+hKey], 0FFFFFFFFFFFFFFFFh
0x180011f86  mov     [rsp+0A8h+Status], 0
0x180011f8e  jz      short loc_180011F9A
0x180011f90  mov     ebx, 32h ; '2'
0x180011f95  jmp     loc_18001202B
0x180011f9a  cmp     cs:byte_180024FA8, 1
0x180011fa1  jz      short loc_180011FA8
0x180011fa3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180011fa8  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x180011faf  call    cs:__imp_EnterCriticalSection
0x180011fb5  lea     rcx, [rsp+0A8h+Uuid2]; Uuid
0x180011fba  call    UmpoGetActiveScheme
0x180011fbf  mov     ebx, eax
0x180011fc1  test    eax, eax
0x180011fc3  jnz     short loc_18001202B
0x180011fc5  lea     r8, [rsp+0A8h+Status]; Status
0x180011fca  mov     rcx, rdi; Uuid1
0x180011fcd  lea     rdx, [rsp+0A8h+Uuid2]; Uuid2
0x180011fd2  call    cs:__imp_UuidEqual
0x180011fd8  test    eax, eax
0x180011fda  jnz     short loc_180011F90
0x180011fdc  xor     r8d, r8d
0x180011fdf  lea     rcx, [rsp+0A8h+hKey]; phkResult
0x180011fe4  mov     edx, 20006h; samDesired
0x180011fe9  call    UmpoInternalOpenUserPowerKey
0x180011fee  mov     ebx, eax
0x180011ff0  test    eax, eax
0x180011ff2  jnz     short loc_18001202B
0x180011ff4  lea     rdx, [rsp+0A8h+SubKey]
0x180011ff9  mov     rcx, rdi
0x180011ffc  call    UmpoInternalConvertGuidToStringBuffer
0x180012001  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180012006  lea     rdx, [rsp+0A8h+SubKey]; lpSubKey
0x18001200b  call    cs:__imp_RegDeleteTreeW
0x180012011  lea     rcx, UmpoPowerSubGroupCache
0x180012018  mov     ebx, eax
0x18001201a  call    UmpoInternalClearPowerSubkeyCache
0x18001201f  lea     rcx, UmpoPowerSettingCache
0x180012026  call    UmpoInternalClearPowerSubkeyCache
0x18001202b  cmp     cs:byte_180024FA8, 1
0x180012032  jz      short loc_180012039
0x180012034  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012039  lea     rcx, UmpoSchemeLock; lpCriticalSection
0x180012040  call    cs:__imp_LeaveCriticalSection
0x180012046  mov     rcx, [rsp+0A8h+hKey]
0x18001204b  call    UmpoInternalCloseUserPowerKey
0x180012050  mov     eax, ebx
0x180012052  mov     rcx, [rsp+0A8h+var_18]
0x18001205a  xor     rcx, rsp; StackCookie
0x18001205d  call    __security_check_cookie
0x180012062  mov     rbx, [rsp+0A8h+arg_8]
0x18001206a  add     rsp, 0A0h
0x180012071  pop     rdi
0x180012072  retn
```
