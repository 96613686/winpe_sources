# VidPartitionIoctlSave

- ea: `0x14008e254`
- end: `0x14008e45e`
- name: `VidPartitionIoctlSave`
- size: `522`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x14002f724`
- `0x140079dfc`
- `0x14008e254`
- `0x1400fdc0c`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14008e34d`
- `ntoskrnl!ProbeForWrite` at `0x14008e34d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e443`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e443`
- `ntoskrnl!ExAllocatePool2` at `0x14008e367`
- `ntoskrnl!ExAllocatePool2` at `0x14008e367`

## pseudocode

```c
__int64 __fastcall VidPartitionIoctlSave(__int64 a1, int a2, volatile void *a3, _DWORD *a4)
{
  int v6; // r15d
  void *Pool2; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rax
  int PartitionState; // eax

  v6 = a1;
  Pool2 = 0;
  if ( (a2 & 0xFFFFFFE5) != 0 )
  {
    v8 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSave",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1527,
      3221225485LL);
  }
  else if ( a3 )
  {
    if ( *a4 >= 0x18u )
    {
      v9 = *(_QWORD *)(a1 + 32) & 0x1E0LL;
      if ( (v9 != 64 || (a2 & 8) != 0) && (v9 != 96 || (a2 & 0x18) != 0) )
      {
        ProbeForWrite(a3, (unsigned int)*a4, 1u);
        Pool2 = (void *)ExAllocatePool2(65, (unsigned int)*a4, 1917084758);
        if ( Pool2 )
        {
          PartitionState = VidSaveRestoreGetPartitionState(v6);
          v8 = PartitionState;
          if ( PartitionState >= 0 )
          {
            RtlCopyToUser((void *)a3, Pool2, (unsigned int)*a4);
            v8 = 0;
          }
          else
          {
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlSave",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              1599,
              (unsigned int)PartitionState);
          }
        }
        else
        {
          v8 = -1073741670;
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlSave",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            1588,
            3221225626LL);
        }
      }
      else
      {
        v8 = -1073741790;
        VidTraceErrorStatusInternal0(
          "VidPartitionIoctlSave",
          "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
          1551,
          3221225506LL);
      }
    }
    else
    {
      v8 = -1073741811;
      VidTraceErrorStatusInternal0(
        "VidPartitionIoctlSave",
        "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1541,
        3221225485LL);
    }
  }
  else
  {
    v8 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VidPartitionIoctlSave",
      "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
      1534,
      3221225485LL);
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72446456u);
  return v8;
}

```

## disassembly

```asm
0x14008e254  push    rbx
0x14008e256  push    rsi
0x14008e257  push    rdi
0x14008e258  push    r14
0x14008e25a  push    r15
0x14008e25c  sub     rsp, 30h
0x14008e260  mov     rsi, r9
0x14008e263  mov     r14, r8
0x14008e266  mov     ebx, edx
0x14008e268  mov     r15, rcx
0x14008e26b  xor     edi, edi
0x14008e26d  mov     [rsp+58h+var_38], rdi
0x14008e272  test    edx, 0FFFFFFE5h
0x14008e278  jz      short loc_14008E2A1
0x14008e27a  mov     r9d, 0C000000Dh
0x14008e280  mov     ebx, r9d
0x14008e283  mov     r8d, 5F7h
0x14008e289  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e290  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e297  call    VidTraceErrorStatusInternal0
0x14008e29c  jmp     loc_14008E436
0x14008e2a1  test    r14, r14
0x14008e2a4  jnz     short loc_14008E2CD
0x14008e2a6  mov     r9d, 0C000000Dh
0x14008e2ac  mov     ebx, r9d
0x14008e2af  mov     r8d, 5FEh
0x14008e2b5  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e2bc  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e2c3  call    VidTraceErrorStatusInternal0
0x14008e2c8  jmp     loc_14008E436
0x14008e2cd  mov     ecx, [r9]
0x14008e2d0  cmp     ecx, 18h
0x14008e2d3  jnb     short loc_14008E2FC
0x14008e2d5  mov     r9d, 0C000000Dh
0x14008e2db  mov     ebx, r9d
0x14008e2de  mov     r8d, 605h
0x14008e2e4  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e2eb  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e2f2  call    VidTraceErrorStatusInternal0
0x14008e2f7  jmp     loc_14008E436
0x14008e2fc  mov     rax, [r15+20h]
0x14008e300  and     eax, 1E0h
0x14008e305  cmp     rax, 40h ; '@'
0x14008e309  jnz     short loc_14008E310
0x14008e30b  test    bl, 8
0x14008e30e  jz      short loc_14008E31B
0x14008e310  cmp     rax, 60h ; '`'
0x14008e314  jnz     short loc_14008E341
0x14008e316  test    bl, 18h
0x14008e319  jnz     short loc_14008E341
0x14008e31b  mov     ebx, 0C0000022h
0x14008e320  mov     r9d, ebx
0x14008e323  mov     r8d, 60Fh
0x14008e329  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e330  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e337  call    VidTraceErrorStatusInternal0
0x14008e33c  jmp     loc_14008E436
0x14008e341  mov     rdx, rcx; Length
0x14008e344  mov     r8d, 1; Alignment
0x14008e34a  mov     rcx, r14; Address
0x14008e34d  call    cs:__imp_ProbeForWrite
0x14008e354  nop     dword ptr [rax+rax+00h]
0x14008e359  nop
0x14008e35a  mov     edx, [rsi]
0x14008e35c  mov     ecx, 41h ; 'A'
0x14008e361  mov     r8d, 72446456h
0x14008e367  call    cs:__imp_ExAllocatePool2
0x14008e36e  nop     dword ptr [rax+rax+00h]
0x14008e373  mov     rdi, rax
0x14008e376  mov     [rsp+58h+var_38], rax
0x14008e37b  test    rax, rax
0x14008e37e  jnz     short loc_14008E3A6
0x14008e380  mov     ebx, 0C000009Ah
0x14008e385  mov     r9d, ebx
0x14008e388  mov     r8d, 634h
0x14008e38e  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e395  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e39c  call    VidTraceErrorStatusInternal0
0x14008e3a1  jmp     loc_14008E436
0x14008e3a6  mov     r9d, ebx
0x14008e3a9  mov     r8, rsi
0x14008e3ac  mov     rdx, rdi
0x14008e3af  mov     rcx, r15; int
0x14008e3b2  call    VidSaveRestoreGetPartitionState
0x14008e3b7  mov     ebx, eax
0x14008e3b9  test    eax, eax
0x14008e3bb  jns     short loc_14008E3DB
0x14008e3bd  mov     r9d, eax
0x14008e3c0  mov     r8d, 63Fh
0x14008e3c6  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e3cd  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e3d4  call    VidTraceErrorStatusInternal0
0x14008e3d9  jmp     short loc_14008E436
0x14008e3db  mov     r8d, [rsi]; Size
0x14008e3de  mov     rdx, rdi; Src
0x14008e3e1  mov     rcx, r14; void *
0x14008e3e4  call    RtlCopyToUser
0x14008e3e9  nop
0x14008e3ea  xor     ebx, ebx
0x14008e3ec  jmp     short loc_14008E436
0x14008e3ee  mov     ebx, eax
0x14008e3f0  mov     r9d, eax
0x14008e3f3  mov     r8d, 64Dh
0x14008e3f9  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e400  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e407  call    VidTraceErrorStatusInternal0
0x14008e40c  mov     rdi, [rsp+58h+var_38]
0x14008e411  jmp     short loc_14008E436
0x14008e413  mov     ebx, eax
0x14008e415  mov     r9d, eax
0x14008e418  mov     r8d, 625h
0x14008e41e  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008e425  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008e42c  call    VidTraceErrorStatusInternal0
0x14008e431  mov     rdi, [rsp+58h+var_38]
0x14008e436  test    rdi, rdi
0x14008e439  jz      short loc_14008E44F
0x14008e43b  mov     edx, 72446456h; Tag
0x14008e440  mov     rcx, rdi; P
0x14008e443  call    cs:__imp_ExFreePoolWithTag
0x14008e44a  nop     dword ptr [rax+rax+00h]
0x14008e44f  mov     eax, ebx
0x14008e451  add     rsp, 30h
0x14008e455  pop     r15
0x14008e457  pop     r14
0x14008e459  pop     rdi
0x14008e45a  pop     rsi
0x14008e45b  pop     rbx
0x14008e45c  retn
```
