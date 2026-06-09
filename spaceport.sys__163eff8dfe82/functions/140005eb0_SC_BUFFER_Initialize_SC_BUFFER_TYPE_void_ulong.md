# SC_BUFFER::Initialize(_SC_BUFFER_TYPE,void *,ulong)

- ea: `0x140005eb0`
- end: `0x140006090`
- name: `?Initialize@SC_BUFFER@@QEAAJW4_SC_BUFFER_TYPE@@PEAXK@Z`
- size: `480`
- prototype: `int __high(enum _SC_BUFFER_TYPE, void *, unsigned int)`
- caller_count: `49`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140004250`
- `0x140005a50`
- `0x1400063f0`
- `0x140006980`
- `0x140007be0`
- `0x140014bc0`
- `0x14001e8d0`
- `0x1400229d0`
- `0x140027d70`
- `0x14002f938`
- `0x14003e268`
- `0x14003fbf8`
- `0x140040be4`
- `0x140041b4c`
- `0x1400445e8`
- `0x140044c54`
- `0x140045234`
- `0x140045664`
- `0x140047d4c`
- `0x140049740`
- `0x14004a2f0`
- `0x14004a644`
- `0x14004a990`
- `0x14004d658`
- `0x14004d9a8`
- `0x14004dbe8`
- `0x14004dfe4`
- `0x14004e140`
- `0x14004e6bc`
- `0x14004e9b0`
- `0x14004f580`
- `0x140050fb4`
- `0x14005116c`
- `0x140051a0c`
- `0x140051c00`
- `0x140051f68`
- `0x140052518`
- `0x140052850`
- `0x140052bd0`
- `0x140052ff0`
- `0x14005417c`
- `0x140059c9c`
- `0x14005b76c`
- `0x14005be64`
- `0x1400a4504`
- `0x1400b0c40`
- `0x1400b1b48`
- `0x1400b2348`
- `0x1400b25c0`

## callees

- `0x140005eb0`
- `0x140068600`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140005f1c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140005f1c`
- `ntoskrnl!IoAllocateMdl` at `0x140005efd`
- `ntoskrnl!IoAllocateMdl` at `0x140005efd`
- `ntoskrnl!ExAllocatePool2` at `0x14000602a`
- `ntoskrnl!ExAllocatePool2` at `0x14000602a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068afd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068afd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000607f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000607f`
- `ntoskrnl!MmMdlPageContentsState` at `0x140005f31`
- `ntoskrnl!MmMdlPageContentsState` at `0x140005f31`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005fea`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140005fea`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005fba`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140005fba`

## pseudocode

```c
__int64 __fastcall SC_BUFFER::Initialize(__int64 a1, int a2, __int64 a3, unsigned int a4)
{
  size_t v5; // r14
  __int64 v6; // r10
  unsigned int v8; // ebp
  void *v9; // rdi
  struct _MDL *Mdl; // rax
  __int64 result; // rax
  int v12; // r15d
  unsigned int v13; // edi
  PVOID v14; // rax
  __int64 Pool2; // rax

  v5 = a4;
  v6 = a3;
  v8 = 0xFFFF;
  if ( a2 == 2 )
  {
    v9 = 0;
    if ( !a3 )
      v6 = 4095;
  }
  else
  {
    if ( a2 != 3 )
      return 3221225485LL;
    if ( a4 - 4096 > 0x3F000 )
    {
      Pool2 = ExAllocatePool2(72, a4, 1715630163);
      v9 = (void *)Pool2;
      if ( !Pool2 )
        return 3221225626LL;
      v6 = Pool2;
    }
    else
    {
      _BitScanReverse((unsigned int *)&v12, a4);
      if ( 1 << v12 != a4 )
        ++v12;
      v13 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
      v8 = v13 * (v12 - 12) + (unsigned __int8)(KeGetCurrentProcessorNumberEx(0) % v13);
      v14 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45)
                                                                     + ((unsigned __int64)v8 << 7)));
      v9 = v14;
      if ( !v14 )
        return 3221225626LL;
      memset(v14, 0, v5);
      v6 = (__int64)v9;
    }
  }
  Mdl = IoAllocateMdl((PVOID)v6, v5, 0, 0, 0);
  *(_QWORD *)(a1 + 8) = Mdl;
  if ( !Mdl )
  {
    if ( v9 )
    {
      if ( v8 == 0xFFFF )
        ExFreePoolWithTag(v9, 0);
      else
        ExFreeToNPagedLookasideList(
          (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45) + ((unsigned __int64)v8 << 7)),
          v9);
    }
    return 3221225626LL;
  }
  if ( a2 == 3 )
  {
    MmBuildMdlForNonPagedPool(Mdl);
    MmMdlPageContentsState(*(_QWORD *)(a1 + 8), 1);
  }
  *(_DWORD *)a1 = a2;
  result = 0;
  *(_WORD *)(a1 + 4) = v8;
  return result;
}

```

## disassembly

```asm
0x140005eb0  mov     [rsp+arg_8], rbx
0x140005eb5  mov     [rsp+arg_10], rbp
0x140005eba  push    rsi
0x140005ebb  push    rdi
0x140005ebc  push    r14
0x140005ebe  sub     rsp, 30h
0x140005ec2  mov     rbx, rcx
0x140005ec5  mov     r14d, r9d
0x140005ec8  mov     ecx, edx
0x140005eca  mov     r10, r8
0x140005ecd  mov     esi, edx
0x140005ecf  mov     ebp, 0FFFFh
0x140005ed4  sub     ecx, 2
0x140005ed7  jnz     loc_140005F74
0x140005edd  xor     edi, edi
0x140005edf  test    r8, r8
0x140005ee2  jz      loc_140005F69
0x140005ee8  xor     r9d, r9d; ChargeQuota
0x140005eeb  mov     [rsp+48h+Irp], 0; Irp
0x140005ef4  xor     r8d, r8d; SecondaryBuffer
0x140005ef7  mov     edx, r14d; Length
0x140005efa  mov     rcx, r10; VirtualAddress
0x140005efd  call    cs:__imp_IoAllocateMdl
0x140005f04  nop     dword ptr [rax+rax+00h]
0x140005f09  mov     [rbx+8], rax
0x140005f0d  test    rax, rax
0x140005f10  jz      short loc_140005F59
0x140005f12  xor     edi, edi
0x140005f14  cmp     esi, 3
0x140005f17  jnz     short loc_140005F3D
0x140005f19  mov     rcx, rax; MemoryDescriptorList
0x140005f1c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140005f23  nop     dword ptr [rax+rax+00h]
0x140005f28  mov     rcx, [rbx+8]
0x140005f2c  mov     edx, 1
0x140005f31  call    cs:__imp_MmMdlPageContentsState
0x140005f38  nop     dword ptr [rax+rax+00h]
0x140005f3d  mov     [rbx], esi
0x140005f3f  mov     eax, edi
0x140005f41  mov     [rbx+4], bp
0x140005f45  mov     rbx, [rsp+48h+arg_8]
0x140005f4a  mov     rbp, [rsp+48h+arg_10]
0x140005f4f  add     rsp, 30h
0x140005f53  pop     r14
0x140005f55  pop     rdi
0x140005f56  pop     rsi
0x140005f57  retn
0x140005f59  test    rdi, rdi
0x140005f5c  jnz     loc_14000605C
0x140005f62  mov     eax, 0C000009Ah
0x140005f67  jmp     short loc_140005F45
0x140005f69  mov     r10d, 0FFFh
0x140005f6f  jmp     loc_140005EE8
0x140005f74  cmp     ecx, 1
0x140005f77  jnz     loc_14000604A
0x140005f7d  lea     eax, [r14-1000h]
0x140005f84  cmp     eax, 3F000h
0x140005f89  ja      loc_14000601C
0x140005f8f  mov     [rsp+48h+arg_0], r15
0x140005f94  mov     eax, 1
0x140005f99  bsr     r15d, r14d
0x140005f9d  mov     ecx, r15d
0x140005fa0  shl     eax, cl
0x140005fa2  cmp     eax, r14d
0x140005fa5  jnz     loc_140006054
0x140005fab  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140005fb2  xor     ecx, ecx; ProcNumber
0x140005fb4  mov     edi, [rax+150h]
0x140005fba  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140005fc1  nop     dword ptr [rax+rax+00h]
0x140005fc6  xor     edx, edx
0x140005fc8  div     edi
0x140005fca  lea     eax, [r15-0Ch]
0x140005fce  imul    eax, edi
0x140005fd1  movzx   ebp, dl
0x140005fd4  add     ebp, eax
0x140005fd6  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140005fdd  mov     ecx, ebp
0x140005fdf  shl     rcx, 7
0x140005fe3  add     rcx, [rax+168h]; Lookaside
0x140005fea  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140005ff1  nop     dword ptr [rax+rax+00h]
0x140005ff6  mov     r15, [rsp+48h+arg_0]
0x140005ffb  mov     rdi, rax
0x140005ffe  test    rax, rax
0x140006001  jz      loc_140005F62
0x140006007  mov     r8, r14; Size
0x14000600a  xor     edx, edx; Val
0x14000600c  mov     rcx, rax; void *
0x14000600f  call    memset
0x140006014  mov     r10, rdi
0x140006017  jmp     loc_140005EE8
0x14000601c  mov     rdx, r14
0x14000601f  mov     ecx, 48h ; 'H'
0x140006024  mov     r8d, 66427053h
0x14000602a  call    cs:__imp_ExAllocatePool2
0x140006031  nop     dword ptr [rax+rax+00h]
0x140006036  mov     rdi, rax
0x140006039  test    rax, rax
0x14000603c  jz      loc_140005F62
0x140006042  mov     r10, rax
0x140006045  jmp     loc_140005EE8
0x14000604a  mov     eax, 0C000000Dh
0x14000604f  jmp     loc_140005F45
0x140006054  inc     r15d
0x140006057  jmp     loc_140005FAB
0x14000605c  cmp     ebp, 0FFFFh
0x140006062  jz      loc_140068AF8
0x140006068  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000606f  mov     rdx, rdi; Entry
0x140006072  mov     ecx, ebp
0x140006074  shl     rcx, 7
0x140006078  add     rcx, [rax+168h]; Lookaside
0x14000607f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006086  nop     dword ptr [rax+rax+00h]
0x14000608b  jmp     loc_140005F62
0x140068af8  xor     edx, edx; Tag
0x140068afa  mov     rcx, rdi; P
0x140068afd  call    cs:__imp_ExFreePoolWithTag
0x140068b04  nop     dword ptr [rax+rax+00h]
0x140068b09  nop
0x140068b0a  jmp     loc_140005F62
```
