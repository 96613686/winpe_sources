# WMCommListInsert

- ea: `0x14000b9bc`
- end: `0x14000bb7f`
- name: `WMCommListInsert`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b070`

## callees

- `0x14000b8b0`
- `0x14000b9bc`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x14000ba75`
- `ntoskrnl!ZwOpenProcess` at `0x14000ba75`
- `ntoskrnl!ZwClose` at `0x14000bb33`
- `ntoskrnl!ZwClose` at `0x14000bb4d`
- `ntoskrnl!ZwClose` at `0x14000bb33`
- `ntoskrnl!ZwClose` at `0x14000bb4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bb61`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ba01`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ba01`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14000bac3`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14000bac3`
- `FLTMGR!FltReleaseResource` at `0x14000bb1e`
- `FLTMGR!FltReleaseResource` at `0x14000bb1e`

## pseudocode

```c
__int64 __fastcall WMCommListInsert(_OWORD *a1, _QWORD *a2, unsigned int a3, _DWORD *a4)
{
  unsigned __int64 v4; // rsi
  char *PoolWithTag; // rax
  char *v9; // rbx
  NTSTATUS v10; // edi
  _QWORD *v11; // rax
  void *v12; // rcx
  void *ProcessHandle; // [rsp+20h] [rbp-50h] BYREF
  _CLIENT_ID ClientId; // [rsp+28h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-38h] BYREF

  v4 = a3;
  ProcessHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  ClientId = 0;
  PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x40u, 0x574D6365u);
  v9 = PoolWithTag;
  if ( PoolWithTag )
  {
    *((_DWORD *)PoolWithTag + 4) = 1;
    *((_QWORD *)PoolWithTag + 6) = 0;
    *((_DWORD *)PoolWithTag + 14) = 0;
    ClientId.UniqueThread = 0;
    ClientId.UniqueProcess = (HANDLE)v4;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    v10 = ZwOpenProcess(&ProcessHandle, 0x40u, &ObjectAttributes, &ClientId);
    if ( v10 >= 0 )
    {
      *(_OWORD *)(v9 + 20) = *a1;
      *((_QWORD *)v9 + 5) = *a2;
      *((_QWORD *)v9 + 6) = ProcessHandle;
      *((_DWORD *)v9 + 14) = v4;
      *((_DWORD *)v9 + 15) = *a4;
      ProcessHandle = 0;
      *a2 = 0;
      FltAcquireResourceExclusive(&stru_1400061E0);
      if ( PriGetEntry(MatchByGuid, a1) )
      {
        v10 = -1073740024;
      }
      else
      {
        v11 = (_QWORD *)qword_1400061D8;
        if ( *(PVOID **)qword_1400061D8 != &g_CommList )
          __fastfail(3u);
        *(_QWORD *)v9 = &g_CommList;
        *((_QWORD *)v9 + 1) = v11;
        *v11 = v9;
        qword_1400061D8 = (__int64)v9;
        v9 = 0;
      }
      FltReleaseResource(&stru_1400061E0);
    }
  }
  else
  {
    v10 = -1073741670;
  }
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( v9 )
  {
    v12 = (void *)*((_QWORD *)v9 + 6);
    if ( v12 )
      ZwClose(v12);
    ExFreePoolWithTag(v9, 0x574D6365u);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000b9bc  push    rbp
0x14000b9be  push    rbx
0x14000b9bf  push    rsi
0x14000b9c0  push    rdi
0x14000b9c1  push    r12
0x14000b9c3  push    r14
0x14000b9c5  push    r15
0x14000b9c7  mov     rbp, rsp
0x14000b9ca  sub     rsp, 70h
0x14000b9ce  xorps   xmm0, xmm0
0x14000b9d1  mov     esi, r8d
0x14000b9d4  xor     eax, eax
0x14000b9d6  mov     r14, rdx
0x14000b9d9  mov     r15, rcx
0x14000b9dc  mov     [rbp+ProcessHandle], rax
0x14000b9e0  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000b9e4  mov     r8d, 574D6365h; Tag
0x14000b9ea  mov     r12, r9
0x14000b9ed  lea     edi, [rax+40h]
0x14000b9f0  mov     edx, edi; NumberOfBytes
0x14000b9f2  lea     ecx, [rax+1]; PoolType
0x14000b9f5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000b9f9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000b9fd  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x14000ba01  call    cs:__imp_ExAllocatePoolWithTag
0x14000ba08  nop     dword ptr [rax+rax+00h]
0x14000ba0d  mov     rbx, rax
0x14000ba10  test    rax, rax
0x14000ba13  jnz     short loc_14000BA1F
0x14000ba15  mov     edi, 0C000009Ah
0x14000ba1a  jmp     loc_14000BB2A
0x14000ba1f  mov     dword ptr [rax+10h], 1
0x14000ba26  lea     r9, [rbp+ClientId]; ClientId
0x14000ba2a  mov     qword ptr [rax+30h], 0
0x14000ba32  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000ba36  mov     dword ptr [rax+38h], 0
0x14000ba3d  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x14000ba41  xorps   xmm0, xmm0
0x14000ba44  mov     [rbp+ClientId.UniqueThread], 0
0x14000ba4c  mov     edx, edi; DesiredAccess
0x14000ba4e  mov     [rbp+ClientId.UniqueProcess], rsi
0x14000ba52  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ba57  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000ba5e  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000ba66  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14000ba6d  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14000ba75  call    cs:__imp_ZwOpenProcess
0x14000ba7c  nop     dword ptr [rax+rax+00h]
0x14000ba81  mov     edi, eax
0x14000ba83  test    eax, eax
0x14000ba85  js      loc_14000BB2A
0x14000ba8b  movups  xmm0, xmmword ptr [r15]
0x14000ba8f  movdqu  xmmword ptr [rbx+14h], xmm0
0x14000ba94  mov     rcx, [r14]
0x14000ba97  mov     [rbx+28h], rcx
0x14000ba9b  mov     rcx, [rbp+ProcessHandle]
0x14000ba9f  mov     [rbx+30h], rcx
0x14000baa3  mov     [rbx+38h], esi
0x14000baa6  mov     ecx, [r12]
0x14000baaa  mov     [rbx+3Ch], ecx
0x14000baad  lea     rcx, stru_1400061E0; Resource
0x14000bab4  mov     [rbp+ProcessHandle], 0
0x14000babc  mov     qword ptr [r14], 0
0x14000bac3  call    cs:__imp_FltAcquireResourceExclusive
0x14000baca  nop     dword ptr [rax+rax+00h]
0x14000bacf  mov     rdx, r15
0x14000bad2  lea     rcx, MatchByGuid
0x14000bad9  call    PriGetEntry
0x14000bade  test    rax, rax
0x14000bae1  jz      short loc_14000BAEA
0x14000bae3  mov     edi, 0C0000708h
0x14000bae8  jmp     short loc_14000BB17
0x14000baea  mov     rax, cs:qword_1400061D8
0x14000baf1  lea     rcx, g_CommList
0x14000baf8  cmp     [rax], rcx
0x14000bafb  jz      short loc_14000BB04
0x14000bafd  mov     ecx, 3
0x14000bb02  int     29h; Win8: RtlFailFast(ecx)
0x14000bb04  mov     [rbx], rcx
0x14000bb07  mov     [rbx+8], rax
0x14000bb0b  mov     [rax], rbx
0x14000bb0e  mov     cs:qword_1400061D8, rbx
0x14000bb15  xor     ebx, ebx
0x14000bb17  lea     rcx, stru_1400061E0; Resource
0x14000bb1e  call    cs:__imp_FltReleaseResource
0x14000bb25  nop     dword ptr [rax+rax+00h]
0x14000bb2a  mov     rcx, [rbp+ProcessHandle]; Handle
0x14000bb2e  test    rcx, rcx
0x14000bb31  jz      short loc_14000BB3F
0x14000bb33  call    cs:__imp_ZwClose
0x14000bb3a  nop     dword ptr [rax+rax+00h]
0x14000bb3f  test    rbx, rbx
0x14000bb42  jz      short loc_14000BB6D
0x14000bb44  mov     rcx, [rbx+30h]; Handle
0x14000bb48  test    rcx, rcx
0x14000bb4b  jz      short loc_14000BB59
0x14000bb4d  call    cs:__imp_ZwClose
0x14000bb54  nop     dword ptr [rax+rax+00h]
0x14000bb59  mov     edx, 574D6365h; Tag
0x14000bb5e  mov     rcx, rbx; P
0x14000bb61  call    cs:__imp_ExFreePoolWithTag
0x14000bb68  nop     dword ptr [rax+rax+00h]
0x14000bb6d  mov     eax, edi
0x14000bb6f  add     rsp, 70h
0x14000bb73  pop     r15
0x14000bb75  pop     r14
0x14000bb77  pop     r12
0x14000bb79  pop     rdi
0x14000bb7a  pop     rsi
0x14000bb7b  pop     rbx
0x14000bb7c  pop     rbp
0x14000bb7d  retn
```
