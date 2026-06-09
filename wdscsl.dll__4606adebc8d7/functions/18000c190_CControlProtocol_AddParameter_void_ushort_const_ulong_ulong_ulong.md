# CControlProtocol::AddParameter(void *,ushort const *,ulong,ulong,ulong)

- ea: `0x18000c190`
- end: `0x18000c3c8`
- name: `?AddParameter@CControlProtocol@@QEAAPEAXPEAXPEBGKKK@Z`
- size: `568`
- prototype: `__int64 __fastcall(CControlProtocol *this, char *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000d2e0`

## callees

- `0x1800017d8`
- `0x180004680`
- `0x18000c0f4`
- `0x18000c190`
- `0x18000c4f8`
- `0x18000c594`
- `0x18000c834`
- `0x18000d6d2`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c396`
- `KERNEL32!SetLastError` at `0x18000c396`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c31f`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c31f`

## pseudocode

```c
__int64 __fastcall CControlProtocol::AddParameter(
        CControlProtocol *this,
        char *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v6; // rbx
  struct PacketVariable *v10; // rdi
  DWORD v11; // esi
  unsigned __int64 v12; // rax
  CControlProtocol *v13; // rcx
  struct PacketVariable *v14; // rax
  size_t v15; // r15
  __int64 v16; // rdx
  struct PacketVariable *v17; // rcx
  char *v18; // r14
  __int16 v19; // ax
  struct PacketVariable *v20; // rax
  unsigned int v21; // eax
  CControlProtocol *v22; // rcx
  void *Packet; // rax
  size_t Size; // [rsp+50h] [rbp+8h] BYREF

  v6 = 0;
  v10 = 0;
  LODWORD(Size) = 0;
  if ( !*((_DWORD *)this + 10) )
  {
    v11 = 5023;
    goto LABEL_37;
  }
  if ( !a2 )
    goto LABEL_36;
  if ( !a3 )
    goto LABEL_36;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  if ( v12 > 0x20
    || (a4 & 0xEFFFFFFF) != 1
    && (a4 & 0xEFFFFFFF) != 2
    && (a4 & 0xEFFFFFFF) != 4
    && (a4 & 0xEFFFFFFF) != 8
    && (a4 & 0xEFFFFFFF) != 0x10
    && (a4 & 0xEFFFFFFF) != 0x20
    && (a4 & 0xEFFFFFFF) != 0x40 )
  {
    goto LABEL_36;
  }
  if ( !(unsigned int)CControlProtocol::GetTypeTotalLength(this, a4, a5, a6, &a5, (unsigned int *)&Size) )
  {
LABEL_36:
    v11 = 87;
    goto LABEL_37;
  }
  if ( !*((_DWORD *)a2 + 6) )
  {
    v11 = 1;
    goto LABEL_37;
  }
  if ( CControlProtocol::FindVariable(v13, (struct ControlPacket *)a2, a3) )
  {
    v11 = 183;
    goto LABEL_37;
  }
  v14 = (struct PacketVariable *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v14;
  if ( !v14 )
  {
    v10 = 0;
    v11 = 8;
    goto LABEL_37;
  }
  v15 = (unsigned int)Size;
  v16 = 33;
  *((_QWORD *)v14 + 12) = 0;
  v17 = v14;
  *((_QWORD *)v14 + 13) = 0;
  *((_QWORD *)v14 + 9) = 0;
  *((_QWORD *)v14 + 10) = 0;
  *((_QWORD *)v14 + 11) = 0;
  *(_WORD *)v14 = 0;
  *((_DWORD *)v14 + 20) = a4;
  *((_DWORD *)v14 + 21) = a5;
  *((_DWORD *)v14 + 23) = v15;
  *((_DWORD *)v14 + 22) = (a4 & 0x10000000) != 0 ? a6 : 0;
  v18 = (char *)((char *)a3 - (char *)v14);
  do
  {
    if ( v16 == -2147483613 )
      break;
    v19 = *(_WORD *)((char *)v17 + (_QWORD)v18);
    if ( !v19 )
      break;
    *(_WORD *)v17 = v19;
    v17 = (struct PacketVariable *)((char *)v17 + 2);
    --v16;
  }
  while ( v16 );
  v20 = (struct PacketVariable *)((char *)v17 - 2);
  if ( v16 )
    v20 = v17;
  *(_WORD *)v20 = 0;
  if ( v16 )
  {
    Packet = CClientLibrary::AllocatePacket((CClientLibrary *)&stru_1800158D0, *((void **)a2 + 2), v15);
    *((_QWORD *)v10 + 9) = Packet;
    if ( Packet )
    {
      memset_0(Packet, 0, v15);
      CSmHashTable<PacketVariable,CNoLock,113>::AddItem(a2 + 32, v10);
      return *((_QWORD *)v10 + 9);
    }
    v11 = 8;
LABEL_33:
    CControlProtocol::FreeVariable(v22, (struct ControlPacket *)a2, v10);
    v10 = 0;
    goto LABEL_37;
  }
  v21 = WIN32_FROM_HRESULT(-2147024774);
  v22 = v10;
  if ( !v21 )
    goto LABEL_38;
  v11 = v21;
  if ( v10 )
    goto LABEL_33;
LABEL_37:
  SetLastError(v11);
LABEL_38:
  if ( v10 )
    return *((_QWORD *)v10 + 9);
  return v6;
}

```

## disassembly

```asm
0x18000c190  mov     rax, rsp
0x18000c193  mov     [rax+10h], rbx
0x18000c197  mov     [rax+18h], rbp
0x18000c19b  mov     [rax+20h], rsi
0x18000c19f  push    rdi
0x18000c1a0  push    r14
0x18000c1a2  push    r15
0x18000c1a4  sub     rsp, 30h
0x18000c1a8  xor     ebx, ebx
0x18000c1aa  mov     esi, r9d
0x18000c1ad  mov     r14, r8
0x18000c1b0  mov     rbp, rdx
0x18000c1b3  mov     edi, ebx
0x18000c1b5  mov     [rax+8], ebx
0x18000c1b8  cmp     [rcx+28h], ebx
0x18000c1bb  jnz     short loc_18000C1C7
0x18000c1bd  mov     esi, 139Fh
0x18000c1c2  jmp     loc_18000C394
0x18000c1c7  test    rbp, rbp
0x18000c1ca  jz      loc_18000C38F
0x18000c1d0  test    r14, r14
0x18000c1d3  jz      loc_18000C38F
0x18000c1d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c1dd  inc     rax
0x18000c1e0  cmp     [r8+rax*2], bx
0x18000c1e5  jnz     short loc_18000C1DD
0x18000c1e7  cmp     rax, 20h ; ' '
0x18000c1eb  ja      loc_18000C38F
0x18000c1f1  mov     eax, esi
0x18000c1f3  btr     eax, 1Ch
0x18000c1f7  sub     eax, 1
0x18000c1fa  jz      short loc_18000C21E
0x18000c1fc  sub     eax, 1
0x18000c1ff  jz      short loc_18000C21E
0x18000c201  sub     eax, 2
0x18000c204  jz      short loc_18000C21E
0x18000c206  sub     eax, 4
0x18000c209  jz      short loc_18000C21E
0x18000c20b  sub     eax, 8
0x18000c20e  jz      short loc_18000C21E
0x18000c210  sub     eax, 10h
0x18000c213  jz      short loc_18000C21E
0x18000c215  cmp     eax, 20h ; ' '
0x18000c218  jnz     loc_18000C38F
0x18000c21e  mov     r8d, [rsp+48h+arg_20]; unsigned int
0x18000c223  lea     rax, [rsp+48h+Size]
0x18000c228  mov     r9d, [rsp+48h+arg_28]; unsigned int
0x18000c22d  mov     edx, esi; unsigned int
0x18000c22f  mov     [rsp+48h+var_20], rax; unsigned int *
0x18000c234  lea     rax, [rsp+48h+arg_20]
0x18000c239  mov     [rsp+48h+var_28], rax; unsigned int *
0x18000c23e  call    ?GetTypeTotalLength@CControlProtocol@@AEAAHKKKPEAK0@Z; CControlProtocol::GetTypeTotalLength(ulong,ulong,ulong,ulong *,ulong *)
0x18000c243  test    eax, eax
0x18000c245  jz      loc_18000C38F
0x18000c24b  cmp     [rbp+18h], ebx
0x18000c24e  jnz     short loc_18000C25A
0x18000c250  mov     esi, 1
0x18000c255  jmp     loc_18000C394
0x18000c25a  mov     r8, r14; unsigned __int16 *
0x18000c25d  mov     rdx, rbp; struct ControlPacket *
0x18000c260  call    ?FindVariable@CControlProtocol@@AEAAPEAUPacketVariable@@PEAUControlPacket@@PEBG@Z; CControlProtocol::FindVariable(ControlPacket *,ushort const *)
0x18000c265  test    rax, rax
0x18000c268  jz      short loc_18000C274
0x18000c26a  mov     esi, 0B7h
0x18000c26f  jmp     loc_18000C394
0x18000c274  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c27b  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000c280  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c285  mov     rdi, rax
0x18000c288  test    rax, rax
0x18000c28b  jz      loc_18000C385
0x18000c291  mov     r15d, dword ptr [rsp+48h+Size]
0x18000c296  mov     edx, 21h ; '!'
0x18000c29b  mov     [rax+60h], rbx
0x18000c29f  mov     rcx, rdi
0x18000c2a2  mov     [rax+68h], rbx
0x18000c2a6  mov     [rax+48h], rbx
0x18000c2aa  mov     [rax+50h], rbx
0x18000c2ae  mov     [rax+58h], rbx
0x18000c2b2  mov     [rax], bx
0x18000c2b5  mov     [rax+50h], esi
0x18000c2b8  and     esi, 10000000h
0x18000c2be  mov     eax, [rsp+48h+arg_20]
0x18000c2c2  neg     esi
0x18000c2c4  mov     [rdi+54h], eax
0x18000c2c7  lea     esi, [rdx-20h]
0x18000c2ca  sbb     eax, eax
0x18000c2cc  mov     [rdi+5Ch], r15d
0x18000c2d0  and     eax, [rsp+48h+arg_28]
0x18000c2d4  mov     [rdi+58h], eax
0x18000c2d7  sub     r14, rdi
0x18000c2da  lea     rax, [rdx+7FFFFFDDh]
0x18000c2e1  test    rax, rax
0x18000c2e4  jz      short loc_18000C2FC
0x18000c2e6  movzx   eax, word ptr [r14+rcx]
0x18000c2eb  test    ax, ax
0x18000c2ee  jz      short loc_18000C2FC
0x18000c2f0  mov     [rcx], ax
0x18000c2f3  add     rcx, 2
0x18000c2f7  sub     rdx, rsi
0x18000c2fa  jnz     short loc_18000C2DA
0x18000c2fc  lea     rax, [rcx-2]
0x18000c300  test    rdx, rdx
0x18000c303  cmovnz  rax, rcx
0x18000c307  mov     [rax], bx
0x18000c30a  mov     rax, rdx
0x18000c30d  neg     rax
0x18000c310  sbb     ecx, ecx
0x18000c312  not     ecx
0x18000c314  and     ecx, 8007007Ah
0x18000c31a  test    rdx, rdx
0x18000c31d  jnz     short loc_18000C33B
0x18000c31f  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c326  nop     dword ptr [rax+rax+00h]
0x18000c32b  mov     rcx, rdi
0x18000c32e  test    eax, eax
0x18000c330  jz      short loc_18000C3A2
0x18000c332  mov     esi, eax
0x18000c334  test    rcx, rcx
0x18000c337  jz      short loc_18000C394
0x18000c339  jmp     short loc_18000C35A
0x18000c33b  mov     rdx, [rbp+10h]; void *
0x18000c33f  lea     rcx, stru_1800158D0; this
0x18000c346  mov     r8d, r15d; unsigned int
0x18000c349  call    ?AllocatePacket@CClientLibrary@@QEAAPEAXPEAXK@Z; CClientLibrary::AllocatePacket(void *,ulong)
0x18000c34e  mov     [rdi+48h], rax
0x18000c352  test    rax, rax
0x18000c355  jnz     short loc_18000C36A
0x18000c357  lea     esi, [rax+8]
0x18000c35a  mov     r8, rdi; struct PacketVariable *
0x18000c35d  mov     rdx, rbp; struct ControlPacket *
0x18000c360  call    ?FreeVariable@CControlProtocol@@AEAAXPEAUControlPacket@@PEAUPacketVariable@@@Z; CControlProtocol::FreeVariable(ControlPacket *,PacketVariable *)
0x18000c365  mov     rdi, rbx
0x18000c368  jmp     short loc_18000C394
0x18000c36a  mov     r8, r15; Size
0x18000c36d  xor     edx, edx; Val
0x18000c36f  mov     rcx, rax; void *
0x18000c372  call    memset_0
0x18000c377  lea     rcx, [rbp+20h]
0x18000c37b  mov     rdx, rdi
0x18000c37e  call    ?AddItem@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@QEAAXPEAUPacketVariable@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::AddItem(PacketVariable *)
0x18000c383  jmp     short loc_18000C3A7
0x18000c385  mov     rdi, rbx
0x18000c388  mov     esi, 8
0x18000c38d  jmp     short loc_18000C394
0x18000c38f  mov     esi, 57h ; 'W'
0x18000c394  mov     ecx, esi; dwErrCode
0x18000c396  call    cs:__imp_SetLastError
0x18000c39d  nop     dword ptr [rax+rax+00h]
0x18000c3a2  test    rdi, rdi
0x18000c3a5  jz      short loc_18000C3AB
0x18000c3a7  mov     rbx, [rdi+48h]
0x18000c3ab  mov     rbp, [rsp+48h+arg_10]
0x18000c3b0  mov     rax, rbx
0x18000c3b3  mov     rbx, [rsp+48h+arg_8]
0x18000c3b8  mov     rsi, [rsp+48h+arg_18]
0x18000c3bd  add     rsp, 30h
0x18000c3c1  pop     r15
0x18000c3c3  pop     r14
0x18000c3c5  pop     rdi
0x18000c3c6  retn
```
