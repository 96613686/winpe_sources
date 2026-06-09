# VsmmMemPartIoctlEnumerate

- ea: `0x1400a54d4`
- end: `0x1400a56fe`
- name: `VsmmMemPartIoctlEnumerate`
- size: `554`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess, _QWORD *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400377bc`

## callees

- `0x140016c50`
- `0x140038630`
- `0x140078f20`
- `0x140078ff8`
- `0x1400790d0`
- `0x1400a54d4`
- `0x1400fbd7c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a55c0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a55c0`
- `ntoskrnl!PsPartitionType` at `0x1400a558f`
- `ntoskrnl!NtClose` at `0x1400a56d4`
- `ntoskrnl!NtClose` at `0x1400a56d4`

## pseudocode

```c
__int64 __fastcall VsmmMemPartIoctlEnumerate(ACCESS_MASK DesiredAccess, _QWORD *a2, void *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  int v7; // esi
  unsigned __int64 ULong64FromUser; // r15
  int i; // esi
  __int64 v10; // rax
  __int64 v11; // r13
  void *PartitionObject; // rax
  POBJECT_TYPE ObjectType; // rdx
  void *Handle[2]; // [rsp+48h] [rbp-70h] BYREF
  HANDLE Src[12]; // [rsp+58h] [rbp-60h] BYREF

  v5 = 0;
  v6 = 0;
  if ( a2 )
  {
    ULong64FromUser = RtlReadULong64FromUser(a2);
    if ( ULong64FromUser >= 2 )
      ULong64FromUser = 2;
    if ( DesiredAccess - 1 <= 1 || DesiredAccess == 2031619 )
    {
      for ( i = 0; i < 2; ++i )
      {
        Handle[1] = (void *)0xFFFFFFFFLL;
        Handle[0] = 0;
        v10 = VsmmMemReserveMemPartGet((unsigned int)i);
        v11 = v10;
        if ( v10 )
        {
          if ( (unsigned int)(*(_DWORD *)(v10 + 32) - 1) <= 2 )
          {
            PartitionObject = (void *)VsmmMemPartGetPartitionObject(v10, PsPartitionType);
            if ( ObOpenObjectByPointer(PartitionObject, 0, 0, DesiredAccess, ObjectType, 1, Handle) >= 0 )
            {
              LODWORD(Handle[1]) = *(_DWORD *)(v11 + 28);
              *(_OWORD *)&Src[2 * v6++] = *(_OWORD *)Handle;
            }
          }
        }
      }
      if ( v6 )
      {
        if ( ULong64FromUser < v6 || !a3 )
        {
          v7 = -1073741789;
          goto LABEL_20;
        }
        RtlCopyToUser(a3, Src, 16 * v6);
      }
      v7 = 0;
      goto LABEL_20;
    }
    v7 = -1073741811;
  }
  else
  {
    v7 = -1073741811;
    VidTraceErrorInternal0("VsmmMemPartIoctlEnumerate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c", 202);
  }
LABEL_20:
  RtlWriteULong64ToUser(a2, v6);
  if ( v7 < 0 && v6 )
  {
    do
      NtClose(Src[2 * v5++]);
    while ( v5 < v6 );
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400a54d4  mov     [rsp+arg_10], r8
0x1400a54d9  mov     [rsp+arg_8], rdx
0x1400a54de  push    rbx
0x1400a54df  push    rsi
0x1400a54e0  push    rdi
0x1400a54e1  push    r12
0x1400a54e3  push    r13
0x1400a54e5  push    r14
0x1400a54e7  push    r15
0x1400a54e9  sub     rsp, 80h
0x1400a54f0  mov     r14, rdx
0x1400a54f3  mov     r12d, ecx
0x1400a54f6  xor     ebx, ebx
0x1400a54f8  mov     edi, ebx
0x1400a54fa  mov     [rsp+0B8h+arg_18], rbx
0x1400a5502  test    rdx, rdx
0x1400a5505  jnz     short loc_1400A552A
0x1400a5507  mov     esi, 0C000000Dh
0x1400a550c  mov     r8d, 0CAh
0x1400a5512  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a5519  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a5520  call    VidTraceErrorInternal0
0x1400a5525  jmp     loc_1400A568D
0x1400a552a  mov     rcx, rdx
0x1400a552d  call    RtlReadULong64FromUser
0x1400a5532  mov     r15, rax
0x1400a5535  mov     [rsp+0B8h+var_78], rax
0x1400a553a  mov     eax, 2
0x1400a553f  cmp     r15, rax
0x1400a5542  cmovnb  r15, rax
0x1400a5546  lea     eax, [r12-1]
0x1400a554b  cmp     eax, 1
0x1400a554e  jbe     short loc_1400A5563
0x1400a5550  cmp     r12d, 1F0003h
0x1400a5557  jz      short loc_1400A5563
0x1400a5559  mov     esi, 0C000000Dh
0x1400a555e  jmp     loc_1400A568D
0x1400a5563  mov     esi, ebx
0x1400a5565  mov     dword ptr [rsp+0B8h+var_70+0Ch], ebx
0x1400a5569  mov     dword ptr [rsp+0B8h+var_70+8], 0FFFFFFFFh
0x1400a5571  mov     [rsp+0B8h+var_70], rbx
0x1400a5576  mov     ecx, esi
0x1400a5578  call    VsmmMemReserveMemPartGet
0x1400a557d  mov     r13, rax
0x1400a5580  test    rax, rax
0x1400a5583  jz      short loc_1400A55F4
0x1400a5585  mov     eax, [rax+20h]
0x1400a5588  dec     eax
0x1400a558a  cmp     eax, 2
0x1400a558d  ja      short loc_1400A55F4
0x1400a558f  mov     rax, cs:__imp_PsPartitionType
0x1400a5596  mov     rdx, [rax]
0x1400a5599  mov     rcx, r13
0x1400a559c  call    VsmmMemPartGetPartitionObject
0x1400a55a1  mov     rcx, rax; Object
0x1400a55a4  lea     rax, [rsp+0B8h+var_70]
0x1400a55a9  mov     [rsp+0B8h+Handle], rax; Handle
0x1400a55ae  mov     [rsp+0B8h+AccessMode], 1; AccessMode
0x1400a55b3  mov     [rsp+0B8h+ObjectType], rdx; ObjectType
0x1400a55b8  mov     r9d, r12d; DesiredAccess
0x1400a55bb  xor     r8d, r8d; PassedAccessState
0x1400a55be  xor     edx, edx; HandleAttributes
0x1400a55c0  call    cs:__imp_ObOpenObjectByPointer
0x1400a55c7  nop     dword ptr [rax+rax+00h]
0x1400a55cc  test    eax, eax
0x1400a55ce  js      short loc_1400A55F4
0x1400a55d0  mov     eax, [r13+1Ch]
0x1400a55d4  mov     dword ptr [rsp+0B8h+var_70+8], eax
0x1400a55d8  mov     rax, rdi
0x1400a55db  add     rax, rax
0x1400a55de  movups  xmm0, xmmword ptr [rsp+0B8h+var_70]
0x1400a55e3  movdqu  xmmword ptr [rsp+rax*8+0B8h+Src], xmm0
0x1400a55e9  inc     rdi
0x1400a55ec  mov     [rsp+0B8h+arg_18], rdi
0x1400a55f4  inc     esi
0x1400a55f6  cmp     esi, 2
0x1400a55f9  jl      loc_1400A5565
0x1400a55ff  test    rdi, rdi
0x1400a5602  jz      short loc_1400A5662
0x1400a5604  cmp     r15, rdi
0x1400a5607  jb      short loc_1400A565B
0x1400a5609  mov     rax, [rsp+0B8h+arg_10]
0x1400a5611  test    rax, rax
0x1400a5614  jz      short loc_1400A565B
0x1400a5616  mov     r8, rdi
0x1400a5619  shl     r8, 4; Size
0x1400a561d  lea     rdx, [rsp+0B8h+Src]; Src
0x1400a5622  mov     rcx, rax; void *
0x1400a5625  call    RtlCopyToUser
0x1400a562a  jmp     short loc_1400A5662
0x1400a562c  mov     esi, eax
0x1400a562e  mov     r8d, 133h
0x1400a5634  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a563b  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a5642  call    VidTraceErrorInternal0
0x1400a5647  xor     ebx, ebx
0x1400a5649  mov     r14, [rsp+0B8h+arg_8]
0x1400a5651  mov     rdi, [rsp+0B8h+arg_18]
0x1400a5659  jmp     short loc_1400A568D
0x1400a565b  mov     esi, 0C0000023h
0x1400a5660  jmp     short loc_1400A568D
0x1400a5662  mov     esi, ebx
0x1400a5664  jmp     short loc_1400A568D
0x1400a5666  mov     esi, eax
0x1400a5668  mov     r8d, 0D4h
0x1400a566e  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a5675  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a567c  call    VidTraceErrorInternal0
0x1400a5681  xor     ebx, ebx
0x1400a5683  mov     r14, [rsp+0B8h+arg_8]
0x1400a568b  mov     edi, ebx
0x1400a568d  nop
0x1400a568e  mov     rdx, rdi
0x1400a5691  mov     rcx, r14
0x1400a5694  call    RtlWriteULong64ToUser
0x1400a5699  jmp     short loc_1400A56C0
0x1400a569b  mov     esi, eax
0x1400a569d  mov     r8d, 14Fh
0x1400a56a3  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a56aa  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a56b1  call    VidTraceErrorInternal0
0x1400a56b6  xor     ebx, ebx
0x1400a56b8  mov     rdi, [rsp+0B8h+arg_18]
0x1400a56c0  test    esi, esi
0x1400a56c2  jns     short loc_1400A56E8
0x1400a56c4  test    rdi, rdi
0x1400a56c7  jz      short loc_1400A56E8
0x1400a56c9  mov     rcx, rbx
0x1400a56cc  add     rcx, rcx
0x1400a56cf  mov     rcx, [rsp+rcx*8+0B8h+Src]; Handle
0x1400a56d4  call    cs:__imp_NtClose
0x1400a56db  nop     dword ptr [rax+rax+00h]
0x1400a56e0  inc     rbx
0x1400a56e3  cmp     rbx, rdi
0x1400a56e6  jb      short loc_1400A56C9
0x1400a56e8  mov     eax, esi
0x1400a56ea  add     rsp, 80h
0x1400a56f1  pop     r15
0x1400a56f3  pop     r14
0x1400a56f5  pop     r13
0x1400a56f7  pop     r12
0x1400a56f9  pop     rdi
0x1400a56fa  pop     rsi
0x1400a56fb  pop     rbx
0x1400a56fc  retn
```
