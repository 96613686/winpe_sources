# VmxpSpanTransferSequentialCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x1400189c0`
- end: `0x140018bb0`
- name: `?VmxpSpanTransferSequentialCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `496`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004ba0`
- `0x140007828`
- `0x14000f368`
- `0x1400189c0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018a74`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018a74`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018aa3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ae0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018aa3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ae0`
- `ntoskrnl!IoBuildPartialMdl` at `0x140018b81`
- `ntoskrnl!IoBuildPartialMdl` at `0x140018b81`
- `ntoskrnl!MmUnmapLockedPages` at `0x140018a11`
- `ntoskrnl!MmUnmapLockedPages` at `0x140018a11`

## pseudocode

```c
void __fastcall VmxpSpanTransferSequentialCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rdi
  NTSTATUS v3; // ebp
  __int64 v4; // rsi
  NTSTATUS v5; // edx
  __int64 v6; // rcx
  unsigned int v7; // r11d
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned __int64 v11; // r8
  __int64 v12; // rbp
  _QWORD **v13; // rdi
  KIRQL v14; // al
  _QWORD *v15; // rbx
  _QWORD *v16; // rcx
  unsigned int v17; // r10d
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  ULONG v20; // r9d
  __int64 v21; // rcx

  v1 = *((_QWORD *)a1 + 22);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *((_QWORD *)a1 + 23);
  v5 = *(_DWORD *)(v1 + 96);
  if ( v3 < 0 )
  {
    if ( VmxpIsWorseStatus(v3, v5) )
      *(_DWORD *)(v1 + 96) = v3;
  }
  else if ( v5 >= 0 )
  {
    *(_QWORD *)(v1 + 104) += *((_QWORD *)a1 + 13);
  }
  v6 = *((_QWORD *)a1 + 3);
  if ( (*(_BYTE *)(v6 + 10) & 0x20) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v6 + 24), *((PMDL *)a1 + 3));
  v7 = *((_DWORD *)a1 + 48);
  v8 = 0;
  if ( v7 )
  {
    v9 = 0;
    do
    {
      v10 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8 * v9);
      v9 = (unsigned int)(v9 + 1);
      v8 += *(_QWORD *)(v10 + 16);
    }
    while ( (unsigned int)v9 < v7 );
  }
  v11 = *((_QWORD *)a1 + 2) + *((unsigned int *)a1 + 2);
  v12 = v11 + v8;
  if ( v11 + v8 == *(_QWORD *)(v1 + 16) + *(unsigned int *)(v1 + 8) )
  {
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    v13 = (_QWORD **)(v4 + 80);
    while ( 1 )
    {
      v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v15 = *v13;
      if ( *v13 == v13 )
        break;
      if ( (_QWORD **)v15[1] != v13 || (v16 = (_QWORD *)*v15, *(_QWORD **)(*v15 + 8LL) != v15) )
        __fastfail(3u);
      *v13 = v16;
      v16[1] = v13;
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v14);
      if ( !VMX_IO_SPAN::LaunchParallel((VMX_IO_SPAN *)v4, (struct VMX_TRANSFER_PACKET *)(v15 - 14)) )
      {
        VMX_IO_SPAN::LaunchSequential((VMX_IO_SPAN *)v4, (struct VMX_TRANSFER_PACKET *)(v15 - 14));
        return;
      }
    }
    *(_BYTE *)(v4 + 72) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v14);
  }
  else
  {
    v17 = 0x10000;
    v18 = *(_QWORD *)(*((_QWORD *)a1 + 6) + 16LL);
    *((_QWORD *)a1 + 2) = v11;
    *((_DWORD *)a1 + 2) = 0x10000;
    if ( v11 >= v18 )
    {
      v11 -= v18;
      *((_QWORD *)a1 + 2) = v11;
      *((_DWORD *)a1 + 48) = v7 + 1;
      v19 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8LL * (v7 + 1));
      *((_QWORD *)a1 + 6) = v19;
      v18 = *(_QWORD *)(v19 + 16);
    }
    if ( v12 + 0x10000 > *(_QWORD *)(v1 + 16) + (unsigned __int64)*(unsigned int *)(v1 + 8) )
    {
      v17 = *(_DWORD *)(v1 + 8) - v12 + *(_DWORD *)(v1 + 16);
      *((_DWORD *)a1 + 2) = v17;
    }
    if ( v11 + v17 <= v18 )
    {
      v20 = v17;
    }
    else
    {
      v20 = v18 - *((_DWORD *)a1 + 4);
      *((_DWORD *)a1 + 2) = v20;
    }
    IoBuildPartialMdl(
      *(PMDL *)(v1 + 24),
      *((PMDL *)a1 + 3),
      (PVOID)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 32LL)
            + *(unsigned int *)(*(_QWORD *)(v1 + 24) + 44LL)
            + (unsigned __int64)(unsigned int)(v12 - *(_DWORD *)(v1 + 16))),
      v20);
    v21 = *((_QWORD *)a1 + 6);
    *((_DWORD *)a1 + 3) = *(_DWORD *)(v1 + 12);
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v21 + 8LL))(v21, a1);
  }
}

```

## disassembly

```asm
0x1400189c0  push    rbx
0x1400189c2  push    rbp
0x1400189c3  push    rsi
0x1400189c4  push    rdi
0x1400189c5  sub     rsp, 28h
0x1400189c9  mov     rdi, [rcx+0B0h]
0x1400189d0  mov     rbx, rcx
0x1400189d3  mov     ebp, [rcx+60h]
0x1400189d6  mov     rsi, [rcx+0B8h]
0x1400189dd  mov     edx, [rdi+60h]; NTSTATUS
0x1400189e0  test    ebp, ebp
0x1400189e2  js      short loc_1400189F2
0x1400189e4  test    edx, edx
0x1400189e6  js      short loc_140018A00
0x1400189e8  mov     rax, [rcx+68h]
0x1400189ec  add     [rdi+68h], rax
0x1400189f0  jmp     short loc_140018A00
0x1400189f2  mov     ecx, ebp; Status
0x1400189f4  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x1400189f9  test    al, al
0x1400189fb  jz      short loc_140018A00
0x1400189fd  mov     [rdi+60h], ebp
0x140018a00  mov     rcx, [rbx+18h]
0x140018a04  test    byte ptr [rcx+0Ah], 20h
0x140018a08  jz      short loc_140018A1D
0x140018a0a  mov     rdx, rcx; MemoryDescriptorList
0x140018a0d  mov     rcx, [rcx+18h]; BaseAddress
0x140018a11  call    cs:__imp_MmUnmapLockedPages
0x140018a18  nop     dword ptr [rax+rax+00h]
0x140018a1d  mov     r11d, [rbx+0C0h]
0x140018a24  xor     r9d, r9d
0x140018a27  test    r11d, r11d
0x140018a2a  jz      short loc_140018A41
0x140018a2c  mov     r8, [rsi+30h]
0x140018a30  xor     edx, edx
0x140018a32  mov     rcx, [r8+rdx*8]
0x140018a36  inc     edx
0x140018a38  add     r9, [rcx+10h]
0x140018a3c  cmp     edx, r11d
0x140018a3f  jb      short loc_140018A32
0x140018a41  mov     r8d, [rbx+8]
0x140018a45  add     r8, [rbx+10h]
0x140018a49  mov     eax, [rdi+8]
0x140018a4c  add     rax, [rdi+10h]
0x140018a50  lea     rbp, [r8+r9]
0x140018a54  cmp     rbp, rax
0x140018a57  jnz     loc_140018AF1
0x140018a5d  mov     rax, [rdi+28h]
0x140018a61  mov     rcx, rdi
0x140018a64  call    _guard_dispatch_icall
0x140018a69  lea     rbp, [rsi+18h]
0x140018a6d  lea     rdi, [rsi+50h]
0x140018a71  mov     rcx, rbp; SpinLock
0x140018a74  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018a7b  nop     dword ptr [rax+rax+00h]
0x140018a80  mov     rbx, [rdi]
0x140018a83  cmp     rbx, rdi
0x140018a86  jz      short loc_140018AD7
0x140018a88  cmp     [rbx+8], rdi
0x140018a8c  jnz     short loc_140018AD0
0x140018a8e  mov     rcx, [rbx]
0x140018a91  cmp     [rcx+8], rbx
0x140018a95  jnz     short loc_140018AD0
0x140018a97  mov     [rdi], rcx
0x140018a9a  mov     dl, al; NewIrql
0x140018a9c  mov     [rcx+8], rdi
0x140018aa0  mov     rcx, rbp; SpinLock
0x140018aa3  call    cs:__imp_KeReleaseSpinLock
0x140018aaa  nop     dword ptr [rax+rax+00h]
0x140018aaf  lea     rdx, [rbx-70h]; struct VMX_TRANSFER_PACKET *
0x140018ab3  mov     rcx, rsi; this
0x140018ab6  call    ?LaunchParallel@VMX_IO_SPAN@@QEAAEPEAVVMX_TRANSFER_PACKET@@@Z; VMX_IO_SPAN::LaunchParallel(VMX_TRANSFER_PACKET *)
0x140018abb  test    al, al
0x140018abd  jnz     short loc_140018A71
0x140018abf  lea     rdx, [rbx-70h]; struct VMX_TRANSFER_PACKET *
0x140018ac3  mov     rcx, rsi; this
0x140018ac6  call    ?LaunchSequential@VMX_IO_SPAN@@QEAAXPEAVVMX_TRANSFER_PACKET@@@Z; VMX_IO_SPAN::LaunchSequential(VMX_TRANSFER_PACKET *)
0x140018acb  jmp     loc_140018BA6
0x140018ad0  mov     ecx, 3
0x140018ad5  int     29h; Win8: RtlFailFast(ecx)
0x140018ad7  mov     dl, al; NewIrql
0x140018ad9  mov     byte ptr [rsi+48h], 0
0x140018add  mov     rcx, rbp; SpinLock
0x140018ae0  call    cs:__imp_KeReleaseSpinLock
0x140018ae7  nop     dword ptr [rax+rax+00h]
0x140018aec  jmp     loc_140018BA6
0x140018af1  mov     rax, [rbx+30h]
0x140018af5  mov     r10d, 10000h
0x140018afb  mov     r9, [rax+10h]
0x140018aff  mov     [rbx+10h], r8
0x140018b03  mov     [rbx+8], r10d
0x140018b07  cmp     r8, r9
0x140018b0a  jb      short loc_140018B2F
0x140018b0c  lea     eax, [r11+1]
0x140018b10  sub     r8, r9
0x140018b13  mov     [rbx+10h], r8
0x140018b17  mov     [rbx+0C0h], eax
0x140018b1d  mov     ecx, eax
0x140018b1f  mov     rax, [rsi+30h]
0x140018b23  mov     rdx, [rax+rcx*8]
0x140018b27  mov     [rbx+30h], rdx
0x140018b2b  mov     r9, [rdx+10h]
0x140018b2f  mov     edx, [rdi+8]
0x140018b32  lea     rax, [rbp+10000h]
0x140018b39  mov     ecx, edx
0x140018b3b  add     rcx, [rdi+10h]
0x140018b3f  cmp     rax, rcx
0x140018b42  jbe     short loc_140018B51
0x140018b44  mov     r10d, [rdi+10h]
0x140018b48  sub     edx, ebp
0x140018b4a  add     r10d, edx
0x140018b4d  mov     [rbx+8], r10d
0x140018b51  mov     eax, r10d
0x140018b54  add     rax, r8
0x140018b57  cmp     rax, r9
0x140018b5a  jbe     short loc_140018B66
0x140018b5c  sub     r9d, [rbx+10h]
0x140018b60  mov     [rbx+8], r9d
0x140018b64  jmp     short loc_140018B69
0x140018b66  mov     r9d, r10d; Length
0x140018b69  mov     rcx, [rdi+18h]; SourceMdl
0x140018b6d  sub     ebp, [rdi+10h]
0x140018b70  mov     rdx, [rbx+18h]; TargetMdl
0x140018b74  mov     r8d, ebp
0x140018b77  mov     eax, [rcx+2Ch]
0x140018b7a  add     r8, rax
0x140018b7d  add     r8, [rcx+20h]; VirtualAddress
0x140018b81  call    cs:__imp_IoBuildPartialMdl
0x140018b88  nop     dword ptr [rax+rax+00h]
0x140018b8d  mov     eax, [rdi+0Ch]
0x140018b90  mov     rdx, rbx
0x140018b93  mov     rcx, [rbx+30h]
0x140018b97  mov     [rbx+0Ch], eax
0x140018b9a  mov     rax, [rcx]
0x140018b9d  mov     rax, [rax+8]
0x140018ba1  call    _guard_dispatch_icall
0x140018ba6  add     rsp, 28h
0x140018baa  pop     rdi
0x140018bab  pop     rsi
0x140018bac  pop     rbp
0x140018bad  pop     rbx
0x140018bae  retn
```
