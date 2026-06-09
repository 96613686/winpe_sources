# RemoveTracking(void)

- ea: `0x140006f78`
- end: `0x1400071ed`
- name: `?RemoveTracking@@YAJXZ`
- size: `629`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001e50c`

## callees

- `0x140003944`
- `0x140006a18`
- `0x140006b70`
- `0x140006f78`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140007137`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400071a7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140007137`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400071a7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006f9b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000718f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000718f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006ff1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140006ff1`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400070ab`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400070ab`
- `FLTMGR!FltEnumerateInstances` at `0x140006fc7`
- `FLTMGR!FltEnumerateInstances` at `0x140007037`
- `FLTMGR!FltEnumerateInstances` at `0x140006fc7`
- `FLTMGR!FltEnumerateInstances` at `0x140007037`
- `FLTMGR!FltDetachVolume` at `0x1400070cf`
- `FLTMGR!FltDetachVolume` at `0x1400070cf`
- `FLTMGR!FltObjectDereference` at `0x1400070e9`
- `FLTMGR!FltObjectDereference` at `0x140007101`
- `FLTMGR!FltObjectDereference` at `0x14000714f`
- `FLTMGR!FltObjectDereference` at `0x14000716d`
- `FLTMGR!FltObjectDereference` at `0x1400070e9`
- `FLTMGR!FltObjectDereference` at `0x140007101`
- `FLTMGR!FltObjectDereference` at `0x14000714f`
- `FLTMGR!FltObjectDereference` at `0x14000716d`

## pseudocode

```c
__int64 RemoveTracking(void)
{
  PVOID *v0; // rdi
  char v1; // r15
  NTSTATUS v2; // ebx
  SIZE_T v3; // rdi
  PFLT_INSTANCE *PoolWithTag; // rax
  PFLT_INSTANCE *v5; // rbx
  ULONG v6; // eax
  __int64 v7; // r14
  PVOID v8; // rcx
  NTSTATUS VolumeFromInstance; // eax
  NTSTATUS v10; // eax
  ULONG v11; // edx
  __int64 i; // rsi
  PVOID v13; // rcx
  ULONG InstanceListSize; // [rsp+60h] [rbp+30h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  InstanceListSize = 0;
  RetVolume = 0;
  ExAcquireFastMutex(&stru_140019468);
  v1 = 1;
  ReleaseTrackedPathsTable();
  v2 = FltEnumerateInstances(0, (PFLT_FILTER)FilterHandle, 0, 0, &InstanceListSize);
  if ( v2 == -1073741789 )
  {
    v3 = 8LL * InstanceListSize;
    PoolWithTag = (PFLT_INSTANCE *)ExAllocatePoolWithTag((POOL_TYPE)1025, v3, 0x6E6D7377u);
    v5 = PoolWithTag;
    if ( ExPoolZeroingNativelySupported || !PoolWithTag )
    {
      v0 = (PVOID *)PoolWithTag;
      if ( !PoolWithTag )
      {
        WriteLogMessage(3, L"Failed to allocate memory for the filter instances array");
        v2 = -1073741670;
        goto LABEL_19;
      }
    }
    else
    {
      memset(PoolWithTag, 0, v3);
      v0 = (PVOID *)v5;
    }
    v2 = FltEnumerateInstances(0, (PFLT_FILTER)FilterHandle, v5, InstanceListSize, &InstanceListSize);
  }
  if ( v2 < 0 )
  {
    WriteLogMessage(3, L"Failed to enumerate filter instances (0x%08X)", (unsigned int)v2);
    goto LABEL_19;
  }
  v6 = InstanceListSize;
  v7 = 0;
  if ( !InstanceListSize )
  {
LABEL_18:
    ReleaseTrackedVolumesList();
    ExReleaseFastMutex(&stru_140019468);
    v1 = 0;
    goto LABEL_19;
  }
  v8 = Instance;
  while ( 1 )
  {
    if ( v8 && v0[v7] == v8 )
      goto LABEL_17;
    VolumeFromInstance = FltGetVolumeFromInstance((PFLT_INSTANCE)v0[v7], &RetVolume);
    v2 = VolumeFromInstance;
    if ( VolumeFromInstance < 0 )
      break;
    v10 = FltDetachVolume((PFLT_FILTER)FilterHandle, RetVolume, 0);
    v2 = v10;
    if ( v10 < 0 )
    {
      WriteLogMessage(3, L"Failed to detach instance [%p] (0x%08X)", v0[v7], (unsigned int)v10);
      goto LABEL_19;
    }
    FltObjectDereference(RetVolume);
    RetVolume = 0;
    FltObjectDereference(v0[v7]);
    v0[v7] = 0;
    v6 = InstanceListSize;
    v8 = Instance;
LABEL_17:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= v6 )
      goto LABEL_18;
  }
  WriteLogMessage(
    3,
    L"Failed to get volume object from instance [%p] (0x%08X)",
    v0[v7],
    (unsigned int)VolumeFromInstance);
LABEL_19:
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  v11 = InstanceListSize;
  for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
  {
    v13 = v0[i];
    if ( v13 )
    {
      FltObjectDereference(v13);
      v11 = InstanceListSize;
    }
  }
  if ( v0 )
    ExFreePoolWithTag(v0, 0x6E6D7377u);
  if ( v1 )
    ExReleaseFastMutex(&stru_140019468);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140006f78  mov     [rsp-28h+arg_10], rbx
0x140006f7d  push    rbp
0x140006f7e  push    rsi
0x140006f7f  push    rdi
0x140006f80  push    r14
0x140006f82  push    r15
0x140006f84  mov     rbp, rsp
0x140006f87  sub     rsp, 30h
0x140006f8b  xor     edi, edi
0x140006f8d  lea     rcx, stru_140019468; FastMutex
0x140006f94  mov     [rbp+InstanceListSize], edi
0x140006f97  mov     [rbp+RetVolume], rdi
0x140006f9b  call    cs:__imp_ExAcquireFastMutex
0x140006fa2  nop     dword ptr [rax+rax+00h]
0x140006fa7  mov     r15b, 1
0x140006faa  call    ReleaseTrackedPathsTable
0x140006faf  mov     rdx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x140006fb6  lea     rax, [rbp+InstanceListSize]
0x140006fba  xor     r9d, r9d; InstanceListSize
0x140006fbd  mov     [rsp+30h+NumberInstancesReturned], rax; NumberInstancesReturned
0x140006fc2  xor     r8d, r8d; InstanceList
0x140006fc5  xor     ecx, ecx; Volume
0x140006fc7  call    cs:__imp_FltEnumerateInstances
0x140006fce  nop     dword ptr [rax+rax+00h]
0x140006fd3  mov     ebx, eax
0x140006fd5  cmp     eax, 0C0000023h
0x140006fda  jnz     short loc_140007045
0x140006fdc  mov     edi, [rbp+InstanceListSize]
0x140006fdf  mov     r8d, 6E6D7377h; Tag
0x140006fe5  shl     rdi, 3
0x140006fe9  mov     ecx, 401h; PoolType
0x140006fee  mov     rdx, rdi; NumberOfBytes
0x140006ff1  call    cs:__imp_ExAllocatePoolWithTag
0x140006ff8  nop     dword ptr [rax+rax+00h]
0x140006ffd  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140007004  mov     rbx, rax
0x140007007  jnz     short loc_140007062
0x140007009  test    rax, rax
0x14000700c  jz      short loc_140007062
0x14000700e  mov     r8, rdi; Size
0x140007011  xor     edx, edx; Val
0x140007013  mov     rcx, rax; void *
0x140007016  call    memset
0x14000701b  mov     rdi, rbx
0x14000701e  mov     r9d, [rbp+InstanceListSize]; InstanceListSize
0x140007022  lea     rax, [rbp+InstanceListSize]
0x140007026  mov     rdx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x14000702d  mov     r8, rbx; InstanceList
0x140007030  xor     ecx, ecx; Volume
0x140007032  mov     [rsp+30h+NumberInstancesReturned], rax; NumberInstancesReturned
0x140007037  call    cs:__imp_FltEnumerateInstances
0x14000703e  nop     dword ptr [rax+rax+00h]
0x140007043  mov     ebx, eax
0x140007045  test    ebx, ebx
0x140007047  jns     short loc_140007083
0x140007049  mov     r8d, ebx
0x14000704c  lea     rdx, aFailedToEnumer; "Failed to enumerate filter instances (0"...
0x140007053  mov     ecx, 3
0x140007058  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x14000705d  jmp     loc_140007146
0x140007062  mov     rdi, rbx
0x140007065  test    rbx, rbx
0x140007068  jnz     short loc_14000701E
0x14000706a  lea     rdx, aFailedToAlloca_4; "Failed to allocate memory for the filte"...
0x140007071  lea     ecx, [rbx+3]
0x140007074  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140007079  mov     ebx, 0C000009Ah
0x14000707e  jmp     loc_140007146
0x140007083  mov     eax, [rbp+InstanceListSize]
0x140007086  xor     r14d, r14d
0x140007089  test    eax, eax
0x14000708b  jz      loc_14000712B
0x140007091  mov     rcx, cs:Instance
0x140007098  test    rcx, rcx
0x14000709b  jz      short loc_1400070A3
0x14000709d  cmp     [rdi+r14*8], rcx
0x1400070a1  jz      short loc_14000711F
0x1400070a3  mov     rcx, [rdi+r14*8]; Instance
0x1400070a7  lea     rdx, [rbp+RetVolume]; RetVolume
0x1400070ab  call    cs:__imp_FltGetVolumeFromInstance
0x1400070b2  nop     dword ptr [rax+rax+00h]
0x1400070b7  mov     ebx, eax
0x1400070b9  test    eax, eax
0x1400070bb  js      loc_1400071D0
0x1400070c1  mov     rdx, [rbp+RetVolume]; Volume
0x1400070c5  xor     r8d, r8d; InstanceName
0x1400070c8  mov     rcx, cs:?FilterHandle@@3PEAU_FLT_FILTER@@EA; Filter
0x1400070cf  call    cs:__imp_FltDetachVolume
0x1400070d6  nop     dword ptr [rax+rax+00h]
0x1400070db  mov     ebx, eax
0x1400070dd  test    eax, eax
0x1400070df  js      loc_1400071C7
0x1400070e5  mov     rcx, [rbp+RetVolume]; FltObject
0x1400070e9  call    cs:__imp_FltObjectDereference
0x1400070f0  nop     dword ptr [rax+rax+00h]
0x1400070f5  mov     [rbp+RetVolume], 0
0x1400070fd  mov     rcx, [rdi+r14*8]; FltObject
0x140007101  call    cs:__imp_FltObjectDereference
0x140007108  nop     dword ptr [rax+rax+00h]
0x14000710d  mov     qword ptr [rdi+r14*8], 0
0x140007115  mov     eax, [rbp+InstanceListSize]
0x140007118  mov     rcx, cs:Instance
0x14000711f  inc     r14d
0x140007122  cmp     r14d, eax
0x140007125  jb      loc_140007098
0x14000712b  call    ReleaseTrackedVolumesList
0x140007130  lea     rcx, stru_140019468; FastMutex
0x140007137  call    cs:__imp_ExReleaseFastMutex
0x14000713e  nop     dword ptr [rax+rax+00h]
0x140007143  xor     r15b, r15b
0x140007146  mov     rcx, [rbp+RetVolume]; FltObject
0x14000714a  test    rcx, rcx
0x14000714d  jz      short loc_14000715B
0x14000714f  call    cs:__imp_FltObjectDereference
0x140007156  nop     dword ptr [rax+rax+00h]
0x14000715b  mov     edx, [rbp+InstanceListSize]
0x14000715e  xor     esi, esi
0x140007160  test    edx, edx
0x140007162  jz      short loc_140007182
0x140007164  mov     rcx, [rdi+rsi*8]; FltObject
0x140007168  test    rcx, rcx
0x14000716b  jz      short loc_14000717C
0x14000716d  call    cs:__imp_FltObjectDereference
0x140007174  nop     dword ptr [rax+rax+00h]
0x140007179  mov     edx, [rbp+InstanceListSize]
0x14000717c  inc     esi
0x14000717e  cmp     esi, edx
0x140007180  jb      short loc_140007164
0x140007182  test    rdi, rdi
0x140007185  jz      short loc_14000719B
0x140007187  mov     edx, 6E6D7377h; Tag
0x14000718c  mov     rcx, rdi; P
0x14000718f  call    cs:__imp_ExFreePoolWithTag
0x140007196  nop     dword ptr [rax+rax+00h]
0x14000719b  test    r15b, r15b
0x14000719e  jz      short loc_1400071B3
0x1400071a0  lea     rcx, stru_140019468; FastMutex
0x1400071a7  call    cs:__imp_ExReleaseFastMutex
0x1400071ae  nop     dword ptr [rax+rax+00h]
0x1400071b3  mov     eax, ebx
0x1400071b5  mov     rbx, [rsp+30h+arg_10]
0x1400071ba  add     rsp, 30h
0x1400071be  pop     r15
0x1400071c0  pop     r14
0x1400071c2  pop     rdi
0x1400071c3  pop     rsi
0x1400071c4  pop     rbp
0x1400071c5  retn
0x1400071c7  lea     rdx, aFailedToDetach; "Failed to detach instance [%p] (0x%08X)"
0x1400071ce  jmp     short loc_1400071D7
0x1400071d0  lea     rdx, aFailedToGetVol; "Failed to get volume object from instan"...
0x1400071d7  mov     r8, [rdi+r14*8]
0x1400071db  mov     r9d, eax
0x1400071de  mov     ecx, 3
0x1400071e3  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400071e8  jmp     loc_140007146
```
