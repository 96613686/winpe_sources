# EcbDoSyncPrefetchAnalysis

- ea: `0x1800b2cb8`
- end: `0x1800b2e3f`
- name: `EcbDoSyncPrefetchAnalysis`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b1930`

## callees

- `0x1800b1f38`
- `0x1800b2cb8`
- `0x1800b3044`
- `0x1800b3094`
- `0x1800b3994`

## import_xrefs

- `ntdll!NtCreateKey` at `0x1800b2dbf`
- `ntdll!NtCreateKey` at `0x1800b2dbf`
- `ntdll!RtlNtStatusToDosError` at `0x1800b2dcb`
- `ntdll!RtlNtStatusToDosError` at `0x1800b2dcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2e20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b2e20`

## string_xrefs

- `0x1800b2d44`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`

## pseudocode

```c
__int64 __fastcall EcbDoSyncPrefetchAnalysis(__int64 a1, unsigned int *a2, unsigned int a3)
{
  ULONG SyncPrefetchSizeFromBootPlan; // ebx
  __int64 v6; // rcx
  const WCHAR *v7; // rax
  __int16 v8; // cx
  int v9; // eax
  unsigned int v10; // eax
  int v12; // [rsp+40h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-11h] BYREF
  __int128 v14; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  unsigned int v16; // [rsp+C0h] [rbp+67h] BYREF
  int v17; // [rsp+D8h] [rbp+7Fh]

  v17 = 0;
  v16 = 0;
  v12 = 0;
  KeyHandle = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (*(_BYTE *)(a1 + 16) & 2) == 0 )
  {
    SyncPrefetchSizeFromBootPlan = EcbGetSyncPrefetchSizeFromBootPlan(&v16, &v12);
    if ( SyncPrefetchSizeFromBootPlan )
    {
      if ( *(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 340LL) != 14 )
        goto LABEL_17;
      EcbGetInitialSyncPrefetchSize(a3, &v16);
    }
LABEL_14:
    v10 = v16;
    SyncPrefetchSizeFromBootPlan = 0;
    if ( v16 > a3 )
      v10 = a3;
    *a2 = v10;
    goto LABEL_17;
  }
  v6 = 0x7FFF;
  v7 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  while ( *v7 )
  {
    ++v7;
    if ( !--v6 )
      goto LABEL_10;
  }
  v8 = 2 * v6;
  *((_QWORD *)&v14 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  LOWORD(v14) = -2 - v8;
  WORD1(v14) = -v8;
LABEL_10:
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.Attributes = 64;
  v9 = NtCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( v9 < 0 )
  {
    SyncPrefetchSizeFromBootPlan = RtlNtStatusToDosError(v9);
    goto LABEL_17;
  }
  SyncPrefetchSizeFromBootPlan = EcbUpdatePendStats((HKEY)KeyHandle);
  if ( !SyncPrefetchSizeFromBootPlan )
  {
    SyncPrefetchSizeFromBootPlan = EcbComputeSyncPrefetch((HKEY)KeyHandle, a3);
    if ( !SyncPrefetchSizeFromBootPlan )
      goto LABEL_14;
  }
LABEL_17:
  if ( KeyHandle )
    RegCloseKey((HKEY)KeyHandle);
  return SyncPrefetchSizeFromBootPlan;
}

```

## disassembly

```asm
0x1800b2cb8  mov     [rsp-8+arg_8], rbx
0x1800b2cbd  push    rbp
0x1800b2cbe  push    rsi
0x1800b2cbf  push    rdi
0x1800b2cc0  push    r14
0x1800b2cc2  push    r15
0x1800b2cc4  lea     rbp, [rsp-37h]
0x1800b2cc9  sub     rsp, 90h
0x1800b2cd0  xor     r15d, r15d
0x1800b2cd3  xorps   xmm0, xmm0
0x1800b2cd6  xor     eax, eax
0x1800b2cd8  mov     [rbp+57h+arg_18], r15d
0x1800b2cdc  mov     r14, rdx
0x1800b2cdf  mov     [rbp+57h+arg_0], r15d
0x1800b2ce3  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800b2ce7  mov     edi, r8d
0x1800b2cea  mov     [rbp+57h+var_70], r15d
0x1800b2cee  lea     edx, [rax+2]
0x1800b2cf1  mov     [rbp+57h+KeyHandle], r15
0x1800b2cf5  mov     rsi, rcx
0x1800b2cf8  movups  [rbp+57h+var_60], xmm0
0x1800b2cfc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800b2d00  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800b2d04  test    [rcx+10h], dl
0x1800b2d07  jnz     short loc_1800B2D44
0x1800b2d09  lea     rdx, [rbp+57h+var_70]
0x1800b2d0d  lea     rcx, [rbp+57h+arg_0]
0x1800b2d11  call    EcbGetSyncPrefetchSizeFromBootPlan
0x1800b2d16  mov     ebx, eax
0x1800b2d18  test    eax, eax
0x1800b2d1a  jz      loc_1800B2E09
0x1800b2d20  mov     rcx, cs:PfSvcGlobals
0x1800b2d27  cmp     dword ptr [rcx+154h], 0Eh
0x1800b2d2e  jnz     loc_1800B2E17
0x1800b2d34  lea     rdx, [rbp+57h+arg_0]
0x1800b2d38  mov     ecx, edi
0x1800b2d3a  call    EcbGetInitialSyncPrefetchSize
0x1800b2d3f  jmp     loc_1800B2E09
0x1800b2d44  lea     r8, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800b2d4b  mov     ecx, 7FFFh
0x1800b2d50  mov     rax, r8
0x1800b2d53  cmp     [rax], r15w
0x1800b2d57  jz      short loc_1800B2D64
0x1800b2d59  add     rax, rdx
0x1800b2d5c  sub     rcx, 1
0x1800b2d60  jnz     short loc_1800B2D53
0x1800b2d62  jmp     short loc_1800B2D7E
0x1800b2d64  add     cx, cx
0x1800b2d67  mov     qword ptr [rbp+57h+var_60+8], r8
0x1800b2d6b  mov     eax, 0FFFEh
0x1800b2d70  sub     ax, cx
0x1800b2d73  mov     word ptr [rbp+57h+var_60], ax
0x1800b2d77  add     ax, dx
0x1800b2d7a  mov     word ptr [rbp+57h+var_60+2], ax
0x1800b2d7e  lea     rax, [rbp+57h+var_60]
0x1800b2d82  mov     [rsp+0B0h+Disposition], r15; Disposition
0x1800b2d87  xorps   xmm0, xmm0
0x1800b2d8a  mov     [rsp+0B0h+CreateOptions], r15d; CreateOptions
0x1800b2d8f  xor     r9d, r9d; TitleIndex
0x1800b2d92  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800b2d96  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800b2d9a  mov     [rsp+0B0h+Class], r15; Class
0x1800b2d9f  mov     edx, 0F003Fh; DesiredAccess
0x1800b2da4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800b2dab  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800b2daf  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800b2db3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b2db8  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800b2dbf  call    cs:__imp_NtCreateKey
0x1800b2dc5  test    eax, eax
0x1800b2dc7  jns     short loc_1800B2DD5
0x1800b2dc9  mov     ecx, eax; Status
0x1800b2dcb  call    cs:__imp_RtlNtStatusToDosError
0x1800b2dd1  mov     ebx, eax
0x1800b2dd3  jmp     short loc_1800B2E17
0x1800b2dd5  mov     edx, [rsi+14h]
0x1800b2dd8  lea     r8, [rbp+57h+arg_18]
0x1800b2ddc  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x1800b2de0  call    EcbUpdatePendStats
0x1800b2de5  mov     ebx, eax
0x1800b2de7  test    eax, eax
0x1800b2de9  jnz     short loc_1800B2E17
0x1800b2deb  mov     r9d, [rbp+57h+arg_18]
0x1800b2def  lea     r8, [rbp+57h+arg_0]
0x1800b2df3  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x1800b2df7  mov     rdx, rsi
0x1800b2dfa  mov     dword ptr [rsp+0B0h+Class], edi; int
0x1800b2dfe  call    EcbComputeSyncPrefetch
0x1800b2e03  mov     ebx, eax
0x1800b2e05  test    eax, eax
0x1800b2e07  jnz     short loc_1800B2E17
0x1800b2e09  mov     eax, [rbp+57h+arg_0]
0x1800b2e0c  mov     ebx, r15d
0x1800b2e0f  cmp     eax, edi
0x1800b2e11  cmova   eax, edi
0x1800b2e14  mov     [r14], eax
0x1800b2e17  mov     rcx, [rbp+57h+KeyHandle]; hKey
0x1800b2e1b  test    rcx, rcx
0x1800b2e1e  jz      short loc_1800B2E26
0x1800b2e20  call    cs:__imp_RegCloseKey
0x1800b2e26  mov     eax, ebx
0x1800b2e28  mov     rbx, [rsp+0B0h+arg_8]
0x1800b2e30  add     rsp, 90h
0x1800b2e37  pop     r15
0x1800b2e39  pop     r14
0x1800b2e3b  pop     rdi
0x1800b2e3c  pop     rsi
0x1800b2e3d  pop     rbp
0x1800b2e3e  retn
```
