# BaseSrvSxsInitializeActivationContextCache

- ea: `0x180006764`
- end: `0x180006936`
- name: `BaseSrvSxsInitializeActivationContextCache`
- size: `466`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006620`

## callees

- `0x180006764`
- `0x180006c30`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1800067a2`
- `ntdll!RtlInitializeCriticalSection` at `0x1800067a2`
- `ntdll!RtlAllocateHeap` at `0x1800067cb`
- `ntdll!RtlAllocateHeap` at `0x1800067cb`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18000680a`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18000680a`
- `ntdll!RtlInitUnicodeString` at `0x180006840`
- `ntdll!RtlInitUnicodeString` at `0x1800068ad`
- `ntdll!RtlInitUnicodeString` at `0x180006840`
- `ntdll!RtlInitUnicodeString` at `0x1800068ad`
- `ntdll!NtOpenKey` at `0x18000687e`
- `ntdll!NtOpenKey` at `0x18000687e`
- `ntdll!NtQueryValueKey` at `0x1800068df`
- `ntdll!NtQueryValueKey` at `0x1800068df`

## string_xrefs

- `0x180006835`: `\Registry\MACHINE\Software\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 BaseSrvSxsInitializeActivationContextCache()
{
  unsigned int v0; // edi
  NTSTATUS v1; // ebx
  struct _RTL_AVL_TABLE *Heap; // rax
  PRTL_AVL_TABLE v3; // rax
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-1h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+78h] [rbp+2Fh] BYREF
  int v11; // [rsp+7Ch] [rbp+33h]
  int v12; // [rsp+80h] [rbp+37h]
  __int64 v13; // [rsp+84h] [rbp+3Bh]

  v0 = 0;
  ResultLength = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v1 = RtlInitializeCriticalSection(&SxsActCtxCacheCS);
  if ( v1 >= 0 )
  {
    Heap = (struct _RTL_AVL_TABLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
    g_SxsActCtxCache = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    RtlInitializeGenericTableAvl(
      Heap,
      (PRTL_AVL_COMPARE_ROUTINE)BaseSrvActivationContextCacheCompareEntries,
      BaseSrvActivationContextCacheAVLTableAllocate,
      BaseSrvActivationContextCacheAVLTableFree,
      0);
    v3 = g_SxsActCtxCache + 1;
    g_SxsActCtxCache[1].BalancedRoot.LeftChild = &g_SxsActCtxCache[1].BalancedRoot;
    v3->BalancedRoot.Parent = &v3->BalancedRoot;
    if ( g_SxsRegKeyHandle )
      return (unsigned int)v1;
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtOpenKey(&g_SxsRegKeyHandle, 0x20019u, &ObjectAttributes);
    v1 = v4;
    if ( v4 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"PublisherPolicyChangeTime");
      v5 = NtQueryValueKey(
             g_SxsRegKeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             KeyValueInformation,
             0x18u,
             &ResultLength);
      v1 = v5;
      if ( v5 < 0 )
      {
        if ( v5 != -1073741772 )
          return (unsigned int)v5;
        return v0;
      }
      if ( v11 == 11 && v12 == 8 )
        g_SxsPublihserPolicyChangeTime = v13;
    }
    else if ( v4 == -1073741772 || v4 == -1073741766 )
    {
      return v0;
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180006764  mov     [rsp-8+arg_0], rbx
0x180006769  mov     [rsp-8+arg_8], rdi
0x18000676e  push    rbp
0x18000676f  lea     rbp, [rsp-57h]
0x180006774  sub     rsp, 0A0h
0x18000677b  mov     rax, cs:__security_cookie
0x180006782  xor     rax, rsp
0x180006785  mov     [rbp+57h+var_10], rax
0x180006789  xor     edi, edi
0x18000678b  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x180006792  xorps   xmm0, xmm0
0x180006795  mov     [rbp+57h+var_70], edi
0x180006798  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000679c  mov     dword ptr [rbp+57h+ObjectAttributes+4], edi
0x18000679f  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], edi
0x1800067a2  call    cs:__imp_RtlInitializeCriticalSection
0x1800067a9  nop     dword ptr [rax+rax+00h]
0x1800067ae  mov     ebx, eax
0x1800067b0  test    eax, eax
0x1800067b2  js      loc_180006912
0x1800067b8  mov     rcx, gs:60h
0x1800067c1  lea     r8d, [rdi+78h]; Size
0x1800067c5  xor     edx, edx; Flags
0x1800067c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800067cb  call    cs:__imp_RtlAllocateHeap
0x1800067d2  nop     dword ptr [rax+rax+00h]
0x1800067d7  mov     cs:g_SxsActCtxCache, rax
0x1800067de  test    rax, rax
0x1800067e1  jnz     short loc_1800067ED
0x1800067e3  mov     ebx, 0C0000017h
0x1800067e8  jmp     loc_180006912
0x1800067ed  lea     r9, BaseSrvActivationContextCacheAVLTableFree; FreeRoutine
0x1800067f4  mov     [rsp+0A0h+TableContext], rdi; TableContext
0x1800067f9  lea     r8, BaseSrvActivationContextCacheAVLTableAllocate; AllocateRoutine
0x180006800  mov     rcx, rax; Table
0x180006803  lea     rdx, BaseSrvActivationContextCacheCompareEntries; CompareRoutine
0x18000680a  call    cs:__imp_RtlInitializeGenericTableAvl
0x180006811  nop     dword ptr [rax+rax+00h]
0x180006816  mov     rax, cs:g_SxsActCtxCache
0x18000681d  add     rax, 68h ; 'h'
0x180006821  mov     [rax+8], rax
0x180006825  mov     [rax], rax
0x180006828  cmp     cs:g_SxsRegKeyHandle, rdi
0x18000682f  jnz     loc_180006912
0x180006835  lea     rdx, aRegistryMachin; "\\Registry\\MACHINE\\Software\\Microsof"...
0x18000683c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180006840  call    cs:__imp_RtlInitUnicodeString
0x180006847  nop     dword ptr [rax+rax+00h]
0x18000684c  lea     rax, [rbp+57h+DestinationString]
0x180006850  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180006857  xorps   xmm0, xmm0
0x18000685a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000685e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180006862  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180006866  mov     edx, 20019h; DesiredAccess
0x18000686b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180006872  lea     rcx, g_SxsRegKeyHandle; KeyHandle
0x180006879  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000687e  call    cs:__imp_NtOpenKey
0x180006885  nop     dword ptr [rax+rax+00h]
0x18000688a  mov     ebx, eax
0x18000688c  test    eax, eax
0x18000688e  jns     short loc_1800068A2
0x180006890  cmp     eax, 0C0000034h
0x180006895  jz      short loc_18000689E
0x180006897  cmp     eax, 0C000003Ah
0x18000689c  jnz     short loc_180006912
0x18000689e  mov     ebx, edi
0x1800068a0  jmp     short loc_180006912
0x1800068a2  lea     rdx, SourceString; "PublisherPolicyChangeTime"
0x1800068a9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800068ad  call    cs:__imp_RtlInitUnicodeString
0x1800068b4  nop     dword ptr [rax+rax+00h]
0x1800068b9  mov     rcx, cs:g_SxsRegKeyHandle; KeyHandle
0x1800068c0  lea     rax, [rbp+57h+var_70]
0x1800068c4  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x1800068c9  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800068cd  mov     r8d, 2; KeyValueInformationClass
0x1800068d3  mov     dword ptr [rsp+0A0h+TableContext], 18h; Length
0x1800068db  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800068df  call    cs:__imp_NtQueryValueKey
0x1800068e6  nop     dword ptr [rax+rax+00h]
0x1800068eb  mov     ebx, eax
0x1800068ed  test    eax, eax
0x1800068ef  jns     short loc_1800068FB
0x1800068f1  cmp     eax, 0C0000034h
0x1800068f6  cmovnz  edi, eax
0x1800068f9  jmp     short loc_18000689E
0x1800068fb  cmp     [rbp+57h+var_24], 0Bh
0x1800068ff  jnz     short loc_180006912
0x180006901  cmp     [rbp+57h+var_20], 8
0x180006905  jnz     short loc_180006912
0x180006907  mov     rax, [rbp+57h+var_1C]
0x18000690b  mov     cs:g_SxsPublihserPolicyChangeTime, rax
0x180006912  mov     eax, ebx
0x180006914  mov     rcx, [rbp+57h+var_10]
0x180006918  xor     rcx, rsp; StackCookie
0x18000691b  call    __security_check_cookie
0x180006920  lea     r11, [rsp+0A0h+var_s0]
0x180006928  mov     rbx, [r11+10h]
0x18000692c  mov     rdi, [r11+18h]
0x180006930  mov     rsp, r11
0x180006933  pop     rbp
0x180006934  retn
```
