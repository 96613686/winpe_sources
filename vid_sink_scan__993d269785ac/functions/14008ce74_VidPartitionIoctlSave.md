# VidPartitionIoctlSave

- ea: `0x14008ce74`
- end: `0x14008d07e`
- name: `VidPartitionIoctlSave`
- size: `522`
- prototype: `__int64 __fastcall(__int64, int, volatile void *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x14002f524`
- `0x140078f20`
- `0x14008ce74`
- `0x1400fb39c`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14008cf6d`
- `ntoskrnl!ProbeForWrite` at `0x14008cf6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008d063`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008d063`
- `ntoskrnl!ExAllocatePool2` at `0x14008cf87`
- `ntoskrnl!ExAllocatePool2` at `0x14008cf87`

## pseudocode

```c
__int64 __fastcall VidPartitionIoctlSave(__int64 a1, int a2, volatile void *a3, _DWORD *a4)
{
  int v6; // r15d
  void *Pool2; // rdi
  int PartitionState; // ebx
  __int64 v9; // rax

  v6 = a1;
  Pool2 = 0;
  if ( (a2 & 0xFFFFFFE5) != 0 )
  {
    PartitionState = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSave", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1522);
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
          if ( PartitionState >= 0 )
          {
            RtlCopyToUser((void *)a3, Pool2, (unsigned int)*a4);
            PartitionState = 0;
          }
          else
          {
            VidTraceErrorStatusInternal0("VidPartitionIoctlSave", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1594);
          }
        }
        else
        {
          PartitionState = -1073741670;
          VidTraceErrorStatusInternal0("VidPartitionIoctlSave", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1583);
        }
      }
      else
      {
        PartitionState = -1073741790;
        VidTraceErrorStatusInternal0("VidPartitionIoctlSave", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1546);
      }
    }
    else
    {
      PartitionState = -1073741811;
      VidTraceErrorStatusInternal0("VidPartitionIoctlSave", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1536);
    }
  }
  else
  {
    PartitionState = -1073741811;
    VidTraceErrorStatusInternal0("VidPartitionIoctlSave", "onecore\\vm\\vid\\sys\\driver\\vidpartition.c", 1529);
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72446456u);
  return (unsigned int)PartitionState;
}

```

## disassembly

```asm
0x14008ce74  push    rbx
0x14008ce76  push    rsi
0x14008ce77  push    rdi
0x14008ce78  push    r14
0x14008ce7a  push    r15
0x14008ce7c  sub     rsp, 30h
0x14008ce80  mov     rsi, r9
0x14008ce83  mov     r14, r8
0x14008ce86  mov     ebx, edx
0x14008ce88  mov     r15, rcx
0x14008ce8b  xor     edi, edi
0x14008ce8d  mov     [rsp+58h+var_38], rdi
0x14008ce92  test    edx, 0FFFFFFE5h
0x14008ce98  jz      short loc_14008CEC1
0x14008ce9a  mov     r9d, 0C000000Dh
0x14008cea0  mov     ebx, r9d
0x14008cea3  mov     r8d, 5F2h
0x14008cea9  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008ceb0  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008ceb7  call    VidTraceErrorStatusInternal0
0x14008cebc  jmp     loc_14008D056
0x14008cec1  test    r14, r14
0x14008cec4  jnz     short loc_14008CEED
0x14008cec6  mov     r9d, 0C000000Dh
0x14008cecc  mov     ebx, r9d
0x14008cecf  mov     r8d, 5F9h
0x14008ced5  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cedc  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008cee3  call    VidTraceErrorStatusInternal0
0x14008cee8  jmp     loc_14008D056
0x14008ceed  mov     ecx, [r9]
0x14008cef0  cmp     ecx, 18h
0x14008cef3  jnb     short loc_14008CF1C
0x14008cef5  mov     r9d, 0C000000Dh
0x14008cefb  mov     ebx, r9d
0x14008cefe  mov     r8d, 600h
0x14008cf04  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cf0b  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008cf12  call    VidTraceErrorStatusInternal0
0x14008cf17  jmp     loc_14008D056
0x14008cf1c  mov     rax, [r15+20h]
0x14008cf20  and     eax, 1E0h
0x14008cf25  cmp     rax, 40h ; '@'
0x14008cf29  jnz     short loc_14008CF30
0x14008cf2b  test    bl, 8
0x14008cf2e  jz      short loc_14008CF3B
0x14008cf30  cmp     rax, 60h ; '`'
0x14008cf34  jnz     short loc_14008CF61
0x14008cf36  test    bl, 18h
0x14008cf39  jnz     short loc_14008CF61
0x14008cf3b  mov     ebx, 0C0000022h
0x14008cf40  mov     r9d, ebx
0x14008cf43  mov     r8d, 60Ah
0x14008cf49  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cf50  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008cf57  call    VidTraceErrorStatusInternal0
0x14008cf5c  jmp     loc_14008D056
0x14008cf61  mov     rdx, rcx; Length
0x14008cf64  mov     r8d, 1; Alignment
0x14008cf6a  mov     rcx, r14; Address
0x14008cf6d  call    cs:__imp_ProbeForWrite
0x14008cf74  nop     dword ptr [rax+rax+00h]
0x14008cf79  nop
0x14008cf7a  mov     edx, [rsi]
0x14008cf7c  mov     ecx, 41h ; 'A'
0x14008cf81  mov     r8d, 72446456h
0x14008cf87  call    cs:__imp_ExAllocatePool2
0x14008cf8e  nop     dword ptr [rax+rax+00h]
0x14008cf93  mov     rdi, rax
0x14008cf96  mov     [rsp+58h+var_38], rax
0x14008cf9b  test    rax, rax
0x14008cf9e  jnz     short loc_14008CFC6
0x14008cfa0  mov     ebx, 0C000009Ah
0x14008cfa5  mov     r9d, ebx
0x14008cfa8  mov     r8d, 62Fh
0x14008cfae  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cfb5  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008cfbc  call    VidTraceErrorStatusInternal0
0x14008cfc1  jmp     loc_14008D056
0x14008cfc6  mov     r9d, ebx
0x14008cfc9  mov     r8, rsi
0x14008cfcc  mov     rdx, rdi
0x14008cfcf  mov     rcx, r15; int
0x14008cfd2  call    VidSaveRestoreGetPartitionState
0x14008cfd7  mov     ebx, eax
0x14008cfd9  test    eax, eax
0x14008cfdb  jns     short loc_14008CFFB
0x14008cfdd  mov     r9d, eax
0x14008cfe0  mov     r8d, 63Ah
0x14008cfe6  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008cfed  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008cff4  call    VidTraceErrorStatusInternal0
0x14008cff9  jmp     short loc_14008D056
0x14008cffb  mov     r8d, [rsi]; Size
0x14008cffe  mov     rdx, rdi; Src
0x14008d001  mov     rcx, r14; void *
0x14008d004  call    RtlCopyToUser
0x14008d009  nop
0x14008d00a  xor     ebx, ebx
0x14008d00c  jmp     short loc_14008D056
0x14008d00e  mov     ebx, eax
0x14008d010  mov     r9d, eax
0x14008d013  mov     r8d, 648h
0x14008d019  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008d020  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008d027  call    VidTraceErrorStatusInternal0
0x14008d02c  mov     rdi, [rsp+58h+var_38]
0x14008d031  jmp     short loc_14008D056
0x14008d033  mov     ebx, eax
0x14008d035  mov     r9d, eax
0x14008d038  mov     r8d, 620h
0x14008d03e  lea     rdx, aOnecoreVmVidSy_45; "onecore\\vm\\vid\\sys\\driver\\vidparti"...
0x14008d045  lea     rcx, aVidpartitionio_6; "VidPartitionIoctlSave"
0x14008d04c  call    VidTraceErrorStatusInternal0
0x14008d051  mov     rdi, [rsp+58h+var_38]
0x14008d056  test    rdi, rdi
0x14008d059  jz      short loc_14008D06F
0x14008d05b  mov     edx, 72446456h; Tag
0x14008d060  mov     rcx, rdi; P
0x14008d063  call    cs:__imp_ExFreePoolWithTag
0x14008d06a  nop     dword ptr [rax+rax+00h]
0x14008d06f  mov     eax, ebx
0x14008d071  add     rsp, 30h
0x14008d075  pop     r15
0x14008d077  pop     r14
0x14008d079  pop     rdi
0x14008d07a  pop     rsi
0x14008d07b  pop     rbx
0x14008d07c  retn
```
