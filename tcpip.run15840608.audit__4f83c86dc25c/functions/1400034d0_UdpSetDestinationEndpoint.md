# UdpSetDestinationEndpoint

- ea: `0x1400034d0`
- end: `0x140003be1`
- name: `UdpSetDestinationEndpoint`
- size: `1809`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `4`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002c80`
- `0x140002db4`
- `0x140021710`
- `0x1400d4b80`

## callees

- `0x1400034d0`
- `0x140003be8`
- `0x140003cc0`
- `0x140004070`
- `0x140005480`
- `0x140023800`
- `0x140023df0`
- `0x140049760`
- `0x140055b30`
- `0x140057040`
- `0x140072c40`
- `0x140074f30`
- `0x1400ec7a0`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000352a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000352a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003950`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400039dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003b92`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003950`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400039dd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003b92`
- `NETIO!RtlCompute37Hash` at `0x1400038d3`
- `NETIO!RtlCompute37Hash` at `0x1400038f7`
- `NETIO!RtlCompute37Hash` at `0x140003916`
- `NETIO!RtlCompute37Hash` at `0x1400038d3`
- `NETIO!RtlCompute37Hash` at `0x1400038f7`
- `NETIO!RtlCompute37Hash` at `0x140003916`

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
  v54 = dword_14022D590;
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
0x1400034d0  push    rbp
0x1400034d2  push    rdi
0x1400034d3  push    r14
0x1400034d5  lea     rbp, [rsp-120h]
0x1400034dd  sub     rsp, 220h
0x1400034e4  mov     rax, cs:__security_cookie
0x1400034eb  xor     rax, rsp
0x1400034ee  mov     [rbp+130h+var_40], rax
0x1400034f5  xor     eax, eax
0x1400034f7  mov     [rsp+230h+var_20C], r8b
0x1400034fc  mov     r14, rdx
0x1400034ff  mov     qword ptr [rbp+130h+LockHandle.OldIrql], rax
0x140003503  mov     rdi, rcx
0x140003506  mov     [rsp+230h+var_210], ax
0x14000350b  xorps   xmm0, xmm0
0x14000350e  lea     rcx, [rbp+130h+var_D0]; void *
0x140003512  xor     edx, edx; Val
0x140003514  mov     r8d, 88h; Size
0x14000351a  movups  xmmword ptr [rbp+130h+LockHandle.LockQueue.Next], xmm0
0x14000351e  call    memset
0x140003523  lea     rdx, [rbp+130h+LockHandle]; LockHandle
0x140003527  mov     rcx, rdi; SpinLock
0x14000352a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003531  nop     dword ptr [rax+rax+00h]
0x140003536  mov     eax, [rdi+8]
0x140003539  test    eax, eax
0x14000353b  jnz     short loc_140003536
0x14000353d  mov     eax, [rdi+18h]
0x140003540  test    al, 1
0x140003542  jz      loc_1400039D9
0x140003548  mov     [rsp+230h+arg_10], rbx
0x140003550  xor     edx, edx
0x140003552  mov     [rsp+230h+var_18], rsi
0x14000355a  xor     eax, eax
0x14000355c  mov     [rsp+230h+var_20], r12
0x140003564  xor     esi, esi
0x140003566  mov     [rsp+230h+var_28], r13
0x14000356e  xor     r12d, r12d
0x140003571  mov     [rsp+230h+var_30], r15
0x140003579  xor     r13d, r13d
0x14000357c  xor     r15d, r15d
0x14000357f  mov     [rsp+230h+var_204], edx
0x140003583  test    r14, r14
0x140003586  jz      loc_1400037B5
0x14000358c  mov     rdx, [rdi+68h]
0x140003590  movzx   eax, word ptr [r14+2]
0x140003595  mov     [rsp+230h+var_210], ax
0x14000359a  test    rdx, rdx
0x14000359d  jnz     loc_140003B6F
0x1400035a3  mov     r9, [rdi+50h]
0x1400035a7  xor     ecx, ecx
0x1400035a9  xor     ebx, ebx
0x1400035ab  mov     [rsp+230h+var_1F0], rcx
0x1400035b0  mov     [rbp+130h+var_198], rbx
0x1400035b4  mov     [rsp+230h+var_1D8], rcx
0x1400035b9  mov     [rsp+230h+var_1E8], r9
0x1400035be  test    r9, r9
0x1400035c1  jz      loc_140003BCD
0x1400035c7  movzx   eax, word ptr [r14+2]
0x1400035cc  mov     esi, [rdi+18h]
0x1400035cf  mov     r10, [rdi+28h]
0x1400035d3  and     esi, 20h
0x1400035d6  mov     r11, [rdi+70h]
0x1400035da  mov     [rsp+230h+var_208], ax
0x1400035df  movzx   eax, word ptr [rdi+0A8h]
0x1400035e6  mov     [rsp+230h+var_20A], ax
0x1400035eb  mov     rax, [rdi+48h]
0x1400035ef  mov     [rbp+130h+var_1A0], rax
0x1400035f3  movzx   eax, word ptr [rdi+0AEh]
0x1400035fa  mov     [rsp+230h+var_200], r10
0x1400035ff  mov     [rsp+230h+var_1E0], r11
0x140003604  test    ax, ax
0x140003607  jz      loc_140003A28
0x14000360d  test    esi, esi
0x14000360f  jnz     loc_140003A28
0x140003615  movzx   r8d, word ptr [r14]
0x140003619  cmp     ax, r8w
0x14000361d  jnz     loc_140003AF2
0x140003623  cmp     ax, 17h
0x140003627  jz      loc_140003AE0
0x14000362d  mov     r15, r11
0x140003630  cmp     r8w, 17h
0x140003635  jz      loc_1400039C7
0x14000363b  lea     rax, [r14+4]
0x14000363f  mov     [rsp+230h+var_200], rax
0x140003644  test    r15, r15
0x140003647  jz      loc_140003B04
0x14000364d  lea     rax, [rdi+0E8h]
0x140003654  test    esi, esi
0x140003656  jnz     loc_140003AFA
0x14000365c  cmp     r11, r15
0x14000365f  jnz     loc_140003AFA
0x140003665  mov     rsi, r9
0x140003668  test    rax, rax
0x14000366b  jz      short loc_140003679
0x14000366d  cmp     r10, r15
0x140003670  jnz     loc_140003ABE
0x140003676  mov     r13, [rax]
0x140003679  cmp     word ptr [r14], 17h
0x14000367e  jz      loc_1400039F0
0x140003684  mov     eax, cs:dword_14022D590
0x14000368a  lea     rcx, [rbp+130h+var_170]; void *
0x14000368e  xor     edx, edx; Val
0x140003690  mov     [rsp+230h+var_1F8], eax
0x140003694  mov     r8d, 0A0h; Size
0x14000369a  call    memset
0x14000369f  mov     rax, [rsp+230h+var_200]
0x1400036a4  xor     ecx, ecx
0x1400036a6  mov     [rbp+130h+var_160], r13
0x1400036aa  mov     [rbp+130h+var_158], ecx
0x1400036ad  mov     [rbp+130h+var_150], rcx
0x1400036b1  mov     [rbp+130h+var_138], ebx
0x1400036b4  mov     [rbp+130h+var_130], rax
0x1400036b8  test    rsi, rsi
0x1400036bb  jz      loc_140003AD1
0x1400036c1  mov     [rbp+130h+var_170], rsi
0x1400036c5  test    r12, r12
0x1400036c8  jnz     loc_1400039D0
0x1400036ce  mov     eax, dword ptr cs:scopeid_unspecified
0x1400036d4  mov     [rbp+130h+var_120], eax
0x1400036d7  mov     [rbp+130h+var_118], rcx
0x1400036db  movzx   eax, [rsp+230h+var_20A]
0x1400036e0  lea     rdx, IpNlpJoinPath
0x1400036e7  mov     rcx, [r15+28h]
0x1400036eb  mov     [rbp+130h+var_D4], ax
0x1400036ef  movzx   eax, [rsp+230h+var_208]
0x1400036f4  mov     [rbp+130h+var_D2], ax
0x1400036f8  mov     eax, [rsp+230h+var_1F8]
0x1400036fc  mov     [rbp+130h+var_D8], eax
0x1400036ff  mov     rax, [rbp+130h+var_1A0]
0x140003703  mov     [rbp+130h+var_F0], rax
0x140003707  mov     rax, [r15+30h]
0x14000370b  mov     rax, [rax+40h]
0x14000370f  cmp     rax, rdx
0x140003712  lea     rdx, [rbp+130h+var_170]
0x140003716  jnz     loc_140003BD7
0x14000371c  mov     rcx, [rcx]
0x14000371f  call    IppJoinPath
0x140003724  mov     r13, [rbp+130h+var_F8]
0x140003728  mov     esi, eax
0x14000372a  test    eax, eax
0x14000372c  js      loc_140003A10
0x140003732  mov     rbx, [rbp+130h+var_198]
0x140003736  test    esi, esi
0x140003738  js      loc_14000394C
0x14000373e  xor     ecx, ecx
0x140003740  mov     [rsp+230h+var_1D0], r13
0x140003745  mov     [rsp+230h+var_1B8], rcx
0x14000374a  lea     rax, [rbp+130h+var_D0]
0x14000374e  mov     [rsp+230h+var_1C8], rcx
0x140003753  lea     rcx, IpNlpQueryPathInformation
0x14000375a  mov     [rsp+230h+var_1C0], rax
0x14000375f  mov     rax, [r15+30h]
0x140003763  mov     rax, [rax+50h]
0x140003767  cmp     rax, rcx
0x14000376a  lea     rcx, [rsp+230h+var_1D0]
0x14000376f  jnz     loc_140003BC3
0x140003775  call    IpNlpQueryPathInformation
0x14000377a  mov     ecx, [rsp+230h+var_204]
0x14000377e  test    eax, eax
0x140003780  mov     rax, cs:UdpRssHash
0x140003787  cmovns  ecx, dword ptr [rsp+230h+var_1B8]
0x14000378c  movzx   r8d, [rsp+230h+var_210]
0x140003792  movzx   edx, word ptr [rdi+0A8h]
0x140003799  mov     rax, [rax+8]
0x14000379d  mov     ebx, [r13+0Ch]
0x1400037a1  mov     [rsp+230h+var_204], ecx
0x1400037a5  movzx   ecx, word ptr [r15+18h]
0x1400037aa  call    _guard_dispatch_icall
0x1400037af  mov     edx, [rsp+230h+var_204]
0x1400037b3  xor     eax, ebx
0x1400037b5  mov     rcx, [rdi+138h]
0x1400037bc  mov     rbx, [rdi+128h]
0x1400037c3  mov     [rsp+230h+var_1F0], rcx
0x1400037c8  mov     rcx, [rdi+130h]
0x1400037cf  mov     [rdi+11Ch], eax
0x1400037d5  movzx   eax, [rsp+230h+var_210]
0x1400037da  mov     [rsp+230h+var_1D8], rcx
0x1400037df  mov     [rdi+128h], r13
0x1400037e6  mov     [rdi+138h], r15
0x1400037ed  mov     [rdi+118h], ax
0x1400037f4  test    r14, r14
0x1400037f7  jz      loc_140003B0E
0x1400037fd  mov     rax, [rbp+130h+var_60]
0x140003804  mov     [rdi+130h], rax
0x14000380b  mov     eax, [rbp+130h+var_54]
0x140003811  mov     [rdi+120h], eax
0x140003817  movzx   eax, [rbp+130h+var_58]
0x14000381e  neg     al
0x140003820  mov     eax, [rdi+18h]
0x140003823  sbb     ecx, ecx
0x140003825  btr     eax, 15h
0x140003829  and     ecx, 200000h
0x14000382f  or      eax, ecx
0x140003831  mov     [rdi+18h], eax
0x140003834  test    edx, edx
0x140003836  jnz     loc_140003A06
0x14000383c  cmp     word ptr [r15+18h], 17h
0x140003842  jz      loc_1400039F9
0x140003848  xor     ecx, ecx
0x14000384a  btr     eax, 16h
0x14000384e  or      eax, ecx
0x140003850  mov     rcx, rdi
0x140003853  mov     [rdi+18h], eax
0x140003856  call    UdpCacheDefaultUsoInformation
0x14000385b  mov     rax, [r15+28h]
0x14000385f  xor     edx, edx
0x140003861  mov     [rsp+230h+var_1D0], rax
0x140003866  mov     rax, [r13+0]
0x14000386a  mov     [rbp+130h+var_1A8], rdx
0x14000386e  mov     [rbp+130h+var_1B0], 11h
0x140003876  mov     [rsp+230h+var_1C8], rdx
0x14000387b  mov     rcx, [rax+10h]
0x14000387f  mov     rax, [rcx]
0x140003882  lea     rcx, IpNlpChecksumDatagram
0x140003889  mov     [rsp+230h+var_1C0], rax
0x14000388e  mov     rax, [r13+10h]
0x140003892  mov     [rsp+230h+var_1B8], rax
0x140003897  mov     rax, [r15+30h]
0x14000389b  mov     rax, [rax+8]
0x14000389f  cmp     rax, rcx
0x1400038a2  lea     rcx, [rsp+230h+var_1D0]
0x1400038a7  jnz     loc_140003BA8
0x1400038ad  call    IpNlpChecksumDatagram
0x1400038b2  mov     ecx, [rdi+144h]
0x1400038b8  mov     [rdi+11Ah], ax
0x1400038bf  mov     rax, [rdi+138h]
0x1400038c6  mov     rdx, [r13+0]
0x1400038ca  movzx   r8d, word ptr [rax+48h]
0x1400038cf  mov     rdx, [rdx+10h]
0x1400038d3  call    cs:__imp_RtlCompute37Hash
0x1400038da  nop     dword ptr [rax+rax+00h]
0x1400038df  mov     rcx, [rdi+138h]
0x1400038e6  lea     rdx, [r13+10h]
0x1400038ea  mov     [rdi+140h], eax
0x1400038f0  movzx   r8d, word ptr [rcx+48h]
0x1400038f5  mov     ecx, eax
0x1400038f7  call    cs:__imp_RtlCompute37Hash
0x1400038fe  nop     dword ptr [rax+rax+00h]
0x140003903  mov     r8d, 2
0x140003909  lea     rdx, [rsp+230h+var_210]
0x14000390e  mov     ecx, eax
0x140003910  mov     [rdi+140h], eax
0x140003916  call    cs:__imp_RtlCompute37Hash
0x14000391d  nop     dword ptr [rax+rax+00h]
0x140003922  mov     [rdi+140h], eax
0x140003928  test    r12, r12
0x14000392b  jnz     loc_140003B29
0x140003931  test    r14, r14
0x140003934  jz      loc_140003A82
0x14000393a  cmp     [rsp+230h+var_20C], 0
0x14000393f  jz      loc_140003A82
0x140003945  or      dword ptr [rdi+18h], 800h
0x14000394c  lea     rcx, [rbp+130h+LockHandle]; LockHandle
0x140003950  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003957  nop     dword ptr [rax+rax+00h]
0x14000395c  mov     rdx, [rsp+230h+var_1D8]
0x140003961  mov     r14, [rsp+230h+var_1F0]
0x140003966  test    rdx, rdx
0x140003969  jnz     loc_140003B4A
0x14000396f  test    rbx, rbx
0x140003972  jnz     loc_140003B57
0x140003978  test    r12, r12
0x14000397b  jnz     loc_140003BB2
0x140003981  mov     eax, esi
0x140003983  mov     r13, [rsp+230h+var_28]
0x14000398b  mov     r12, [rsp+230h+var_20]
0x140003993  mov     rsi, [rsp+230h+var_18]
0x14000399b  mov     rbx, [rsp+230h+arg_10]
0x1400039a3  mov     r15, [rsp+230h+var_30]
0x1400039ab  mov     rcx, [rbp+130h+var_40]
0x1400039b2  xor     rcx, rsp; StackCookie
0x1400039b5  call    __security_check_cookie
0x1400039ba  add     rsp, 220h
0x1400039c1  pop     r14
0x1400039c3  pop     rdi
0x1400039c4  pop     rbp
0x1400039c5  retn
0x1400039c7  lea     rax, [r14+8]
0x1400039cb  jmp     loc_14000363F
0x1400039d0  mov     [rbp+130h+var_128], r12
0x1400039d4  jmp     loc_1400036DB
0x1400039d9  lea     rcx, [rbp+130h+LockHandle]; LockHandle
0x1400039dd  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400039e4  nop     dword ptr [rax+rax+00h]
0x1400039e9  mov     eax, 0C0000239h
0x1400039ee  jmp     short loc_1400039AB
0x1400039f0  mov     ebx, [r14+18h]
0x1400039f4  jmp     loc_140003684
0x1400039f9  cmp     [rbp+130h+var_57], 0
0x140003a00  jz      loc_140003848
0x140003a06  mov     ecx, 400000h
0x140003a0b  jmp     loc_14000384A
0x140003a10  cmp     r15, [rsp+230h+var_1E0]
0x140003a15  jz      loc_140003732
0x140003a1b  mov     rcx, r15
0x140003a1e  call    _InetDereferenceAf
0x140003a23  jmp     loc_140003732
0x140003a28  movzx   edx, word ptr [r14]
0x140003a2c  cmp     dx, 17h
  ... truncated ...
```
