# EfiApiInitialize

- ea: `0x180014094`
- end: `0x18001426b`
- name: `EfiApiInitialize`
- size: `471`
- prototype: `__int64()`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013490`
- `0x180013bd0`
- `0x180014274`
- `0x1800142b4`
- `0x180014304`
- `0x180014354`
- `0x1800143a4`
- `0x1800143f4`
- `0x180014444`
- `0x1800145d0`

## callees

- `0x180014040`
- `0x180014094`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800140d9`
- `ntdll!RtlInitUnicodeString` at `0x1800140d9`
- `ntdll!LdrGetDllHandle` at `0x1800140eb`
- `ntdll!LdrGetDllHandle` at `0x1800140eb`

## string_xrefs

- `0x1800140ce`: `ntdll.dll`
- `0x180014124`: `NtDeleteBootEntry`
- `0x18001413b`: `NtDeleteDriverEntry`
- `0x1800141f3`: `NtTranslateFilePath`

## pseudocode

```c
__int64 EfiApiInitialize()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-10h] BYREF
  PVOID DllHandle; // [rsp+48h] [rbp+18h] BYREF

  DllHandle = 0;
  DestinationString = 0;
  while ( _InterlockedCompareExchange(&EfipHaveLock, 1, 0) )
    ;
  if ( !EfipApisInitialized )
  {
    RtlInitUnicodeString(&DestinationString, L"ntdll.dll");
    if ( LdrGetDllHandle(0, 0, &DestinationString, &DllHandle) >= 0 )
    {
      EfipAddBootEntry = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtAddBootEntry");
      EfipAddDriverEntry = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtAddDriverEntry");
      EfipDeleteBootEntry = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtDeleteBootEntry");
      EfipDeleteDriverEntry = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtDeleteDriverEntry");
      EfipEnumerateBootEntries = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtEnumerateBootEntries");
      EfipEnumerateDriverEntries = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtEnumerateDriverEntries");
      EfipModifyBootEntry = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtModifyBootEntry");
      EfipModifyDriverEntry = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtModifyDriverEntry");
      EfipSetBootEntryOrder = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtSetBootEntryOrder");
      EfipSetBootOptions = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtSetBootOptions");
      EfipSetDriverEntryOrder = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtSetDriverEntryOrder");
      EfipTranslateFilePath = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtTranslateFilePath");
      EfipQueryBootEntryOrder = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtQueryBootEntryOrder");
      EfipQueryBootOptions = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtQueryBootOptions");
      EfipQueryDriverEntryOrder = (__int64)EfiApiGetProcedureAddress(DllHandle, "NtQueryDriverEntryOrder");
    }
    EfipApisInitialized = 1;
  }
  return (unsigned int)_InterlockedExchange(&EfipHaveLock, 0);
}

```

## disassembly

```asm
0x180014094  mov     [rsp-8+arg_10], rbx
0x180014099  push    rbp
0x18001409a  mov     rbp, rsp
0x18001409d  sub     rsp, 30h
0x1800140a1  xorps   xmm0, xmm0
0x1800140a4  mov     [rbp+DllHandle], 0
0x1800140ac  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800140b0  mov     ebx, 1
0x1800140b5  xor     eax, eax
0x1800140b7  lock cmpxchg cs:EfipHaveLock, ebx
0x1800140bf  jnz     short loc_1800140B5
0x1800140c1  cmp     cs:EfipApisInitialized, 0
0x1800140c8  jnz     loc_180014258
0x1800140ce  lea     rdx, aNtdllDll_0; "ntdll.dll"
0x1800140d5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800140d9  call    cs:__imp_RtlInitUnicodeString
0x1800140df  lea     r9, [rbp+DllHandle]; DllHandle
0x1800140e3  xor     edx, edx; DllCharacteristics
0x1800140e5  lea     r8, [rbp+DestinationString]; DllName
0x1800140e9  xor     ecx, ecx; DllPath
0x1800140eb  call    cs:__imp_LdrGetDllHandle
0x1800140f1  test    eax, eax
0x1800140f3  js      loc_180014252
0x1800140f9  mov     rcx, [rbp+DllHandle]; BaseAddress
0x1800140fd  lea     rdx, aNtaddbootentry; "NtAddBootEntry"
0x180014104  call    EfiApiGetProcedureAddress
0x180014109  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18001410d  lea     rdx, aNtadddriverent; "NtAddDriverEntry"
0x180014114  mov     cs:EfipAddBootEntry, rax
0x18001411b  call    EfiApiGetProcedureAddress
0x180014120  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180014124  lea     rdx, aNtdeletebooten; "NtDeleteBootEntry"
0x18001412b  mov     cs:EfipAddDriverEntry, rax
0x180014132  call    EfiApiGetProcedureAddress
0x180014137  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18001413b  lea     rdx, aNtdeletedriver; "NtDeleteDriverEntry"
0x180014142  mov     cs:EfipDeleteBootEntry, rax
0x180014149  call    EfiApiGetProcedureAddress
0x18001414e  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180014152  lea     rdx, aNtenumerateboo; "NtEnumerateBootEntries"
0x180014159  mov     cs:EfipDeleteDriverEntry, rax
0x180014160  call    EfiApiGetProcedureAddress
0x180014165  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180014169  lea     rdx, aNtenumeratedri; "NtEnumerateDriverEntries"
0x180014170  mov     cs:EfipEnumerateBootEntries, rax
0x180014177  call    EfiApiGetProcedureAddress
0x18001417c  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180014180  lea     rdx, aNtmodifybooten; "NtModifyBootEntry"
0x180014187  mov     cs:EfipEnumerateDriverEntries, rax
0x18001418e  call    EfiApiGetProcedureAddress
0x180014193  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180014197  lea     rdx, aNtmodifydriver; "NtModifyDriverEntry"
0x18001419e  mov     cs:EfipModifyBootEntry, rax
0x1800141a5  call    EfiApiGetProcedureAddress
0x1800141aa  mov     rcx, [rbp+DllHandle]; BaseAddress
0x1800141ae  lea     rdx, aNtsetbootentry; "NtSetBootEntryOrder"
0x1800141b5  mov     cs:EfipModifyDriverEntry, rax
0x1800141bc  call    EfiApiGetProcedureAddress
0x1800141c1  mov     rcx, [rbp+DllHandle]; BaseAddress
0x1800141c5  lea     rdx, aNtsetbootoptio; "NtSetBootOptions"
0x1800141cc  mov     cs:EfipSetBootEntryOrder, rax
0x1800141d3  call    EfiApiGetProcedureAddress
0x1800141d8  mov     rcx, [rbp+DllHandle]; BaseAddress
0x1800141dc  lea     rdx, aNtsetdriverent; "NtSetDriverEntryOrder"
0x1800141e3  mov     cs:EfipSetBootOptions, rax
0x1800141ea  call    EfiApiGetProcedureAddress
0x1800141ef  mov     rcx, [rbp+DllHandle]; BaseAddress
0x1800141f3  lea     rdx, aNttranslatefil; "NtTranslateFilePath"
0x1800141fa  mov     cs:EfipSetDriverEntryOrder, rax
0x180014201  call    EfiApiGetProcedureAddress
0x180014206  mov     rcx, [rbp+DllHandle]; BaseAddress
0x18001420a  lea     rdx, aNtquerybootent; "NtQueryBootEntryOrder"
0x180014211  mov     cs:EfipTranslateFilePath, rax
0x180014218  call    EfiApiGetProcedureAddress
0x18001421d  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180014221  lea     rdx, aNtquerybootopt; "NtQueryBootOptions"
0x180014228  mov     cs:EfipQueryBootEntryOrder, rax
0x18001422f  call    EfiApiGetProcedureAddress
0x180014234  mov     rcx, [rbp+DllHandle]; BaseAddress
0x180014238  lea     rdx, aNtquerydrivere; "NtQueryDriverEntryOrder"
0x18001423f  mov     cs:EfipQueryBootOptions, rax
0x180014246  call    EfiApiGetProcedureAddress
0x18001424b  mov     cs:EfipQueryDriverEntryOrder, rax
0x180014252  mov     cs:EfipApisInitialized, bl
0x180014258  mov     rbx, [rsp+30h+arg_10]
0x18001425d  xor     eax, eax
0x18001425f  xchg    eax, cs:EfipHaveLock
0x180014265  add     rsp, 30h
0x180014269  pop     rbp
0x18001426a  retn
```
