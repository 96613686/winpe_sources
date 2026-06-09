# SampMachineNameChangeCallBack(_POLICY_NOTIFICATION_INFORMATION_CLASS)

- ea: `0x18007c1b0`
- end: `0x18007c41c`
- name: `?SampMachineNameChangeCallBack@@YAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z`
- size: `620`
- prototype: `void __fastcall(enum _POLICY_NOTIFICATION_INFORMATION_CLASS)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180021400`
- `0x180027030`
- `0x180027080`
- `0x18002cd80`
- `0x18002d720`
- `0x18007c1b0`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18007c287`
- `ntdll!RtlEqualUnicodeString` at `0x18007c287`
- `ntdll!RtlFreeHeap` at `0x18007c30f`
- `ntdll!RtlFreeHeap` at `0x18007c3c3`
- `ntdll!RtlFreeHeap` at `0x18007c30f`
- `ntdll!RtlFreeHeap` at `0x18007c3c3`
- `ntdll!RtlAllocateHeap` at `0x18007c2b1`
- `ntdll!RtlAllocateHeap` at `0x18007c367`
- `ntdll!RtlAllocateHeap` at `0x18007c2b1`
- `ntdll!RtlAllocateHeap` at `0x18007c367`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007c23d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007c23d`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18007c20e`
- `LSASRV!LsaIQueryInformationPolicyTrusted` at `0x18007c20e`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18007c3f3`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x18007c3f3`
- `DNSAPI!DnsNameCompare_W` at `0x18007c335`
- `DNSAPI!DnsNameCompare_W` at `0x18007c335`

## pseudocode

```c
void __fastcall SampMachineNameChangeCallBack(__int64 a1, __int64 a2)
{
  int v2; // ebx
  BOOL ComputerName; // r13d
  unsigned int i; // esi
  struct _PSAMP_DEFINED_DOMAINS *v5; // rdi
  __int64 v6; // rbx
  char *v7; // r15
  unsigned int MaximumLength; // r12d
  PVOID Heap; // rax
  void *v10; // r14
  const WCHAR *v11; // rcx
  DWORD v12; // r15d
  PVOID v13; // rax
  void *v14; // r14
  void *v15; // r8
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  PCUNICODE_STRING String2; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = a1;
  String2 = 0;
  nSize = 257;
  if ( !(unsigned __int8)SampDsIsRunning(a1, a2) && v2 == 2 && (int)LsaIQueryInformationPolicyTrusted(5, &String2) >= 0 )
  {
    memset_0(Buffer, 0, 2LL * nSize);
    ComputerName = GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize);
    SampAcquireSamLockExclusive();
    for ( i = 0; i < SampDefinedDomainsCount; ++i )
    {
      v5 = SampDefinedDomains;
      v6 = 1360LL * i;
      if ( !*((_BYTE *)SampDefinedDomains + v6 + 1296) )
      {
        v7 = (char *)SampDefinedDomains + v6;
        if ( !RtlEqualUnicodeString((PCUNICODE_STRING)((char *)SampDefinedDomains + v6 + 16), String2, 1u) )
        {
          MaximumLength = String2->MaximumLength;
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, String2->MaximumLength);
          v10 = Heap;
          if ( Heap )
          {
            memset_0(Heap, 0, MaximumLength);
            memcpy_0(v10, String2->Buffer, MaximumLength);
            *((_WORD *)v7 + 8) = String2->Length;
            *(_WORD *)((char *)v5 + v6 + 18) = String2->MaximumLength;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)((char *)v5 + v6 + 24));
            *(_QWORD *)((char *)v5 + v6 + 24) = v10;
          }
        }
        if ( ComputerName )
        {
          v11 = *(const WCHAR **)((char *)v5 + v6 + 1328);
          if ( !v11 || !DnsNameCompare_W(v11, Buffer) )
          {
            v12 = 2 * nSize + 2;
            v13 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
            v14 = v13;
            if ( v13 )
            {
              memset_0(v13, 0, v12);
              memcpy_0(v14, Buffer, v12);
              v15 = *(void **)((char *)v5 + v6 + 1328);
              *(_WORD *)((char *)v5 + v6 + 1320) = v12 - 2;
              *(_WORD *)((char *)v5 + v6 + 1322) = v12;
              if ( v15 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
              *(_QWORD *)((char *)v5 + v6 + 1328) = v14;
            }
          }
        }
      }
    }
    SampReleaseSamLockExclusive();
    if ( String2 )
      LsaIFree_LSAPR_POLICY_INFORMATION(5, String2);
  }
}

```

## disassembly

```asm
0x18007c1b0  push    rbp
0x18007c1b2  push    rbx
0x18007c1b3  push    rsi
0x18007c1b4  push    rdi
0x18007c1b5  push    r12
0x18007c1b7  push    r13
0x18007c1b9  push    r14
0x18007c1bb  push    r15
0x18007c1bd  lea     rbp, [rsp-158h]
0x18007c1c5  sub     rsp, 258h
0x18007c1cc  mov     rax, cs:__security_cookie
0x18007c1d3  xor     rax, rsp
0x18007c1d6  mov     [rbp+190h+var_50], rax
0x18007c1dd  mov     ebx, ecx
0x18007c1df  mov     [rsp+290h+String2], 0
0x18007c1e8  mov     [rsp+290h+nSize], 101h
0x18007c1f0  call    SampDsIsRunning
0x18007c1f5  test    al, al
0x18007c1f7  jnz     loc_18007C3F9
0x18007c1fd  cmp     ebx, 2
0x18007c200  jnz     loc_18007C3F9
0x18007c206  lea     rdx, [rsp+290h+String2]
0x18007c20b  lea     ecx, [rbx+3]
0x18007c20e  call    cs:__imp_LsaIQueryInformationPolicyTrusted
0x18007c214  test    eax, eax
0x18007c216  js      loc_18007C3F9
0x18007c21c  mov     r8d, [rsp+290h+nSize]
0x18007c221  lea     rcx, [rsp+290h+Buffer]; void *
0x18007c226  add     r8, r8; Size
0x18007c229  xor     edx, edx; Val
0x18007c22b  call    memset_0
0x18007c230  lea     r8, [rsp+290h+nSize]; nSize
0x18007c235  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x18007c23a  lea     ecx, [rbx+1]; NameType
0x18007c23d  call    cs:__imp_GetComputerNameExW
0x18007c243  mov     r13d, eax
0x18007c246  call    SampAcquireSamLockExclusive
0x18007c24b  xor     esi, esi
0x18007c24d  cmp     cs:?SampDefinedDomainsCount@@3KA, esi; ulong SampDefinedDomainsCount
0x18007c253  jbe     loc_18007C3DF
0x18007c259  mov     rdi, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18007c260  mov     ecx, esi
0x18007c262  imul    rbx, rcx, 550h
0x18007c269  cmp     byte ptr [rbx+rdi+510h], 0
0x18007c271  jnz     loc_18007C3D1
0x18007c277  mov     rdx, [rsp+290h+String2]; String2
0x18007c27c  lea     r15, [rbx+rdi]
0x18007c280  lea     rcx, [r15+10h]; String1
0x18007c284  mov     r8b, 1; CaseInsensitive
0x18007c287  call    cs:__imp_RtlEqualUnicodeString
0x18007c28d  test    al, al
0x18007c28f  jnz     loc_18007C31A
0x18007c295  mov     rax, [rsp+290h+String2]
0x18007c29a  xor     edx, edx; Flags
0x18007c29c  mov     rcx, gs:60h
0x18007c2a5  movzx   r12d, word ptr [rax+2]
0x18007c2aa  mov     rcx, [rcx+30h]; HeapHandle
0x18007c2ae  mov     r8d, r12d; Size
0x18007c2b1  call    cs:__imp_RtlAllocateHeap
0x18007c2b7  mov     r14, rax
0x18007c2ba  test    rax, rax
0x18007c2bd  jz      short loc_18007C31A
0x18007c2bf  mov     r8d, r12d; Size
0x18007c2c2  xor     edx, edx; Val
0x18007c2c4  mov     rcx, rax; void *
0x18007c2c7  call    memset_0
0x18007c2cc  mov     rdx, [rsp+290h+String2]
0x18007c2d1  mov     r8d, r12d; Size
0x18007c2d4  mov     rcx, r14; void *
0x18007c2d7  mov     rdx, [rdx+8]; Src
0x18007c2db  call    memcpy_0
0x18007c2e0  mov     rcx, [rsp+290h+String2]
0x18007c2e5  movzx   edx, word ptr [rcx]
0x18007c2e8  mov     [r15+10h], dx
0x18007c2ed  xor     edx, edx; Flags
0x18007c2ef  mov     rax, [rsp+290h+String2]
0x18007c2f4  movzx   ecx, word ptr [rax+2]
0x18007c2f8  mov     [rbx+rdi+12h], cx
0x18007c2fd  mov     rcx, gs:60h
0x18007c306  mov     r8, [rbx+rdi+18h]; P
0x18007c30b  mov     rcx, [rcx+30h]; HeapHandle
0x18007c30f  call    cs:__imp_RtlFreeHeap
0x18007c315  mov     [rbx+rdi+18h], r14
0x18007c31a  test    r13d, r13d
0x18007c31d  jz      loc_18007C3D1
0x18007c323  mov     rcx, [rbx+rdi+530h]; pName1
0x18007c32b  test    rcx, rcx
0x18007c32e  jz      short loc_18007C343
0x18007c330  lea     rdx, [rsp+290h+Buffer]; pName2
0x18007c335  call    cs:__imp_DnsNameCompare_W
0x18007c33b  test    eax, eax
0x18007c33d  jnz     loc_18007C3D1
0x18007c343  mov     eax, [rsp+290h+nSize]
0x18007c347  mov     edx, 8; Flags
0x18007c34c  mov     rcx, gs:60h
0x18007c355  lea     r15d, ds:2[rax*2]
0x18007c35d  mov     rcx, [rcx+30h]; HeapHandle
0x18007c361  mov     r8d, r15d; Size
0x18007c364  mov     r12d, r15d
0x18007c367  call    cs:__imp_RtlAllocateHeap
0x18007c36d  mov     r14, rax
0x18007c370  test    rax, rax
0x18007c373  jz      short loc_18007C3D1
0x18007c375  mov     r8d, r12d; Size
0x18007c378  xor     edx, edx; Val
0x18007c37a  mov     rcx, rax; void *
0x18007c37d  call    memset_0
0x18007c382  mov     r8d, r12d; Size
0x18007c385  lea     rdx, [rsp+290h+Buffer]; Src
0x18007c38a  mov     rcx, r14; void *
0x18007c38d  call    memcpy_0
0x18007c392  mov     r8, [rbx+rdi+530h]; P
0x18007c39a  lea     ecx, [r15-2]
0x18007c39e  mov     [rbx+rdi+528h], cx
0x18007c3a6  mov     [rbx+rdi+52Ah], r15w
0x18007c3af  test    r8, r8
0x18007c3b2  jz      short loc_18007C3C9
0x18007c3b4  mov     rcx, gs:60h
0x18007c3bd  xor     edx, edx; Flags
0x18007c3bf  mov     rcx, [rcx+30h]; HeapHandle
0x18007c3c3  call    cs:__imp_RtlFreeHeap
0x18007c3c9  mov     [rbx+rdi+530h], r14
0x18007c3d1  inc     esi
0x18007c3d3  cmp     esi, cs:?SampDefinedDomainsCount@@3KA; ulong SampDefinedDomainsCount
0x18007c3d9  jb      loc_18007C259
0x18007c3df  call    SampReleaseSamLockExclusive
0x18007c3e4  mov     rdx, [rsp+290h+String2]
0x18007c3e9  test    rdx, rdx
0x18007c3ec  jz      short loc_18007C3F9
0x18007c3ee  mov     ecx, 5
0x18007c3f3  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x18007c3f9  mov     rcx, [rbp+190h+var_50]
0x18007c400  xor     rcx, rsp; StackCookie
0x18007c403  call    __security_check_cookie
0x18007c408  add     rsp, 258h
0x18007c40f  pop     r15
0x18007c411  pop     r14
0x18007c413  pop     r13
0x18007c415  pop     r12
0x18007c417  pop     rdi
0x18007c418  pop     rsi
0x18007c419  pop     rbx
0x18007c41a  pop     rbp
0x18007c41b  retn
```
