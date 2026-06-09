# CControlProtocol::GetPacketBuffer(void *,void * *,ulong *)

- ea: `0x18000c5dc`
- end: `0x18000c82e`
- name: `?GetPacketBuffer@CControlProtocol@@QEAAKPEAXPEAPEAXPEAK@Z`
- size: `594`
- prototype: `__int64 __fastcall(CControlProtocol *this, char *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d190`

## callees

- `0x1800026c4`
- `0x180004680`
- `0x180006080`
- `0x18000c5dc`
- `0x18000cbe8`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c7e7`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c7e7`

## pseudocode

```c
__int64 __fastcall CControlProtocol::GetPacketBuffer(CControlProtocol *this, char *a2, void **a3, unsigned int *a4)
{
  unsigned int v6; // ebx
  unsigned int v7; // edi
  unsigned int v8; // r12d
  char *v9; // r15
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r11
  unsigned int *Packet; // rax
  __int64 v14; // r11
  char *v15; // rsi
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rdx
  char *v21; // r11
  _WORD *v22; // rcx
  __int16 v23; // ax
  _WORD *v24; // rax
  __int128 v26; // [rsp+20h] [rbp-20h] BYREF
  __int128 v27; // [rsp+30h] [rbp-10h] BYREF

  v6 = 0;
  v7 = 16;
  v8 = 16;
  if ( *((_DWORD *)this + 10) )
  {
    if ( a2 && a3 && a4 )
    {
      v9 = a2 + 32;
      v10 = 0;
      v11 = *((_QWORD *)a2 + 5);
      *(_QWORD *)&v27 = 0;
      if ( v11 )
      {
        *((_QWORD *)&v27 + 1) = v11;
      }
      else
      {
        *((_QWORD *)&v27 + 1) = 0;
        CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(v9, &v27);
        v10 = v27;
      }
      v26 = v27;
      if ( !v10 )
      {
        do
        {
          CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(v9, &v26);
          v7 = (*(_DWORD *)(v12 + 92) + v7 + 98) & 0xFFFFFFF0;
        }
        while ( !(_DWORD)v26 );
      }
      Packet = (unsigned int *)CClientLibrary::AllocatePacket((CClientLibrary *)&stru_1800158D0, *((void **)a2 + 2), v7);
      v14 = 0;
      v15 = (char *)Packet;
      if ( Packet )
      {
        *Packet = v7;
        *((_WORD *)Packet + 2) = 256;
        *((_BYTE *)Packet + 6) = a2[4];
        Packet[2] = *((_DWORD *)a2 + 2);
        Packet[3] = _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 688, 0);
        v16 = 0;
        v17 = *((_QWORD *)v9 + 1);
        *(_QWORD *)&v27 = 0;
        if ( v17 )
        {
          *((_QWORD *)&v27 + 1) = v17;
        }
        else
        {
          *((_QWORD *)&v27 + 1) = 0;
          CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(v9, &v27);
          v16 = v27;
        }
        v26 = v27;
        if ( v16 )
        {
LABEL_28:
          *a3 = v15;
          *a4 = v8;
        }
        else
        {
          v18 = v26;
          while ( 1 )
          {
            v19 = v14;
            if ( !v18 )
              v19 = *((_QWORD *)&v26 + 1);
            CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(v9, &v26);
            v20 = 33;
            v21 = &v15[v8];
            v22 = v21;
            *((_DWORD *)v21 + 17) = *(_DWORD *)(v19 + 80);
            *((_DWORD *)v21 + 18) = *(_DWORD *)(v19 + 84);
            *((_DWORD *)v21 + 19) = *(_DWORD *)(v19 + 88);
            do
            {
              if ( v20 == -2147483613 )
                break;
              v23 = *(_WORD *)((char *)v22 + v19 - (_QWORD)v21);
              if ( !v23 )
                break;
              *v22++ = v23;
              --v20;
            }
            while ( v20 );
            v24 = v22 - 1;
            if ( v20 )
              v24 = v22;
            *v24 = 0;
            if ( !v20 )
              break;
            memmove_0(v21 + 80, *(const void **)(v19 + 72), *(unsigned int *)(v19 + 92));
            v14 = 0;
            v18 = v26;
            v8 = (*(_DWORD *)(v19 + 92) + 98 + v8) & 0xFFFFFFF0;
            if ( (_DWORD)v26 )
              goto LABEL_28;
          }
          v6 = WIN32_FROM_HRESULT(-2147024774);
          if ( v6 )
            CClientLibrary::FreePacket((CClientLibrary *)&stru_1800158D0, *((void **)a2 + 2), v15);
        }
      }
      else
      {
        return 8;
      }
    }
    else
    {
      return 87;
    }
  }
  else
  {
    return 5023;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c5dc  mov     [rsp-38h+arg_8], rbx
0x18000c5e1  mov     [rsp-38h+arg_10], r8
0x18000c5e6  push    rbp
0x18000c5e7  push    rsi
0x18000c5e8  push    rdi
0x18000c5e9  push    r12
0x18000c5eb  push    r13
0x18000c5ed  push    r14
0x18000c5ef  push    r15
0x18000c5f1  mov     rbp, rsp
0x18000c5f4  sub     rsp, 40h
0x18000c5f8  xor     esi, esi
0x18000c5fa  mov     r13, r9
0x18000c5fd  mov     rax, r8
0x18000c600  mov     r14, rdx
0x18000c603  mov     ebx, esi
0x18000c605  lea     edi, [rsi+10h]
0x18000c608  mov     r12d, edi
0x18000c60b  cmp     [rcx+28h], esi
0x18000c60e  jnz     short loc_18000C61A
0x18000c610  mov     ebx, 139Fh
0x18000c615  jmp     loc_18000C813
0x18000c61a  test    r14, r14
0x18000c61d  jz      loc_18000C80E
0x18000c623  test    rax, rax
0x18000c626  jz      loc_18000C80E
0x18000c62c  test    r13, r13
0x18000c62f  jz      loc_18000C80E
0x18000c635  lea     r15, [rdx+20h]
0x18000c639  mov     rax, rsi
0x18000c63c  mov     rcx, [r15+8]
0x18000c640  mov     qword ptr [rbp+var_10], rax
0x18000c644  test    rcx, rcx
0x18000c647  jnz     short loc_18000C65F
0x18000c649  lea     rdx, [rbp+var_10]
0x18000c64d  mov     qword ptr [rbp+var_10+8], rsi
0x18000c651  mov     rcx, r15
0x18000c654  call    ?MoveNext@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000c659  mov     rax, qword ptr [rbp+var_10]
0x18000c65d  jmp     short loc_18000C663
0x18000c65f  mov     qword ptr [rbp+var_10+8], rcx
0x18000c663  movaps  xmm0, [rbp+var_10]
0x18000c667  movdqa  [rbp+var_20], xmm0
0x18000c66c  test    eax, eax
0x18000c66e  jnz     short loc_18000C69B
0x18000c670  mov     eax, dword ptr [rbp+var_20]
0x18000c673  mov     r11, rsi
0x18000c676  test    eax, eax
0x18000c678  jnz     short loc_18000C67E
0x18000c67a  mov     r11, qword ptr [rbp+var_20+8]
0x18000c67e  lea     rdx, [rbp+var_20]
0x18000c682  mov     rcx, r15
0x18000c685  call    ?MoveNext@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000c68a  mov     eax, dword ptr [rbp+var_20]
0x18000c68d  add     edi, 62h ; 'b'
0x18000c690  add     edi, [r11+5Ch]
0x18000c694  and     edi, 0FFFFFFF0h
0x18000c697  test    eax, eax
0x18000c699  jz      short loc_18000C673
0x18000c69b  mov     rdx, [r14+10h]; void *
0x18000c69f  lea     rcx, stru_1800158D0; this
0x18000c6a6  mov     r8d, edi; unsigned int
0x18000c6a9  call    ?AllocatePacket@CClientLibrary@@QEAAPEAXPEAXK@Z; CClientLibrary::AllocatePacket(void *,ulong)
0x18000c6ae  xor     r11d, r11d
0x18000c6b1  mov     rsi, rax
0x18000c6b4  test    rax, rax
0x18000c6b7  jnz     short loc_18000C6C1
0x18000c6b9  lea     ebx, [rax+8]
0x18000c6bc  jmp     loc_18000C813
0x18000c6c1  mov     [rax], edi
0x18000c6c3  mov     word ptr [rax+4], 100h
0x18000c6c9  mov     al, [r14+4]
0x18000c6cd  mov     [rsi+6], al
0x18000c6d0  mov     eax, [r14+8]
0x18000c6d4  mov     [rsi+8], eax
0x18000c6d7  mov     eax, r11d
0x18000c6da  lock xadd [r14+0AC0h], eax
0x18000c6e3  mov     [rsi+0Ch], eax
0x18000c6e6  mov     rax, r11
0x18000c6e9  mov     rcx, [r15+8]
0x18000c6ed  mov     qword ptr [rbp+var_10], rax
0x18000c6f1  test    rcx, rcx
0x18000c6f4  jnz     short loc_18000C70C
0x18000c6f6  lea     rdx, [rbp+var_10]
0x18000c6fa  mov     qword ptr [rbp+var_10+8], r11
0x18000c6fe  mov     rcx, r15
0x18000c701  call    ?MoveNext@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000c706  mov     rax, qword ptr [rbp+var_10]
0x18000c70a  jmp     short loc_18000C710
0x18000c70c  mov     qword ptr [rbp+var_10+8], rcx
0x18000c710  movaps  xmm0, [rbp+var_10]
0x18000c714  movdqa  [rbp+var_20], xmm0
0x18000c719  test    eax, eax
0x18000c71b  jnz     loc_18000C7DA
0x18000c721  mov     eax, dword ptr [rbp+var_20]
0x18000c724  mov     rdi, r11
0x18000c727  test    eax, eax
0x18000c729  jnz     short loc_18000C72F
0x18000c72b  mov     rdi, qword ptr [rbp+var_20+8]
0x18000c72f  lea     rdx, [rbp+var_20]
0x18000c733  mov     rcx, r15
0x18000c736  call    ?MoveNext@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000c73b  mov     eax, [rdi+50h]
0x18000c73e  mov     r8, rdi
0x18000c741  mov     r11d, r12d
0x18000c744  mov     edx, 21h ; '!'
0x18000c749  add     r11, rsi
0x18000c74c  sub     r8, r11
0x18000c74f  mov     rcx, r11
0x18000c752  xor     r9d, r9d
0x18000c755  mov     [r11+44h], eax
0x18000c759  mov     eax, [rdi+54h]
0x18000c75c  mov     [r11+48h], eax
0x18000c760  mov     eax, [rdi+58h]
0x18000c763  mov     [r11+4Ch], eax
0x18000c767  lea     rax, [rdx+7FFFFFDDh]
0x18000c76e  test    rax, rax
0x18000c771  jz      short loc_18000C78A
0x18000c773  movzx   eax, word ptr [r8+rcx]
0x18000c778  test    ax, ax
0x18000c77b  jz      short loc_18000C78A
0x18000c77d  mov     [rcx], ax
0x18000c780  add     rcx, 2
0x18000c784  sub     rdx, 1
0x18000c788  jnz     short loc_18000C767
0x18000c78a  lea     rax, [rcx-2]
0x18000c78e  test    rdx, rdx
0x18000c791  cmovnz  rax, rcx
0x18000c795  mov     [rax], r9w
0x18000c799  mov     rax, rdx
0x18000c79c  neg     rax
0x18000c79f  sbb     ecx, ecx
0x18000c7a1  not     ecx
0x18000c7a3  and     ecx, 8007007Ah
0x18000c7a9  test    rdx, rdx
0x18000c7ac  jz      short loc_18000C7E7
0x18000c7ae  mov     r8d, [rdi+5Ch]; Size
0x18000c7b2  lea     rcx, [r11+50h]; void *
0x18000c7b6  mov     rdx, [rdi+48h]; Src
0x18000c7ba  call    memmove_0
0x18000c7bf  mov     eax, [rdi+5Ch]
0x18000c7c2  xor     r11d, r11d
0x18000c7c5  add     eax, 62h ; 'b'
0x18000c7c8  add     r12d, eax
0x18000c7cb  mov     eax, dword ptr [rbp+var_20]
0x18000c7ce  and     r12d, 0FFFFFFF0h
0x18000c7d2  test    eax, eax
0x18000c7d4  jz      loc_18000C724
0x18000c7da  mov     rax, [rbp+arg_10]
0x18000c7de  mov     [rax], rsi
0x18000c7e1  mov     [r13+0], r12d
0x18000c7e5  jmp     short loc_18000C813
0x18000c7e7  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c7ee  nop     dword ptr [rax+rax+00h]
0x18000c7f3  mov     ebx, eax
0x18000c7f5  test    eax, eax
0x18000c7f7  jz      short loc_18000C813
0x18000c7f9  mov     rdx, [r14+10h]; void *
0x18000c7fd  lea     rcx, stru_1800158D0; this
0x18000c804  mov     r8, rsi; void *
0x18000c807  call    ?FreePacket@CClientLibrary@@QEAAKPEAX0@Z; CClientLibrary::FreePacket(void *,void *)
0x18000c80c  jmp     short loc_18000C813
0x18000c80e  mov     ebx, 57h ; 'W'
0x18000c813  mov     eax, ebx
0x18000c815  mov     rbx, [rsp+40h+arg_8]
0x18000c81d  add     rsp, 40h
0x18000c821  pop     r15
0x18000c823  pop     r14
0x18000c825  pop     r13
0x18000c827  pop     r12
0x18000c829  pop     rdi
0x18000c82a  pop     rsi
0x18000c82b  pop     rbp
0x18000c82c  retn
```
