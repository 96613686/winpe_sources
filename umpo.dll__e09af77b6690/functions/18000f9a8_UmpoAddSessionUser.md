# UmpoAddSessionUser

- ea: `0x18000f9a8`
- end: `0x18000fb52`
- name: `UmpoAddSessionUser`
- size: `426`
- prototype: `__int64 __fastcall(int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e490`

## callees

- `0x18000f3dc`
- `0x18000f9a8`
- `0x18000fbb4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000fa4f`
- `ntdll!RtlAllocateHeap` at `0x18000faaa`
- `ntdll!RtlAllocateHeap` at `0x18000fa4f`
- `ntdll!RtlAllocateHeap` at `0x18000faaa`
- `ntdll!RtlLengthSid` at `0x18000fa94`
- `ntdll!RtlLengthSid` at `0x18000fa94`
- `ntdll!RtlFreeHeap` at `0x18000fb39`
- `ntdll!RtlFreeHeap` at `0x18000fb39`
- `ntdll!RtlNtStatusToDosError` at `0x18000fa2f`
- `ntdll!RtlNtStatusToDosError` at `0x18000fa2f`
- `ntdll!RtlCopySid` at `0x18000facd`
- `ntdll!RtlCopySid` at `0x18000facd`
- `ntdll!NtQueryInformationToken` at `0x18000fa19`
- `ntdll!NtQueryInformationToken` at `0x18000fa83`
- `ntdll!NtQueryInformationToken` at `0x18000fa19`
- `ntdll!NtQueryInformationToken` at `0x18000fa83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb22`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000f9ee`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000f9ee`

## pseudocode

```c
__int64 __fastcall UmpoAddSessionUser(int a1, __int64 a2, _QWORD *a3)
{
  PSID *Heap; // rdi
  int v7; // eax
  ULONG v8; // ebx
  NTSTATUS v9; // ebx
  NTSTATUS v10; // ecx
  NTSTATUS v11; // eax
  ULONG v12; // r14d
  _DWORD *v13; // rax
  _DWORD *v14; // rbx
  _QWORD *v15; // rax
  _UNKNOWN **v16; // rcx
  ULONG TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  if ( a1 == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  TokenHandle = 0;
  Heap = 0;
  v7 = UMgrQueryUserToken(a2, &TokenHandle);
  if ( v7 < 0 )
  {
    v8 = (unsigned __int16)v7;
    goto LABEL_16;
  }
  v9 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( v9 != -1073741789 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v10 = v9;
LABEL_7:
    v8 = RtlNtStatusToDosError(v10);
    goto LABEL_16;
  }
  Heap = (PSID *)RtlAllocateHeap(UmpoHeapHandle, 8u, TokenInformationLength);
  if ( !Heap )
    goto LABEL_9;
  v11 = NtQueryInformationToken(TokenHandle, TokenUser, Heap, TokenInformationLength, &TokenInformationLength);
  if ( v11 < 0 )
  {
    v10 = v11;
    goto LABEL_7;
  }
  v12 = RtlLengthSid(*Heap);
  v13 = RtlAllocateHeap(UmpoHeapHandle, 8u, v12 + 40);
  v14 = v13;
  if ( v13 )
  {
    v13[6] = a1;
    *((_QWORD *)v13 + 2) = v13 + 10;
    *((_QWORD *)v13 + 4) = a2;
    RtlCopySid(v12, v13 + 10, *Heap);
    v15 = UmpoUserContextList;
    v16 = &UmpoUserContextList;
    if ( *((_UNKNOWN ***)UmpoUserContextList + 1) != &UmpoUserContextList )
      __fastfail(3u);
    *((_QWORD *)v14 + 1) = &UmpoUserContextList;
    LOBYTE(v16) = 1;
    *(_QWORD *)v14 = v15;
    v15[1] = v14;
    UmpoUserContextList = v14;
    UmpoTraceSessionUserLoginChange(v16, *((_QWORD *)v14 + 4), (unsigned int)v14[6], *((_QWORD *)v14 + 2));
    *a3 = v14;
    v8 = 0;
  }
  else
  {
LABEL_9:
    v8 = 14;
  }
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( Heap )
    RtlFreeHeap(UmpoHeapHandle, 0, Heap);
  return v8;
}

```

## disassembly

```asm
0x18000f9a8  mov     [rsp+arg_8], rbx
0x18000f9ad  push    rbp
0x18000f9ae  push    rsi
0x18000f9af  push    rdi
0x18000f9b0  push    r14
0x18000f9b2  push    r15
0x18000f9b4  sub     rsp, 30h
0x18000f9b8  mov     [rsp+58h+TokenInformationLength], 0
0x18000f9c0  mov     r15, r8
0x18000f9c3  mov     [rsp+58h+TokenHandle], 0
0x18000f9cc  mov     rbp, rdx
0x18000f9cf  mov     esi, ecx
0x18000f9d1  cmp     ecx, 0FFFFFFFFh
0x18000f9d4  jnz     short loc_18000F9DB
0x18000f9d6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f9db  lea     rdx, [rsp+58h+TokenHandle]
0x18000f9e0  mov     [rsp+58h+TokenHandle], 0
0x18000f9e9  mov     rcx, rbp
0x18000f9ec  xor     edi, edi
0x18000f9ee  call    cs:__imp_UMgrQueryUserToken
0x18000f9f4  test    eax, eax
0x18000f9f6  jns     short loc_18000FA00
0x18000f9f8  movzx   ebx, ax
0x18000f9fb  jmp     loc_18000FB18
0x18000fa00  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000fa05  lea     rax, [rsp+58h+TokenInformationLength]
0x18000fa0a  xor     r9d, r9d; TokenInformationLength
0x18000fa0d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000fa12  xor     r8d, r8d; TokenInformation
0x18000fa15  lea     edx, [r9+1]; TokenInformationClass
0x18000fa19  call    cs:__imp_NtQueryInformationToken
0x18000fa1f  mov     ebx, eax
0x18000fa21  cmp     eax, 0C0000023h
0x18000fa26  jz      short loc_18000FA3C
0x18000fa28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000fa2d  mov     ecx, ebx; Status
0x18000fa2f  call    cs:__imp_RtlNtStatusToDosError
0x18000fa35  mov     ebx, eax
0x18000fa37  jmp     loc_18000FB18
0x18000fa3c  mov     r8d, [rsp+58h+TokenInformationLength]; Size
0x18000fa41  mov     ebx, 8
0x18000fa46  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000fa4d  mov     edx, ebx; Flags
0x18000fa4f  call    cs:__imp_RtlAllocateHeap
0x18000fa55  mov     rdi, rax
0x18000fa58  test    rax, rax
0x18000fa5b  jnz     short loc_18000FA67
0x18000fa5d  mov     ebx, 0Eh
0x18000fa62  jmp     loc_18000FB18
0x18000fa67  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000fa6c  lea     rax, [rsp+58h+TokenInformationLength]
0x18000fa71  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000fa76  mov     r8, rdi; TokenInformation
0x18000fa79  mov     edx, 1; TokenInformationClass
0x18000fa7e  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000fa83  call    cs:__imp_NtQueryInformationToken
0x18000fa89  test    eax, eax
0x18000fa8b  jns     short loc_18000FA91
0x18000fa8d  mov     ecx, eax
0x18000fa8f  jmp     short loc_18000FA2F
0x18000fa91  mov     rcx, [rdi]; Sid
0x18000fa94  call    cs:__imp_RtlLengthSid
0x18000fa9a  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000faa1  mov     edx, ebx; Flags
0x18000faa3  mov     r14d, eax
0x18000faa6  lea     r8d, [rax+28h]; Size
0x18000faaa  call    cs:__imp_RtlAllocateHeap
0x18000fab0  mov     rbx, rax
0x18000fab3  test    rax, rax
0x18000fab6  jz      short loc_18000FA5D
0x18000fab8  lea     rdx, [rax+28h]; DestinationSid
0x18000fabc  mov     [rax+18h], esi
0x18000fabf  mov     [rax+10h], rdx
0x18000fac3  mov     ecx, r14d; DestinationSidLength
0x18000fac6  mov     [rax+20h], rbp
0x18000faca  mov     r8, [rdi]; SourceSid
0x18000facd  call    cs:__imp_RtlCopySid
0x18000fad3  mov     rax, cs:UmpoUserContextList
0x18000fada  lea     rcx, UmpoUserContextList
0x18000fae1  cmp     [rax+8], rcx
0x18000fae5  jz      short loc_18000FAEE
0x18000fae7  mov     ecx, 3
0x18000faec  int     29h; Win8: RtlFailFast(ecx)
0x18000faee  mov     [rbx+8], rcx
0x18000faf2  mov     cl, 1
0x18000faf4  mov     [rbx], rax
0x18000faf7  mov     [rax+8], rbx
0x18000fafb  mov     cs:UmpoUserContextList, rbx
0x18000fb02  mov     r9, [rbx+10h]
0x18000fb06  mov     r8d, [rbx+18h]
0x18000fb0a  mov     rdx, [rbx+20h]
0x18000fb0e  call    UmpoTraceSessionUserLoginChange
0x18000fb13  mov     [r15], rbx
0x18000fb16  xor     ebx, ebx
0x18000fb18  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000fb1d  test    rcx, rcx
0x18000fb20  jz      short loc_18000FB28
0x18000fb22  call    cs:__imp_CloseHandle
0x18000fb28  test    rdi, rdi
0x18000fb2b  jz      short loc_18000FB3F
0x18000fb2d  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000fb34  mov     r8, rdi; P
0x18000fb37  xor     edx, edx; Flags
0x18000fb39  call    cs:__imp_RtlFreeHeap
0x18000fb3f  mov     eax, ebx
0x18000fb41  mov     rbx, [rsp+58h+arg_8]
0x18000fb46  add     rsp, 30h
0x18000fb4a  pop     r15
0x18000fb4c  pop     r14
0x18000fb4e  pop     rdi
0x18000fb4f  pop     rsi
0x18000fb50  pop     rbp
0x18000fb51  retn
```
