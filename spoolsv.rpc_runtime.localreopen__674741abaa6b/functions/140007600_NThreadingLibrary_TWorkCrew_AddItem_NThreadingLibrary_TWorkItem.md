# NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)

- ea: `0x140007600`
- end: `0x14000786b`
- name: `?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z`
- size: `619`
- prototype: `__int64 __fastcall(NThreadingLibrary::TWorkCrew *__hidden this, struct NThreadingLibrary::TWorkItem *)`
- caller_count: `76`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007360`
- `0x140007500`
- `0x140007880`
- `0x140007d80`
- `0x140007fe0`
- `0x140008320`
- `0x140008b90`
- `0x14000b130`
- `0x14000da70`
- `0x140015c0c`
- `0x1400451d0`
- `0x140045270`
- `0x140045310`
- `0x1400453f0`
- `0x140045510`
- `0x140045650`
- `0x140045790`
- `0x140045920`
- `0x140045a30`
- `0x140045b70`
- `0x140045c50`
- `0x140045cf0`
- `0x140045e20`
- `0x140045f80`
- `0x1400460b0`
- `0x140046210`
- `0x1400462b0`
- `0x140046390`
- `0x140046480`
- `0x1400465e0`
- `0x140046750`
- `0x140046850`
- `0x1400468f0`
- `0x1400469d0`
- `0x140046a70`
- `0x140046b10`
- `0x140046c20`
- `0x140046d00`
- `0x140046e10`
- `0x140046f20`
- `0x140047030`
- `0x140047160`
- `0x140047290`
- `0x140047380`
- `0x140047480`
- `0x1400475b0`
- `0x1400476a0`
- `0x140047770`
- `0x140047870`
- `0x140047980`

## callees

- `0x140007600`
- `0x140007a90`
- `0x14005628c`
- `0x140056320`
- `0x140056390`
- `0x140056430`
- `0x1400564d4`
- `0x140081010`

## import_xrefs

- `ntdll!TpSimpleTryPost` at `0x140007800`
- `ntdll!TpSimpleTryPost` at `0x140007800`
- `ntdll!RtlNtStatusToDosError` at `0x14000780e`
- `ntdll!RtlNtStatusToDosError` at `0x14000780e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007766`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007766`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007650`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000765f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000765f`

## pseudocode

```c
__int64 __fastcall NThreadingLibrary::TWorkCrew::AddItem(
        struct _RTL_CRITICAL_SECTION *this,
        struct NThreadingLibrary::TWorkItem *a2)
{
  unsigned int v4; // edi
  int v5; // r14d
  char *v6; // rdx
  __int64 v7; // rax
  char *v8; // r8
  __int64 v9; // r9
  signed __int32 i; // eax
  struct _TP_CALLBACK_ENVIRON_V3 *LockSemaphore; // r8
  int v13; // ecx
  NThreadingLibrary::TWorkCrew *v14; // rcx
  NThreadingLibrary::TWorkCrew *v15; // rcx
  NThreadingLibrary::TWorkCrew *v16; // rcx
  NThreadingLibrary::TWorkCrew *v17; // rcx
  NTSTATUS v18; // eax
  signed int v19; // eax

  if ( !a2
    || (*(int (__fastcall **)(struct NThreadingLibrary::TWorkItem *))(*(_QWORD *)a2 + 16LL))(a2) < 0
    || *((_DWORD *)a2 + 16) != 1953063799 )
  {
    return 2147942487LL;
  }
  EnterCriticalSection(this + 1);
  ++HIDWORD(this[2].DebugInfo);
  LODWORD(this[2].DebugInfo) = GetCurrentThreadId();
  v4 = -2147024809;
  if ( LODWORD(this[4].OwningThread) )
  {
    v5 = -2147467259;
  }
  else if ( *((_QWORD *)a2 + 10) )
  {
    v5 = 0;
    if ( *((_DWORD *)a2 + 18) )
      v5 = -2147024846;
  }
  else
  {
    v6 = (char *)a2 + 32;
    if ( a2 == (struct NThreadingLibrary::TWorkItem *)-32LL )
    {
      v5 = -2147024809;
    }
    else
    {
      v7 = *((_QWORD *)a2 + 6);
      v8 = (char *)a2 + 56;
      if ( v7 && *(_QWORD *)v8 )
        v5 = 0;
      else
        v5 = -2147467259;
      if ( v5 >= 0 )
      {
        v9 = *(_QWORD *)&this[3].LockCount;
        if ( (char *)v7 != v6 && *(char **)v8 != v6 )
        {
          *(_QWORD *)(v7 + 24) = *(_QWORD *)v8;
          *(_QWORD *)(*(_QWORD *)v8 + 16LL) = *((_QWORD *)a2 + 6);
          *((_QWORD *)a2 + 6) = v6;
          *(_QWORD *)v8 = v6;
        }
        v5 = 0;
        *(_QWORD *)(*(_QWORD *)(v9 + 16) + 24LL) = v6;
        *((_QWORD *)a2 + 6) = *(_QWORD *)(v9 + 16);
        *(_QWORD *)v8 = v9;
        *(_QWORD *)(v9 + 16) = v6;
        *((_QWORD *)a2 + 10) = this;
        *(_QWORD *)((char *)a2 + 68) = 0;
        ++LODWORD(this[5].DebugInfo);
        for ( i = *((_DWORD *)a2 + 2); i != 0x7FFFFFFF; i = *((_DWORD *)a2 + 2) )
        {
          if ( i == _InterlockedCompareExchange((volatile signed __int32 *)a2 + 2, i + 1, i) )
            break;
        }
      }
    }
  }
  if ( HIDWORD(this[2].DebugInfo)-- == 1 )
    LODWORD(this[2].DebugInfo) = 0;
  LeaveCriticalSection(this + 1);
  if ( v5 >= 0 )
  {
    LockSemaphore = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)a2 + 3);
    if ( LockSemaphore )
      LockSemaphore->Pool = (PTP_POOL)this[5].LockSemaphore;
    else
      LockSemaphore = (struct _TP_CALLBACK_ENVIRON_V3 *)this->LockSemaphore;
    v13 = *((_DWORD *)a2 + 22);
    if ( v13 )
    {
      v14 = (NThreadingLibrary::TWorkCrew *)(unsigned int)(v13 - 1);
      if ( (_DWORD)v14 )
      {
        v15 = (NThreadingLibrary::TWorkCrew *)(unsigned int)((_DWORD)v14 - 1);
        if ( (_DWORD)v15 )
        {
          v16 = (NThreadingLibrary::TWorkCrew *)(unsigned int)((_DWORD)v15 - 1);
          if ( (_DWORD)v16 )
          {
            v17 = (NThreadingLibrary::TWorkCrew *)(unsigned int)((_DWORD)v16 - 1);
            if ( (_DWORD)v17 )
            {
              if ( (_DWORD)v17 != 1 )
                goto LABEL_43;
              v4 = NThreadingLibrary::TWorkCrew::AddLpcItem(v17, a2, LockSemaphore);
            }
            else
            {
              v4 = NThreadingLibrary::TWorkCrew::AddIOItem(v17, a2, LockSemaphore);
            }
          }
          else
          {
            v4 = NThreadingLibrary::TWorkCrew::AddTimerItem(v16, a2, LockSemaphore);
          }
        }
        else
        {
          v4 = NThreadingLibrary::TWorkCrew::AddWaitItem(v15, a2, LockSemaphore);
        }
      }
      else
      {
        v4 = NThreadingLibrary::TWorkCrew::AddWorkItem(v14, a2, LockSemaphore);
      }
    }
    else
    {
      v18 = TpSimpleTryPost(NThreadingLibrary::TWorkCrew::tpSimpleCallback, a2, LockSemaphore);
      v19 = RtlNtStatusToDosError(v18);
      v4 = v19;
      if ( v19 > 0 )
        v4 = (unsigned __int16)v19 | 0x80070000;
    }
    if ( (v4 & 0x80000000) == 0 )
      return v4;
LABEL_43:
    NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue((NThreadingLibrary::TWorkCrew *)this, a2);
    return v4;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140007600  mov     [rsp+arg_10], rbp
0x140007605  mov     [rsp+arg_18], rsi
0x14000760a  push    rdi
0x14000760b  sub     rsp, 20h
0x14000760f  mov     rsi, rdx
0x140007612  mov     rbp, rcx
0x140007615  test    rdx, rdx
0x140007618  jz      loc_140007855
0x14000761e  mov     rax, [rdx]
0x140007621  mov     rcx, rdx
0x140007624  mov     rax, [rax+10h]
0x140007628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000762d  test    eax, eax
0x14000762f  js      loc_140007855
0x140007635  cmp     dword ptr [rsi+40h], 74696377h
0x14000763c  jnz     loc_140007855
0x140007642  mov     [rsp+28h+arg_0], rbx
0x140007647  lea     rcx, [rbp+28h]; lpCriticalSection
0x14000764b  mov     [rsp+28h+arg_8], r14
0x140007650  call    cs:__imp_EnterCriticalSection
0x140007657  nop     dword ptr [rax+rax+00h]
0x14000765c  inc     dword ptr [rbp+54h]
0x14000765f  call    cs:__imp_GetCurrentThreadId
0x140007666  nop     dword ptr [rax+rax+00h]
0x14000766b  mov     [rbp+50h], eax
0x14000766e  mov     edi, 80070057h
0x140007673  cmp     dword ptr [rbp+0B0h], 0
0x14000767a  jnz     loc_14000774C
0x140007680  cmp     qword ptr [rsi+50h], 0
0x140007685  jz      short loc_14000769F
0x140007687  xor     r14d, r14d
0x14000768a  cmp     [rsi+48h], r14d
0x14000768e  jz      loc_140007752
0x140007694  mov     r14d, 80070032h
0x14000769a  jmp     loc_140007752
0x14000769f  lea     rdx, [rsi+20h]
0x1400076a3  test    rdx, rdx
0x1400076a6  jz      loc_140007747
0x1400076ac  mov     rax, [rsi+30h]
0x1400076b0  lea     r8, [rsi+38h]
0x1400076b4  test    rax, rax
0x1400076b7  jz      short loc_1400076C4
0x1400076b9  cmp     qword ptr [r8], 0
0x1400076bd  jz      short loc_1400076C4
0x1400076bf  xor     r14d, r14d
0x1400076c2  jmp     short loc_1400076CA
0x1400076c4  mov     r14d, 80004005h
0x1400076ca  test    r14d, r14d
0x1400076cd  js      loc_140007752
0x1400076d3  mov     r9, [rbp+80h]
0x1400076da  cmp     rax, rdx
0x1400076dd  jz      short loc_1400076FD
0x1400076df  mov     rcx, [r8]
0x1400076e2  cmp     rcx, rdx
0x1400076e5  jz      short loc_1400076FD
0x1400076e7  mov     [rax+18h], rcx
0x1400076eb  mov     rcx, [r8]
0x1400076ee  mov     rax, [rsi+30h]
0x1400076f2  mov     [rcx+10h], rax
0x1400076f6  mov     [rsi+30h], rdx
0x1400076fa  mov     [r8], rdx
0x1400076fd  mov     rax, [r9+10h]
0x140007701  xor     ecx, ecx
0x140007703  xor     r14d, r14d
0x140007706  mov     [rax+18h], rdx
0x14000770a  mov     rax, [r9+10h]
0x14000770e  mov     [rsi+30h], rax
0x140007712  mov     [r8], r9
0x140007715  mov     [r9+10h], rdx
0x140007719  mov     [rsi+50h], rbp
0x14000771d  mov     [rsi+44h], rcx
0x140007721  inc     dword ptr [rbp+0C8h]
0x140007727  mov     eax, [rsi+8]
0x14000772a  cmp     eax, 7FFFFFFFh
0x14000772f  jz      short loc_140007752
0x140007731  lea     ecx, [rax+1]
0x140007734  lock cmpxchg [rsi+8], ecx
0x140007739  jz      short loc_140007752
0x14000773b  mov     eax, [rsi+8]
0x14000773e  cmp     eax, 7FFFFFFFh
0x140007743  jnz     short loc_140007731
0x140007745  jmp     short loc_140007752
0x140007747  mov     r14d, edi
0x14000774a  jmp     short loc_140007752
0x14000774c  mov     r14d, 80004005h
0x140007752  add     dword ptr [rbp+54h], 0FFFFFFFFh
0x140007756  mov     eax, [rbp+54h]
0x140007759  jnz     short loc_140007762
0x14000775b  mov     dword ptr [rbp+50h], 0
0x140007762  lea     rcx, [rbp+28h]; lpCriticalSection
0x140007766  call    cs:__imp_LeaveCriticalSection
0x14000776d  nop     dword ptr [rax+rax+00h]
0x140007772  mov     rbx, [rsp+28h+arg_0]
0x140007777  test    r14d, r14d
0x14000777a  js      loc_140007850
0x140007780  mov     r8, [rsi+18h]
0x140007784  test    r8, r8
0x140007787  jz      short loc_140007796
0x140007789  mov     rax, [rbp+0E0h]
0x140007790  mov     [r8+8], rax
0x140007794  jmp     short loc_14000779A
0x140007796  mov     r8, [rbp+18h]; struct _TP_CALLBACK_ENVIRON_V3 *
0x14000779a  mov     ecx, [rsi+58h]
0x14000779d  test    ecx, ecx
0x14000779f  jz      short loc_1400077F6
0x1400077a1  sub     ecx, 1; this
0x1400077a4  jz      short loc_1400077EA
0x1400077a6  sub     ecx, 1; this
0x1400077a9  jz      short loc_1400077DE
0x1400077ab  sub     ecx, 1; this
0x1400077ae  jz      short loc_1400077D2
0x1400077b0  sub     ecx, 1; this
0x1400077b3  jz      short loc_1400077C6
0x1400077b5  cmp     ecx, 1
0x1400077b8  jnz     short loc_14000782D
0x1400077ba  mov     rdx, rsi; struct NThreadingLibrary::TLpcItem *
0x1400077bd  call    ?AddLpcItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTLpcItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddLpcItem(NThreadingLibrary::TLpcItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x1400077c2  mov     edi, eax
0x1400077c4  jmp     short loc_140007829
0x1400077c6  mov     rdx, rsi; struct NThreadingLibrary::TIOItem *
0x1400077c9  call    ?AddIOItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTIOItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddIOItem(NThreadingLibrary::TIOItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x1400077ce  mov     edi, eax
0x1400077d0  jmp     short loc_140007829
0x1400077d2  mov     rdx, rsi; struct NThreadingLibrary::TTimerItem *
0x1400077d5  call    ?AddTimerItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTTimerItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddTimerItem(NThreadingLibrary::TTimerItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x1400077da  mov     edi, eax
0x1400077dc  jmp     short loc_140007829
0x1400077de  mov     rdx, rsi; struct NThreadingLibrary::TWaitItem *
0x1400077e1  call    ?AddWaitItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWaitItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddWaitItem(NThreadingLibrary::TWaitItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x1400077e6  mov     edi, eax
0x1400077e8  jmp     short loc_140007829
0x1400077ea  mov     rdx, rsi; struct NThreadingLibrary::TQueuedItem *
0x1400077ed  call    ?AddWorkItem@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTQueuedItem@2@PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; NThreadingLibrary::TWorkCrew::AddWorkItem(NThreadingLibrary::TQueuedItem *,_TP_CALLBACK_ENVIRON_V3 *)
0x1400077f2  mov     edi, eax
0x1400077f4  jmp     short loc_140007829
0x1400077f6  mov     rdx, rsi
0x1400077f9  lea     rcx, ?tpSimpleCallback@TWorkCrew@NThreadingLibrary@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; NThreadingLibrary::TWorkCrew::tpSimpleCallback(_TP_CALLBACK_INSTANCE *,void *)
0x140007800  call    cs:__imp_TpSimpleTryPost
0x140007807  nop     dword ptr [rax+rax+00h]
0x14000780c  mov     ecx, eax; Status
0x14000780e  call    cs:__imp_RtlNtStatusToDosError
0x140007815  nop     dword ptr [rax+rax+00h]
0x14000781a  mov     edi, eax
0x14000781c  test    eax, eax
0x14000781e  jle     short loc_140007829
0x140007820  movzx   edi, ax
0x140007823  or      edi, 80070000h
0x140007829  test    edi, edi
0x14000782b  jns     short loc_140007838
0x14000782d  mov     rdx, rsi; struct NThreadingLibrary::TWorkItem *
0x140007830  mov     rcx, rbp; this
0x140007833  call    ?MoveWorkItemToCancelQueue@TWorkCrew@NThreadingLibrary@@AEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::MoveWorkItemToCancelQueue(NThreadingLibrary::TWorkItem *)
0x140007838  mov     eax, edi
0x14000783a  mov     r14, [rsp+28h+arg_8]
0x14000783f  mov     rbp, [rsp+28h+arg_10]
0x140007844  mov     rsi, [rsp+28h+arg_18]
0x140007849  add     rsp, 20h
0x14000784d  pop     rdi
0x14000784e  retn
0x140007850  mov     eax, r14d
0x140007853  jmp     short loc_14000783A
0x140007855  mov     rbp, [rsp+28h+arg_10]
0x14000785a  mov     eax, 80070057h
0x14000785f  mov     rsi, [rsp+28h+arg_18]
0x140007864  add     rsp, 20h
0x140007868  pop     rdi
0x140007869  retn
```
