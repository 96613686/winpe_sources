# VsmmpMapUserBufferToSystem

- ea: `0x1400d51fc`
- end: `0x1400d5358`
- name: `VsmmpMapUserBufferToSystem`
- size: `348`
- prototype: `__int64 __fastcall(void *, ULONG, struct _MDL **, LOCK_OPERATION, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bc64`
- `0x14000d75c`

## callees

- `0x14002f524`
- `0x1400d51fc`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d52af`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d52af`
- `ntoskrnl!IoFreeMdl` at `0x1400d533f`
- `ntoskrnl!IoFreeMdl` at `0x1400d533f`
- `ntoskrnl!IoAllocateMdl` at `0x1400d5223`
- `ntoskrnl!IoAllocateMdl` at `0x1400d5223`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400d526b`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400d526b`
- `ntoskrnl!MmUnlockPages` at `0x1400d5330`
- `ntoskrnl!MmUnlockPages` at `0x1400d5330`

## pseudocode

```c
__int64 __fastcall VsmmpMapUserBufferToSystem(void *a1, ULONG a2, struct _MDL **a3, LOCK_OPERATION a4, _QWORD *a5)
{
  char v7; // si
  struct _MDL *Mdl; // rax
  struct _MDL *v9; // rbx
  unsigned int v10; // edi
  ULONG Priority; // ecx
  PVOID MappedSystemVa; // rcx

  v7 = 0;
  Mdl = IoAllocateMdl(a1, a2, 0, 0, 0);
  v9 = Mdl;
  if ( Mdl )
  {
    MmProbeAndLockPages(Mdl, 0, a4);
    v7 = 1;
    Priority = 1073741840;
    if ( a4 != IoWriteAccess )
      Priority = -1073741808;
    if ( (v9->MdlFlags & 5) != 0 )
      MappedSystemVa = v9->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, Priority);
    if ( MappedSystemVa )
    {
      *a5 = MappedSystemVa;
      *a3 = v9;
      v9 = 0;
      v10 = 0;
    }
    else
    {
      v10 = -1073741670;
      VidTraceErrorStatusInternal0("VsmmpMapUserBufferToSystem", "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c", 377);
    }
  }
  else
  {
    v10 = -1073741670;
    VidTraceErrorStatusInternal0("VsmmpMapUserBufferToSystem", "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c", 345);
  }
  if ( v9 )
  {
    if ( v7 )
      MmUnlockPages(v9);
    IoFreeMdl(v9);
  }
  return v10;
}

```

## disassembly

```asm
0x1400d51fc  push    rbx
0x1400d51fe  push    rsi
0x1400d51ff  push    rdi
0x1400d5200  push    r14
0x1400d5202  sub     rsp, 48h
0x1400d5206  mov     edi, r9d
0x1400d5209  mov     r14, r8
0x1400d520c  xor     sil, sil
0x1400d520f  mov     [rsp+68h+var_38], sil
0x1400d5214  mov     [rsp+68h+Irp], 0; Irp
0x1400d521d  xor     r9d, r9d; ChargeQuota
0x1400d5220  xor     r8d, r8d; SecondaryBuffer
0x1400d5223  call    cs:__imp_IoAllocateMdl
0x1400d522a  nop     dword ptr [rax+rax+00h]
0x1400d522f  mov     rbx, rax
0x1400d5232  mov     [rsp+68h+var_30], rax
0x1400d5237  test    rax, rax
0x1400d523a  jnz     short loc_1400D5263
0x1400d523c  mov     r9d, 0C000009Ah
0x1400d5242  mov     edi, r9d
0x1400d5245  mov     r8d, 159h
0x1400d524b  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d5252  lea     rcx, aVsmmpmapuserbu; "VsmmpMapUserBufferToSystem"
0x1400d5259  call    VidTraceErrorStatusInternal0
0x1400d525e  jmp     loc_1400D5323
0x1400d5263  mov     r8d, edi; Operation
0x1400d5266  xor     edx, edx; AccessMode
0x1400d5268  mov     rcx, rbx; MemoryDescriptorList
0x1400d526b  call    cs:__imp_MmProbeAndLockPages
0x1400d5272  nop     dword ptr [rax+rax+00h]
0x1400d5277  nop
0x1400d5278  mov     esi, 1
0x1400d527d  mov     ecx, 40000010h
0x1400d5282  mov     eax, 0C0000010h
0x1400d5287  cmp     edi, esi
0x1400d5289  cmovnz  ecx, eax
0x1400d528c  test    byte ptr [rbx+0Ah], 5
0x1400d5290  jz      short loc_1400D5298
0x1400d5292  mov     rcx, [rbx+18h]
0x1400d5296  jmp     short loc_1400D52BE
0x1400d5298  mov     [rsp+68h+Priority], ecx; Priority
0x1400d529c  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x1400d52a4  xor     r9d, r9d; RequestedAddress
0x1400d52a7  mov     r8d, esi; CacheType
0x1400d52aa  xor     edx, edx; AccessMode
0x1400d52ac  mov     rcx, rbx; MemoryDescriptorList
0x1400d52af  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d52b6  nop     dword ptr [rax+rax+00h]
0x1400d52bb  mov     rcx, rax
0x1400d52be  test    rcx, rcx
0x1400d52c1  jnz     short loc_1400D52E7
0x1400d52c3  mov     r9d, 0C000009Ah
0x1400d52c9  mov     edi, r9d
0x1400d52cc  mov     r8d, 179h
0x1400d52d2  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d52d9  lea     rcx, aVsmmpmapuserbu; "VsmmpMapUserBufferToSystem"
0x1400d52e0  call    VidTraceErrorStatusInternal0
0x1400d52e5  jmp     short loc_1400D5323
0x1400d52e7  mov     rax, [rsp+68h+arg_20]
0x1400d52ef  mov     [rax], rcx
0x1400d52f2  mov     [r14], rbx
0x1400d52f5  xor     ebx, ebx
0x1400d52f7  xor     edi, edi
0x1400d52f9  jmp     short loc_1400D5323
0x1400d52fb  mov     edi, eax
0x1400d52fd  mov     r9d, eax
0x1400d5300  mov     r8d, 164h
0x1400d5306  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d530d  lea     rcx, aVsmmpmapuserbu; "VsmmpMapUserBufferToSystem"
0x1400d5314  call    VidTraceErrorStatusInternal0
0x1400d5319  mov     rbx, [rsp+68h+var_30]
0x1400d531e  mov     sil, [rsp+68h+var_38]
0x1400d5323  test    rbx, rbx
0x1400d5326  jz      short loc_1400D534B
0x1400d5328  test    sil, sil
0x1400d532b  jz      short loc_1400D533C
0x1400d532d  mov     rcx, rbx; MemoryDescriptorList
0x1400d5330  call    cs:__imp_MmUnlockPages
0x1400d5337  nop     dword ptr [rax+rax+00h]
0x1400d533c  mov     rcx, rbx; Mdl
0x1400d533f  call    cs:__imp_IoFreeMdl
0x1400d5346  nop     dword ptr [rax+rax+00h]
0x1400d534b  mov     eax, edi
0x1400d534d  add     rsp, 48h
0x1400d5351  pop     r14
0x1400d5353  pop     rdi
0x1400d5354  pop     rsi
0x1400d5355  pop     rbx
0x1400d5356  retn
```
