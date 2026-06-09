# BaseSrvSxsInitializeActivationContextCache

- ea: `0x180006834`
- end: `0x180006a12`
- name: `BaseSrvSxsInitializeActivationContextCache`
- size: `478`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800066f0`

## callees

- `0x180006834`
- `0x180006cf0`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x180006877`
- `ntdll!RtlInitializeCriticalSection` at `0x180006877`
- `ntdll!RtlAllocateHeap` at `0x1800068a0`
- `ntdll!RtlAllocateHeap` at `0x1800068a0`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800068e3`
- `ntdll!RtlInitializeGenericTableAvl` at `0x1800068e3`
- `ntdll!RtlInitUnicodeString` at `0x18000691a`
- `ntdll!RtlInitUnicodeString` at `0x18000698b`
- `ntdll!RtlInitUnicodeString` at `0x18000691a`
- `ntdll!RtlInitUnicodeString` at `0x18000698b`
- `ntdll!NtOpenKey` at `0x18000695c`
- `ntdll!NtOpenKey` at `0x18000695c`
- `ntdll!NtQueryValueKey` at `0x1800069bd`
- `ntdll!NtQueryValueKey` at `0x1800069bd`

## string_xrefs

- `0x18000690f`: `\Registry\MACHINE\Software\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 BaseSrvSxsInitializeActivationContextCache()
{
  NTSTATUS v0; // ebx
  struct _RTL_AVL_TABLE *Heap; // rax
  PRTL_AVL_TABLE v2; // rax
  NTSTATUS v3; // eax
  NTSTATUS v4; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-1h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+78h] [rbp+2Fh] BYREF
  int v10; // [rsp+7Ch] [rbp+33h]
  int v11; // [rsp+80h] [rbp+37h]
  __int64 v12; // [rsp+84h] [rbp+3Bh]

  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v0 = RtlInitializeCriticalSection(&SxsActCtxCacheCS);
  if ( v0 >= 0 )
  {
    Heap = (struct _RTL_AVL_TABLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x78u);
    g_SxsActCtxCache = Heap;
    if ( Heap )
    {
      RtlInitializeGenericTableAvl(
        Heap,
        (PRTL_AVL_COMPARE_ROUTINE)BaseSrvActivationContextCacheCompareEntries,
        BaseSrvActivationContextCacheAVLTableAllocate,
        BaseSrvActivationContextCacheAVLTableFree,
        0);
      v2 = g_SxsActCtxCache + 1;
      g_SxsActCtxCache[1].BalancedRoot.LeftChild = &g_SxsActCtxCache[1].BalancedRoot;
      v2->BalancedRoot.Parent = &v2->BalancedRoot;
      if ( !g_SxsRegKeyHandle )
      {
        RtlInitUnicodeString(
          &DestinationString,
          L"\\Registry\\MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion\\SideBySide");
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v3 = NtOpenKey(&g_SxsRegKeyHandle, 0x20019u, &ObjectAttributes);
        v0 = v3;
        if ( v3 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, L"PublisherPolicyChangeTime");
          v4 = NtQueryValueKey(
                 g_SxsRegKeyHandle,
                 &DestinationString,
                 KeyValuePartialInformation,
                 KeyValueInformation,
                 0x18u,
                 &ResultLength);
          if ( v4 >= 0 )
          {
            v0 = v4;
            if ( v10 == 11 && v11 == 8 )
              g_SxsPublihserPolicyChangeTime = v12;
          }
          else
          {
            v0 = 0;
            if ( v4 != -1073741772 )
              return (unsigned int)v4;
          }
        }
        else if ( v3 == -1073741772 || v3 == -1073741766 )
        {
          return 0;
        }
      }
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180006834  mov     [rsp-8+arg_0], rbx
0x180006839  push    rbp
0x18000683a  lea     rbp, [rsp-57h]
0x18000683f  sub     rsp, 0A0h
0x180006846  mov     rax, cs:__security_cookie
0x18000684d  xor     rax, rsp
0x180006850  mov     [rbp+57h+var_10], rax
0x180006854  xorps   xmm0, xmm0
0x180006857  mov     [rbp+57h+var_70], 0
0x18000685e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180006862  xor     eax, eax
0x180006864  lea     rcx, SxsActCtxCacheCS; CriticalSection
0x18000686b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000686f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180006873  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180006877  call    cs:__imp_RtlInitializeCriticalSection
0x18000687e  nop     dword ptr [rax+rax+00h]
0x180006883  mov     ebx, eax
0x180006885  test    eax, eax
0x180006887  js      loc_1800069F2
0x18000688d  mov     rcx, gs:60h
0x180006896  xor     edx, edx; Flags
0x180006898  mov     rcx, [rcx+30h]; HeapHandle
0x18000689c  lea     r8d, [rdx+78h]; Size
0x1800068a0  call    cs:__imp_RtlAllocateHeap
0x1800068a7  nop     dword ptr [rax+rax+00h]
0x1800068ac  mov     cs:g_SxsActCtxCache, rax
0x1800068b3  test    rax, rax
0x1800068b6  jnz     short loc_1800068C2
0x1800068b8  mov     ebx, 0C0000017h
0x1800068bd  jmp     loc_1800069F2
0x1800068c2  lea     r9, BaseSrvActivationContextCacheAVLTableFree; FreeRoutine
0x1800068c9  mov     [rsp+0A0h+TableContext], 0; TableContext
0x1800068d2  lea     r8, BaseSrvActivationContextCacheAVLTableAllocate; AllocateRoutine
0x1800068d9  mov     rcx, rax; Table
0x1800068dc  lea     rdx, BaseSrvActivationContextCacheCompareEntries; CompareRoutine
0x1800068e3  call    cs:__imp_RtlInitializeGenericTableAvl
0x1800068ea  nop     dword ptr [rax+rax+00h]
0x1800068ef  mov     rax, cs:g_SxsActCtxCache
0x1800068f6  add     rax, 68h ; 'h'
0x1800068fa  mov     [rax+8], rax
0x1800068fe  mov     [rax], rax
0x180006901  cmp     cs:g_SxsRegKeyHandle, 0
0x180006909  jnz     loc_1800069F2
0x18000690f  lea     rdx, aRegistryMachin; "\\Registry\\MACHINE\\Software\\Microsof"...
0x180006916  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000691a  call    cs:__imp_RtlInitUnicodeString
0x180006921  nop     dword ptr [rax+rax+00h]
0x180006926  lea     rax, [rbp+57h+DestinationString]
0x18000692a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180006931  xorps   xmm0, xmm0
0x180006934  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180006938  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000693c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180006944  mov     edx, 20019h; DesiredAccess
0x180006949  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180006950  lea     rcx, g_SxsRegKeyHandle; KeyHandle
0x180006957  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000695c  call    cs:__imp_NtOpenKey
0x180006963  nop     dword ptr [rax+rax+00h]
0x180006968  mov     ebx, eax
0x18000696a  test    eax, eax
0x18000696c  jns     short loc_180006980
0x18000696e  cmp     eax, 0C0000034h
0x180006973  jz      short loc_18000697C
0x180006975  cmp     eax, 0C000003Ah
0x18000697a  jnz     short loc_1800069F2
0x18000697c  xor     ebx, ebx
0x18000697e  jmp     short loc_1800069F2
0x180006980  lea     rdx, SourceString; "PublisherPolicyChangeTime"
0x180006987  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000698b  call    cs:__imp_RtlInitUnicodeString
0x180006992  nop     dword ptr [rax+rax+00h]
0x180006997  mov     rcx, cs:g_SxsRegKeyHandle; KeyHandle
0x18000699e  lea     rax, [rbp+57h+var_70]
0x1800069a2  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x1800069a7  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800069ab  mov     r8d, 2; KeyValueInformationClass
0x1800069b1  mov     dword ptr [rsp+0A0h+TableContext], 18h; Length
0x1800069b9  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800069bd  call    cs:__imp_NtQueryValueKey
0x1800069c4  nop     dword ptr [rax+rax+00h]
0x1800069c9  test    eax, eax
0x1800069cb  jns     short loc_1800069D9
0x1800069cd  xor     ebx, ebx
0x1800069cf  cmp     eax, 0C0000034h
0x1800069d4  cmovnz  ebx, eax
0x1800069d7  jmp     short loc_1800069F2
0x1800069d9  cmp     [rbp+57h+var_24], 0Bh
0x1800069dd  mov     ebx, eax
0x1800069df  jnz     short loc_1800069F2
0x1800069e1  cmp     [rbp+57h+var_20], 8
0x1800069e5  jnz     short loc_1800069F2
0x1800069e7  mov     rax, [rbp+57h+var_1C]
0x1800069eb  mov     cs:g_SxsPublihserPolicyChangeTime, rax
0x1800069f2  mov     eax, ebx
0x1800069f4  mov     rcx, [rbp+57h+var_10]
0x1800069f8  xor     rcx, rsp; StackCookie
0x1800069fb  call    __security_check_cookie
0x180006a00  mov     rbx, [rsp+0A0h+arg_0]
0x180006a08  add     rsp, 0A0h
0x180006a0f  pop     rbp
0x180006a10  retn
```
