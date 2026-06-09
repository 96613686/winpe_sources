# WwanRegisterForGroupPolicyChangeNotification

- ea: `0x1800c0504`
- end: `0x1800c06bb`
- name: `WwanRegisterForGroupPolicyChangeNotification`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180015ac8`

## callees

- `0x18000a144`
- `0x180012300`
- `0x180016c50`
- `0x180019f24`
- `0x180074758`
- `0x1800c0504`
- `0x1800c06c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c0527`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800c0527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c05d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c05d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c068e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c068e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c0667`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c0667`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800c056f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800c056f`
- `MobileNetworking!PersistentRegPathOpenKey` at `0x1800c0626`
- `MobileNetworking!PersistentRegPathOpenKey` at `0x1800c0626`
- `USERENV!RegisterGPNotification` at `0x1800c05b7`
- `USERENV!RegisterGPNotification` at `0x1800c05b7`

## string_xrefs

- `0x1800c053f`: `CreateEvent failed [err:%d]`
- `0x1800c05fb`: `Group Policy is not present. Register for registry change notification.`
- `0x1800c0635`: `Unable to open wwan root windows GP registry [err:%d]`

## pseudocode

```c
__int64 WwanRegisterForGroupPolicyChangeNotification()
{
  HANDLE EventW; // rax
  DWORD v1; // eax
  const unsigned __int16 *v2; // r8
  __int64 LastError; // rbx
  unsigned int v4; // eax
  unsigned int v5; // eax

  WwanLog::Enter("WwanRegisterForGroupPolicyChangeNotification");
  EventW = CreateEventW(0, 0, 0, 0);
  g_hPolicyEvent = EventW;
  if ( EventW )
  {
    if ( !RegisterWaitForSingleObject(&g_hWaitObject, EventW, PolicyChangeCallback, 0, 0xFFFFFFFF, 0) )
    {
      LastError = GetLastError();
      WwanLog::Error(
        "WwanRegisterForGroupPolicyChangeNotification",
        0,
        L"RegisterWaitForSingleObject failed [err:%d]",
        LastError);
      g_hWaitObject = 0;
      goto LABEL_10;
    }
    if ( !(unsigned __int8)IsRegisterGPNotificationInternalWorkerPresent() )
    {
      WwanLog::Verbose(
        "WwanRegisterForGroupPolicyChangeNotification",
        0,
        L"Group Policy is not present. Register for registry change notification.");
      v4 = PersistentRegPathOpenKey(6, 0, 0, 131097, &g_hKeyRootWindowsGP);
      LODWORD(LastError) = v4;
      if ( v4 )
      {
        WwanLog::Error(
          "WwanRegisterForGroupPolicyChangeNotification",
          0,
          L"Unable to open wwan root windows GP registry [err:%d]",
          v4);
      }
      else
      {
        v5 = RegNotifyChangeKeyValue(g_hKeyRootWindowsGP, 1, 4u, g_hPolicyEvent, 1);
        LODWORD(LastError) = v5;
        if ( !v5 )
          goto LABEL_17;
        WwanLog::Error(
          "WwanRegisterForGroupPolicyChangeNotification",
          0,
          L"RegNotifyChangeKeyValue failed [err:%d]",
          v5);
        RegCloseKey(g_hKeyRootWindowsGP);
        g_hKeyRootWindowsGP = 0;
      }
LABEL_16:
      WwanUnregisterGroupPolicyNotification();
      goto LABEL_17;
    }
    if ( RegisterGPNotification(g_hPolicyEvent, 1) )
    {
      LODWORD(LastError) = 0;
      g_fRegisteredForPolicyNotification = 1;
      goto LABEL_17;
    }
    v1 = GetLastError();
    v2 = L"RegisterGPNotification failed [err:%d]";
  }
  else
  {
    v1 = GetLastError();
    v2 = L"CreateEvent failed [err:%d]";
  }
  LODWORD(LastError) = v1;
  WwanLog::Error("WwanRegisterForGroupPolicyChangeNotification", 0, v2, v1);
LABEL_10:
  if ( (_DWORD)LastError )
    goto LABEL_16;
LABEL_17:
  WwanLog::ExitWithStatus("WwanRegisterForGroupPolicyChangeNotification", LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800c0504  mov     [rsp+arg_0], rbx
0x1800c0509  push    rbp
0x1800c050a  sub     rsp, 30h
0x1800c050e  lea     rbp, aWwanregisterfo; "WwanRegisterForGroupPolicyChangeNotific"...
0x1800c0515  mov     rcx, rbp; char *
0x1800c0518  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800c051d  xor     r9d, r9d; lpName
0x1800c0520  xor     r8d, r8d; bInitialState
0x1800c0523  xor     edx, edx; bManualReset
0x1800c0525  xor     ecx, ecx; lpEventAttributes
0x1800c0527  call    cs:__imp_CreateEventW
0x1800c052d  mov     cs:?g_hPolicyEvent@@3PEAXEA, rax; void * g_hPolicyEvent
0x1800c0534  test    rax, rax
0x1800c0537  jnz     short loc_1800C054B
0x1800c0539  call    cs:__imp_GetLastError
0x1800c053f  lea     r8, aCreateeventFai; "CreateEvent failed [err:%d]"
0x1800c0546  jmp     loc_1800C05DF
0x1800c054b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800c0553  lea     r8, ?PolicyChangeCallback@@YAXPEAXE@Z; Callback
0x1800c055a  xor     r9d, r9d; Context
0x1800c055d  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800c0565  mov     rdx, rax; hObject
0x1800c0568  lea     rcx, ?g_hWaitObject@@3PEAXEA; phNewWaitObject
0x1800c056f  call    cs:__imp_RegisterWaitForSingleObject
0x1800c0575  test    eax, eax
0x1800c0577  jnz     short loc_1800C05A2
0x1800c0579  call    cs:__imp_GetLastError
0x1800c057f  lea     r8, aRegisterwaitfo; "RegisterWaitForSingleObject failed [err"...
0x1800c0586  xor     edx, edx; struct _GUID *
0x1800c0588  mov     r9d, eax
0x1800c058b  mov     rcx, rbp; char *
0x1800c058e  mov     ebx, eax
0x1800c0590  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c0595  mov     cs:?g_hWaitObject@@3PEAXEA, 0; void * g_hWaitObject
0x1800c05a0  jmp     short loc_1800C05EE
0x1800c05a2  call    IsRegisterGPNotificationInternalWorkerPresent
0x1800c05a7  test    al, al
0x1800c05a9  jz      short loc_1800C05FB
0x1800c05ab  mov     rcx, cs:?g_hPolicyEvent@@3PEAXEA; hEvent
0x1800c05b2  mov     edx, 1; bMachine
0x1800c05b7  call    cs:__imp_RegisterGPNotification
0x1800c05bd  test    eax, eax
0x1800c05bf  jz      short loc_1800C05D2
0x1800c05c1  xor     ebx, ebx
0x1800c05c3  mov     cs:?g_fRegisteredForPolicyNotification@@3HA, 1; int g_fRegisteredForPolicyNotification
0x1800c05cd  jmp     loc_1800C06A4
0x1800c05d2  call    cs:__imp_GetLastError
0x1800c05d8  lea     r8, aRegistergpnoti_0; "RegisterGPNotification failed [err:%d]"
0x1800c05df  mov     r9d, eax
0x1800c05e2  xor     edx, edx; struct _GUID *
0x1800c05e4  mov     rcx, rbp; char *
0x1800c05e7  mov     ebx, eax
0x1800c05e9  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c05ee  test    ebx, ebx
0x1800c05f0  jz      loc_1800C06A4
0x1800c05f6  jmp     loc_1800C069F
0x1800c05fb  lea     r8, aGroupPolicyIsN; "Group Policy is not present. Register f"...
0x1800c0602  xor     edx, edx; struct _GUID *
0x1800c0604  mov     rcx, rbp; char *
0x1800c0607  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800c060c  xor     edx, edx
0x1800c060e  lea     rax, ?g_hKeyRootWindowsGP@@3PEAXEA; void * g_hKeyRootWindowsGP
0x1800c0615  mov     r9d, 20019h
0x1800c061b  mov     qword ptr [rsp+38h+dwMilliseconds], rax
0x1800c0620  xor     r8d, r8d
0x1800c0623  lea     ecx, [rdx+6]
0x1800c0626  call    cs:__imp_PersistentRegPathOpenKey
0x1800c062c  mov     ebx, eax
0x1800c062e  test    eax, eax
0x1800c0630  jz      short loc_1800C0648
0x1800c0632  mov     r9d, eax
0x1800c0635  lea     r8, aUnableToOpenWw; "Unable to open wwan root windows GP reg"...
0x1800c063c  xor     edx, edx; struct _GUID *
0x1800c063e  mov     rcx, rbp; char *
0x1800c0641  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c0646  jmp     short loc_1800C069F
0x1800c0648  mov     r9, cs:?g_hPolicyEvent@@3PEAXEA; hEvent
0x1800c064f  mov     edx, 1; bWatchSubtree
0x1800c0654  mov     rcx, cs:?g_hKeyRootWindowsGP@@3PEAXEA; hKey
0x1800c065b  mov     [rsp+38h+dwMilliseconds], 1; fAsynchronous
0x1800c0663  lea     r8d, [rdx+3]; dwNotifyFilter
0x1800c0667  call    cs:__imp_RegNotifyChangeKeyValue
0x1800c066d  mov     ebx, eax
0x1800c066f  test    eax, eax
0x1800c0671  jz      short loc_1800C06A4
0x1800c0673  mov     r9d, eax
0x1800c0676  lea     r8, aRegnotifychang; "RegNotifyChangeKeyValue failed [err:%d]"
0x1800c067d  xor     edx, edx; struct _GUID *
0x1800c067f  mov     rcx, rbp; char *
0x1800c0682  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800c0687  mov     rcx, cs:?g_hKeyRootWindowsGP@@3PEAXEA; hKey
0x1800c068e  call    cs:__imp_RegCloseKey
0x1800c0694  mov     cs:?g_hKeyRootWindowsGP@@3PEAXEA, 0; void * g_hKeyRootWindowsGP
0x1800c069f  call    WwanUnregisterGroupPolicyNotification
0x1800c06a4  mov     edx, ebx; unsigned int
0x1800c06a6  mov     rcx, rbp; char *
0x1800c06a9  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800c06ae  mov     eax, ebx
0x1800c06b0  mov     rbx, [rsp+38h+arg_0]
0x1800c06b5  add     rsp, 30h
0x1800c06b9  pop     rbp
0x1800c06ba  retn
```
