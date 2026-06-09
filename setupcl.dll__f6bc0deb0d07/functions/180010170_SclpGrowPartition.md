# SclpGrowPartition

- ea: `0x180010170`
- end: `0x18001053c`
- name: `SclpGrowPartition`
- size: `972`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000f6e4`

## callees

- `0x18000a524`
- `0x18000e8d4`
- `0x18000ea28`
- `0x18000fc6c`
- `0x180010170`
- `0x180010544`
- `0x1800179e0`

## import_xrefs

- `ntdll!NtClose` at `0x18001044f`
- `ntdll!NtClose` at `0x18001048b`
- `ntdll!NtClose` at `0x180010505`
- `ntdll!NtClose` at `0x180010514`
- `ntdll!NtClose` at `0x18001044f`
- `ntdll!NtClose` at `0x18001048b`
- `ntdll!NtClose` at `0x180010505`
- `ntdll!NtClose` at `0x180010514`
- `ntdll!RtlFreeHeap` at `0x180010476`
- `ntdll!RtlFreeHeap` at `0x1800104f7`
- `ntdll!RtlFreeHeap` at `0x180010476`
- `ntdll!RtlFreeHeap` at `0x1800104f7`
- `ntdll!NtQuerySystemInformation` at `0x1800101cc`
- `ntdll!NtQuerySystemInformation` at `0x1800101cc`
- `ntdll!_wcsicmp` at `0x180010353`
- `ntdll!_wcsicmp` at `0x180010353`

## string_xrefs

- `0x180010411`: `Partition/Volume extension succeeded.`

## pseudocode

```c
__int64 __fastcall SclpGrowPartition(__int64 a1)
{
  PVOID v1; // rbx
  HANDLE v3; // rdi
  NTSTATUS v4; // eax
  __int64 v5; // r14
  int VolumeHandle; // esi
  unsigned int i; // r12d
  int DiskLayout; // eax
  unsigned int v9; // r8d
  __int64 j; // r9
  unsigned int v11; // ecx
  char *v12; // r13
  __int64 v14; // [rsp+38h] [rbp-41h]
  char v15; // [rsp+40h] [rbp-39h]
  HANDLE v16; // [rsp+48h] [rbp-31h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-29h] BYREF
  PVOID P; // [rsp+58h] [rbp-21h] BYREF
  int v19; // [rsp+60h] [rbp-19h] BYREF
  __int128 SystemInformation; // [rsp+68h] [rbp-11h] BYREF
  __int64 v21; // [rsp+78h] [rbp-1h]

  v1 = 0;
  v19 = 0;
  P = 0;
  v16 = 0;
  v3 = 0;
  v21 = 0;
  Handle = 0;
  SystemInformation = 0;
  v4 = NtQuerySystemInformation(SystemDeviceInformation, &SystemInformation, 0x18u, 0);
  v5 = a1 + 1152;
  VolumeHandle = v4;
  if ( v4 >= 0 )
  {
    v15 = 0;
    if ( !a1 )
      v5 = 0;
    SclLogGenericMessage(
      v5,
      1,
      (int)SclEvent_Generic_Info,
      169,
      (__int64)"SclpGrowPartition",
      "Found [%lu] disks",
      (_DWORD)SystemInformation);
    for ( i = 0; VolumeHandle >= 0 && i < (unsigned int)SystemInformation; ++i )
    {
      if ( v15 )
        goto LABEL_36;
      SclLogGenericMessage(
        v5,
        1,
        (int)SclEvent_Generic_Info,
        177,
        (__int64)"SclpGrowPartition",
        "Inspecting disk [%u]",
        i);
      if ( (int)SclGetDiskHandle(a1, i, &v16) >= 0 )
      {
        DiskLayout = SclGetDiskLayout(a1, v16, &P, &v19);
        v1 = P;
        VolumeHandle = DiskLayout;
        if ( DiskLayout < 0 )
          goto LABEL_32;
        v9 = 0;
        for ( j = 0; (unsigned int)j < *((_DWORD *)P + 1); v9 = v11 )
        {
          v11 = j;
          if ( *((_QWORD *)P + 18 * j + 7) <= *((_QWORD *)P + 18 * v9 + 7) )
            v11 = v9;
          j = (unsigned int)(j + 1);
        }
        v12 = (char *)P + 144 * v9 + 48;
        if ( *(_DWORD *)v12 == 1 && !_wcsicmp((const wchar_t *)v12 + 36, (const wchar_t *)(a1 + 1080)) )
        {
          LODWORD(v14) = i;
          SclLogGenericMessage(
            v5,
            1,
            (int)SclEvent_Generic_Info,
            223,
            (__int64)"SclpGrowPartition",
            "Partition [%ws] found in disk [%d].",
            a1 + 1080,
            v14);
          VolumeHandle = SclpGetVolumeHandle(a1, i, *((_QWORD *)v12 + 1), &Handle);
          if ( VolumeHandle < 0 )
          {
            v3 = Handle;
            goto LABEL_32;
          }
          SclLogGenericMessage(
            v5,
            1,
            (int)SclEvent_Generic_Info,
            239,
            (__int64)"SclpGrowPartition",
            "Corresponding volume is also found.");
          v3 = Handle;
          VolumeHandle = SclpGrowPartitionInternal(a1, v16, Handle, v1, v12);
          if ( VolumeHandle < 0 )
            goto LABEL_32;
          v15 = 1;
          SclLogGenericMessage(
            v5,
            1,
            (int)SclEvent_Generic_Info,
            255,
            (__int64)"SclpGrowPartition",
            "Partition/Volume extension succeeded.");
          if ( v3 )
            NtClose(v3);
          v3 = 0;
          Handle = 0;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
        v1 = 0;
        P = 0;
        if ( v16 )
          NtClose(v16);
        v16 = 0;
      }
      else
      {
        VolumeHandle = 0;
      }
    }
    if ( v15 )
      goto LABEL_36;
    SclLogGenericMessage(
      v5,
      1,
      (int)SclEvent_Generic_Info,
      270,
      (__int64)"SclpGrowPartition",
      "Partition [%ws] not found.",
      a1 + 1080);
LABEL_32:
    if ( v1 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
    if ( v3 )
      NtClose(v3);
  }
  else
  {
    if ( !a1 )
      v5 = 0;
    SclLogGenericMessage(
      v5,
      3,
      (int)SclEvent_Generic_Error,
      162,
      (__int64)"SclpGrowPartition",
      "(%lx): Unable to get system device information.",
      v4);
  }
LABEL_36:
  if ( v16 )
    NtClose(v16);
  return (unsigned int)VolumeHandle;
}

```

## disassembly

```asm
0x180010170  push    rbp
0x180010172  push    rbx
0x180010173  push    rsi
0x180010174  push    rdi
0x180010175  push    r12
0x180010177  push    r13
0x180010179  push    r14
0x18001017b  push    r15
0x18001017d  lea     rbp, [rsp-1Fh]
0x180010182  sub     rsp, 98h
0x180010189  mov     rax, cs:__security_cookie
0x180010190  xor     rax, rsp
0x180010193  mov     [rbp+57h+var_50], rax
0x180010197  xor     ebx, ebx
0x180010199  mov     [rbp+57h+var_70], 0
0x1800101a0  mov     r15, rcx
0x1800101a3  mov     [rbp+57h+P], rbx
0x1800101a7  xorps   xmm0, xmm0
0x1800101aa  mov     [rbp+57h+var_88], rbx
0x1800101ae  xor     eax, eax
0x1800101b0  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1800101b4  xor     edi, edi
0x1800101b6  mov     [rbp+57h+var_58], rax
0x1800101ba  lea     r8d, [rbx+18h]; SystemInformationLength
0x1800101be  mov     [rbp+57h+Handle], rdi
0x1800101c2  lea     ecx, [rbx+7]; SystemInformationClass
0x1800101c5  xor     r9d, r9d; ReturnLength
0x1800101c8  movups  [rbp+57h+SystemInformation], xmm0
0x1800101cc  call    cs:__imp_NtQuerySystemInformation
0x1800101d2  lea     r14, [r15+480h]
0x1800101d9  mov     esi, eax
0x1800101db  test    eax, eax
0x1800101dd  jns     short loc_180010221
0x1800101df  xor     ecx, ecx
0x1800101e1  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1800101e5  test    r15, r15
0x1800101e8  lea     rax, aLxUnableToGetS; "(%lx): Unable to get system device info"...
0x1800101ef  mov     [rsp+0D0h+var_A8], rax
0x1800101f4  lea     rdi, aSclpgrowpartit; "SclpGrowPartition"
0x1800101fb  cmovz   r14, rcx
0x1800101ff  mov     [rsp+0D0h+var_B0], rdi
0x180010204  mov     rcx, r14
0x180010207  lea     r8, SclEvent_Generic_Error
0x18001020e  mov     r9d, 0A2h
0x180010214  lea     edx, [rbx+3]
0x180010217  call    SclLogGenericMessage
0x18001021c  jmp     loc_18001050B
0x180010221  xor     eax, eax
0x180010223  mov     [rbp+57h+var_90], bl
0x180010226  test    r15, r15
0x180010229  lea     r13, aSclpgrowpartit; "SclpGrowPartition"
0x180010230  mov     r9d, 0A9h
0x180010236  lea     r8, SclEvent_Generic_Info
0x18001023d  cmovz   r14, rax
0x180010241  mov     edx, 1
0x180010246  mov     eax, dword ptr [rbp+57h+SystemInformation]
0x180010249  mov     rcx, r14
0x18001024c  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180010250  lea     rax, aFoundLuDisks; "Found [%lu] disks"
0x180010257  mov     [rsp+0D0h+var_A8], rax
0x18001025c  mov     [rsp+0D0h+var_B0], r13
0x180010261  call    SclLogGenericMessage
0x180010266  xor     r12d, r12d
0x180010269  test    esi, esi
0x18001026b  js      loc_1800104A3
0x180010271  cmp     r12d, dword ptr [rbp+57h+SystemInformation]
0x180010275  jnb     loc_1800104A3
0x18001027b  cmp     [rbp+57h+var_90], 0
0x18001027f  jnz     loc_18001050B
0x180010285  lea     rax, aInspectingDisk_0; "Inspecting disk [%u]"
0x18001028c  mov     dword ptr [rsp+0D0h+var_A0], r12d
0x180010291  mov     [rsp+0D0h+var_A8], rax
0x180010296  lea     r8, SclEvent_Generic_Info
0x18001029d  mov     r9d, 0B1h
0x1800102a3  mov     [rsp+0D0h+var_B0], r13
0x1800102a8  mov     edx, 1
0x1800102ad  mov     rcx, r14
0x1800102b0  call    SclLogGenericMessage
0x1800102b5  lea     r8, [rbp+57h+var_88]
0x1800102b9  mov     edx, r12d
0x1800102bc  mov     rcx, r15
0x1800102bf  call    SclGetDiskHandle
0x1800102c4  test    eax, eax
0x1800102c6  jns     short loc_1800102CF
0x1800102c8  xor     esi, esi
0x1800102ca  jmp     loc_180010495
0x1800102cf  mov     rdx, [rbp+57h+var_88]
0x1800102d3  lea     r9, [rbp+57h+var_70]
0x1800102d7  lea     r8, [rbp+57h+P]
0x1800102db  mov     rcx, r15
0x1800102de  call    SclGetDiskLayout
0x1800102e3  mov     rbx, [rbp+57h+P]
0x1800102e7  mov     esi, eax
0x1800102e9  test    eax, eax
0x1800102eb  js      loc_1800104E0
0x1800102f1  xor     r8d, r8d
0x1800102f4  xor     r9d, r9d
0x1800102f7  cmp     [rbx+4], r8d
0x1800102fb  jbe     short loc_18001032B
0x1800102fd  mov     eax, r8d
0x180010300  lea     rdx, [r9+r9*8]
0x180010304  add     rdx, rdx
0x180010307  mov     ecx, r9d
0x18001030a  lea     rax, [rax+rax*8]
0x18001030e  add     rax, rax
0x180010311  mov     rax, [rbx+rax*8+38h]
0x180010316  cmp     [rbx+rdx*8+38h], rax
0x18001031b  cmovle  ecx, r8d
0x18001031f  inc     r9d
0x180010322  mov     r8d, ecx
0x180010325  cmp     r9d, [rbx+4]
0x180010329  jb      short loc_1800102FD
0x18001032b  mov     eax, r8d
0x18001032e  lea     r13, [rax+rax*8]
0x180010332  shl     r13, 4
0x180010336  add     r13, 30h ; '0'
0x18001033a  add     r13, rbx
0x18001033d  cmp     dword ptr [r13+0], 1
0x180010342  jnz     loc_18001045D
0x180010348  lea     rdx, [r15+438h]; String2
0x18001034f  lea     rcx, [r13+48h]; String1
0x180010353  call    cs:__imp__wcsicmp
0x180010359  test    eax, eax
0x18001035b  jnz     loc_18001045D
0x180010361  mov     dword ptr [rsp+0D0h+var_98], r12d
0x180010366  lea     rax, [r15+438h]
0x18001036d  mov     [rsp+0D0h+var_A0], rax
0x180010372  lea     rdi, aSclpgrowpartit; "SclpGrowPartition"
0x180010379  lea     rax, aPartitionWsFou; "Partition [%ws] found in disk [%d]."
0x180010380  mov     r9d, 0DFh
0x180010386  mov     [rsp+0D0h+var_A8], rax
0x18001038b  lea     r8, SclEvent_Generic_Info
0x180010392  mov     edx, 1
0x180010397  mov     [rsp+0D0h+var_B0], rdi
0x18001039c  mov     rcx, r14
0x18001039f  call    SclLogGenericMessage
0x1800103a4  mov     r8, [r13+8]
0x1800103a8  lea     r9, [rbp+57h+Handle]
0x1800103ac  mov     edx, r12d
0x1800103af  mov     rcx, r15
0x1800103b2  call    SclpGetVolumeHandle
0x1800103b7  mov     esi, eax
0x1800103b9  test    eax, eax
0x1800103bb  js      loc_18001049D
0x1800103c1  lea     rax, aCorrespondingV; "Corresponding volume is also found."
0x1800103c8  mov     r9d, 0EFh
0x1800103ce  mov     [rsp+0D0h+var_A8], rax
0x1800103d3  lea     r8, SclEvent_Generic_Info
0x1800103da  mov     edx, 1
0x1800103df  mov     [rsp+0D0h+var_B0], rdi
0x1800103e4  mov     rcx, r14
0x1800103e7  call    SclLogGenericMessage
0x1800103ec  mov     rdi, [rbp+57h+Handle]
0x1800103f0  mov     r9, rbx
0x1800103f3  mov     rdx, [rbp+57h+var_88]
0x1800103f7  mov     r8, rdi
0x1800103fa  mov     rcx, r15
0x1800103fd  mov     [rsp+0D0h+var_B0], r13
0x180010402  call    SclpGrowPartitionInternal
0x180010407  mov     esi, eax
0x180010409  test    eax, eax
0x18001040b  js      loc_1800104E0
0x180010411  lea     rax, aPartitionVolum; "Partition/Volume extension succeeded."
0x180010418  mov     [rbp+57h+var_90], 1
0x18001041c  mov     [rsp+0D0h+var_A8], rax
0x180010421  lea     r13, aSclpgrowpartit; "SclpGrowPartition"
0x180010428  mov     r9d, 0FFh
0x18001042e  mov     [rsp+0D0h+var_B0], r13
0x180010433  lea     r8, SclEvent_Generic_Info
0x18001043a  mov     edx, 1
0x18001043f  mov     rcx, r14
0x180010442  call    SclLogGenericMessage
0x180010447  test    rdi, rdi
0x18001044a  jz      short loc_180010455
0x18001044c  mov     rcx, rdi; Handle
0x18001044f  call    cs:__imp_NtClose
0x180010455  xor     edi, edi
0x180010457  mov     [rbp+57h+Handle], rdi
0x18001045b  jmp     short loc_180010464
0x18001045d  lea     r13, aSclpgrowpartit; "SclpGrowPartition"
0x180010464  mov     rcx, gs:60h
0x18001046d  mov     r8, rbx; P
0x180010470  xor     edx, edx; Flags
0x180010472  mov     rcx, [rcx+30h]; HeapHandle
0x180010476  call    cs:__imp_RtlFreeHeap
0x18001047c  mov     rcx, [rbp+57h+var_88]; Handle
0x180010480  xor     ebx, ebx
0x180010482  mov     [rbp+57h+P], rbx
0x180010486  test    rcx, rcx
0x180010489  jz      short loc_180010491
0x18001048b  call    cs:__imp_NtClose
0x180010491  mov     [rbp+57h+var_88], rbx
0x180010495  inc     r12d
0x180010498  jmp     loc_180010269
0x18001049d  mov     rdi, [rbp+57h+Handle]
0x1800104a1  jmp     short loc_1800104E0
0x1800104a3  cmp     [rbp+57h+var_90], 0
0x1800104a7  jnz     short loc_18001050B
0x1800104a9  lea     rax, [r15+438h]
0x1800104b0  mov     r9d, 10Eh
0x1800104b6  mov     [rsp+0D0h+var_A0], rax
0x1800104bb  lea     r8, SclEvent_Generic_Info
0x1800104c2  lea     rax, aPartitionWsNot; "Partition [%ws] not found."
0x1800104c9  mov     edx, 1
0x1800104ce  mov     [rsp+0D0h+var_A8], rax
0x1800104d3  mov     rcx, r14
0x1800104d6  mov     [rsp+0D0h+var_B0], r13
0x1800104db  call    SclLogGenericMessage
0x1800104e0  test    rbx, rbx
0x1800104e3  jz      short loc_1800104FD
0x1800104e5  mov     rcx, gs:60h
0x1800104ee  mov     r8, rbx; P
0x1800104f1  xor     edx, edx; Flags
0x1800104f3  mov     rcx, [rcx+30h]; HeapHandle
0x1800104f7  call    cs:__imp_RtlFreeHeap
0x1800104fd  test    rdi, rdi
0x180010500  jz      short loc_18001050B
0x180010502  mov     rcx, rdi; Handle
0x180010505  call    cs:__imp_NtClose
0x18001050b  mov     rcx, [rbp+57h+var_88]; Handle
0x18001050f  test    rcx, rcx
0x180010512  jz      short loc_18001051A
0x180010514  call    cs:__imp_NtClose
0x18001051a  mov     eax, esi
0x18001051c  mov     rcx, [rbp+57h+var_50]
0x180010520  xor     rcx, rsp; StackCookie
0x180010523  call    __security_check_cookie
0x180010528  add     rsp, 98h
0x18001052f  pop     r15
0x180010531  pop     r14
0x180010533  pop     r13
0x180010535  pop     r12
0x180010537  pop     rdi
0x180010538  pop     rsi
0x180010539  pop     rbx
0x18001053a  pop     rbp
0x18001053b  retn
```
