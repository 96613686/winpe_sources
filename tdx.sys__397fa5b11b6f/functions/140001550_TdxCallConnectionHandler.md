# TdxCallConnectionHandler

- ea: `0x140001550`
- end: `0x140001977`
- name: `TdxCallConnectionHandler`
- size: `1063`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001a70`
- `0x140001ce0`

## callees

- `0x140001008`
- `0x140001550`
- `0x140002250`
- `0x140002fb0`
- `0x1400034c0`
- `0x140003590`
- `0x140012b8c`
- `0x140012c74`
- `0x1400184b0`
- `0x140018590`
- `0x140018600`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400016e8`
- `ntoskrnl!IofCompleteRequest` at `0x140001966`
- `ntoskrnl!IofCompleteRequest` at `0x1400016e8`
- `ntoskrnl!IofCompleteRequest` at `0x140001966`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000169a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000190e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000169a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000190e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001618`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001837`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400018fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000193d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001618`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400016bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001837`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400018fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000193d`

## pseudocode

```c
__int64 __fastcall TdxCallConnectionHandler(__int64 a1, __int128 *a2, __int128 *a3, KIRQL a4)
{
  __int64 v5; // r13
  unsigned int v6; // r9d
  __int128 *v7; // rax
  __int16 *v10; // rdi
  char v11; // dl
  __int16 v12; // ax
  unsigned __int16 v13; // cx
  unsigned int v14; // esi
  char *FsContext; // rsi
  KIRQL v16; // r14
  __int64 v17; // rax
  __int64 result; // rax
  ADDRESS_FAMILY v19; // cx
  UCHAR v20; // al
  __int64 v21; // r8
  __int64 v22; // r13
  __int128 v23; // xmm0
  union _IRP::$66699B8BF83DC91F51A70E4C6E3F33A6 *p_Tail; // rcx
  __int64 v25; // rax
  int v26; // [rsp+20h] [rbp-79h]
  PIRP Irp[2]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v28; // [rsp+60h] [rbp-39h] BYREF
  __int64 v29; // [rsp+70h] [rbp-29h] BYREF
  unsigned int (__fastcall *v30)(__int64, _QWORD, int *, _QWORD, _QWORD, _DWORD, _QWORD, __int64 *, PIRP *); // [rsp+78h] [rbp-21h]
  int v31; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int16 v32; // [rsp+84h] [rbp-15h]
  __int16 v33; // [rsp+86h] [rbp-13h]
  __int16 v34; // [rsp+88h] [rbp-11h] BYREF
  int v35; // [rsp+8Ah] [rbp-Fh]
  __int64 v36; // [rsp+8Eh] [rbp-Bh]

  v5 = *(_QWORD *)(a1 + 400);
  v6 = 0;
  v30 = *(unsigned int (__fastcall **)(__int64, _QWORD, int *, _QWORD, _QWORD, _DWORD, _QWORD, __int64 *, PIRP *))(a1 + 392);
  v7 = a2;
  *(_QWORD *)&v28 = a3;
  if ( !a2 )
    v7 = a3;
  v29 = 0;
  Irp[0] = 0;
  v10 = (__int16 *)*((_QWORD *)v7 + 3);
  if ( (*(_DWORD *)a1 & 0x40) != 0 )
  {
    if ( !(unsigned __int8)INETADDR_ISV4MAPPED(v10) )
      v11 = v6;
  }
  else
  {
    v11 = 0;
  }
  v12 = *v10;
  if ( *v10 == 35 || v12 == 2 )
  {
    v13 = 14;
  }
  else
  {
    if ( v12 != 23 )
    {
      v14 = v6;
      goto LABEL_10;
    }
    v13 = 14;
    if ( !v11 )
      v13 = 26;
  }
  v14 = v13 + 8;
  if ( v14 > 0x22 )
  {
    v14 = v6;
  }
  else
  {
    v31 = 1;
    v32 = v13;
    if ( v11 )
    {
      v33 = 2;
      v34 = v10[1];
      v25 = 10;
      if ( *v10 != 23 )
        v25 = 8;
      v35 = *(_DWORD *)&v10[v25];
      v36 = 0;
    }
    else
    {
      v33 = *v10;
      memmove(&v34, v10 + 1, v13);
    }
  }
LABEL_10:
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), a4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids, a1);
  }
  if ( v30(v5, v14, &v31, 0, 0, 0, 0, &v29, Irp) != -1073741802 )
  {
    if ( a2 )
      goto LABEL_15;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      v19 = *v10;
      v28 = (unsigned __int64)v10;
      v20 = SOCKADDR_SIZE(v19);
      WORD4(v28) = v20;
      WPP_SF_q_SOCKADDR_(*(_QWORD *)(v21 + 24), v20, v21, a1, (__int64)&v28);
    }
    return 3221226038LL;
  }
  FsContext = (char *)Irp[0]->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)FsContext + 1);
  v17 = *((_QWORD *)FsContext + 11);
  if ( !v17 || v17 != a1 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v16);
    Irp[0]->IoStatus.Status = -1073741504;
    Irp[0]->IoStatus.Information = 0;
    IofCompleteRequest(Irp[0], 2);
    if ( a2 )
      goto LABEL_15;
    return 3221226038LL;
  }
  v22 = v28;
  if ( !(_QWORD)v28 )
  {
    if ( *((int *)FsContext + 19) <= 1 && (*(_DWORD *)FsContext & 2) == 0 )
    {
      *(_DWORD *)FsContext |= 4u;
      v23 = *a2;
      *((_DWORD *)FsContext + 19) = 2;
      *(_OWORD *)(FsContext + 248) = v23;
      p_Tail = &Irp[0]->Tail;
      Irp[0]->Tail.Overlay.DriverContext[3] = Irp[0];
      p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Blink = &p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry;
      p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry.Flink = &p_Tail->Overlay.DeviceQueueEntry.DeviceListEntry;
      p_Tail->Overlay.DriverContext[2] = FsContext;
      DbgTdxReferenceConnection(FsContext, "TdxCallConnectionHandler", 3938);
      TdxHashInsertIrp(Irp[0], a2);
      *((_QWORD *)FsContext + 10) = v29;
      KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v16);
      result = 0;
      *((_DWORD *)a2 + 8) = 1;
      return result;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v16);
    Irp[0]->IoStatus.Status = -1073741504;
    Irp[0]->IoStatus.Information = 0;
    IofCompleteRequest(Irp[0], 2);
LABEL_15:
    *((_DWORD *)a2 + 8) = 2;
    return 0;
  }
  DbgTdxReferenceConnection(FsContext, "TdxCallConnectionHandler", 3902);
  *(_DWORD *)FsContext |= 4u;
  *((_DWORD *)FsContext + 19) = 2;
  KeReleaseSpinLock((PKSPIN_LOCK)FsContext + 1, v16);
  LOBYTE(v26) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  return TdxEventConnectConnection(FsContext, a1, v22, Irp[0], v26);
}

```

## disassembly

```asm
0x140001550  push    rbp
0x140001552  push    rbx
0x140001553  push    rsi
0x140001554  push    rdi
0x140001555  push    r12
0x140001557  push    r13
0x140001559  push    r14
0x14000155b  push    r15
0x14000155d  lea     rbp, [rsp-1Fh]
0x140001562  sub     rsp, 0B8h
0x140001569  mov     rax, cs:__security_cookie
0x140001570  xor     rax, rsp
0x140001573  mov     [rbp+57h+var_48], rax
0x140001577  mov     rax, [rcx+188h]
0x14000157e  movzx   r14d, r9b
0x140001582  mov     r13, [rcx+190h]
0x140001589  xor     r9d, r9d
0x14000158c  mov     [rbp+57h+var_78], rax
0x140001590  test    rdx, rdx
0x140001593  mov     rax, rdx
0x140001596  mov     qword ptr [rbp+57h+var_90], r8
0x14000159a  cmovz   rax, r8
0x14000159e  mov     [rbp+57h+var_80], r9
0x1400015a2  mov     [rbp+57h+Irp], r9
0x1400015a6  mov     rbx, rdx
0x1400015a9  mov     r15, rcx
0x1400015ac  mov     rdi, [rax+18h]
0x1400015b0  mov     eax, [rcx]
0x1400015b2  test    al, 40h
0x1400015b4  jnz     loc_140001866
0x1400015ba  xor     dl, dl
0x1400015bc  movzx   eax, word ptr [rdi]
0x1400015bf  mov     r8d, 2
0x1400015c5  cmp     ax, 23h ; '#'
0x1400015c9  jnz     loc_140001727
0x1400015cf  mov     ecx, 0Eh
0x1400015d4  movzx   eax, cx
0x1400015d7  add     eax, 8
0x1400015da  mov     esi, eax
0x1400015dc  cmp     eax, 22h ; '"'
0x1400015df  ja      loc_140001743
0x1400015e5  mov     [rbp+57h+var_70], 1
0x1400015ec  mov     [rbp+57h+var_6C], cx
0x1400015f0  test    dl, dl
0x1400015f2  jnz     loc_14000187E
0x1400015f8  movzx   eax, word ptr [rdi]
0x1400015fb  lea     rdx, [rdi+2]; Src
0x1400015ff  movzx   r8d, cx; Size
0x140001603  lea     rcx, [rbp+57h+var_68]; void *
0x140001607  mov     [rbp+57h+var_6A], ax
0x14000160b  call    memmove
0x140001610  movzx   edx, r14b; NewIrql
0x140001614  lea     rcx, [r15+8]; SpinLock
0x140001618  call    cs:__imp_KeReleaseSpinLock
0x14000161f  nop     dword ptr [rax+rax+00h]
0x140001624  mov     rcx, cs:WPP_GLOBAL_Control
0x14000162b  lea     r14, WPP_GLOBAL_Control
0x140001632  cmp     rcx, r14
0x140001635  jz      short loc_140001641
0x140001637  cmp     byte ptr [rcx+29h], 5
0x14000163b  jnb     loc_1400018AD
0x140001641  lea     rax, [rbp+57h+Irp]
0x140001645  xor     r9d, r9d
0x140001648  mov     [rsp+0F0h+var_B0], rax
0x14000164d  lea     r8, [rbp+57h+var_70]
0x140001651  lea     rax, [rbp+57h+var_80]
0x140001655  mov     edx, esi
0x140001657  mov     [rsp+0F0h+var_B8], rax
0x14000165c  mov     rcx, r13
0x14000165f  xor     eax, eax
0x140001661  mov     [rsp+0F0h+var_C0], rax
0x140001666  mov     [rsp+0F0h+var_C8], eax
0x14000166a  mov     [rsp+0F0h+var_D0], rax
0x14000166f  mov     rax, [rbp+57h+var_78]
0x140001673  call    _guard_dispatch_icall
0x140001678  cmp     eax, 0C0000016h
0x14000167d  jnz     loc_14000174B
0x140001683  mov     rax, [rbp+57h+Irp]
0x140001687  mov     rcx, [rax+0B8h]
0x14000168e  mov     rax, [rcx+30h]
0x140001692  mov     rsi, [rax+18h]
0x140001696  lea     rcx, [rsi+8]; SpinLock
0x14000169a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400016a1  nop     dword ptr [rax+rax+00h]
0x1400016a6  movzx   r14d, al
0x1400016aa  mov     rax, [rsi+58h]
0x1400016ae  test    rax, rax
0x1400016b1  jnz     loc_1400017AF
0x1400016b7  movzx   edx, r14b; NewIrql
0x1400016bb  lea     rcx, [rsi+8]; SpinLock
0x1400016bf  call    cs:__imp_KeReleaseSpinLock
0x1400016c6  nop     dword ptr [rax+rax+00h]
0x1400016cb  mov     rax, [rbp+57h+Irp]
0x1400016cf  mov     dl, 2; PriorityBoost
0x1400016d1  mov     dword ptr [rax+30h], 0C0000140h
0x1400016d8  mov     rax, [rbp+57h+Irp]
0x1400016dc  mov     qword ptr [rax+38h], 0
0x1400016e4  mov     rcx, [rbp+57h+Irp]; Irp
0x1400016e8  call    cs:__imp_IofCompleteRequest
0x1400016ef  nop     dword ptr [rax+rax+00h]
0x1400016f4  test    rbx, rbx
0x1400016f7  jz      loc_1400017A5
0x1400016fd  mov     dword ptr [rbx+20h], 2
0x140001704  xor     eax, eax
0x140001706  mov     rcx, [rbp+57h+var_48]
0x14000170a  xor     rcx, rsp; StackCookie
0x14000170d  call    __security_check_cookie
0x140001712  add     rsp, 0B8h
0x140001719  pop     r15
0x14000171b  pop     r14
0x14000171d  pop     r13
0x14000171f  pop     r12
0x140001721  pop     rdi
0x140001722  pop     rsi
0x140001723  pop     rbx
0x140001724  pop     rbp
0x140001725  retn
0x140001727  cmp     ax, r8w
0x14000172b  jz      loc_1400015CF
0x140001731  cmp     ax, 17h
0x140001735  jz      loc_140001851
0x14000173b  mov     esi, r9d
0x14000173e  jmp     loc_140001610
0x140001743  mov     esi, r9d
0x140001746  jmp     loc_140001610
0x14000174b  test    rbx, rbx
0x14000174e  jnz     short loc_1400016FD
0x140001750  mov     r8, cs:WPP_GLOBAL_Control
0x140001757  cmp     r8, r14
0x14000175a  jz      short loc_1400017A5
0x14000175c  cmp     byte ptr [r8+29h], 4
0x140001761  jb      short loc_1400017A5
0x140001763  test    dword ptr [r8+2Ch], 200h
0x14000176b  jz      short loc_1400017A5
0x14000176d  movzx   ecx, word ptr [rdi]; af
0x140001770  xorps   xmm0, xmm0
0x140001773  movups  [rbp+57h+var_90], xmm0
0x140001777  mov     qword ptr [rbp+57h+var_90], rdi
0x14000177b  call    SOCKADDR_SIZE
0x140001780  movzx   edx, al
0x140001783  mov     r9, r15
0x140001786  mov     word ptr [rbp+57h+var_90+8], dx
0x14000178a  lea     rax, [rbp+57h+var_90]
0x14000178e  movaps  xmm0, [rbp+57h+var_90]
0x140001792  movdqa  [rbp+57h+var_90], xmm0
0x140001797  mov     rcx, [r8+18h]
0x14000179b  mov     [rsp+0F0h+var_D0], rax
0x1400017a0  call    WPP_SF_q_SOCKADDR_
0x1400017a5  mov     eax, 0C0000236h
0x1400017aa  jmp     loc_140001706
0x1400017af  cmp     rax, r15
0x1400017b2  jnz     loc_1400016B7
0x1400017b8  mov     r13, qword ptr [rbp+57h+var_90]
0x1400017bc  test    r13, r13
0x1400017bf  jnz     loc_1400018D7
0x1400017c5  cmp     dword ptr [rsi+4Ch], 1
0x1400017c9  jg      loc_140001935
0x1400017cf  mov     eax, [rsi]
0x1400017d1  test    al, 2
0x1400017d3  jnz     loc_140001935
0x1400017d9  or      eax, 4
0x1400017dc  lea     rdx, aTdxcallconnect; "TdxCallConnectionHandler"
0x1400017e3  mov     [rsi], eax
0x1400017e5  mov     r8d, 0F62h
0x1400017eb  movups  xmm0, xmmword ptr [rbx]
0x1400017ee  mov     dword ptr [rsi+4Ch], 2
0x1400017f5  movups  xmmword ptr [rsi+0F8h], xmm0
0x1400017fc  mov     rax, [rbp+57h+Irp]
0x140001800  lea     rcx, [rax+78h]
0x140001804  mov     [rcx+18h], rax
0x140001808  mov     [rcx+8], rcx
0x14000180c  mov     [rcx], rcx
0x14000180f  mov     [rcx+10h], rsi
0x140001813  mov     rcx, rsi
0x140001816  call    DbgTdxReferenceConnection
0x14000181b  mov     rcx, [rbp+57h+Irp]
0x14000181f  mov     rdx, rbx
0x140001822  call    TdxHashInsertIrp
0x140001827  mov     rax, [rbp+57h+var_80]
0x14000182b  lea     rcx, [rsi+8]; SpinLock
0x14000182f  movzx   edx, r14b; NewIrql
0x140001833  mov     [rsi+50h], rax
0x140001837  call    cs:__imp_KeReleaseSpinLock
0x14000183e  nop     dword ptr [rax+rax+00h]
0x140001843  xor     eax, eax
0x140001845  mov     dword ptr [rbx+20h], 1
0x14000184c  jmp     loc_140001706
0x140001851  test    dl, dl
0x140001853  mov     ecx, 0Eh
0x140001858  mov     eax, 1Ah
0x14000185d  cmovz   cx, ax
0x140001861  jmp     loc_1400015D4
0x140001866  mov     rcx, rdi
0x140001869  mov     dl, 1
0x14000186b  call    INETADDR_ISV4MAPPED
0x140001870  test    al, al
0x140001872  movzx   edx, dl
0x140001875  cmovz   edx, r9d
0x140001879  jmp     loc_1400015BC
0x14000187e  mov     [rbp+57h+var_6A], r8w
0x140001883  mov     ecx, 10h
0x140001888  movzx   eax, word ptr [rdi+2]
0x14000188c  mov     [rbp+57h+var_68], ax
0x140001890  mov     eax, 14h
0x140001895  cmp     word ptr [rdi], 17h
0x140001899  cmovnz  eax, ecx
0x14000189c  mov     eax, [rax+rdi]
0x14000189f  mov     [rbp+57h+var_66], eax
0x1400018a2  xor     eax, eax
0x1400018a4  mov     [rbp+57h+var_62], rax
0x1400018a8  jmp     loc_140001610
0x1400018ad  test    dword ptr [rcx+2Ch], 200h
0x1400018b4  jz      loc_140001641
0x1400018ba  mov     rcx, [rcx+18h]
0x1400018be  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x1400018c5  mov     edx, 28h ; '('
0x1400018ca  mov     r9, r15
0x1400018cd  call    WPP_SF_q
0x1400018d2  jmp     loc_140001641
0x1400018d7  mov     r8d, 0F3Eh
0x1400018dd  lea     rdx, aTdxcallconnect; "TdxCallConnectionHandler"
0x1400018e4  mov     rcx, rsi
0x1400018e7  call    DbgTdxReferenceConnection
0x1400018ec  or      dword ptr [rsi], 4
0x1400018ef  lea     rcx, [rsi+8]; SpinLock
0x1400018f3  movzx   edx, r14b; NewIrql
0x1400018f7  mov     dword ptr [rsi+4Ch], 2
0x1400018fe  call    cs:__imp_KeReleaseSpinLock
0x140001905  nop     dword ptr [rax+rax+00h]
0x14000190a  lea     rcx, [r15+8]; SpinLock
0x14000190e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001915  nop     dword ptr [rax+rax+00h]
0x14000191a  mov     r9, [rbp+57h+Irp]
0x14000191e  mov     r8, r13
0x140001921  mov     rdx, r15
0x140001924  mov     byte ptr [rsp+0F0h+var_D0], al
0x140001928  mov     rcx, rsi
0x14000192b  call    TdxEventConnectConnection
0x140001930  jmp     loc_140001706
0x140001935  movzx   edx, r14b; NewIrql
0x140001939  lea     rcx, [rsi+8]; SpinLock
0x14000193d  call    cs:__imp_KeReleaseSpinLock
0x140001944  nop     dword ptr [rax+rax+00h]
0x140001949  mov     rax, [rbp+57h+Irp]
0x14000194d  mov     dl, 2; PriorityBoost
0x14000194f  mov     dword ptr [rax+30h], 0C0000140h
0x140001956  mov     rax, [rbp+57h+Irp]
0x14000195a  mov     qword ptr [rax+38h], 0
0x140001962  mov     rcx, [rbp+57h+Irp]; Irp
0x140001966  call    cs:__imp_IofCompleteRequest
0x14000196d  nop     dword ptr [rax+rax+00h]
0x140001972  jmp     loc_1400016FD
```
