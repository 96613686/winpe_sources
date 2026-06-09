# TdxEventInspectTransportAddress

- ea: `0x140001ce0`
- end: `0x14000223f`
- name: `TdxEventInspectTransportAddress`
- size: `1375`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001550`
- `0x140001980`
- `0x140001ce0`
- `0x140002250`
- `0x140002850`
- `0x1400034c0`
- `0x1400054ec`
- `0x140012ee4`
- `0x140018090`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140001e19`
- `ntoskrnl!KeLowerIrql` at `0x140001e19`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400021a1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400021a1`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000218e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000218e`
- `ntoskrnl!IofCompleteRequest` at `0x14000220a`
- `ntoskrnl!IofCompleteRequest` at `0x14000220a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001f2c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001fb2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002076`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400021b0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001f2c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001fb2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002076`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400021b0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001e01`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001fc8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001ff3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002107`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000216b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000217a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400021be`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001e01`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001fc8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001ff3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002107`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000216b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000217a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400021be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d05`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d05`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001da7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001f44`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002012`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000211a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001da7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001f44`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002012`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000211a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400021d0`

## pseudocode

```c
void __fastcall TdxEventInspectTransportAddress(__int64 a1, __int64 a2)
{
  ADDRESS_FAMILY **v4; // r15
  KIRQL v5; // bp
  __int64 v6; // rdi
  int v7; // r12d
  ADDRESS_FAMILY *v8; // r9
  _QWORD *v9; // rcx
  _QWORD *v10; // r14
  char v11; // r12
  _QWORD *v12; // rbx
  __int64 v13; // r8
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  ADDRESS_FAMILY *v18; // rax
  __int128 v19; // xmm0
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // r8
  ADDRESS_FAMILY *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // r15d
  __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // r8d
  __int64 v29; // rbx
  __int64 v30; // r8
  _QWORD *v31; // r14
  _QWORD *v32; // rax
  KSPIN_LOCK *v33; // r12
  ADDRESS_FAMILY *v34; // rcx
  __int64 v35; // r8
  _QWORD *v36; // r8
  __int128 v37; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *Irql; // [rsp+80h] [rbp+8h] BYREF
  ADDRESS_FAMILY *v39; // [rsp+88h] [rbp+10h]
  PKSPIN_LOCK SpinLock; // [rsp+90h] [rbp+18h]

  *(_DWORD *)(a2 + 32) = 2;
  v4 = (ADDRESS_FAMILY **)(a2 + 24);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  if ( (*(_DWORD *)a1 & 0x20) != 0 && (unsigned __int8)INETADDR_ISV4MAPPED(*v4) )
  {
    v6 = *(_QWORD *)(a1 + 504);
    if ( v6 )
      DbgTdxReferenceTransportAddress(*(_QWORD *)(a1 + 504), "minio\\netio\\session\\tdi\\address.h", 363);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 8));
    if ( !v6 )
      goto LABEL_19;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v6 + 8));
  }
  else
  {
    v6 = a1;
  }
  if ( !v6 )
  {
LABEL_19:
    KeLowerIrql(v5);
    return;
  }
  v7 = *(_DWORD *)v6;
  if ( (*(_DWORD *)v6 & 4) != 0 )
  {
    v8 = *v4;
    v9 = (_QWORD *)(v6 + 360);
    v10 = *(_QWORD **)(v6 + 360);
    v39 = *v4;
    v11 = (v7 & 0x40) != 0;
    Irql = 0;
    while ( v10 != v9 )
    {
      v26 = v10[8];
      Irql = v10;
      v27 = *(_QWORD *)(v26 + 16);
      if ( !v27 )
        break;
      v28 = *(_DWORD *)(v27 + 32);
      if ( !v28 )
        break;
      if ( (unsigned __int8)SockAddrEqualsTaList((_DWORD)v8, *(_QWORD *)(v27 + 40), v28, (_DWORD)v8, v11) )
      {
        v29 = v10[2];
        SpinLock = (PKSPIN_LOCK)(v29 + 8);
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v29 + 8));
        if ( *(_DWORD *)(v29 + 76) == 1 )
        {
          KeReleaseSpinLockFromDpcLevel(SpinLock);
          v9 = (_QWORD *)(v6 + 360);
          break;
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v29 + 8));
      }
      v10 = (_QWORD *)*v10;
      v9 = (_QWORD *)(v6 + 360);
      LODWORD(v8) = (_DWORD)v39;
    }
    v12 = 0;
    if ( v10 != v9 )
      v12 = Irql;
    if ( v12 )
    {
      v31 = v12 - 15;
      v32 = (_QWORD *)v12[8];
      v39 = (ADDRESS_FAMILY *)v12[2];
      v33 = (KSPIN_LOCK *)(v39 + 4);
      Irql = v32;
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v39 + 1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v34 = *v4;
        v37 = (unsigned __int64)*v4;
        WORD4(v37) = SOCKADDR_SIZE(*v34);
        WPP_SF_qq_SOCKADDR_(*(_QWORD *)(v35 + 24), 27, v35, v6, (_DWORD)v12 - 120, (__int64)&v37);
      }
      v36 = Irql;
      if ( (Irql[1] & 1) == 0 )
      {
        KeReleaseSpinLockFromDpcLevel(v33);
        KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 8), v5);
        if ( v6 == a1 )
          goto LABEL_13;
        v30 = 2043;
        goto LABEL_51;
      }
      v14 = *v12;
      if ( *(_QWORD **)(*v12 + 8LL) != v12
        || (v15 = (_QWORD *)v12[1], (_QWORD *)*v15 != v12)
        || (*v15 = v14, *(_QWORD *)(v14 + 8) = v15, v16 = v31[21], *(_QWORD **)(v16 + 8) != v31 + 21)
        || (v17 = (_QWORD *)v31[22], (_QWORD *)*v17 != v31 + 21) )
      {
        __fastfail(3u);
      }
      v18 = v39;
      *v17 = v16;
      *(_QWORD *)(v16 + 8) = v17;
      LODWORD(Irql) = 0;
      *((_DWORD *)v18 + 19) = 2;
      v19 = *(_OWORD *)a2;
      *(_DWORD *)v18 |= 2u;
      *(_OWORD *)(v18 + 124) = v19;
      v20 = v36[3];
      if ( v20 && (v21 = *(_DWORD *)(v20 + 32)) != 0 )
      {
        v22 = *(_QWORD *)(v20 + 40);
        v23 = *v4;
        v24 = *(_DWORD *)v6 >> 6;
        LOBYTE(v24) = (*(_DWORD *)v6 & 0x40) != 0;
        LODWORD(Irql) = v21;
        v25 = SockAddrToTaList(v23, v24, v22, &Irql);
      }
      else
      {
        v25 = (unsigned int)Irql;
      }
      if ( _InterlockedExchange64(v31 + 13, 0) )
      {
        KeReleaseSpinLockFromDpcLevel(v33);
      }
      else
      {
        LOBYTE(Irql) = 0;
        KeReleaseSpinLockFromDpcLevel(v33);
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v6 + 8));
        IoAcquireCancelSpinLock((PKIRQL)&Irql);
        IoReleaseCancelSpinLock((KIRQL)Irql);
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v6 + 8));
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 8), v5);
      if ( v6 != a1 )
        DbgTdxDereferenceTransportAddress(v6, "minio\\netio\\session\\tdi\\address.c", 2108);
      v31[7] = v25;
      *((_DWORD *)v31 + 12) = 0;
      IofCompleteRequest((PIRP)v31, 2);
      DbgTdxDereferenceTransportAddress(v6, "minio\\netio\\session\\tdi\\address.c", 2128);
      *(_DWORD *)(a2 + 32) = 3;
    }
    else if ( *(_QWORD *)(v6 + 392) )
    {
      if ( TdxPrematureConnectIndDisabled )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 8), v5);
        if ( v6 == a1 )
        {
LABEL_13:
          *(_DWORD *)(a2 + 32) = 1;
          return;
        }
        v30 = 1998;
LABEL_51:
        DbgTdxDereferenceTransportAddress(v6, "minio\\netio\\session\\tdi\\address.c", v30);
        goto LABEL_13;
      }
      TdxCallConnectionHandler(v6, (__int128 *)a2, 0, v5);
      if ( v6 != a1 )
      {
        v13 = 2012;
LABEL_22:
        DbgTdxDereferenceTransportAddress(v6, "minio\\netio\\session\\tdi\\address.c", v13);
      }
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 8), v5);
      if ( v6 != a1 )
        DbgTdxDereferenceTransportAddress(v6, "minio\\netio\\session\\tdi\\address.c", 1982);
      *(_DWORD *)(a2 + 32) = 2;
    }
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 8), v5);
    if ( v6 != a1 )
    {
      v13 = 1962;
      goto LABEL_22;
    }
  }
}

```

## disassembly

```asm
0x140001ce0  mov     [rsp+arg_18], rbx
0x140001ce5  push    rbp
0x140001ce6  push    rsi
0x140001ce7  push    rdi
0x140001ce8  push    r12
0x140001cea  push    r13
0x140001cec  push    r14
0x140001cee  push    r15
0x140001cf0  sub     rsp, 40h
0x140001cf4  mov     rsi, rcx
0x140001cf7  mov     dword ptr [rdx+20h], 2
0x140001cfe  add     rcx, 8; SpinLock
0x140001d02  mov     r13, rdx
0x140001d05  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d0c  nop     dword ptr [rax+rax+00h]
0x140001d11  mov     r8d, [rsi]
0x140001d14  lea     r15, [r13+18h]
0x140001d18  mov     bpl, al
0x140001d1b  test    r8b, 20h
0x140001d1f  jnz     loc_140001DDD
0x140001d25  mov     rdi, rsi
0x140001d28  test    rdi, rdi
0x140001d2b  jz      loc_140001E16
0x140001d31  mov     r12d, [rdi]
0x140001d34  test    r12b, 4
0x140001d38  jz      loc_140001F3D
0x140001d3e  mov     r9, [r15]
0x140001d41  lea     rcx, [rdi+168h]
0x140001d48  mov     r14, [rcx]
0x140001d4b  shr     r12d, 6
0x140001d4f  mov     [rsp+78h+arg_8], r9
0x140001d57  and     r12b, 1
0x140001d5b  mov     [rsp+78h+Irql], 0
0x140001d67  cmp     r14, rcx
0x140001d6a  jnz     loc_140001F64
0x140001d70  xor     ebx, ebx
0x140001d72  cmp     r14, rcx
0x140001d75  cmovnz  rbx, [rsp+78h+Irql]
0x140001d7e  test    rbx, rbx
0x140001d81  jnz     loc_140002050
0x140001d87  cmp     [rdi+188h], rbx
0x140001d8e  jz      loc_14000200B
0x140001d94  cmp     cs:TdxPrematureConnectIndDisabled, bl
0x140001d9a  jz      loc_140001E27
0x140001da0  lea     rcx, [rdi+8]; SpinLock
0x140001da4  mov     dl, bpl; NewIrql
0x140001da7  call    cs:__imp_KeReleaseSpinLock
0x140001dae  nop     dword ptr [rax+rax+00h]
0x140001db3  cmp     rdi, rsi
0x140001db6  jnz     loc_140002045
0x140001dbc  mov     dword ptr [r13+20h], 1
0x140001dc4  mov     rbx, [rsp+78h+arg_18]
0x140001dcc  add     rsp, 40h
0x140001dd0  pop     r15
0x140001dd2  pop     r14
0x140001dd4  pop     r13
0x140001dd6  pop     r12
0x140001dd8  pop     rdi
0x140001dd9  pop     rsi
0x140001dda  pop     rbp
0x140001ddb  retn
0x140001ddd  mov     rcx, [r15]
0x140001de0  call    INETADDR_ISV4MAPPED
0x140001de5  test    al, al
0x140001de7  jz      loc_140001D25
0x140001ded  mov     rdi, [rsi+1F8h]
0x140001df4  test    rdi, rdi
0x140001df7  jnz     loc_140001F0E
0x140001dfd  lea     rcx, [rsi+8]; SpinLock
0x140001e01  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140001e08  nop     dword ptr [rax+rax+00h]
0x140001e0d  test    rdi, rdi
0x140001e10  jnz     loc_140001F28
0x140001e16  mov     cl, bpl; NewIrql
0x140001e19  call    cs:__imp_KeLowerIrql
0x140001e20  nop     dword ptr [rax+rax+00h]
0x140001e25  jmp     short loc_140001DC4
0x140001e27  mov     r9b, bpl
0x140001e2a  xor     r8d, r8d
0x140001e2d  mov     rdx, r13
0x140001e30  mov     rcx, rdi
0x140001e33  call    TdxCallConnectionHandler
0x140001e38  cmp     rdi, rsi
0x140001e3b  jz      short loc_140001DC4
0x140001e3d  mov     r8d, 7DCh
0x140001e43  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140001e4a  mov     rcx, rdi
0x140001e4d  call    DbgTdxDereferenceTransportAddress
0x140001e52  jmp     loc_140001DC4
0x140001e57  mov     rcx, [rbx]
0x140001e5a  cmp     [rcx+8], rbx
0x140001e5e  jnz     loc_140002238
0x140001e64  mov     rax, [rbx+8]
0x140001e68  cmp     [rax], rbx
0x140001e6b  jnz     loc_140002238
0x140001e71  mov     [rax], rcx
0x140001e74  mov     [rcx+8], rax
0x140001e78  lea     rax, [r14+0A8h]
0x140001e7f  mov     rdx, [rax]
0x140001e82  cmp     [rdx+8], rax
0x140001e86  jnz     loc_140002238
0x140001e8c  mov     rcx, [rax+8]
0x140001e90  cmp     [rcx], rax
0x140001e93  jnz     loc_140002238
0x140001e99  mov     rax, [rsp+78h+arg_8]
0x140001ea1  mov     [rcx], rdx
0x140001ea4  mov     [rdx+8], rcx
0x140001ea8  mov     dword ptr [rsp+78h+Irql], 0
0x140001eb3  mov     dword ptr [rax+4Ch], 2
0x140001eba  movups  xmm0, xmmword ptr [r13+0]
0x140001ebf  or      dword ptr [rax], 2
0x140001ec2  movdqu  xmmword ptr [rax+0F8h], xmm0
0x140001eca  mov     r8, [r8+18h]
0x140001ece  test    r8, r8
0x140001ed1  jz      loc_140002149
0x140001ed7  mov     eax, [r8+20h]
0x140001edb  test    eax, eax
0x140001edd  jz      loc_140002149
0x140001ee3  mov     edx, [rdi]
0x140001ee5  lea     r9, [rsp+78h+Irql]
0x140001eed  mov     r8, [r8+28h]
0x140001ef1  mov     rcx, [r15]
0x140001ef4  shr     edx, 6
0x140001ef7  and     dl, 1
0x140001efa  mov     dword ptr [rsp+78h+Irql], eax
0x140001f01  call    SockAddrToTaList
0x140001f06  mov     r15d, eax
0x140001f09  jmp     loc_140002151
0x140001f0e  mov     r8d, 16Bh
0x140001f14  lea     rdx, aMinioNetioSess; "minio\\netio\\session\\tdi\\address.h"
0x140001f1b  mov     rcx, rdi
0x140001f1e  call    DbgTdxReferenceTransportAddress
0x140001f23  jmp     loc_140001DFD
0x140001f28  lea     rcx, [rdi+8]; SpinLock
0x140001f2c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140001f33  nop     dword ptr [rax+rax+00h]
0x140001f38  jmp     loc_140001D28
0x140001f3d  lea     rcx, [rdi+8]; SpinLock
0x140001f41  mov     dl, bpl; NewIrql
0x140001f44  call    cs:__imp_KeReleaseSpinLock
0x140001f4b  nop     dword ptr [rax+rax+00h]
0x140001f50  cmp     rdi, rsi
0x140001f53  jz      loc_140001DC4
0x140001f59  mov     r8d, 7AAh
0x140001f5f  jmp     loc_140001E43
0x140001f64  mov     rax, [r14+40h]
0x140001f68  mov     [rsp+78h+Irql], r14
0x140001f70  mov     rdx, [rax+10h]
0x140001f74  test    rdx, rdx
0x140001f77  jz      loc_140001D70
0x140001f7d  mov     r8d, [rdx+20h]
0x140001f81  test    r8d, r8d
0x140001f84  jz      loc_140001D70
0x140001f8a  mov     rdx, [rdx+28h]
0x140001f8e  mov     rcx, r9
0x140001f91  mov     byte ptr [rsp+78h+var_58], r12b
0x140001f96  call    SockAddrEqualsTaList
0x140001f9b  test    al, al
0x140001f9d  jz      short loc_140001FD4
0x140001f9f  mov     rbx, [r14+10h]
0x140001fa3  lea     rax, [rbx+8]
0x140001fa7  mov     rcx, rax; SpinLock
0x140001faa  mov     [rsp+78h+SpinLock], rax
0x140001fb2  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140001fb9  nop     dword ptr [rax+rax+00h]
0x140001fbe  cmp     dword ptr [rbx+4Ch], 1
0x140001fc2  jz      short loc_140001FEB
0x140001fc4  lea     rcx, [rbx+8]; SpinLock
0x140001fc8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140001fcf  nop     dword ptr [rax+rax+00h]
0x140001fd4  mov     r14, [r14]
0x140001fd7  lea     rcx, [rdi+168h]
0x140001fde  mov     r9, [rsp+78h+arg_8]
0x140001fe6  jmp     loc_140001D67
0x140001feb  mov     rcx, [rsp+78h+SpinLock]; SpinLock
0x140001ff3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140001ffa  nop     dword ptr [rax+rax+00h]
0x140001fff  lea     rcx, [rdi+168h]
0x140002006  jmp     loc_140001D70
0x14000200b  lea     rcx, [rdi+8]; SpinLock
0x14000200f  mov     dl, bpl; NewIrql
0x140002012  call    cs:__imp_KeReleaseSpinLock
0x140002019  nop     dword ptr [rax+rax+00h]
0x14000201e  cmp     rdi, rsi
0x140002021  jz      short loc_140002038
0x140002023  mov     r8d, 7BEh
0x140002029  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140002030  mov     rcx, rdi
0x140002033  call    DbgTdxDereferenceTransportAddress
0x140002038  mov     dword ptr [r13+20h], 2
0x140002040  jmp     loc_140001DC4
0x140002045  mov     r8d, 7CEh
0x14000204b  jmp     loc_140002135
0x140002050  mov     r12, [rbx+10h]
0x140002054  lea     r14, [rbx-78h]
0x140002058  mov     rax, [r14+0B8h]
0x14000205f  mov     [rsp+78h+arg_8], r12
0x140002067  add     r12, 8
0x14000206b  mov     rcx, r12; SpinLock
0x14000206e  mov     [rsp+78h+Irql], rax
0x140002076  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000207d  nop     dword ptr [rax+rax+00h]
0x140002082  mov     r8, cs:WPP_GLOBAL_Control
0x140002089  lea     rax, WPP_GLOBAL_Control
0x140002090  cmp     r8, rax
0x140002093  jz      short loc_1400020F1
0x140002095  cmp     byte ptr [r8+29h], 5
0x14000209a  jb      short loc_1400020F1
0x14000209c  test    dword ptr [r8+2Ch], 200h
0x1400020a4  jz      short loc_1400020F1
0x1400020a6  mov     rcx, [r15]
0x1400020a9  xorps   xmm0, xmm0
0x1400020ac  movups  [rsp+78h+var_48], xmm0
0x1400020b1  mov     qword ptr [rsp+78h+var_48], rcx
0x1400020b6  movzx   ecx, word ptr [rcx]; af
0x1400020b9  call    SOCKADDR_SIZE
0x1400020be  movzx   edx, al
0x1400020c1  mov     r9, rdi
0x1400020c4  mov     word ptr [rsp+78h+var_48+8], dx
0x1400020c9  lea     rax, [rsp+78h+var_48]
0x1400020ce  movaps  xmm0, [rsp+78h+var_48]
0x1400020d3  mov     edx, 1Bh
0x1400020d8  movdqa  [rsp+78h+var_48], xmm0
0x1400020de  mov     rcx, [r8+18h]
0x1400020e2  mov     [rsp+78h+var_50], rax
0x1400020e7  mov     [rsp+78h+var_58], r14
0x1400020ec  call    WPP_SF_qq_SOCKADDR_
0x1400020f1  mov     r8, [rsp+78h+Irql]
0x1400020f9  test    byte ptr [r8+8], 1
0x1400020fe  jnz     loc_140001E57
0x140002104  mov     rcx, r12; SpinLock
0x140002107  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000210e  nop     dword ptr [rax+rax+00h]
0x140002113  lea     rcx, [rdi+8]; SpinLock
0x140002117  mov     dl, bpl; NewIrql
0x14000211a  call    cs:__imp_KeReleaseSpinLock
0x140002121  nop     dword ptr [rax+rax+00h]
0x140002126  cmp     rdi, rsi
0x140002129  jz      loc_140001DBC
0x14000212f  mov     r8d, 7FBh
0x140002135  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x14000213c  mov     rcx, rdi
0x14000213f  call    DbgTdxDereferenceTransportAddress
0x140002144  jmp     loc_140001DBC
0x140002149  mov     r15d, dword ptr [rsp+78h+Irql]
0x140002151  xor     ecx, ecx
0x140002153  lea     rbx, [rdi+8]
0x140002157  xchg    rcx, [r14+68h]
0x14000215b  test    rcx, rcx
0x14000215e  mov     rcx, r12; SpinLock
0x140002161  jnz     short loc_1400021BE
0x140002163  mov     byte ptr [rsp+78h+Irql], 0
0x14000216b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002172  nop     dword ptr [rax+rax+00h]
0x140002177  mov     rcx, rbx; SpinLock
0x14000217a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002181  nop     dword ptr [rax+rax+00h]
0x140002186  lea     rcx, [rsp+78h+Irql]; Irql
0x14000218e  call    cs:__imp_IoAcquireCancelSpinLock
0x140002195  nop     dword ptr [rax+rax+00h]
0x14000219a  mov     cl, byte ptr [rsp+78h+Irql]; Irql
0x1400021a1  call    cs:__imp_IoReleaseCancelSpinLock
0x1400021a8  nop     dword ptr [rax+rax+00h]
0x1400021ad  mov     rcx, rbx; SpinLock
0x1400021b0  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400021b7  nop     dword ptr [rax+rax+00h]
0x1400021bc  jmp     short loc_1400021CA
0x1400021be  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400021c5  nop     dword ptr [rax+rax+00h]
0x1400021ca  mov     dl, bpl; NewIrql
0x1400021cd  mov     rcx, rbx; SpinLock
0x1400021d0  call    cs:__imp_KeReleaseSpinLock
0x1400021d7  nop     dword ptr [rax+rax+00h]
0x1400021dc  cmp     rdi, rsi
0x1400021df  jz      short loc_1400021F6
0x1400021e1  mov     r8d, 83Ch
0x1400021e7  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x1400021ee  mov     rcx, rdi
0x1400021f1  call    DbgTdxDereferenceTransportAddress
0x1400021f6  mov     eax, r15d
0x1400021f9  mov     dl, 2; PriorityBoost
0x1400021fb  mov     rcx, r14; Irp
0x1400021fe  mov     [r14+38h], rax
0x140002202  mov     dword ptr [r14+30h], 0
0x14000220a  call    cs:__imp_IofCompleteRequest
0x140002211  nop     dword ptr [rax+rax+00h]
0x140002216  mov     r8d, 850h
0x14000221c  lea     rdx, aMinioNetioSess_2; "minio\\netio\\session\\tdi\\address.c"
0x140002223  mov     rcx, rdi
0x140002226  call    DbgTdxDereferenceTransportAddress
0x14000222b  mov     dword ptr [r13+20h], 3
0x140002233  jmp     loc_140001DC4
0x140002238  mov     ecx, 3
0x14000223d  int     29h; Win8: RtlFailFast(ecx)
```
