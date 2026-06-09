# VMX_MIRROR_REGENERATION_TASK::Resume(void)

- ea: `0x1400116d0`
- end: `0x1400118d1`
- name: `?Resume@VMX_MIRROR_REGENERATION_TASK@@UEAAXXZ`
- size: `513`
- prototype: `void __fastcall(VMX_MIRROR_REGENERATION_TASK *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005aa0`
- `0x14000d078`
- `0x14000e784`
- `0x1400116d0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011791`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400116f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011791`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011738`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001180c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011837`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011738`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001180c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011837`

## pseudocode

```c
void __fastcall VMX_MIRROR_REGENERATION_TASK::Resume(VMX_MIRROR_REGENERATION_TASK *this)
{
  __int64 v1; // rdi
  KSPIN_LOCK *v3; // rsi
  KIRQL v4; // di
  VMX_MIRROR_REGENERATION_TASK **v5; // r8
  VMX_MIRROR_REGENERATION_TASK **v6; // rdx
  KIRQL v7; // r12
  __int64 v8; // rbp
  unsigned int v9; // r14d
  char v10; // r15
  __int64 i; // rdx
  __int64 v12; // rcx
  int v13; // ecx

  v1 = *((_QWORD *)this + 4);
  v3 = (KSPIN_LOCK *)(v1 + 24);
  if ( *((_QWORD *)this + 7) < *((_QWORD *)this + 6) )
  {
    *(_QWORD *)(*((_QWORD *)this + 16) + 48LL) = v1;
    *(_DWORD *)(*((_QWORD *)this + 16) + 168LL) = 0;
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
    if ( *(_BYTE *)(v1 + 159) )
    {
      v8 = *(_QWORD *)(v1 + 96);
      v9 = 0;
      v10 = 1;
      if ( *(_DWORD *)(v1 + 56) )
      {
        do
        {
          if ( *(_BYTE *)(v8 + 20) && *(_DWORD *)(v8 + 16) != 4 )
          {
            if ( VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)v1, v9, 1) )
              ++*(_DWORD *)(*((_QWORD *)this + 16) + 168LL);
            else
              v10 = 0;
          }
          ++v9;
          v8 += 40;
        }
        while ( v9 < *(_DWORD *)(v1 + 56) );
        if ( !v10 )
        {
          *(_BYTE *)(v1 + 158) = 1;
          KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), v7);
          VMX_MIRROR_REGENERATION_TASK::IterationCompletion(this, -1073741823);
          return;
        }
      }
      *(_BYTE *)(v1 + 159) = 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), v7);
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 24); *(_QWORD *)(v12 + 232) = v1 )
    {
      v12 = *(_QWORD *)(*((_QWORD *)this + 15) + 8 * i);
      i = (unsigned int)(i + 1);
    }
    *(_QWORD *)(*((_QWORD *)this + 14) + 16LL) = *((_QWORD *)this + 7);
    v13 = 0x10000;
    if ( (unsigned __int64)(*((_QWORD *)this + 7) + 0x10000LL) > *((_QWORD *)this + 6) )
      v13 = *((_DWORD *)this + 12) - *((_DWORD *)this + 14);
    *(_DWORD *)(*((_QWORD *)this + 14) + 8LL) = v13;
    *(_QWORD *)(*((_QWORD *)this + 14) + 56LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 14) + 232LL) = v1;
    *(_QWORD *)(*((_QWORD *)this + 14) + 40LL) = VmxpMirrorRegenerationPhase1;
    VMX_OVERLAPPED_IO_MANAGER::AcquireIoRegion(
      (VMX_OVERLAPPED_IO_MANAGER *)(v1 + 104),
      *((struct VMX_OVERLAP_TRANSFER_PACKET **)this + 14),
      1);
  }
  else
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
    (*(void (__fastcall **)(VMX_MIRROR_REGENERATION_TASK *))(*(_QWORD *)this + 16LL))(this);
    v5 = (VMX_MIRROR_REGENERATION_TASK **)*((_QWORD *)this + 1);
    if ( v5[1] != (VMX_MIRROR_REGENERATION_TASK *)((char *)this + 8)
      || (v6 = (VMX_MIRROR_REGENERATION_TASK **)*((_QWORD *)this + 2),
          *v6 != (VMX_MIRROR_REGENERATION_TASK *)((char *)this + 8)) )
    {
      __fastfail(3u);
    }
    *v6 = (VMX_MIRROR_REGENERATION_TASK *)v5;
    v5[1] = (VMX_MIRROR_REGENERATION_TASK *)v6;
    KeReleaseSpinLock(v3, v4);
    (*(void (__fastcall **)(VMX_MIRROR_REGENERATION_TASK *))(*(_QWORD *)this + 24LL))(this);
    (**(void (__fastcall ***)(VMX_MIRROR_REGENERATION_TASK *, __int64))this)(this, 1);
  }
}

```

## disassembly

```asm
0x1400116d0  push    rbx
0x1400116d2  push    rbp
0x1400116d3  push    rsi
0x1400116d4  push    rdi
0x1400116d5  push    r12
0x1400116d7  push    r14
0x1400116d9  push    r15
0x1400116db  sub     rsp, 20h
0x1400116df  mov     rdi, [rcx+20h]
0x1400116e3  mov     rbx, rcx
0x1400116e6  mov     rax, [rcx+30h]
0x1400116ea  lea     rsi, [rdi+18h]
0x1400116ee  cmp     [rcx+38h], rax
0x1400116f2  jb      short loc_140011772
0x1400116f4  mov     rcx, rsi; SpinLock
0x1400116f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400116fe  nop     dword ptr [rax+rax+00h]
0x140011703  mov     rdx, [rbx]
0x140011706  mov     rcx, rbx
0x140011709  mov     dil, al
0x14001170c  mov     rax, [rdx+10h]
0x140011710  call    _guard_dispatch_icall
0x140011715  lea     rcx, [rbx+8]
0x140011719  mov     r8, [rcx]
0x14001171c  cmp     [r8+8], rcx
0x140011720  jnz     short loc_14001176B
0x140011722  mov     rdx, [rcx+8]
0x140011726  cmp     [rdx], rcx
0x140011729  jnz     short loc_14001176B
0x14001172b  mov     [rdx], r8
0x14001172e  mov     rcx, rsi; SpinLock
0x140011731  mov     [r8+8], rdx
0x140011735  mov     dl, dil; NewIrql
0x140011738  call    cs:__imp_KeReleaseSpinLock
0x14001173f  nop     dword ptr [rax+rax+00h]
0x140011744  mov     rax, [rbx]
0x140011747  mov     rcx, rbx
0x14001174a  mov     rax, [rax+18h]
0x14001174e  call    _guard_dispatch_icall
0x140011753  mov     rax, [rbx]
0x140011756  mov     edx, 1
0x14001175b  mov     rcx, rbx
0x14001175e  mov     rax, [rax]
0x140011761  call    _guard_dispatch_icall
0x140011766  jmp     loc_1400118C1
0x14001176b  mov     ecx, 3
0x140011770  int     29h; Win8: RtlFailFast(ecx)
0x140011772  mov     rax, [rcx+80h]
0x140011779  mov     [rax+30h], rdi
0x14001177d  mov     rax, [rcx+80h]
0x140011784  mov     rcx, rsi; SpinLock
0x140011787  mov     dword ptr [rax+0A8h], 0
0x140011791  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011798  nop     dword ptr [rax+rax+00h]
0x14001179d  cmp     byte ptr [rdi+9Fh], 0
0x1400117a4  mov     r12b, al
0x1400117a7  jz      loc_140011831
0x1400117ad  mov     rbp, [rdi+60h]
0x1400117b1  xor     r14d, r14d
0x1400117b4  mov     r15b, 1
0x1400117b7  cmp     [rdi+38h], r14d
0x1400117bb  jbe     short loc_14001182A
0x1400117bd  cmp     byte ptr [rbp+14h], 0
0x1400117c1  jz      short loc_1400117ED
0x1400117c3  cmp     dword ptr [rbp+10h], 4
0x1400117c7  jz      short loc_1400117ED
0x1400117c9  mov     r8b, 1; unsigned __int8
0x1400117cc  mov     edx, r14d; unsigned int
0x1400117cf  mov     rcx, rdi; this
0x1400117d2  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x1400117d7  test    al, al
0x1400117d9  jz      short loc_1400117EA
0x1400117db  mov     rax, [rbx+80h]
0x1400117e2  inc     dword ptr [rax+0A8h]
0x1400117e8  jmp     short loc_1400117ED
0x1400117ea  xor     r15b, r15b
0x1400117ed  inc     r14d
0x1400117f0  add     rbp, 28h ; '('
0x1400117f4  cmp     r14d, [rdi+38h]
0x1400117f8  jb      short loc_1400117BD
0x1400117fa  test    r15b, r15b
0x1400117fd  jnz     short loc_14001182A
0x1400117ff  mov     dl, r12b; NewIrql
0x140011802  mov     byte ptr [rdi+9Eh], 1
0x140011809  mov     rcx, rsi; SpinLock
0x14001180c  call    cs:__imp_KeReleaseSpinLock
0x140011813  nop     dword ptr [rax+rax+00h]
0x140011818  mov     edx, 0C0000001h; int
0x14001181d  mov     rcx, rbx; this
0x140011820  call    ?IterationCompletion@VMX_MIRROR_REGENERATION_TASK@@QEAAXJ@Z; VMX_MIRROR_REGENERATION_TASK::IterationCompletion(long)
0x140011825  jmp     loc_1400118C1
0x14001182a  mov     byte ptr [rdi+9Fh], 0
0x140011831  mov     dl, r12b; NewIrql
0x140011834  mov     rcx, rsi; SpinLock
0x140011837  call    cs:__imp_KeReleaseSpinLock
0x14001183e  nop     dword ptr [rax+rax+00h]
0x140011843  xor     edx, edx
0x140011845  cmp     [rbx+60h], edx
0x140011848  jbe     short loc_140011860
0x14001184a  mov     rax, [rbx+78h]
0x14001184e  mov     rcx, [rax+rdx*8]
0x140011852  inc     edx
0x140011854  mov     [rcx+0E8h], rdi
0x14001185b  cmp     edx, [rbx+60h]
0x14001185e  jb      short loc_14001184A
0x140011860  mov     rcx, [rbx+70h]
0x140011864  mov     rax, [rbx+38h]
0x140011868  mov     [rcx+10h], rax
0x14001186c  mov     ecx, 10000h
0x140011871  mov     rax, [rbx+38h]
0x140011875  add     rax, rcx
0x140011878  cmp     rax, [rbx+30h]
0x14001187c  mov     rax, [rbx+70h]
0x140011880  jbe     short loc_140011888
0x140011882  mov     ecx, [rbx+30h]
0x140011885  sub     ecx, [rbx+38h]
0x140011888  mov     [rax+8], ecx
0x14001188b  mov     r8b, 1; unsigned __int8
0x14001188e  mov     rax, [rbx+70h]
0x140011892  lea     rcx, ?VmxpMirrorRegenerationPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRegenerationPhase1(VMX_TRANSFER_PACKET *)
0x140011899  mov     qword ptr [rax+38h], 0
0x1400118a1  mov     rax, [rbx+70h]
0x1400118a5  mov     [rax+0E8h], rdi
0x1400118ac  mov     rax, [rbx+70h]
0x1400118b0  mov     [rax+28h], rcx
0x1400118b4  lea     rcx, [rdi+68h]; this
0x1400118b8  mov     rdx, [rbx+70h]; struct VMX_OVERLAP_TRANSFER_PACKET *
0x1400118bc  call    ?AcquireIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@E@Z; VMX_OVERLAPPED_IO_MANAGER::AcquireIoRegion(VMX_OVERLAP_TRANSFER_PACKET *,uchar)
0x1400118c1  add     rsp, 20h
0x1400118c5  pop     r15
0x1400118c7  pop     r14
0x1400118c9  pop     r12
0x1400118cb  pop     rdi
0x1400118cc  pop     rsi
0x1400118cd  pop     rbp
0x1400118ce  pop     rbx
0x1400118cf  retn
```
