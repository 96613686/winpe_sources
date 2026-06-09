# VmxpRaid5RecoverUpdateParityPhase2(VMX_TRANSFER_PACKET *)

- ea: `0x1400160f0`
- end: `0x14001632b`
- name: `?VmxpRaid5RecoverUpdateParityPhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `571`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007828`
- `0x14000d0dc`
- `0x140012560`
- `0x1400160f0`
- `0x140018fcc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016115`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400161a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016202`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016115`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400161a7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016202`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400161ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001623c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400161ef`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001623c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14001614c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14001614c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001627c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400162da`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001627c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400162da`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverUpdateParityPhase2(struct VMX_TRANSFER_PACKET *a1)
{
  NTSTATUS v1; // ebx
  __int64 v3; // rdi
  KSPIN_LOCK *v4; // rsi
  KIRQL v5; // r14
  __int64 v6; // r14
  KSPIN_LOCK *v7; // rsi
  __int64 v8; // r8
  KIRQL v9; // al
  __int64 v10; // rdx
  KIRQL v11; // r11
  int v12; // ebx
  __int64 v13; // rcx
  PVOID v14; // rbp
  _QWORD **v15; // rbx
  _QWORD *v16; // rcx
  _QWORD *v17; // rdx
  void (__fastcall ***v18)(_QWORD, __int64); // rsi
  __int64 v19; // rcx
  PVOID v20; // rax

  v1 = *((_DWORD *)a1 + 24);
  v3 = *((_QWORD *)a1 + 17);
  if ( v1 < 0 )
  {
    v6 = *(_QWORD *)(v3 + 224);
    v7 = *(KSPIN_LOCK **)(v6 - 336);
    if ( FsRtlIsTotalDeviceFailure(v1) && v1 != -2147483626 )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 34, v8, v7, v1);
      }
      v9 = KeAcquireSpinLockRaiseToDpc(v7 + 3);
      v10 = *((unsigned int *)a1 + 36);
      v11 = v9;
      if ( *(_DWORD *)(v7[14] + 24 * v10 + 16) != 4
        && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v7, v10, 1) )
      {
        ++*(_DWORD *)(*(_QWORD *)(v6 - 312) + 168LL);
      }
      KeReleaseSpinLock(v7 + 3, v11);
    }
    v4 = (KSPIN_LOCK *)(v3 + 88);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 88));
    if ( VmxpIsWorseStatus(v1, *(_DWORD *)(v3 + 96)) )
    {
      *(_DWORD *)(v3 + 96) = v1;
      *(_QWORD *)(v3 + 104) = 0;
    }
  }
  else
  {
    v4 = (KSPIN_LOCK *)(v3 + 88);
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 88));
    if ( *(int *)(v3 + 96) >= 0 )
      *(_OWORD *)(v3 + 96) = *((_OWORD *)a1 + 6);
  }
  v12 = --*(_DWORD *)(v3 + 128);
  KeReleaseSpinLock(v4, v5);
  if ( !v12 )
  {
    v13 = *(_QWORD *)(v3 + 24);
    if ( (*(_BYTE *)(v13 + 10) & 5) != 0 )
      v14 = *(PVOID *)(v13 + 24);
    else
      v14 = MmMapLockedPagesSpecifyCache((PMDL)v13, 0, MmCached, 0, 0, 0x40000010u);
    v15 = (_QWORD **)(v3 + 112);
    while ( 1 )
    {
      v16 = *v15;
      if ( *v15 == v15 )
        break;
      if ( (_QWORD **)v16[1] != v15 || (v17 = (_QWORD *)*v16, *(_QWORD **)(*v16 + 8LL) != v16) )
        __fastfail(3u);
      *v15 = v17;
      v18 = (void (__fastcall ***)(_QWORD, __int64))(v16 - 19);
      v17[1] = v15;
      v19 = *(v16 - 16);
      if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
        v20 = *(PVOID *)(v19 + 24);
      else
        v20 = MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000010u);
      VmxpComputeParity(v14, v20, *(_DWORD *)(v3 + 8));
      (**v18)(v18, 1);
    }
    (*(void (__fastcall **)(__int64))(v3 + 40))(v3);
  }
}

```

## disassembly

```asm
0x1400160f0  push    rbx
0x1400160f2  push    rbp
0x1400160f3  push    rsi
0x1400160f4  push    rdi
0x1400160f5  push    r14
0x1400160f7  push    r15
0x1400160f9  sub     rsp, 38h
0x1400160fd  mov     ebx, [rcx+60h]
0x140016100  mov     rbp, rcx
0x140016103  mov     rdi, [rcx+88h]
0x14001610a  test    ebx, ebx
0x14001610c  js      short loc_14001613C
0x14001610e  lea     rsi, [rdi+58h]
0x140016112  mov     rcx, rsi; SpinLock
0x140016115  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001611c  nop     dword ptr [rax+rax+00h]
0x140016121  cmp     dword ptr [rdi+60h], 0
0x140016125  mov     r14b, al
0x140016128  jl      loc_14001622A
0x14001612e  movups  xmm0, xmmword ptr [rbp+60h]
0x140016132  movdqu  xmmword ptr [rdi+60h], xmm0
0x140016137  jmp     loc_14001622A
0x14001613c  mov     r14, [rdi+0E0h]
0x140016143  mov     ecx, ebx; Status
0x140016145  mov     rsi, [r14-150h]
0x14001614c  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140016153  nop     dword ptr [rax+rax+00h]
0x140016158  test    al, al
0x14001615a  jz      loc_1400161FB
0x140016160  cmp     ebx, 80000016h
0x140016166  jz      loc_1400161FB
0x14001616c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016173  lea     rax, WPP_GLOBAL_Control
0x14001617a  cmp     rcx, rax
0x14001617d  jz      short loc_1400161A3
0x14001617f  test    dword ptr [rcx+2Ch], 1000h
0x140016186  jz      short loc_1400161A3
0x140016188  cmp     byte ptr [rcx+29h], 3
0x14001618c  jb      short loc_1400161A3
0x14001618e  mov     rcx, [rcx+18h]
0x140016192  mov     edx, 22h ; '"'
0x140016197  mov     r9, rsi
0x14001619a  mov     [rsp+68h+BugCheckOnFailure], ebx
0x14001619e  call    WPP_SF_qd
0x1400161a3  lea     rcx, [rsi+18h]; SpinLock
0x1400161a7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400161ae  nop     dword ptr [rax+rax+00h]
0x1400161b3  mov     edx, [rbp+90h]; unsigned int
0x1400161b9  mov     r11b, al
0x1400161bc  mov     r8, [rsi+70h]
0x1400161c0  lea     r9, [rdx+rdx*2]
0x1400161c4  cmp     dword ptr [r8+r9*8+10h], 4
0x1400161ca  jz      short loc_1400161E8
0x1400161cc  mov     r8b, 1; unsigned __int8
0x1400161cf  mov     rcx, rsi; this
0x1400161d2  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x1400161d7  test    al, al
0x1400161d9  jz      short loc_1400161E8
0x1400161db  mov     rax, [r14-138h]
0x1400161e2  inc     dword ptr [rax+0A8h]
0x1400161e8  mov     dl, r11b; NewIrql
0x1400161eb  lea     rcx, [rsi+18h]; SpinLock
0x1400161ef  call    cs:__imp_KeReleaseSpinLock
0x1400161f6  nop     dword ptr [rax+rax+00h]
0x1400161fb  lea     rsi, [rdi+58h]
0x1400161ff  mov     rcx, rsi; SpinLock
0x140016202  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016209  nop     dword ptr [rax+rax+00h]
0x14001620e  mov     edx, [rdi+60h]; NTSTATUS
0x140016211  mov     ecx, ebx; Status
0x140016213  mov     r14b, al
0x140016216  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x14001621b  test    al, al
0x14001621d  jz      short loc_14001622A
0x14001621f  mov     [rdi+60h], ebx
0x140016222  mov     qword ptr [rdi+68h], 0
0x14001622a  dec     dword ptr [rdi+80h]
0x140016230  mov     dl, r14b; NewIrql
0x140016233  mov     ebx, [rdi+80h]
0x140016239  mov     rcx, rsi; SpinLock
0x14001623c  call    cs:__imp_KeReleaseSpinLock
0x140016243  nop     dword ptr [rax+rax+00h]
0x140016248  test    ebx, ebx
0x14001624a  jnz     loc_14001631D
0x140016250  mov     rcx, [rdi+18h]; MemoryDescriptorList
0x140016254  mov     r14d, 40000010h
0x14001625a  test    byte ptr [rcx+0Ah], 5
0x14001625e  jz      short loc_140016266
0x140016260  mov     rbp, [rcx+18h]
0x140016264  jmp     short loc_14001628B
0x140016266  xor     r9d, r9d; RequestedAddress
0x140016269  mov     [rsp+68h+Priority], r14d; Priority
0x14001626e  xor     edx, edx; AccessMode
0x140016270  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140016278  lea     r8d, [r9+1]; CacheType
0x14001627c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140016283  nop     dword ptr [rax+rax+00h]
0x140016288  mov     rbp, rax
0x14001628b  lea     rbx, [rdi+70h]
0x14001628f  mov     rcx, [rbx]
0x140016292  cmp     rcx, rbx
0x140016295  jz      short loc_140016311
0x140016297  cmp     [rcx+8], rbx
0x14001629b  jnz     short loc_14001630A
0x14001629d  mov     rdx, [rcx]
0x1400162a0  cmp     [rdx+8], rcx
0x1400162a4  jnz     short loc_14001630A
0x1400162a6  mov     [rbx], rdx
0x1400162a9  lea     rsi, [rcx-98h]
0x1400162b0  mov     [rdx+8], rbx
0x1400162b4  mov     rcx, [rsi+18h]; MemoryDescriptorList
0x1400162b8  test    byte ptr [rcx+0Ah], 5
0x1400162bc  jz      short loc_1400162C4
0x1400162be  mov     rax, [rcx+18h]
0x1400162c2  jmp     short loc_1400162E6
0x1400162c4  xor     r9d, r9d; RequestedAddress
0x1400162c7  mov     [rsp+68h+Priority], r14d; Priority
0x1400162cc  xor     edx, edx; AccessMode
0x1400162ce  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400162d6  lea     r8d, [r9+1]; CacheType
0x1400162da  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400162e1  nop     dword ptr [rax+rax+00h]
0x1400162e6  mov     r8d, [rdi+8]; unsigned int
0x1400162ea  mov     rdx, rax; void *
0x1400162ed  mov     rcx, rbp; void *
0x1400162f0  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x1400162f5  mov     rax, [rsi]
0x1400162f8  mov     edx, 1
0x1400162fd  mov     rcx, rsi
0x140016300  mov     rax, [rax]
0x140016303  call    _guard_dispatch_icall
0x140016308  jmp     short loc_14001628F
0x14001630a  mov     ecx, 3
0x14001630f  int     29h; Win8: RtlFailFast(ecx)
0x140016311  mov     rax, [rdi+28h]
0x140016315  mov     rcx, rdi
0x140016318  call    _guard_dispatch_icall
0x14001631d  add     rsp, 38h
0x140016321  pop     r15
0x140016323  pop     r14
0x140016325  pop     rdi
0x140016326  pop     rsi
0x140016327  pop     rbp
0x140016328  pop     rbx
0x140016329  retn
```
