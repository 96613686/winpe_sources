# CompatibilityAdapter::ProcessJobStatus(void)

- ea: `0x180012594`
- end: `0x180012851`
- name: `?ProcessJobStatus@CompatibilityAdapter@@QEAAXXZ`
- size: `701`
- prototype: `void __fastcall(CompatibilityAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180012360`

## callees

- `0x1800057a0`
- `0x180007908`
- `0x180007988`
- `0x180011080`
- `0x180012594`
- `0x180012d48`
- `0x1800254fc`
- `0x1800267fc`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800125b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012621`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800126c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800126c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall CompatibilityAdapter::ProcessJobStatus(CompatibilityAdapter *this)
{
  __int64 v2; // rbx
  unsigned __int16 *v3; // rdi
  CompatibilityAdapter *v4; // rcx
  signed int v5; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  EventManager *v7; // rcx
  signed int v8; // esi
  CJob *v9; // r14
  int v10; // r12d
  int updated; // eax
  int v12; // edx
  __int16 v13; // ax
  __int16 v14; // ax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  EventManager *v16; // rcx
  struct CJob *v17; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v18; // [rsp+B8h] [rbp+20h]

  while ( 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( !*((_QWORD *)this + 9) )
      break;
    v2 = *(_QWORD *)(**((_QWORD **)this + 8) + 16LL);
    v18 = v2;
    if ( v2 )
      operator delete(0);
    std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::pop_front((char *)this + 64);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v3 = *(unsigned __int16 **)(v2 + 8);
    v17 = 0;
    v5 = CompatibilityAdapter::ActivateJob(v4, v3, &v17, 1);
    v8 = v5;
    if ( v5 >= 0 )
    {
      v9 = v17;
      v10 = *((_DWORD *)v17 + 22);
      switch ( *(_DWORD *)v2 )
      {
        case 1:
          updated = (*(__int64 (__fastcall **)(struct CJob *, _QWORD))(*(_QWORD *)v17 + 224LL))(v17, v10 | 4u);
          v8 = updated;
          break;
        case 3:
          updated = CJob::UpdateJobState(v17, 0);
          v8 = updated;
          if ( updated >= 0 )
          {
            v12 = *(_DWORD *)(v2 + 16);
            v13 = *((_WORD *)v9 + 33);
            if ( !v13 || (v14 = v13 - 1, (*((_WORD *)v9 + 33) = v14) == 0) )
              *((_DWORD *)v9 + 21) = (*((_DWORD *)v9 + 22) & 0x40000) != 0 ? 267015 : 267008;
            *((_DWORD *)v9 + 20) = v12;
            *((_DWORD *)v9 + 22) &= ~0x8000000u;
            v8 = 0;
            (*(void (__fastcall **)(CJob *, _QWORD))(*(_QWORD *)v9 + 224LL))(v9, v10 | 0x20000000u);
            updated = 0;
          }
          break;
        case 4:
          updated = CJob::UpdateJobState(v17, 1);
          v8 = updated;
          if ( updated >= 0 )
          {
            *((_DWORD *)v9 + 21) = 267009;
            *((_DWORD *)v9 + 22) &= ~0x80000u;
            *((_DWORD *)v9 + 48) = 0;
            *((_WORD *)v9 + 33) = 1;
            *((_OWORD *)v9 + 6) = *(_OWORD *)(v2 + 20);
          }
          break;
        default:
          SetLastError(0xA0u);
          updated = v8;
          break;
      }
      *((_DWORD *)v9 + 22) |= 0x20000000u;
      if ( updated >= 0 )
        v8 = CJob::SaveWithRetry(v9, 0, 0, 7u);
      wmi::AutoRef<CJob>::Release(&v17);
      if ( v8 < 0 )
        EventManager::EvtReport(v16, v15, v3, *(_DWORD *)v2, v8);
      operator delete(v3);
      operator delete((void *)v2);
    }
    else
    {
      EventManager::EvtReport(v7, v6, v3, *(_DWORD *)v2, v5);
      wmi::AutoRef<CJob>::Release(&v17);
      operator delete(v3);
      operator delete((void *)v2);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  operator delete(0);
}

```

## disassembly

```asm
0x180012594  mov     [rsp+arg_0], rcx
0x180012599  push    rbx
0x18001259a  push    rsi
0x18001259b  push    rdi
0x18001259c  push    r12
0x18001259e  push    r13
0x1800125a0  push    r14
0x1800125a2  push    r15
0x1800125a4  sub     rsp, 60h
0x1800125a8  mov     r13, rcx
0x1800125ab  xor     r15d, r15d
0x1800125ae  lea     r12d, [r15+1]
0x1800125b2  lea     rdi, [r13+18h]
0x1800125b6  mov     rcx, rdi; lpCriticalSection
0x1800125b9  call    cs:__imp_EnterCriticalSection
0x1800125c0  nop     dword ptr [rax+rax+00h]
0x1800125c5  cmp     [r13+48h], r15
0x1800125c9  jnz     short loc_1800125F1
0x1800125cb  mov     rcx, rdi; lpCriticalSection
0x1800125ce  call    cs:__imp_LeaveCriticalSection
0x1800125d5  nop     dword ptr [rax+rax+00h]
0x1800125da  nop
0x1800125db  xor     ecx, ecx; Block
0x1800125dd  add     rsp, 60h
0x1800125e1  pop     r15
0x1800125e3  pop     r14
0x1800125e5  pop     r13
0x1800125e7  pop     r12
0x1800125e9  pop     rdi
0x1800125ea  pop     rsi
0x1800125eb  pop     rbx
0x1800125ec  jmp     ??3@YAXPEAX@Z; operator delete(void *)
0x1800125f1  mov     rax, [r13+40h]
0x1800125f5  mov     rbx, [rax]
0x1800125f8  mov     rbx, [rbx+10h]
0x1800125fc  mov     [rsp+98h+arg_18], rbx
0x180012604  test    rbx, rbx
0x180012607  jz      short loc_180012610
0x180012609  xor     ecx, ecx; Block
0x18001260b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012610  mov     [rsp+98h+var_50], rbx
0x180012615  lea     rcx, [r13+40h]
0x180012619  call    ?pop_front@?$list@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAAXXZ; std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::pop_front(void)
0x18001261e  mov     rcx, rdi; lpCriticalSection
0x180012621  call    cs:__imp_LeaveCriticalSection
0x180012628  nop     dword ptr [rax+rax+00h]
0x18001262d  mov     rdi, [rbx+8]
0x180012631  mov     [rsp+98h+var_58], rdi
0x180012636  mov     [rsp+98h+var_48], rdi
0x18001263b  mov     [rsp+98h+arg_8], r15d
0x180012643  mov     [rsp+98h+arg_10], r15
0x18001264b  mov     r9d, r12d; int
0x18001264e  lea     r8, [rsp+98h+arg_10]; struct CJob **
0x180012656  mov     rdx, rdi; unsigned __int16 *
0x180012659  call    ?ActivateJob@CompatibilityAdapter@@QEAAJPEBGPEAPEAVCJob@@H@Z; CompatibilityAdapter::ActivateJob(ushort const *,CJob * *,int)
0x18001265e  mov     esi, eax
0x180012660  mov     [rsp+98h+arg_8], eax
0x180012667  test    eax, eax
0x180012669  jns     short loc_18001269F
0x18001266b  mov     [rsp+98h+var_78], eax; unsigned int
0x18001266f  mov     r9d, [rbx]; unsigned int
0x180012672  mov     r8, rdi; unsigned __int16 *
0x180012675  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x18001267a  nop
0x18001267b  lea     rcx, [rsp+98h+arg_10]
0x180012683  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x180012688  nop
0x180012689  mov     rcx, rdi; Block
0x18001268c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012691  nop
0x180012692  mov     rcx, rbx; Block
0x180012695  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001269a  jmp     loc_1800125B2
0x18001269f  mov     r14, [rsp+98h+arg_10]
0x1800126a7  mov     r12d, [r14+58h]
0x1800126ab  mov     ecx, [rbx]
0x1800126ad  sub     ecx, 1
0x1800126b0  jz      loc_1800127A6
0x1800126b6  sub     ecx, 2
0x1800126b9  jz      short loc_180012723
0x1800126bb  cmp     ecx, 1
0x1800126be  jz      short loc_1800126D8
0x1800126c0  mov     ecx, 0A0h; dwErrCode
0x1800126c5  call    cs:__imp_SetLastError
0x1800126cc  nop     dword ptr [rax+rax+00h]
0x1800126d1  mov     eax, esi
0x1800126d3  jmp     loc_1800127C8
0x1800126d8  mov     r12d, 1
0x1800126de  mov     edx, r12d; int
0x1800126e1  mov     rcx, r14; this
0x1800126e4  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x1800126e9  mov     esi, eax
0x1800126eb  mov     [rsp+98h+arg_8], eax
0x1800126f2  test    eax, eax
0x1800126f4  js      loc_1800127CE
0x1800126fa  mov     dword ptr [r14+54h], 41301h
0x180012702  btr     dword ptr [r14+58h], 13h
0x180012708  mov     [r14+0C0h], r15d
0x18001270f  mov     [r14+42h], r12w
0x180012714  movups  xmm0, xmmword ptr [rbx+14h]
0x180012718  movdqu  xmmword ptr [r14+60h], xmm0
0x18001271e  jmp     loc_1800127CE
0x180012723  xor     edx, edx; int
0x180012725  mov     rcx, r14; this
0x180012728  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x18001272d  mov     esi, eax
0x18001272f  mov     [rsp+98h+arg_8], eax
0x180012736  test    eax, eax
0x180012738  js      loc_1800127C8
0x18001273e  mov     edx, [rbx+10h]
0x180012741  movzx   eax, word ptr [r14+42h]
0x180012746  test    ax, ax
0x180012749  jz      short loc_180012758
0x18001274b  dec     ax
0x18001274e  mov     [r14+42h], ax
0x180012753  test    ax, ax
0x180012756  jnz     short loc_180012772
0x180012758  mov     eax, [r14+58h]
0x18001275c  and     eax, 40000h
0x180012761  neg     eax
0x180012763  sbb     ecx, ecx
0x180012765  and     ecx, 7
0x180012768  add     ecx, 41300h
0x18001276e  mov     [r14+54h], ecx
0x180012772  mov     [r14+50h], edx
0x180012776  btr     dword ptr [r14+58h], 1Bh
0x18001277c  mov     esi, r15d
0x18001277f  mov     [rsp+98h+arg_8], r15d
0x180012787  mov     rax, [r14]
0x18001278a  bts     r12d, 1Dh
0x18001278f  mov     edx, r12d
0x180012792  mov     rcx, r14
0x180012795  mov     rax, [rax+0E0h]
0x18001279c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127a1  mov     eax, r15d
0x1800127a4  jmp     short loc_1800127C8
0x1800127a6  mov     rax, [r14]
0x1800127a9  or      r12d, 4
0x1800127ad  mov     edx, r12d
0x1800127b0  mov     rcx, r14
0x1800127b3  mov     rax, [rax+0E0h]
0x1800127ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127bf  mov     esi, eax
0x1800127c1  mov     [rsp+98h+arg_8], eax
0x1800127c8  mov     r12d, 1
0x1800127ce  bts     dword ptr [r14+58h], 1Dh
0x1800127d4  test    eax, eax
0x1800127d6  js      short loc_1800127F4
0x1800127d8  mov     r9d, 7; unsigned int
0x1800127de  xor     r8d, r8d; int
0x1800127e1  xor     edx, edx; lpFileName
0x1800127e3  mov     rcx, r14; this
0x1800127e6  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x1800127eb  mov     esi, eax
0x1800127ed  mov     [rsp+98h+arg_8], eax
0x1800127f4  lea     rcx, [rsp+98h+arg_10]
0x1800127fc  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x180012801  nop
0x180012802  jmp     short loc_180012827
0x180012804  xor     r15d, r15d
0x180012807  lea     r12d, [r15+1]
0x18001280b  mov     r13, [rsp+98h+arg_0]
0x180012813  mov     esi, [rsp+98h+arg_8]
0x18001281a  mov     rbx, [rsp+98h+arg_18]
0x180012822  mov     rdi, [rsp+98h+var_58]
0x180012827  test    esi, esi
0x180012829  jns     short loc_18001283B
0x18001282b  mov     [rsp+98h+var_78], esi; unsigned int
0x18001282f  mov     r9d, [rbx]; unsigned int
0x180012832  mov     r8, rdi; unsigned __int16 *
0x180012835  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x18001283a  nop
0x18001283b  mov     rcx, rdi; Block
0x18001283e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012843  nop
0x180012844  mov     rcx, rbx; Block
0x180012847  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001284c  jmp     loc_1800125B2
```
