# Srv2RegisterEndpoint

- ea: `0x14008c850`
- end: `0x14008cbc4`
- name: `Srv2RegisterEndpoint`
- size: `884`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x14000c450`
- `0x140015000`
- `0x14001ab44`
- `0x14001b348`
- `0x14001b4e8`
- `0x140020170`
- `0x14002396c`
- `0x140023c68`
- `0x140023e80`
- `0x140038680`
- `0x14008c850`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008c8b8`
- `ntoskrnl!ExAllocatePool2` at `0x14008c8b8`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009b8f9`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009b8f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008ca9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009b8e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008ca9b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009b8e9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008ca30`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008ca30`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008c8fe`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008c8fe`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008c911`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008c911`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b913`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b913`

## pseudocode

```c
__int64 __fastcall Srv2RegisterEndpoint(
        __int64 a1,
        const void **a2,
        const void **a3,
        const void **a4,
        int a5,
        __int16 a6,
        unsigned __int8 a7)
{
  unsigned int v11; // r12d
  __int64 Pool2; // rax
  int v13; // r8d
  __int64 v14; // rbx
  unsigned __int64 v15; // rcx
  void *v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  _QWORD *v24; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_dZZZqd(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      (_DWORD)a3,
      a7,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4,
      a1,
      *(_BYTE *)a1);
  }
  v11 = *(unsigned __int16 *)a3 + *(unsigned __int16 *)a2 + *(unsigned __int16 *)a4 + 304;
  Pool2 = ExAllocatePool2(64, v11, 1697796940);
  v14 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 1;
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_DWORD *)(Pool2 + 12) = 220;
    *(_WORD *)(Pool2 + 16) = v11;
    *(_QWORD *)(Pool2 + 48) = 0;
    *(_QWORD *)(Pool2 + 56) = Pool2;
    *(_QWORD *)(Pool2 + 64) = a1;
    *(_DWORD *)(Pool2 + 72) = 0;
    ExInitializeResourceLite((PERESOURCE)(Pool2 + 96));
    KeInitializeSpinLock((PKSPIN_LOCK)(v14 + 200));
    *(_QWORD *)(v14 + 216) = v14 + 208;
    *(_QWORD *)(v14 + 208) = v14 + 208;
    *(_QWORD *)(v14 + 232) = v14 + 224;
    *(_QWORD *)(v14 + 224) = v14 + 224;
    Srv2ReferenceInstance(a1);
    *(_BYTE *)(v14 + 288) = a7;
    *(_WORD *)(v14 + 240) = *(_WORD *)a2;
    *(_WORD *)(v14 + 242) = *(_WORD *)a2;
    *(_QWORD *)(v14 + 248) = v14 + 304;
    memmove((void *)(v14 + 304), a2[1], *(unsigned __int16 *)a2);
    v15 = *(unsigned __int16 *)(v14 + 240);
    *(_WORD *)(v14 + 256) = *(_WORD *)a3;
    *(_WORD *)(v14 + 258) = *(_WORD *)a3;
    v16 = (void *)(*(_QWORD *)(v14 + 248) + 2 * (v15 >> 1));
    *(_QWORD *)(v14 + 264) = v16;
    memmove(v16, a3[1], *(unsigned __int16 *)a3);
    v17 = *(unsigned __int16 *)(v14 + 256);
    *(_WORD *)(v14 + 272) = *(_WORD *)a4;
    *(_WORD *)(v14 + 274) = *(_WORD *)a4;
    v18 = (void *)(*(_QWORD *)(v14 + 264) + 2 * (v17 >> 1));
    *(_QWORD *)(v14 + 280) = v18;
    memmove(v18, a4[1], *(unsigned __int16 *)a4);
    if ( (a6 & 2) != 0 )
      *(_DWORD *)(v14 + 296) = 1;
    if ( (a6 & 0x1000) != 0 )
    {
      *(_BYTE *)(v14 + 289) = 1;
      v19 = 0x10000;
    }
    else
    {
      v19 = Smb2GetMaxLargeMtuReadWriteSize();
    }
    *(_DWORD *)(v14 + 292) = v19;
    ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 16), 1u);
    if ( Srv2DriverState == 1 )
      v20 = Srv2ReferenceDriverUnsafe();
    else
      v20 = Srv2ReferenceDriver();
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qdZZZqd(
          WPP_GLOBAL_Control->AttachedDevice,
          v21,
          v22,
          v14,
          a7,
          (__int64)a2,
          (__int64)a3,
          (__int64)a4,
          a1,
          *(_BYTE *)a1);
      }
      ExReleaseResourceLite((PERESOURCE)(a1 + 16));
      ExDeleteResourceLite((PERESOURCE)(v14 + 96));
      Srv2DereferenceInstance(*(PVOID *)(v14 + 64));
      ExFreePoolWithTag((PVOID)v14, 0);
      return 0;
    }
    else
    {
      v24 = *(_QWORD **)(a1 + 128);
      if ( *v24 != a1 + 120 )
        __fastfail(3u);
      *(_QWORD *)(v14 + 80) = a1 + 120;
      *(_QWORD *)(v14 + 88) = v24;
      *v24 = v14 + 80;
      *(_QWORD *)(a1 + 128) = v14 + 80;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_dqdZZZqd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v24,
          v22,
          v23,
          v14,
          a7,
          (__int64)a2,
          (__int64)a3,
          (__int64)a4,
          a1,
          *(_BYTE *)a1);
      }
      ExReleaseResourceLite((PERESOURCE)(a1 + 16));
      Srv2ReferenceConnection(v14);
    }
    return v14;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dZZZqd(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        v13,
        a7,
        (__int64)a2,
        (__int64)a3,
        (__int64)a4,
        a1,
        *(_BYTE *)a1);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14008c850  push    rbx
0x14008c852  push    rbp
0x14008c853  push    rsi
0x14008c854  push    rdi
0x14008c855  push    r12
0x14008c857  push    r13
0x14008c859  push    r14
0x14008c85b  push    r15
0x14008c85d  sub     rsp, 68h
0x14008c861  mov     rsi, r9
0x14008c864  mov     r14, r8
0x14008c867  mov     r15, rdx
0x14008c86a  mov     rdi, rcx
0x14008c86d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c874  lea     rax, WPP_GLOBAL_Control
0x14008c87b  movzx   ebp, [rsp+0A8h+arg_30]
0x14008c883  mov     r13d, 1
0x14008c889  cmp     rcx, rax
0x14008c88c  jnz     loc_14008CAEF
0x14008c892  movzx   ecx, word ptr [r15]
0x14008c896  mov     r8d, 6532534Ch
0x14008c89c  movzx   eax, word ptr [r14]
0x14008c8a0  movzx   r12d, word ptr [rsi]
0x14008c8a4  add     ecx, eax
0x14008c8a6  add     r12d, 130h
0x14008c8ad  add     r12d, ecx
0x14008c8b0  mov     ecx, 40h ; '@'
0x14008c8b5  mov     edx, r12d
0x14008c8b8  call    cs:__imp_ExAllocatePool2
0x14008c8bf  nop     dword ptr [rax+rax+00h]
0x14008c8c4  mov     rbx, rax
0x14008c8c7  test    rax, rax
0x14008c8ca  jz      loc_14008CAD8
0x14008c8d0  mov     [rax], r13
0x14008c8d3  lea     rcx, [rax+60h]; Resource
0x14008c8d7  mov     [rax+8], r13d
0x14008c8db  mov     dword ptr [rax+0Ch], 0DCh
0x14008c8e2  mov     [rax+10h], r12w
0x14008c8e7  mov     qword ptr [rax+30h], 0
0x14008c8ef  mov     [rax+38h], rax
0x14008c8f3  mov     [rax+40h], rdi
0x14008c8f7  mov     dword ptr [rax+48h], 0
0x14008c8fe  call    cs:__imp_ExInitializeResourceLite
0x14008c905  nop     dword ptr [rax+rax+00h]
0x14008c90a  lea     rcx, [rbx+0C8h]; SpinLock
0x14008c911  call    cs:__imp_KeInitializeSpinLock
0x14008c918  nop     dword ptr [rax+rax+00h]
0x14008c91d  lea     rax, [rbx+0D0h]
0x14008c924  mov     rcx, rdi
0x14008c927  mov     [rax+8], rax
0x14008c92b  mov     [rax], rax
0x14008c92e  lea     rax, [rbx+0E0h]
0x14008c935  mov     [rax+8], rax
0x14008c939  mov     [rax], rax
0x14008c93c  call    Srv2ReferenceInstance
0x14008c941  mov     [rbx+120h], bpl
0x14008c948  lea     rcx, [rbx+130h]; void *
0x14008c94f  movzx   eax, word ptr [r15]
0x14008c953  mov     [rbx+0F0h], ax
0x14008c95a  movzx   eax, word ptr [r15]
0x14008c95e  mov     [rbx+0F2h], ax
0x14008c965  mov     [rbx+0F8h], rcx
0x14008c96c  movzx   r8d, word ptr [r15]; Size
0x14008c970  mov     rdx, [r15+8]; Src
0x14008c974  call    memmove
0x14008c979  movzx   eax, word ptr [r14]
0x14008c97d  movzx   ecx, word ptr [rbx+0F0h]
0x14008c984  mov     [rbx+100h], ax
0x14008c98b  movzx   eax, word ptr [r14]
0x14008c98f  mov     [rbx+102h], ax
0x14008c996  mov     rax, [rbx+0F8h]
0x14008c99d  shr     rcx, 1
0x14008c9a0  lea     rcx, [rax+rcx*2]; void *
0x14008c9a4  mov     [rbx+108h], rcx
0x14008c9ab  movzx   r8d, word ptr [r14]; Size
0x14008c9af  mov     rdx, [r14+8]; Src
0x14008c9b3  call    memmove
0x14008c9b8  movzx   eax, word ptr [rsi]
0x14008c9bb  movzx   ecx, word ptr [rbx+100h]
0x14008c9c2  mov     [rbx+110h], ax
0x14008c9c9  movzx   eax, word ptr [rsi]
0x14008c9cc  mov     [rbx+112h], ax
0x14008c9d3  mov     rax, [rbx+108h]
0x14008c9da  shr     rcx, 1
0x14008c9dd  lea     rcx, [rax+rcx*2]; void *
0x14008c9e1  mov     [rbx+118h], rcx
0x14008c9e8  movzx   r8d, word ptr [rsi]; Size
0x14008c9ec  mov     rdx, [rsi+8]; Src
0x14008c9f0  call    memmove
0x14008c9f5  test    byte ptr [rsp+0A8h+arg_28], 2
0x14008c9fd  jnz     loc_14008CB75
0x14008ca03  test    dword ptr [rsp+0A8h+arg_28], 1000h
0x14008ca0e  jz      loc_14008CAC4
0x14008ca14  mov     [rbx+121h], r13b
0x14008ca1b  mov     eax, 10000h
0x14008ca20  lea     r12, [rdi+10h]
0x14008ca24  mov     [rbx+124h], eax
0x14008ca2a  mov     rcx, r12; Resource
0x14008ca2d  mov     dl, r13b; Wait
0x14008ca30  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14008ca37  nop     dword ptr [rax+rax+00h]
0x14008ca3c  cmp     cs:Srv2DriverState, r13d
0x14008ca43  jnz     loc_14008CACE
0x14008ca49  call    Srv2ReferenceDriverUnsafe
0x14008ca4e  test    eax, eax
0x14008ca50  js      loc_14009B89A
0x14008ca56  lea     rcx, [rdi+78h]
0x14008ca5a  mov     rdx, [rcx+8]
0x14008ca5e  cmp     [rdx], rcx
0x14008ca61  jnz     loc_14008CB81
0x14008ca67  lea     rax, [rbx+50h]
0x14008ca6b  mov     [rax], rcx
0x14008ca6e  mov     [rax+8], rdx
0x14008ca72  mov     [rdx], rax
0x14008ca75  mov     [rcx+8], rax
0x14008ca79  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ca80  lea     rax, WPP_GLOBAL_Control
0x14008ca87  cmp     rcx, rax
0x14008ca8a  jz      short loc_14008CA98
0x14008ca8c  mov     eax, [rcx+2Ch]
0x14008ca8f  test    r13b, al
0x14008ca92  jnz     loc_14008CB88
0x14008ca98  mov     rcx, r12; Resource
0x14008ca9b  call    cs:__imp_ExReleaseResourceLite
0x14008caa2  nop     dword ptr [rax+rax+00h]
0x14008caa7  mov     rcx, rbx
0x14008caaa  call    Srv2ReferenceConnection
0x14008caaf  mov     rax, rbx
0x14008cab2  add     rsp, 68h
0x14008cab6  pop     r15
0x14008cab8  pop     r14
0x14008caba  pop     r13
0x14008cabc  pop     r12
0x14008cabe  pop     rdi
0x14008cabf  pop     rsi
0x14008cac0  pop     rbp
0x14008cac1  pop     rbx
0x14008cac2  retn
0x14008cac4  call    Smb2GetMaxLargeMtuReadWriteSize
0x14008cac9  jmp     loc_14008CA20
0x14008cace  call    Srv2ReferenceDriver
0x14008cad3  jmp     loc_14008CA4E
0x14008cad8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cadf  lea     rax, WPP_GLOBAL_Control
0x14008cae6  cmp     rcx, rax
0x14008cae9  jnz     short loc_14008CB36
0x14008caeb  xor     eax, eax
0x14008caed  jmp     short loc_14008CAB2
0x14008caef  mov     eax, [rcx+2Ch]
0x14008caf2  test    r13b, al
0x14008caf5  jz      loc_14008C892
0x14008cafb  cmp     byte ptr [rcx+29h], 2
0x14008caff  jb      loc_14008C892
0x14008cb05  movzx   eax, byte ptr [rdi]
0x14008cb08  mov     r9d, ebp
0x14008cb0b  mov     rcx, [rcx+18h]
0x14008cb0f  mov     edx, 0Ah
0x14008cb14  mov     dword ptr [rsp+0A8h+var_68], eax
0x14008cb18  mov     [rsp+0A8h+var_70], rdi
0x14008cb1d  mov     [rsp+0A8h+var_78], rsi
0x14008cb22  mov     [rsp+0A8h+var_80], r14
0x14008cb27  mov     [rsp+0A8h+var_88], r15
0x14008cb2c  call    WPP_SF_dZZZqd
0x14008cb31  jmp     loc_14008C892
0x14008cb36  mov     eax, [rcx+2Ch]
0x14008cb39  test    r13b, al
0x14008cb3c  jz      short loc_14008CAEB
0x14008cb3e  cmp     byte ptr [rcx+29h], 2
0x14008cb42  jb      short loc_14008CAEB
0x14008cb44  movzx   eax, byte ptr [rdi]
0x14008cb47  mov     r9d, ebp
0x14008cb4a  mov     rcx, [rcx+18h]
0x14008cb4e  mov     edx, 0Bh
0x14008cb53  mov     dword ptr [rsp+0A8h+var_68], eax
0x14008cb57  mov     [rsp+0A8h+var_70], rdi
0x14008cb5c  mov     [rsp+0A8h+var_78], rsi
0x14008cb61  mov     [rsp+0A8h+var_80], r14
0x14008cb66  mov     [rsp+0A8h+var_88], r15
0x14008cb6b  call    WPP_SF_dZZZqd
0x14008cb70  jmp     loc_14008CAEB
0x14008cb75  mov     [rbx+128h], r13d
0x14008cb7c  jmp     loc_14008CA03
0x14008cb81  mov     ecx, 3
0x14008cb86  int     29h; Win8: RtlFailFast(ecx)
0x14008cb88  cmp     byte ptr [rcx+29h], 2
0x14008cb8c  jb      loc_14008CA98
0x14008cb92  movzx   eax, byte ptr [rdi]
0x14008cb95  mov     rcx, [rcx+18h]
0x14008cb99  mov     [rsp+0A8h+var_58], eax
0x14008cb9d  mov     [rsp+0A8h+var_60], rdi
0x14008cba2  mov     [rsp+0A8h+var_68], rsi
0x14008cba7  mov     [rsp+0A8h+var_70], r14
0x14008cbac  mov     [rsp+0A8h+var_78], r15
0x14008cbb1  mov     dword ptr [rsp+0A8h+var_80], ebp
0x14008cbb5  mov     [rsp+0A8h+var_88], rbx
0x14008cbba  call    WPP_SF_dqdZZZqd
0x14008cbbf  jmp     loc_14008CA98
0x14009b89a  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b8a1  lea     rax, WPP_GLOBAL_Control
0x14009b8a8  cmp     rcx, rax
0x14009b8ab  jz      short loc_14009B8E6
0x14009b8ad  mov     eax, [rcx+2Ch]
0x14009b8b0  test    r13b, al
0x14009b8b3  jz      short loc_14009B8E6
0x14009b8b5  cmp     [rcx+29h], r13b
0x14009b8b9  jb      short loc_14009B8E6
0x14009b8bb  movzx   eax, byte ptr [rdi]
0x14009b8be  mov     r9, rbx
0x14009b8c1  mov     rcx, [rcx+18h]
0x14009b8c5  mov     dword ptr [rsp+0A8h+var_60], eax
0x14009b8c9  mov     [rsp+0A8h+var_68], rdi
0x14009b8ce  mov     [rsp+0A8h+var_70], rsi
0x14009b8d3  mov     [rsp+0A8h+var_78], r14
0x14009b8d8  mov     [rsp+0A8h+var_80], r15
0x14009b8dd  mov     dword ptr [rsp+0A8h+var_88], ebp
0x14009b8e1  call    WPP_SF_qdZZZqd
0x14009b8e6  mov     rcx, r12; Resource
0x14009b8e9  call    cs:__imp_ExReleaseResourceLite
0x14009b8f0  nop     dword ptr [rax+rax+00h]
0x14009b8f5  lea     rcx, [rbx+60h]; Resource
0x14009b8f9  call    cs:__imp_ExDeleteResourceLite
0x14009b900  nop     dword ptr [rax+rax+00h]
0x14009b905  mov     rcx, [rbx+40h]; Context
0x14009b909  call    Srv2DereferenceInstance
0x14009b90e  xor     edx, edx; Tag
0x14009b910  mov     rcx, rbx; P
0x14009b913  call    cs:__imp_ExFreePoolWithTag
0x14009b91a  nop     dword ptr [rax+rax+00h]
0x14009b91f  xor     ebx, ebx
0x14009b921  jmp     loc_14008CAAF
```
