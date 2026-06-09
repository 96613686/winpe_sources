# SclGetPendedRequest

- ea: `0x180002010`
- end: `0x1800025e4`
- name: `SclGetPendedRequest`
- size: `1492`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002a60`
- `0x180005a90`
- `0x1800061b0`

## callees

- `0x180001f70`
- `0x180002010`
- `0x180004c88`
- `0x18000505c`
- `0x180006484`
- `0x18000952c`
- `0x180009668`
- `0x18000a4a0`
- `0x18000a524`
- `0x18000aa80`
- `0x18000de94`
- `0x1800179ad`
- `0x1800179c5`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000217f`
- `ntdll!RtlAllocateHeap` at `0x180002277`
- `ntdll!RtlAllocateHeap` at `0x180002442`
- `ntdll!RtlAllocateHeap` at `0x18000217f`
- `ntdll!RtlAllocateHeap` at `0x180002277`
- `ntdll!RtlAllocateHeap` at `0x180002442`
- `ntdll!NtClose` at `0x1800025bd`
- `ntdll!NtClose` at `0x1800025bd`
- `ntdll!RtlFreeHeap` at `0x1800020f2`
- `ntdll!RtlFreeHeap` at `0x1800021eb`
- `ntdll!RtlFreeHeap` at `0x1800022e4`
- `ntdll!RtlFreeHeap` at `0x1800024ad`
- `ntdll!RtlFreeHeap` at `0x180002519`
- `ntdll!RtlFreeHeap` at `0x1800020f2`
- `ntdll!RtlFreeHeap` at `0x1800021eb`
- `ntdll!RtlFreeHeap` at `0x1800022e4`
- `ntdll!RtlFreeHeap` at `0x1800024ad`
- `ntdll!RtlFreeHeap` at `0x180002519`

## string_xrefs

- `0x1800021a6`: `SclRetrieveSid`
- `0x18000229e`: `SclRetrieveSid`
- `0x180002108`: `SidAccountDomainOld`
- `0x180002156`: `SidAccountDomainOld`
- `0x180002206`: `SidAccountDomainNew`
- `0x18000224e`: `SidAccountDomainNew`
- `0x1800024d7`: `SclpCanonicalizePaths failed. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall SclGetPendedRequest(__int64 a1, void *a2)
{
  int v4; // ebx
  HANDLE Handle; // [rsp+A8h] [rbp+58h] BYREF

  if ( !(unsigned __int8)SclOSIsValid() || !a2 )
    return 3221225485LL;
  Handle = 0;
  memset_0(a2, 0, 0x478u);
  v4 = SclpStateOpenRequestKey(a1, &Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = SclRegValueExists(Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = SclRegValueExists(Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = SclRegValueExists(Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = SclRegValueExists(Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = SclRegValueExists(Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = SclRegValueExists(Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  v4 = SclRegValueExists(Handle);
  if ( v4 < 0 )
    goto LABEL_13;
  if ( !(unsigned __int8)SclRequestIsValid(a1, a2) )
  {
    SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 1306, (__int64)"SclGetPendedRequest");
    v4 = -1073741637;
LABEL_13:
    SclFreeRequest(a2);
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002010  mov     [rsp-38h+arg_0], rbx
0x180002015  push    rbp
0x180002016  push    rsi
0x180002017  push    rdi
0x180002018  push    r12
0x18000201a  push    r13
0x18000201c  push    r14
0x18000201e  push    r15
0x180002020  mov     rbp, rsp
0x180002023  sub     rsp, 50h
0x180002027  xor     r13d, r13d
0x18000202a  mov     rsi, rdx
0x18000202d  mov     [rbp+arg_10], r13b
0x180002031  mov     r12, rcx
0x180002034  call    SclOSIsValid
0x180002039  test    al, al
0x18000203b  jz      loc_1800025C7
0x180002041  test    rsi, rsi
0x180002044  jz      loc_1800025C7
0x18000204a  xor     edx, edx; Val
0x18000204c  mov     [rbp+Handle], r13
0x180002050  mov     r8d, 478h; Size
0x180002056  mov     rcx, rsi; void *
0x180002059  call    memset_0
0x18000205e  lea     rdx, [rbp+Handle]
0x180002062  mov     rcx, r12
0x180002065  call    SclpStateOpenRequestKey
0x18000206a  mov     ebx, eax
0x18000206c  test    eax, eax
0x18000206e  js      loc_1800025AC
0x180002074  mov     rcx, [rbp+Handle]; KeyHandle
0x180002078  lea     r8, [rbp+arg_10]
0x18000207c  lea     rdx, aOperationflags; "OperationFlags"
0x180002083  call    SclRegValueExists
0x180002088  mov     ebx, eax
0x18000208a  test    eax, eax
0x18000208c  js      loc_1800025AC
0x180002092  cmp     [rbp+arg_10], r13b
0x180002096  jz      short loc_180002100
0x180002098  mov     rcx, [rbp+Handle]; KeyHandle
0x18000209c  lea     r9, [rbp+P]
0x1800020a0  xor     r8d, r8d
0x1800020a3  mov     [rbp+P], r13
0x1800020a7  lea     rdx, aOperationflags; "OperationFlags"
0x1800020ae  call    SclRegGetValue
0x1800020b3  mov     ebx, eax
0x1800020b5  test    eax, eax
0x1800020b7  js      loc_1800025AC
0x1800020bd  mov     r8, [rbp+P]; P
0x1800020c1  cmp     dword ptr [r8+4], 4
0x1800020c6  jz      short loc_1800020CF
0x1800020c8  mov     ebx, 0C0000024h
0x1800020cd  jmp     short loc_1800020E3
0x1800020cf  cmp     dword ptr [r8+8], 4
0x1800020d4  jz      short loc_1800020DD
0x1800020d6  mov     ebx, 0C0000004h
0x1800020db  jmp     short loc_1800020E3
0x1800020dd  mov     eax, [r8+0Ch]
0x1800020e1  mov     [rsi], eax
0x1800020e3  mov     rcx, gs:60h
0x1800020ec  xor     edx, edx; Flags
0x1800020ee  mov     rcx, [rcx+30h]; HeapHandle
0x1800020f2  call    cs:__imp_RtlFreeHeap
0x1800020f8  test    ebx, ebx
0x1800020fa  js      loc_1800025AC
0x180002100  mov     rcx, [rbp+Handle]; KeyHandle
0x180002104  lea     r8, [rbp+arg_10]
0x180002108  lea     rdx, aSidaccountdoma; "SidAccountDomainOld"
0x18000210f  call    SclRegValueExists
0x180002114  mov     ebx, eax
0x180002116  test    eax, eax
0x180002118  js      loc_1800025AC
0x18000211e  mov     r14d, 0C000000Dh
0x180002124  cmp     [rbp+arg_10], r13b
0x180002128  jz      loc_1800021FE
0x18000212e  mov     rcx, [rbp+Handle]; KeyHandle
0x180002132  test    rcx, rcx
0x180002135  jz      loc_1800021F3
0x18000213b  lea     r15, [rsi+8]
0x18000213f  test    r15, r15
0x180002142  jz      loc_1800021F3
0x180002148  lea     r9, [rbp+P]
0x18000214c  mov     [rbp+P], r13
0x180002150  mov     r8d, 10h
0x180002156  lea     rdx, aSidaccountdoma; "SidAccountDomainOld"
0x18000215d  call    SclRegGetValue
0x180002162  mov     rdi, [rbp+P]
0x180002166  mov     ebx, eax
0x180002168  test    eax, eax
0x18000216a  js      short loc_1800021D4
0x18000216c  mov     rcx, gs:60h
0x180002175  xor     edx, edx; Flags
0x180002177  mov     r8d, [rdi+8]; Size
0x18000217b  mov     rcx, [rcx+30h]; HeapHandle
0x18000217f  call    cs:__imp_RtlAllocateHeap
0x180002185  mov     [r15], rax
0x180002188  test    rax, rax
0x18000218b  jnz     short loc_1800021C4
0x18000218d  lea     rax, aCallToSclalloc; "Call to SclAlloc failed!"
0x180002194  mov     r9d, 102h
0x18000219a  mov     [rsp+50h+var_28], rax
0x18000219f  lea     r8, SclEvent_Generic_Error
0x1800021a6  lea     rax, aSclretrievesid; "SclRetrieveSid"
0x1800021ad  mov     edx, 3
0x1800021b2  xor     ecx, ecx
0x1800021b4  mov     qword ptr [rsp+50h+var_30], rax
0x1800021b9  lea     ebx, [r14+0Ah]
0x1800021bd  call    SclLogGenericMessage
0x1800021c2  jmp     short loc_1800021D4
0x1800021c4  mov     r8d, [rdi+8]; Size
0x1800021c8  lea     rdx, [rdi+0Ch]; Src
0x1800021cc  mov     rcx, rax; void *
0x1800021cf  call    memcpy_0
0x1800021d4  test    rdi, rdi
0x1800021d7  jz      short loc_1800021F6
0x1800021d9  mov     rcx, gs:60h
0x1800021e2  mov     r8, rdi; P
0x1800021e5  xor     edx, edx; Flags
0x1800021e7  mov     rcx, [rcx+30h]; HeapHandle
0x1800021eb  call    cs:__imp_RtlFreeHeap
0x1800021f1  jmp     short loc_1800021F6
0x1800021f3  mov     ebx, r14d
0x1800021f6  test    ebx, ebx
0x1800021f8  js      loc_1800025AC
0x1800021fe  mov     rcx, [rbp+Handle]; KeyHandle
0x180002202  lea     r8, [rbp+arg_10]
0x180002206  lea     rdx, aSidaccountdoma_0; "SidAccountDomainNew"
0x18000220d  call    SclRegValueExists
0x180002212  mov     ebx, eax
0x180002214  test    eax, eax
0x180002216  js      loc_1800025AC
0x18000221c  cmp     [rbp+arg_10], r13b
0x180002220  jz      loc_1800022F7
0x180002226  mov     rcx, [rbp+Handle]; KeyHandle
0x18000222a  test    rcx, rcx
0x18000222d  jz      loc_1800022EC
0x180002233  lea     r15, [rsi+10h]
0x180002237  test    r15, r15
0x18000223a  jz      loc_1800022EC
0x180002240  lea     r9, [rbp+P]
0x180002244  mov     [rbp+P], r13
0x180002248  mov     r8d, 10h
0x18000224e  lea     rdx, aSidaccountdoma_0; "SidAccountDomainNew"
0x180002255  call    SclRegGetValue
0x18000225a  mov     rdi, [rbp+P]
0x18000225e  mov     ebx, eax
0x180002260  test    eax, eax
0x180002262  js      short loc_1800022CD
0x180002264  mov     rcx, gs:60h
0x18000226d  xor     edx, edx; Flags
0x18000226f  mov     r8d, [rdi+8]; Size
0x180002273  mov     rcx, [rcx+30h]; HeapHandle
0x180002277  call    cs:__imp_RtlAllocateHeap
0x18000227d  mov     [r15], rax
0x180002280  test    rax, rax
0x180002283  jnz     short loc_1800022BD
0x180002285  lea     rax, aCallToSclalloc; "Call to SclAlloc failed!"
0x18000228c  mov     r9d, 102h
0x180002292  mov     [rsp+50h+var_28], rax
0x180002297  lea     r8, SclEvent_Generic_Error
0x18000229e  lea     rax, aSclretrievesid; "SclRetrieveSid"
0x1800022a5  mov     edx, 3
0x1800022aa  xor     ecx, ecx
0x1800022ac  mov     qword ptr [rsp+50h+var_30], rax
0x1800022b1  mov     ebx, 0C0000017h
0x1800022b6  call    SclLogGenericMessage
0x1800022bb  jmp     short loc_1800022CD
0x1800022bd  mov     r8d, [rdi+8]; Size
0x1800022c1  lea     rdx, [rdi+0Ch]; Src
0x1800022c5  mov     rcx, rax; void *
0x1800022c8  call    memcpy_0
0x1800022cd  test    rdi, rdi
0x1800022d0  jz      short loc_1800022EF
0x1800022d2  mov     rcx, gs:60h
0x1800022db  mov     r8, rdi; P
0x1800022de  xor     edx, edx; Flags
0x1800022e0  mov     rcx, [rcx+30h]; HeapHandle
0x1800022e4  call    cs:__imp_RtlFreeHeap
0x1800022ea  jmp     short loc_1800022EF
0x1800022ec  mov     ebx, r14d
0x1800022ef  test    ebx, ebx
0x1800022f1  js      loc_1800025AC
0x1800022f7  mov     rcx, [rbp+Handle]; KeyHandle
0x1800022fb  lea     r8, [rbp+arg_10]
0x1800022ff  lea     rdx, aWindirold; "WinDirOld"
0x180002306  call    SclRegValueExists
0x18000230b  mov     ebx, eax
0x18000230d  test    eax, eax
0x18000230f  js      loc_1800025AC
0x180002315  mov     r15d, 5Ch ; '\'
0x18000231b  cmp     [rbp+arg_10], r13b
0x18000231f  jz      short loc_180002363
0x180002321  mov     rcx, [rbp+Handle]
0x180002325  lea     r9, [rsi+18h]
0x180002329  lea     r8, aWindirold; "WinDirOld"
0x180002330  mov     [rsp+50h+var_30], 104h
0x180002338  xor     edx, edx
0x18000233a  call    SclRegGetString
0x18000233f  mov     ebx, eax
0x180002341  test    eax, eax
0x180002343  js      loc_1800025AC
0x180002349  mov     r8d, r15d
0x18000234c  lea     edx, [r15+20h]
0x180002350  lea     rcx, [rsi+18h]
0x180002354  call    SclReplaceCharInString
0x180002359  mov     ebx, eax
0x18000235b  test    eax, eax
0x18000235d  js      loc_1800025AC
0x180002363  mov     rcx, [rbp+Handle]; KeyHandle
0x180002367  lea     r8, [rbp+arg_10]
0x18000236b  lea     rdx, aWindirnew; "WinDirNew"
0x180002372  call    SclRegValueExists
0x180002377  mov     ebx, eax
0x180002379  test    eax, eax
0x18000237b  js      loc_1800025AC
0x180002381  cmp     [rbp+arg_10], r13b
0x180002385  jz      short loc_1800023CF
0x180002387  mov     rcx, [rbp+Handle]
0x18000238b  lea     rdi, [rsi+220h]
0x180002392  mov     r9, rdi
0x180002395  mov     [rsp+50h+var_30], 104h; ULONG
0x18000239d  lea     r8, aWindirnew; "WinDirNew"
0x1800023a4  xor     edx, edx
0x1800023a6  call    SclRegGetString
0x1800023ab  mov     ebx, eax
0x1800023ad  test    eax, eax
0x1800023af  js      loc_1800025AC
0x1800023b5  mov     r8d, r15d
0x1800023b8  mov     edx, 7Ch ; '|'
0x1800023bd  mov     rcx, rdi
0x1800023c0  call    SclReplaceCharInString
0x1800023c5  mov     ebx, eax
0x1800023c7  test    eax, eax
0x1800023c9  js      loc_1800025AC
0x1800023cf  mov     rcx, [rbp+Handle]; KeyHandle
0x1800023d3  lea     r8, [rbp+arg_10]
0x1800023d7  lea     rdx, aOsFootprint; "OS Footprint"
0x1800023de  call    SclRegValueExists
0x1800023e3  mov     ebx, eax
0x1800023e5  test    eax, eax
0x1800023e7  js      loc_1800025AC
0x1800023ed  lea     r15, aSclgetpendedre_0; "SclGetPendedRequest"
0x1800023f4  cmp     [rbp+arg_10], r13b
0x1800023f8  jz      loc_180002527
0x1800023fe  mov     rcx, [rbp+Handle]; KeyHandle
0x180002402  mov     rdi, r13
0x180002405  test    rcx, rcx
0x180002408  jz      loc_1800024FF
0x18000240e  lea     r9, [rbp+P]
0x180002412  mov     [rbp+P], r13
0x180002416  xor     r8d, r8d
0x180002419  lea     rdx, aOsFootprint; "OS Footprint"
0x180002420  call    SclRegGetValue
0x180002425  mov     r14, [rbp+P]
0x180002429  mov     ebx, eax
0x18000242b  test    eax, eax
0x18000242d  js      short loc_180002496
0x18000242f  mov     rcx, gs:60h
0x180002438  xor     edx, edx; Flags
0x18000243a  mov     r8d, [r14+8]; Size
0x18000243e  mov     rcx, [rcx+30h]; HeapHandle
0x180002442  call    cs:__imp_RtlAllocateHeap
0x180002448  mov     rdi, rax
0x18000244b  test    rax, rax
0x18000244e  jnz     short loc_180002486
0x180002450  lea     rax, aCallToSclalloc; "Call to SclAlloc failed!"
0x180002457  mov     r9d, 1A8h
0x18000245d  mov     [rsp+50h+var_28], rax
0x180002462  lea     r8, SclEvent_Generic_Error
0x180002469  lea     rax, aSclretrievemul; "SclRetrieveMultiSz"
0x180002470  xor     ecx, ecx
0x180002472  lea     edx, [rdi+3]
0x180002475  mov     qword ptr [rsp+50h+var_30], rax
0x18000247a  mov     ebx, 0C0000017h
0x18000247f  call    SclLogGenericMessage
0x180002484  jmp     short loc_180002496
0x180002486  mov     r8d, [r14+8]; Size
0x18000248a  lea     rdx, [r14+0Ch]; Src
0x18000248e  mov     rcx, rax; void *
0x180002491  call    memcpy_0
0x180002496  test    r14, r14
0x180002499  jz      short loc_1800024B3
0x18000249b  mov     rcx, gs:60h
0x1800024a4  mov     r8, r14; P
0x1800024a7  xor     edx, edx; Flags
0x1800024a9  mov     rcx, [rcx+30h]; HeapHandle
0x1800024ad  call    cs:__imp_RtlFreeHeap
0x1800024b3  test    ebx, ebx
0x1800024b5  js      short loc_180002502
0x1800024b7  lea     r8, [rsi+428h]
0x1800024be  mov     rdx, rdi
0x1800024c1  call    SclpCanonicalizePaths
0x1800024c6  mov     ebx, eax
0x1800024c8  test    eax, eax
0x1800024ca  jns     short loc_180002502
0x1800024cc  mov     [rsp+50h+var_20], eax
0x1800024d0  lea     r8, SclEvent_Generic_Error
0x1800024d7  lea     rax, aSclpcanonicali; "SclpCanonicalizePaths failed. Error: 0x"...
0x1800024de  mov     r9d, 4F6h
0x1800024e4  mov     [rsp+50h+var_28], rax
  ... truncated ...
```
