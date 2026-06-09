# VMX_LOG::FlushSequentialIo(void)

- ea: `0x140019ac4`
- end: `0x140019d07`
- name: `?FlushSequentialIo@VMX_LOG@@AEAAXXZ`
- size: `579`
- prototype: `void __fastcall(VMX_LOG *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400199dc`
- `0x14001a350`

## callees

- `0x140004550`
- `0x140019430`
- `0x140019ac4`
- `0x14001bb80`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140019cdf`
- `ntoskrnl!IofCallDriver` at `0x140019cdf`
- `ntoskrnl!IoReuseIrp` at `0x140019c0d`
- `ntoskrnl!IoReuseIrp` at `0x140019c0d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140019c45`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140019c45`

## pseudocode

```c
void __fastcall VMX_LOG::FlushSequentialIo(VMX_LOG *this)
{
  __int64 v1; // rax
  __int64 *v2; // rbx
  __int64 v3; // r15
  unsigned int v4; // r12d
  __int64 *v6; // rsi
  bool i; // r9
  __int64 *v8; // rax
  __int64 v9; // r13
  int v10; // ecx
  unsigned int v11; // r8d
  unsigned int v12; // edi
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // r14d
  unsigned int v17; // r9d
  unsigned int v18; // ecx
  unsigned int j; // edx
  unsigned int v20; // ecx
  IRP *v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rcx
  PVOID v24; // rax
  unsigned int v25; // edi
  __int64 v26; // rcx
  __int64 v27; // rcx

  v1 = *((_QWORD *)this + 31);
  v2 = (__int64 *)((char *)this + 16);
  v3 = 0;
  v4 = 0;
  if ( v1 )
    v6 = (__int64 *)*((_QWORD *)this + 31);
  else
    v6 = (__int64 *)*v2;
  for ( i = v1 == 0; ; i = 1 )
  {
    if ( v6 == v2 )
    {
      VMX_LOG::FlushChunkCompletionRoutine(this);
      return;
    }
    v8 = (__int64 *)*((_QWORD *)this + 23);
    if ( !v8 || v6 == v8 )
    {
      if ( *((_BYTE *)v6 + 45) )
      {
        v9 = v6[3];
        v10 = *((_DWORD *)this + 54);
        v11 = *(_DWORD *)(v9 + 36) >> 9;
        v12 = v11 + v10 + *((_DWORD *)this + 55) - 1 - (v11 + v10 + *((_DWORD *)this + 55) - 1) % v11;
        if ( i )
        {
          v16 = v11 + v10 - (v11 + v10 - 1) % v11 - 1;
          v15 = v12 - v16;
        }
        else
        {
          v13 = *((_DWORD *)this + 65);
          v14 = *((_DWORD *)this + 64);
          v15 = v12 - v14 - v13;
          v16 = v14 + v13;
        }
        if ( v15 )
          break;
      }
    }
LABEL_21:
    v6 = (__int64 *)*v6;
  }
  v17 = *((_DWORD *)v6 + 10);
  v18 = 0;
  if ( v17 )
  {
    for ( j = 0; j < v17; ++j )
    {
      v4 = v18;
      v3 = v6[4] + 16LL * j;
      v18 += *(_DWORD *)(v3 + 8) * v11;
      if ( v16 < v18 )
        break;
    }
  }
  v20 = v18 - v16;
  if ( v15 >= v20 )
    v15 = v20;
  if ( (int)VMX_DISK_DEVICE::Reference((VMX_DISK_DEVICE *)v6[3]) < 0 )
  {
    *((_WORD *)v6 + 22) = 1;
    goto LABEL_21;
  }
  v21 = (IRP *)*((_QWORD *)this + 29);
  v22 = *(_QWORD *)v3 * *(unsigned int *)(v9 + 36) + ((v16 - v4) << 9);
  *((_QWORD *)this + 31) = v6;
  *((_DWORD *)this + 64) = v16;
  *((_DWORD *)this + 65) = v15;
  IoReuseIrp(v21, 0);
  v23 = *((_QWORD *)this + 30);
  if ( (*(_BYTE *)(v23 + 10) & 5) != 0 )
    v24 = *(PVOID *)(v23 + 24);
  else
    v24 = MmMapLockedPagesSpecifyCache((PMDL)v23, 0, MmCached, 0, 0, 0x40000010u);
  v25 = v15 << 9;
  memmove(v24, (const void *)(*((_QWORD *)this + 8) + (v16 << 9)), v25);
  *(_QWORD *)(*((_QWORD *)this + 29) + 8LL) = *((_QWORD *)this + 30);
  v26 = *(_QWORD *)(*((_QWORD *)this + 29) + 184LL);
  *(_QWORD *)(v26 - 48) = v22;
  *(_DWORD *)(v26 - 64) = v25;
  *(_BYTE *)(v26 - 72) = 4;
  *(_QWORD *)(v26 - 32) = *(_QWORD *)(v9 + 24);
  *(_QWORD *)(*((_QWORD *)this + 29) + 152LL) = 0;
  *(_BYTE *)(v26 - 70) |= 0x14u;
  v27 = *(_QWORD *)(*((_QWORD *)this + 29) + 184LL);
  *(_QWORD *)(v27 - 16) = VmxpLogFlushSequentialIoCompletionRoutine;
  *(_QWORD *)(v27 - 8) = v6;
  *(_BYTE *)(v27 - 69) = -32;
  IofCallDriver(*(PDEVICE_OBJECT *)(v9 + 24), *((PIRP *)this + 29));
}

```

## disassembly

```asm
0x140019ac4  push    rbx
0x140019ac6  push    rbp
0x140019ac7  push    rsi
0x140019ac8  push    rdi
0x140019ac9  push    r12
0x140019acb  push    r13
0x140019acd  push    r14
0x140019acf  push    r15
0x140019ad1  sub     rsp, 38h
0x140019ad5  mov     rax, [rcx+0F8h]
0x140019adc  lea     rbx, [rcx+10h]
0x140019ae0  xor     r15d, r15d
0x140019ae3  xor     r12d, r12d
0x140019ae6  mov     rbp, rcx
0x140019ae9  test    rax, rax
0x140019aec  jnz     short loc_140019AF3
0x140019aee  mov     rsi, [rbx]
0x140019af1  jmp     short loc_140019AF6
0x140019af3  mov     rsi, rax
0x140019af6  test    rax, rax
0x140019af9  setz    r9b
0x140019afd  cmp     rsi, rbx
0x140019b00  jz      loc_140019CED
0x140019b06  mov     rax, [rbp+0B8h]
0x140019b0d  test    rax, rax
0x140019b10  jz      short loc_140019B1B
0x140019b12  cmp     rsi, rax
0x140019b15  jnz     loc_140019BD1
0x140019b1b  cmp     byte ptr [rsi+2Dh], 0
0x140019b1f  jz      loc_140019BD1
0x140019b25  mov     r13, [rsi+18h]
0x140019b29  xor     edx, edx
0x140019b2b  mov     edi, [rbp+0DCh]
0x140019b31  mov     ecx, [rbp+0D8h]
0x140019b37  dec     edi
0x140019b39  add     edi, ecx
0x140019b3b  mov     r8d, [r13+24h]
0x140019b3f  shr     r8d, 9
0x140019b43  add     edi, r8d
0x140019b46  mov     eax, edi
0x140019b48  div     r8d
0x140019b4b  sub     edi, edx
0x140019b4d  test    r9b, r9b
0x140019b50  jnz     short loc_140019B68
0x140019b52  mov     ecx, [rbp+104h]
0x140019b58  mov     eax, [rbp+100h]
0x140019b5e  sub     edi, eax
0x140019b60  sub     edi, ecx
0x140019b62  lea     r14d, [rax+rcx]
0x140019b66  jmp     short loc_140019B7F
0x140019b68  lea     eax, [rcx-1]
0x140019b6b  xor     edx, edx
0x140019b6d  add     eax, r8d
0x140019b70  div     r8d
0x140019b73  sub     ecx, edx
0x140019b75  lea     r14d, [rcx-1]
0x140019b79  add     r14d, r8d
0x140019b7c  sub     edi, r14d
0x140019b7f  test    edi, edi
0x140019b81  jz      short loc_140019BD1
0x140019b83  mov     r9d, [rsi+28h]
0x140019b87  xor     ecx, ecx
0x140019b89  test    r9d, r9d
0x140019b8c  jz      short loc_140019BB7
0x140019b8e  mov     r10, [rsi+20h]
0x140019b92  xor     edx, edx
0x140019b94  mov     r15d, edx
0x140019b97  mov     eax, r8d
0x140019b9a  shl     r15, 4
0x140019b9e  mov     r12d, ecx
0x140019ba1  add     r15, r10
0x140019ba4  imul    eax, [r15+8]
0x140019ba9  add     ecx, eax
0x140019bab  cmp     r14d, ecx
0x140019bae  jb      short loc_140019BB7
0x140019bb0  inc     edx
0x140019bb2  cmp     edx, r9d
0x140019bb5  jb      short loc_140019B94
0x140019bb7  sub     ecx, r14d
0x140019bba  cmp     edi, ecx
0x140019bbc  cmovnb  edi, ecx
0x140019bbf  mov     rcx, r13; this
0x140019bc2  call    ?Reference@VMX_DISK_DEVICE@@QEAAJXZ; VMX_DISK_DEVICE::Reference(void)
0x140019bc7  test    eax, eax
0x140019bc9  jns     short loc_140019BDC
0x140019bcb  mov     word ptr [rsi+2Ch], 1
0x140019bd1  mov     rsi, [rsi]
0x140019bd4  mov     r9b, 1
0x140019bd7  jmp     loc_140019AFD
0x140019bdc  mov     eax, [r13+24h]
0x140019be0  mov     ebx, r14d
0x140019be3  imul    rax, [r15]
0x140019be7  mov     rcx, [rbp+0E8h]; Irp
0x140019bee  sub     ebx, r12d
0x140019bf1  shl     ebx, 9
0x140019bf4  xor     edx, edx; Iostatus
0x140019bf6  add     rbx, rax
0x140019bf9  mov     [rbp+0F8h], rsi
0x140019c00  mov     [rbp+100h], r14d
0x140019c07  mov     [rbp+104h], edi
0x140019c0d  call    cs:__imp_IoReuseIrp
0x140019c14  nop     dword ptr [rax+rax+00h]
0x140019c19  mov     rcx, [rbp+0F0h]; MemoryDescriptorList
0x140019c20  test    byte ptr [rcx+0Ah], 5
0x140019c24  jz      short loc_140019C2C
0x140019c26  mov     rax, [rcx+18h]
0x140019c2a  jmp     short loc_140019C51
0x140019c2c  xor     r9d, r9d; RequestedAddress
0x140019c2f  mov     [rsp+78h+Priority], 40000010h; Priority
0x140019c37  xor     edx, edx; AccessMode
0x140019c39  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140019c41  lea     r8d, [r9+1]; CacheType
0x140019c45  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140019c4c  nop     dword ptr [rax+rax+00h]
0x140019c51  shl     r14d, 9
0x140019c55  mov     rcx, rax; void *
0x140019c58  mov     edx, r14d
0x140019c5b  add     rdx, [rbp+40h]; Src
0x140019c5f  shl     edi, 9
0x140019c62  mov     r8d, edi; Size
0x140019c65  call    memmove
0x140019c6a  mov     rcx, [rbp+0E8h]
0x140019c71  mov     rax, [rbp+0F0h]
0x140019c78  mov     [rcx+8], rax
0x140019c7c  mov     rax, [rbp+0E8h]
0x140019c83  mov     rcx, [rax+0B8h]
0x140019c8a  mov     [rcx-30h], rbx
0x140019c8e  mov     [rcx-40h], edi
0x140019c91  mov     byte ptr [rcx-48h], 4
0x140019c95  mov     rax, [r13+18h]
0x140019c99  mov     [rcx-20h], rax
0x140019c9d  mov     rax, [rbp+0E8h]
0x140019ca4  mov     qword ptr [rax+98h], 0
0x140019caf  or      byte ptr [rcx-46h], 14h
0x140019cb3  mov     rax, [rbp+0E8h]
0x140019cba  mov     rcx, [rax+0B8h]
0x140019cc1  lea     rax, ?VmxpLogFlushSequentialIoCompletionRoutine@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; VmxpLogFlushSequentialIoCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140019cc8  mov     [rcx-10h], rax
0x140019ccc  mov     [rcx-8], rsi
0x140019cd0  mov     byte ptr [rcx-45h], 0E0h
0x140019cd4  mov     rdx, [rbp+0E8h]; Irp
0x140019cdb  mov     rcx, [r13+18h]; DeviceObject
0x140019cdf  call    cs:__imp_IofCallDriver
0x140019ce6  nop     dword ptr [rax+rax+00h]
0x140019ceb  jmp     short loc_140019CF5
0x140019ced  mov     rcx, rbp; this
0x140019cf0  call    ?FlushChunkCompletionRoutine@VMX_LOG@@AEAAXXZ; VMX_LOG::FlushChunkCompletionRoutine(void)
0x140019cf5  add     rsp, 38h
0x140019cf9  pop     r15
0x140019cfb  pop     r14
0x140019cfd  pop     r13
0x140019cff  pop     r12
0x140019d01  pop     rdi
0x140019d02  pop     rsi
0x140019d03  pop     rbp
0x140019d04  pop     rbx
0x140019d05  retn
```
