# SampRODCRegistryWatch(void *)

- ea: `0x180039ae0`
- end: `0x180039c41`
- name: `?SampRODCRegistryWatch@@YAJPEAX@Z`
- size: `353`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800888c0`

## callees

- `0x180027e24`
- `0x180039ae0`
- `0x180039c48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039b57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180039b57`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180039b3d`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180039b3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039b21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039b21`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180039b9f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180039b9f`
- `LSASRV!LsaIRegisterNotification` at `0x180039bd1`
- `LSASRV!LsaIRegisterNotification` at `0x180039bd1`

## pseudocode

```c
__int64 __fastcall SampRODCRegistryWatch(void *a1)
{
  unsigned int v1; // edi
  unsigned int v2; // ebx
  PUNICODE_STRING v3; // rcx

  v1 = 31;
  if ( SampRODCRegistryKey )
  {
LABEL_6:
    SampRODCCacheValid = 0;
    SampRefreshRODCCache((unsigned __int8)a1);
    RegNotifyChangeKeyValue(SampRODCRegistryKey, 1, 5u, SampRODCRegistryWatchEvent, 1);
    LsaIRegisterNotification(SampRODCRegistryWatch, 0, 2, 0, 0, 0, SampRODCRegistryWatchEvent);
    v2 = 0;
    goto LABEL_7;
  }
  v2 = -1073741823;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Lsa\\RODCROLES",
         0,
         0x20019u,
         &SampRODCRegistryKey);
  if ( !v1 )
  {
    v1 = RtlInitializeCriticalSectionAndSpinCount(&SampRODCCacheRebuild, 0xFA0u);
    if ( !v1 )
    {
      SampRODCRegistryWatchEvent = CreateEventW(0, 0, 0, 0);
      if ( !SampRODCRegistryWatchEvent )
      {
LABEL_10:
        v3 = WPP_GLOBAL_Control;
        goto LABEL_11;
      }
      SampRODCCacheEnabled = 1;
      goto LABEL_6;
    }
  }
LABEL_7:
  v3 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 64, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, v1, v2);
    goto LABEL_10;
  }
LABEL_11:
  if ( (*(_DWORD *)(&v3[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v3[3].Buffer, 65, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, v2, v2);
  return v2;
}

```

## disassembly

```asm
0x180039ae0  mov     [rsp+arg_0], rbx
0x180039ae5  push    rdi
0x180039ae6  sub     rsp, 40h
0x180039aea  cmp     cs:?SampRODCRegistryKey@@3PEAUHKEY__@@EA, 0; HKEY__ * SampRODCRegistryKey
0x180039af2  mov     edi, 1Fh
0x180039af7  jnz     short loc_180039B74
0x180039af9  lea     rax, ?SampRODCRegistryKey@@3PEAUHKEY__@@EA; HKEY__ * SampRODCRegistryKey
0x180039b00  mov     r9d, 20019h; samDesired
0x180039b06  xor     r8d, r8d; ulOptions
0x180039b09  mov     [rsp+48h+phkResult], rax; phkResult
0x180039b0e  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Lsa"...
0x180039b15  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039b1c  mov     ebx, 0C0000001h
0x180039b21  call    cs:__imp_RegOpenKeyExW
0x180039b27  mov     edi, eax
0x180039b29  test    eax, eax
0x180039b2b  jnz     loc_180039BD9
0x180039b31  mov     edx, 0FA0h; SpinCount
0x180039b36  lea     rcx, ?SampRODCCacheRebuild@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180039b3d  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180039b43  mov     edi, eax
0x180039b45  test    eax, eax
0x180039b47  jnz     loc_180039BD9
0x180039b4d  xor     r9d, r9d; lpName
0x180039b50  xor     r8d, r8d; bInitialState
0x180039b53  xor     edx, edx; bManualReset
0x180039b55  xor     ecx, ecx; lpEventAttributes
0x180039b57  call    cs:__imp_CreateEventW
0x180039b5d  mov     cs:?SampRODCRegistryWatchEvent@@3PEAXEA, rax; void * SampRODCRegistryWatchEvent
0x180039b64  test    rax, rax
0x180039b67  jz      loc_180039C08
0x180039b6d  mov     cs:?SampRODCCacheEnabled@@3EA, 1; uchar SampRODCCacheEnabled
0x180039b74  mov     cs:?SampRODCCacheValid@@3EA, 0; uchar SampRODCCacheValid
0x180039b7b  call    ?SampRefreshRODCCache@@YAJE@Z; SampRefreshRODCCache(uchar)
0x180039b80  mov     r9, cs:?SampRODCRegistryWatchEvent@@3PEAXEA; hEvent
0x180039b87  mov     edx, 1; bWatchSubtree
0x180039b8c  mov     rcx, cs:?SampRODCRegistryKey@@3PEAUHKEY__@@EA; hKey
0x180039b93  mov     dword ptr [rsp+48h+phkResult], 1; fAsynchronous
0x180039b9b  lea     r8d, [rdx+4]; dwNotifyFilter
0x180039b9f  call    cs:__imp_RegNotifyChangeKeyValue
0x180039ba5  mov     rax, cs:?SampRODCRegistryWatchEvent@@3PEAXEA; void * SampRODCRegistryWatchEvent
0x180039bac  lea     rcx, ?SampRODCRegistryWatch@@YAJPEAX@Z; SampRODCRegistryWatch(void *)
0x180039bb3  mov     [rsp+48h+var_18], rax
0x180039bb8  xor     r9d, r9d
0x180039bbb  mov     [rsp+48h+var_20], 0
0x180039bc3  xor     edx, edx
0x180039bc5  mov     dword ptr [rsp+48h+phkResult], 0
0x180039bcd  lea     r8d, [r9+2]
0x180039bd1  call    cs:__imp_LsaIRegisterNotification
0x180039bd7  xor     ebx, ebx
0x180039bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180039be0  test    byte ptr [rcx+44h], 20h
0x180039be4  jz      short loc_180039C0F
0x180039be6  cmp     byte ptr [rcx+41h], 2
0x180039bea  jb      short loc_180039C0F
0x180039bec  mov     rcx, [rcx+38h]
0x180039bf0  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x180039bf7  mov     edx, 40h ; '@'
0x180039bfc  mov     dword ptr [rsp+48h+phkResult], ebx
0x180039c00  mov     r9d, edi
0x180039c03  call    WPP_SF_Dd
0x180039c08  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c0f  test    dword ptr [rcx+44h], 20000h
0x180039c16  jz      short loc_180039C34
0x180039c18  mov     rcx, [rcx+38h]
0x180039c1c  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x180039c23  mov     edx, 41h ; 'A'
0x180039c28  mov     dword ptr [rsp+48h+phkResult], ebx
0x180039c2c  mov     r9d, ebx
0x180039c2f  call    WPP_SF_Dd
0x180039c34  mov     eax, ebx
0x180039c36  mov     rbx, [rsp+48h+arg_0]
0x180039c3b  add     rsp, 40h
0x180039c3f  pop     rdi
0x180039c40  retn
```
