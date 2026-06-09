# Srv2RegisterEndpoint

- ea: `0x14008c8a0`
- end: `0x14008cc14`
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
- `0x14008c8a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008c908`
- `ntoskrnl!ExAllocatePool2` at `0x14008c908`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009b949`
- `ntoskrnl!ExDeleteResourceLite` at `0x14009b949`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008caeb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009b939`
- `ntoskrnl!ExReleaseResourceLite` at `0x14008caeb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009b939`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008ca80`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14008ca80`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008c94e`
- `ntoskrnl!ExInitializeResourceLite` at `0x14008c94e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008c961`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008c961`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b963`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b963`

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
0x14008c8a0  push    rbx
0x14008c8a2  push    rbp
0x14008c8a3  push    rsi
0x14008c8a4  push    rdi
0x14008c8a5  push    r12
0x14008c8a7  push    r13
0x14008c8a9  push    r14
0x14008c8ab  push    r15
0x14008c8ad  sub     rsp, 68h
0x14008c8b1  mov     rsi, r9
0x14008c8b4  mov     r14, r8
0x14008c8b7  mov     r15, rdx
0x14008c8ba  mov     rdi, rcx
0x14008c8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c8c4  lea     rax, WPP_GLOBAL_Control
0x14008c8cb  movzx   ebp, [rsp+0A8h+arg_30]
0x14008c8d3  mov     r13d, 1
0x14008c8d9  cmp     rcx, rax
0x14008c8dc  jnz     loc_14008CB3F
0x14008c8e2  movzx   ecx, word ptr [r15]
0x14008c8e6  mov     r8d, 6532534Ch
0x14008c8ec  movzx   eax, word ptr [r14]
0x14008c8f0  movzx   r12d, word ptr [rsi]
0x14008c8f4  add     ecx, eax
0x14008c8f6  add     r12d, 130h
0x14008c8fd  add     r12d, ecx
0x14008c900  mov     ecx, 40h ; '@'
0x14008c905  mov     edx, r12d
0x14008c908  call    cs:__imp_ExAllocatePool2
0x14008c90f  nop     dword ptr [rax+rax+00h]
0x14008c914  mov     rbx, rax
0x14008c917  test    rax, rax
0x14008c91a  jz      loc_14008CB28
0x14008c920  mov     [rax], r13
0x14008c923  lea     rcx, [rax+60h]; Resource
0x14008c927  mov     [rax+8], r13d
0x14008c92b  mov     dword ptr [rax+0Ch], 0DCh
0x14008c932  mov     [rax+10h], r12w
0x14008c937  mov     qword ptr [rax+30h], 0
0x14008c93f  mov     [rax+38h], rax
0x14008c943  mov     [rax+40h], rdi
0x14008c947  mov     dword ptr [rax+48h], 0
0x14008c94e  call    cs:__imp_ExInitializeResourceLite
0x14008c955  nop     dword ptr [rax+rax+00h]
0x14008c95a  lea     rcx, [rbx+0C8h]; SpinLock
0x14008c961  call    cs:__imp_KeInitializeSpinLock
0x14008c968  nop     dword ptr [rax+rax+00h]
0x14008c96d  lea     rax, [rbx+0D0h]
0x14008c974  mov     rcx, rdi
0x14008c977  mov     [rax+8], rax
0x14008c97b  mov     [rax], rax
0x14008c97e  lea     rax, [rbx+0E0h]
0x14008c985  mov     [rax+8], rax
0x14008c989  mov     [rax], rax
0x14008c98c  call    Srv2ReferenceInstance
0x14008c991  mov     [rbx+120h], bpl
0x14008c998  lea     rcx, [rbx+130h]; void *
0x14008c99f  movzx   eax, word ptr [r15]
0x14008c9a3  mov     [rbx+0F0h], ax
0x14008c9aa  movzx   eax, word ptr [r15]
0x14008c9ae  mov     [rbx+0F2h], ax
0x14008c9b5  mov     [rbx+0F8h], rcx
0x14008c9bc  movzx   r8d, word ptr [r15]; Size
0x14008c9c0  mov     rdx, [r15+8]; Src
0x14008c9c4  call    memmove
0x14008c9c9  movzx   eax, word ptr [r14]
0x14008c9cd  movzx   ecx, word ptr [rbx+0F0h]
0x14008c9d4  mov     [rbx+100h], ax
0x14008c9db  movzx   eax, word ptr [r14]
0x14008c9df  mov     [rbx+102h], ax
0x14008c9e6  mov     rax, [rbx+0F8h]
0x14008c9ed  shr     rcx, 1
0x14008c9f0  lea     rcx, [rax+rcx*2]; void *
0x14008c9f4  mov     [rbx+108h], rcx
0x14008c9fb  movzx   r8d, word ptr [r14]; Size
0x14008c9ff  mov     rdx, [r14+8]; Src
0x14008ca03  call    memmove
0x14008ca08  movzx   eax, word ptr [rsi]
0x14008ca0b  movzx   ecx, word ptr [rbx+100h]
0x14008ca12  mov     [rbx+110h], ax
0x14008ca19  movzx   eax, word ptr [rsi]
0x14008ca1c  mov     [rbx+112h], ax
0x14008ca23  mov     rax, [rbx+108h]
0x14008ca2a  shr     rcx, 1
0x14008ca2d  lea     rcx, [rax+rcx*2]; void *
0x14008ca31  mov     [rbx+118h], rcx
0x14008ca38  movzx   r8d, word ptr [rsi]; Size
0x14008ca3c  mov     rdx, [rsi+8]; Src
0x14008ca40  call    memmove
0x14008ca45  test    byte ptr [rsp+0A8h+arg_28], 2
0x14008ca4d  jnz     loc_14008CBC5
0x14008ca53  test    dword ptr [rsp+0A8h+arg_28], 1000h
0x14008ca5e  jz      loc_14008CB14
0x14008ca64  mov     [rbx+121h], r13b
0x14008ca6b  mov     eax, 10000h
0x14008ca70  lea     r12, [rdi+10h]
0x14008ca74  mov     [rbx+124h], eax
0x14008ca7a  mov     rcx, r12; Resource
0x14008ca7d  mov     dl, r13b; Wait
0x14008ca80  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14008ca87  nop     dword ptr [rax+rax+00h]
0x14008ca8c  cmp     cs:Srv2DriverState, r13d
0x14008ca93  jnz     loc_14008CB1E
0x14008ca99  call    Srv2ReferenceDriverUnsafe
0x14008ca9e  test    eax, eax
0x14008caa0  js      loc_14009B8EA
0x14008caa6  lea     rcx, [rdi+78h]
0x14008caaa  mov     rdx, [rcx+8]
0x14008caae  cmp     [rdx], rcx
0x14008cab1  jnz     loc_14008CBD1
0x14008cab7  lea     rax, [rbx+50h]
0x14008cabb  mov     [rax], rcx
0x14008cabe  mov     [rax+8], rdx
0x14008cac2  mov     [rdx], rax
0x14008cac5  mov     [rcx+8], rax
0x14008cac9  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cad0  lea     rax, WPP_GLOBAL_Control
0x14008cad7  cmp     rcx, rax
0x14008cada  jz      short loc_14008CAE8
0x14008cadc  mov     eax, [rcx+2Ch]
0x14008cadf  test    r13b, al
0x14008cae2  jnz     loc_14008CBD8
0x14008cae8  mov     rcx, r12; Resource
0x14008caeb  call    cs:__imp_ExReleaseResourceLite
0x14008caf2  nop     dword ptr [rax+rax+00h]
0x14008caf7  mov     rcx, rbx
0x14008cafa  call    Srv2ReferenceConnection
0x14008caff  mov     rax, rbx
0x14008cb02  add     rsp, 68h
0x14008cb06  pop     r15
0x14008cb08  pop     r14
0x14008cb0a  pop     r13
0x14008cb0c  pop     r12
0x14008cb0e  pop     rdi
0x14008cb0f  pop     rsi
0x14008cb10  pop     rbp
0x14008cb11  pop     rbx
0x14008cb12  retn
0x14008cb14  call    Smb2GetMaxLargeMtuReadWriteSize
0x14008cb19  jmp     loc_14008CA70
0x14008cb1e  call    Srv2ReferenceDriver
0x14008cb23  jmp     loc_14008CA9E
0x14008cb28  mov     rcx, cs:WPP_GLOBAL_Control
0x14008cb2f  lea     rax, WPP_GLOBAL_Control
0x14008cb36  cmp     rcx, rax
0x14008cb39  jnz     short loc_14008CB86
0x14008cb3b  xor     eax, eax
0x14008cb3d  jmp     short loc_14008CB02
0x14008cb3f  mov     eax, [rcx+2Ch]
0x14008cb42  test    r13b, al
0x14008cb45  jz      loc_14008C8E2
0x14008cb4b  cmp     byte ptr [rcx+29h], 2
0x14008cb4f  jb      loc_14008C8E2
0x14008cb55  movzx   eax, byte ptr [rdi]
0x14008cb58  mov     r9d, ebp
0x14008cb5b  mov     rcx, [rcx+18h]
0x14008cb5f  mov     edx, 0Ah
0x14008cb64  mov     dword ptr [rsp+0A8h+var_68], eax
0x14008cb68  mov     [rsp+0A8h+var_70], rdi
0x14008cb6d  mov     [rsp+0A8h+var_78], rsi
0x14008cb72  mov     [rsp+0A8h+var_80], r14
0x14008cb77  mov     [rsp+0A8h+var_88], r15
0x14008cb7c  call    WPP_SF_dZZZqd
0x14008cb81  jmp     loc_14008C8E2
0x14008cb86  mov     eax, [rcx+2Ch]
0x14008cb89  test    r13b, al
0x14008cb8c  jz      short loc_14008CB3B
0x14008cb8e  cmp     byte ptr [rcx+29h], 2
0x14008cb92  jb      short loc_14008CB3B
0x14008cb94  movzx   eax, byte ptr [rdi]
0x14008cb97  mov     r9d, ebp
0x14008cb9a  mov     rcx, [rcx+18h]
0x14008cb9e  mov     edx, 0Bh
0x14008cba3  mov     dword ptr [rsp+0A8h+var_68], eax
0x14008cba7  mov     [rsp+0A8h+var_70], rdi
0x14008cbac  mov     [rsp+0A8h+var_78], rsi
0x14008cbb1  mov     [rsp+0A8h+var_80], r14
0x14008cbb6  mov     [rsp+0A8h+var_88], r15
0x14008cbbb  call    WPP_SF_dZZZqd
0x14008cbc0  jmp     loc_14008CB3B
0x14008cbc5  mov     [rbx+128h], r13d
0x14008cbcc  jmp     loc_14008CA53
0x14008cbd1  mov     ecx, 3
0x14008cbd6  int     29h; Win8: RtlFailFast(ecx)
0x14008cbd8  cmp     byte ptr [rcx+29h], 2
0x14008cbdc  jb      loc_14008CAE8
0x14008cbe2  movzx   eax, byte ptr [rdi]
0x14008cbe5  mov     rcx, [rcx+18h]
0x14008cbe9  mov     [rsp+0A8h+var_58], eax
0x14008cbed  mov     [rsp+0A8h+var_60], rdi
0x14008cbf2  mov     [rsp+0A8h+var_68], rsi
0x14008cbf7  mov     [rsp+0A8h+var_70], r14
0x14008cbfc  mov     [rsp+0A8h+var_78], r15
0x14008cc01  mov     dword ptr [rsp+0A8h+var_80], ebp
0x14008cc05  mov     [rsp+0A8h+var_88], rbx
0x14008cc0a  call    WPP_SF_dqdZZZqd
0x14008cc0f  jmp     loc_14008CAE8
0x14009b8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b8f1  lea     rax, WPP_GLOBAL_Control
0x14009b8f8  cmp     rcx, rax
0x14009b8fb  jz      short loc_14009B936
0x14009b8fd  mov     eax, [rcx+2Ch]
0x14009b900  test    r13b, al
0x14009b903  jz      short loc_14009B936
0x14009b905  cmp     [rcx+29h], r13b
0x14009b909  jb      short loc_14009B936
0x14009b90b  movzx   eax, byte ptr [rdi]
0x14009b90e  mov     r9, rbx
0x14009b911  mov     rcx, [rcx+18h]
0x14009b915  mov     dword ptr [rsp+0A8h+var_60], eax
0x14009b919  mov     [rsp+0A8h+var_68], rdi
0x14009b91e  mov     [rsp+0A8h+var_70], rsi
0x14009b923  mov     [rsp+0A8h+var_78], r14
0x14009b928  mov     [rsp+0A8h+var_80], r15
0x14009b92d  mov     dword ptr [rsp+0A8h+var_88], ebp
0x14009b931  call    WPP_SF_qdZZZqd
0x14009b936  mov     rcx, r12; Resource
0x14009b939  call    cs:__imp_ExReleaseResourceLite
0x14009b940  nop     dword ptr [rax+rax+00h]
0x14009b945  lea     rcx, [rbx+60h]; Resource
0x14009b949  call    cs:__imp_ExDeleteResourceLite
0x14009b950  nop     dword ptr [rax+rax+00h]
0x14009b955  mov     rcx, [rbx+40h]; Context
0x14009b959  call    Srv2DereferenceInstance
0x14009b95e  xor     edx, edx; Tag
0x14009b960  mov     rcx, rbx; P
0x14009b963  call    cs:__imp_ExFreePoolWithTag
0x14009b96a  nop     dword ptr [rax+rax+00h]
0x14009b96f  xor     ebx, ebx
0x14009b971  jmp     loc_14008CAFF
```
