# UdpSetDestinationEndpoint

- ea: `0x1400125a0`
- end: `0x140012cb1`
- name: `UdpSetDestinationEndpoint`
- size: `1809`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `4`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011da0`
- `0x140011ed4`
- `0x140017170`
- `0x1400b6250`

## callees

- `0x1400125a0`
- `0x140012cb8`
- `0x140012d90`
- `0x140013140`
- `0x140014430`
- `0x140017060`
- `0x140024ec8`
- `0x140026ec0`
- `0x140030380`
- `0x140039860`
- `0x14003b680`
- `0x140064be0`
- `0x1400e6890`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400125fa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400125fa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012a20`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012aad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012c62`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012a20`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012aad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140012c62`
- `NETIO!RtlCompute37Hash` at `0x1400129a3`
- `NETIO!RtlCompute37Hash` at `0x1400129c7`
- `NETIO!RtlCompute37Hash` at `0x1400129e6`
- `NETIO!RtlCompute37Hash` at `0x1400129a3`
- `NETIO!RtlCompute37Hash` at `0x1400129c7`
- `NETIO!RtlCompute37Hash` at `0x1400129e6`

## pseudocode

```c
__int64 __fastcall UdpSetDestinationEndpoint(PKSPIN_LOCK SpinLock, __int16 *a2, char a3)
{
  int v5; // edx
  int v6; // eax
  int v7; // esi
  __int64 v8; // r12
  KSPIN_LOCK v9; // r13
  KSPIN_LOCK v10; // r15
  KSPIN_LOCK v11; // rdx
  KSPIN_LOCK v12; // r9
  KSPIN_LOCK v13; // rbx
  KSPIN_LOCK v14; // r10
  int v15; // esi
  KSPIN_LOCK v16; // r11
  __int16 v17; // ax
  __int16 v18; // r8
  KSPIN_LOCK v19; // rax
  KSPIN_LOCK v20; // rsi
  _QWORD *v21; // rcx
  __int64 (__fastcall *v22)(); // rax
  int v23; // eax
  __int64 (__fastcall *v24)(KSPIN_LOCK *); // rax
  int v25; // eax
  int v26; // ecx
  __int64 v27; // rdx
  __int64 (__fastcall *v28)(_QWORD, __int64, _QWORD); // rax
  int v29; // ebx
  int v30; // eax
  KSPIN_LOCK v31; // rcx
  unsigned __int16 v32; // ax
  int v33; // eax
  int v34; // ecx
  __int64 v35; // rax
  __int64 (__fastcall *v36)(KSPIN_LOCK *); // rax
  __int16 v37; // ax
  __int64 v38; // rcx
  unsigned int v39; // eax
  KSPIN_LOCK v40; // rcx
  unsigned int v41; // eax
  KSPIN_LOCK v42; // r14
  __int16 v44; // dx
  __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  KSPIN_LOCK v48; // rax
  unsigned __int16 v49[2]; // [rsp+20h] [rbp-E0h] BYREF
  char v50; // [rsp+24h] [rbp-DCh]
  unsigned int v51; // [rsp+26h] [rbp-DAh]
  int v52; // [rsp+2Ch] [rbp-D4h]
  KSPIN_LOCK v53; // [rsp+30h] [rbp-D0h]
  int v54; // [rsp+38h] [rbp-C8h]
  KSPIN_LOCK v55; // [rsp+40h] [rbp-C0h]
  _DWORD *v56; // [rsp+48h] [rbp-B8h]
  KSPIN_LOCK v57; // [rsp+50h] [rbp-B0h]
  KSPIN_LOCK v58; // [rsp+58h] [rbp-A8h]
  KSPIN_LOCK v59; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h]
  _QWORD *v61; // [rsp+70h] [rbp-90h]
  __int64 v62; // [rsp+78h] [rbp-88h]
  __int64 v63; // [rsp+80h] [rbp-80h]
  __int64 v64; // [rsp+88h] [rbp-78h]
  KSPIN_LOCK v65; // [rsp+90h] [rbp-70h]
  KSPIN_LOCK v66; // [rsp+98h] [rbp-68h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v68[20]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v69[18]; // [rsp+160h] [rbp+60h] BYREF

  v50 = a3;
  v49[0] = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(v69, 0, 0x88u);
  KeAcquireInStackQueuedSpinLock(SpinLock, &LockHandle);
  while ( *((_DWORD *)SpinLock + 2) )
    ;
  if ( (SpinLock[3] & 1) == 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 3221226041LL;
  }
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v52 = 0;
  if ( !a2 )
    goto LABEL_37;
  v11 = SpinLock[13];
  v49[0] = a2[1];
  if ( v11 )
  {
    if ( *(_DWORD *)(v11 + 24) == 1 )
    {
      v8 = InetValidateLocalAddressAf(SpinLock[14]);
      if ( !v8 )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        return 3221225793LL;
      }
    }
  }
  v12 = SpinLock[10];
  v13 = 0;
  v55 = 0;
  v66 = 0;
  v58 = 0;
  v56 = (_DWORD *)v12;
  if ( !v12 )
  {
    v7 = -1073741808;
    goto LABEL_31;
  }
  v14 = SpinLock[5];
  v15 = SpinLock[3] & 0x20;
  v16 = SpinLock[14];
  HIWORD(v51) = a2[1];
  LOWORD(v51) = *((_WORD *)SpinLock + 84);
  v65 = SpinLock[9];
  v17 = *((_WORD *)SpinLock + 87);
  v53 = v14;
  v57 = v16;
  if ( !v17 || v15 )
  {
    v44 = *a2;
    if ( *a2 == 23 && IN6_IS_ADDR_V4MAPPED((const IN6_ADDR *)(a2 + 4)) )
    {
      if ( v15 )
      {
        v10 = v16;
      }
      else
      {
        v46 = InetFindAndReferenceAf(&UdpInetTransport, 2);
        v12 = (KSPIN_LOCK)v56;
        v45 = a2 + 4;
        v14 = v53;
        v10 = v46;
        v16 = v57;
      }
      if ( *a2 != 23 )
        v45 = a2 + 2;
      v19 = (KSPIN_LOCK)(v45 + 6);
    }
    else
    {
      if ( v15 || *(_WORD *)(v16 + 24) != v44 )
      {
        v10 = 0;
        goto LABEL_82;
      }
      v19 = (KSPIN_LOCK)(a2 + 4);
      v10 = v16;
      if ( v44 != 23 )
        goto LABEL_13;
    }
  }
  else
  {
    v18 = *a2;
    if ( v17 != *a2 || v17 == 23 && (unsigned __int8)INETADDR_ISV4MAPPED(a2) )
      v10 = 0;
    else
      v10 = v16;
    if ( v18 != 23 )
    {
LABEL_13:
      v19 = (KSPIN_LOCK)(a2 + 2);
      goto LABEL_14;
    }
    v19 = (KSPIN_LOCK)(a2 + 4);
  }
LABEL_14:
  v53 = v19;
  if ( !v10 )
  {
LABEL_82:
    v7 = -1073741305;
    goto LABEL_31;
  }
  if ( v15 || v16 != v10 )
    v20 = 0;
  else
    v20 = v12;
  if ( SpinLock != (PKSPIN_LOCK)-232LL )
  {
    if ( v14 == v10 )
    {
      v9 = SpinLock[29];
    }
    else if ( v10 == SpinLock[32] )
    {
      v9 = SpinLock[31];
    }
  }
  if ( *a2 == 23 )
    LODWORD(v13) = *((_DWORD *)a2 + 6);
  v54 = dword_140229570;
  memset(v68, 0, sizeof(v68));
  v68[2] = v9;
  LODWORD(v68[3]) = 0;
  v68[4] = 0;
  LODWORD(v68[7]) = v13;
  v68[8] = v53;
  if ( v20 )
    v68[0] = v20;
  else
    LODWORD(v68[1]) = *v56;
  if ( v8 )
  {
    v68[9] = v8;
  }
  else
  {
    LODWORD(v68[10]) = scopeid_unspecified;
    v68[11] = 0;
  }
  v21 = *(_QWORD **)(v10 + 40);
  v68[19] = __PAIR64__(v51, v54);
  v68[16] = v65;
  v22 = *(__int64 (__fastcall **)())(*(_QWORD *)(v10 + 48) + 64LL);
  if ( v22 == IpNlpJoinPath )
    v23 = IppJoinPath(*v21, v68);
  else
    v23 = ((__int64 (__fastcall *)(_QWORD *, _QWORD *))v22)(v21, v68);
  v9 = v68[15];
  v7 = v23;
  if ( v23 < 0 && v10 != v57 )
    InetDereferenceAf(v10);
  v13 = v66;
LABEL_31:
  if ( v7 >= 0 )
  {
    v59 = v9;
    v62 = 0;
    v60 = 0;
    v61 = v69;
    v24 = *(__int64 (__fastcall **)(KSPIN_LOCK *))(*(_QWORD *)(v10 + 48) + 80LL);
    if ( (char *)v24 == (char *)IpNlpQueryPathInformation )
      v25 = IpNlpQueryPathInformation(&v59);
    else
      v25 = v24(&v59);
    v26 = v52;
    if ( v25 >= 0 )
      v26 = v62;
    v27 = *((unsigned __int16 *)SpinLock + 84);
    v28 = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD))*((_QWORD *)UdpRssHash + 1);
    v29 = *(_DWORD *)(v9 + 12);
    v52 = v26;
    v30 = v28(*(unsigned __int16 *)(v10 + 24), v27, v49[0]);
    v5 = v52;
    v6 = v29 ^ v30;
LABEL_37:
    v13 = SpinLock[37];
    v55 = SpinLock[39];
    v31 = SpinLock[38];
    *((_DWORD *)SpinLock + 71) = v6;
    v32 = v49[0];
    v58 = v31;
    SpinLock[37] = v9;
    SpinLock[39] = v10;
    *((_WORD *)SpinLock + 140) = v32;
    if ( a2 )
    {
      SpinLock[38] = v69[14];
      *((_DWORD *)SpinLock + 72) = HIDWORD(v69[15]);
      v33 = (LOBYTE(v69[15]) != 0 ? 0x200000 : 0) | SpinLock[3] & 0xFFDFFFFF;
      *((_DWORD *)SpinLock + 6) = v33;
      if ( v5 || *(_WORD *)(v10 + 24) == 23 && BYTE1(v69[15]) )
        v34 = 0x400000;
      else
        v34 = 0;
      *((_DWORD *)SpinLock + 6) = v34 | v33 & 0xFFBFFFFF;
      UdpCacheDefaultUsoInformation(SpinLock);
      v59 = *(_QWORD *)(v10 + 40);
      v35 = *(_QWORD *)v9;
      v64 = 0;
      v63 = 17;
      v60 = 0;
      v61 = **(_QWORD ***)(v35 + 16);
      v62 = *(_QWORD *)(v9 + 16);
      v36 = *(__int64 (__fastcall **)(KSPIN_LOCK *))(*(_QWORD *)(v10 + 48) + 8LL);
      if ( (char *)v36 == (char *)IpNlpChecksumDatagram )
        v37 = IpNlpChecksumDatagram(&v59);
      else
        v37 = v36(&v59);
      v38 = *((unsigned int *)SpinLock + 81);
      *((_WORD *)SpinLock + 141) = v37;
      v39 = RtlCompute37Hash(v38, *(_QWORD *)(*(_QWORD *)v9 + 16LL), *(unsigned __int16 *)(SpinLock[39] + 72));
      v40 = SpinLock[39];
      *((_DWORD *)SpinLock + 80) = v39;
      v41 = RtlCompute37Hash(v39, v9 + 16, *(unsigned __int16 *)(v40 + 72));
      *((_DWORD *)SpinLock + 80) = v41;
      *((_DWORD *)SpinLock + 80) = RtlCompute37Hash(v41, v49, 2);
    }
    else
    {
      SpinLock[38] = 0;
      SpinLock[36] = 0;
    }
    if ( v8 )
    {
      v48 = SpinLock[13];
      if ( v8 != v48 )
      {
        SpinLock[13] = v8;
        v8 = v48;
      }
    }
    if ( a2 && v50 )
    {
      *((_DWORD *)SpinLock + 6) |= 0x800u;
    }
    else
    {
      v47 = *((_DWORD *)SpinLock + 6);
      if ( (v47 & 0x800) != 0 )
        *((_DWORD *)SpinLock + 6) = v47 & 0xFFFFF7FF;
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v42 = v55;
  if ( v58 )
    InetDereferenceNextHopAf(v55);
  if ( v13 )
  {
    InetLeavePathAf(v42, v13);
    InetDereferenceAf(v42);
  }
  if ( v8 )
    InetDereferenceLocalAddressAf(SpinLock[14], v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400125a0  push    rbp
0x1400125a2  push    rdi
0x1400125a3  push    r14
0x1400125a5  lea     rbp, [rsp-120h]
0x1400125ad  sub     rsp, 220h
0x1400125b4  mov     rax, cs:__security_cookie
0x1400125bb  xor     rax, rsp
0x1400125be  mov     [rbp+130h+var_40], rax
0x1400125c5  xor     eax, eax
0x1400125c7  mov     [rsp+230h+var_20C], r8b
0x1400125cc  mov     r14, rdx
0x1400125cf  mov     qword ptr [rbp+130h+LockHandle.OldIrql], rax
0x1400125d3  mov     rdi, rcx
0x1400125d6  mov     [rsp+230h+var_210], ax
0x1400125db  xorps   xmm0, xmm0
0x1400125de  lea     rcx, [rbp+130h+var_D0]; void *
0x1400125e2  xor     edx, edx; Val
0x1400125e4  mov     r8d, 88h; Size
0x1400125ea  movups  xmmword ptr [rbp+130h+LockHandle.LockQueue.Next], xmm0
0x1400125ee  call    memset
0x1400125f3  lea     rdx, [rbp+130h+LockHandle]; LockHandle
0x1400125f7  mov     rcx, rdi; SpinLock
0x1400125fa  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140012601  nop     dword ptr [rax+rax+00h]
0x140012606  mov     eax, [rdi+8]
0x140012609  test    eax, eax
0x14001260b  jnz     short loc_140012606
0x14001260d  mov     eax, [rdi+18h]
0x140012610  test    al, 1
0x140012612  jz      loc_140012AA9
0x140012618  mov     [rsp+230h+arg_10], rbx
0x140012620  xor     edx, edx
0x140012622  mov     [rsp+230h+var_18], rsi
0x14001262a  xor     eax, eax
0x14001262c  mov     [rsp+230h+var_20], r12
0x140012634  xor     esi, esi
0x140012636  mov     [rsp+230h+var_28], r13
0x14001263e  xor     r12d, r12d
0x140012641  mov     [rsp+230h+var_30], r15
0x140012649  xor     r13d, r13d
0x14001264c  xor     r15d, r15d
0x14001264f  mov     [rsp+230h+var_204], edx
0x140012653  test    r14, r14
0x140012656  jz      loc_140012885
0x14001265c  mov     rdx, [rdi+68h]
0x140012660  movzx   eax, word ptr [r14+2]
0x140012665  mov     [rsp+230h+var_210], ax
0x14001266a  test    rdx, rdx
0x14001266d  jnz     loc_140012C3F
0x140012673  mov     r9, [rdi+50h]
0x140012677  xor     ecx, ecx
0x140012679  xor     ebx, ebx
0x14001267b  mov     [rsp+230h+var_1F0], rcx
0x140012680  mov     [rbp+130h+var_198], rbx
0x140012684  mov     [rsp+230h+var_1D8], rcx
0x140012689  mov     [rsp+230h+var_1E8], r9
0x14001268e  test    r9, r9
0x140012691  jz      loc_140012C9D
0x140012697  movzx   eax, word ptr [r14+2]
0x14001269c  mov     esi, [rdi+18h]
0x14001269f  mov     r10, [rdi+28h]
0x1400126a3  and     esi, 20h
0x1400126a6  mov     r11, [rdi+70h]
0x1400126aa  mov     [rsp+230h+var_208], ax
0x1400126af  movzx   eax, word ptr [rdi+0A8h]
0x1400126b6  mov     [rsp+230h+var_20A], ax
0x1400126bb  mov     rax, [rdi+48h]
0x1400126bf  mov     [rbp+130h+var_1A0], rax
0x1400126c3  movzx   eax, word ptr [rdi+0AEh]
0x1400126ca  mov     [rsp+230h+var_200], r10
0x1400126cf  mov     [rsp+230h+var_1E0], r11
0x1400126d4  test    ax, ax
0x1400126d7  jz      loc_140012AF8
0x1400126dd  test    esi, esi
0x1400126df  jnz     loc_140012AF8
0x1400126e5  movzx   r8d, word ptr [r14]
0x1400126e9  cmp     ax, r8w
0x1400126ed  jnz     loc_140012BC2
0x1400126f3  cmp     ax, 17h
0x1400126f7  jz      loc_140012BB0
0x1400126fd  mov     r15, r11
0x140012700  cmp     r8w, 17h
0x140012705  jz      loc_140012A97
0x14001270b  lea     rax, [r14+4]
0x14001270f  mov     [rsp+230h+var_200], rax
0x140012714  test    r15, r15
0x140012717  jz      loc_140012BD4
0x14001271d  lea     rax, [rdi+0E8h]
0x140012724  test    esi, esi
0x140012726  jnz     loc_140012BCA
0x14001272c  cmp     r11, r15
0x14001272f  jnz     loc_140012BCA
0x140012735  mov     rsi, r9
0x140012738  test    rax, rax
0x14001273b  jz      short loc_140012749
0x14001273d  cmp     r10, r15
0x140012740  jnz     loc_140012B8E
0x140012746  mov     r13, [rax]
0x140012749  cmp     word ptr [r14], 17h
0x14001274e  jz      loc_140012AC0
0x140012754  mov     eax, cs:dword_140229570
0x14001275a  lea     rcx, [rbp+130h+var_170]; void *
0x14001275e  xor     edx, edx; Val
0x140012760  mov     [rsp+230h+var_1F8], eax
0x140012764  mov     r8d, 0A0h; Size
0x14001276a  call    memset
0x14001276f  mov     rax, [rsp+230h+var_200]
0x140012774  xor     ecx, ecx
0x140012776  mov     [rbp+130h+var_160], r13
0x14001277a  mov     [rbp+130h+var_158], ecx
0x14001277d  mov     [rbp+130h+var_150], rcx
0x140012781  mov     [rbp+130h+var_138], ebx
0x140012784  mov     [rbp+130h+var_130], rax
0x140012788  test    rsi, rsi
0x14001278b  jz      loc_140012BA1
0x140012791  mov     [rbp+130h+var_170], rsi
0x140012795  test    r12, r12
0x140012798  jnz     loc_140012AA0
0x14001279e  mov     eax, dword ptr cs:scopeid_unspecified
0x1400127a4  mov     [rbp+130h+var_120], eax
0x1400127a7  mov     [rbp+130h+var_118], rcx
0x1400127ab  movzx   eax, [rsp+230h+var_20A]
0x1400127b0  lea     rdx, IpNlpJoinPath
0x1400127b7  mov     rcx, [r15+28h]
0x1400127bb  mov     [rbp+130h+var_D4], ax
0x1400127bf  movzx   eax, [rsp+230h+var_208]
0x1400127c4  mov     [rbp+130h+var_D2], ax
0x1400127c8  mov     eax, [rsp+230h+var_1F8]
0x1400127cc  mov     [rbp+130h+var_D8], eax
0x1400127cf  mov     rax, [rbp+130h+var_1A0]
0x1400127d3  mov     [rbp+130h+var_F0], rax
0x1400127d7  mov     rax, [r15+30h]
0x1400127db  mov     rax, [rax+40h]
0x1400127df  cmp     rax, rdx
0x1400127e2  lea     rdx, [rbp+130h+var_170]
0x1400127e6  jnz     loc_140012CA7
0x1400127ec  mov     rcx, [rcx]
0x1400127ef  call    IppJoinPath
0x1400127f4  mov     r13, [rbp+130h+var_F8]
0x1400127f8  mov     esi, eax
0x1400127fa  test    eax, eax
0x1400127fc  js      loc_140012AE0
0x140012802  mov     rbx, [rbp+130h+var_198]
0x140012806  test    esi, esi
0x140012808  js      loc_140012A1C
0x14001280e  xor     ecx, ecx
0x140012810  mov     [rsp+230h+var_1D0], r13
0x140012815  mov     [rsp+230h+var_1B8], rcx
0x14001281a  lea     rax, [rbp+130h+var_D0]
0x14001281e  mov     [rsp+230h+var_1C8], rcx
0x140012823  lea     rcx, IpNlpQueryPathInformation
0x14001282a  mov     [rsp+230h+var_1C0], rax
0x14001282f  mov     rax, [r15+30h]
0x140012833  mov     rax, [rax+50h]
0x140012837  cmp     rax, rcx
0x14001283a  lea     rcx, [rsp+230h+var_1D0]
0x14001283f  jnz     loc_140012C93
0x140012845  call    IpNlpQueryPathInformation
0x14001284a  mov     ecx, [rsp+230h+var_204]
0x14001284e  test    eax, eax
0x140012850  mov     rax, cs:UdpRssHash
0x140012857  cmovns  ecx, dword ptr [rsp+230h+var_1B8]
0x14001285c  movzx   r8d, [rsp+230h+var_210]
0x140012862  movzx   edx, word ptr [rdi+0A8h]
0x140012869  mov     rax, [rax+8]
0x14001286d  mov     ebx, [r13+0Ch]
0x140012871  mov     [rsp+230h+var_204], ecx
0x140012875  movzx   ecx, word ptr [r15+18h]
0x14001287a  call    _guard_dispatch_icall
0x14001287f  mov     edx, [rsp+230h+var_204]
0x140012883  xor     eax, ebx
0x140012885  mov     rcx, [rdi+138h]
0x14001288c  mov     rbx, [rdi+128h]
0x140012893  mov     [rsp+230h+var_1F0], rcx
0x140012898  mov     rcx, [rdi+130h]
0x14001289f  mov     [rdi+11Ch], eax
0x1400128a5  movzx   eax, [rsp+230h+var_210]
0x1400128aa  mov     [rsp+230h+var_1D8], rcx
0x1400128af  mov     [rdi+128h], r13
0x1400128b6  mov     [rdi+138h], r15
0x1400128bd  mov     [rdi+118h], ax
0x1400128c4  test    r14, r14
0x1400128c7  jz      loc_140012BDE
0x1400128cd  mov     rax, [rbp+130h+var_60]
0x1400128d4  mov     [rdi+130h], rax
0x1400128db  mov     eax, [rbp+130h+var_54]
0x1400128e1  mov     [rdi+120h], eax
0x1400128e7  movzx   eax, [rbp+130h+var_58]
0x1400128ee  neg     al
0x1400128f0  mov     eax, [rdi+18h]
0x1400128f3  sbb     ecx, ecx
0x1400128f5  btr     eax, 15h
0x1400128f9  and     ecx, 200000h
0x1400128ff  or      eax, ecx
0x140012901  mov     [rdi+18h], eax
0x140012904  test    edx, edx
0x140012906  jnz     loc_140012AD6
0x14001290c  cmp     word ptr [r15+18h], 17h
0x140012912  jz      loc_140012AC9
0x140012918  xor     ecx, ecx
0x14001291a  btr     eax, 16h
0x14001291e  or      eax, ecx
0x140012920  mov     rcx, rdi
0x140012923  mov     [rdi+18h], eax
0x140012926  call    UdpCacheDefaultUsoInformation
0x14001292b  mov     rax, [r15+28h]
0x14001292f  xor     edx, edx
0x140012931  mov     [rsp+230h+var_1D0], rax
0x140012936  mov     rax, [r13+0]
0x14001293a  mov     [rbp+130h+var_1A8], rdx
0x14001293e  mov     [rbp+130h+var_1B0], 11h
0x140012946  mov     [rsp+230h+var_1C8], rdx
0x14001294b  mov     rcx, [rax+10h]
0x14001294f  mov     rax, [rcx]
0x140012952  lea     rcx, IpNlpChecksumDatagram
0x140012959  mov     [rsp+230h+var_1C0], rax
0x14001295e  mov     rax, [r13+10h]
0x140012962  mov     [rsp+230h+var_1B8], rax
0x140012967  mov     rax, [r15+30h]
0x14001296b  mov     rax, [rax+8]
0x14001296f  cmp     rax, rcx
0x140012972  lea     rcx, [rsp+230h+var_1D0]
0x140012977  jnz     loc_140012C78
0x14001297d  call    IpNlpChecksumDatagram
0x140012982  mov     ecx, [rdi+144h]
0x140012988  mov     [rdi+11Ah], ax
0x14001298f  mov     rax, [rdi+138h]
0x140012996  mov     rdx, [r13+0]
0x14001299a  movzx   r8d, word ptr [rax+48h]
0x14001299f  mov     rdx, [rdx+10h]
0x1400129a3  call    cs:__imp_RtlCompute37Hash
0x1400129aa  nop     dword ptr [rax+rax+00h]
0x1400129af  mov     rcx, [rdi+138h]
0x1400129b6  lea     rdx, [r13+10h]
0x1400129ba  mov     [rdi+140h], eax
0x1400129c0  movzx   r8d, word ptr [rcx+48h]
0x1400129c5  mov     ecx, eax
0x1400129c7  call    cs:__imp_RtlCompute37Hash
0x1400129ce  nop     dword ptr [rax+rax+00h]
0x1400129d3  mov     r8d, 2
0x1400129d9  lea     rdx, [rsp+230h+var_210]
0x1400129de  mov     ecx, eax
0x1400129e0  mov     [rdi+140h], eax
0x1400129e6  call    cs:__imp_RtlCompute37Hash
0x1400129ed  nop     dword ptr [rax+rax+00h]
0x1400129f2  mov     [rdi+140h], eax
0x1400129f8  test    r12, r12
0x1400129fb  jnz     loc_140012BF9
0x140012a01  test    r14, r14
0x140012a04  jz      loc_140012B52
0x140012a0a  cmp     [rsp+230h+var_20C], 0
0x140012a0f  jz      loc_140012B52
0x140012a15  or      dword ptr [rdi+18h], 800h
0x140012a1c  lea     rcx, [rbp+130h+LockHandle]; LockHandle
0x140012a20  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140012a27  nop     dword ptr [rax+rax+00h]
0x140012a2c  mov     rdx, [rsp+230h+var_1D8]
0x140012a31  mov     r14, [rsp+230h+var_1F0]
0x140012a36  test    rdx, rdx
0x140012a39  jnz     loc_140012C1A
0x140012a3f  test    rbx, rbx
0x140012a42  jnz     loc_140012C27
0x140012a48  test    r12, r12
0x140012a4b  jnz     loc_140012C82
0x140012a51  mov     eax, esi
0x140012a53  mov     r13, [rsp+230h+var_28]
0x140012a5b  mov     r12, [rsp+230h+var_20]
0x140012a63  mov     rsi, [rsp+230h+var_18]
0x140012a6b  mov     rbx, [rsp+230h+arg_10]
0x140012a73  mov     r15, [rsp+230h+var_30]
0x140012a7b  mov     rcx, [rbp+130h+var_40]
0x140012a82  xor     rcx, rsp; StackCookie
0x140012a85  call    __security_check_cookie
0x140012a8a  add     rsp, 220h
0x140012a91  pop     r14
0x140012a93  pop     rdi
0x140012a94  pop     rbp
0x140012a95  retn
0x140012a97  lea     rax, [r14+8]
0x140012a9b  jmp     loc_14001270F
0x140012aa0  mov     [rbp+130h+var_128], r12
0x140012aa4  jmp     loc_1400127AB
0x140012aa9  lea     rcx, [rbp+130h+LockHandle]; LockHandle
0x140012aad  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140012ab4  nop     dword ptr [rax+rax+00h]
0x140012ab9  mov     eax, 0C0000239h
0x140012abe  jmp     short loc_140012A7B
0x140012ac0  mov     ebx, [r14+18h]
0x140012ac4  jmp     loc_140012754
0x140012ac9  cmp     [rbp+130h+var_57], 0
0x140012ad0  jz      loc_140012918
0x140012ad6  mov     ecx, 400000h
0x140012adb  jmp     loc_14001291A
0x140012ae0  cmp     r15, [rsp+230h+var_1E0]
0x140012ae5  jz      loc_140012802
0x140012aeb  mov     rcx, r15
0x140012aee  call    _InetDereferenceAf
0x140012af3  jmp     loc_140012802
0x140012af8  movzx   edx, word ptr [r14]
0x140012afc  cmp     dx, 17h
  ... truncated ...
```
