# VhdmpiQueryPowerRelations(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b7920`
- end: `0x1400b7b32`
- name: `?VhdmpiQueryPowerRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400b7bbc`

## callees

- `0x14001df30`
- `0x14001f58c`
- `0x14002227c`
- `0x140026344`
- `0x140026510`
- `0x140034054`
- `0x14005dd00`
- `0x1400b65b8`
- `0x1400b7920`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400b7aac`
- `ntoskrnl!ObfReferenceObject` at `0x1400b7aac`
- `ntoskrnl!IofCompleteRequest` at `0x1400b7b12`
- `ntoskrnl!IofCompleteRequest` at `0x1400b7b12`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7af7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7af7`
- `ntoskrnl!ExAllocatePool2` at `0x1400b79af`
- `ntoskrnl!ExAllocatePool2` at `0x1400b79af`

## pseudocode

```c
__int64 __fastcall VhdmpiQueryPowerRelations(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  __int64 v4; // rax
  __int64 v5; // r13
  NTSTATUS v6; // ebx
  __int64 v7; // rbp
  __int64 v8; // r12
  __int64 v9; // rax
  int v10; // ecx
  _DWORD *Pool2; // rdi
  __int64 v12; // rbp
  __int64 v13; // rsi
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  void *v16; // r15
  __int64 v17; // rcx
  _DWORD v19[38]; // [rsp+20h] [rbp-98h] BYREF
  PVOID P; // [rsp+C8h] [rbp+10h] BYREF

  memset(v19, 0, 0x48u);
  P = 0;
  v4 = VhdmpiAddRundownRefSurfaceByPdo(a1);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -1073741823;
LABEL_26:
    Pool2 = 0;
    goto LABEL_27;
  }
  v7 = *(_QWORD *)(v4 + 16);
  v8 = v7 + 128;
  VhdmpiAcquirePassiveLockShared(v7 + 128);
  v9 = *(_QWORD *)(v7 + 144);
  v10 = 0;
  while ( v9 )
  {
    v9 = *(_QWORD *)(v9 + 1144);
    ++v10;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(256, (unsigned int)(336 * v10 + 8), 1682196566);
  if ( Pool2 )
  {
    v12 = *(_QWORD *)(v7 + 144);
    v6 = 0;
    v13 = 0;
    while ( v12 )
    {
      v14 = *(unsigned int *)(v12 + 596);
      if ( (unsigned int)v14 <= 0x24 )
      {
        v15 = 0x1080000084LL;
        if ( _bittest64(&v15, v14) )
        {
          memset(v19, 0, 0x48u);
          LOWORD(v19[0]) = 1819;
          v19[2] = 4;
          if ( (__int64 *)v12 == &VhdmpiEmptyISOBackingStore )
          {
            v6 = -1073741823;
            goto LABEL_23;
          }
          v6 = VhdmpiFileWrapperPinFile(v12 + 72, 0, 0, 0);
          if ( v6 < 0 )
            goto LABEL_23;
          v6 = VhdmpiSendPnpIrp(*(_QWORD *)(v12 + 600), v19, &P);
          VhdmpiFileWrapperUnpinFile(v12 + 72, 0);
          if ( v6 < 0 )
            goto LABEL_23;
          v16 = (void *)*((_QWORD *)P + 1);
          ExFreePoolWithTag(P, 0);
          v17 = 0;
          if ( (_DWORD)v13 )
          {
            while ( *(void **)&Pool2[2 * v17 + 2] != v16 )
            {
              v17 = (unsigned int)(v17 + 1);
              if ( (unsigned int)v17 >= (unsigned int)v13 )
                goto LABEL_18;
            }
          }
          else
          {
LABEL_18:
            if ( (_DWORD)v17 == (_DWORD)v13 )
            {
              ObfReferenceObject(v16);
              *(_QWORD *)&Pool2[2 * v13 + 2] = v16;
              v13 = (unsigned int)(v13 + 1);
            }
          }
        }
      }
      v12 = *(_QWORD *)(v12 + 1144);
    }
    *Pool2 = v13;
  }
  else
  {
    v6 = -1073741670;
  }
LABEL_23:
  VhdmpiReleasePassiveLockShared(v8);
  VhdmpiReleaseRundownRefVirtualDiskSurface(v5, 0);
  if ( v6 < 0 && Pool2 )
  {
    ExFreePoolWithTag(Pool2, 0x64444856u);
    goto LABEL_26;
  }
LABEL_27:
  Irp->IoStatus.Information = (ULONG_PTR)Pool2;
  Irp->IoStatus.Status = v6;
  IofCompleteRequest(Irp, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400b7920  push    rbx
0x1400b7922  push    rbp
0x1400b7923  push    rsi
0x1400b7924  push    rdi
0x1400b7925  push    r12
0x1400b7927  push    r13
0x1400b7929  push    r14
0x1400b792b  push    r15
0x1400b792d  sub     rsp, 78h
0x1400b7931  mov     r14, rdx
0x1400b7934  mov     rbx, rcx
0x1400b7937  xor     edx, edx; Val
0x1400b7939  lea     rcx, [rsp+0B8h+var_98]; void *
0x1400b793e  lea     r8d, [rdx+48h]; Size
0x1400b7942  call    memset
0x1400b7947  xor     edx, edx
0x1400b7949  mov     [rsp+0B8h+P], 0
0x1400b7955  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x1400b7958  call    VhdmpiAddRundownRefSurfaceByPdo
0x1400b795d  mov     r13, rax
0x1400b7960  test    rax, rax
0x1400b7963  jnz     short loc_1400B796F
0x1400b7965  mov     ebx, 0C0000001h
0x1400b796a  jmp     loc_1400B7B03
0x1400b796f  mov     rbp, [rax+10h]
0x1400b7973  lea     r12, [rbp+80h]
0x1400b797a  mov     rcx, r12
0x1400b797d  call    VhdmpiAcquirePassiveLockShared
0x1400b7982  mov     rax, [rbp+90h]
0x1400b7989  xor     ecx, ecx
0x1400b798b  jmp     short loc_1400B7996
0x1400b798d  mov     rax, [rax+478h]
0x1400b7994  inc     ecx
0x1400b7996  test    rax, rax
0x1400b7999  jnz     short loc_1400B798D
0x1400b799b  imul    edx, ecx, 150h
0x1400b79a1  mov     r8d, 64444856h
0x1400b79a7  mov     ecx, 100h
0x1400b79ac  add     edx, 8
0x1400b79af  call    cs:__imp_ExAllocatePool2
0x1400b79b6  nop     dword ptr [rax+rax+00h]
0x1400b79bb  mov     rdi, rax
0x1400b79be  test    rax, rax
0x1400b79c1  jnz     short loc_1400B79CD
0x1400b79c3  mov     ebx, 0C000009Ah
0x1400b79c8  jmp     loc_1400B7AD4
0x1400b79cd  mov     rbp, [rbp+90h]
0x1400b79d4  xor     ebx, ebx
0x1400b79d6  xor     esi, esi
0x1400b79d8  test    rbp, rbp
0x1400b79db  jz      loc_1400B7AD2
0x1400b79e1  mov     eax, [rbp+254h]
0x1400b79e7  cmp     eax, 24h ; '$'
0x1400b79ea  ja      loc_1400B7ABF
0x1400b79f0  mov     rcx, 1080000084h
0x1400b79fa  bt      rcx, rax
0x1400b79fe  jnb     loc_1400B7ABF
0x1400b7a04  xor     edx, edx; Val
0x1400b7a06  lea     rcx, [rsp+0B8h+var_98]; void *
0x1400b7a0b  lea     r8d, [rdx+48h]; Size
0x1400b7a0f  call    memset
0x1400b7a14  lea     rax, VhdmpiEmptyISOBackingStore
0x1400b7a1b  mov     [rsp+0B8h+var_98], 71Bh
0x1400b7a22  mov     [rsp+0B8h+var_90], 4
0x1400b7a2a  cmp     rbp, rax
0x1400b7a2d  jz      loc_1400B7ACB
0x1400b7a33  xor     r9d, r9d
0x1400b7a36  lea     rcx, [rbp+48h]
0x1400b7a3a  xor     r8d, r8d
0x1400b7a3d  xor     edx, edx
0x1400b7a3f  call    VhdmpiFileWrapperPinFile
0x1400b7a44  mov     ebx, eax
0x1400b7a46  test    eax, eax
0x1400b7a48  js      loc_1400B7AD4
0x1400b7a4e  mov     rcx, [rbp+258h]
0x1400b7a55  lea     r8, [rsp+0B8h+P]
0x1400b7a5d  lea     rdx, [rsp+0B8h+var_98]
0x1400b7a62  call    VhdmpiSendPnpIrp
0x1400b7a67  xor     edx, edx
0x1400b7a69  lea     rcx, [rbp+48h]
0x1400b7a6d  mov     ebx, eax
0x1400b7a6f  call    VhdmpiFileWrapperUnpinFile
0x1400b7a74  test    ebx, ebx
0x1400b7a76  js      short loc_1400B7AD4
0x1400b7a78  mov     rcx, [rsp+0B8h+P]; P
0x1400b7a80  xor     edx, edx; Tag
0x1400b7a82  mov     r15, [rcx+8]
0x1400b7a86  call    cs:__imp_ExFreePoolWithTag
0x1400b7a8d  nop     dword ptr [rax+rax+00h]
0x1400b7a92  xor     ecx, ecx
0x1400b7a94  test    esi, esi
0x1400b7a96  jz      short loc_1400B7AA5
0x1400b7a98  cmp     [rdi+rcx*8+8], r15
0x1400b7a9d  jz      short loc_1400B7ABF
0x1400b7a9f  inc     ecx
0x1400b7aa1  cmp     ecx, esi
0x1400b7aa3  jb      short loc_1400B7A98
0x1400b7aa5  cmp     ecx, esi
0x1400b7aa7  jnz     short loc_1400B7ABF
0x1400b7aa9  mov     rcx, r15; Object
0x1400b7aac  call    cs:__imp_ObfReferenceObject
0x1400b7ab3  nop     dword ptr [rax+rax+00h]
0x1400b7ab8  mov     [rdi+rsi*8+8], r15
0x1400b7abd  inc     esi
0x1400b7abf  mov     rbp, [rbp+478h]
0x1400b7ac6  jmp     loc_1400B79D8
0x1400b7acb  mov     ebx, 0C0000001h
0x1400b7ad0  jmp     short loc_1400B7AD4
0x1400b7ad2  mov     [rdi], esi
0x1400b7ad4  mov     rcx, r12
0x1400b7ad7  call    VhdmpiReleasePassiveLockShared
0x1400b7adc  xor     edx, edx
0x1400b7ade  mov     rcx, r13
0x1400b7ae1  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b7ae6  test    ebx, ebx
0x1400b7ae8  jns     short loc_1400B7B05
0x1400b7aea  test    rdi, rdi
0x1400b7aed  jz      short loc_1400B7B05
0x1400b7aef  mov     edx, 64444856h; Tag
0x1400b7af4  mov     rcx, rdi; P
0x1400b7af7  call    cs:__imp_ExFreePoolWithTag
0x1400b7afe  nop     dword ptr [rax+rax+00h]
0x1400b7b03  xor     edi, edi
0x1400b7b05  xor     edx, edx; PriorityBoost
0x1400b7b07  mov     [r14+38h], rdi
0x1400b7b0b  mov     rcx, r14; Irp
0x1400b7b0e  mov     [r14+30h], ebx
0x1400b7b12  call    cs:__imp_IofCompleteRequest
0x1400b7b19  nop     dword ptr [rax+rax+00h]
0x1400b7b1e  mov     eax, ebx
0x1400b7b20  add     rsp, 78h
0x1400b7b24  pop     r15
0x1400b7b26  pop     r14
0x1400b7b28  pop     r13
0x1400b7b2a  pop     r12
0x1400b7b2c  pop     rdi
0x1400b7b2d  pop     rsi
0x1400b7b2e  pop     rbp
0x1400b7b2f  pop     rbx
0x1400b7b30  retn
```
