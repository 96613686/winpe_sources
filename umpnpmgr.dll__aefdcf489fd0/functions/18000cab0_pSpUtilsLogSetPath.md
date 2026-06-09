# _pSpUtilsLogSetPath

- ea: `0x18000cab0`
- end: `0x18000cb99`
- name: `_pSpUtilsLogSetPath`
- size: `233`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180016424`
- `0x1800164e0`

## callees

- `0x18000cab0`
- `0x18000cba0`
- `0x180018730`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cad2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cad2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb5a`

## pseudocode

```c
__int64 __fastcall pSpUtilsLogSetPath(__int64 a1)
{
  unsigned int appended; // ebx
  __int64 result; // rax

  if ( InstallLogFilePath )
  {
    HeapFree(hHeap, 0, InstallLogFilePath);
    InstallLogFilePath = 0;
  }
  appended = pSetupAppendPath(a1, L"setupapi.ev1", &InstallLogFilePath);
  if ( !appended )
    goto LABEL_10;
  if ( EventLogFilePath )
  {
    HeapFree(hHeap, 0, EventLogFilePath);
    EventLogFilePath = 0;
  }
  appended = pSetupAppendPath(a1, L"setupapi.ev2", &EventLogFilePath);
  if ( !appended )
    goto LABEL_10;
  if ( StringLogFilePath )
  {
    HeapFree(hHeap, 0, StringLogFilePath);
    StringLogFilePath = 0;
  }
  result = pSetupAppendPath(a1, L"setupapi.ev3", &StringLogFilePath);
  appended = result;
  if ( !(_DWORD)result )
  {
LABEL_10:
    pSpUtilsInstallLogUninitialize();
    return appended;
  }
  return result;
}

```

## disassembly

```asm
0x18000cab0  mov     [rsp+arg_0], rbx
0x18000cab5  push    rdi
0x18000cab6  sub     rsp, 20h
0x18000caba  mov     r8, cs:InstallLogFilePath; lpMem
0x18000cac1  mov     rdi, rcx
0x18000cac4  test    r8, r8
0x18000cac7  jz      short loc_18000CAE3
0x18000cac9  mov     rcx, cs:hHeap; hHeap
0x18000cad0  xor     edx, edx; dwFlags
0x18000cad2  call    cs:__imp_HeapFree
0x18000cad8  mov     cs:InstallLogFilePath, 0
0x18000cae3  lea     r8, InstallLogFilePath
0x18000caea  mov     rcx, rdi
0x18000caed  lea     rdx, aSetupapiEv1; "setupapi.ev1"
0x18000caf4  call    pSetupAppendPath
0x18000caf9  mov     ebx, eax
0x18000cafb  test    eax, eax
0x18000cafd  jz      loc_18000CB87
0x18000cb03  mov     r8, cs:EventLogFilePath; lpMem
0x18000cb0a  test    r8, r8
0x18000cb0d  jz      short loc_18000CB29
0x18000cb0f  mov     rcx, cs:hHeap; hHeap
0x18000cb16  xor     edx, edx; dwFlags
0x18000cb18  call    cs:__imp_HeapFree
0x18000cb1e  mov     cs:EventLogFilePath, 0
0x18000cb29  lea     r8, EventLogFilePath
0x18000cb30  mov     rcx, rdi
0x18000cb33  lea     rdx, aSetupapiEv2; "setupapi.ev2"
0x18000cb3a  call    pSetupAppendPath
0x18000cb3f  mov     ebx, eax
0x18000cb41  test    eax, eax
0x18000cb43  jz      short loc_18000CB87
0x18000cb45  mov     r8, cs:StringLogFilePath; lpMem
0x18000cb4c  test    r8, r8
0x18000cb4f  jz      short loc_18000CB6B
0x18000cb51  mov     rcx, cs:hHeap; hHeap
0x18000cb58  xor     edx, edx; dwFlags
0x18000cb5a  call    cs:__imp_HeapFree
0x18000cb60  mov     cs:StringLogFilePath, 0
0x18000cb6b  lea     r8, StringLogFilePath
0x18000cb72  mov     rcx, rdi
0x18000cb75  lea     rdx, aSetupapiEv3; "setupapi.ev3"
0x18000cb7c  call    pSetupAppendPath
0x18000cb81  mov     ebx, eax
0x18000cb83  test    eax, eax
0x18000cb85  jnz     short loc_18000CB8E
0x18000cb87  call    _pSpUtilsInstallLogUninitialize
0x18000cb8c  mov     eax, ebx
0x18000cb8e  mov     rbx, [rsp+28h+arg_0]
0x18000cb93  add     rsp, 20h
0x18000cb97  pop     rdi
0x18000cb98  retn
```
