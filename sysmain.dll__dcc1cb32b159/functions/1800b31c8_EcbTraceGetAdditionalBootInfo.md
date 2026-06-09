# EcbTraceGetAdditionalBootInfo

- ea: `0x1800b31c8`
- end: `0x1800b332a`
- name: `EcbTraceGetAdditionalBootInfo`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d394`

## callees

- `0x1800382e0`
- `0x1800b31c8`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800b325f`
- `ntdll!NtOpenKey` at `0x1800b325f`
- `ntdll!NtClose` at `0x1800b330c`
- `ntdll!NtClose` at `0x1800b330c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b331b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b331b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b32c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b32c5`

## string_xrefs

- `0x1800b31d6`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`
- `0x1800b327f`: `ReadyBootPlanAge`

## pseudocode

```c
LSTATUS __fastcall EcbTraceGetAdditionalBootInfo(_DWORD *a1)
{
  __int64 v2; // rcx
  const WCHAR *v3; // rax
  __int16 v4; // cx
  unsigned int v5; // eax
  LSTATUS result; // eax
  __int128 v7; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v9; // [rsp+A0h] [rbp+28h] BYREF
  LSTATUS v10; // [rsp+A8h] [rbp+30h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+40h] BYREF

  v9 = 0;
  v10 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  v2 = 0x7FFF;
  *(&ObjectAttributes.Attributes + 1) = 0;
  KeyHandle = 0;
  v3 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  hKey = 0;
  v7 = 0;
  while ( *v3 )
  {
    ++v3;
    if ( !--v2 )
      goto LABEL_6;
  }
  v4 = 2 * v2;
  *((_QWORD *)&v7 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  LOWORD(v7) = -2 - v4;
  WORD1(v7) = -v4;
LABEL_6:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v7;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0
    && !(unsigned int)PfsRegQueryValue((_DWORD)KeyHandle, (unsigned int)L"ReadyBootPlanAge", 4, 4, (__int64)&v9) )
  {
    v5 = v9;
    a1[29] = v9;
    if ( v5 >= 5 )
      a1[26] |= 8u;
  }
  result = RegOpenKeyExW(*(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL), L"DiskAssessment", 0, 0x20019u, &hKey);
  if ( !result )
  {
    result = PfsRegQueryValue((_DWORD)hKey, (unsigned int)L"RPM", 4, 4, (__int64)&v10);
    if ( !result )
    {
      result = v10;
      a1[27] = v10;
    }
  }
  if ( !a1[27] )
    a1[26] |= 2u;
  if ( KeyHandle )
    result = NtClose(KeyHandle);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x1800b31c8  push    rbp
0x1800b31ca  push    rbx
0x1800b31cb  push    rsi
0x1800b31cc  push    rdi
0x1800b31cd  mov     rbp, rsp
0x1800b31d0  sub     rsp, 78h
0x1800b31d4  xor     edi, edi
0x1800b31d6  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800b31dd  xorps   xmm0, xmm0
0x1800b31e0  mov     [rbp+arg_0], edi
0x1800b31e3  mov     rbx, rcx
0x1800b31e6  mov     [rbp+arg_8], edi
0x1800b31e9  mov     dword ptr [rbp+ObjectAttributes+4], edi
0x1800b31ec  mov     ecx, 7FFFh
0x1800b31f1  lea     esi, [rdi+2]
0x1800b31f4  mov     dword ptr [rbp+ObjectAttributes+1Ch], edi
0x1800b31f7  mov     [rbp+KeyHandle], rdi
0x1800b31fb  mov     rax, rdx
0x1800b31fe  mov     [rbp+hKey], rdi
0x1800b3202  movups  [rbp+var_48], xmm0
0x1800b3206  cmp     [rax], di
0x1800b3209  jz      short loc_1800B3216
0x1800b320b  add     rax, rsi
0x1800b320e  sub     rcx, 1
0x1800b3212  jnz     short loc_1800B3206
0x1800b3214  jmp     short loc_1800B3230
0x1800b3216  add     cx, cx
0x1800b3219  mov     qword ptr [rbp+var_48+8], rdx
0x1800b321d  mov     eax, 0FFFEh
0x1800b3222  sub     ax, cx
0x1800b3225  mov     word ptr [rbp+var_48], ax
0x1800b3229  add     ax, si
0x1800b322c  mov     word ptr [rbp+var_48+2], ax
0x1800b3230  lea     rax, [rbp+var_48]
0x1800b3234  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800b323b  xorps   xmm0, xmm0
0x1800b323e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800b3242  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800b3246  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x1800b324a  mov     edx, 0F003Fh; DesiredAccess
0x1800b324f  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800b3256  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800b325a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b325f  call    cs:__imp_NtOpenKey
0x1800b3265  test    eax, eax
0x1800b3267  js      short loc_1800B329E
0x1800b3269  mov     rcx, [rbp+KeyHandle]
0x1800b326d  lea     rax, [rbp+arg_0]
0x1800b3271  mov     r9d, 4
0x1800b3277  mov     [rsp+78h+phkResult], rax
0x1800b327c  mov     r8d, r9d
0x1800b327f  lea     rdx, aReadybootplana; "ReadyBootPlanAge"
0x1800b3286  call    PfsRegQueryValue
0x1800b328b  test    eax, eax
0x1800b328d  jnz     short loc_1800B329E
0x1800b328f  mov     eax, [rbp+arg_0]
0x1800b3292  mov     [rbx+74h], eax
0x1800b3295  cmp     eax, 5
0x1800b3298  jb      short loc_1800B329E
0x1800b329a  or      dword ptr [rbx+68h], 8
0x1800b329e  mov     rcx, cs:PfSvcGlobals
0x1800b32a5  lea     rax, [rbp+hKey]
0x1800b32a9  mov     r9d, 20019h; samDesired
0x1800b32af  mov     [rsp+78h+phkResult], rax; phkResult
0x1800b32b4  xor     r8d, r8d; ulOptions
0x1800b32b7  lea     rdx, aDiskassessment; "DiskAssessment"
0x1800b32be  mov     rcx, [rcx+598h]; hKey
0x1800b32c5  call    cs:__imp_RegOpenKeyExW
0x1800b32cb  test    eax, eax
0x1800b32cd  jnz     short loc_1800B32FB
0x1800b32cf  mov     rcx, [rbp+hKey]
0x1800b32d3  lea     rax, [rbp+arg_8]
0x1800b32d7  mov     r9d, 4
0x1800b32dd  mov     [rsp+78h+phkResult], rax
0x1800b32e2  mov     r8d, r9d
0x1800b32e5  lea     rdx, aRpm; "RPM"
0x1800b32ec  call    PfsRegQueryValue
0x1800b32f1  test    eax, eax
0x1800b32f3  jnz     short loc_1800B32FB
0x1800b32f5  mov     eax, [rbp+arg_8]
0x1800b32f8  mov     [rbx+6Ch], eax
0x1800b32fb  cmp     [rbx+6Ch], edi
0x1800b32fe  jnz     short loc_1800B3303
0x1800b3300  or      [rbx+68h], esi
0x1800b3303  mov     rcx, [rbp+KeyHandle]; Handle
0x1800b3307  test    rcx, rcx
0x1800b330a  jz      short loc_1800B3312
0x1800b330c  call    cs:__imp_NtClose
0x1800b3312  mov     rcx, [rbp+hKey]; hKey
0x1800b3316  test    rcx, rcx
0x1800b3319  jz      short loc_1800B3321
0x1800b331b  call    cs:__imp_RegCloseKey
0x1800b3321  add     rsp, 78h
0x1800b3325  pop     rdi
0x1800b3326  pop     rsi
0x1800b3327  pop     rbx
0x1800b3328  pop     rbp
0x1800b3329  retn
```
