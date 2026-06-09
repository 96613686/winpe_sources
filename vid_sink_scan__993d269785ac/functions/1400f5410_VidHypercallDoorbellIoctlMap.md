# VidHypercallDoorbellIoctlMap

- ea: `0x1400f5410`
- end: `0x1400f5738`
- name: `VidHypercallDoorbellIoctlMap`
- size: `808`
- prototype: `__int64 __fastcall(__int64, void *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140035698`

## callees

- `0x1400217a0`
- `0x140024754`
- `0x140030790`
- `0x1400307d0`
- `0x140038630`
- `0x14008a2b8`
- `0x1400f5410`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400f54d7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400f54d7`
- `ntoskrnl!PsProcessType` at `0x1400f54c1`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400f5578`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400f5578`
- `ntoskrnl!ZwClose` at `0x1400f56e1`
- `ntoskrnl!ZwClose` at `0x1400f56e1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f549b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f549b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f56fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f56fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400f5483`
- `ntoskrnl!ExAllocatePool2` at `0x1400f5483`
- `winhvr!WinHvGetPartitionProperty` at `0x1400f5643`
- `winhvr!WinHvGetPartitionProperty` at `0x1400f5643`

## pseudocode

```c
__int64 __fastcall VidHypercallDoorbellIoctlMap(__int64 a1, void *a2, __int64 **a3)
{
  __int64 v3; // r13
  __int64 **Pool2; // rdi
  __int64 *v7; // rsi
  __int64 *i; // rax
  void *CurrentProcess; // r12
  NTSTATUS PartitionProperty; // ebx
  __int64 **v12; // rcx
  __int64 **v13; // rax
  __int64 v14; // rdx
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  __int64 *v16; // [rsp+90h] [rbp+40h] BYREF
  __int64 **v17; // [rsp+A0h] [rbp+50h]
  HANDLE Handle; // [rsp+A8h] [rbp+58h] BYREF

  v17 = a3;
  v3 = a1 + 10864;
  v15 = 0;
  v16 = 0;
  Handle = 0;
  Pool2 = 0;
  VidLockAcquireExclusive(a1 + 10864);
  if ( (*(_DWORD *)(a1 + 32) & 0x800LL) != 0 )
  {
    v7 = (__int64 *)(a1 + 10872);
    for ( i = *(__int64 **)(a1 + 10872); i != v7; i = (__int64 *)*i )
    {
      if ( (void *)i[2] == a2 )
      {
        if ( i )
        {
          VidTraceErrorInternal0(
            "VidHypercallDoorbellIoctlMap",
            "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
            293);
          PartitionProperty = -1073741436;
          goto LABEL_7;
        }
        break;
      }
    }
    Pool2 = (__int64 **)ExAllocatePool2(256, 48, 1917084758);
    if ( Pool2 )
    {
      CurrentProcess = (void *)PsGetCurrentProcess();
      PartitionProperty = ObOpenObjectByPointer(
                            CurrentProcess,
                            0x200u,
                            0,
                            0x1FFFFFu,
                            (POBJECT_TYPE)PsProcessType,
                            0,
                            &Handle);
      if ( PartitionProperty >= 0 )
      {
        PartitionProperty = WinHvGetPartitionProperty(*(_QWORD *)(a1 + 648), 327698, &v15);
        if ( PartitionProperty >= 0 )
        {
          if ( (*(_DWORD *)(a1 + 16) & 0x8000LL) != 0 && (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
            (*((void (__fastcall **)(void *))VidDeviceExtension + 255))(CurrentProcess);
          PartitionProperty = VidHypercallDoorbellpMapPhysicalPagesToUserModeForExecute(v15, v14, &v16);
          if ( PartitionProperty >= 0 )
          {
            ObfReferenceObjectWithTag(a2, 0x72446456u);
            v12 = v17;
            Pool2[2] = (__int64 *)a2;
            Pool2[4] = (__int64 *)Handle;
            Handle = 0;
            Pool2[5] = (__int64 *)CurrentProcess;
            Pool2[3] = v16;
            *v12 = v16;
            v13 = *(__int64 ***)(a1 + 10880);
            v16 = 0;
            if ( *v13 != v7 )
              __fastfail(3u);
            *Pool2 = v7;
            Pool2[1] = (__int64 *)v13;
            *v13 = (__int64 *)Pool2;
            *(_QWORD *)(a1 + 10880) = Pool2;
            Pool2 = 0;
            PartitionProperty = 0;
          }
          else
          {
            VidTraceErrorInternal0(
              "VidHypercallDoorbellIoctlMap",
              "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
              363);
          }
        }
        else
        {
          VidTraceErrorInternal0(
            "VidHypercallDoorbellIoctlMap",
            "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
            334);
        }
      }
      else
      {
        VidTraceErrorInternal0(
          "VidHypercallDoorbellIoctlMap",
          "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
          321);
      }
    }
    else
    {
      VidTraceErrorInternal0(
        "VidHypercallDoorbellIoctlMap",
        "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
        301);
      PartitionProperty = -1073741670;
    }
  }
  else
  {
    VidTraceErrorInternal0("VidHypercallDoorbellIoctlMap", "onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c", 283);
    PartitionProperty = -1073741811;
  }
LABEL_7:
  if ( Handle )
    ZwClose(Handle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72446456u);
  VidLockRelease(v3);
  if ( PartitionProperty < 0 )
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidHypercallDoorbellIoctlMap",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhypercalldoorbell.c",
      394,
      PartitionProperty,
      a1 + 656);
  return (unsigned int)PartitionProperty;
}

```

## disassembly

```asm
0x1400f5410  mov     [rsp-38h+arg_8], rbx
0x1400f5415  mov     [rsp-38h+arg_10], r8
0x1400f541a  push    rbp
0x1400f541b  push    rsi
0x1400f541c  push    rdi
0x1400f541d  push    r12
0x1400f541f  push    r13
0x1400f5421  push    r14
0x1400f5423  push    r15
0x1400f5425  mov     rbp, rsp
0x1400f5428  sub     rsp, 50h
0x1400f542c  xor     ebx, ebx
0x1400f542e  lea     r13, [rcx+2A70h]
0x1400f5435  mov     r14, rcx
0x1400f5438  mov     [rbp+var_10], rbx
0x1400f543c  mov     rcx, r13
0x1400f543f  mov     [rbp+arg_0], rbx
0x1400f5443  mov     r15, rdx
0x1400f5446  mov     [rbp+arg_18], rbx
0x1400f544a  mov     edi, ebx
0x1400f544c  call    VidLockAcquireExclusive
0x1400f5451  mov     eax, [r14+20h]
0x1400f5455  bt      rax, 0Bh
0x1400f545a  jnb     loc_1400F55DB
0x1400f5460  lea     rsi, [r14+2A78h]
0x1400f5467  mov     rax, [rsi]
0x1400f546a  cmp     rax, rsi
0x1400f546d  jnz     loc_1400F55FE
0x1400f5473  mov     edx, 30h ; '0'
0x1400f5478  mov     ecx, 100h
0x1400f547d  mov     r8d, 72446456h
0x1400f5483  call    cs:__imp_ExAllocatePool2
0x1400f548a  nop     dword ptr [rax+rax+00h]
0x1400f548f  mov     rdi, rax
0x1400f5492  test    rax, rax
0x1400f5495  jz      loc_1400F5610
0x1400f549b  call    cs:__imp_PsGetCurrentProcess
0x1400f54a2  nop     dword ptr [rax+rax+00h]
0x1400f54a7  mov     r9d, 1FFFFFh; DesiredAccess
0x1400f54ad  xor     r8d, r8d; PassedAccessState
0x1400f54b0  mov     r12, rax
0x1400f54b3  mov     edx, 200h; HandleAttributes
0x1400f54b8  lea     rax, [rbp+arg_18]
0x1400f54bc  mov     [rsp+50h+Handle], rax; Handle
0x1400f54c1  mov     rax, cs:__imp_PsProcessType
0x1400f54c8  mov     [rsp+50h+AccessMode], bl; AccessMode
0x1400f54cc  mov     rcx, [rax]
0x1400f54cf  mov     [rsp+50h+ObjectType], rcx; ObjectType
0x1400f54d4  mov     rcx, r12; Object
0x1400f54d7  call    cs:__imp_ObOpenObjectByPointer
0x1400f54de  nop     dword ptr [rax+rax+00h]
0x1400f54e3  mov     ebx, eax
0x1400f54e5  test    eax, eax
0x1400f54e7  jns     loc_1400F5633
0x1400f54ed  mov     r8d, 141h
0x1400f54f3  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f54fa  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f5501  call    VidTraceErrorInternal0
0x1400f5506  mov     rcx, [rbp+arg_18]; Handle
0x1400f550a  test    rcx, rcx
0x1400f550d  jnz     loc_1400F56E1
0x1400f5513  test    rdi, rdi
0x1400f5516  jnz     loc_1400F56F2
0x1400f551c  mov     rcx, r13
0x1400f551f  call    VidLockRelease
0x1400f5524  test    ebx, ebx
0x1400f5526  js      loc_1400F570B
0x1400f552c  mov     eax, ebx
0x1400f552e  mov     rbx, [rsp+50h+arg_8]
0x1400f5536  add     rsp, 50h
0x1400f553a  pop     r15
0x1400f553c  pop     r14
0x1400f553e  pop     r13
0x1400f5540  pop     r12
0x1400f5542  pop     rdi
0x1400f5543  pop     rsi
0x1400f5544  pop     rbp
0x1400f5545  retn
0x1400f5547  test    rax, rax
0x1400f554a  jz      loc_1400F5473
0x1400f5550  mov     r8d, 125h
0x1400f5556  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f555d  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f5564  call    VidTraceErrorInternal0
0x1400f5569  mov     ebx, 0C0000184h
0x1400f556e  jmp     short loc_1400F5506
0x1400f5570  mov     edx, 72446456h; Tag
0x1400f5575  mov     rcx, r15; Object
0x1400f5578  call    cs:__imp_ObfReferenceObjectWithTag
0x1400f557f  nop     dword ptr [rax+rax+00h]
0x1400f5584  mov     rcx, [rbp+arg_10]
0x1400f5588  mov     [rdi+10h], r15
0x1400f558c  mov     rax, [rbp+arg_18]
0x1400f5590  mov     [rdi+20h], rax
0x1400f5594  mov     [rbp+arg_18], 0
0x1400f559c  mov     [rdi+28h], r12
0x1400f55a0  mov     rax, [rbp+arg_0]
0x1400f55a4  mov     [rdi+18h], rax
0x1400f55a8  mov     rax, [rbp+arg_0]
0x1400f55ac  mov     [rcx], rax
0x1400f55af  mov     rax, [rsi+8]
0x1400f55b3  mov     [rbp+arg_0], 0
0x1400f55bb  cmp     [rax], rsi
0x1400f55be  jnz     loc_1400F56DA
0x1400f55c4  mov     [rdi], rsi
0x1400f55c7  mov     [rdi+8], rax
0x1400f55cb  mov     [rax], rdi
0x1400f55ce  mov     [rsi+8], rdi
0x1400f55d2  xor     edi, edi
0x1400f55d4  xor     ebx, ebx
0x1400f55d6  jmp     loc_1400F5506
0x1400f55db  mov     r8d, 11Bh
0x1400f55e1  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f55e8  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f55ef  call    VidTraceErrorInternal0
0x1400f55f4  mov     ebx, 0C000000Dh
0x1400f55f9  jmp     loc_1400F5506
0x1400f55fe  cmp     [rax+10h], r15
0x1400f5602  jz      loc_1400F5547
0x1400f5608  mov     rax, [rax]
0x1400f560b  jmp     loc_1400F546A
0x1400f5610  mov     r8d, 12Dh
0x1400f5616  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f561d  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f5624  call    VidTraceErrorInternal0
0x1400f5629  mov     ebx, 0C000009Ah
0x1400f562e  jmp     loc_1400F5506
0x1400f5633  mov     rcx, [r14+288h]
0x1400f563a  lea     r8, [rbp+var_10]
0x1400f563e  mov     edx, 50012h
0x1400f5643  call    cs:__imp_WinHvGetPartitionProperty
0x1400f564a  nop     dword ptr [rax+rax+00h]
0x1400f564f  mov     ebx, eax
0x1400f5651  test    eax, eax
0x1400f5653  jns     short loc_1400F5673
0x1400f5655  mov     r8d, 14Eh
0x1400f565b  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f5662  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f5669  call    VidTraceErrorInternal0
0x1400f566e  jmp     loc_1400F5506
0x1400f5673  mov     eax, [r14+10h]
0x1400f5677  bt      rax, 0Fh
0x1400f567c  jnb     short loc_1400F56A5
0x1400f567e  mov     rax, cs:VidDeviceExtension
0x1400f5685  mov     eax, [rax+288h]
0x1400f568b  test    al, 20h
0x1400f568d  jz      short loc_1400F56A5
0x1400f568f  mov     rax, cs:VidDeviceExtension
0x1400f5696  mov     rcx, r12
0x1400f5699  mov     rax, [rax+7F8h]
0x1400f56a0  call    _guard_dispatch_icall
0x1400f56a5  mov     rcx, [rbp+var_10]
0x1400f56a9  lea     r8, [rbp+arg_0]
0x1400f56ad  call    VidHypercallDoorbellpMapPhysicalPagesToUserModeForExecute
0x1400f56b2  mov     ebx, eax
0x1400f56b4  test    eax, eax
0x1400f56b6  jns     loc_1400F5570
0x1400f56bc  mov     r8d, 16Bh
0x1400f56c2  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f56c9  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f56d0  call    VidTraceErrorInternal0
0x1400f56d5  jmp     loc_1400F5506
0x1400f56da  mov     ecx, 3
0x1400f56df  int     29h; Win8: RtlFailFast(ecx)
0x1400f56e1  call    cs:__imp_ZwClose
0x1400f56e8  nop     dword ptr [rax+rax+00h]
0x1400f56ed  jmp     loc_1400F5513
0x1400f56f2  mov     edx, 72446456h; Tag
0x1400f56f7  mov     rcx, rdi; P
0x1400f56fa  call    cs:__imp_ExFreePoolWithTag
0x1400f5701  nop     dword ptr [rax+rax+00h]
0x1400f5706  jmp     loc_1400F551C
0x1400f570b  lea     rax, [r14+290h]
0x1400f5712  mov     r9d, ebx
0x1400f5715  mov     r8d, 18Ah
0x1400f571b  mov     [rsp+50h+ObjectType], rax
0x1400f5720  lea     rdx, aOnecoreVmVidSy_19; "onecore\\vm\\vid\\sys\\driver\\vidhyper"...
0x1400f5727  lea     rcx, aVidhypercalldo; "VidHypercallDoorbellIoctlMap"
0x1400f572e  call    VidTraceErrorStatusPartitionInternal0
0x1400f5733  jmp     loc_1400F552C
```
