# WMCommListInsert

- ea: `0x14000ba5c`
- end: `0x14000bc1f`
- name: `WMCommListInsert`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000b110`

## callees

- `0x14000b950`
- `0x14000ba5c`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x14000bb15`
- `ntoskrnl!ZwOpenProcess` at `0x14000bb15`
- `ntoskrnl!ZwClose` at `0x14000bbd3`
- `ntoskrnl!ZwClose` at `0x14000bbed`
- `ntoskrnl!ZwClose` at `0x14000bbd3`
- `ntoskrnl!ZwClose` at `0x14000bbed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bc01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bc01`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000baa1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000baa1`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14000bb63`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14000bb63`
- `FLTMGR!FltReleaseResource` at `0x14000bbbe`
- `FLTMGR!FltReleaseResource` at `0x14000bbbe`

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
0x14000ba5c  push    rbp
0x14000ba5e  push    rbx
0x14000ba5f  push    rsi
0x14000ba60  push    rdi
0x14000ba61  push    r12
0x14000ba63  push    r14
0x14000ba65  push    r15
0x14000ba67  mov     rbp, rsp
0x14000ba6a  sub     rsp, 70h
0x14000ba6e  xorps   xmm0, xmm0
0x14000ba71  mov     esi, r8d
0x14000ba74  xor     eax, eax
0x14000ba76  mov     r14, rdx
0x14000ba79  mov     r15, rcx
0x14000ba7c  mov     [rbp+ProcessHandle], rax
0x14000ba80  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000ba84  mov     r8d, 574D6365h; Tag
0x14000ba8a  mov     r12, r9
0x14000ba8d  lea     edi, [rax+40h]
0x14000ba90  mov     edx, edi; NumberOfBytes
0x14000ba92  lea     ecx, [rax+1]; PoolType
0x14000ba95  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000ba99  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000ba9d  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x14000baa1  call    cs:__imp_ExAllocatePoolWithTag
0x14000baa8  nop     dword ptr [rax+rax+00h]
0x14000baad  mov     rbx, rax
0x14000bab0  test    rax, rax
0x14000bab3  jnz     short loc_14000BABF
0x14000bab5  mov     edi, 0C000009Ah
0x14000baba  jmp     loc_14000BBCA
0x14000babf  mov     dword ptr [rax+10h], 1
0x14000bac6  lea     r9, [rbp+ClientId]; ClientId
0x14000baca  mov     qword ptr [rax+30h], 0
0x14000bad2  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000bad6  mov     dword ptr [rax+38h], 0
0x14000badd  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x14000bae1  xorps   xmm0, xmm0
0x14000bae4  mov     [rbp+ClientId.UniqueThread], 0
0x14000baec  mov     edx, edi; DesiredAccess
0x14000baee  mov     [rbp+ClientId.UniqueProcess], rsi
0x14000baf2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000baf7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000bafe  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000bb06  mov     [rbp+ObjectAttributes.Attributes], 200h
0x14000bb0d  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14000bb15  call    cs:__imp_ZwOpenProcess
0x14000bb1c  nop     dword ptr [rax+rax+00h]
0x14000bb21  mov     edi, eax
0x14000bb23  test    eax, eax
0x14000bb25  js      loc_14000BBCA
0x14000bb2b  movups  xmm0, xmmword ptr [r15]
0x14000bb2f  movdqu  xmmword ptr [rbx+14h], xmm0
0x14000bb34  mov     rcx, [r14]
0x14000bb37  mov     [rbx+28h], rcx
0x14000bb3b  mov     rcx, [rbp+ProcessHandle]
0x14000bb3f  mov     [rbx+30h], rcx
0x14000bb43  mov     [rbx+38h], esi
0x14000bb46  mov     ecx, [r12]
0x14000bb4a  mov     [rbx+3Ch], ecx
0x14000bb4d  lea     rcx, stru_1400061E0; Resource
0x14000bb54  mov     [rbp+ProcessHandle], 0
0x14000bb5c  mov     qword ptr [r14], 0
0x14000bb63  call    cs:__imp_FltAcquireResourceExclusive
0x14000bb6a  nop     dword ptr [rax+rax+00h]
0x14000bb6f  mov     rdx, r15
0x14000bb72  lea     rcx, MatchByGuid
0x14000bb79  call    PriGetEntry
0x14000bb7e  test    rax, rax
0x14000bb81  jz      short loc_14000BB8A
0x14000bb83  mov     edi, 0C0000708h
0x14000bb88  jmp     short loc_14000BBB7
0x14000bb8a  mov     rax, cs:qword_1400061D8
0x14000bb91  lea     rcx, g_CommList
0x14000bb98  cmp     [rax], rcx
0x14000bb9b  jz      short loc_14000BBA4
0x14000bb9d  mov     ecx, 3
0x14000bba2  int     29h; Win8: RtlFailFast(ecx)
0x14000bba4  mov     [rbx], rcx
0x14000bba7  mov     [rbx+8], rax
0x14000bbab  mov     [rax], rbx
0x14000bbae  mov     cs:qword_1400061D8, rbx
0x14000bbb5  xor     ebx, ebx
0x14000bbb7  lea     rcx, stru_1400061E0; Resource
0x14000bbbe  call    cs:__imp_FltReleaseResource
0x14000bbc5  nop     dword ptr [rax+rax+00h]
0x14000bbca  mov     rcx, [rbp+ProcessHandle]; Handle
0x14000bbce  test    rcx, rcx
0x14000bbd1  jz      short loc_14000BBDF
0x14000bbd3  call    cs:__imp_ZwClose
0x14000bbda  nop     dword ptr [rax+rax+00h]
0x14000bbdf  test    rbx, rbx
0x14000bbe2  jz      short loc_14000BC0D
0x14000bbe4  mov     rcx, [rbx+30h]; Handle
0x14000bbe8  test    rcx, rcx
0x14000bbeb  jz      short loc_14000BBF9
0x14000bbed  call    cs:__imp_ZwClose
0x14000bbf4  nop     dword ptr [rax+rax+00h]
0x14000bbf9  mov     edx, 574D6365h; Tag
0x14000bbfe  mov     rcx, rbx; P
0x14000bc01  call    cs:__imp_ExFreePoolWithTag
0x14000bc08  nop     dword ptr [rax+rax+00h]
0x14000bc0d  mov     eax, edi
0x14000bc0f  add     rsp, 70h
0x14000bc13  pop     r15
0x14000bc15  pop     r14
0x14000bc17  pop     r12
0x14000bc19  pop     rdi
0x14000bc1a  pop     rsi
0x14000bc1b  pop     rbx
0x14000bc1c  pop     rbp
0x14000bc1d  retn
```
