# CControlProtocol::InitializeRecvPacket(void *,void *,ulong,tagWDSCPL_PACKET_INFO *,void * *)

- ea: `0x18000c8bc`
- end: `0x18000cbdf`
- name: `?InitializeRecvPacket@CControlProtocol@@QEAAKPEAX0KPEAUtagWDSCPL_PACKET_INFO@@PEAPEAX@Z`
- size: `803`
- prototype: `__int64 __fastcall(CControlProtocol *this, void *, _WORD *, unsigned int, struct tagWDSCPL_PACKET_INFO *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d570`

## callees

- `0x1800017d8`
- `0x18000c0dc`
- `0x18000c0f4`
- `0x18000c3d0`
- `0x18000c834`
- `0x18000c8bc`
- `0x18000cc4c`

## pseudocode

```c
__int64 __fastcall CControlProtocol::InitializeRecvPacket(
        CControlProtocol *this,
        void *a2,
        _WORD *a3,
        unsigned int a4,
        struct tagWDSCPL_PACKET_INFO *a5,
        void **a6)
{
  unsigned int v6; // ebx
  __int64 v7; // r15
  unsigned int v10; // r13d
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rsi
  char *v14; // r14
  unsigned int v15; // eax
  char *v16; // r14
  CControlProtocol *v17; // rcx
  unsigned int *v18; // r12
  CControlProtocol *v19; // rcx
  unsigned int v20; // edx
  _WORD *v21; // rax
  _WORD *v22; // rcx
  unsigned int v23; // esi
  __int64 v24; // r8
  _WORD *v25; // rdx
  __int64 v26; // r14
  __int16 v27; // ax
  _WORD *v28; // rax
  unsigned int v30[4]; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  v7 = a4;
  v30[0] = 0;
  v10 = 16;
  if ( !*((_DWORD *)this + 10) )
    return 5023;
  if ( !a3 || a4 < 0x10 || !a5 || !a6 )
    return 87;
  if ( !a2 )
  {
    if ( !dword_180015900 )
      goto LABEL_9;
    return 6;
  }
  if ( !dword_180015900 )
    return 6;
LABEL_9:
  if ( *(_DWORD *)a3 != a4 || a3[2] != 256 )
    return 13;
  v11 = (volatile signed __int32 *)operator new(0xAC8u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
    return 8;
  v13 = 113;
  v14 = (char *)(v11 + 10);
  do
  {
    CList<PacketVariable,CNoLock>::CList<PacketVariable,CNoLock>(v14);
    v14 += 24;
    --v13;
  }
  while ( v13 );
  *((_DWORD *)v12 + 688) = 0;
  *((_QWORD *)v12 + 2) = 0;
  *((_DWORD *)v12 + 6) = 1;
  *v12 = 12;
  *((_BYTE *)v12 + 4) = *((_BYTE *)a3 + 6);
  *((_DWORD *)v12 + 2) = *((_DWORD *)a3 + 2);
  *((_DWORD *)v12 + 6) = 0;
  *((_QWORD *)v12 + 2) = a2;
  if ( (unsigned int)v7 <= 0x10 )
  {
LABEL_40:
    if ( _InterlockedExchangeAdd(v12 + 688, 0) == *((_DWORD *)a3 + 3) )
    {
      *(_QWORD *)a5 = *(_QWORD *)v12;
      *((_DWORD *)a5 + 2) = *((_DWORD *)v12 + 2);
      *a6 = (void *)v12;
      return v6;
    }
  }
  else
  {
    while ( (unsigned int)v7 - v10 >= 0x54 )
    {
      v15 = 0;
      v16 = (char *)a3 + v10;
      v17 = (CControlProtocol *)v16;
      do
      {
        if ( !*(_WORD *)v17 )
          break;
        ++v15;
        v17 = (CControlProtocol *)((char *)v17 + 2);
      }
      while ( v15 < 0x21 );
      if ( !v15
        || v15 == 33
        || (*((_DWORD *)v16 + 17) & 0xEFFFFFFF) != 1
        && (*((_DWORD *)v16 + 17) & 0xEFFFFFFF) != 2
        && (*((_DWORD *)v16 + 17) & 0xEFFFFFFF) != 4
        && (*((_DWORD *)v16 + 17) & 0xEFFFFFFF) != 8
        && (*((_DWORD *)v16 + 17) & 0xEFFFFFFF) != 0x10
        && (*((_DWORD *)v16 + 17) & 0xEFFFFFFF) != 0x20
        && (*((_DWORD *)v16 + 17) & 0xEFFFFFFF) != 0x40 )
      {
        break;
      }
      v18 = (unsigned int *)(v16 + 72);
      if ( !(unsigned int)CControlProtocol::GetTypeTotalLength(
                            v17,
                            *((_DWORD *)v16 + 17),
                            *((_DWORD *)v16 + 18),
                            *((_DWORD *)v16 + 19),
                            (unsigned int *)v16 + 18,
                            v30) )
        break;
      v19 = (CControlProtocol *)(v7 - v10 - 83);
      if ( (unsigned __int64)v19 < v30[0] )
        break;
      v20 = *((_DWORD *)v16 + 17);
      if ( (v20 & 0x30) != 0
        && !(unsigned int)CControlProtocol::CheckStringTermination(
                            v19,
                            v20,
                            *v18,
                            *((_DWORD *)v16 + 19),
                            (unsigned __int8 *)v16 + 80) )
      {
        break;
      }
      v21 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
      v22 = v21;
      if ( !v21 )
      {
        v6 = 8;
        goto LABEL_42;
      }
      v23 = v30[0];
      v24 = 33;
      *((_QWORD *)v21 + 12) = 0;
      v25 = v21;
      *((_QWORD *)v21 + 13) = 0;
      *((_QWORD *)v21 + 9) = 0;
      *((_QWORD *)v21 + 10) = 0;
      *((_QWORD *)v21 + 11) = 0;
      *v21 = 0;
      *((_DWORD *)v21 + 23) = v23;
      *((_DWORD *)v21 + 22) = *((_DWORD *)v16 + 19);
      *((_DWORD *)v21 + 21) = *v18;
      *((_DWORD *)v21 + 20) = *((_DWORD *)v16 + 17);
      *((_QWORD *)v21 + 9) = v16 + 80;
      v26 = v16 - (char *)v21;
      do
      {
        if ( v24 == -2147483613 )
          break;
        v27 = *(_WORD *)((char *)v22 + v26);
        if ( !v27 )
          break;
        *v22++ = v27;
        --v24;
      }
      while ( v24 );
      v28 = v22 - 1;
      if ( v24 )
        v28 = v22;
      *v28 = 0;
      CSmHashTable<PacketVariable,CNoLock,113>::AddItem(v12 + 8, v25);
      v10 = (v23 + v10 + 98) & 0xFFFFFFF0;
      if ( v10 >= (unsigned int)v7 )
        goto LABEL_40;
    }
  }
  v6 = 13;
LABEL_42:
  CControlProtocol::ReleasePacket(this, (void *)v12);
  return v6;
}

```

## disassembly

```asm
0x18000c8bc  mov     rax, rsp
0x18000c8bf  mov     [rax+10h], rbx
0x18000c8c3  mov     [rax+18h], rbp
0x18000c8c7  mov     [rax+20h], rsi
0x18000c8cb  mov     [rax+8], rcx
0x18000c8cf  push    rdi
0x18000c8d0  push    r12
0x18000c8d2  push    r13
0x18000c8d4  push    r14
0x18000c8d6  push    r15
0x18000c8d8  sub     rsp, 40h
0x18000c8dc  xor     ebx, ebx
0x18000c8de  mov     r15d, r9d
0x18000c8e1  mov     rbp, r8
0x18000c8e4  mov     r12, rdx
0x18000c8e7  mov     [rax-38h], ebx
0x18000c8ea  lea     r13d, [rbx+10h]
0x18000c8ee  cmp     [rcx+28h], ebx
0x18000c8f1  jnz     short loc_18000C8FD
0x18000c8f3  mov     ebx, 139Fh
0x18000c8f8  jmp     loc_18000CBBE
0x18000c8fd  test    rbp, rbp
0x18000c900  jz      loc_18000CBB9
0x18000c906  cmp     r15d, r13d
0x18000c909  jb      loc_18000CBB9
0x18000c90f  cmp     [rsp+68h+arg_20], rbx
0x18000c917  jz      loc_18000CBB9
0x18000c91d  cmp     [rsp+68h+arg_28], rbx
0x18000c925  jz      loc_18000CBB9
0x18000c92b  test    r12, r12
0x18000c92e  jnz     loc_18000CB6E
0x18000c934  cmp     cs:dword_180015900, ebx
0x18000c93a  jnz     loc_18000CB7A
0x18000c940  cmp     [r8], r15d
0x18000c943  jnz     loc_18000CBB2
0x18000c949  mov     eax, 100h
0x18000c94e  cmp     [r8+4], ax
0x18000c953  jnz     loc_18000CBB2
0x18000c959  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c960  mov     ecx, 0AC8h; unsigned __int64
0x18000c965  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c96a  mov     rdi, rax
0x18000c96d  test    rax, rax
0x18000c970  jz      loc_18000CBAB
0x18000c976  mov     esi, 71h ; 'q'
0x18000c97b  lea     r14, [rax+28h]
0x18000c97f  mov     rcx, r14
0x18000c982  call    ??0?$CList@UPacketVariable@@VCNoLock@@@@QEAA@XZ; CList<PacketVariable,CNoLock>::CList<PacketVariable,CNoLock>(void)
0x18000c987  add     r14, 18h
0x18000c98b  sub     rsi, 1
0x18000c98f  jnz     short loc_18000C97F
0x18000c991  mov     [rdi+0AC0h], ebx
0x18000c997  mov     [rdi+10h], rbx
0x18000c99b  mov     dword ptr [rdi+18h], 1
0x18000c9a2  mov     dword ptr [rdi], 0Ch
0x18000c9a8  mov     al, [rbp+6]
0x18000c9ab  mov     [rdi+4], al
0x18000c9ae  mov     eax, [rbp+8]
0x18000c9b1  mov     [rdi+8], eax
0x18000c9b4  mov     [rdi+18h], ebx
0x18000c9b7  mov     [rdi+10h], r12
0x18000c9bb  cmp     r15d, r13d
0x18000c9be  jbe     loc_18000CB4B
0x18000c9c4  mov     eax, r15d
0x18000c9c7  sub     eax, r13d
0x18000c9ca  cmp     eax, 54h ; 'T'
0x18000c9cd  jb      loc_18000CB5A
0x18000c9d3  mov     r14d, r13d
0x18000c9d6  mov     eax, ebx
0x18000c9d8  add     r14, rbp
0x18000c9db  mov     rcx, r14
0x18000c9de  cmp     [rcx], bx
0x18000c9e1  jz      short loc_18000C9EE
0x18000c9e3  inc     eax
0x18000c9e5  add     rcx, 2; this
0x18000c9e9  cmp     eax, 21h ; '!'
0x18000c9ec  jb      short loc_18000C9DE
0x18000c9ee  test    eax, eax
0x18000c9f0  jz      loc_18000CB5A
0x18000c9f6  cmp     eax, 21h ; '!'
0x18000c9f9  jz      loc_18000CB5A
0x18000c9ff  mov     edx, [r14+44h]; unsigned int
0x18000ca03  mov     eax, edx
0x18000ca05  btr     eax, 1Ch
0x18000ca09  sub     eax, 1
0x18000ca0c  jz      short loc_18000CA30
0x18000ca0e  sub     eax, 1
0x18000ca11  jz      short loc_18000CA30
0x18000ca13  sub     eax, 2
0x18000ca16  jz      short loc_18000CA30
0x18000ca18  sub     eax, 4
0x18000ca1b  jz      short loc_18000CA30
0x18000ca1d  sub     eax, 8
0x18000ca20  jz      short loc_18000CA30
0x18000ca22  sub     eax, 10h
0x18000ca25  jz      short loc_18000CA30
0x18000ca27  cmp     eax, 20h ; ' '
0x18000ca2a  jnz     loc_18000CB5A
0x18000ca30  mov     r9d, [r14+4Ch]; unsigned int
0x18000ca34  lea     r12, [r14+48h]
0x18000ca38  mov     r8d, [r12]; unsigned int
0x18000ca3c  lea     rax, [rsp+68h+var_38]
0x18000ca41  mov     [rsp+68h+var_40], rax; unsigned int *
0x18000ca46  mov     [rsp+68h+var_48], r12; unsigned int *
0x18000ca4b  call    ?GetTypeTotalLength@CControlProtocol@@AEAAHKKKPEAK0@Z; CControlProtocol::GetTypeTotalLength(ulong,ulong,ulong,ulong *,ulong *)
0x18000ca50  test    eax, eax
0x18000ca52  jz      loc_18000CB5A
0x18000ca58  mov     eax, r13d
0x18000ca5b  mov     rcx, r15
0x18000ca5e  sub     rcx, rax
0x18000ca61  mov     eax, [rsp+68h+var_38]
0x18000ca65  sub     rcx, 53h ; 'S'; this
0x18000ca69  cmp     rcx, rax
0x18000ca6c  jb      loc_18000CB5A
0x18000ca72  mov     edx, [r14+44h]; unsigned int
0x18000ca76  test    dl, 30h
0x18000ca79  jz      short loc_18000CA99
0x18000ca7b  mov     r8d, [r12]; unsigned int
0x18000ca7f  lea     rax, [r14+50h]
0x18000ca83  mov     r9d, [r14+4Ch]; unsigned int
0x18000ca87  mov     [rsp+68h+var_48], rax; unsigned __int8 *
0x18000ca8c  call    ?CheckStringTermination@CControlProtocol@@AEAAHKKKPEAE@Z; CControlProtocol::CheckStringTermination(ulong,ulong,ulong,uchar *)
0x18000ca91  test    eax, eax
0x18000ca93  jz      loc_18000CB5A
0x18000ca99  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000caa0  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000caa5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000caaa  mov     rcx, rax
0x18000caad  test    rax, rax
0x18000cab0  jz      loc_18000CB81
0x18000cab6  mov     esi, [rsp+68h+var_38]
0x18000caba  mov     r8d, 21h ; '!'
0x18000cac0  mov     [rax+60h], rbx
0x18000cac4  mov     rdx, rcx
0x18000cac7  mov     [rax+68h], rbx
0x18000cacb  mov     [rax+48h], rbx
0x18000cacf  mov     [rax+50h], rbx
0x18000cad3  mov     [rax+58h], rbx
0x18000cad7  mov     [rax], bx
0x18000cada  mov     [rax+5Ch], esi
0x18000cadd  mov     eax, [r14+4Ch]
0x18000cae1  mov     [rcx+58h], eax
0x18000cae4  mov     eax, [r12]
0x18000cae8  mov     [rcx+54h], eax
0x18000caeb  mov     eax, [r14+44h]
0x18000caef  mov     [rcx+50h], eax
0x18000caf2  lea     rax, [r14+50h]
0x18000caf6  mov     [rcx+48h], rax
0x18000cafa  sub     r14, rcx
0x18000cafd  lea     rax, [r8+7FFFFFDDh]
0x18000cb04  test    rax, rax
0x18000cb07  jz      short loc_18000CB20
0x18000cb09  movzx   eax, word ptr [r14+rcx]
0x18000cb0e  test    ax, ax
0x18000cb11  jz      short loc_18000CB20
0x18000cb13  mov     [rcx], ax
0x18000cb16  add     rcx, 2
0x18000cb1a  sub     r8, 1
0x18000cb1e  jnz     short loc_18000CAFD
0x18000cb20  lea     rax, [rcx-2]
0x18000cb24  test    r8, r8
0x18000cb27  cmovnz  rax, rcx
0x18000cb2b  lea     rcx, [rdi+20h]
0x18000cb2f  mov     [rax], bx
0x18000cb32  call    ?AddItem@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@QEAAXPEAUPacketVariable@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::AddItem(PacketVariable *)
0x18000cb37  add     r13d, 62h ; 'b'
0x18000cb3b  add     r13d, esi
0x18000cb3e  and     r13d, 0FFFFFFF0h
0x18000cb42  cmp     r13d, r15d
0x18000cb45  jb      loc_18000C9C4
0x18000cb4b  mov     eax, ebx
0x18000cb4d  lock xadd [rdi+0AC0h], eax
0x18000cb55  cmp     eax, [rbp+0Ch]
0x18000cb58  jz      short loc_18000CB88
0x18000cb5a  mov     ebx, 0Dh
0x18000cb5f  mov     rcx, [rsp+68h+arg_0]; this
0x18000cb64  mov     rdx, rdi; void *
0x18000cb67  call    ?ReleasePacket@CControlProtocol@@QEAAKPEAX@Z; CControlProtocol::ReleasePacket(void *)
0x18000cb6c  jmp     short loc_18000CBBE
0x18000cb6e  cmp     cs:dword_180015900, ebx
0x18000cb74  jnz     loc_18000C940
0x18000cb7a  mov     ebx, 6
0x18000cb7f  jmp     short loc_18000CBBE
0x18000cb81  mov     ebx, 8
0x18000cb86  jmp     short loc_18000CB5F
0x18000cb88  movsd   xmm0, qword ptr [rdi]
0x18000cb8c  mov     rcx, [rsp+68h+arg_20]
0x18000cb94  movsd   qword ptr [rcx], xmm0
0x18000cb98  mov     eax, [rdi+8]
0x18000cb9b  mov     [rcx+8], eax
0x18000cb9e  mov     rax, [rsp+68h+arg_28]
0x18000cba6  mov     [rax], rdi
0x18000cba9  jmp     short loc_18000CBBE
0x18000cbab  mov     ebx, 8
0x18000cbb0  jmp     short loc_18000CBBE
0x18000cbb2  mov     ebx, 0Dh
0x18000cbb7  jmp     short loc_18000CBBE
0x18000cbb9  mov     ebx, 57h ; 'W'
0x18000cbbe  lea     r11, [rsp+68h+var_28]
0x18000cbc3  mov     eax, ebx
0x18000cbc5  mov     rbx, [r11+38h]
0x18000cbc9  mov     rbp, [r11+40h]
0x18000cbcd  mov     rsi, [r11+48h]
0x18000cbd1  mov     rsp, r11
0x18000cbd4  pop     r15
0x18000cbd6  pop     r14
0x18000cbd8  pop     r13
0x18000cbda  pop     r12
0x18000cbdc  pop     rdi
0x18000cbdd  retn
```
