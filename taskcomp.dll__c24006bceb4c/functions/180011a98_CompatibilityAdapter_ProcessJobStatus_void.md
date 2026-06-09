# CompatibilityAdapter::ProcessJobStatus(void)

- ea: `0x180011a98`
- end: `0x180011d3d`
- name: `?ProcessJobStatus@CompatibilityAdapter@@QEAAXXZ`
- size: `677`
- prototype: `void __fastcall(CompatibilityAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180011880`

## callees

- `0x1800054ec`
- `0x180007448`
- `0x1800074c8`
- `0x180010678`
- `0x180011a98`
- `0x180012214`
- `0x180023e5c`
- `0x180025090`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011abd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011abd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011acc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011acc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011bb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall CompatibilityAdapter::ProcessJobStatus(CompatibilityAdapter *this)
{
  unsigned int *v2; // rbx
  unsigned __int16 *v3; // rdi
  CompatibilityAdapter *v4; // rcx
  signed int v5; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rdx
  EventManager *v7; // rcx
  signed int v8; // esi
  CJob *v9; // r14
  int v10; // r12d
  int updated; // eax
  unsigned int v12; // edx
  __int16 v13; // ax
  __int16 v14; // ax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  EventManager *v16; // rcx
  struct CJob *v17; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int *v18; // [rsp+B8h] [rbp+20h]

  while ( 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( !*((_QWORD *)this + 9) )
      break;
    v2 = *(unsigned int **)(**((_QWORD **)this + 8) + 16LL);
    v18 = v2;
    if ( v2 )
      operator delete(0);
    std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::pop_front((char *)this + 64);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v3 = (unsigned __int16 *)*((_QWORD *)v2 + 1);
    v17 = 0;
    v5 = CompatibilityAdapter::ActivateJob(v4, v3, &v17, 1);
    v8 = v5;
    if ( v5 >= 0 )
    {
      v9 = v17;
      v10 = *((_DWORD *)v17 + 22);
      switch ( *v2 )
      {
        case 1u:
          updated = (*(__int64 (__fastcall **)(struct CJob *, _QWORD))(*(_QWORD *)v17 + 224LL))(v17, v10 | 4u);
          v8 = updated;
          break;
        case 3u:
          updated = CJob::UpdateJobState(v17, 0);
          v8 = updated;
          if ( updated >= 0 )
          {
            v12 = v2[4];
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
        case 4u:
          updated = CJob::UpdateJobState(v17, 1);
          v8 = updated;
          if ( updated >= 0 )
          {
            *((_DWORD *)v9 + 21) = 267009;
            *((_DWORD *)v9 + 22) &= ~0x80000u;
            *((_DWORD *)v9 + 48) = 0;
            *((_WORD *)v9 + 33) = 1;
            *((_OWORD *)v9 + 6) = *(_OWORD *)(v2 + 5);
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
        EventManager::EvtReport(v16, v15, v3, *v2, v8);
      operator delete(v3);
      operator delete(v2);
    }
    else
    {
      EventManager::EvtReport(v7, v6, v3, *v2, v5);
      wmi::AutoRef<CJob>::Release(&v17);
      operator delete(v3);
      operator delete(v2);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  operator delete(0);
}

```

## disassembly

```asm
0x180011a98  mov     [rsp+arg_0], rcx
0x180011a9d  push    rbx
0x180011a9e  push    rsi
0x180011a9f  push    rdi
0x180011aa0  push    r12
0x180011aa2  push    r13
0x180011aa4  push    r14
0x180011aa6  push    r15
0x180011aa8  sub     rsp, 60h
0x180011aac  mov     r13, rcx
0x180011aaf  xor     r15d, r15d
0x180011ab2  lea     r12d, [r15+1]
0x180011ab6  lea     rdi, [r13+18h]
0x180011aba  mov     rcx, rdi; lpCriticalSection
0x180011abd  call    cs:__imp_EnterCriticalSection
0x180011ac3  cmp     [r13+48h], r15
0x180011ac7  jnz     short loc_180011AE9
0x180011ac9  mov     rcx, rdi; lpCriticalSection
0x180011acc  call    cs:__imp_LeaveCriticalSection
0x180011ad2  nop
0x180011ad3  xor     ecx, ecx; Block
0x180011ad5  add     rsp, 60h
0x180011ad9  pop     r15
0x180011adb  pop     r14
0x180011add  pop     r13
0x180011adf  pop     r12
0x180011ae1  pop     rdi
0x180011ae2  pop     rsi
0x180011ae3  pop     rbx
0x180011ae4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
0x180011ae9  mov     rax, [r13+40h]
0x180011aed  mov     rbx, [rax]
0x180011af0  mov     rbx, [rbx+10h]
0x180011af4  mov     [rsp+98h+arg_18], rbx
0x180011afc  test    rbx, rbx
0x180011aff  jz      short loc_180011B08
0x180011b01  xor     ecx, ecx; Block
0x180011b03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011b08  mov     [rsp+98h+var_50], rbx
0x180011b0d  lea     rcx, [r13+40h]
0x180011b11  call    ?pop_front@?$list@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAAXXZ; std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::pop_front(void)
0x180011b16  mov     rcx, rdi; lpCriticalSection
0x180011b19  call    cs:__imp_LeaveCriticalSection
0x180011b1f  mov     rdi, [rbx+8]
0x180011b23  mov     [rsp+98h+var_58], rdi
0x180011b28  mov     [rsp+98h+var_48], rdi
0x180011b2d  mov     [rsp+98h+arg_8], r15d
0x180011b35  mov     [rsp+98h+arg_10], r15
0x180011b3d  mov     r9d, r12d; int
0x180011b40  lea     r8, [rsp+98h+arg_10]; struct CJob **
0x180011b48  mov     rdx, rdi; unsigned __int16 *
0x180011b4b  call    ?ActivateJob@CompatibilityAdapter@@QEAAJPEBGPEAPEAVCJob@@H@Z; CompatibilityAdapter::ActivateJob(ushort const *,CJob * *,int)
0x180011b50  mov     esi, eax
0x180011b52  mov     [rsp+98h+arg_8], eax
0x180011b59  test    eax, eax
0x180011b5b  jns     short loc_180011B91
0x180011b5d  mov     [rsp+98h+var_78], eax; unsigned int
0x180011b61  mov     r9d, [rbx]; unsigned int
0x180011b64  mov     r8, rdi; unsigned __int16 *
0x180011b67  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x180011b6c  nop
0x180011b6d  lea     rcx, [rsp+98h+arg_10]
0x180011b75  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x180011b7a  nop
0x180011b7b  mov     rcx, rdi; Block
0x180011b7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011b83  nop
0x180011b84  mov     rcx, rbx; Block
0x180011b87  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011b8c  jmp     loc_180011AB6
0x180011b91  mov     r14, [rsp+98h+arg_10]
0x180011b99  mov     r12d, [r14+58h]
0x180011b9d  mov     ecx, [rbx]
0x180011b9f  sub     ecx, 1
0x180011ba2  jz      loc_180011C92
0x180011ba8  sub     ecx, 2
0x180011bab  jz      short loc_180011C0F
0x180011bad  cmp     ecx, 1
0x180011bb0  jz      short loc_180011BC4
0x180011bb2  mov     ecx, 0A0h; dwErrCode
0x180011bb7  call    cs:__imp_SetLastError
0x180011bbd  mov     eax, esi
0x180011bbf  jmp     loc_180011CB4
0x180011bc4  mov     r12d, 1
0x180011bca  mov     edx, r12d; int
0x180011bcd  mov     rcx, r14; this
0x180011bd0  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x180011bd5  mov     esi, eax
0x180011bd7  mov     [rsp+98h+arg_8], eax
0x180011bde  test    eax, eax
0x180011be0  js      loc_180011CBA
0x180011be6  mov     dword ptr [r14+54h], 41301h
0x180011bee  btr     dword ptr [r14+58h], 13h
0x180011bf4  mov     [r14+0C0h], r15d
0x180011bfb  mov     [r14+42h], r12w
0x180011c00  movups  xmm0, xmmword ptr [rbx+14h]
0x180011c04  movdqu  xmmword ptr [r14+60h], xmm0
0x180011c0a  jmp     loc_180011CBA
0x180011c0f  xor     edx, edx; int
0x180011c11  mov     rcx, r14; this
0x180011c14  call    ?UpdateJobState@CJob@@QEAAJH@Z; CJob::UpdateJobState(int)
0x180011c19  mov     esi, eax
0x180011c1b  mov     [rsp+98h+arg_8], eax
0x180011c22  test    eax, eax
0x180011c24  js      loc_180011CB4
0x180011c2a  mov     edx, [rbx+10h]
0x180011c2d  movzx   eax, word ptr [r14+42h]
0x180011c32  test    ax, ax
0x180011c35  jz      short loc_180011C44
0x180011c37  dec     ax
0x180011c3a  mov     [r14+42h], ax
0x180011c3f  test    ax, ax
0x180011c42  jnz     short loc_180011C5E
0x180011c44  mov     eax, [r14+58h]
0x180011c48  and     eax, 40000h
0x180011c4d  neg     eax
0x180011c4f  sbb     ecx, ecx
0x180011c51  and     ecx, 7
0x180011c54  add     ecx, 41300h
0x180011c5a  mov     [r14+54h], ecx
0x180011c5e  mov     [r14+50h], edx
0x180011c62  btr     dword ptr [r14+58h], 1Bh
0x180011c68  mov     esi, r15d
0x180011c6b  mov     [rsp+98h+arg_8], r15d
0x180011c73  mov     rax, [r14]
0x180011c76  bts     r12d, 1Dh
0x180011c7b  mov     edx, r12d
0x180011c7e  mov     rcx, r14
0x180011c81  mov     rax, [rax+0E0h]
0x180011c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c8d  mov     eax, r15d
0x180011c90  jmp     short loc_180011CB4
0x180011c92  mov     rax, [r14]
0x180011c95  or      r12d, 4
0x180011c99  mov     edx, r12d
0x180011c9c  mov     rcx, r14
0x180011c9f  mov     rax, [rax+0E0h]
0x180011ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cab  mov     esi, eax
0x180011cad  mov     [rsp+98h+arg_8], eax
0x180011cb4  mov     r12d, 1
0x180011cba  bts     dword ptr [r14+58h], 1Dh
0x180011cc0  test    eax, eax
0x180011cc2  js      short loc_180011CE0
0x180011cc4  mov     r9d, 7; unsigned int
0x180011cca  xor     r8d, r8d; int
0x180011ccd  xor     edx, edx; lpFileName
0x180011ccf  mov     rcx, r14; this
0x180011cd2  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x180011cd7  mov     esi, eax
0x180011cd9  mov     [rsp+98h+arg_8], eax
0x180011ce0  lea     rcx, [rsp+98h+arg_10]
0x180011ce8  call    ?Release@?$AutoRef@VCJob@@@wmi@@QEAAXXZ; wmi::AutoRef<CJob>::Release(void)
0x180011ced  nop
0x180011cee  jmp     short loc_180011D13
0x180011cf0  xor     r15d, r15d
0x180011cf3  lea     r12d, [r15+1]
0x180011cf7  mov     r13, [rsp+98h+arg_0]
0x180011cff  mov     esi, [rsp+98h+arg_8]
0x180011d06  mov     rbx, [rsp+98h+arg_18]
0x180011d0e  mov     rdi, [rsp+98h+var_58]
0x180011d13  test    esi, esi
0x180011d15  jns     short loc_180011D27
0x180011d17  mov     [rsp+98h+var_78], esi; unsigned int
0x180011d1b  mov     r9d, [rbx]; unsigned int
0x180011d1e  mov     r8, rdi; unsigned __int16 *
0x180011d21  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,ulong,void *,_GUID const *)
0x180011d26  nop
0x180011d27  mov     rcx, rdi; Block
0x180011d2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011d2f  nop
0x180011d30  mov     rcx, rbx; Block
0x180011d33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011d38  jmp     loc_180011AB6
```
