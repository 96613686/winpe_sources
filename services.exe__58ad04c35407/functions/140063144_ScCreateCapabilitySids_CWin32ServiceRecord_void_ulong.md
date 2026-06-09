# ScCreateCapabilitySids(CWin32ServiceRecord *,void * * *,ulong *)

- ea: `0x140063144`
- end: `0x140063504`
- name: `?ScCreateCapabilitySids@@YAKPEAVCWin32ServiceRecord@@PEAPEAPEAXPEAK@Z`
- size: `960`
- prototype: `unsigned int __fastcall(struct CWin32ServiceRecord *, void ***, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1400381d4`
- `0x14003ae4c`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000bebc`
- `0x14001c1e0`
- `0x14001f99c`
- `0x140029228`
- `0x14002b4a4`
- `0x140063144`
- `0x14007af50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400632fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400632fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063449`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140063449`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1400633db`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1400633db`
- `ntdll!RtlLengthRequiredSid` at `0x140063344`
- `ntdll!RtlLengthRequiredSid` at `0x140063392`
- `ntdll!RtlLengthRequiredSid` at `0x140063344`
- `ntdll!RtlLengthRequiredSid` at `0x140063392`
- `ntdll!RtlNtStatusToDosError` at `0x14006346b`
- `ntdll!RtlNtStatusToDosError` at `0x14006346b`
- `ntdll!RtlInitUnicodeString` at `0x1400633ca`
- `ntdll!RtlInitUnicodeString` at `0x1400633ca`
- `ntdll!RtlFreeHeap` at `0x14006341d`
- `ntdll!RtlFreeHeap` at `0x14006343a`
- `ntdll!RtlFreeHeap` at `0x1400634cf`
- `ntdll!RtlFreeHeap` at `0x1400634f0`
- `ntdll!RtlFreeHeap` at `0x14006341d`
- `ntdll!RtlFreeHeap` at `0x14006343a`
- `ntdll!RtlFreeHeap` at `0x1400634cf`
- `ntdll!RtlFreeHeap` at `0x1400634f0`
- `ntdll!RtlAllocateHeap` at `0x1400632ed`
- `ntdll!RtlAllocateHeap` at `0x14006335c`
- `ntdll!RtlAllocateHeap` at `0x1400633aa`
- `ntdll!RtlAllocateHeap` at `0x1400632ed`
- `ntdll!RtlAllocateHeap` at `0x14006335c`
- `ntdll!RtlAllocateHeap` at `0x1400633aa`

## pseudocode

```c
__int64 __fastcall ScCreateCapabilitySids(struct CWin32ServiceRecord *a1, void ***a2, unsigned int *a3)
{
  unsigned int v3; // r15d
  unsigned int LastError; // ebx
  unsigned int *v6; // r8
  unsigned int Capabilities; // eax
  _WORD *v8; // r12
  unsigned int v9; // eax
  unsigned int v10; // r14d
  void **Heap; // rsi
  ULONG v12; // eax
  PVOID v13; // r13
  __int16 v14; // r10
  ULONG v15; // eax
  PVOID v16; // rax
  NTSTATUS v17; // eax
  char v18; // di
  unsigned int i; // edi
  void *v21; // r8
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  PVOID P; // [rsp+38h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PCWSTR SourceString; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  P = 0;
  SourceString = 0;
  DestinationString = 0;
  hKey = 0;
  LastError = CServiceRecord::OpenServiceConfigKey(a1, 0x20019u, (__int64)a3, &hKey);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        68,
        (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
        *((_QWORD *)a1 + 7),
        LastError);
    goto LABEL_35;
  }
  Capabilities = ScReadCapabilities(hKey, (unsigned __int16 **)&P, v6);
  v8 = P;
  LastError = Capabilities;
  if ( Capabilities )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        69,
        (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
        *((_QWORD *)a1 + 7),
        Capabilities);
    goto LABEL_33;
  }
  v9 = ScWStrArrayStrCount(P);
  v10 = v9;
  if ( !v9 )
  {
    LastError = 0;
    goto LABEL_33;
  }
  if ( (*((_BYTE *)a1 + 80) & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 70, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
    LastError = 87;
    goto LABEL_33;
  }
  if ( v9 > 0x400 )
  {
    LastError = 1389;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 71, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
    goto LABEL_33;
  }
  LastError = 8;
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8LL * v9);
  if ( !Heap )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 72, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, LastError);
    goto LABEL_33;
  }
  v12 = RtlLengthRequiredSid(0xAu);
  v13 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( !v13 )
    goto LABEL_45;
  P = v8;
  if ( !*v8 )
  {
LABEL_31:
    LastError = 0;
    *a2 = Heap;
    *a3 = v10;
    goto LABEL_32;
  }
  while ( !(unsigned int)ScGetToken((unsigned __int16 **)&P, (unsigned __int16 **)&SourceString) )
  {
LABEL_30:
    if ( *(_WORD *)P == v14 )
      goto LABEL_31;
  }
  v15 = RtlLengthRequiredSid(9u);
  v16 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  Heap[v3] = v16;
  if ( !v16 )
    goto LABEL_41;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v17 = RtlDeriveCapabilitySidsFromName(&DestinationString, Heap[v3], v13);
  v14 = 0;
  v18 = v17;
  if ( v17 >= 0 )
  {
    ++v3;
    goto LABEL_30;
  }
  LastError = RtlNtStatusToDosError(v17);
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      73,
      (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
      (_DWORD)SourceString,
      v18);
LABEL_41:
  for ( i = 0; i < v3; ++i )
  {
    v21 = Heap[i];
    if ( v21 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
  }
LABEL_45:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v13 )
LABEL_32:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
LABEL_33:
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x140063144  mov     [rsp-38h+arg_0], rbx
0x140063149  mov     [rsp-38h+arg_10], r8
0x14006314e  mov     [rsp-38h+arg_8], rdx
0x140063153  push    rbp
0x140063154  push    rsi
0x140063155  push    rdi
0x140063156  push    r12
0x140063158  push    r13
0x14006315a  push    r14
0x14006315c  push    r15
0x14006315e  mov     rbp, rsp
0x140063161  sub     rsp, 50h
0x140063165  xor     r15d, r15d
0x140063168  lea     r9, [rbp+hKey]; HKEY *
0x14006316c  xorps   xmm0, xmm0
0x14006316f  mov     [rbp+P], r15
0x140063173  mov     edx, 20019h; unsigned int
0x140063178  mov     [rbp+SourceString], r15
0x14006317c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140063180  mov     [rbp+hKey], r15
0x140063184  mov     rdi, rcx
0x140063187  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x14006318c  mov     ebx, eax
0x14006318e  test    eax, eax
0x140063190  jz      short loc_1400631D4
0x140063192  mov     rcx, cs:WPP_GLOBAL_Control
0x140063199  lea     rax, WPP_GLOBAL_Control
0x1400631a0  cmp     rcx, rax
0x1400631a3  jz      loc_140063440
0x1400631a9  test    byte ptr [rcx+1Ch], 1
0x1400631ad  jz      loc_140063440
0x1400631b3  mov     r9, [rdi+38h]
0x1400631b7  lea     edx, [r15+44h]
0x1400631bb  mov     rcx, [rcx+10h]
0x1400631bf  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400631c6  mov     [rsp+50h+var_30], ebx
0x1400631ca  call    WPP_SF_Sd
0x1400631cf  jmp     loc_140063440
0x1400631d4  mov     rcx, [rbp+hKey]; HKEY
0x1400631d8  lea     rdx, [rbp+P]; unsigned __int16 **
0x1400631dc  call    ?ScReadCapabilities@@YAKPEAUHKEY__@@PEAPEAGPEAK@Z; ScReadCapabilities(HKEY__ *,ushort * *,ulong *)
0x1400631e1  mov     r12, [rbp+P]
0x1400631e5  mov     ebx, eax
0x1400631e7  test    eax, eax
0x1400631e9  jz      short loc_14006322E
0x1400631eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400631f2  lea     rax, WPP_GLOBAL_Control
0x1400631f9  cmp     rcx, rax
0x1400631fc  jz      loc_140063423
0x140063202  test    byte ptr [rcx+1Ch], 1
0x140063206  jz      loc_140063423
0x14006320c  mov     r9, [rdi+38h]
0x140063210  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063217  mov     rcx, [rcx+10h]
0x14006321b  mov     edx, 45h ; 'E'
0x140063220  mov     [rsp+50h+var_30], ebx
0x140063224  call    WPP_SF_Sd
0x140063229  jmp     loc_140063423
0x14006322e  mov     rcx, r12
0x140063231  call    ScWStrArrayStrCount
0x140063236  mov     r14d, eax
0x140063239  test    eax, eax
0x14006323b  jnz     short loc_140063245
0x14006323d  mov     ebx, r15d
0x140063240  jmp     loc_140063423
0x140063245  test    byte ptr [rdi+50h], 10h
0x140063249  jnz     short loc_140063283
0x14006324b  mov     rcx, cs:WPP_GLOBAL_Control
0x140063252  lea     rax, WPP_GLOBAL_Control
0x140063259  cmp     rcx, rax
0x14006325c  jz      short loc_140063279
0x14006325e  test    byte ptr [rcx+1Ch], 1
0x140063262  jz      short loc_140063279
0x140063264  mov     rcx, [rcx+10h]
0x140063268  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14006326f  mov     edx, 46h ; 'F'
0x140063274  call    WPP_SF_
0x140063279  mov     ebx, 57h ; 'W'
0x14006327e  jmp     loc_140063423
0x140063283  mov     r9d, 400h
0x140063289  cmp     r14d, r9d
0x14006328c  jbe     short loc_1400632D2
0x14006328e  mov     ebx, 56Dh
0x140063293  mov     rcx, cs:WPP_GLOBAL_Control
0x14006329a  lea     rax, WPP_GLOBAL_Control
0x1400632a1  cmp     rcx, rax
0x1400632a4  jz      loc_140063423
0x1400632aa  test    byte ptr [rcx+1Ch], 1
0x1400632ae  jz      loc_140063423
0x1400632b4  mov     rcx, [rcx+10h]
0x1400632b8  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x1400632bf  mov     edx, 47h ; 'G'
0x1400632c4  mov     [rsp+50h+var_30], ebx
0x1400632c8  call    WPP_SF_Dd
0x1400632cd  jmp     loc_140063423
0x1400632d2  mov     rcx, gs:60h
0x1400632db  mov     r8, r14
0x1400632de  mov     ebx, 8
0x1400632e3  shl     r8, 3; Size
0x1400632e7  mov     edx, ebx; Flags
0x1400632e9  mov     rcx, [rcx+30h]; HeapHandle
0x1400632ed  call    cs:__imp_RtlAllocateHeap
0x1400632f3  mov     rsi, rax
0x1400632f6  test    rax, rax
0x1400632f9  jnz     short loc_14006333F
0x1400632fb  call    cs:__imp_GetLastError
0x140063301  mov     ebx, eax
0x140063303  mov     rcx, cs:WPP_GLOBAL_Control
0x14006330a  lea     rax, WPP_GLOBAL_Control
0x140063311  cmp     rcx, rax
0x140063314  jz      loc_140063423
0x14006331a  test    byte ptr [rcx+1Ch], 1
0x14006331e  jz      loc_140063423
0x140063324  mov     rcx, [rcx+10h]
0x140063328  lea     edx, [rsi+48h]
0x14006332b  mov     r9d, ebx
0x14006332e  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063335  call    WPP_SF_d
0x14006333a  jmp     loc_140063423
0x14006333f  mov     ecx, 0Ah; SubAuthorityCount
0x140063344  call    cs:__imp_RtlLengthRequiredSid
0x14006334a  mov     rcx, gs:60h
0x140063353  xor     edx, edx; Flags
0x140063355  mov     r8d, eax; Size
0x140063358  mov     rcx, [rcx+30h]; HeapHandle
0x14006335c  call    cs:__imp_RtlAllocateHeap
0x140063362  mov     r13, rax
0x140063365  test    rax, rax
0x140063368  jz      loc_1400634DE
0x14006336e  xor     r10d, r10d
0x140063371  mov     [rbp+P], r12
0x140063375  cmp     [r12], r10w
0x14006337a  jz      short loc_1400633F7
0x14006337c  lea     rdx, [rbp+SourceString]; unsigned __int16 **
0x140063380  lea     rcx, [rbp+P]; unsigned __int16 **
0x140063384  call    ?ScGetToken@@YAHPEAPEAG0@Z; ScGetToken(ushort * *,ushort * *)
0x140063389  test    eax, eax
0x14006338b  jz      short loc_1400633ED
0x14006338d  mov     ecx, 9; SubAuthorityCount
0x140063392  call    cs:__imp_RtlLengthRequiredSid
0x140063398  mov     rcx, gs:60h
0x1400633a1  xor     edx, edx; Flags
0x1400633a3  mov     r8d, eax; Size
0x1400633a6  mov     rcx, [rcx+30h]; HeapHandle
0x1400633aa  call    cs:__imp_RtlAllocateHeap
0x1400633b0  mov     edi, r15d
0x1400633b3  xor     ecx, ecx
0x1400633b5  mov     [rsi+rdi*8], rax
0x1400633b9  test    rax, rax
0x1400633bc  jz      loc_1400634AB
0x1400633c2  mov     rdx, [rbp+SourceString]; SourceString
0x1400633c6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400633ca  call    cs:__imp_RtlInitUnicodeString
0x1400633d0  mov     rdx, [rsi+rdi*8]
0x1400633d4  lea     rcx, [rbp+DestinationString]
0x1400633d8  mov     r8, r13
0x1400633db  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1400633e1  xor     r10d, r10d
0x1400633e4  mov     edi, eax
0x1400633e6  test    eax, eax
0x1400633e8  js      short loc_140063469
0x1400633ea  inc     r15d
0x1400633ed  mov     rax, [rbp+P]
0x1400633f1  cmp     [rax], r10w
0x1400633f5  jnz     short loc_14006337C
0x1400633f7  mov     rax, [rbp+arg_8]
0x1400633fb  xor     r15d, r15d
0x1400633fe  mov     ebx, r15d
0x140063401  mov     [rax], rsi
0x140063404  mov     rax, [rbp+arg_10]
0x140063408  mov     [rax], r14d
0x14006340b  mov     rcx, gs:60h
0x140063414  mov     r8, r13; P
0x140063417  xor     edx, edx; Flags
0x140063419  mov     rcx, [rcx+30h]; HeapHandle
0x14006341d  call    cs:__imp_RtlFreeHeap
0x140063423  test    r12, r12
0x140063426  jz      short loc_140063440
0x140063428  mov     rcx, gs:60h
0x140063431  mov     r8, r12; P
0x140063434  xor     edx, edx; Flags
0x140063436  mov     rcx, [rcx+30h]; HeapHandle
0x14006343a  call    cs:__imp_RtlFreeHeap
0x140063440  mov     rcx, [rbp+hKey]; hKey
0x140063444  test    rcx, rcx
0x140063447  jz      short loc_14006344F
0x140063449  call    cs:__imp_RegCloseKey
0x14006344f  mov     eax, ebx
0x140063451  mov     rbx, [rsp+50h+arg_0]
0x140063459  add     rsp, 50h
0x14006345d  pop     r15
0x14006345f  pop     r14
0x140063461  pop     r13
0x140063463  pop     r12
0x140063465  pop     rdi
0x140063466  pop     rsi
0x140063467  pop     rbp
0x140063468  retn
0x140063469  mov     ecx, edi; Status
0x14006346b  call    cs:__imp_RtlNtStatusToDosError
0x140063471  mov     ebx, eax
0x140063473  mov     rcx, cs:WPP_GLOBAL_Control
0x14006347a  lea     rax, WPP_GLOBAL_Control
0x140063481  cmp     rcx, rax
0x140063484  jz      short loc_1400634A9
0x140063486  test    byte ptr [rcx+1Ch], 1
0x14006348a  jz      short loc_1400634A9
0x14006348c  mov     r9, [rbp+SourceString]
0x140063490  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063497  mov     rcx, [rcx+10h]
0x14006349b  mov     edx, 49h ; 'I'
0x1400634a0  mov     [rsp+50h+var_30], edi
0x1400634a4  call    WPP_SF_Sd
0x1400634a9  xor     ecx, ecx
0x1400634ab  mov     r14, rsi
0x1400634ae  mov     edi, ecx
0x1400634b0  test    r15d, r15d
0x1400634b3  jz      short loc_1400634DE
0x1400634b5  mov     eax, edi
0x1400634b7  mov     r8, [r14+rax*8]; P
0x1400634bb  test    r8, r8
0x1400634be  jz      short loc_1400634D7
0x1400634c0  mov     rcx, gs:60h
0x1400634c9  xor     edx, edx; Flags
0x1400634cb  mov     rcx, [rcx+30h]; HeapHandle
0x1400634cf  call    cs:__imp_RtlFreeHeap
0x1400634d5  xor     ecx, ecx
0x1400634d7  inc     edi
0x1400634d9  cmp     edi, r15d
0x1400634dc  jb      short loc_1400634B5
0x1400634de  mov     rcx, gs:60h
0x1400634e7  mov     r8, rsi; P
0x1400634ea  xor     edx, edx; Flags
0x1400634ec  mov     rcx, [rcx+30h]; HeapHandle
0x1400634f0  call    cs:__imp_RtlFreeHeap
0x1400634f6  test    r13, r13
0x1400634f9  jz      loc_140063423
0x1400634ff  jmp     loc_14006340B
```
