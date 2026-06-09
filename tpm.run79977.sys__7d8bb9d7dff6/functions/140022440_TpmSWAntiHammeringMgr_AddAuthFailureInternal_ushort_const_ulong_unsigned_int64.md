# TpmSWAntiHammeringMgr::_AddAuthFailureInternal(ushort const *,ulong,unsigned __int64)

- ea: `0x140022440`
- end: `0x14002255f`
- name: `?_AddAuthFailureInternal@TpmSWAntiHammeringMgr@@AEAAJPEBGK_K@Z`
- size: `287`
- prototype: `int(TpmSWAntiHammeringMgr *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002215c`

## callees

- `0x14000e854`
- `0x1400134ec`
- `0x140022138`
- `0x1400222b8`
- `0x140022440`
- `0x140028dec`
- `0x140028ef0`

## import_xrefs

- `ntoskrnl!memmove_s` at `0x1400224f4`
- `ntoskrnl!memmove_s` at `0x1400224f4`

## pseudocode

```c
__int64 __fastcall TpmSWAntiHammeringMgr::_AddAuthFailureInternal(
        TpmSWAntiHammeringMgr *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int64 a4)
{
  TpmUserAuthFailureData *AuthFailureDataFromSid; // rax
  unsigned __int64 v9; // rcx
  TpmUserAuthFailureData *v10; // rbx
  _QWORD *v11; // rax
  TpmUserAuthFailureData *v12; // rcx
  _QWORD *v13; // rax
  unsigned int v14; // edx
  unsigned __int64 v15; // rcx
  int v16; // edi
  int v17; // esi
  __int64 v18; // rdx
  unsigned int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx

  AuthFailureDataFromSid = TpmSWAntiHammeringMgr::_GetAuthFailureDataFromSid(this, a2);
  v10 = AuthFailureDataFromSid;
  if ( AuthFailureDataFromSid )
  {
    v17 = 0;
    TpmUserAuthFailureData::AgeAuthFailureList(AuthFailureDataFromSid, a4, *((_DWORD *)this + 2));
  }
  else
  {
    v11 = TpmUserAuthFailureData::operator new(v9);
    v10 = (TpmUserAuthFailureData *)v11;
    if ( !v11 )
      return (unsigned int)-1073741670;
    *v11 = 0;
    v11[1] = 0;
    v11[2] = 0;
    v12 = (TpmUserAuthFailureData *)v11;
    v13 = v11 + 3;
    v13[1] = v13;
    *v13 = v13;
    v16 = TpmUserAuthFailureData::Initialize(v12, a2, a3);
    if ( v16 < 0 )
    {
      TpmRequest::`scalar deleting destructor'(v10, v14);
      return (unsigned int)v16;
    }
    v17 = 1;
  }
  v18 = *((unsigned int *)v10 + 4);
  v19 = *((_DWORD *)v10 + 5);
  if ( v19 == (_DWORD)v18 )
  {
    memmove_s(*((void **)v10 + 1), 8 * v18, (const void *)(*((_QWORD *)v10 + 1) + 8LL), 8LL * (unsigned int)(v18 - 1));
    v15 = (unsigned int)(*((_DWORD *)v10 + 5) - 1);
    *(_QWORD *)(*((_QWORD *)v10 + 1) + 8LL * (unsigned int)v15) = a4;
  }
  else if ( v19 < (unsigned int)v18 )
  {
    v15 = *((unsigned int *)v10 + 5);
    *(_QWORD *)(*((_QWORD *)v10 + 1) + 8 * v15) = a4;
    ++*((_DWORD *)v10 + 5);
  }
  v16 = 0;
  TpmSWAntiHammeringMgr::WriteUserAuthFailureData((TpmSWAntiHammeringMgr *)v15, v10);
  if ( v17 )
  {
    v20 = (_QWORD *)((char *)this + 16);
    v21 = *((_QWORD *)this + 2);
    if ( *(TpmSWAntiHammeringMgr **)(v21 + 8) != (TpmSWAntiHammeringMgr *)((char *)this + 16) )
      __fastfail(3u);
    *((_QWORD *)v10 + 3) = v21;
    *((_QWORD *)v10 + 4) = v20;
    *(_QWORD *)(v21 + 8) = (char *)v10 + 24;
    *v20 = (char *)v10 + 24;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140022440  push    rbx
0x140022442  push    rbp
0x140022443  push    rsi
0x140022444  push    rdi
0x140022445  push    r14
0x140022447  sub     rsp, 20h
0x14002244b  mov     r14, r9
0x14002244e  mov     esi, r8d
0x140022451  mov     rdi, rdx
0x140022454  mov     rbp, rcx
0x140022457  call    ?_GetAuthFailureDataFromSid@TpmSWAntiHammeringMgr@@AEAAPEAVTpmUserAuthFailureData@@PEBG@Z; TpmSWAntiHammeringMgr::_GetAuthFailureDataFromSid(ushort const *)
0x14002245c  mov     rbx, rax
0x14002245f  test    rax, rax
0x140022462  jnz     short loc_1400224C5
0x140022464  call    ??2TpmUserAuthFailureData@@SAPEAX_K@Z; TpmUserAuthFailureData::operator new(unsigned __int64)
0x140022469  mov     rbx, rax
0x14002246c  test    rax, rax
0x14002246f  jz      short loc_1400224BB
0x140022471  mov     qword ptr [rax], 0
0x140022478  mov     r8d, esi; unsigned int
0x14002247b  mov     qword ptr [rax+8], 0
0x140022483  mov     rdx, rdi; unsigned __int16 *
0x140022486  mov     qword ptr [rax+10h], 0
0x14002248e  mov     rcx, rbx; this
0x140022491  add     rax, 18h
0x140022495  mov     [rax+8], rax
0x140022499  mov     [rax], rax
0x14002249c  call    ?Initialize@TpmUserAuthFailureData@@QEAAJPEBGK@Z; TpmUserAuthFailureData::Initialize(ushort const *,ulong)
0x1400224a1  mov     edi, eax
0x1400224a3  test    eax, eax
0x1400224a5  js      short loc_1400224AE
0x1400224a7  mov     esi, 1
0x1400224ac  jmp     short loc_1400224D6
0x1400224ae  mov     rcx, rbx; this
0x1400224b1  call    ??_GTpmRequest@@QEAAPEAXI@Z; TpmRequest::`scalar deleting destructor'(uint)
0x1400224b6  jmp     loc_140022551
0x1400224bb  mov     edi, 0C000009Ah
0x1400224c0  jmp     loc_140022551
0x1400224c5  mov     r8d, [rbp+8]; unsigned int
0x1400224c9  xor     esi, esi
0x1400224cb  mov     rdx, r14; unsigned __int64
0x1400224ce  mov     rcx, rax; this
0x1400224d1  call    ?AgeAuthFailureList@TpmUserAuthFailureData@@QEAAK_KK@Z; TpmUserAuthFailureData::AgeAuthFailureList(unsigned __int64,ulong)
0x1400224d6  mov     edx, [rbx+10h]
0x1400224d9  mov     eax, [rbx+14h]
0x1400224dc  cmp     eax, edx
0x1400224de  jnz     short loc_14002250F
0x1400224e0  mov     rcx, [rbx+8]; void *
0x1400224e4  lea     r9d, [rdx-1]
0x1400224e8  shl     r9, 3; MaxCount
0x1400224ec  shl     rdx, 3; DstSize
0x1400224f0  lea     r8, [rcx+8]; Src
0x1400224f4  call    cs:__imp_memmove_s
0x1400224fb  nop     dword ptr [rax+rax+00h]
0x140022500  mov     ecx, [rbx+14h]
0x140022503  mov     rax, [rbx+8]
0x140022507  dec     ecx
0x140022509  mov     [rax+rcx*8], r14
0x14002250d  jmp     short loc_14002251F
0x14002250f  jnb     short loc_14002251F
0x140022511  mov     rcx, rax; this
0x140022514  mov     rax, [rbx+8]
0x140022518  mov     [rax+rcx*8], r14
0x14002251c  inc     dword ptr [rbx+14h]
0x14002251f  mov     rdx, rbx; struct TpmUserAuthFailureData *
0x140022522  xor     edi, edi
0x140022524  call    ?WriteUserAuthFailureData@TpmSWAntiHammeringMgr@@AEAAJPEAVTpmUserAuthFailureData@@@Z; TpmSWAntiHammeringMgr::WriteUserAuthFailureData(TpmUserAuthFailureData *)
0x140022529  test    esi, esi
0x14002252b  jz      short loc_140022551
0x14002252d  lea     rcx, [rbp+10h]
0x140022531  mov     rdx, [rcx]
0x140022534  cmp     [rdx+8], rcx
0x140022538  jz      short loc_14002253F
0x14002253a  lea     ecx, [rdi+3]
0x14002253d  int     29h; Win8: RtlFailFast(ecx)
0x14002253f  lea     rax, [rbx+18h]
0x140022543  mov     [rax], rdx
0x140022546  mov     [rax+8], rcx
0x14002254a  mov     [rdx+8], rax
0x14002254e  mov     [rcx], rax
0x140022551  mov     eax, edi
0x140022553  add     rsp, 20h
0x140022557  pop     r14
0x140022559  pop     rdi
0x14002255a  pop     rsi
0x14002255b  pop     rbp
0x14002255c  pop     rbx
0x14002255d  retn
```
