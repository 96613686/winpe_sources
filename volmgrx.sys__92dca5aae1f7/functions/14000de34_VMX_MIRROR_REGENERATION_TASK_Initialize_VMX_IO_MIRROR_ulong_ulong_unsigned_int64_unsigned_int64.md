# VMX_MIRROR_REGENERATION_TASK::Initialize(VMX_IO_MIRROR *,ulong,ulong *,unsigned __int64,unsigned __int64)

- ea: `0x14000de34`
- end: `0x14000e07f`
- name: `?Initialize@VMX_MIRROR_REGENERATION_TASK@@QEAAJPEAVVMX_IO_MIRROR@@KPEAK_K2@Z`
- size: `587`
- prototype: `__int64 __fastcall(struct _KEVENT *this, struct _LIST_ENTRY *, LONG, struct _LIST_ENTRY *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000ba90`

## callees

- `0x140002470`
- `0x14000b420`
- `0x14000de34`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000df43`
- `ntoskrnl!ExAllocatePool2` at `0x14000df43`
- `ntoskrnl!KeInitializeEvent` at `0x14000de7d`
- `ntoskrnl!KeInitializeEvent` at `0x14000de7d`

## pseudocode

```c
__int64 __fastcall VMX_MIRROR_REGENERATION_TASK::Initialize(
        struct _KEVENT *this,
        struct _LIST_ENTRY *a2,
        LONG a3,
        struct _LIST_ENTRY *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  struct _LIST_ENTRY *v8; // rax
  __int64 result; // rax
  void *Pool2; // rax
  unsigned int v11; // edi
  _BYTE *v12; // rax
  __int64 v13; // rcx
  struct _LIST_ENTRY *v14; // rax

  this[1].Header.WaitListHead.Flink = a2;
  this[4].Header.LockNV = a3;
  this[2].Header.WaitListHead.Flink = 0;
  this[1].Header.WaitListHead.Blink = 0;
  *(_QWORD *)&this[2].Header.Lock = a6;
  LOWORD(this[2].Header.WaitListHead.Blink) = 0;
  BYTE2(this[2].Header.WaitListHead.Blink) = 0;
  this[1].Header.LockNV = 1;
  KeInitializeEvent(this + 3, NotificationEvent, 0);
  v8 = (struct _LIST_ENTRY *)VMX_TRANSFER_PACKET::operator new(0x128u);
  if ( v8 )
  {
    v8[2].Flink = 0;
    v8[1].Blink = 0;
    BYTE3(v8[5].Flink) = 0;
    WORD2(v8[8].Flink) = 0;
    v8[13].Blink = 0;
    BYTE1(v8[11].Flink) = 0;
    v8->Flink = (struct _LIST_ENTRY *)&VMX_RAID5_TRANSFER_PACKET::`vftable';
    LOWORD(v8[17].Flink) = 0;
    BYTE2(v8[17].Flink) = 0;
  }
  else
  {
    v8 = 0;
  }
  this[4].Header.WaitListHead.Blink = v8;
  if ( !v8 )
    return 3221225626LL;
  result = VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v8, 0x10000u);
  if ( (int)result < 0 )
    return result;
  LODWORD(this[4].Header.WaitListHead.Blink[4].Flink) = 0;
  this[4].Header.WaitListHead.Blink[4].Blink = 0;
  BYTE1(this[4].Header.WaitListHead.Blink[5].Flink) = 2;
  BYTE2(this[4].Header.WaitListHead.Blink[5].Flink) = 1;
  this[4].Header.WaitListHead.Blink[14].Flink = (struct _LIST_ENTRY *)this;
  BYTE1(this[4].Header.WaitListHead.Blink[17].Flink) = 1;
  Pool2 = (void *)ExAllocatePool2(66, 8LL * (unsigned int)this[4].Header.Lock, 1934650710);
  *(_QWORD *)&this[5].Header.Lock = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 8LL * (unsigned int)this[4].Header.Lock);
  v11 = 0;
  while ( v11 < this[4].Header.LockNV )
  {
    v12 = VMX_TRANSFER_PACKET::operator new(0x128u);
    if ( !v12 )
      return 3221225626LL;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 3) = 0;
    v12[83] = 0;
    *((_WORD *)v12 + 66) = 0;
    *((_QWORD *)v12 + 27) = 0;
    v12[177] = 0;
    *(_QWORD *)v12 = &VMX_RAID5_TRANSFER_PACKET::`vftable';
    *((_WORD *)v12 + 136) = 0;
    v12[274] = 0;
    *((_QWORD *)v12 + 3) = this[4].Header.WaitListHead.Blink[1].Blink;
    *((_QWORD *)v12 + 5) = VmxpMirrorRegenerationPhase3;
    *((_DWORD *)v12 + 16) = 0;
    *((_QWORD *)v12 + 9) = 0;
    *(_WORD *)(v12 + 81) = 2;
    *((_QWORD *)v12 + 28) = this;
    v12[273] = 1;
    v13 = v11++;
    *(_QWORD *)(*(_QWORD *)&this[5].Header.Lock + 8 * v13) = v12;
  }
  v14 = (struct _LIST_ENTRY *)VMX_TRANSFER_PACKET::operator new(0x128u);
  if ( v14 )
  {
    v14[2].Flink = 0;
    v14[1].Blink = 0;
    BYTE3(v14[5].Flink) = 0;
    WORD2(v14[8].Flink) = 0;
    v14[13].Blink = 0;
    BYTE1(v14[11].Flink) = 0;
    v14->Flink = (struct _LIST_ENTRY *)&VMX_RAID5_TRANSFER_PACKET::`vftable';
    LOWORD(v14[17].Flink) = 0;
    BYTE2(v14[17].Flink) = 0;
  }
  else
  {
    v14 = 0;
  }
  this[5].Header.WaitListHead.Flink = v14;
  if ( !v14 )
    return 3221225626LL;
  v14[14].Flink = (struct _LIST_ENTRY *)this;
  BYTE1(this[5].Header.WaitListHead.Flink[17].Flink) = 1;
  result = 0;
  this[4].Header.WaitListHead.Flink = a4;
  return result;
}

```

## disassembly

```asm
0x14000de34  push    rbx
0x14000de36  push    rbp
0x14000de37  push    rsi
0x14000de38  push    rdi
0x14000de39  push    r14
0x14000de3b  push    r15
0x14000de3d  sub     rsp, 28h
0x14000de41  mov     rax, [rsp+58h+arg_28]
0x14000de49  xor     ebp, ebp
0x14000de4b  mov     [rcx+20h], rdx
0x14000de4f  mov     rbx, rcx
0x14000de52  mov     [rcx+60h], r8d
0x14000de56  xor     edx, edx; Type
0x14000de58  mov     [rcx+38h], rbp
0x14000de5c  xor     r8d, r8d; State
0x14000de5f  mov     [rcx+28h], rbp
0x14000de63  mov     rsi, r9
0x14000de66  mov     [rcx+30h], rax
0x14000de6a  mov     [rcx+40h], bp
0x14000de6e  mov     [rcx+42h], bpl
0x14000de72  mov     dword ptr [rcx+18h], 1
0x14000de79  add     rcx, 48h ; 'H'; Event
0x14000de7d  call    cs:__imp_KeInitializeEvent
0x14000de84  nop     dword ptr [rax+rax+00h]
0x14000de89  mov     r15d, 128h
0x14000de8f  mov     ecx, r15d; unsigned __int64
0x14000de92  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x14000de97  lea     r14, ??_7VMX_RAID5_TRANSFER_PACKET@@6B@; const VMX_RAID5_TRANSFER_PACKET::`vftable'
0x14000de9e  test    rax, rax
0x14000dea1  jz      short loc_14000DED7
0x14000dea3  mov     [rax+20h], rbp
0x14000dea7  mov     [rax+18h], rbp
0x14000deab  mov     [rax+53h], bpl
0x14000deaf  mov     [rax+84h], bp
0x14000deb6  mov     [rax+0D8h], rbp
0x14000debd  mov     [rax+0B1h], bpl
0x14000dec4  mov     [rax], r14
0x14000dec7  mov     [rax+110h], bp
0x14000dece  mov     [rax+112h], bpl
0x14000ded5  jmp     short loc_14000DEDA
0x14000ded7  mov     rax, rbp
0x14000deda  mov     [rbx+70h], rax
0x14000dede  test    rax, rax
0x14000dee1  jz      loc_14000E06C
0x14000dee7  mov     edx, 10000h; unsigned int
0x14000deec  mov     rcx, rax; this
0x14000deef  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJK@Z; VMX_TRANSFER_PACKET::AllocateMdl(ulong)
0x14000def4  test    eax, eax
0x14000def6  js      loc_14000E071
0x14000defc  mov     rax, [rbx+70h]
0x14000df00  mov     ecx, 42h ; 'B'
0x14000df05  mov     r8d, 73506D56h
0x14000df0b  mov     [rax+40h], ebp
0x14000df0e  mov     rax, [rbx+70h]
0x14000df12  mov     [rax+48h], rbp
0x14000df16  mov     rax, [rbx+70h]
0x14000df1a  mov     byte ptr [rax+51h], 2
0x14000df1e  mov     rax, [rbx+70h]
0x14000df22  mov     byte ptr [rax+52h], 1
0x14000df26  mov     rax, [rbx+70h]
0x14000df2a  mov     [rax+0E0h], rbx
0x14000df31  mov     rax, [rbx+70h]
0x14000df35  mov     byte ptr [rax+111h], 1
0x14000df3c  mov     edx, [rbx+60h]
0x14000df3f  shl     rdx, 3
0x14000df43  call    cs:__imp_ExAllocatePool2
0x14000df4a  nop     dword ptr [rax+rax+00h]
0x14000df4f  mov     [rbx+78h], rax
0x14000df53  test    rax, rax
0x14000df56  jz      loc_14000E06C
0x14000df5c  mov     r8d, [rbx+60h]
0x14000df60  xor     edx, edx; Val
0x14000df62  shl     r8, 3; Size
0x14000df66  mov     rcx, rax; void *
0x14000df69  call    memset
0x14000df6e  mov     edi, ebp
0x14000df70  mov     rcx, r15; unsigned __int64
0x14000df73  cmp     edi, [rbx+60h]
0x14000df76  jnb     loc_14000E002
0x14000df7c  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x14000df81  mov     rdx, rax
0x14000df84  test    rax, rax
0x14000df87  jz      loc_14000E06C
0x14000df8d  mov     [rax+20h], rbp
0x14000df91  mov     [rax+18h], rbp
0x14000df95  mov     [rax+53h], bpl
0x14000df99  mov     [rax+84h], bp
0x14000dfa0  mov     [rax+0D8h], rbp
0x14000dfa7  mov     [rax+0B1h], bpl
0x14000dfae  mov     [rax], r14
0x14000dfb1  mov     [rax+110h], bp
0x14000dfb8  mov     [rax+112h], bpl
0x14000dfbf  mov     rax, [rbx+70h]
0x14000dfc3  mov     rcx, [rax+18h]
0x14000dfc7  lea     rax, ?VmxpMirrorRegenerationPhase3@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRegenerationPhase3(VMX_TRANSFER_PACKET *)
0x14000dfce  mov     [rdx+18h], rcx
0x14000dfd2  mov     [rdx+28h], rax
0x14000dfd6  mov     [rdx+40h], ebp
0x14000dfd9  mov     [rdx+48h], rbp
0x14000dfdd  mov     word ptr [rdx+51h], 2
0x14000dfe3  mov     [rdx+0E0h], rbx
0x14000dfea  mov     byte ptr [rdx+111h], 1
0x14000dff1  mov     rax, [rbx+78h]
0x14000dff5  mov     ecx, edi
0x14000dff7  inc     edi
0x14000dff9  mov     [rax+rcx*8], rdx
0x14000dffd  jmp     loc_14000DF70
0x14000e002  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x14000e007  test    rax, rax
0x14000e00a  jz      short loc_14000E040
0x14000e00c  mov     [rax+20h], rbp
0x14000e010  mov     [rax+18h], rbp
0x14000e014  mov     [rax+53h], bpl
0x14000e018  mov     [rax+84h], bp
0x14000e01f  mov     [rax+0D8h], rbp
0x14000e026  mov     [rax+0B1h], bpl
0x14000e02d  mov     [rax], r14
0x14000e030  mov     [rax+110h], bp
0x14000e037  mov     [rax+112h], bpl
0x14000e03e  jmp     short loc_14000E043
0x14000e040  mov     rax, rbp
0x14000e043  mov     [rbx+80h], rax
0x14000e04a  test    rax, rax
0x14000e04d  jz      short loc_14000E06C
0x14000e04f  mov     [rax+0E0h], rbx
0x14000e056  mov     rax, [rbx+80h]
0x14000e05d  mov     byte ptr [rax+111h], 1
0x14000e064  xor     eax, eax
0x14000e066  mov     [rbx+68h], rsi
0x14000e06a  jmp     short loc_14000E071
0x14000e06c  mov     eax, 0C000009Ah
0x14000e071  add     rsp, 28h
0x14000e075  pop     r15
0x14000e077  pop     r14
0x14000e079  pop     rdi
0x14000e07a  pop     rsi
0x14000e07b  pop     rbp
0x14000e07c  pop     rbx
0x14000e07d  retn
```
