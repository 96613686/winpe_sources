# FilterSendNetBufferListsLegacy

- ea: `0x140009300`
- end: `0x140009734`
- name: `FilterSendNetBufferListsLegacy`
- size: `1076`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140008cf0`
- `0x140008e10`

## callees

- `0x140009270`
- `0x140009300`
- `0x14000ada8`
- `0x14000d91c`
- `0x14000dc58`
- `0x14000dd28`
- `0x14000eed4`
- `0x14000f150`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400095f5`
- `ntoskrnl!DbgPrint` at `0x140009690`
- `ntoskrnl!DbgPrint` at `0x1400095f5`
- `ntoskrnl!DbgPrint` at `0x140009690`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400094ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400094ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400094c6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400094c6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009357`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009357`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400093c3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400093c3`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000942c`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x14000942c`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x1400093ff`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x1400093ff`
- `NDIS!NdisFSendNetBufferLists` at `0x140009490`
- `NDIS!NdisFSendNetBufferLists` at `0x140009490`
- `NDIS!NdisFreeCloneNetBufferList` at `0x140009578`
- `NDIS!NdisFreeCloneNetBufferList` at `0x140009578`

## string_xrefs

- `0x1400095bf`: `PrevNblCopy`

## pseudocode

```c
void __fastcall FilterSendNetBufferListsLegacy(
        __int64 a1,
        struct _NET_BUFFER_LIST *a2,
        unsigned int a3,
        NDIS_PORT_NUMBER a4,
        ULONG SendFlags)
{
  __int64 v5; // rbp
  struct _NET_BUFFER_LIST *v6; // r12
  unsigned __int8 v8; // di
  KSPIN_LOCK *v11; // rcx
  KSPIN_LOCK *v12; // rcx
  __int64 v13; // r8
  NDIS_HANDLE *v14; // rdi
  struct _NET_BUFFER_LIST *Alignment; // rbx
  NDIS_HANDLE *v16; // r15
  PNET_BUFFER_LIST CloneNetBufferList; // rax
  __int64 v18; // r8
  PNET_BUFFER_LIST v19; // rsi
  PNET_BUFFER_LIST *v20; // rdx
  char v21; // r15
  int v22; // esi
  unsigned int v23; // ebx
  struct _NET_BUFFER_LIST *v24; // rdx
  struct _NET_BUFFER_LIST *i; // rax
  struct _NET_BUFFER_LIST *v26; // rbx
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  SLIST_HEADER *v29; // [rsp+80h] [rbp+8h]

  v5 = *(_QWORD *)(a1 + 8);
  v6 = 0;
  v8 = SendFlags & 1;
  if ( *(_DWORD *)(v5 + 24) != 1801678668 )
  {
    DbgPrint(
      "Trying to acquire uninited lock %p, %s, Line %d\n",
      (const void *)(v5 + 24),
      "FilterSendNetBufferListsLegacy",
      3847);
    __debugbreak();
  }
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 28));
  v11 = (KSPIN_LOCK *)(v5 + 104);
  if ( v8 )
    KeAcquireSpinLockAtDpcLevel(v11);
  else
    *(_BYTE *)(v5 + 112) = KeAcquireSpinLockRaiseToDpc(v11);
  *(_BYTE *)(v5 + 32) = 1;
  *(_QWORD *)(v5 + 72) = "FilterSendNetBufferListsLegacy";
  *(_DWORD *)(v5 + 80) = 3847;
  if ( !*(_BYTE *)(a1 + 3) )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_46;
    v28 = 232;
    goto LABEL_45;
  }
  if ( *(_DWORD *)(v5 + 120) != 4 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_46;
    v28 = 233;
LABEL_45:
    WPP_SF_d(v27->AttachedDevice, v28, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
LABEL_46:
    v22 = 0;
    v21 = 0;
    ReleaseSpinLock(v5 + 24, "FilterSendNetBufferListsLegacy", 3932, v8);
    goto LABEL_49;
  }
  v29 = 0;
  _InterlockedAdd((volatile signed __int32 *)(a1 + 124), a3);
  if ( *(_DWORD *)(v5 + 24) != 1801678668 )
  {
    DbgPrint(
      "Trying to acquire uninited lock %p, %s, Line %d\n",
      (const void *)(v5 + 24),
      "FilterSendNetBufferListsLegacy",
      3877);
    __debugbreak();
  }
  *(_QWORD *)(v5 + 88) = "FilterSendNetBufferListsLegacy";
  v12 = (KSPIN_LOCK *)(v5 + 104);
  *(_DWORD *)(v5 + 96) = 3877;
  *(_BYTE *)(v5 + 32) = 0;
  if ( v8 )
    KeReleaseSpinLockFromDpcLevel(v12);
  else
    KeReleaseSpinLock(v12, *(_BYTE *)(v5 + 112));
  _InterlockedDecrement((volatile signed __int32 *)(v5 + 28));
  v14 = (NDIS_HANDLE *)(v5 + 128);
  Alignment = a2;
  v16 = (NDIS_HANDLE *)(v5 + 128);
  while ( 1 )
  {
    if ( !Alignment )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v14 = v16;
      }
      else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 235, v13, *(unsigned int *)(a1 + 104), a3);
      }
      NdisFSendNetBufferLists(*v14, v6, a4, SendFlags);
      return;
    }
    CloneNetBufferList = NdisAllocateCloneNetBufferList(Alignment, *(NDIS_HANDLE *)(v5 + 2568), 0, 2u);
    v19 = CloneNetBufferList;
    if ( !CloneNetBufferList )
      break;
    CloneNetBufferList->ProtocolReserved[0] = (PVOID)a1;
    CloneNetBufferList->ProtocolReserved[1] = Alignment;
    CloneNetBufferList->Link.Alignment = 0;
    NdisCopySendNetBufferListInfo(CloneNetBufferList, Alignment);
    v16 = (NDIS_HANDLE *)(v5 + 128);
    v19->SourceHandle = *(NDIS_HANDLE *)(v5 + 128);
    if ( v6 )
    {
      v20 = (PNET_BUFFER_LIST *)v29;
      if ( !v29
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        WPP_SF_ssL(
          WPP_GLOBAL_Control->AttachedDevice,
          0,
          v13,
          (unsigned int)"PrevNblCopy",
          (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c",
          77);
        v20 = 0;
      }
      *v20 = v19;
    }
    else
    {
      v6 = v19;
    }
    Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
    v29 = (SLIST_HEADER *)v19;
  }
  v21 = 1;
  v22 = -1073741670;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v23 = a3;
    goto LABEL_29;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 234, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids, v5);
LABEL_49:
  v23 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 236, v18, *(unsigned int *)(a1 + 104), a3, v22);
  if ( v22 )
  {
LABEL_29:
    v24 = a2;
    for ( i = a2; i; i = (struct _NET_BUFFER_LIST *)i->Link.Alignment )
      i->Status = v22;
  }
  else
  {
    v24 = a2;
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 140));
  (*(void (__fastcall **)(_QWORD, struct _NET_BUFFER_LIST *, _QWORD))(a1 + 72))(*(_QWORD *)(a1 + 56), v24, SendFlags);
  _InterlockedDecrement((volatile signed __int32 *)(a1 + 140));
  if ( v21 )
    _InterlockedAdd((volatile signed __int32 *)(a1 + 124), -v23);
  if ( v6 )
  {
    do
    {
      v26 = (struct _NET_BUFFER_LIST *)v6->Link.Alignment;
      NdisFreeCloneNetBufferList(v6, 2u);
      v6 = v26;
    }
    while ( v26 );
  }
}

```

## disassembly

```asm
0x140009300  mov     [rsp+PortNumber], r9d
0x140009305  mov     [rsp+arg_10], r8d
0x14000930a  mov     [rsp+arg_8], rdx
0x14000930f  push    rbx
0x140009310  push    rbp
0x140009311  push    rsi
0x140009312  push    rdi
0x140009313  push    r12
0x140009315  push    r13
0x140009317  push    r14
0x140009319  push    r15
0x14000931b  sub     rsp, 38h
0x14000931f  mov     rbp, [rcx+8]
0x140009323  xor     r12d, r12d
0x140009326  mov     edi, [rsp+78h+SendFlags]
0x14000932d  mov     r15d, r8d
0x140009330  and     edi, 1
0x140009333  mov     r14, rdx
0x140009336  mov     r13, rcx
0x140009339  cmp     dword ptr [rbp+18h], 6B636F4Ch
0x140009340  jnz     loc_1400095DD
0x140009346  lock inc dword ptr [rbp+1Ch]
0x14000934a  lea     rcx, [rbp+68h]; SpinLock
0x14000934e  test    dil, dil
0x140009351  jz      loc_1400094AE
0x140009357  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000935e  nop     dword ptr [rax+rax+00h]
0x140009363  lea     rcx, aFiltersendnetb; "FilterSendNetBufferListsLegacy"
0x14000936a  mov     byte ptr [rbp+20h], 1
0x14000936e  mov     [rbp+48h], rcx
0x140009372  mov     dword ptr [rbp+50h], 0F07h
0x140009379  cmp     [r13+3], r12b
0x14000937d  jz      loc_140009607
0x140009383  cmp     dword ptr [rbp+78h], 4
0x140009387  jnz     loc_140009628
0x14000938d  mov     [rsp+78h+arg_0], r12
0x140009395  lock add [r13+7Ch], r15d
0x14000939a  cmp     dword ptr [rbp+18h], 6B636F4Ch
0x1400093a1  jnz     loc_14000967C
0x1400093a7  mov     [rbp+58h], rcx
0x1400093ab  lea     rcx, [rbp+68h]; SpinLock
0x1400093af  mov     dword ptr [rbp+60h], 0F25h
0x1400093b6  mov     [rbp+20h], r12b
0x1400093ba  test    dil, dil
0x1400093bd  jz      loc_1400094C2
0x1400093c3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400093ca  nop     dword ptr [rax+rax+00h]
0x1400093cf  lock dec dword ptr [rbp+1Ch]
0x1400093d3  lea     rdi, [rbp+80h]
0x1400093da  mov     rbx, r14
0x1400093dd  mov     r15, rdi
0x1400093e0  lea     r14, WPP_GLOBAL_Control
0x1400093e7  test    rbx, rbx
0x1400093ea  jz      short loc_14000945F
0x1400093ec  mov     rdx, [rbp+0A08h]; NetBufferListPoolHandle
0x1400093f3  mov     r9d, 2; AllocateCloneFlags
0x1400093f9  xor     r8d, r8d; NetBufferPoolHandle
0x1400093fc  mov     rcx, rbx; OriginalNetBufferList
0x1400093ff  call    cs:__imp_NdisAllocateCloneNetBufferList
0x140009406  nop     dword ptr [rax+rax+00h]
0x14000940b  mov     rsi, rax
0x14000940e  test    rax, rax
0x140009411  jz      loc_1400094F5
0x140009417  mov     rdx, rbx; SrcNetBufferList
0x14000941a  mov     [rax+40h], r13
0x14000941e  mov     rcx, rax; DestNetBufferList
0x140009421  mov     [rax+48h], rbx
0x140009425  mov     qword ptr [rax], 0
0x14000942c  call    cs:__imp_NdisCopySendNetBufferListInfo
0x140009433  nop     dword ptr [rax+rax+00h]
0x140009438  lea     r15, [rbp+80h]
0x14000943f  mov     rcx, [r15]
0x140009442  mov     [rsi+78h], rcx
0x140009446  test    r12, r12
0x140009449  jnz     loc_1400094D7
0x14000944f  mov     r12, rsi
0x140009452  mov     rbx, [rbx]
0x140009455  mov     [rsp+78h+arg_0], rsi
0x14000945d  jmp     short loc_1400093E7
0x14000945f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009466  cmp     rcx, r14
0x140009469  jz      loc_1400094F0
0x14000946f  mov     eax, [rcx+2Ch]
0x140009472  test    al, 4
0x140009474  jnz     loc_140009712
0x14000947a  mov     r9d, [rsp+78h+SendFlags]; SendFlags
0x140009482  mov     rdx, r12; NetBufferList
0x140009485  mov     r8d, [rsp+78h+PortNumber]; PortNumber
0x14000948d  mov     rcx, [rdi]; NdisFilterHandle
0x140009490  call    cs:__imp_NdisFSendNetBufferLists
0x140009497  nop     dword ptr [rax+rax+00h]
0x14000949c  add     rsp, 38h
0x1400094a0  pop     r15
0x1400094a2  pop     r14
0x1400094a4  pop     r13
0x1400094a6  pop     r12
0x1400094a8  pop     rdi
0x1400094a9  pop     rsi
0x1400094aa  pop     rbp
0x1400094ab  pop     rbx
0x1400094ac  retn
0x1400094ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400094b5  nop     dword ptr [rax+rax+00h]
0x1400094ba  mov     [rbp+70h], al
0x1400094bd  jmp     loc_140009363
0x1400094c2  movzx   edx, byte ptr [rbp+70h]; NewIrql
0x1400094c6  call    cs:__imp_KeReleaseSpinLock
0x1400094cd  nop     dword ptr [rax+rax+00h]
0x1400094d2  jmp     loc_1400093CF
0x1400094d7  mov     rdx, [rsp+78h+arg_0]
0x1400094df  test    rdx, rdx
0x1400094e2  jz      loc_140009591
0x1400094e8  mov     [rdx], rsi
0x1400094eb  jmp     loc_140009452
0x1400094f0  mov     rdi, r15
0x1400094f3  jmp     short loc_14000947A
0x1400094f5  mov     r15b, 1
0x1400094f8  mov     esi, 0C000009Ah
0x1400094fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140009504  cmp     rcx, r14
0x140009507  jnz     loc_1400096A9
0x14000950d  mov     ebx, [rsp+78h+arg_10]
0x140009514  mov     rdx, [rsp+78h+arg_8]
0x14000951c  mov     rax, rdx
0x14000951f  test    rdx, rdx
0x140009522  jz      short loc_140009532
0x140009524  mov     [rax+8Ch], esi
0x14000952a  mov     rax, [rax]
0x14000952d  test    rax, rax
0x140009530  jnz     short loc_140009524
0x140009532  lock inc dword ptr [r13+8Ch]
0x14000953a  mov     rax, [r13+48h]
0x14000953e  mov     r8d, [rsp+78h+SendFlags]
0x140009546  mov     rcx, [r13+38h]
0x14000954a  call    _guard_dispatch_icall
0x14000954f  lock dec dword ptr [r13+8Ch]
0x140009557  test    r15b, r15b
0x14000955a  jz      short loc_140009563
0x14000955c  neg     ebx
0x14000955e  lock add [r13+7Ch], ebx
0x140009563  test    r12, r12
0x140009566  jz      loc_14000949C
0x14000956c  mov     rbx, [r12]
0x140009570  mov     edx, 2; FreeCloneFlags
0x140009575  mov     rcx, r12; CloneNetBufferList
0x140009578  call    cs:__imp_NdisFreeCloneNetBufferList
0x14000957f  nop     dword ptr [rax+rax+00h]
0x140009584  mov     r12, rbx
0x140009587  test    rbx, rbx
0x14000958a  jnz     short loc_14000956C
0x14000958c  jmp     loc_14000949C
0x140009591  mov     rcx, cs:WPP_GLOBAL_Control
0x140009598  cmp     rcx, r14
0x14000959b  jz      loc_1400094E8
0x1400095a1  mov     eax, [rcx+2Ch]
0x1400095a4  test    al, 2
0x1400095a6  jz      loc_1400094E8
0x1400095ac  mov     rcx, [rcx+18h]
0x1400095b0  lea     rax, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x1400095b7  mov     [rsp+78h+var_50], 0F4Dh
0x1400095bf  lea     r9, aPrevnblcopy; "PrevNblCopy"
0x1400095c6  mov     [rsp+78h+var_58], rax
0x1400095cb  call    WPP_SF_ssL
0x1400095d0  mov     rdx, [rsp+78h+arg_0]
0x1400095d8  jmp     loc_1400094E8
0x1400095dd  mov     r9d, 0F07h
0x1400095e3  lea     r8, aFiltersendnetb; "FilterSendNetBufferListsLegacy"
0x1400095ea  lea     rdx, [rbp+18h]
0x1400095ee  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x1400095f5  call    cs:__imp_DbgPrint
0x1400095fc  nop     dword ptr [rax+rax+00h]
0x140009601  int     3; Trap to Debugger
0x140009602  jmp     loc_140009346
0x140009607  mov     rcx, cs:WPP_GLOBAL_Control
0x14000960e  lea     r14, WPP_GLOBAL_Control
0x140009615  cmp     rcx, r14
0x140009618  jz      short loc_14000965B
0x14000961a  mov     eax, [rcx+2Ch]
0x14000961d  test    al, 4
0x14000961f  jz      short loc_14000965B
0x140009621  mov     edx, 0E8h
0x140009626  jmp     short loc_140009647
0x140009628  mov     rcx, cs:WPP_GLOBAL_Control
0x14000962f  lea     r14, WPP_GLOBAL_Control
0x140009636  cmp     rcx, r14
0x140009639  jz      short loc_14000965B
0x14000963b  mov     eax, [rcx+2Ch]
0x14000963e  test    al, 4
0x140009640  jz      short loc_14000965B
0x140009642  mov     edx, 0E9h
0x140009647  mov     r9d, [r13+68h]
0x14000964b  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140009652  mov     rcx, [rcx+18h]
0x140009656  call    WPP_SF_d
0x14000965b  xor     esi, esi
0x14000965d  lea     rdx, aFiltersendnetb; "FilterSendNetBufferListsLegacy"
0x140009664  xor     r15b, r15b
0x140009667  lea     rcx, [rbp+18h]
0x14000966b  movzx   r9d, dil
0x14000966f  mov     r8d, 0F5Ch
0x140009675  call    ReleaseSpinLock
0x14000967a  jmp     short loc_1400096C9
0x14000967c  mov     r8, rcx
0x14000967f  lea     rdx, [rbp+18h]
0x140009683  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x14000968a  mov     r9d, 0F25h
0x140009690  call    cs:__imp_DbgPrint
0x140009697  nop     dword ptr [rax+rax+00h]
0x14000969c  int     3; Trap to Debugger
0x14000969d  lea     rcx, aFiltersendnetb; "FilterSendNetBufferListsLegacy"
0x1400096a4  jmp     loc_1400093A7
0x1400096a9  mov     eax, [rcx+2Ch]
0x1400096ac  test    r15b, al
0x1400096af  jz      short loc_1400096C9
0x1400096b1  mov     rcx, [rcx+18h]
0x1400096b5  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400096bc  mov     edx, 0EAh
0x1400096c1  mov     r9, rbp
0x1400096c4  call    WPP_SF_q
0x1400096c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400096d0  mov     ebx, [rsp+78h+arg_10]
0x1400096d7  cmp     rcx, r14
0x1400096da  jz      short loc_1400096FD
0x1400096dc  mov     eax, [rcx+2Ch]
0x1400096df  test    al, 4
0x1400096e1  jz      short loc_1400096FD
0x1400096e3  mov     r9d, [r13+68h]
0x1400096e7  mov     edx, 0ECh
0x1400096ec  mov     rcx, [rcx+18h]
0x1400096f0  mov     [rsp+78h+var_50], esi
0x1400096f4  mov     dword ptr [rsp+78h+var_58], ebx
0x1400096f8  call    WPP_SF_ddD
0x1400096fd  test    esi, esi
0x1400096ff  jnz     loc_140009514
0x140009705  mov     rdx, [rsp+78h+arg_8]
0x14000970d  jmp     loc_140009532
0x140009712  mov     ebx, [rsp+78h+arg_10]
0x140009719  mov     edx, 0EBh
0x14000971e  mov     r9d, [r13+68h]
0x140009722  mov     rcx, [rcx+18h]
0x140009726  mov     dword ptr [rsp+78h+var_58], ebx
0x14000972a  call    WPP_SF_Dd
0x14000972f  jmp     loc_14000947A
```
