# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::CreateLogicalProcessorInfo(_LOGICAL_PROCESSOR_RELATIONSHIP,_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX * *)

- ea: `0x180001e50`
- end: `0x180001f2b`
- name: `?CreateLogicalProcessorInfo@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@AEAAJW4_LOGICAL_PROCESSOR_RELATIONSHIP@@PEAPEAU_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *__hidden this, enum _LOGICAL_PROCESSOR_RELATIONSHIP, struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ddc`

## callees

- `0x180001e50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001efe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001e9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001efe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001eab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001eab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001f0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ee0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ee0`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180001e7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180001ed6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180001e7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLogicalProcessorInformationEx` at `0x180001ed6`

## pseudocode

```c
__int64 __fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::CreateLogicalProcessorInfo(
        AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *this,
        enum _LOGICAL_PROCESSOR_RELATIONSHIP a2,
        struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX **a3)
{
  struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *v4; // rbx
  signed int v5; // edi
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  bool v9; // sf
  signed int LastError; // eax
  HANDLE v11; // rax
  DWORD ReturnedLength; // [rsp+38h] [rbp+10h] BYREF

  ReturnedLength = 0;
  v4 = 0;
  if ( GetLogicalProcessorInformationEx(RelationGroup, 0, &ReturnedLength) )
  {
LABEL_8:
    if ( GetLogicalProcessorInformationEx(RelationGroup, v4, &ReturnedLength) )
    {
      result = 0;
      *a3 = v4;
      return result;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError <= 0 )
      goto LABEL_12;
    v5 = (unsigned __int16)LastError;
LABEL_11:
    v5 |= 0x80070000;
LABEL_12:
    v9 = v5 < 0;
    goto LABEL_13;
  }
  v5 = GetLastError();
  if ( v5 == 122 )
  {
    if ( ReturnedLength )
    {
      v6 = ReturnedLength;
      ProcessHeap = GetProcessHeap();
      v4 = (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX *)HeapAlloc(ProcessHeap, 0, v6);
      if ( !v4 )
        return 2147942522LL;
      goto LABEL_8;
    }
LABEL_7:
    v5 = (unsigned __int16)v5;
    goto LABEL_11;
  }
  v9 = v5 < 0;
  if ( v5 > 0 )
    goto LABEL_7;
LABEL_13:
  if ( v9 )
  {
    if ( v4 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v4);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001e50  mov     [rsp+arg_0], rbx
0x180001e55  mov     [rsp+arg_10], rsi
0x180001e5a  mov     [rsp+ReturnedLength], edx
0x180001e5e  push    rdi
0x180001e5f  sub     rsp, 20h
0x180001e63  mov     rsi, r8
0x180001e66  mov     [rsp+28h+ReturnedLength], 0
0x180001e6e  lea     r8, [rsp+28h+ReturnedLength]; ReturnedLength
0x180001e73  xor     edx, edx; Buffer
0x180001e75  mov     ecx, 4; RelationshipType
0x180001e7a  xor     ebx, ebx
0x180001e7c  call    cs:__imp_GetLogicalProcessorInformationEx
0x180001e82  test    eax, eax
0x180001e84  jnz     short loc_180001EC9
0x180001e86  call    cs:__imp_GetLastError
0x180001e8c  mov     edi, eax
0x180001e8e  cmp     eax, 7Ah ; 'z'
0x180001e91  jnz     short loc_180001EC0
0x180001e93  mov     eax, [rsp+28h+ReturnedLength]
0x180001e97  test    eax, eax
0x180001e99  jz      short loc_180001EC4
0x180001e9b  mov     ebx, eax
0x180001e9d  call    cs:__imp_GetProcessHeap
0x180001ea3  mov     r8d, ebx; dwBytes
0x180001ea6  xor     edx, edx; dwFlags
0x180001ea8  mov     rcx, rax; hHeap
0x180001eab  call    cs:__imp_HeapAlloc
0x180001eb1  mov     rbx, rax
0x180001eb4  test    rax, rax
0x180001eb7  jnz     short loc_180001EC9
0x180001eb9  mov     eax, 8007007Ah
0x180001ebe  jmp     short loc_180001F1B
0x180001ec0  test    edi, edi
0x180001ec2  jle     short loc_180001EF7
0x180001ec4  movzx   edi, di
0x180001ec7  jmp     short loc_180001EEF
0x180001ec9  lea     r8, [rsp+28h+ReturnedLength]; ReturnedLength
0x180001ece  mov     rdx, rbx; Buffer
0x180001ed1  mov     ecx, 4; RelationshipType
0x180001ed6  call    cs:__imp_GetLogicalProcessorInformationEx
0x180001edc  test    eax, eax
0x180001ede  jnz     short loc_180001F16
0x180001ee0  call    cs:__imp_GetLastError
0x180001ee6  mov     edi, eax
0x180001ee8  test    eax, eax
0x180001eea  jle     short loc_180001EF5
0x180001eec  movzx   edi, ax
0x180001eef  or      edi, 80070000h
0x180001ef5  test    edi, edi
0x180001ef7  jns     short loc_180001F12
0x180001ef9  test    rbx, rbx
0x180001efc  jz      short loc_180001F12
0x180001efe  call    cs:__imp_GetProcessHeap
0x180001f04  mov     r8, rbx; lpMem
0x180001f07  xor     edx, edx; dwFlags
0x180001f09  mov     rcx, rax; hHeap
0x180001f0c  call    cs:__imp_HeapFree
0x180001f12  mov     eax, edi
0x180001f14  jmp     short loc_180001F1B
0x180001f16  xor     eax, eax
0x180001f18  mov     [rsi], rbx
0x180001f1b  mov     rbx, [rsp+28h+arg_0]
0x180001f20  mov     rsi, [rsp+28h+arg_10]
0x180001f25  add     rsp, 20h
0x180001f29  pop     rdi
0x180001f2a  retn
```
