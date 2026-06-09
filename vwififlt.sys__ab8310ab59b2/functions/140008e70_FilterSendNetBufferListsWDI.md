# FilterSendNetBufferListsWDI

- ea: `0x140008e70`
- end: `0x140009269`
- name: `FilterSendNetBufferListsWDI`
- size: `1017`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140008cf0`
- `0x140008e10`

## callees

- `0x140008e70`
- `0x140009270`
- `0x14000ada8`
- `0x14000d91c`
- `0x14000dc58`
- `0x14000dd28`
- `0x14000eed4`
- `0x14000f150`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140009140`
- `ntoskrnl!DbgPrint` at `0x1400091c1`
- `ntoskrnl!DbgPrint` at `0x140009140`
- `ntoskrnl!DbgPrint` at `0x1400091c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000903f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000903f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009059`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009059`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008ed6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140008ed6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008f44`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140008f44`
- `NDIS!NdisFSendNetBufferLists` at `0x140009009`
- `NDIS!NdisFSendNetBufferLists` at `0x140009009`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140008f75`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140008f75`

## pseudocode

```c
void __fastcall FilterSendNetBufferListsWDI(
        __int64 a1,
        struct _NET_BUFFER_LIST *a2,
        int a3,
        NDIS_PORT_NUMBER a4,
        ULONG SendFlags)
{
  __int64 v5; // r13
  struct _NET_BUFFER_LIST *v6; // r14
  unsigned __int8 v7; // r15
  KSPIN_LOCK *v10; // rcx
  struct _NET_BUFFER_LIST *v11; // r12
  KSPIN_LOCK *v12; // rcx
  __int64 v13; // r8
  struct _NET_BUFFER_LIST *Alignment; // rbx
  int v15; // edx
  struct _NET_BUFFER_LIST *v16; // rax
  int v17; // ebx
  PDEVICE_OBJECT v18; // rcx
  unsigned __int16 v19; // dx
  struct _NET_BUFFER_LIST *v20; // rax
  SLIST_HEADER *v21; // [rsp+38h] [rbp-40h]
  unsigned int v22; // [rsp+80h] [rbp+8h]

  v5 = *(_QWORD *)(a1 + 8);
  v6 = 0;
  v7 = SendFlags & 1;
  v22 = 0;
  if ( *(_DWORD *)(v5 + 24) != 1801678668 )
  {
    DbgPrint(
      "Trying to acquire uninited lock %p, %s, Line %d\n",
      (const void *)(v5 + 24),
      "FilterSendNetBufferListsWDI",
      3716);
    __debugbreak();
  }
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 28));
  v10 = (KSPIN_LOCK *)(v5 + 104);
  if ( v7 )
    KeAcquireSpinLockAtDpcLevel(v10);
  else
    *(_BYTE *)(v5 + 112) = KeAcquireSpinLockRaiseToDpc(v10);
  *(_BYTE *)(v5 + 32) = 1;
  *(_QWORD *)(v5 + 72) = "FilterSendNetBufferListsWDI";
  *(_DWORD *)(v5 + 80) = 3716;
  if ( !*(_BYTE *)(a1 + 3) )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_38;
    v19 = 227;
    goto LABEL_45;
  }
  if ( *(_DWORD *)(v5 + 120) != 4 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_38;
    v19 = 228;
LABEL_45:
    WPP_SF_d(
      (__int64)v18->AttachedDevice,
      v19,
      (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
      *(_DWORD *)(a1 + 104));
LABEL_38:
    v11 = a2;
    ReleaseSpinLock(v5 + 24, "FilterSendNetBufferListsWDI", 3789, v7);
    v17 = 0;
    goto LABEL_25;
  }
  v11 = 0;
  v21 = 0;
  if ( *(_DWORD *)(v5 + 24) != 1801678668 )
  {
    DbgPrint(
      "Trying to acquire uninited lock %p, %s, Line %d\n",
      (const void *)(v5 + 24),
      "FilterSendNetBufferListsWDI",
      3737);
    __debugbreak();
  }
  *(_DWORD *)(v5 + 96) = 3737;
  *(_QWORD *)(v5 + 88) = "FilterSendNetBufferListsWDI";
  v12 = (KSPIN_LOCK *)(v5 + 104);
  *(_BYTE *)(v5 + 32) = 0;
  if ( v7 )
    KeReleaseSpinLockFromDpcLevel(v12);
  else
    KeReleaseSpinLock(v12, *(_BYTE *)(v5 + 112));
  _InterlockedDecrement((volatile signed __int32 *)(v5 + 28));
  while ( 1 )
  {
    if ( !a2 )
    {
      v17 = 0;
      goto LABEL_19;
    }
    Alignment = (struct _NET_BUFFER_LIST *)a2->Link.Alignment;
    if ( NdisAllocateNetBufferListContext(a2, 0x10u, 0, 0x46465756u) )
      break;
    if ( a2->Context->Size < 8u
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    {
      WPP_SF_ssL(
        WPP_GLOBAL_Control->AttachedDevice,
        v15,
        v13,
        (unsigned int)"NET_BUFFER_LIST_CONTEXT_DATA_SIZE(pCurNbl) >= sizeof(FILTER_SEND_CTX)",
        (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c",
        180);
    }
    ++v22;
    v21 = (SLIST_HEADER *)a2;
    *(_QWORD *)&a2->Context->ContextData[a2->Context->Offset] = a1;
    v16 = a2;
    if ( v6 )
      v16 = v6;
    a2 = Alignment;
    v6 = v16;
  }
  if ( v21 )
    v21->Alignment = 0;
  v17 = -1073741670;
  v11 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 229, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids, v5);
LABEL_19:
  if ( v6 )
  {
    _InterlockedAdd((volatile signed __int32 *)(a1 + 124), v22);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 230, v22, *(unsigned int *)(a1 + 104), v22);
    NdisFSendNetBufferLists(*(NDIS_HANDLE *)(v5 + 128), v6, a4, SendFlags);
  }
  LODWORD(v6) = v22;
LABEL_25:
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 231, v13, *(unsigned int *)(a1 + 104), a3 - (_DWORD)v6, v17);
    if ( v17 )
    {
      v20 = v11;
      do
      {
        v20->Status = v17;
        v20 = (struct _NET_BUFFER_LIST *)v20->Link.Alignment;
      }
      while ( v20 );
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 140));
    (*(void (__fastcall **)(_QWORD, struct _NET_BUFFER_LIST *, _QWORD))(a1 + 72))(
      *(_QWORD *)(a1 + 56),
      v11,
      SendFlags & 1);
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 140));
  }
}

```

## disassembly

```asm
0x140008e70  mov     [rsp+arg_8], rbx
0x140008e75  mov     [rsp+PortNumber], r9d
0x140008e7a  mov     [rsp+arg_10], r8d
0x140008e7f  push    rbp
0x140008e80  push    rsi
0x140008e81  push    rdi
0x140008e82  push    r12
0x140008e84  push    r13
0x140008e86  push    r14
0x140008e88  push    r15
0x140008e8a  sub     rsp, 40h
0x140008e8e  mov     r13, [rcx+8]
0x140008e92  lea     r12, aFiltersendnetb_0; "FilterSendNetBufferListsWDI"
0x140008e99  mov     r15d, [rsp+78h+SendFlags]
0x140008ea1  xor     r14d, r14d
0x140008ea4  and     r15d, 1
0x140008ea8  mov     [rsp+78h+arg_0], r14d
0x140008eb0  mov     rdi, rdx
0x140008eb3  mov     rbp, rcx
0x140008eb6  cmp     dword ptr [r13+18h], 6B636F4Ch
0x140008ebe  jnz     loc_14000912C
0x140008ec4  lock inc dword ptr [r13+1Ch]
0x140008ec9  lea     rcx, [r13+68h]; SpinLock
0x140008ecd  test    r15b, r15b
0x140008ed0  jz      loc_14000903F
0x140008ed6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140008edd  nop     dword ptr [rax+rax+00h]
0x140008ee2  mov     byte ptr [r13+20h], 1
0x140008ee7  mov     [r13+48h], r12
0x140008eeb  mov     dword ptr [r13+50h], 0E84h
0x140008ef3  cmp     [rbp+3], r14b
0x140008ef7  jz      loc_140009152
0x140008efd  cmp     dword ptr [r13+78h], 4
0x140008f02  jnz     loc_140009173
0x140008f08  xor     eax, eax
0x140008f0a  xor     r12d, r12d
0x140008f0d  cmp     dword ptr [r13+18h], 6B636F4Ch
0x140008f15  mov     [rsp+78h+var_40], rax
0x140008f1a  jnz     loc_1400091A9
0x140008f20  mov     dword ptr [r13+60h], 0E99h
0x140008f28  lea     rax, aFiltersendnetb_0; "FilterSendNetBufferListsWDI"
0x140008f2f  mov     [r13+58h], rax
0x140008f33  lea     rcx, [r13+68h]; SpinLock
0x140008f37  mov     [r13+20h], r12b
0x140008f3b  test    r15b, r15b
0x140008f3e  jz      loc_140009054
0x140008f44  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140008f4b  nop     dword ptr [rax+rax+00h]
0x140008f50  lock dec dword ptr [r13+1Ch]
0x140008f55  lea     rsi, WPP_GLOBAL_Control
0x140008f5c  test    rdi, rdi
0x140008f5f  jz      short loc_140008FC3
0x140008f61  mov     rbx, [rdi]
0x140008f64  xor     r8d, r8d; ContextBackFill
0x140008f67  mov     edx, 10h; ContextSize
0x140008f6c  mov     r9d, 46465756h; PoolTag
0x140008f72  mov     rcx, rdi; NetBufferList
0x140008f75  call    cs:__imp_NdisAllocateNetBufferListContext
0x140008f7c  nop     dword ptr [rax+rax+00h]
0x140008f81  test    eax, eax
0x140008f83  jnz     loc_14000906A
0x140008f89  mov     rax, [rdi+10h]
0x140008f8d  cmp     word ptr [rax+8], 8
0x140008f92  jb      loc_1400090B8
0x140008f98  mov     rcx, [rdi+10h]
0x140008f9c  inc     [rsp+78h+arg_0]
0x140008fa3  test    r14, r14
0x140008fa6  mov     [rsp+78h+var_40], rdi
0x140008fab  movzx   eax, word ptr [rcx+0Ah]
0x140008faf  mov     [rax+rcx+10h], rbp
0x140008fb4  mov     rax, rdi
0x140008fb7  cmovnz  rax, r14
0x140008fbb  mov     rdi, rbx
0x140008fbe  mov     r14, rax
0x140008fc1  jmp     short loc_140008F5C
0x140008fc3  mov     ebx, r12d
0x140008fc6  test    r14, r14
0x140008fc9  jz      short loc_140009015
0x140008fcb  mov     r8d, [rsp+78h+arg_0]
0x140008fd3  lock add [rbp+7Ch], r8d
0x140008fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140008fdf  cmp     rcx, rsi
0x140008fe2  jz      short loc_140008FEF
0x140008fe4  mov     eax, [rcx+2Ch]
0x140008fe7  test    al, 4
0x140008fe9  jnz     loc_1400091DB
0x140008fef  mov     r9d, [rsp+78h+SendFlags]; SendFlags
0x140008ff7  mov     rdx, r14; NetBufferList
0x140008ffa  mov     r8d, [rsp+78h+PortNumber]; PortNumber
0x140009002  mov     rcx, [r13+80h]; NdisFilterHandle
0x140009009  call    cs:__imp_NdisFSendNetBufferLists
0x140009010  nop     dword ptr [rax+rax+00h]
0x140009015  mov     r14d, [rsp+78h+arg_0]
0x14000901d  test    r12, r12
0x140009020  jnz     loc_1400091F7
0x140009026  mov     rbx, [rsp+78h+arg_8]
0x14000902e  add     rsp, 40h
0x140009032  pop     r15
0x140009034  pop     r14
0x140009036  pop     r13
0x140009038  pop     r12
0x14000903a  pop     rdi
0x14000903b  pop     rsi
0x14000903c  pop     rbp
0x14000903d  retn
0x14000903f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009046  nop     dword ptr [rax+rax+00h]
0x14000904b  mov     [r13+70h], al
0x14000904f  jmp     loc_140008EE2
0x140009054  movzx   edx, byte ptr [r13+70h]; NewIrql
0x140009059  call    cs:__imp_KeReleaseSpinLock
0x140009060  nop     dword ptr [rax+rax+00h]
0x140009065  jmp     loc_140008F50
0x14000906a  mov     rax, [rsp+78h+var_40]
0x14000906f  test    rax, rax
0x140009072  jnz     loc_1400091D3
0x140009078  mov     ebx, 0C000009Ah
0x14000907d  mov     r12, rdi
0x140009080  mov     rcx, cs:WPP_GLOBAL_Control
0x140009087  cmp     rcx, rsi
0x14000908a  jz      loc_140008FC6
0x140009090  mov     eax, [rcx+2Ch]
0x140009093  test    al, 1
0x140009095  jz      loc_140008FC6
0x14000909b  mov     rcx, [rcx+18h]
0x14000909f  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400090a6  mov     edx, 0E5h
0x1400090ab  mov     r9, r13
0x1400090ae  call    WPP_SF_q
0x1400090b3  jmp     loc_140008FC6
0x1400090b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400090bf  cmp     rcx, rsi
0x1400090c2  jz      loc_140008F98
0x1400090c8  mov     eax, [rcx+2Ch]
0x1400090cb  test    al, 2
0x1400090cd  jz      loc_140008F98
0x1400090d3  mov     rcx, [rcx+18h]
0x1400090d7  lea     rax, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x1400090de  mov     [rsp+78h+var_50], 0EB4h
0x1400090e6  lea     r9, aNetBufferListC; "NET_BUFFER_LIST_CONTEXT_DATA_SIZE(pCurN"...
0x1400090ed  mov     [rsp+78h+var_58], rax
0x1400090f2  call    WPP_SF_ssL
0x1400090f7  jmp     loc_140008F98
0x1400090fc  mov     eax, [rcx+2Ch]
0x1400090ff  test    al, 4
0x140009101  jnz     loc_14000918B
0x140009107  movzx   r9d, r15b
0x14000910b  lea     rdx, aFiltersendnetb_0; "FilterSendNetBufferListsWDI"
0x140009112  mov     r8d, 0ECDh
0x140009118  lea     rcx, [r13+18h]
0x14000911c  mov     r12, rdi
0x14000911f  call    ReleaseSpinLock
0x140009124  mov     ebx, r14d
0x140009127  jmp     loc_14000901D
0x14000912c  mov     r9d, 0E84h
0x140009132  lea     rdx, [r13+18h]
0x140009136  mov     r8, r12
0x140009139  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x140009140  call    cs:__imp_DbgPrint
0x140009147  nop     dword ptr [rax+rax+00h]
0x14000914c  int     3; Trap to Debugger
0x14000914d  jmp     loc_140008EC4
0x140009152  mov     rcx, cs:WPP_GLOBAL_Control
0x140009159  lea     rsi, WPP_GLOBAL_Control
0x140009160  cmp     rcx, rsi
0x140009163  jz      short loc_140009107
0x140009165  mov     eax, [rcx+2Ch]
0x140009168  test    al, 4
0x14000916a  jz      short loc_140009107
0x14000916c  mov     edx, 0E3h
0x140009171  jmp     short loc_140009190
0x140009173  mov     rcx, cs:WPP_GLOBAL_Control
0x14000917a  lea     rsi, WPP_GLOBAL_Control
0x140009181  cmp     rcx, rsi
0x140009184  jz      short loc_140009107
0x140009186  jmp     loc_1400090FC
0x14000918b  mov     edx, 0E4h
0x140009190  mov     r9d, [rbp+68h]
0x140009194  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000919b  mov     rcx, [rcx+18h]
0x14000919f  call    WPP_SF_d
0x1400091a4  jmp     loc_140009107
0x1400091a9  mov     r9d, 0E99h
0x1400091af  lea     r8, aFiltersendnetb_0; "FilterSendNetBufferListsWDI"
0x1400091b6  lea     rdx, [r13+18h]
0x1400091ba  lea     rcx, Format; "Trying to acquire uninited lock %p, %s,"...
0x1400091c1  call    cs:__imp_DbgPrint
0x1400091c8  nop     dword ptr [rax+rax+00h]
0x1400091cd  int     3; Trap to Debugger
0x1400091ce  jmp     loc_140008F20
0x1400091d3  mov     [rax], r12
0x1400091d6  jmp     loc_140009078
0x1400091db  mov     r9d, [rbp+68h]
0x1400091df  mov     edx, 0E6h
0x1400091e4  mov     rcx, [rcx+18h]
0x1400091e8  mov     dword ptr [rsp+78h+var_58], r8d
0x1400091ed  call    WPP_SF_Dd
0x1400091f2  jmp     loc_140008FEF
0x1400091f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400091fe  cmp     rcx, rsi
0x140009201  jz      short loc_14000922E
0x140009203  mov     eax, [rcx+2Ch]
0x140009206  test    al, 4
0x140009208  jz      short loc_14000922E
0x14000920a  mov     eax, [rsp+78h+arg_10]
0x140009211  mov     edx, 0E7h
0x140009216  mov     r9d, [rbp+68h]
0x14000921a  sub     eax, r14d
0x14000921d  mov     rcx, [rcx+18h]
0x140009221  mov     [rsp+78h+var_50], ebx
0x140009225  mov     dword ptr [rsp+78h+var_58], eax
0x140009229  call    WPP_SF_ddD
0x14000922e  test    ebx, ebx
0x140009230  jz      short loc_140009243
0x140009232  mov     rax, r12
0x140009235  mov     [rax+8Ch], ebx
0x14000923b  mov     rax, [rax]
0x14000923e  test    rax, rax
0x140009241  jnz     short loc_140009235
0x140009243  lock inc dword ptr [rbp+8Ch]
0x14000924a  mov     rax, [rbp+48h]
0x14000924e  mov     r8d, r15d
0x140009251  mov     rcx, [rbp+38h]
0x140009255  mov     rdx, r12
0x140009258  call    _guard_dispatch_icall
0x14000925d  lock dec dword ptr [rbp+8Ch]
0x140009264  jmp     loc_140009026
```
