# VhdmpiQueryPowerRelations(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400b7908`
- end: `0x1400b7b1a`
- name: `?VhdmpiQueryPowerRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400b7ba4`

## callees

- `0x14001e350`
- `0x14001f9ac`
- `0x14002269c`
- `0x140026764`
- `0x140026930`
- `0x140034514`
- `0x14005e100`
- `0x1400b65b8`
- `0x1400b7908`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400b7a94`
- `ntoskrnl!ObfReferenceObject` at `0x1400b7a94`
- `ntoskrnl!IofCompleteRequest` at `0x1400b7afa`
- `ntoskrnl!IofCompleteRequest` at `0x1400b7afa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7a6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7a6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b7adf`
- `ntoskrnl!ExAllocatePool2` at `0x1400b7997`
- `ntoskrnl!ExAllocatePool2` at `0x1400b7997`

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
  _QWORD v19[19]; // [rsp+20h] [rbp-98h] BYREF
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
          LODWORD(v19[1]) = 4;
          if ( (__int64 *)v12 == &VhdmpiEmptyISOBackingStore )
          {
            v6 = -1073741823;
            goto LABEL_23;
          }
          v6 = VhdmpiFileWrapperPinFile(v12 + 72, 0, 0, 0, v19[0], v19[1]);
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
0x1400b7908  push    rbx
0x1400b790a  push    rbp
0x1400b790b  push    rsi
0x1400b790c  push    rdi
0x1400b790d  push    r12
0x1400b790f  push    r13
0x1400b7911  push    r14
0x1400b7913  push    r15
0x1400b7915  sub     rsp, 78h
0x1400b7919  mov     r14, rdx
0x1400b791c  mov     rbx, rcx
0x1400b791f  xor     edx, edx; Val
0x1400b7921  lea     rcx, [rsp+0B8h+var_98]; void *
0x1400b7926  lea     r8d, [rdx+48h]; Size
0x1400b792a  call    memset
0x1400b792f  xor     edx, edx
0x1400b7931  mov     [rsp+0B8h+P], 0
0x1400b793d  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x1400b7940  call    VhdmpiAddRundownRefSurfaceByPdo
0x1400b7945  mov     r13, rax
0x1400b7948  test    rax, rax
0x1400b794b  jnz     short loc_1400B7957
0x1400b794d  mov     ebx, 0C0000001h
0x1400b7952  jmp     loc_1400B7AEB
0x1400b7957  mov     rbp, [rax+10h]
0x1400b795b  lea     r12, [rbp+80h]
0x1400b7962  mov     rcx, r12
0x1400b7965  call    VhdmpiAcquirePassiveLockShared
0x1400b796a  mov     rax, [rbp+90h]
0x1400b7971  xor     ecx, ecx
0x1400b7973  jmp     short loc_1400B797E
0x1400b7975  mov     rax, [rax+478h]
0x1400b797c  inc     ecx
0x1400b797e  test    rax, rax
0x1400b7981  jnz     short loc_1400B7975
0x1400b7983  imul    edx, ecx, 150h
0x1400b7989  mov     r8d, 64444856h
0x1400b798f  mov     ecx, 100h
0x1400b7994  add     edx, 8
0x1400b7997  call    cs:__imp_ExAllocatePool2
0x1400b799e  nop     dword ptr [rax+rax+00h]
0x1400b79a3  mov     rdi, rax
0x1400b79a6  test    rax, rax
0x1400b79a9  jnz     short loc_1400B79B5
0x1400b79ab  mov     ebx, 0C000009Ah
0x1400b79b0  jmp     loc_1400B7ABC
0x1400b79b5  mov     rbp, [rbp+90h]
0x1400b79bc  xor     ebx, ebx
0x1400b79be  xor     esi, esi
0x1400b79c0  test    rbp, rbp
0x1400b79c3  jz      loc_1400B7ABA
0x1400b79c9  mov     eax, [rbp+254h]
0x1400b79cf  cmp     eax, 24h ; '$'
0x1400b79d2  ja      loc_1400B7AA7
0x1400b79d8  mov     rcx, 1080000084h
0x1400b79e2  bt      rcx, rax
0x1400b79e6  jnb     loc_1400B7AA7
0x1400b79ec  xor     edx, edx; Val
0x1400b79ee  lea     rcx, [rsp+0B8h+var_98]; void *
0x1400b79f3  lea     r8d, [rdx+48h]; Size
0x1400b79f7  call    memset
0x1400b79fc  lea     rax, VhdmpiEmptyISOBackingStore
0x1400b7a03  mov     [rsp+0B8h+var_98], 71Bh
0x1400b7a0a  mov     [rsp+0B8h+var_90], 4
0x1400b7a12  cmp     rbp, rax
0x1400b7a15  jz      loc_1400B7AB3
0x1400b7a1b  xor     r9d, r9d
0x1400b7a1e  lea     rcx, [rbp+48h]
0x1400b7a22  xor     r8d, r8d
0x1400b7a25  xor     edx, edx
0x1400b7a27  call    VhdmpiFileWrapperPinFile
0x1400b7a2c  mov     ebx, eax
0x1400b7a2e  test    eax, eax
0x1400b7a30  js      loc_1400B7ABC
0x1400b7a36  mov     rcx, [rbp+258h]
0x1400b7a3d  lea     r8, [rsp+0B8h+P]
0x1400b7a45  lea     rdx, [rsp+0B8h+var_98]
0x1400b7a4a  call    VhdmpiSendPnpIrp
0x1400b7a4f  xor     edx, edx
0x1400b7a51  lea     rcx, [rbp+48h]
0x1400b7a55  mov     ebx, eax
0x1400b7a57  call    VhdmpiFileWrapperUnpinFile
0x1400b7a5c  test    ebx, ebx
0x1400b7a5e  js      short loc_1400B7ABC
0x1400b7a60  mov     rcx, [rsp+0B8h+P]; P
0x1400b7a68  xor     edx, edx; Tag
0x1400b7a6a  mov     r15, [rcx+8]
0x1400b7a6e  call    cs:__imp_ExFreePoolWithTag
0x1400b7a75  nop     dword ptr [rax+rax+00h]
0x1400b7a7a  xor     ecx, ecx
0x1400b7a7c  test    esi, esi
0x1400b7a7e  jz      short loc_1400B7A8D
0x1400b7a80  cmp     [rdi+rcx*8+8], r15
0x1400b7a85  jz      short loc_1400B7AA7
0x1400b7a87  inc     ecx
0x1400b7a89  cmp     ecx, esi
0x1400b7a8b  jb      short loc_1400B7A80
0x1400b7a8d  cmp     ecx, esi
0x1400b7a8f  jnz     short loc_1400B7AA7
0x1400b7a91  mov     rcx, r15; Object
0x1400b7a94  call    cs:__imp_ObfReferenceObject
0x1400b7a9b  nop     dword ptr [rax+rax+00h]
0x1400b7aa0  mov     [rdi+rsi*8+8], r15
0x1400b7aa5  inc     esi
0x1400b7aa7  mov     rbp, [rbp+478h]
0x1400b7aae  jmp     loc_1400B79C0
0x1400b7ab3  mov     ebx, 0C0000001h
0x1400b7ab8  jmp     short loc_1400B7ABC
0x1400b7aba  mov     [rdi], esi
0x1400b7abc  mov     rcx, r12
0x1400b7abf  call    VhdmpiReleasePassiveLockShared
0x1400b7ac4  xor     edx, edx
0x1400b7ac6  mov     rcx, r13
0x1400b7ac9  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x1400b7ace  test    ebx, ebx
0x1400b7ad0  jns     short loc_1400B7AED
0x1400b7ad2  test    rdi, rdi
0x1400b7ad5  jz      short loc_1400B7AED
0x1400b7ad7  mov     edx, 64444856h; Tag
0x1400b7adc  mov     rcx, rdi; P
0x1400b7adf  call    cs:__imp_ExFreePoolWithTag
0x1400b7ae6  nop     dword ptr [rax+rax+00h]
0x1400b7aeb  xor     edi, edi
0x1400b7aed  xor     edx, edx; PriorityBoost
0x1400b7aef  mov     [r14+38h], rdi
0x1400b7af3  mov     rcx, r14; Irp
0x1400b7af6  mov     [r14+30h], ebx
0x1400b7afa  call    cs:__imp_IofCompleteRequest
0x1400b7b01  nop     dword ptr [rax+rax+00h]
0x1400b7b06  mov     eax, ebx
0x1400b7b08  add     rsp, 78h
0x1400b7b0c  pop     r15
0x1400b7b0e  pop     r14
0x1400b7b10  pop     r13
0x1400b7b12  pop     r12
0x1400b7b14  pop     rdi
0x1400b7b15  pop     rsi
0x1400b7b16  pop     rbp
0x1400b7b17  pop     rbx
0x1400b7b18  retn
```
