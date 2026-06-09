# FlagEntry

- ea: `0x18003c7f0`
- end: `0x18003c992`
- name: `FlagEntry`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c758`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180012c50`
- `0x18003c7f0`
- `0x180072a60`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18003c8e8`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18003c8e8`
- `ntdll!NtQuerySystemInformation` at `0x18003c856`
- `ntdll!NtQuerySystemInformation` at `0x18003c856`
- `bcd!BcdOpenObject` at `0x18003c926`
- `bcd!BcdOpenObject` at `0x18003c926`
- `bcd!BcdOpenStoreFromFile` at `0x18003c905`
- `bcd!BcdOpenStoreFromFile` at `0x18003c905`
- `bcd!BcdOpenStore` at `0x18003c890`
- `bcd!BcdOpenStore` at `0x18003c890`
- `bcd!BcdCloseStore` at `0x18003c95f`
- `bcd!BcdCloseStore` at `0x18003c95f`
- `bcd!BcdCloseObject` at `0x18003c942`
- `bcd!BcdCloseObject` at `0x18003c942`

## pseudocode

```c
__int64 FlagEntry()
{
  const unsigned __int16 *v0; // rdi
  int v1; // eax
  unsigned __int64 v2; // rdx
  int v3; // ebx
  __int64 v4; // rcx
  struct _UNICODE_STRING NtPathName; // [rsp+20h] [rbp-E0h] BYREF
  __int128 SystemInformation; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v8; // [rsp+40h] [rbp-C0h]
  WCHAR DosPathName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[526]; // [rsp+52h] [rbp-AEh] BYREF

  DosPathName = 0;
  memset_0(v10, 0, 0x206u);
  SystemInformation = 0;
  v8 = 0;
  NtPathName = 0;
  if ( NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0) >= 0 && (_DWORD)v8 == 2 )
  {
    v0 = L"\\EFI\\Microsoft\\Boot\\BCD";
    WriteEfi = 1;
  }
  else
  {
    v0 = L"\\Boot\\BCD";
  }
  UsingEfi = 0;
  v1 = BcdOpenStore(0, 0, &BCDStore);
  v3 = v1;
  if ( v1 >= 0 )
    goto LABEL_14;
  v4 = (unsigned int)(v1 + 1073740719);
  if ( (unsigned int)v4 <= 1 )
  {
    if ( (int)GetPartitionPathNoContext(v4, &DosPathName) < 0 )
    {
      v3 = -1073741766;
      goto LABEL_15;
    }
    if ( StringCchCatW(&DosPathName, v2, v0) < 0 )
    {
      v3 = -1073741765;
      goto LABEL_15;
    }
    if ( !RtlDosPathNameToNtPathName_U(&DosPathName, &NtPathName, 0, 0) )
    {
      v3 = -1073741823;
      goto LABEL_15;
    }
    v3 = BcdOpenStoreFromFile(&NtPathName, &BCDStore);
    if ( v3 < 0 )
      goto LABEL_15;
LABEL_14:
    v3 = BcdOpenObject(BCDStore, &GlobalSettingsGroup, &BCDEGlobalSettingsHandle);
    if ( v3 >= 0 )
      return (unsigned int)v3;
  }
LABEL_15:
  if ( BCDEGlobalSettingsHandle != (void *)-1LL )
  {
    BcdCloseObject(BCDEGlobalSettingsHandle, v2);
    BCDEGlobalSettingsHandle = (void *)-1LL;
  }
  if ( v3 < 0 && BCDStore != (void *)-1LL )
  {
    BcdCloseStore(BCDStore, v2);
    BCDStore = (void *)-1LL;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003c7f0  mov     [rsp-8+arg_0], rbx
0x18003c7f5  mov     [rsp-8+arg_8], rdi
0x18003c7fa  push    rbp
0x18003c7fb  lea     rbp, [rsp-170h]
0x18003c803  sub     rsp, 270h
0x18003c80a  mov     rax, cs:__security_cookie
0x18003c811  xor     rax, rsp
0x18003c814  mov     [rbp+170h+var_10], rax
0x18003c81b  xor     eax, eax
0x18003c81d  lea     rcx, [rsp+270h+var_21E]; void *
0x18003c822  xor     edx, edx; Val
0x18003c824  mov     [rsp+270h+DosPathName], ax
0x18003c829  mov     r8d, 206h; Size
0x18003c82f  call    memset_0
0x18003c834  xorps   xmm0, xmm0
0x18003c837  lea     rdx, [rsp+270h+SystemInformation]; SystemInformation
0x18003c83c  xor     r9d, r9d; ReturnLength
0x18003c83f  movups  [rsp+270h+SystemInformation], xmm0
0x18003c844  movups  [rsp+270h+var_230], xmm0
0x18003c849  lea     r8d, [r9+20h]; SystemInformationLength
0x18003c84d  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18003c851  movups  xmmword ptr [rsp+270h+NtPathName.Length], xmm0
0x18003c856  call    cs:__imp_NtQuerySystemInformation
0x18003c85c  test    eax, eax
0x18003c85e  js      short loc_18003C877
0x18003c860  cmp     dword ptr [rsp+270h+var_230], 2
0x18003c865  jnz     short loc_18003C877
0x18003c867  lea     rdi, aEfiMicrosoftBo; "\\EFI\\Microsoft\\Boot\\BCD"
0x18003c86e  mov     cs:?WriteEfi@@3EA, 1; uchar WriteEfi
0x18003c875  jmp     short loc_18003C87E
0x18003c877  lea     rdi, aBootBcd; "\\Boot\\BCD"
0x18003c87e  lea     r8, ?BCDStore@@3PEAXEA; void * BCDStore
0x18003c885  mov     cs:?UsingEfi@@3EA, 0; uchar UsingEfi
0x18003c88c  xor     edx, edx
0x18003c88e  xor     ecx, ecx
0x18003c890  call    cs:__imp_BcdOpenStore
0x18003c896  mov     ebx, eax
0x18003c898  test    eax, eax
0x18003c89a  jns     short loc_18003C911
0x18003c89c  lea     ecx, [rax+3FFFFBAFh]
0x18003c8a2  cmp     ecx, 1
0x18003c8a5  ja      loc_18003C932
0x18003c8ab  lea     rdx, [rsp+270h+DosPathName]
0x18003c8b0  call    GetPartitionPathNoContext
0x18003c8b5  test    eax, eax
0x18003c8b7  jns     short loc_18003C8C0
0x18003c8b9  mov     ebx, 0C000003Ah
0x18003c8be  jmp     short loc_18003C932
0x18003c8c0  mov     r8, rdi; unsigned __int16 *
0x18003c8c3  lea     rcx, [rsp+270h+DosPathName]; unsigned __int16 *
0x18003c8c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003c8cd  test    eax, eax
0x18003c8cf  jns     short loc_18003C8D8
0x18003c8d1  mov     ebx, 0C000003Bh
0x18003c8d6  jmp     short loc_18003C932
0x18003c8d8  xor     r9d, r9d; DirectoryInfo
0x18003c8db  lea     rdx, [rsp+270h+NtPathName]; NtPathName
0x18003c8e0  xor     r8d, r8d; NtFileNamePart
0x18003c8e3  lea     rcx, [rsp+270h+DosPathName]; DosPathName
0x18003c8e8  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18003c8ee  test    al, al
0x18003c8f0  jnz     short loc_18003C8F9
0x18003c8f2  mov     ebx, 0C0000001h
0x18003c8f7  jmp     short loc_18003C932
0x18003c8f9  lea     rdx, ?BCDStore@@3PEAXEA; void * BCDStore
0x18003c900  lea     rcx, [rsp+270h+NtPathName]
0x18003c905  call    cs:__imp_BcdOpenStoreFromFile
0x18003c90b  mov     ebx, eax
0x18003c90d  test    eax, eax
0x18003c90f  js      short loc_18003C932
0x18003c911  mov     rcx, cs:?BCDStore@@3PEAXEA; void * BCDStore
0x18003c918  lea     r8, ?BCDEGlobalSettingsHandle@@3PEAXEA; void * BCDEGlobalSettingsHandle
0x18003c91f  lea     rdx, ?GlobalSettingsGroup@@3U_GUID@@A; _GUID GlobalSettingsGroup
0x18003c926  call    cs:__imp_BcdOpenObject
0x18003c92c  mov     ebx, eax
0x18003c92e  test    eax, eax
0x18003c930  jns     short loc_18003C96C
0x18003c932  mov     rcx, cs:?BCDEGlobalSettingsHandle@@3PEAXEA; void * BCDEGlobalSettingsHandle
0x18003c939  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003c93d  cmp     rcx, rdi
0x18003c940  jz      short loc_18003C94F
0x18003c942  call    cs:__imp_BcdCloseObject
0x18003c948  mov     cs:?BCDEGlobalSettingsHandle@@3PEAXEA, rdi; void * BCDEGlobalSettingsHandle
0x18003c94f  test    ebx, ebx
0x18003c951  jns     short loc_18003C96C
0x18003c953  mov     rcx, cs:?BCDStore@@3PEAXEA; void * BCDStore
0x18003c95a  cmp     rcx, rdi
0x18003c95d  jz      short loc_18003C96C
0x18003c95f  call    cs:__imp_BcdCloseStore
0x18003c965  mov     cs:?BCDStore@@3PEAXEA, rdi; void * BCDStore
0x18003c96c  mov     eax, ebx
0x18003c96e  mov     rcx, [rbp+170h+var_10]
0x18003c975  xor     rcx, rsp; StackCookie
0x18003c978  call    __security_check_cookie
0x18003c97d  lea     r11, [rsp+270h+var_s0]
0x18003c985  mov     rbx, [r11+10h]
0x18003c989  mov     rdi, [r11+18h]
0x18003c98d  mov     rsp, r11
0x18003c990  pop     rbp
0x18003c991  retn
```
