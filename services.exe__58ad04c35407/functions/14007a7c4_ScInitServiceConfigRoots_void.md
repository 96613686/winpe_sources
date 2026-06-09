# ScInitServiceConfigRoots(void)

- ea: `0x14007a7c4`
- end: `0x14007aa4c`
- name: `?ScInitServiceConfigRoots@@YAKXZ`
- size: `648`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400437bc`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14001f99c`
- `0x140054530`
- `0x14007a248`
- `0x14007a7c4`

## import_xrefs

- `ntdll!NtClose` at `0x14007a884`
- `ntdll!NtClose` at `0x14007a884`
- `ntdll!RtlNtStatusToDosError` at `0x14007a925`
- `ntdll!RtlNtStatusToDosError` at `0x14007a925`
- `ntdll!RtlFreeHeap` at `0x14007a8a1`
- `ntdll!RtlFreeHeap` at `0x14007a8a1`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x14007a840`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x14007a840`
- `ntdll!NtQueryDirectoryObject` at `0x14007a986`
- `ntdll!NtQueryDirectoryObject` at `0x14007a986`
- `ntdll!NtOpenDirectoryObject` at `0x14007a8e6`
- `ntdll!NtOpenDirectoryObject` at `0x14007a8e6`
- `ntdll!RtlAllocateHeap` at `0x14007a94c`
- `ntdll!RtlAllocateHeap` at `0x14007a94c`

## pseudocode

```c
__int64 ScInitServiceConfigRoots(void)
{
  unsigned __int16 *Heap; // rsi
  unsigned int inited; // ebx
  int v3; // ebx
  PRPC_ASYNC_STATE v4; // rcx
  __int64 v5; // rdx
  BOOLEAN RestartScan; // al
  NTSTATUS v7; // eax
  const unsigned __int16 **i; // rdi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ReturnLength; // [rsp+A0h] [rbp+30h] BYREF
  ULONG Context; // [rsp+A8h] [rbp+38h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+40h] BYREF

  Handle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Heap = 0;
  Context = 0;
  ReturnLength = 0;
  inited = ScInitConfigRoot(L"SYSTEM", 6u, 1);
  if ( inited )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 340, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, inited);
    goto LABEL_10;
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 341, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids);
    goto LABEL_9;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)L"$&";
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenDirectoryObject(&Handle, 1u, &ObjectAttributes);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_20;
    v5 = 342;
LABEL_19:
    WPP_SF_d(v4->StubInfo, v5, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids, (unsigned int)v3);
LABEL_20:
    inited = RtlNtStatusToDosError(v3);
    goto LABEL_10;
  }
  inited = 8;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x242u);
  if ( !Heap )
    goto LABEL_10;
  RestartScan = 1;
LABEL_23:
  v7 = NtQueryDirectoryObject(Handle, Heap, 0x242u, 1u, RestartScan, &Context, &ReturnLength);
  v3 = v7;
  if ( v7 == -2147483622 )
  {
LABEL_9:
    inited = 0;
    goto LABEL_10;
  }
  if ( v7 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_20;
    v5 = 343;
    goto LABEL_19;
  }
  for ( i = (const unsigned __int16 **)Heap; ; i += 4 )
  {
    if ( !*(_WORD *)i )
    {
      RestartScan = 0;
      goto LABEL_23;
    }
    if ( wcscmp(i[1], L"SYSTEM") )
    {
      inited = ScInitConfigRoot(i[1], *(unsigned __int16 *)i, 0);
      if ( inited )
        break;
    }
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      344,
      (unsigned int)WPP_e5a68143c9d03da933de77b1bc511594_Traceguids,
      (unsigned int)i[1],
      inited);
LABEL_10:
  if ( Handle )
    NtClose(Handle);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return inited;
}

```

## disassembly

```asm
0x14007a7c4  push    rbp
0x14007a7c6  push    rbx
0x14007a7c7  push    rsi
0x14007a7c8  push    rdi
0x14007a7c9  push    r14
0x14007a7cb  mov     rbp, rsp
0x14007a7ce  sub     rsp, 70h
0x14007a7d2  xor     r14d, r14d
0x14007a7d5  lea     rcx, aSystem; "SYSTEM"
0x14007a7dc  xorps   xmm0, xmm0
0x14007a7df  mov     [rbp+Handle], r14
0x14007a7e3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14007a7e7  mov     esi, r14d
0x14007a7ea  mov     [rbp+arg_8], r14d
0x14007a7ee  lea     edx, [r14+6]; unsigned int
0x14007a7f2  mov     [rbp+arg_0], r14d
0x14007a7f6  lea     r8d, [r14+1]; int
0x14007a7fa  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14007a7fe  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14007a802  call    ?ScInitConfigRoot@@YAKPEBGKH@Z; ScInitConfigRoot(ushort const *,ulong,int)
0x14007a807  mov     ebx, eax
0x14007a809  test    eax, eax
0x14007a80b  jz      short loc_14007A840
0x14007a80d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a814  lea     rax, WPP_GLOBAL_Control
0x14007a81b  cmp     rcx, rax
0x14007a81e  jz      short loc_14007A87B
0x14007a820  test    byte ptr [rcx+1Ch], 1
0x14007a824  jz      short loc_14007A87B
0x14007a826  mov     rcx, [rcx+10h]
0x14007a82a  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a831  mov     edx, 154h
0x14007a836  mov     r9d, ebx
0x14007a839  call    WPP_SF_d
0x14007a83e  jmp     short loc_14007A87B
0x14007a840  call    cs:__imp_RtlGetCurrentServiceSessionId
0x14007a846  test    eax, eax
0x14007a848  jz      short loc_14007A8B4
0x14007a84a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a851  lea     rax, WPP_GLOBAL_Control
0x14007a858  cmp     rcx, rax
0x14007a85b  jz      short loc_14007A878
0x14007a85d  test    byte ptr [rcx+1Ch], 4
0x14007a861  jz      short loc_14007A878
0x14007a863  mov     rcx, [rcx+10h]
0x14007a867  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a86e  mov     edx, 155h
0x14007a873  call    WPP_SF_
0x14007a878  mov     ebx, r14d
0x14007a87b  mov     rcx, [rbp+Handle]; Handle
0x14007a87f  test    rcx, rcx
0x14007a882  jz      short loc_14007A88A
0x14007a884  call    cs:__imp_NtClose
0x14007a88a  test    rsi, rsi
0x14007a88d  jz      short loc_14007A8A7
0x14007a88f  mov     rcx, gs:60h
0x14007a898  mov     r8, rsi; P
0x14007a89b  xor     edx, edx; Flags
0x14007a89d  mov     rcx, [rcx+30h]; HeapHandle
0x14007a8a1  call    cs:__imp_RtlFreeHeap
0x14007a8a7  mov     eax, ebx
0x14007a8a9  add     rsp, 70h
0x14007a8ad  pop     r14
0x14007a8af  pop     rdi
0x14007a8b0  pop     rsi
0x14007a8b1  pop     rbx
0x14007a8b2  pop     rbp
0x14007a8b3  retn
0x14007a8b4  lea     rax, asc_140098728; "$&"
0x14007a8bb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14007a8c2  xorps   xmm0, xmm0
0x14007a8c5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14007a8c9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14007a8cd  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x14007a8d1  mov     edx, 1; DesiredAccess
0x14007a8d6  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14007a8dd  lea     rcx, [rbp+Handle]; FileHandle
0x14007a8e1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14007a8e6  call    cs:__imp_NtOpenDirectoryObject
0x14007a8ec  mov     ebx, eax
0x14007a8ee  test    eax, eax
0x14007a8f0  jns     short loc_14007A932
0x14007a8f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a8f9  lea     rax, WPP_GLOBAL_Control
0x14007a900  cmp     rcx, rax
0x14007a903  jz      short loc_14007A923
0x14007a905  test    byte ptr [rcx+1Ch], 1
0x14007a909  jz      short loc_14007A923
0x14007a90b  mov     edx, 156h
0x14007a910  mov     rcx, [rcx+10h]
0x14007a914  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007a91b  mov     r9d, ebx
0x14007a91e  call    WPP_SF_d
0x14007a923  mov     ecx, ebx; Status
0x14007a925  call    cs:__imp_RtlNtStatusToDosError
0x14007a92b  mov     ebx, eax
0x14007a92d  jmp     loc_14007A87B
0x14007a932  mov     rcx, gs:60h
0x14007a93b  mov     ebx, 8
0x14007a940  mov     r8d, 242h; Size
0x14007a946  mov     edx, ebx; Flags
0x14007a948  mov     rcx, [rcx+30h]; HeapHandle
0x14007a94c  call    cs:__imp_RtlAllocateHeap
0x14007a952  mov     rsi, rax
0x14007a955  test    rax, rax
0x14007a958  jz      loc_14007A87B
0x14007a95e  mov     al, 1
0x14007a960  lea     rcx, [rbp+arg_0]
0x14007a964  mov     r9b, 1; ReturnSingleEntry
0x14007a967  mov     [rsp+70h+ReturnLength], rcx; ReturnLength
0x14007a96c  mov     r8d, 242h; BufferLength
0x14007a972  lea     rcx, [rbp+arg_8]
0x14007a976  mov     rdx, rsi; Buffer
0x14007a979  mov     [rsp+70h+Context], rcx; Context
0x14007a97e  mov     rcx, [rbp+Handle]; DirectoryHandle
0x14007a982  mov     [rsp+70h+RestartScan], al; RestartScan
0x14007a986  call    cs:__imp_NtQueryDirectoryObject
0x14007a98c  mov     ebx, eax
0x14007a98e  cmp     eax, 8000001Ah
0x14007a993  jz      loc_14007A878
0x14007a999  test    eax, eax
0x14007a99b  js      loc_14007AA21
0x14007a9a1  mov     rdi, rsi
0x14007a9a4  cmp     [rdi], r14w
0x14007a9a8  jz      short loc_14007A9D9
0x14007a9aa  mov     rcx, [rdi+8]; String1
0x14007a9ae  lea     rdx, aSystem; "SYSTEM"
0x14007a9b5  call    wcscmp
0x14007a9ba  test    eax, eax
0x14007a9bc  jz      short loc_14007A9D3
0x14007a9be  movzx   edx, word ptr [rdi]; unsigned int
0x14007a9c1  xor     r8d, r8d; int
0x14007a9c4  mov     rcx, [rdi+8]; unsigned __int16 *
0x14007a9c8  call    ?ScInitConfigRoot@@YAKPEBGKH@Z; ScInitConfigRoot(ushort const *,ulong,int)
0x14007a9cd  mov     ebx, eax
0x14007a9cf  test    eax, eax
0x14007a9d1  jnz     short loc_14007A9DE
0x14007a9d3  add     rdi, 20h ; ' '
0x14007a9d7  jmp     short loc_14007A9A4
0x14007a9d9  mov     al, r14b
0x14007a9dc  jmp     short loc_14007A960
0x14007a9de  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a9e5  lea     rax, WPP_GLOBAL_Control
0x14007a9ec  cmp     rcx, rax
0x14007a9ef  jz      loc_14007A87B
0x14007a9f5  test    byte ptr [rcx+1Ch], 1
0x14007a9f9  jz      loc_14007A87B
0x14007a9ff  mov     r9, [rdi+8]
0x14007aa03  lea     r8, WPP_e5a68143c9d03da933de77b1bc511594_Traceguids
0x14007aa0a  mov     rcx, [rcx+10h]
0x14007aa0e  mov     edx, 158h
0x14007aa13  mov     dword ptr [rsp+70h+RestartScan], ebx
0x14007aa17  call    WPP_SF_Sd
0x14007aa1c  jmp     loc_14007A87B
0x14007aa21  mov     rcx, cs:WPP_GLOBAL_Control
0x14007aa28  lea     rax, WPP_GLOBAL_Control
0x14007aa2f  cmp     rcx, rax
0x14007aa32  jz      loc_14007A923
0x14007aa38  test    byte ptr [rcx+1Ch], 1
0x14007aa3c  jz      loc_14007A923
0x14007aa42  mov     edx, 157h
0x14007aa47  jmp     loc_14007A910
```
