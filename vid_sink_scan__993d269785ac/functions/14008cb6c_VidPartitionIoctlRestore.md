# VidPartitionIoctlRestore

- ea: `0x14008cb6c`
- end: `0x14008ce6d`
- name: `VidPartitionIoctlRestore`
- size: `769`
- prototype: `__int64 __fastcall(__int64, int, volatile void *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140035698`
- `0x1400377bc`

## callees

- `0x1400116c8`
- `0x140024754`
- `0x14002f524`
- `0x14008cb6c`
- `0x1400fb664`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14008cc8a`
- `ntoskrnl!ProbeForRead` at `0x14008cc8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cdf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cdf7`
- `ntoskrnl!ExAllocatePool2` at `0x14008cca5`
- `ntoskrnl!ExAllocatePool2` at `0x14008cca5`

## pseudocode

```c
__int64 __fastcall VidPartitionIoctlRestore(__int64 a1, int a2, volatile void *a3, unsigned int a4)
{
  size_t *v6; // rdi
  int v7; // ebx
  int v8; // edx
  bool v9; // r15
  size_t v10; // rbx
  size_t *Pool2; // rax
  __int64 v12; // r8
  size_t v13; // rax
  size_t v14; // rdx

  v6 = 0;
  if ( (a2 & 0xFFFFFFFB) != 0 )
  {
    v7 = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlRestore", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1313);
    goto LABEL_23;
  }
  v8 = a2 & 4;
  v9 = v8 != 0;
  if ( a1 )
  {
    if ( v8 )
    {
      v7 = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlRestore", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1344);
      goto LABEL_23;
    }
  }
  else if ( !v8 )
  {
    v7 = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlRestore", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1334);
    goto LABEL_23;
  }
  if ( a3 )
  {
    if ( a4 >= 0x18 )
    {
      v10 = a4;
      ProbeForRead(a3, a4, 1u);
      Pool2 = (size_t *)ExAllocatePool2(65, v10, 1917084758);
      v6 = Pool2;
      if ( Pool2 )
      {
        RtlCopyFromUser(Pool2, (void *)a3, v10);
        v13 = v6[1];
        if ( v13 > v10 || (v14 = v6[2], v14 > v10) )
        {
          v7 = -1073741811;
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlRestore",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            1419);
        }
        else if ( *v6 < 0x18 || *v6 > v13 || v13 > v14 )
        {
          v7 = -1070137305;
          VidTraceErrorStatusInternal0(
            "VidPartitionIoctlRestore",
            "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
            1431);
        }
        else
        {
          LOBYTE(v12) = v9;
          v7 = VidSaveRestoreSetPartitionState(a1, v6, v12);
          if ( v7 < 0 )
            VidTraceErrorStatusInternal0(
              "VidPartitionIoctlRestore",
              "onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
              1441);
        }
      }
      else
      {
        v7 = -1073741670;
        VidTraceErrorStatusInternal0("VidPartitionIoctlRestore", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1394);
      }
    }
    else
    {
      v7 = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlRestore", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1360);
    }
  }
  else
  {
    v7 = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlRestore", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1353);
  }
LABEL_23:
  if ( v6 )
    ExFreePoolWithTag(v6, 0x72446456u);
  if ( a1 )
  {
    if ( v7 < 0 )
      VidTraceErrorStatusPartitionInternal0(
        (unsigned int)"VidPartitionIoctlRestore",
        (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidpartition.c",
        1455,
        v7,
        a1 + 656);
  }
  else if ( v7 < 0 )
  {
    VidTraceErrorStatusInternal0("VidPartitionIoctlRestore", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1459);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14008cb6c  mov     [rsp+arg_8], rbx
0x14008cb71  mov     [rsp+arg_10], rsi
0x14008cb76  mov     [rsp+arg_0], rcx
0x14008cb7b  push    rdi
0x14008cb7c  push    r14
0x14008cb7e  push    r15
0x14008cb80  sub     rsp, 40h
0x14008cb84  mov     rsi, r8
0x14008cb87  mov     r14, rcx
0x14008cb8a  xor     edi, edi
0x14008cb8c  mov     [rsp+58h+var_28], rdi
0x14008cb91  test    edx, 0FFFFFFFBh
0x14008cb97  jz      short loc_14008CBC0
0x14008cb99  mov     r9d, 0C000000Dh
0x14008cb9f  mov     ebx, r9d
0x14008cba2  mov     r8d, 521h
0x14008cba8  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cbaf  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cbb6  call    VidTraceErrorStatusInternal0
0x14008cbbb  jmp     loc_14008CDEA
0x14008cbc0  and     edx, 4
0x14008cbc3  setnz   r15b
0x14008cbc7  test    r14, r14
0x14008cbca  jnz     short loc_14008CBF7
0x14008cbcc  test    edx, edx
0x14008cbce  jnz     short loc_14008CC22
0x14008cbd0  mov     r9d, 0C000000Dh
0x14008cbd6  mov     ebx, r9d
0x14008cbd9  mov     r8d, 536h
0x14008cbdf  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cbe6  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cbed  call    VidTraceErrorStatusInternal0
0x14008cbf2  jmp     loc_14008CDEA
0x14008cbf7  test    edx, edx
0x14008cbf9  jz      short loc_14008CC22
0x14008cbfb  mov     r9d, 0C000000Dh
0x14008cc01  mov     ebx, r9d
0x14008cc04  mov     r8d, 540h
0x14008cc0a  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cc11  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cc18  call    VidTraceErrorStatusInternal0
0x14008cc1d  jmp     loc_14008CDEA
0x14008cc22  test    rsi, rsi
0x14008cc25  jnz     short loc_14008CC4E
0x14008cc27  mov     r9d, 0C000000Dh
0x14008cc2d  mov     ebx, r9d
0x14008cc30  mov     r8d, 549h
0x14008cc36  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cc3d  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cc44  call    VidTraceErrorStatusInternal0
0x14008cc49  jmp     loc_14008CDEA
0x14008cc4e  cmp     r9d, 18h
0x14008cc52  jnb     short loc_14008CC7B
0x14008cc54  mov     r9d, 0C000000Dh
0x14008cc5a  mov     ebx, r9d
0x14008cc5d  mov     r8d, 550h
0x14008cc63  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cc6a  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cc71  call    VidTraceErrorStatusInternal0
0x14008cc76  jmp     loc_14008CDEA
0x14008cc7b  mov     ebx, r9d
0x14008cc7e  mov     r8d, 1; Alignment
0x14008cc84  mov     edx, r9d; Length
0x14008cc87  mov     rcx, rsi; Address
0x14008cc8a  call    cs:__imp_ProbeForRead
0x14008cc91  nop     dword ptr [rax+rax+00h]
0x14008cc96  nop
0x14008cc97  mov     r8d, 72446456h
0x14008cc9d  mov     rdx, rbx
0x14008cca0  mov     ecx, 41h ; 'A'
0x14008cca5  call    cs:__imp_ExAllocatePool2
0x14008ccac  nop     dword ptr [rax+rax+00h]
0x14008ccb1  mov     rdi, rax
0x14008ccb4  mov     [rsp+58h+var_28], rax
0x14008ccb9  test    rax, rax
0x14008ccbc  jnz     short loc_14008CCE4
0x14008ccbe  mov     ebx, 0C000009Ah
0x14008ccc3  mov     r9d, ebx
0x14008ccc6  mov     r8d, 572h
0x14008cccc  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008ccd3  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008ccda  call    VidTraceErrorStatusInternal0
0x14008ccdf  jmp     loc_14008CDEA
0x14008cce4  mov     r8, rbx; Size
0x14008cce7  mov     rdx, rsi; Src
0x14008ccea  mov     rcx, rdi; void *
0x14008cced  call    RtlCopyFromUser
0x14008ccf2  nop
0x14008ccf3  mov     rax, [rdi+8]
0x14008ccf7  cmp     rax, rbx
0x14008ccfa  ja      short loc_14008CD74
0x14008ccfc  mov     rdx, [rdi+10h]
0x14008cd00  cmp     rdx, rbx
0x14008cd03  ja      short loc_14008CD74
0x14008cd05  mov     rcx, [rdi]
0x14008cd08  cmp     rcx, 18h
0x14008cd0c  jb      short loc_14008CD51
0x14008cd0e  cmp     rcx, rax
0x14008cd11  ja      short loc_14008CD51
0x14008cd13  cmp     rax, rdx
0x14008cd16  ja      short loc_14008CD51
0x14008cd18  mov     r8b, r15b
0x14008cd1b  mov     rdx, rdi
0x14008cd1e  mov     rcx, r14
0x14008cd21  call    VidSaveRestoreSetPartitionState
0x14008cd26  mov     ebx, eax
0x14008cd28  test    eax, eax
0x14008cd2a  jns     loc_14008CDEA
0x14008cd30  mov     r9d, eax
0x14008cd33  mov     r8d, 5A1h
0x14008cd39  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cd40  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cd47  call    VidTraceErrorStatusInternal0
0x14008cd4c  jmp     loc_14008CDEA
0x14008cd51  mov     ebx, 0C0370027h
0x14008cd56  mov     r9d, ebx
0x14008cd59  mov     r8d, 597h
0x14008cd5f  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cd66  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cd6d  call    VidTraceErrorStatusInternal0
0x14008cd72  jmp     short loc_14008CDEA
0x14008cd74  mov     r9d, 0C000000Dh
0x14008cd7a  mov     ebx, r9d
0x14008cd7d  mov     r8d, 58Bh
0x14008cd83  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cd8a  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cd91  call    VidTraceErrorStatusInternal0
0x14008cd96  jmp     short loc_14008CDEA
0x14008cd98  mov     ebx, eax
0x14008cd9a  mov     r9d, eax
0x14008cd9d  mov     r8d, 580h
0x14008cda3  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cdaa  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cdb1  call    VidTraceErrorStatusInternal0
0x14008cdb6  mov     r14, [rsp+58h+arg_0]
0x14008cdbb  mov     rdi, [rsp+58h+var_28]
0x14008cdc0  jmp     short loc_14008CDEA
0x14008cdc2  mov     ebx, eax
0x14008cdc4  mov     r9d, eax
0x14008cdc7  mov     r8d, 566h
0x14008cdcd  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cdd4  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008cddb  call    VidTraceErrorStatusInternal0
0x14008cde0  mov     r14, [rsp+58h+arg_0]
0x14008cde5  mov     rdi, [rsp+58h+var_28]
0x14008cdea  test    rdi, rdi
0x14008cded  jz      short loc_14008CE03
0x14008cdef  mov     edx, 72446456h; Tag
0x14008cdf4  mov     rcx, rdi; P
0x14008cdf7  call    cs:__imp_ExFreePoolWithTag
0x14008cdfe  nop     dword ptr [rax+rax+00h]
0x14008ce03  test    r14, r14
0x14008ce06  jz      short loc_14008CE36
0x14008ce08  test    ebx, ebx
0x14008ce0a  jns     short loc_14008CE56
0x14008ce0c  lea     rax, [r14+290h]
0x14008ce13  mov     [rsp+58h+var_38], rax
0x14008ce18  mov     r9d, ebx
0x14008ce1b  mov     r8d, 5AFh
0x14008ce21  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008ce28  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008ce2f  call    VidTraceErrorStatusPartitionInternal0
0x14008ce34  jmp     short loc_14008CE56
0x14008ce36  test    ebx, ebx
0x14008ce38  jns     short loc_14008CE56
0x14008ce3a  mov     r9d, ebx
0x14008ce3d  mov     r8d, 5B3h
0x14008ce43  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008ce4a  lea     rcx, aVidpartitionio_13; "VidPartitionIoctlRestore"
0x14008ce51  call    VidTraceErrorStatusInternal0
0x14008ce56  mov     eax, ebx
0x14008ce58  mov     rbx, [rsp+58h+arg_8]
0x14008ce5d  mov     rsi, [rsp+58h+arg_10]
0x14008ce62  add     rsp, 40h
0x14008ce66  pop     r15
0x14008ce68  pop     r14
0x14008ce6a  pop     rdi
0x14008ce6b  retn
```
