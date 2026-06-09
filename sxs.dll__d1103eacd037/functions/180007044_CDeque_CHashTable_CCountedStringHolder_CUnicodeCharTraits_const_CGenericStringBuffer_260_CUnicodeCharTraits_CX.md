# CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::~CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>(void)

- ea: `0x180007044`
- end: `0x18000707e`
- name: `??1?$CDeque@VCBucket@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@$0CEA@@@QEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180006840`
- `0x180007084`
- `0x180014068`
- `0x180036c88`
- `0x180036dc0`
- `0x18004ac00`
- `0x180056464`
- `0x180056788`
- `0x18005d580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000704d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000704d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007063`

## pseudocode

```c
void __fastcall CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>::~CDeque<CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::CBucket,576>(
        __int64 a1)
{
  DWORD LastError; // eax

  LastError = GetLastError();
  *(_QWORD *)(a1 + 32) = 0;
  SetLastError(LastError);
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180007044  push    rbx
0x180007046  sub     rsp, 20h
0x18000704a  mov     rbx, rcx
0x18000704d  call    cs:__imp_GetLastError
0x180007054  nop     dword ptr [rax+rax+00h]
0x180007059  mov     ecx, eax; dwErrCode
0x18000705b  mov     qword ptr [rbx+20h], 0
0x180007063  call    cs:__imp_SetLastError
0x18000706a  nop     dword ptr [rax+rax+00h]
0x18000706f  mov     qword ptr [rbx+10h], 0
0x180007077  add     rsp, 20h
0x18000707b  pop     rbx
0x18000707c  retn
```
