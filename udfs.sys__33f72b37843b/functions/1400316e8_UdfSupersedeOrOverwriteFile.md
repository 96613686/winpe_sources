# UdfSupersedeOrOverwriteFile

- ea: `0x1400316e8`
- end: `0x1400318eb`
- name: `UdfSupersedeOrOverwriteFile`
- size: `515`
- prototype: `__int64 __fastcall(int, int, __int64, int, int, char, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x140050ee0`

## callees

- `0x140005e80`
- `0x14000653c`
- `0x14000cb6c`
- `0x14001758c`
- `0x1400177ac`
- `0x1400316e8`
- `0x1400333bc`
- `0x140038724`
- `0x14004ce50`
- `0x140051d74`
- `0x140057330`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140031884`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b61b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140031884`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b61b`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140031766`
- `ntoskrnl!MmCanFileBeTruncated` at `0x140031766`

## pseudocode

```c
__int64 __fastcall UdfSupersedeOrOverwriteFile(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        union _LARGE_INTEGER *a7,
        int a8)
{
  char v12; // r15
  __int64 v13; // rdi
  __int64 NextStreamScb; // rax
  int v15; // r14d
  unsigned int v16; // edi
  __int64 v17; // rcx
  __int64 v18; // rdx
  _BYTE v20[32]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v21; // [rsp+68h] [rbp-30h]

  v21 = 0;
  v12 = 0;
  memset(v20, 0, sizeof(v20));
  UdfAcquireResource(a1, *(_QWORD *)(a3 + 16), 0, 0);
  if ( (*(_DWORD *)(a3 + 212) & 0x18) == 0 )
  {
    v13 = a3;
    while ( 1 )
    {
      NextStreamScb = UdfGetNextStreamScb(v13);
      v13 = NextStreamScb;
      if ( !NextStreamScb )
        break;
      if ( !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(NextStreamScb + 424) + 8LL), 0) )
      {
        v15 = -1073741245;
        goto LABEL_20;
      }
    }
  }
  v15 = UdfSetFileAllocationSize(a1, a2, a3, 0, a7, 1, 0);
  if ( v15 >= 0 )
  {
    v16 = a8 | 0x20;
    if ( (a8 & 2) != 0 )
    {
      if ( a5 && (*(_DWORD *)(a5 + 72) & 2) == 0 )
        UdfSetHiddenAttribute(a1);
      v16 = a8 & 0xFFFFFFDD | 0x20;
    }
    if ( a6 )
      *(_DWORD *)(a3 + 220) = v16;
    else
      *(_DWORD *)(a3 + 220) |= v16;
    v17 = *(_QWORD *)(*(_QWORD *)(a3 + 136) + 16LL);
    *(_DWORD *)(v17 + 212) |= 0x40000u;
    UdfUpdateScbTimeStamps(v17, a3, a4);
    if ( (*(_DWORD *)(a3 + 212) & 0x18) == 0 && *(_DWORD *)(*(_QWORD *)(a3 + 136) + 48LL) )
      v12 = UdfRemoveAlternateDataStreams(a1, v18);
    UdfPrepareModifyIcbForScb(a1, a3, v20);
    UdfFinishModifyIcb(a1, (__int64)v20, 1, (__int16 *)a3);
  }
LABEL_20:
  ExReleaseResourceLite(*(PERESOURCE *)(a3 + 16));
  UdfUnpinView(a1, v20);
  if ( v12 )
    UdfNotifyReportChange(a1, a4, a5, (int)a2, a3, 0x200u, 7u);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400316e8  mov     rax, rsp
0x1400316eb  mov     [rax+10h], rbx
0x1400316ef  mov     [rax+20h], rsi
0x1400316f3  mov     [rax+18h], r8
0x1400316f7  mov     [rax+8], rcx
0x1400316fb  push    rdi
0x1400316fc  push    r12
0x1400316fe  push    r13
0x140031700  push    r14
0x140031702  push    r15
0x140031704  sub     rsp, 70h
0x140031708  mov     r12, r9
0x14003170b  mov     rbx, r8
0x14003170e  mov     r13, rdx
0x140031711  mov     rsi, rcx
0x140031714  xorps   xmm0, xmm0
0x140031717  movdqu  xmmword ptr [rax-40h], xmm0
0x14003171c  mov     qword ptr [rax-30h], 0
0x140031724  xor     r15b, r15b
0x140031727  movdqu  xmmword ptr [rax-50h], xmm0
0x14003172c  xor     r9d, r9d
0x14003172f  xor     r8d, r8d
0x140031732  mov     rdx, [rbx+10h]
0x140031736  call    UdfAcquireResource
0x14003173b  nop
0x14003173c  mov     eax, [rbx+0D4h]
0x140031742  test    al, 18h
0x140031744  jnz     short loc_140031788
0x140031746  mov     rdi, rbx
0x140031749  mov     rcx, rdi
0x14003174c  call    UdfGetNextStreamScb
0x140031751  mov     rdi, rax
0x140031754  test    rax, rax
0x140031757  jz      short loc_140031788
0x140031759  mov     rcx, [rax+1A8h]
0x140031760  add     rcx, 8; SectionPointer
0x140031764  xor     edx, edx; NewFileSize
0x140031766  call    cs:__imp_MmCanFileBeTruncated
0x14003176d  nop     dword ptr [rax+rax+00h]
0x140031772  test    al, al
0x140031774  jnz     short loc_140031786
0x140031776  mov     r14d, 0C0000243h
0x14003177c  mov     [rsp+98h+var_58], r14d
0x140031781  jmp     loc_140031880
0x140031786  jmp     short loc_140031749
0x140031788  mov     byte ptr [rsp+98h+var_68], 0
0x14003178d  mov     byte ptr [rsp+98h+var_70], 1
0x140031792  mov     rax, [rsp+98h+arg_30]
0x14003179a  mov     [rsp+98h+var_78], rax
0x14003179f  xor     r9d, r9d
0x1400317a2  mov     r8, rbx
0x1400317a5  mov     rdx, r13
0x1400317a8  mov     rcx, rsi
0x1400317ab  call    UdfSetFileAllocationSize
0x1400317b0  mov     r14d, eax
0x1400317b3  mov     [rsp+98h+var_58], eax
0x1400317b7  test    eax, eax
0x1400317b9  js      loc_140031880
0x1400317bf  mov     edi, [rsp+98h+arg_38]
0x1400317c6  or      edi, 20h
0x1400317c9  mov     [rsp+98h+arg_38], edi
0x1400317d0  test    dil, 2
0x1400317d4  jz      short loc_140031803
0x1400317d6  mov     r8, [rsp+98h+arg_20]
0x1400317de  test    r8, r8
0x1400317e1  jz      short loc_1400317F9
0x1400317e3  mov     eax, [r8+48h]
0x1400317e7  test    al, 2
0x1400317e9  jnz     short loc_1400317F9
0x1400317eb  mov     r9b, 1
0x1400317ee  mov     rdx, rbx
0x1400317f1  mov     rcx, rsi; int
0x1400317f4  call    UdfSetHiddenAttribute
0x1400317f9  and     edi, 0FFFFFFFDh
0x1400317fc  mov     [rsp+98h+arg_38], edi
0x140031803  cmp     [rsp+98h+arg_28], 0
0x14003180b  jz      short loc_140031815
0x14003180d  mov     [rbx+0DCh], edi
0x140031813  jmp     short loc_14003181B
0x140031815  or      [rbx+0DCh], edi
0x14003181b  mov     rax, [rbx+88h]
0x140031822  mov     rcx, [rax+10h]
0x140031826  bts     dword ptr [rcx+0D4h], 12h
0x14003182e  mov     r8, r12
0x140031831  mov     rdx, rbx
0x140031834  call    UdfUpdateScbTimeStamps
0x140031839  mov     ecx, [rbx+0D4h]
0x14003183f  test    cl, 18h
0x140031842  jnz     short loc_14003185C
0x140031844  mov     rax, [rbx+88h]
0x14003184b  cmp     dword ptr [rax+30h], 0
0x14003184f  jz      short loc_14003185C
0x140031851  mov     rcx, rsi; int
0x140031854  call    UdfRemoveAlternateDataStreams
0x140031859  mov     r15b, al
0x14003185c  lea     r8, [rsp+98h+var_50]
0x140031861  mov     rdx, rbx
0x140031864  mov     rcx, rsi
0x140031867  call    UdfPrepareModifyIcbForScb
0x14003186c  mov     r9, rbx
0x14003186f  mov     r8b, 1
0x140031872  lea     rdx, [rsp+98h+var_50]
0x140031877  mov     rcx, rsi
0x14003187a  call    UdfFinishModifyIcb
0x14003187f  nop
0x140031880  mov     rcx, [rbx+10h]; Resource
0x140031884  call    cs:__imp_ExReleaseResourceLite
0x14003188b  nop     dword ptr [rax+rax+00h]
0x140031890  lea     rdx, [rsp+98h+var_50]
0x140031895  mov     rcx, rsi
0x140031898  call    UdfUnpinView
0x14003189d  test    r15b, r15b
0x1400318a0  jz      short loc_1400318CD
0x1400318a2  mov     [rsp+98h+var_68], 7; ULONG
0x1400318aa  mov     [rsp+98h+var_70], 200h; ULONG
0x1400318b2  mov     [rsp+98h+var_78], rbx; __int64
0x1400318b7  mov     r9, r13; int
0x1400318ba  mov     r8, [rsp+98h+arg_20]; int
0x1400318c2  mov     rdx, r12; int
0x1400318c5  mov     rcx, rsi; int
0x1400318c8  call    UdfNotifyReportChange
0x1400318cd  mov     eax, r14d
0x1400318d0  lea     r11, [rsp+98h+var_28]
0x1400318d5  mov     rbx, [r11+38h]
0x1400318d9  mov     rsi, [r11+48h]
0x1400318dd  mov     rsp, r11
0x1400318e0  pop     r15
0x1400318e2  pop     r14
0x1400318e4  pop     r13
0x1400318e6  pop     r12
0x1400318e8  pop     rdi
0x1400318e9  retn
0x14005b607  push    rbp
0x14005b609  sub     rsp, 40h
0x14005b60d  mov     rbp, rdx
0x14005b610  mov     rcx, [rbp+0B0h]
0x14005b617  mov     rcx, [rcx+10h]; Resource
0x14005b61b  call    cs:__imp_ExReleaseResourceLite
0x14005b622  nop     dword ptr [rax+rax+00h]
0x14005b627  lea     rdx, [rbp+48h]
0x14005b62b  mov     rcx, [rbp+0A0h]
0x14005b632  call    UdfUnpinView
0x14005b637  nop
0x14005b638  add     rsp, 40h
0x14005b63c  pop     rbp
0x14005b63d  retn
```
