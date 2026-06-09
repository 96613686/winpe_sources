# PnPServices::_HandleInterfaceEvent(CServiceControlEvent *)

- ea: `0x1800023b0`
- end: `0x18000265c`
- name: `?_HandleInterfaceEvent@PnPServices@@YAJPEAVCServiceControlEvent@@@Z`
- size: `684`
- prototype: `__int64 __fastcall(PnPServices *__hidden this, struct CServiceControlEvent *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1800015f0`

## callees

- `0x1800014f0`
- `0x180001670`
- `0x180001a30`
- `0x1800023b0`
- `0x180003570`
- `0x18001b404`
- `0x180032c6a`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800024d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800025ef`

## pseudocode

```c
__int64 __fastcall PnPServices::_HandleInterfaceEvent(PnPServices *this, struct CServiceControlEvent *a2)
{
  __int64 v2; // r15
  _WORD *v4; // rbx
  char *v6; // rax
  char *v7; // r12
  _WORD *v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  _WORD *v11; // rcx
  unsigned int v12; // ebx
  CRefCounted *v13; // r13
  __int64 v14; // rdx
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  __int64 ValidHead; // rdi
  __int64 v17; // rbx
  CRefCounted *v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rax
  BOOL v21; // r14d
  __int64 v22; // rdx
  struct _RTL_CRITICAL_SECTION *v23; // rcx
  PnPServices::CInterfaceNotifBase *v24; // rbx
  __int64 v25; // rdx
  struct _RTL_CRITICAL_SECTION *v26; // rcx

  v2 = *((_QWORD *)this + 4);
  v4 = (_WORD *)(v2 + 28);
  if ( !*(_WORD *)(v2 + 28) || *((_DWORD *)this + 7) != 0x8000 && *((_DWORD *)this + 7) != 32772 )
    return 1;
  v6 = (char *)operator new(0x240u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  memset_0(v6 + 12, 0, 0x234u);
  *((_DWORD *)v7 + 2) = 1;
  *(_QWORD *)v7 = &PnPServices::CPnPInterfaceEvent::`vftable';
  v8 = v7 + 20;
  v9 = 2147483646;
  *((_DWORD *)v7 + 4) = *((_DWORD *)this + 7);
  v10 = 260;
  *(GUID *)(v7 + 540) = GUID_NULL;
  *(_OWORD *)(v7 + 556) = *(_OWORD *)(v2 + 12);
  do
  {
    if ( !v9 )
      break;
    if ( !*v4 )
      break;
    *v8++ = *v4++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v8 - 1;
  v12 = -2147024774;
  if ( v10 )
  {
    v11 = v8;
    v12 = 0;
  }
  *v11 = 0;
  if ( v10 )
  {
    CMostRecentEvents<PnPServices::CPnPInterfaceEvent,20>::Add(v11, v7);
    v13 = PnPServices::g_pnelInterfaceNotif;
    v14 = *((_QWORD *)PnPServices::g_pnelInterfaceNotif + 3);
    v15 = (struct _RTL_CRITICAL_SECTION *)(v14 + 8);
    if ( !v14 )
      v15 = 0;
    EnterCriticalSection(v15);
    ValidHead = CNamedElemList<PnPServices::CInterfaceNotif>::_GetValidHead((__int64)v13);
    v17 = ValidHead;
    v18 = 0;
    while ( 1 )
    {
      if ( !ValidHead || v18 )
      {
        if ( v18 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v18 + 2) + 8LL));
          v24 = (PnPServices::CInterfaceNotifBase *)*((_QWORD *)v18 + 2);
          CRefCounted::Release(v18);
          v25 = *((_QWORD *)v13 + 3);
          v26 = (struct _RTL_CRITICAL_SECTION *)(v25 + 8);
          if ( !v25 )
            v26 = 0;
          LeaveCriticalSection(v26);
          PnPServices::CInterfaceNotifBase::Callback(v24, (struct PnPServices::CPnPInterfaceEvent *)v7);
          CRefCounted::Release(v24);
          v12 = 0;
        }
        else
        {
          v22 = *((_QWORD *)v13 + 3);
          v23 = (struct _RTL_CRITICAL_SECTION *)(v22 + 8);
          if ( !v22 )
            v23 = 0;
          LeaveCriticalSection(v23);
          v12 = -2147467259;
        }
        goto LABEL_41;
      }
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(ValidHead + 16) + 8LL));
      v19 = *(_QWORD *)(ValidHead + 16);
      v20 = *(_QWORD *)(v2 + 12) - *(_QWORD *)(v19 + 88);
      if ( !v20 )
        v20 = *(_QWORD *)(v2 + 20) - *(_QWORD *)(v19 + 96);
      v21 = v20 == 0;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 8), 0xFFFFFFFF) == 1 && v19 )
        (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
      if ( v21 )
        break;
      ValidHead = *(_QWORD *)(ValidHead + 32);
      if ( ValidHead )
      {
        while ( !*(_QWORD *)(ValidHead + 16) )
        {
          ValidHead = *(_QWORD *)(ValidHead + 32);
          if ( !ValidHead )
            goto LABEL_26;
        }
        goto LABEL_25;
      }
LABEL_26:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 8), 0xFFFFFFFF) == 1 )
      {
        if ( v17 )
          (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
      }
      v17 = ValidHead;
    }
    v18 = (CRefCounted *)ValidHead;
LABEL_25:
    _InterlockedIncrement((volatile signed __int32 *)(ValidHead + 8));
    goto LABEL_26;
  }
LABEL_41:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(char *, __int64))v7)(v7, 1);
  return v12;
}

```

## disassembly

```asm
0x1800023b0  push    rbx
0x1800023b2  push    rdi
0x1800023b3  push    r15
0x1800023b5  sub     rsp, 30h
0x1800023b9  mov     r15, [rcx+20h]
0x1800023bd  mov     rdi, rcx
0x1800023c0  cmp     word ptr [r15+1Ch], 0
0x1800023c6  lea     rbx, [r15+1Ch]
0x1800023ca  jz      short loc_1800023DC
0x1800023cc  mov     edx, [rcx+1Ch]
0x1800023cf  sub     edx, 8000h
0x1800023d5  jz      short loc_1800023EA
0x1800023d7  cmp     edx, 4
0x1800023da  jz      short loc_1800023EA
0x1800023dc  mov     eax, 1
0x1800023e1  add     rsp, 30h
0x1800023e5  pop     r15
0x1800023e7  pop     rdi
0x1800023e8  pop     rbx
0x1800023e9  retn
0x1800023ea  mov     ecx, 240h; Size
0x1800023ef  mov     [rsp+48h+arg_18], r12
0x1800023f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800023f9  mov     r12, rax
0x1800023fc  test    rax, rax
0x1800023ff  jz      loc_180002649
0x180002405  lea     rcx, [rax+0Ch]; void *
0x180002409  mov     [rsp+48h+arg_8], rbp
0x18000240e  xor     edx, edx; Val
0x180002410  mov     r8d, 234h; Size
0x180002416  call    memset_0
0x18000241b  mov     dword ptr [r12+8], 1
0x180002424  lea     rax, ??_7CPnPInterfaceEvent@PnPServices@@6B@; const PnPServices::CPnPInterfaceEvent::`vftable'
0x18000242b  mov     [r12], rax
0x18000242f  lea     r8, [r12+14h]
0x180002434  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000243b  mov     eax, [rdi+1Ch]
0x18000243e  mov     ecx, 7FFFFFFEh
0x180002443  mov     [r12+10h], eax
0x180002448  mov     edx, 104h
0x18000244d  movups  xmmword ptr [r12+21Ch], xmm0
0x180002456  movups  xmm0, xmmword ptr [r15+0Ch]
0x18000245b  movups  xmmword ptr [r12+22Ch], xmm0
0x180002464  test    rcx, rcx
0x180002467  jz      short loc_180002486
0x180002469  movzx   eax, word ptr [rbx]
0x18000246c  test    ax, ax
0x18000246f  jz      short loc_180002486
0x180002471  mov     [r8], ax
0x180002475  add     rbx, 2
0x180002479  add     r8, 2
0x18000247d  dec     rcx
0x180002480  sub     rdx, 1
0x180002484  jnz     short loc_180002464
0x180002486  xor     eax, eax
0x180002488  lea     rcx, [r8-2]
0x18000248c  test    rdx, rdx
0x18000248f  mov     ebx, 8007007Ah
0x180002494  mov     ebp, 0FFFFFFFFh
0x180002499  cmovnz  rcx, r8
0x18000249d  cmovnz  ebx, eax
0x1800024a0  mov     [rcx], ax
0x1800024a3  jz      loc_180002614
0x1800024a9  mov     [rsp+48h+arg_10], rsi
0x1800024ae  mov     rdx, r12
0x1800024b1  mov     [rsp+48h+var_20], r13
0x1800024b6  call    ?Add@?$CMostRecentEvents@VCPnPInterfaceEvent@PnPServices@@$0BE@@@QEAAJPEAVCPnPInterfaceEvent@PnPServices@@@Z; CMostRecentEvents<PnPServices::CPnPInterfaceEvent,20>::Add(PnPServices::CPnPInterfaceEvent *)
0x1800024bb  mov     r13, cs:?g_pnelInterfaceNotif@PnPServices@@3PEAV?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@EA; CNamedElemList<PnPServices::CInterfaceNotif> * PnPServices::g_pnelInterfaceNotif
0x1800024c2  xor     eax, eax
0x1800024c4  mov     rdx, [r13+18h]
0x1800024c8  test    rdx, rdx
0x1800024cb  lea     rcx, [rdx+8]
0x1800024cf  cmovz   rcx, rax; lpCriticalSection
0x1800024d3  call    cs:__imp_EnterCriticalSection
0x1800024d9  mov     rcx, r13
0x1800024dc  call    ?_GetValidHead@?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@AEBAPEAV?$CElemSlot@VCInterfaceNotif@PnPServices@@@@XZ; CNamedElemList<PnPServices::CInterfaceNotif>::_GetValidHead(void)
0x1800024e1  mov     rdi, rax
0x1800024e4  mov     [rsp+48h+var_28], r14
0x1800024e9  mov     rbx, rax
0x1800024ec  xor     esi, esi
0x1800024ee  xchg    ax, ax
0x1800024f0  test    rdi, rdi
0x1800024f3  jz      loc_1800025A2
0x1800024f9  test    rsi, rsi
0x1800024fc  jnz     loc_1800025A2
0x180002502  mov     rcx, [rdi+10h]
0x180002506  lock inc dword ptr [rcx+8]
0x18000250a  mov     rcx, [rdi+10h]
0x18000250e  mov     rax, [r15+0Ch]
0x180002512  sub     rax, [rcx+58h]
0x180002516  jnz     short loc_180002520
0x180002518  mov     rax, [r15+14h]
0x18000251c  sub     rax, [rcx+60h]
0x180002520  xor     r14d, r14d
0x180002523  test    rax, rax
0x180002526  mov     eax, ebp
0x180002528  setz    r14b
0x18000252c  lock xadd [rcx+8], eax
0x180002531  cmp     eax, 1
0x180002534  jnz     short loc_18000254B
0x180002536  test    rcx, rcx
0x180002539  jz      short loc_18000254B
0x18000253b  mov     rax, [rcx]
0x18000253e  mov     edx, 1
0x180002543  mov     rax, [rax]
0x180002546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000254b  test    r14d, r14d
0x18000254e  jz      short loc_180002583
0x180002550  mov     rsi, rdi
0x180002553  lock inc dword ptr [rdi+8]
0x180002557  mov     eax, ebp
0x180002559  lock xadd [rbx+8], eax
0x18000255e  cmp     eax, 1
0x180002561  jnz     short loc_18000257B
0x180002563  test    rbx, rbx
0x180002566  jz      short loc_18000257B
0x180002568  mov     rax, [rbx]
0x18000256b  mov     edx, 1
0x180002570  mov     rcx, rbx
0x180002573  mov     rax, [rax]
0x180002576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257b  mov     rbx, rdi
0x18000257e  jmp     loc_1800024F0
0x180002583  mov     rdi, [rdi+20h]
0x180002587  test    rdi, rdi
0x18000258a  jz      short loc_180002557
0x18000258c  nop     dword ptr [rax+00h]
0x180002590  cmp     qword ptr [rdi+10h], 0
0x180002595  jnz     short loc_180002553
0x180002597  mov     rdi, [rdi+20h]
0x18000259b  test    rdi, rdi
0x18000259e  jnz     short loc_180002590
0x1800025a0  jmp     short loc_180002557
0x1800025a2  mov     r14, [rsp+48h+var_28]
0x1800025a7  test    rsi, rsi
0x1800025aa  jnz     short loc_1800025CA
0x1800025ac  mov     rdx, [r13+18h]
0x1800025b0  xor     eax, eax
0x1800025b2  test    rdx, rdx
0x1800025b5  lea     rcx, [rdx+8]
0x1800025b9  cmovz   rcx, rax; lpCriticalSection
0x1800025bd  call    cs:__imp_LeaveCriticalSection
0x1800025c3  mov     ebx, 80004005h
0x1800025c8  jmp     short loc_18000260A
0x1800025ca  mov     rax, [rsi+10h]
0x1800025ce  lock inc dword ptr [rax+8]
0x1800025d2  mov     rbx, [rsi+10h]
0x1800025d6  mov     rcx, rsi; this
0x1800025d9  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800025de  mov     rdx, [r13+18h]
0x1800025e2  xor     eax, eax
0x1800025e4  test    rdx, rdx
0x1800025e7  lea     rcx, [rdx+8]
0x1800025eb  cmovz   rcx, rax; lpCriticalSection
0x1800025ef  call    cs:__imp_LeaveCriticalSection
0x1800025f5  mov     rdx, r12; struct PnPServices::CPnPInterfaceEvent *
0x1800025f8  mov     rcx, rbx; this
0x1800025fb  call    ?Callback@CInterfaceNotifBase@PnPServices@@QEAAJPEAVCPnPInterfaceEvent@2@@Z; PnPServices::CInterfaceNotifBase::Callback(PnPServices::CPnPInterfaceEvent *)
0x180002600  mov     rcx, rbx; this
0x180002603  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002608  xor     ebx, ebx
0x18000260a  mov     rsi, [rsp+48h+arg_10]
0x18000260f  mov     r13, [rsp+48h+var_20]
0x180002614  lock xadd [r12+8], ebp
0x18000261b  cmp     ebp, 1
0x18000261e  mov     rbp, [rsp+48h+arg_8]
0x180002623  jnz     short loc_180002639
0x180002625  mov     rdx, [r12]
0x180002629  mov     rcx, r12
0x18000262c  mov     rax, [rdx]
0x18000262f  mov     edx, 1
0x180002634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002639  mov     r12, [rsp+48h+arg_18]
0x18000263e  mov     eax, ebx
0x180002640  add     rsp, 30h
0x180002644  pop     r15
0x180002646  pop     rdi
0x180002647  pop     rbx
0x180002648  retn
0x180002649  mov     r12, [rsp+48h+arg_18]
0x18000264e  mov     eax, 8007000Eh
0x180002653  add     rsp, 30h
0x180002657  pop     r15
0x180002659  pop     rdi
0x18000265a  pop     rbx
0x18000265b  retn
```
