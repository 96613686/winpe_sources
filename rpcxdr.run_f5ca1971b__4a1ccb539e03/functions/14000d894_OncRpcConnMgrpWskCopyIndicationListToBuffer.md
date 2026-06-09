# OncRpcConnMgrpWskCopyIndicationListToBuffer

- ea: `0x14000d894`
- end: `0x14000db24`
- name: `OncRpcConnMgrpWskCopyIndicationListToBuffer`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000df80`

## callees

- `0x1400020c0`
- `0x140005794`
- `0x14000d894`
- `0x14000efe4`
- `0x140015840`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d9aa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000d9aa`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskCopyIndicationListToBuffer(
        __int64 **a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r12
  int v7; // esi
  struct _MDL *v9; // r14
  __int64 v10; // rbp
  size_t v11; // r13
  size_t v12; // rbx
  char *MappedSystemVa; // rcx
  char *v14; // rax
  unsigned __int64 v15; // rax
  size_t v16; // rdi
  unsigned __int64 v18; // [rsp+80h] [rbp+8h]
  unsigned __int64 v20; // [rsp+90h] [rbp+18h]

  v20 = a3;
  v5 = 0;
  v6 = 0;
  v18 = 0;
  v7 = 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    goto LABEL_37;
  WPP_SF_iii(WPP_GLOBAL_Control->AttachedDevice, 47, a3, a2, a3, a5);
LABEL_36:
  a3 = v20;
LABEL_37:
  if ( a1 && v6 < a3 && v7 >= 0 )
  {
    v9 = (struct _MDL *)a1[1];
    v10 = *((unsigned int *)a1 + 4);
    v11 = (size_t)a1[3];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_iii(WPP_GLOBAL_Control->AttachedDevice, 48, a3, (unsigned int)v10, v11, v6);
      goto LABEL_9;
    }
    while ( 1 )
    {
      if ( !v9 || v6 >= a3 )
      {
LABEL_35:
        a1 = (__int64 **)*a1;
        goto LABEL_36;
      }
      v12 = v11;
      if ( v11 >= (unsigned __int64)v9->ByteCount - v10 )
        v12 = v9->ByteCount - v10;
      if ( (v9->MdlFlags & 5) != 0 )
      {
        MappedSystemVa = (char *)v9->MappedSystemVa;
      }
      else
      {
        v14 = (char *)MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000000u);
        a3 = v20;
        MappedSystemVa = v14;
      }
      if ( !MappedSystemVa )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids);
        }
        v7 = -1073741670;
        goto LABEL_35;
      }
      if ( v5 < a2 )
      {
        v15 = a2 - v5;
        if ( v12 <= a2 - v5 )
          goto LABEL_26;
        v10 += v15;
        v18 = a2;
        v12 -= v15;
        v11 -= v15;
      }
      if ( v12 )
      {
        v16 = a3 - v6;
        if ( v12 < a3 - v6 )
          v16 = v12;
        if ( a5 - v6 < v16 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            WPP_SF_iii(WPP_GLOBAL_Control->AttachedDevice, 50, a5, a5, v6, v16);
          }
          v5 = v18;
          v7 = -1073741789;
          goto LABEL_35;
        }
        memmove((void *)(v6 + a4), &MappedSystemVa[v10], v16);
        v18 += v16;
        v6 += v16;
        v11 -= v16;
      }
LABEL_26:
      v9 = v9->Next;
      v10 = 0;
      v5 = v18;
LABEL_9:
      a3 = v20;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000d894  mov     r11, rsp
0x14000d897  mov     [r11+20h], r9
0x14000d89b  mov     [r11+18h], r8
0x14000d89f  mov     [r11+10h], rdx
0x14000d8a3  push    rbx
0x14000d8a4  push    rbp
0x14000d8a5  push    rsi
0x14000d8a6  push    rdi
0x14000d8a7  push    r12
0x14000d8a9  push    r13
0x14000d8ab  push    r14
0x14000d8ad  push    r15
0x14000d8af  sub     rsp, 38h
0x14000d8b3  xor     edi, edi
0x14000d8b5  xor     r12d, r12d
0x14000d8b8  mov     [rsp+78h+arg_0], rdi
0x14000d8c0  xor     esi, esi
0x14000d8c2  mov     r9, rdx
0x14000d8c5  mov     r15, rcx
0x14000d8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8cf  lea     rbx, WPP_GLOBAL_Control
0x14000d8d6  cmp     rcx, rbx
0x14000d8d9  jz      loc_14000DADB
0x14000d8df  mov     eax, [rcx+2Ch]
0x14000d8e2  test    al, 1
0x14000d8e4  jz      loc_14000DADB
0x14000d8ea  mov     rax, [rsp+78h+arg_20]
0x14000d8f2  lea     edx, [rdi+2Fh]
0x14000d8f5  mov     rcx, [rcx+18h]
0x14000d8f9  mov     [r11-50h], rax
0x14000d8fd  mov     [r11-58h], r8
0x14000d901  call    WPP_SF_iii
0x14000d906  jmp     loc_14000DAD3
0x14000d90b  cmp     r12, r8
0x14000d90e  jnb     loc_14000DAE4
0x14000d914  test    esi, esi
0x14000d916  js      loc_14000DAE4
0x14000d91c  mov     r14, [r15+8]
0x14000d920  mov     ebp, [r15+10h]
0x14000d924  mov     r13, [r15+18h]
0x14000d928  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d92f  cmp     rcx, rbx
0x14000d932  jz      short loc_14000D95E
0x14000d934  mov     eax, [rcx+2Ch]
0x14000d937  test    al, 8
0x14000d939  jz      short loc_14000D95E
0x14000d93b  mov     rcx, [rcx+18h]
0x14000d93f  mov     edx, 30h ; '0'
0x14000d944  mov     qword ptr [rsp+78h+Priority], r12
0x14000d949  mov     r9d, ebp
0x14000d94c  mov     qword ptr [rsp+78h+BugCheckOnFailure], r13
0x14000d951  call    WPP_SF_iii
0x14000d956  mov     r8, [rsp+78h+arg_10]
0x14000d95e  test    r14, r14
0x14000d961  jz      loc_14000DAC9
0x14000d967  cmp     r12, r8
0x14000d96a  jnb     loc_14000DAC9
0x14000d970  mov     eax, [r14+28h]
0x14000d974  mov     rbx, r13
0x14000d977  sub     rax, rbp
0x14000d97a  cmp     r13, rax
0x14000d97d  cmovnb  rbx, rax
0x14000d981  test    byte ptr [r14+0Ah], 5
0x14000d986  jz      short loc_14000D98E
0x14000d988  mov     rcx, [r14+18h]
0x14000d98c  jmp     short loc_14000D9C1
0x14000d98e  xor     r9d, r9d; RequestedAddress
0x14000d991  mov     [rsp+78h+Priority], 40000000h; Priority
0x14000d999  xor     edx, edx; AccessMode
0x14000d99b  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000d9a3  mov     rcx, r14; MemoryDescriptorList
0x14000d9a6  lea     r8d, [r9+1]; CacheType
0x14000d9aa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000d9b1  nop     dword ptr [rax+rax+00h]
0x14000d9b6  mov     r8, [rsp+78h+arg_10]
0x14000d9be  mov     rcx, rax
0x14000d9c1  test    rcx, rcx
0x14000d9c4  jz      loc_14000DA93
0x14000d9ca  mov     rdx, [rsp+78h+arg_8]
0x14000d9d2  cmp     rdi, rdx
0x14000d9d5  jnb     short loc_14000D9F3
0x14000d9d7  mov     rax, rdx
0x14000d9da  sub     rax, rdi
0x14000d9dd  cmp     rbx, rax
0x14000d9e0  jbe     short loc_14000DA3D
0x14000d9e2  add     rbp, rax
0x14000d9e5  mov     [rsp+78h+arg_0], rdx
0x14000d9ed  sub     rbx, rax
0x14000d9f0  sub     r13, rax
0x14000d9f3  test    rbx, rbx
0x14000d9f6  jz      short loc_14000DA3D
0x14000d9f8  mov     rdi, r8
0x14000d9fb  mov     r8, [rsp+78h+arg_20]
0x14000da03  sub     rdi, r12
0x14000da06  mov     rax, r8
0x14000da09  cmp     rbx, rdi
0x14000da0c  cmovb   rdi, rbx
0x14000da10  sub     rax, r12
0x14000da13  cmp     rax, rdi
0x14000da16  jb      short loc_14000DA4F
0x14000da18  lea     rdx, [rcx+rbp]; Src
0x14000da1c  mov     r8, rdi; Size
0x14000da1f  mov     rcx, [rsp+78h+arg_18]
0x14000da27  add     rcx, r12; void *
0x14000da2a  call    memmove
0x14000da2f  add     [rsp+78h+arg_0], rdi
0x14000da37  add     r12, rdi
0x14000da3a  sub     r13, rdi
0x14000da3d  mov     r14, [r14]
0x14000da40  xor     ebp, ebp
0x14000da42  mov     rdi, [rsp+78h+arg_0]
0x14000da4a  jmp     loc_14000D956
0x14000da4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da56  lea     rbx, WPP_GLOBAL_Control
0x14000da5d  cmp     rcx, rbx
0x14000da60  jz      short loc_14000DA84
0x14000da62  mov     eax, [rcx+2Ch]
0x14000da65  test    al, 10h
0x14000da67  jz      short loc_14000DA84
0x14000da69  mov     rcx, [rcx+18h]
0x14000da6d  mov     edx, 32h ; '2'
0x14000da72  mov     qword ptr [rsp+78h+Priority], rdi
0x14000da77  mov     r9, r8
0x14000da7a  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12
0x14000da7f  call    WPP_SF_iii
0x14000da84  mov     rdi, [rsp+78h+arg_0]
0x14000da8c  mov     esi, 0C0000023h
0x14000da91  jmp     short loc_14000DAD0
0x14000da93  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da9a  lea     rbx, WPP_GLOBAL_Control
0x14000daa1  cmp     rcx, rbx
0x14000daa4  jz      short loc_14000DAC2
0x14000daa6  mov     eax, [rcx+2Ch]
0x14000daa9  test    al, 10h
0x14000daab  jz      short loc_14000DAC2
0x14000daad  mov     rcx, [rcx+18h]
0x14000dab1  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000dab8  mov     edx, 31h ; '1'
0x14000dabd  call    WPP_SF_
0x14000dac2  mov     esi, 0C000009Ah
0x14000dac7  jmp     short loc_14000DAD0
0x14000dac9  lea     rbx, WPP_GLOBAL_Control
0x14000dad0  mov     r15, [r15]
0x14000dad3  mov     r8, [rsp+78h+arg_10]
0x14000dadb  test    r15, r15
0x14000dade  jnz     loc_14000D90B
0x14000dae4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000daeb  cmp     rcx, rbx
0x14000daee  jz      short loc_14000DB10
0x14000daf0  mov     edx, [rcx+2Ch]
0x14000daf3  test    dl, 1
0x14000daf6  jz      short loc_14000DB10
0x14000daf8  mov     rcx, [rcx+18h]
0x14000dafc  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000db03  mov     edx, 33h ; '3'
0x14000db08  mov     r9d, esi
0x14000db0b  call    WPP_SF_d
0x14000db10  mov     eax, esi
0x14000db12  add     rsp, 38h
0x14000db16  pop     r15
0x14000db18  pop     r14
0x14000db1a  pop     r13
0x14000db1c  pop     r12
0x14000db1e  pop     rdi
0x14000db1f  pop     rsi
0x14000db20  pop     rbp
0x14000db21  pop     rbx
0x14000db22  retn
```
