# TdxCloseConnectionEndpointTlRequestComplete

- ea: `0x1400043b0`
- end: `0x1400047c6`
- name: `TdxCloseConnectionEndpointTlRequestComplete`
- size: `1046`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400075b0`
- `0x14000f4f0`

## callees

- `0x140002850`
- `0x140003590`
- `0x1400043b0`
- `0x1400047d0`
- `0x1400054ec`
- `0x140013bf8`
- `0x140018590`
- `0x140018900`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000479e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000479e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000478a`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000478a`
- `ntoskrnl!IofCompleteRequest` at `0x14000466d`
- `ntoskrnl!IofCompleteRequest` at `0x14000466d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400047ae`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400047ae`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004776`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140004776`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400043f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004590`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400043f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004590`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004568`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400045b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004568`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400045b1`

## string_xrefs

- `0x1400043dd`: `TdxCloseConnectionEndpointTlRequestComplete`
- `0x1400045c6`: `TdxCloseConnectionEndpointTlRequestComplete`
- `0x140004701`: `TdxCloseConnectionEndpointTlRequestComplete`
- `0x14000472f`: `TdxCloseConnectionEndpointTlRequestComplete`

## pseudocode

```c
__int64 __fastcall TdxCloseConnectionEndpointTlRequestComplete(unsigned int *a1, NTSTATUS a2)
{
  KIRQL v3; // al
  KSPIN_LOCK *v4; // rbp
  KIRQL v5; // r13
  unsigned int v6; // r15d
  __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  volatile __int64 *v10; // rbx
  char v11; // si
  int v12; // edi
  char v13; // r15
  unsigned int v14; // eax
  __int64 v15; // rax
  KIRQL v16; // al
  KSPIN_LOCK v17; // rsi
  void (__fastcall *v18)(KSPIN_LOCK, __int64, _QWORD, _QWORD, _DWORD, _QWORD, unsigned int); // rdi
  NTSTATUS v19; // ebx
  __int64 v20; // rcx
  __int64 result; // rax
  __int64 v22; // rax
  IRP *v23; // rcx
  __int64 v24; // [rsp+40h] [rbp-68h]
  _OWORD v25[2]; // [rsp+48h] [rbp-60h] BYREF
  KIRQL Irql; // [rsp+B0h] [rbp+8h] BYREF
  NTSTATUS v27; // [rsp+B8h] [rbp+10h]
  unsigned int v28; // [rsp+C0h] [rbp+18h]
  unsigned int v29; // [rsp+C8h] [rbp+20h]

  v27 = a2;
  v25[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_qs(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      (unsigned int)WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids,
      (_DWORD)a1,
      (__int64)"TdxCloseConnectionEndpointTlRequestComplete");
  }
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 1);
  v4 = (KSPIN_LOCK *)*((_QWORD *)a1 + 11);
  v5 = v3;
  v6 = *a1;
  v24 = *((_QWORD *)a1 + 10);
  if ( v4 )
    DbgTdxReferenceTransportAddress(v4, "minio\\netio\\session\\tdi\\connection.c", 2848);
  v7 = *((_QWORD *)a1 + 12);
  v29 = a1[17];
  v8 = a1 + 24;
  if ( (unsigned int *)v7 == a1 + 24 )
  {
    v10 = (volatile __int64 *)v25;
    *(_QWORD *)&v25[0] = v25;
    v9 = v25;
  }
  else
  {
    if ( *(_QWORD **)(v7 + 8) != v8
      || (*(_QWORD *)&v25[0] = v7,
          *((_QWORD *)&v25[0] + 1) = a1 + 24,
          *(_QWORD *)(v7 + 8) = v25,
          *v8 = v25,
          *((_QWORD **)&v25[0] + 1) != v8)
      || (v9 = (_QWORD *)*((_QWORD *)a1 + 13), (_QWORD *)*v9 != v8) )
    {
LABEL_36:
      __fastfail(3u);
    }
    *v9 = v25;
    v10 = *(volatile __int64 **)&v25[0];
  }
  *((_QWORD *)a1 + 13) = a1 + 24;
  *v8 = v8;
  *((_QWORD *)&v25[0] + 1) = v9;
  v11 = 0;
  v12 = *a1 & 0x1000;
  v28 = v6 >> 4;
  v13 = BYTE1(v6) & 1;
  *a1 = 0;
  a1[17] = 0;
  *((_QWORD *)a1 + 14) = 0;
  memset(a1 + 30, 0, 0x80u);
  *(_OWORD *)(a1 + 62) = 0;
  v14 = *a1;
  a1[19] = 0;
  *((_QWORD *)a1 + 33) = 0;
  *((_QWORD *)a1 + 36) = 0;
  *a1 = v14 & 0xFFFFEFFF | (v12 != 0 ? 0x1000 : 0);
  while ( v10 != (volatile __int64 *)v25 )
  {
    v15 = _InterlockedExchange64(v10 - 8, 0);
    v10 = (volatile __int64 *)*v10;
    if ( !v15 )
      v11 = 1;
  }
  if ( v13 )
    DbgTdxReferenceConnection(a1, "TdxCloseConnectionEndpointTlRequestComplete", 2887);
  if ( v11 )
  {
    Irql = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)a1 + 1);
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)a1 + 1);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)a1 + 1, v5);
  if ( v13 )
  {
    if ( v4 )
    {
      if ( (v28 & 1) == 0 )
      {
        v16 = KeAcquireSpinLockRaiseToDpc(v4 + 1);
        v17 = v4[52];
        v18 = (void (__fastcall *)(KSPIN_LOCK, __int64, _QWORD, _QWORD, _DWORD, _QWORD, unsigned int))v4[51];
        KeReleaseSpinLock(v4 + 1, v16);
        if ( v18 )
        {
          v18(v17, v24, 0, 0, 0, 0, v29);
          *a1 &= ~0x100u;
        }
      }
    }
    DbgTdxDereferenceConnection(a1, "TdxCloseConnectionEndpointTlRequestComplete", 2937);
  }
  v19 = v27;
  while ( 1 )
  {
    v20 = *(_QWORD *)&v25[0];
    if ( *(_OWORD **)&v25[0] == v25 )
      break;
    if ( *(_OWORD **)(*(_QWORD *)&v25[0] + 8LL) != v25 )
      goto LABEL_36;
    v22 = **(_QWORD **)&v25[0];
    if ( *(_QWORD *)(**(_QWORD **)&v25[0] + 8LL) != *(_QWORD *)&v25[0] )
      goto LABEL_36;
    *(_QWORD *)&v25[0] = **(_QWORD **)&v25[0];
    *(_QWORD *)(v22 + 8) = v25;
    v23 = (IRP *)(v20 - 168);
    v23->IoStatus.Status = v19;
    v23->IoStatus.Information = 0;
    IofCompleteRequest(v23, 0);
    DbgTdxDereferenceConnection(a1, "TdxCloseConnectionEndpointTlRequestComplete", 2952);
  }
  result = DbgTdxDereferenceConnection(a1, "TdxCloseConnectionEndpointTlRequestComplete", 2958);
  if ( v4 )
    return DbgTdxDereferenceTransportAddress(v4, "minio\\netio\\session\\tdi\\connection.c", 2960);
  return result;
}

```

## disassembly

```asm
0x1400043b0  mov     [rsp+arg_8], edx
0x1400043b4  push    rbp
0x1400043b5  push    r12
0x1400043b7  push    r13
0x1400043b9  push    r14
0x1400043bb  push    r15
0x1400043bd  sub     rsp, 80h
0x1400043c4  xorps   xmm0, xmm0
0x1400043c7  mov     r14, rcx
0x1400043ca  movups  [rsp+0A8h+var_60], xmm0
0x1400043cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043d6  lea     rax, WPP_GLOBAL_Control
0x1400043dd  lea     r8, aTdxcloseconnec; "TdxCloseConnectionEndpointTlRequestComp"...
0x1400043e4  cmp     rcx, rax
0x1400043e7  jz      short loc_1400043F3
0x1400043e9  cmp     byte ptr [rcx+29h], 5
0x1400043ed  jnb     loc_14000473B
0x1400043f3  lea     rcx, [r14+8]; SpinLock
0x1400043f7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400043fe  nop     dword ptr [rax+rax+00h]
0x140004403  mov     rbp, [r14+58h]
0x140004407  movzx   r13d, al
0x14000440b  mov     rax, [r14+50h]
0x14000440f  mov     r15d, [r14]
0x140004412  mov     [rsp+0A8h+var_68], rax
0x140004417  test    rbp, rbp
0x14000441a  jnz     loc_14000468F
0x140004420  mov     eax, [r14+44h]
0x140004424  mov     rcx, [r14+60h]
0x140004428  mov     [rsp+0A8h+arg_18], eax
0x14000442f  lea     rax, [r14+60h]
0x140004433  mov     [rsp+0A8h+var_30], rbx
0x140004438  mov     [rsp+0A8h+var_38], rsi
0x14000443d  cmp     rcx, rax
0x140004440  jz      loc_1400046A9
0x140004446  cmp     [rcx+8], rax
0x14000444a  jnz     loc_1400047BF
0x140004450  mov     qword ptr [rsp+0A8h+var_60], rcx
0x140004455  lea     rdx, [rsp+0A8h+var_60]
0x14000445a  mov     qword ptr [rsp+0A8h+var_60+8], rax
0x14000445f  mov     [rcx+8], rdx
0x140004463  lea     rcx, [rsp+0A8h+var_60]
0x140004468  mov     [rax], rcx
0x14000446b  cmp     qword ptr [rsp+0A8h+var_60+8], rax
0x140004470  jnz     loc_1400047BF
0x140004476  mov     rcx, [rax+8]
0x14000447a  cmp     [rcx], rax
0x14000447d  jnz     loc_1400047BF
0x140004483  lea     rdx, [rsp+0A8h+var_60]
0x140004488  mov     [rcx], rdx
0x14000448b  mov     rbx, qword ptr [rsp+0A8h+var_60]
0x140004490  mov     [rax+8], rax
0x140004494  xor     edx, edx; Val
0x140004496  mov     [rax], rax
0x140004499  mov     r8d, 80h; Size
0x14000449f  mov     qword ptr [rsp+0A8h+var_60+8], rcx
0x1400044a4  xor     eax, eax
0x1400044a6  mov     ecx, r15d
0x1400044a9  mov     [rsp+0A8h+var_40], rdi
0x1400044ae  mov     edi, [r14]
0x1400044b1  xor     sil, sil
0x1400044b4  shr     ecx, 4
0x1400044b7  and     edi, 1000h
0x1400044bd  mov     [rsp+0A8h+arg_10], ecx
0x1400044c4  lea     rcx, [r14+78h]; void *
0x1400044c8  shr     r15d, 8
0x1400044cc  and     r15b, 1
0x1400044d0  mov     [r14], eax
0x1400044d3  mov     [r14+44h], eax
0x1400044d7  mov     [r14+70h], rax
0x1400044db  call    memset
0x1400044e0  xor     edx, edx
0x1400044e2  xorps   xmm0, xmm0
0x1400044e5  movups  xmmword ptr [r14+0F8h], xmm0
0x1400044ed  mov     eax, [r14]
0x1400044f0  neg     edi
0x1400044f2  mov     [r14+4Ch], edx
0x1400044f6  sbb     ecx, ecx
0x1400044f8  mov     [r14+108h], rdx
0x1400044ff  btr     eax, 0Ch
0x140004503  mov     [r14+120h], rdx
0x14000450a  and     ecx, 1000h
0x140004510  or      ecx, eax
0x140004512  lea     rax, [rsp+0A8h+var_60]
0x140004517  mov     [r14], ecx
0x14000451a  cmp     rbx, rax
0x14000451d  jz      short loc_14000454E
0x14000451f  mov     ecx, 1
0x140004524  nop     dword ptr [rax+00h]
0x140004528  nop     dword ptr [rax+rax+00000000h]
0x140004530  mov     rax, rdx
0x140004533  movzx   esi, sil
0x140004537  xchg    rax, [rbx-40h]
0x14000453b  mov     rbx, [rbx]
0x14000453e  test    rax, rax
0x140004541  lea     rax, [rsp+0A8h+var_60]
0x140004546  cmovz   esi, ecx
0x140004549  cmp     rbx, rax
0x14000454c  jnz     short loc_140004530
0x14000454e  test    r15b, r15b
0x140004551  jnz     loc_1400046FB
0x140004557  test    sil, sil
0x14000455a  jnz     loc_14000476A
0x140004560  movzx   edx, r13b; NewIrql
0x140004564  lea     rcx, [r14+8]; SpinLock
0x140004568  call    cs:__imp_KeReleaseSpinLock
0x14000456f  nop     dword ptr [rax+rax+00h]
0x140004574  test    r15b, r15b
0x140004577  jz      loc_14000472F
0x14000457d  test    rbp, rbp
0x140004580  jz      short loc_1400045C6
0x140004582  test    byte ptr [rsp+0A8h+arg_10], 1
0x14000458a  jnz     short loc_1400045C6
0x14000458c  lea     rcx, [rbp+8]; SpinLock
0x140004590  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004597  nop     dword ptr [rax+rax+00h]
0x14000459c  mov     rsi, [rbp+1A0h]
0x1400045a3  lea     rcx, [rbp+8]; SpinLock
0x1400045a7  mov     rdi, [rbp+198h]
0x1400045ae  movzx   edx, al; NewIrql
0x1400045b1  call    cs:__imp_KeReleaseSpinLock
0x1400045b8  nop     dword ptr [rax+rax+00h]
0x1400045bd  test    rdi, rdi
0x1400045c0  jnz     loc_1400046BD
0x1400045c6  lea     rsi, aTdxcloseconnec; "TdxCloseConnectionEndpointTlRequestComp"...
0x1400045cd  mov     r8d, 0B79h
0x1400045d3  mov     rdx, rsi
0x1400045d6  mov     rcx, r14
0x1400045d9  call    DbgTdxDereferenceConnection
0x1400045de  mov     ebx, [rsp+0A8h+arg_8]
0x1400045e5  mov     rdi, [rsp+0A8h+var_40]
0x1400045ea  mov     rcx, qword ptr [rsp+0A8h+var_60]
0x1400045ef  lea     rax, [rsp+0A8h+var_60]
0x1400045f4  cmp     rcx, rax
0x1400045f7  jnz     short loc_14000462F
0x1400045f9  mov     r8d, 0B8Eh
0x1400045ff  mov     rdx, rsi
0x140004602  mov     rcx, r14
0x140004605  call    DbgTdxDereferenceConnection
0x14000460a  test    rbp, rbp
0x14000460d  jnz     loc_140004715
0x140004613  mov     rsi, [rsp+0A8h+var_38]
0x140004618  mov     rbx, [rsp+0A8h+var_30]
0x14000461d  add     rsp, 80h
0x140004624  pop     r15
0x140004626  pop     r14
0x140004628  pop     r13
0x14000462a  pop     r12
0x14000462c  pop     rbp
0x14000462d  retn
0x14000462f  lea     rax, [rsp+0A8h+var_60]
0x140004634  cmp     [rcx+8], rax
0x140004638  jnz     loc_1400047BF
0x14000463e  mov     rax, [rcx]
0x140004641  cmp     [rax+8], rcx
0x140004645  jnz     loc_1400047BF
0x14000464b  mov     qword ptr [rsp+0A8h+var_60], rax
0x140004650  lea     rdx, [rsp+0A8h+var_60]
0x140004655  mov     [rax+8], rdx
0x140004659  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140004660  xor     edx, edx; PriorityBoost
0x140004662  mov     [rcx+30h], ebx
0x140004665  mov     qword ptr [rcx+38h], 0
0x14000466d  call    cs:__imp_IofCompleteRequest
0x140004674  nop     dword ptr [rax+rax+00h]
0x140004679  mov     r8d, 0B88h
0x14000467f  mov     rdx, rsi
0x140004682  mov     rcx, r14
0x140004685  call    DbgTdxDereferenceConnection
0x14000468a  jmp     loc_1400045EA
0x14000468f  mov     r8d, 0B20h
0x140004695  lea     rdx, aMinioNetioSess_6; "minio\\netio\\session\\tdi\\connection."...
0x14000469c  mov     rcx, rbp
0x14000469f  call    DbgTdxReferenceTransportAddress
0x1400046a4  jmp     loc_140004420
0x1400046a9  lea     rbx, [rsp+0A8h+var_60]
0x1400046ae  mov     qword ptr [rsp+0A8h+var_60], rbx
0x1400046b3  lea     rcx, [rsp+0A8h+var_60]
0x1400046b8  jmp     loc_140004490
0x1400046bd  mov     eax, [rsp+0A8h+arg_18]
0x1400046c4  xor     r9d, r9d
0x1400046c7  mov     rdx, [rsp+0A8h+var_68]
0x1400046cc  xor     r8d, r8d
0x1400046cf  mov     [rsp+0A8h+var_78], eax
0x1400046d3  mov     rcx, rsi
0x1400046d6  mov     [rsp+0A8h+var_80], 0
0x1400046df  mov     rax, rdi
0x1400046e2  mov     dword ptr [rsp+0A8h+var_88], 0
0x1400046ea  call    _guard_dispatch_icall
0x1400046ef  and     dword ptr [r14], 0FFFFFEFFh
0x1400046f6  jmp     loc_1400045C6
0x1400046fb  mov     r8d, 0B47h
0x140004701  lea     rdx, aTdxcloseconnec; "TdxCloseConnectionEndpointTlRequestComp"...
0x140004708  mov     rcx, r14
0x14000470b  call    DbgTdxReferenceConnection
0x140004710  jmp     loc_140004557
0x140004715  mov     r8d, 0B90h
0x14000471b  lea     rdx, aMinioNetioSess_6; "minio\\netio\\session\\tdi\\connection."...
0x140004722  mov     rcx, rbp
0x140004725  call    DbgTdxDereferenceTransportAddress
0x14000472a  jmp     loc_140004613
0x14000472f  lea     rsi, aTdxcloseconnec; "TdxCloseConnectionEndpointTlRequestComp"...
0x140004736  jmp     loc_1400045DE
0x14000473b  test    dword ptr [rcx+2Ch], 200h
0x140004742  jz      loc_1400043F3
0x140004748  mov     rcx, [rcx+18h]
0x14000474c  mov     edx, 0Bh
0x140004751  mov     [rsp+0A8h+var_88], r8
0x140004756  mov     r9, r14
0x140004759  lea     r8, WPP_3f4cea39b6aa324a7b8e41338ba6e995_Traceguids
0x140004760  call    WPP_SF_qs
0x140004765  jmp     loc_1400043F3
0x14000476a  lea     rcx, [r14+8]; SpinLock
0x14000476e  mov     [rsp+0A8h+Irql], 0
0x140004776  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000477d  nop     dword ptr [rax+rax+00h]
0x140004782  lea     rcx, [rsp+0A8h+Irql]; Irql
0x14000478a  call    cs:__imp_IoAcquireCancelSpinLock
0x140004791  nop     dword ptr [rax+rax+00h]
0x140004796  movzx   ecx, [rsp+0A8h+Irql]; Irql
0x14000479e  call    cs:__imp_IoReleaseCancelSpinLock
0x1400047a5  nop     dword ptr [rax+rax+00h]
0x1400047aa  lea     rcx, [r14+8]; SpinLock
0x1400047ae  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400047b5  nop     dword ptr [rax+rax+00h]
0x1400047ba  jmp     loc_140004560
0x1400047bf  mov     ecx, 3
0x1400047c4  int     29h; Win8: RtlFailFast(ecx)
```
