# CControlProtocol::ReleasePacket(void *)

- ea: `0x18000cc4c`
- end: `0x18000cdcd`
- name: `?ReleasePacket@CControlProtocol@@QEAAKPEAX@Z`
- size: `385`
- prototype: `unsigned int(CControlProtocol *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c8bc`
- `0x18000d2c0`

## callees

- `0x18000b8a0`
- `0x18000c594`
- `0x18000cbe8`
- `0x18000cc4c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cda4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cda4`

## pseudocode

```c
__int64 __fastcall CControlProtocol::ReleasePacket(CControlProtocol *this, _QWORD *a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rcx
  int v5; // eax
  struct PacketVariable *v6; // r11
  struct PacketVariable *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  char *v12; // r14
  __int64 v13; // rdi
  struct PacketVariable *v15[2]; // [rsp+20h] [rbp-10h] BYREF

  v2 = 0;
  if ( !*((_DWORD *)this + 10) )
    return 5023;
  if ( !a2 )
    return 87;
  v4 = a2[5];
  v5 = 0;
  v15[0] = 0;
  if ( v4 )
  {
    v15[1] = (struct PacketVariable *)v4;
  }
  else
  {
    v15[1] = 0;
    CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(a2 + 4, v15);
    v5 = (int)v15[0];
  }
  if ( !v5 )
  {
    while ( 1 )
    {
      v6 = v15[1];
      v7 = v15[1];
      v8 = 3LL * HIDWORD(v15[0]);
      if ( v15[1] )
        break;
LABEL_20:
      if ( !v7 )
        CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(a2 + 4, v15);
      --*((_DWORD *)a2 + 688);
      CControlProtocol::FreeVariable((CControlProtocol *)v4, (struct ControlPacket *)a2, v6);
      if ( LODWORD(v15[0]) )
        goto LABEL_23;
    }
    v4 = a2[3 * HIDWORD(v15[0]) + 5];
    v9 = a2[3 * HIDWORD(v15[0]) + 6];
    if ( v4 == v9 )
    {
      a2[3 * HIDWORD(v15[0]) + 6] = 0;
      a2[v8 + 5] = 0;
LABEL_16:
      v15[1] = 0;
      v7 = 0;
LABEL_19:
      --HIDWORD(a2[v8 + 7]);
      goto LABEL_20;
    }
    if ( v15[1] == (struct PacketVariable *)v4 )
    {
      v10 = *(_QWORD *)(v4 + 96);
      a2[3 * HIDWORD(v15[0]) + 5] = v10;
      *(_QWORD *)(v10 + 104) = 0;
      v7 = (struct PacketVariable *)a2[v8 + 5];
    }
    else
    {
      if ( v15[1] == (struct PacketVariable *)v9 )
      {
        v11 = *(_QWORD *)(v9 + 104);
        a2[3 * HIDWORD(v15[0]) + 6] = v11;
        *(_QWORD *)(v11 + 96) = 0;
        goto LABEL_16;
      }
      v7 = (struct PacketVariable *)*((_QWORD *)v15[1] + 12);
      *(_QWORD *)(*((_QWORD *)v15[1] + 13) + 96LL) = v7;
      v4 = *((_QWORD *)v6 + 12);
      *(_QWORD *)(v4 + 104) = *((_QWORD *)v6 + 13);
    }
    v15[1] = v7;
    goto LABEL_19;
  }
LABEL_23:
  a2[2] = 0;
  v12 = (char *)(a2 + 344);
  *((_DWORD *)a2 + 6) = 1;
  v13 = 113;
  do
  {
    v12 -= 24;
    wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(v12);
    --v13;
  }
  while ( v13 );
  operator delete(a2);
  return v2;
}

```

## disassembly

```asm
0x18000cc4c  mov     rax, rsp
0x18000cc4f  mov     [rax+8], rbx
0x18000cc53  mov     [rax+10h], rsi
0x18000cc57  mov     [rax+18h], rdi
0x18000cc5b  mov     [rax+20h], r14
0x18000cc5f  push    rbp
0x18000cc60  mov     rbp, rsp
0x18000cc63  sub     rsp, 30h
0x18000cc67  xor     ebx, ebx
0x18000cc69  mov     rsi, rdx
0x18000cc6c  cmp     [rcx+28h], ebx
0x18000cc6f  jnz     short loc_18000CC7B
0x18000cc71  mov     ebx, 139Fh
0x18000cc76  jmp     loc_18000CDB0
0x18000cc7b  test    rsi, rsi
0x18000cc7e  jnz     short loc_18000CC88
0x18000cc80  lea     ebx, [rsi+57h]
0x18000cc83  jmp     loc_18000CDB0
0x18000cc88  mov     rcx, [rdx+28h]
0x18000cc8c  mov     rax, rbx
0x18000cc8f  mov     [rbp+var_10], rbx
0x18000cc93  test    rcx, rcx
0x18000cc96  jnz     short loc_18000CCAF
0x18000cc98  lea     rdx, [rbp+var_10]
0x18000cc9c  mov     [rbp+var_10+8], rbx
0x18000cca0  lea     rcx, [rsi+20h]
0x18000cca4  call    ?MoveNext@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000cca9  mov     rax, [rbp+var_10]
0x18000ccad  jmp     short loc_18000CCB3
0x18000ccaf  mov     [rbp+var_10+8], rcx
0x18000ccb3  movaps  xmm0, xmmword ptr [rbp+var_10]
0x18000ccb7  movdqa  xmmword ptr [rbp+var_10], xmm0
0x18000ccbc  test    eax, eax
0x18000ccbe  jnz     loc_18000CD78
0x18000ccc4  or      r14d, 0FFFFFFFFh
0x18000ccc8  mov     r11, [rbp+var_10+8]
0x18000cccc  mov     eax, dword ptr [rbp+var_10+4]
0x18000cccf  mov     r8, r11
0x18000ccd2  lea     rdx, [rax+rax*2]
0x18000ccd6  test    r11, r11
0x18000ccd9  jz      short loc_18000CD4B
0x18000ccdb  mov     rcx, [rsi+rdx*8+28h]
0x18000cce0  mov     rax, [rsi+rdx*8+30h]
0x18000cce5  cmp     rcx, rax
0x18000cce8  jnz     short loc_18000CCF6
0x18000ccea  mov     [rsi+rdx*8+30h], rbx
0x18000ccef  mov     [rsi+rdx*8+28h], rbx
0x18000ccf4  jmp     short loc_18000CD21
0x18000ccf6  cmp     r11, rcx
0x18000ccf9  jnz     short loc_18000CD0F
0x18000ccfb  mov     rax, [rcx+60h]
0x18000ccff  mov     [rsi+rdx*8+28h], rax
0x18000cd04  mov     [rax+68h], rbx
0x18000cd08  mov     r8, [rsi+rdx*8+28h]
0x18000cd0d  jmp     short loc_18000CD42
0x18000cd0f  cmp     r11, rax
0x18000cd12  jnz     short loc_18000CD2A
0x18000cd14  mov     rax, [rax+68h]
0x18000cd18  mov     [rsi+rdx*8+30h], rax
0x18000cd1d  mov     [rax+60h], rbx
0x18000cd21  mov     [rbp+var_10+8], rbx
0x18000cd25  mov     r8, rbx
0x18000cd28  jmp     short loc_18000CD46
0x18000cd2a  mov     rax, [r11+68h]
0x18000cd2e  mov     r8, [r11+60h]
0x18000cd32  mov     [rax+60h], r8
0x18000cd36  mov     rcx, [r11+60h]
0x18000cd3a  mov     rax, [r11+68h]
0x18000cd3e  mov     [rcx+68h], rax
0x18000cd42  mov     [rbp+var_10+8], r8
0x18000cd46  add     [rsi+rdx*8+3Ch], r14d
0x18000cd4b  test    r8, r8
0x18000cd4e  jnz     short loc_18000CD5D
0x18000cd50  lea     rdx, [rbp+var_10]
0x18000cd54  lea     rcx, [rsi+20h]
0x18000cd58  call    ?MoveNext@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000cd5d  add     [rsi+0AC0h], r14d
0x18000cd64  mov     r8, r11; struct PacketVariable *
0x18000cd67  mov     rdx, rsi; struct ControlPacket *
0x18000cd6a  call    ?FreeVariable@CControlProtocol@@AEAAXPEAUControlPacket@@PEAUPacketVariable@@@Z; CControlProtocol::FreeVariable(ControlPacket *,PacketVariable *)
0x18000cd6f  cmp     dword ptr [rbp+var_10], ebx
0x18000cd72  jz      loc_18000CCC8
0x18000cd78  mov     [rsi+10h], rbx
0x18000cd7c  lea     r14, [rsi+0AC0h]
0x18000cd83  mov     dword ptr [rsi+18h], 1
0x18000cd8a  mov     edi, 71h ; 'q'
0x18000cd8f  sub     r14, 18h
0x18000cd93  mov     rcx, r14
0x18000cd96  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18000cd9b  sub     rdi, 1
0x18000cd9f  jnz     short loc_18000CD8F
0x18000cda1  mov     rcx, rsi
0x18000cda4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cdab  nop     dword ptr [rax+rax+00h]
0x18000cdb0  mov     rsi, [rsp+30h+arg_8]
0x18000cdb5  mov     eax, ebx
0x18000cdb7  mov     rbx, [rsp+30h+arg_0]
0x18000cdbc  mov     rdi, [rsp+30h+arg_10]
0x18000cdc1  mov     r14, [rsp+30h+arg_18]
0x18000cdc6  add     rsp, 30h
0x18000cdca  pop     rbp
0x18000cdcb  retn
```
