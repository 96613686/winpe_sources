# RQueryServiceObjectSecurity

- ea: `0x140030680`
- end: `0x14003085e`
- name: `RQueryServiceObjectSecurity`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400083f0`
- `0x14001f99c`
- `0x140030680`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140030748`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140030797`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140030748`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140030797`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14003077b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400307c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14003077b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400307c5`
- `ntdll!RtlQuerySecurityObject` at `0x14003076b`
- `ntdll!RtlQuerySecurityObject` at `0x1400307b6`
- `ntdll!RtlQuerySecurityObject` at `0x14003076b`
- `ntdll!RtlQuerySecurityObject` at `0x1400307b6`
- `ntdll!RtlReleaseResource` at `0x140030788`
- `ntdll!RtlReleaseResource` at `0x140030788`
- `ntdll!RtlAcquireResourceShared` at `0x140030734`
- `ntdll!RtlAcquireResourceShared` at `0x140030734`
- `ntdll!RtlAreAllAccessesGranted` at `0x140030704`
- `ntdll!RtlAreAllAccessesGranted` at `0x140030704`
- `ntdll!RtlNtStatusToDosError` at `0x140030828`
- `ntdll!RtlNtStatusToDosError` at `0x140030828`

## pseudocode

```c
ULONG __fastcall RQueryServiceObjectSecurity(__int64 a1, SECURITY_INFORMATION a2, void *a3, unsigned int a4, ULONG *a5)
{
  size_t v5; // rbp
  int v9; // esi
  ACCESS_MASK v10; // edx
  RTL_SRWLOCK *v12; // rsi
  int v13; // ebx
  ULONG ReturnLength; // [rsp+50h] [rbp+8h] BYREF

  v5 = a4;
  ReturnLength = 0;
  ScSetTcpKeepalive();
  if ( !a1 )
    return 6;
  if ( *(_DWORD *)a1 != 1215456627 )
  {
    if ( *(_DWORD *)a1 == 1215456115 )
    {
      v9 = 0;
      goto LABEL_6;
    }
    return 6;
  }
  v9 = 1;
LABEL_6:
  if ( !a2 || (a2 & 0x9F) != a2 )
    return 87;
  v10 = ((a2 & 0x88) != 0 ? 0x1000000 : 0) | 0x20000;
  if ( (a2 & 0x17) == 0 )
    v10 = (a2 & 0x88) != 0 ? 0x1000000 : 0;
  if ( !RtlAreAllAccessesGranted(*(_DWORD *)(a1 + 8), v10) )
    return 5;
  memset(a3, 0, v5);
  if ( v9 == 1 )
  {
    RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
    v12 = (RTL_SRWLOCK *)(*(_QWORD *)(a1 + 16) + 312LL);
    AcquireSRWLockShared(v12);
    v13 = RtlQuerySecurityObject(*(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(a1 + 16) + 144LL), a2, a3, v5, &ReturnLength);
    if ( v12 )
      ReleaseSRWLockShared(v12);
    RtlReleaseResource(&ScServiceRecordLock);
  }
  else
  {
    AcquireSRWLockShared(&ScManagerSdLock);
    v13 = RtlQuerySecurityObject(ScManagerSd, a2, a3, v5, &ReturnLength);
    ReleaseSRWLockShared(&ScManagerSdLock);
  }
  if ( v13 >= 0 )
  {
    *a5 = ReturnLength;
    return 0;
  }
  else if ( v13 == -1073741593 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 11, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids);
    return 31;
  }
  else if ( v13 == -1073741789 )
  {
    *a5 = ReturnLength;
    return 122;
  }
  else
  {
    return RtlNtStatusToDosError(v13);
  }
}

```

## disassembly

```asm
0x140030680  mov     [rsp+arg_8], rbx
0x140030685  mov     [rsp+arg_10], rbp
0x14003068a  push    rsi
0x14003068b  push    rdi
0x14003068c  push    r14
0x14003068e  sub     rsp, 30h
0x140030692  mov     ebp, r9d
0x140030695  mov     r14, r8
0x140030698  mov     ebx, edx
0x14003069a  mov     [rsp+48h+arg_0], 0
0x1400306a2  mov     rdi, rcx
0x1400306a5  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x1400306aa  test    rdi, rdi
0x1400306ad  jz      loc_140030846
0x1400306b3  cmp     dword ptr [rdi], 48726573h
0x1400306b9  jnz     short loc_1400306C2
0x1400306bb  mov     esi, 1
0x1400306c0  jmp     short loc_1400306D0
0x1400306c2  cmp     dword ptr [rdi], 48726373h
0x1400306c8  jnz     loc_140030846
0x1400306ce  xor     esi, esi
0x1400306d0  test    ebx, ebx
0x1400306d2  jz      loc_14003083F
0x1400306d8  mov     eax, ebx
0x1400306da  and     eax, 9Fh
0x1400306df  cmp     eax, ebx
0x1400306e1  jnz     loc_14003083F
0x1400306e7  mov     eax, ebx
0x1400306e9  and     al, 88h
0x1400306eb  neg     al
0x1400306ed  sbb     ecx, ecx
0x1400306ef  and     ecx, 1000000h
0x1400306f5  mov     edx, ecx
0x1400306f7  bts     edx, 11h
0x1400306fb  test    bl, 17h
0x1400306fe  cmovz   edx, ecx; DesiredAccess
0x140030701  mov     ecx, [rdi+8]; GrantedAccess
0x140030704  call    cs:__imp_RtlAreAllAccessesGranted
0x14003070a  test    al, al
0x14003070c  jnz     short loc_140030718
0x14003070e  mov     eax, 5
0x140030713  jmp     loc_14003084B
0x140030718  mov     r8, rbp; Size
0x14003071b  xor     edx, edx; Val
0x14003071d  mov     rcx, r14; void *
0x140030720  call    memset
0x140030725  cmp     esi, 1
0x140030728  jnz     short loc_140030790
0x14003072a  mov     dl, sil; Wait
0x14003072d  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140030734  call    cs:__imp_RtlAcquireResourceShared
0x14003073a  mov     rsi, [rdi+10h]
0x14003073e  add     rsi, 138h
0x140030745  mov     rcx, rsi; SRWLock
0x140030748  call    cs:__imp_AcquireSRWLockShared
0x14003074e  mov     rcx, [rdi+10h]
0x140030752  lea     rax, [rsp+48h+arg_0]
0x140030757  mov     r9d, ebp; DescriptorLength
0x14003075a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14003075f  mov     r8, r14; ResultantDescriptor
0x140030762  mov     edx, ebx; SecurityInformation
0x140030764  mov     rcx, [rcx+90h]; ObjectDescriptor
0x14003076b  call    cs:__imp_RtlQuerySecurityObject
0x140030771  mov     ebx, eax
0x140030773  test    rsi, rsi
0x140030776  jz      short loc_140030781
0x140030778  mov     rcx, rsi; SRWLock
0x14003077b  call    cs:__imp_ReleaseSRWLockShared
0x140030781  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140030788  call    cs:__imp_RtlReleaseResource
0x14003078e  jmp     short loc_1400307CB
0x140030790  lea     rcx, ?ScManagerSdLock@@3VCScmLock@@A; SRWLock
0x140030797  call    cs:__imp_AcquireSRWLockShared
0x14003079d  mov     rcx, cs:?ScManagerSd@@3PEAXEA; ObjectDescriptor
0x1400307a4  lea     rax, [rsp+48h+arg_0]
0x1400307a9  mov     r9d, ebp; DescriptorLength
0x1400307ac  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1400307b1  mov     r8, r14; ResultantDescriptor
0x1400307b4  mov     edx, ebx; SecurityInformation
0x1400307b6  call    cs:__imp_RtlQuerySecurityObject
0x1400307bc  lea     rcx, ?ScManagerSdLock@@3VCScmLock@@A; SRWLock
0x1400307c3  mov     ebx, eax
0x1400307c5  call    cs:__imp_ReleaseSRWLockShared
0x1400307cb  test    ebx, ebx
0x1400307cd  jns     short loc_140030830
0x1400307cf  cmp     ebx, 0C00000E7h
0x1400307d5  jnz     short loc_14003080C
0x1400307d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307de  lea     rax, WPP_GLOBAL_Control
0x1400307e5  cmp     rcx, rax
0x1400307e8  jz      short loc_140030805
0x1400307ea  test    byte ptr [rcx+1Ch], 1
0x1400307ee  jz      short loc_140030805
0x1400307f0  mov     rcx, [rcx+10h]
0x1400307f4  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x1400307fb  mov     edx, 0Bh
0x140030800  call    WPP_SF_
0x140030805  mov     eax, 1Fh
0x14003080a  jmp     short loc_14003084B
0x14003080c  cmp     ebx, 0C0000023h
0x140030812  jnz     short loc_140030826
0x140030814  mov     rax, [rsp+48h+arg_20]
0x140030819  mov     ecx, [rsp+48h+arg_0]
0x14003081d  mov     [rax], ecx
0x14003081f  mov     eax, 7Ah ; 'z'
0x140030824  jmp     short loc_14003084B
0x140030826  mov     ecx, ebx; Status
0x140030828  call    cs:__imp_RtlNtStatusToDosError
0x14003082e  jmp     short loc_14003084B
0x140030830  mov     eax, [rsp+48h+arg_0]
0x140030834  mov     rcx, [rsp+48h+arg_20]
0x140030839  mov     [rcx], eax
0x14003083b  xor     eax, eax
0x14003083d  jmp     short loc_14003084B
0x14003083f  mov     eax, 57h ; 'W'
0x140030844  jmp     short loc_14003084B
0x140030846  mov     eax, 6
0x14003084b  mov     rbx, [rsp+48h+arg_8]
0x140030850  mov     rbp, [rsp+48h+arg_10]
0x140030855  add     rsp, 30h
0x140030859  pop     r14
0x14003085b  pop     rdi
0x14003085c  pop     rsi
0x14003085d  retn
```
