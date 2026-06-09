# VMX_IO_MIRROR::LaunchRead(VMX_TRANSFER_PACKET *,VMX_MIRROR_TRANSFER_PACKET *)

- ea: `0x140001ea0`
- end: `0x14000246a`
- name: `?LaunchRead@VMX_IO_MIRROR@@QEAAEPEAVVMX_TRANSFER_PACKET@@PEAVVMX_MIRROR_TRANSFER_PACKET@@@Z`
- size: `1482`
- prototype: `unsigned __int8 __fastcall(VMX_IO_MIRROR *__hidden this, struct VMX_TRANSFER_PACKET *, struct VMX_MIRROR_TRANSFER_PACKET *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001ab0`
- `0x140003774`

## callees

- `0x140001ea0`
- `0x140003bd8`
- `0x140009fcc`
- `0x14000d078`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002057`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001f11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002057`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001fe3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000209e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000220d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002357`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001fe3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000209e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000220d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400022c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002357`

## pseudocode

```c
unsigned __int8 __fastcall VMX_IO_MIRROR::LaunchRead(
        VMX_IO_MIRROR *this,
        struct VMX_TRANSFER_PACKET *a2,
        struct VMX_MIRROR_TRANSFER_PACKET *a3)
{
  KSPIN_LOCK *v3; // r14
  char v7; // al
  KIRQL v8; // al
  KIRQL v9; // r15
  unsigned int v10; // ebp
  __int64 *i; // rcx
  char v12; // al
  __int64 v13; // rax
  __int64 v14; // rax
  bool v15; // zf
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdi
  KSPIN_LOCK *v20; // rbp
  KIRQL v21; // al
  _QWORD *v22; // rcx
  _QWORD *k; // rsi
  unsigned int v25; // r8d
  __int64 v26; // r9
  unsigned int v27; // r10d
  unsigned __int64 v28; // r12
  __int64 v29; // rcx
  unsigned int v30; // esi
  unsigned int j; // edx
  unsigned int v32; // r10d
  unsigned __int64 v33; // r11
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // r8
  unsigned __int64 v37; // r9
  __int64 v38; // rdx
  char *v39; // rdi
  char **v40; // rcx
  void (__fastcall *v41)(struct VMX_TRANSFER_PACKET *); // rax
  char v42; // al
  __int64 v43; // r12
  unsigned int v44; // r13d
  char v45; // [rsp+50h] [rbp+8h]

  v3 = (KSPIN_LOCK *)((char *)this + 24);
  *((_QWORD *)a3 + 3) = *((_QWORD *)a2 + 3);
  *((_QWORD *)a3 + 4) = *((_QWORD *)a2 + 4);
  *((_DWORD *)a3 + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)a3 + 2) = *((_QWORD *)a2 + 2);
  *((_QWORD *)a3 + 7) = *((_QWORD *)a2 + 7);
  *((_DWORD *)a3 + 16) = *((_DWORD *)a2 + 16);
  *((_QWORD *)a3 + 9) = *((_QWORD *)a2 + 9);
  v7 = *((_BYTE *)a2 + 81);
  *((_QWORD *)a3 + 29) = this;
  *((_BYTE *)a3 + 81) = v7;
  *((_BYTE *)a3 + 82) = 1;
  *((_QWORD *)a3 + 28) = a2;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 3);
  v9 = v8;
  if ( *((_BYTE *)this + 158) )
  {
    KeReleaseSpinLock(v3, v8);
    v41 = (void (__fastcall *)(struct VMX_TRANSFER_PACKET *))*((_QWORD *)a2 + 5);
    *((_QWORD *)a2 + 13) = 0;
    *((_DWORD *)a2 + 24) = -1073741435;
    v41(a2);
    return 0;
  }
  else
  {
    if ( !*((_DWORD *)this + 38) )
    {
      v10 = 0;
      if ( *((_BYTE *)this + 159) )
      {
        v42 = 1;
        v43 = *((_QWORD *)this + 12);
        v44 = 0;
        v45 = 1;
        if ( *((_DWORD *)this + 14) )
        {
          do
          {
            if ( *(_BYTE *)(v43 + 20) && *(_DWORD *)(v43 + 16) != 4 )
            {
              if ( VMX_IO_MIRROR::DetachFaultTolerantMember(this, v44, 1u) )
              {
                ++*((_DWORD *)a2 + 42);
                v42 = v45;
              }
              else
              {
                v42 = 0;
                v45 = 0;
              }
            }
            ++v44;
            v43 += 40;
          }
          while ( v44 < *((_DWORD *)this + 14) );
          if ( !v42 )
          {
            *((_BYTE *)this + 158) = 1;
            KeReleaseSpinLock(v3, v9);
            *((_DWORD *)a2 + 24) = -1073741435;
            *((_QWORD *)a2 + 13) = 0;
            if ( *((_DWORD *)a2 + 42) )
            {
LABEL_50:
              *((_QWORD *)a2 + 19) = VmxpMirrorLogDetachOperation;
              *((_QWORD *)a2 + 20) = VmxpMirrorLogDetachCompletion;
              VMX_LOG::QueueLogPacket(*((VMX_LOG **)this + 16), a2);
              return 0;
            }
LABEL_54:
            (*((void (__fastcall **)(struct VMX_TRANSFER_PACKET *))a2 + 5))(a2);
            return 0;
          }
        }
        *((_BYTE *)this + 159) = 0;
      }
      if ( *((_BYTE *)this + 156) )
      {
        for ( i = (__int64 *)*((_QWORD *)this + 4); i != (__int64 *)((char *)this + 32); i = (__int64 *)*i )
        {
          if ( !*((_DWORD *)i + 4) )
          {
            if ( i[6] >= *((_QWORD *)a3 + 2) + (unsigned __int64)*((unsigned int *)a3 + 2) )
              goto LABEL_10;
            break;
          }
        }
        *((_BYTE *)a3 + 274) = 1;
      }
LABEL_10:
      v12 = *((_BYTE *)a2 + 83);
      if ( *((_BYTE *)a3 + 274) )
      {
        if ( v12 )
          *((_BYTE *)a2 + 83) = 0;
        v13 = *((_QWORD *)this + 12);
        while ( v10 < *((_DWORD *)this + 14) )
        {
          if ( !*(_DWORD *)(v13 + 16) )
            goto LABEL_16;
          ++v10;
          v13 += 40;
        }
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 16, WPP_43c4c1db85da3f20b60669b3f7220105_Traceguids);
        }
LABEL_16:
        *((_DWORD *)a3 + 60) = v10;
        goto LABEL_17;
      }
      if ( !v12 )
      {
        v25 = *((_DWORD *)this + 14);
        v26 = *((_QWORD *)this + 12);
        v27 = -1;
        v28 = *((_QWORD *)a3 + 2);
        v29 = v26;
        v30 = v25;
        for ( j = 0; j < v25; v29 += 40 )
        {
          if ( !*(_DWORD *)(v29 + 16) && *(_DWORD *)(v29 + 28) < v27 )
            v27 = *(_DWORD *)(v29 + 28);
          ++j;
        }
        v32 = v27 + 4;
        if ( v32 < 4 )
          v32 = -1;
        v33 = -1;
        if ( !v25 )
          goto LABEL_77;
        do
        {
          if ( !*(_DWORD *)(v26 + 16) && *(_DWORD *)(v26 + 28) <= v32 )
          {
            v34 = *(_QWORD *)(v26 + 32);
            v35 = v28 - v34;
            if ( v34 >= v28 )
              v35 = *(_QWORD *)(v26 + 32) - v28;
            if ( v35 < v33 )
            {
              v30 = v10;
              if ( !v35 )
                goto LABEL_41;
              v33 = v35;
            }
          }
          ++v10;
          v26 += 40;
        }
        while ( v10 < v25 );
        if ( v30 == v25 )
        {
LABEL_77:
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 17, WPP_43c4c1db85da3f20b60669b3f7220105_Traceguids);
          }
        }
LABEL_41:
        *((_DWORD *)a3 + 60) = v30;
        v10 = v30;
        goto LABEL_17;
      }
      v38 = *((unsigned int *)a2 + 21);
      if ( (unsigned int)v38 < *((_DWORD *)this + 14) && !*(_DWORD *)(*((_QWORD *)this + 12) + 40 * v38 + 16) )
      {
        *((_DWORD *)a3 + 60) = v38;
        v10 = v38;
LABEL_17:
        v14 = *((_QWORD *)this + 12);
        ++*(_DWORD *)(v14 + 40LL * v10 + 28);
        *(_QWORD *)(v14 + 40LL * v10 + 32) = *((_QWORD *)a3 + 2) + *((unsigned int *)a3 + 2);
        KeReleaseSpinLock(v3, v9);
        v15 = *((_BYTE *)a3 + 274) == 0;
        v16 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * *((unsigned int *)a3 + 60));
        *((_QWORD *)a3 + 6) = v16;
        if ( v15 )
        {
          *((_DWORD *)a3 + 3) = 16842753;
          *((_QWORD *)a3 + 5) = VmxpMirrorTransferCompletionRoutine;
          (*(void (__fastcall **)(__int64, struct VMX_MIRROR_TRANSFER_PACKET *))(*(_QWORD *)v16 + 8LL))(v16, a3);
          return 1;
        }
        *((_BYTE *)a3 + 176) = 1;
        *((_QWORD *)a3 + 27) = (char *)this + 104;
        *((_QWORD *)a3 + 5) = VmxpMirrorReadWriteBackPhase1;
        v17 = *((_QWORD *)a3 + 2) / (unsigned __int64)*((unsigned int *)this + 27) % *((unsigned int *)this + 26);
        v18 = *((_QWORD *)this + 14);
        v19 = *((_QWORD *)this + 15) + 16LL * (unsigned int)v17;
        v20 = (KSPIN_LOCK *)(v18 + 8LL * (unsigned int)v17);
        v21 = KeAcquireSpinLockRaiseToDpc(v20);
        v22 = *(_QWORD **)(v19 + 8);
        for ( k = v22; k != (_QWORD *)v19; k = (_QWORD *)k[1] )
        {
          if ( *((_BYTE *)a3 + 176) || *((_BYTE *)k - 8) || *(k - 17) == *((_QWORD *)a3 + 6) )
          {
            v36 = *((_QWORD *)a3 + 2);
            v37 = *(k - 21);
            if ( v37 < v36 + *((unsigned int *)a3 + 2) && v36 < v37 + *((unsigned int *)k - 44) )
              break;
          }
        }
        if ( *v22 == v19 )
        {
          *((_QWORD *)a3 + 24) = v22;
          *((_QWORD *)a3 + 23) = v19;
          *v22 = (char *)a3 + 184;
          *(_QWORD *)(v19 + 8) = (char *)a3 + 184;
          *((_BYTE *)a3 + 177) = 1;
          KeReleaseSpinLock(v20, v21);
          if ( k == (_QWORD *)v19 )
            (*((void (__fastcall **)(struct VMX_MIRROR_TRANSFER_PACKET *))a3 + 5))(a3);
          return 1;
        }
LABEL_82:
        __fastfail(3u);
      }
      KeReleaseSpinLock(v3, v9);
      *((_DWORD *)a2 + 24) = -1073741811;
      *((_QWORD *)a2 + 13) = 0;
      if ( *((_DWORD *)a2 + 42) )
        goto LABEL_50;
      goto LABEL_54;
    }
    v39 = (char *)this + 136;
    v40 = (char **)*((_QWORD *)v39 + 1);
    if ( *v40 != v39 )
      goto LABEL_82;
    *((_QWORD *)a2 + 15) = v40;
    *((_QWORD *)a2 + 14) = v39;
    *v40 = (char *)a2 + 112;
    *((_QWORD *)v39 + 1) = (char *)a2 + 112;
    KeReleaseSpinLock(v3, v8);
    return 0;
  }
}

```

## disassembly

```asm
0x140001ea0  mov     [rsp+arg_18], rbx
0x140001ea5  push    rbp
0x140001ea6  push    rsi
0x140001ea7  push    rdi
0x140001ea8  push    r14
0x140001eaa  push    r15
0x140001eac  sub     rsp, 20h
0x140001eb0  mov     rax, [rdx+18h]
0x140001eb4  lea     r14, [rcx+18h]
0x140001eb8  mov     [r8+18h], rax
0x140001ebc  mov     rdi, rcx
0x140001ebf  mov     rax, [rdx+20h]
0x140001ec3  mov     rbx, r8
0x140001ec6  mov     [r8+20h], rax
0x140001eca  mov     rsi, rdx
0x140001ecd  mov     eax, [rdx+8]
0x140001ed0  mov     [r8+8], eax
0x140001ed4  mov     rax, [rdx+10h]
0x140001ed8  mov     [r8+10h], rax
0x140001edc  mov     rax, [rdx+38h]
0x140001ee0  mov     [r8+38h], rax
0x140001ee4  mov     eax, [rdx+40h]
0x140001ee7  mov     [r8+40h], eax
0x140001eeb  mov     rax, [rdx+48h]
0x140001eef  mov     [r8+48h], rax
0x140001ef3  movzx   eax, byte ptr [rdx+51h]
0x140001ef7  mov     [r8+0E8h], rcx
0x140001efe  mov     rcx, r14; SpinLock
0x140001f01  mov     [r8+51h], al
0x140001f05  mov     byte ptr [r8+52h], 1
0x140001f0a  mov     [r8+0E0h], rdx
0x140001f11  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001f18  nop     dword ptr [rax+rax+00h]
0x140001f1d  cmp     byte ptr [rdi+9Eh], 0
0x140001f24  movzx   r15d, al
0x140001f28  jnz     loc_1400022BF
0x140001f2e  cmp     dword ptr [rdi+98h], 0
0x140001f35  mov     [rsp+48h+arg_8], r12
0x140001f3a  mov     [rsp+48h+arg_10], r13
0x140001f3f  jnz     loc_14000227F
0x140001f45  xor     ebp, ebp
0x140001f47  cmp     [rdi+9Fh], bpl
0x140001f4e  jnz     loc_1400022F2
0x140001f54  cmp     [rdi+9Ch], bpl
0x140001f5b  jz      short loc_140001F87
0x140001f5d  mov     rcx, [rdi+20h]
0x140001f61  lea     rax, [rdi+20h]
0x140001f65  cmp     rcx, rax
0x140001f68  jz      short loc_140001F80
0x140001f6a  cmp     [rcx+10h], ebp
0x140001f6d  jnz     loc_140002269
0x140001f73  mov     eax, [rbx+8]
0x140001f76  add     rax, [rbx+10h]
0x140001f7a  cmp     [rcx+30h], rax
0x140001f7e  jnb     short loc_140001F87
0x140001f80  mov     byte ptr [rbx+112h], 1
0x140001f87  movzx   eax, byte ptr [rsi+53h]
0x140001f8b  cmp     [rbx+112h], bpl
0x140001f92  jz      loc_1400020D9
0x140001f98  test    al, al
0x140001f9a  jnz     loc_14000238B
0x140001fa0  mov     rax, [rdi+60h]
0x140001fa4  mov     ecx, [rdi+38h]
0x140001fa7  cmp     ebp, ecx
0x140001fa9  jnb     loc_140002394
0x140001faf  cmp     dword ptr [rax+10h], 0
0x140001fb3  jnz     loc_14000225E
0x140001fb9  mov     [rbx+0F0h], ebp
0x140001fbf  mov     eax, ebp
0x140001fc1  lea     rcx, [rax+rax*4]
0x140001fc5  mov     rax, [rdi+60h]
0x140001fc9  inc     dword ptr [rax+rcx*8+1Ch]
0x140001fcd  lea     rdx, [rax+rcx*8]
0x140001fd1  mov     eax, [rbx+8]
0x140001fd4  add     rax, [rbx+10h]
0x140001fd8  mov     rcx, r14; SpinLock
0x140001fdb  mov     [rdx+20h], rax
0x140001fdf  movzx   edx, r15b; NewIrql
0x140001fe3  call    cs:__imp_KeReleaseSpinLock
0x140001fea  nop     dword ptr [rax+rax+00h]
0x140001fef  cmp     byte ptr [rbx+112h], 0
0x140001ff6  mov     rax, [rdi+30h]
0x140001ffa  mov     ecx, [rbx+0F0h]
0x140002000  mov     rcx, [rax+rcx*8]
0x140002004  mov     [rbx+30h], rcx
0x140002008  jz      loc_1400021D4
0x14000200e  lea     r8, [rdi+68h]
0x140002012  mov     byte ptr [rbx+0B0h], 1
0x140002019  mov     [rbx+0D8h], r8
0x140002020  lea     rax, ?VmxpMirrorReadWriteBackPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorReadWriteBackPhase1(VMX_TRANSFER_PACKET *)
0x140002027  mov     [rbx+28h], rax
0x14000202b  xor     edx, edx
0x14000202d  mov     ecx, [r8+4]
0x140002031  mov     rax, [rbx+10h]
0x140002035  div     rcx
0x140002038  mov     ecx, [r8]
0x14000203b  xor     edx, edx
0x14000203d  div     rcx
0x140002040  mov     rax, [r8+8]
0x140002044  mov     ecx, edx
0x140002046  mov     edi, edx
0x140002048  shl     rdi, 4
0x14000204c  add     rdi, [r8+10h]
0x140002050  lea     rbp, [rax+rcx*8]
0x140002054  mov     rcx, rbp; SpinLock
0x140002057  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000205e  nop     dword ptr [rax+rax+00h]
0x140002063  mov     rcx, [rdi+8]
0x140002067  movzx   edx, al; NewIrql
0x14000206a  mov     rsi, rcx
0x14000206d  cmp     rcx, rdi
0x140002070  jnz     loc_14000218D
0x140002076  cmp     [rcx], rdi
0x140002079  jnz     loc_140002463
0x14000207f  lea     rax, [rbx+0B8h]
0x140002086  mov     [rax+8], rcx
0x14000208a  mov     [rax], rdi
0x14000208d  mov     [rcx], rax
0x140002090  mov     rcx, rbp; SpinLock
0x140002093  mov     [rdi+8], rax
0x140002097  mov     byte ptr [rbx+0B1h], 1
0x14000209e  call    cs:__imp_KeReleaseSpinLock
0x1400020a5  nop     dword ptr [rax+rax+00h]
0x1400020aa  cmp     rsi, rdi
0x1400020ad  jnz     short loc_1400020BB
0x1400020af  mov     rax, [rbx+28h]
0x1400020b3  mov     rcx, rbx
0x1400020b6  call    _guard_dispatch_icall
0x1400020bb  mov     al, 1
0x1400020bd  mov     r12, [rsp+48h+arg_8]
0x1400020c2  mov     r13, [rsp+48h+arg_10]
0x1400020c7  mov     rbx, [rsp+48h+arg_18]
0x1400020cc  add     rsp, 20h
0x1400020d0  pop     r15
0x1400020d2  pop     r14
0x1400020d4  pop     rdi
0x1400020d5  pop     rsi
0x1400020d6  pop     rbp
0x1400020d7  retn
0x1400020d9  test    al, al
0x1400020db  jnz     loc_1400021FA
0x1400020e1  mov     r8d, [rdi+38h]
0x1400020e5  mov     r11d, 0FFFFFFFFh
0x1400020eb  mov     r9, [rdi+60h]
0x1400020ef  mov     r10d, r11d
0x1400020f2  mov     r12, [rbx+10h]
0x1400020f6  mov     rcx, r9
0x1400020f9  mov     esi, r8d
0x1400020fc  mov     edx, ebp
0x1400020fe  test    r8d, r8d
0x140002101  jz      short loc_14000211D
0x140002103  cmp     [rcx+10h], ebp
0x140002106  jnz     short loc_140002112
0x140002108  mov     eax, [rcx+1Ch]
0x14000210b  cmp     eax, r10d
0x14000210e  cmovb   r10d, eax
0x140002112  inc     edx
0x140002114  add     rcx, 28h ; '('
0x140002118  cmp     edx, r8d
0x14000211b  jb      short loc_140002103
0x14000211d  add     r10d, 4
0x140002121  cmp     r10d, 4
0x140002125  cmovb   r10d, r11d
0x140002129  mov     r11, 0FFFFFFFFFFFFFFFFh
0x140002130  test    r8d, r8d
0x140002133  jz      loc_1400023FB
0x140002139  cmp     dword ptr [r9+10h], 0
0x14000213e  jnz     short loc_14000216C
0x140002140  cmp     [r9+1Ch], r10d
0x140002144  ja      short loc_14000216C
0x140002146  mov     rax, [r9+20h]
0x14000214a  mov     rdx, r12
0x14000214d  sub     rdx, rax
0x140002150  mov     rcx, rax
0x140002153  sub     rcx, r12
0x140002156  cmp     rax, r12
0x140002159  cmovnb  rdx, rcx
0x14000215d  cmp     rdx, r11
0x140002160  jnb     short loc_14000216C
0x140002162  mov     esi, ebp
0x140002164  test    rdx, rdx
0x140002167  jz      short loc_140002180
0x140002169  mov     r11, rdx
0x14000216c  inc     ebp
0x14000216e  add     r9, 28h ; '('
0x140002172  cmp     ebp, r8d
0x140002175  jb      short loc_140002139
0x140002177  cmp     esi, r8d
0x14000217a  jz      loc_1400023FB
0x140002180  mov     [rbx+0F0h], esi
0x140002186  mov     ebp, esi
0x140002188  jmp     loc_140001FBF
0x14000218d  movzx   r10d, byte ptr [rbx+0B0h]
0x140002195  test    r10b, r10b
0x140002198  jz      loc_140002443
0x14000219e  mov     r8, [rbx+10h]
0x1400021a2  mov     eax, [rbx+8]
0x1400021a5  mov     r9, [rsi-0A8h]
0x1400021ac  add     rax, r8
0x1400021af  cmp     r9, rax
0x1400021b2  jnb     short loc_1400021C6
0x1400021b4  mov     eax, [rsi-0B0h]
0x1400021ba  add     rax, r9
0x1400021bd  cmp     r8, rax
0x1400021c0  jb      loc_140002076
0x1400021c6  mov     rsi, [rsi+8]
0x1400021ca  cmp     rsi, rdi
0x1400021cd  jnz     short loc_140002195
0x1400021cf  jmp     loc_140002076
0x1400021d4  lea     rax, ?VmxpMirrorTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorTransferCompletionRoutine(VMX_TRANSFER_PACKET *)
0x1400021db  mov     dword ptr [rbx+0Ch], 1010001h
0x1400021e2  mov     [rbx+28h], rax
0x1400021e6  mov     rdx, rbx
0x1400021e9  mov     rax, [rcx]
0x1400021ec  mov     rax, [rax+8]
0x1400021f0  call    _guard_dispatch_icall
0x1400021f5  jmp     loc_1400020BB
0x1400021fa  mov     edx, [rsi+54h]
0x1400021fd  cmp     edx, [rdi+38h]
0x140002200  jb      loc_1400023DC
0x140002206  movzx   edx, r15b; NewIrql
0x14000220a  mov     rcx, r14; SpinLock
0x14000220d  call    cs:__imp_KeReleaseSpinLock
0x140002214  nop     dword ptr [rax+rax+00h]
0x140002219  mov     dword ptr [rsi+60h], 0C000000Dh
0x140002220  mov     [rsi+68h], rbp
0x140002224  cmp     [rsi+0A8h], ebp
0x14000222a  jbe     short loc_140002271
0x14000222c  lea     rax, ?VmxpMirrorLogDetachOperation@@YAJPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VmxpMirrorLogDetachOperation(VMX_LOG_TRANSFER_PACKET *)
0x140002233  mov     rdx, rsi; struct VMX_LOG_TRANSFER_PACKET *
0x140002236  mov     [rsi+98h], rax
0x14000223d  lea     rax, ?VmxpMirrorLogDetachCompletion@@YAXPEAVVMX_LOG_TRANSFER_PACKET@@J@Z; VmxpMirrorLogDetachCompletion(VMX_LOG_TRANSFER_PACKET *,long)
0x140002244  mov     [rsi+0A0h], rax
0x14000224b  mov     rcx, [rdi+80h]; this
0x140002252  call    ?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z; VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)
0x140002257  xor     al, al
0x140002259  jmp     loc_1400020BD
0x14000225e  inc     ebp
0x140002260  add     rax, 28h ; '('
0x140002264  jmp     loc_140001FA7
0x140002269  mov     rcx, [rcx]
0x14000226c  jmp     loc_140001F65
0x140002271  mov     rax, [rsi+28h]
0x140002275  mov     rcx, rsi
0x140002278  call    _guard_dispatch_icall
0x14000227d  jmp     short loc_140002257
0x14000227f  add     rdi, 88h
0x140002286  mov     rcx, [rdi+8]
0x14000228a  cmp     [rcx], rdi
0x14000228d  jnz     loc_140002463
0x140002293  lea     rax, [rsi+70h]
0x140002297  movzx   edx, r15b; NewIrql
0x14000229b  mov     [rax+8], rcx
0x14000229f  mov     [rax], rdi
0x1400022a2  mov     [rcx], rax
0x1400022a5  mov     rcx, r14; SpinLock
0x1400022a8  mov     [rdi+8], rax
0x1400022ac  call    cs:__imp_KeReleaseSpinLock
0x1400022b3  nop     dword ptr [rax+rax+00h]
0x1400022b8  xor     al, al
0x1400022ba  jmp     loc_1400020BD
0x1400022bf  movzx   edx, r15b; NewIrql
0x1400022c3  mov     rcx, r14; SpinLock
0x1400022c6  call    cs:__imp_KeReleaseSpinLock
0x1400022cd  nop     dword ptr [rax+rax+00h]
0x1400022d2  mov     rax, [rsi+28h]
0x1400022d6  xor     ebp, ebp
0x1400022d8  mov     rcx, rsi
0x1400022db  mov     [rsi+68h], rbp
0x1400022df  mov     dword ptr [rsi+60h], 0C0000185h
0x1400022e6  call    _guard_dispatch_icall
0x1400022eb  xor     al, al
0x1400022ed  jmp     loc_1400020C7
0x1400022f2  mov     al, 1
0x1400022f4  mov     r12, [rdi+60h]
0x1400022f8  mov     r13d, ebp
0x1400022fb  mov     [rsp+48h+arg_0], al
0x1400022ff  cmp     [rdi+38h], ebp
0x140002302  jbe     short loc_14000237F
0x140002304  cmp     [r12+14h], bpl
0x140002309  jz      short loc_140002338
0x14000230b  cmp     dword ptr [r12+10h], 4
0x140002311  jz      short loc_140002338
0x140002313  mov     r8b, 1; unsigned __int8
0x140002316  mov     edx, r13d; unsigned int
0x140002319  mov     rcx, rdi; this
0x14000231c  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x140002321  test    al, al
0x140002323  jz      short loc_140002332
0x140002325  inc     dword ptr [rsi+0A8h]
0x14000232b  movzx   eax, [rsp+48h+arg_0]
0x140002330  jmp     short loc_140002338
0x140002332  xor     al, al
0x140002334  mov     [rsp+48h+arg_0], al
0x140002338  inc     r13d
0x14000233b  add     r12, 28h ; '('
0x14000233f  cmp     r13d, [rdi+38h]
0x140002343  jb      short loc_140002304
0x140002345  test    al, al
0x140002347  jnz     short loc_14000237F
  ... truncated ...
```
