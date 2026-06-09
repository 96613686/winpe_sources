# CAttachmentServices::_OpZoneMarking(void)

- ea: `0x1800022f0`
- end: `0x180002604`
- name: `?_OpZoneMarking@CAttachmentServices@@AEAAXXZ`
- size: `788`
- prototype: `void __fastcall(CAttachmentServices *this, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d110`
- `0x1800113a0`
- `0x18001143c`

## callees

- `0x1800022f0`
- `0x180002610`
- `0x180004340`
- `0x1800115bc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002427`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002427`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAttachmentServices::_OpZoneMarking(CAttachmentServices *this, int a2)
{
  int v3; // r14d
  const unsigned __int16 *v4; // rdx
  void *v5; // rdi
  HRESULT v6; // esi
  bool v7; // zf
  __int64 v8; // rcx
  void *v9; // rcx
  __int64 v10; // rcx
  int v11; // ecx
  LPVOID v12; // rcx
  char *v13; // rdx
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF
  void *v15; // [rsp+68h] [rbp+38h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  if ( *((_DWORD *)this + 72) || *((_DWORD *)this + 73) || *((_DWORD *)this + 67) )
    return;
  if ( *((_DWORD *)this + 66) == 1 )
  {
    *((_DWORD *)this + 67) = 2;
    return;
  }
  *((_DWORD *)this + 67) = 1;
  v3 = *((_DWORD *)this + 75);
  *((_DWORD *)this + 75) = 10;
  if ( !*((_DWORD *)this + 2) || !*((_DWORD *)this + 4) )
  {
    LODWORD(ppv) = 0;
    v4 = (const unsigned __int16 *)*((_QWORD *)this + 6);
    if ( !v4 )
      v4 = (const unsigned __int16 *)*((_QWORD *)this + 7);
    CAttachmentServices::_ZoneCheck(this, v4, 0x1806u, (unsigned int *)&ppv);
    if ( !*((_DWORD *)this + 23) || !(_DWORD)ppv )
      goto LABEL_40;
    goto LABEL_14;
  }
  if ( *((_DWORD *)this + 5) )
  {
LABEL_14:
    ppv = 0;
    v15 = 0;
    if ( (int)ECFGetClassObject(
                this,
                a2,
                &CLSID_PersistentZoneIdentifier,
                &GUID_00000001_0000_0000_c000_000000000046,
                &v15) < 0 )
    {
      v6 = CoCreateInstance(&CLSID_PersistentZoneIdentifier, 0, 1u, &GUID_eb5e760c_09ef_45c0_b510_70830ce31e6a, &ppv);
    }
    else
    {
      v5 = v15;
      v6 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, LPVOID *))(*(_QWORD *)v15 + 24LL))(
             v15,
             0,
             &GUID_eb5e760c_09ef_45c0_b510_70830ce31e6a,
             &ppv);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v7 = v6 == 0;
    if ( v6 >= 0 )
    {
      v15 = 0;
      if ( (**(int (__fastcall ***)(LPVOID, GUID *, void **))ppv)(ppv, &GUID_31114b0a_accb_4e12_a053_754cb41c1d0f, &v15) < 0
        || (!*((_QWORD *)this + 6)
         || (v6 = (*(__int64 (__fastcall **)(void *, const wchar_t *))(*(_QWORD *)v15 + 48LL))(v15, L"HostUrl"), v6 >= 0))
        && (!*((_QWORD *)this + 7)
         || (v6 = (*(__int64 (__fastcall **)(void *, const wchar_t *))(*(_QWORD *)v15 + 48LL))(v15, L"ReferrerUrl"),
             v6 >= 0)) )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned int *)this + 23));
        if ( v6 >= 0 )
        {
          v16 = 0;
          v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                 ppv,
                 &GUID_0000010b_0000_0000_c000_000000000046,
                 &v16);
          if ( v6 >= 0 )
            v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v16 + 48LL))(
                   v16,
                   *((_QWORD *)this + 5),
                   1);
          v8 = v16;
          if ( v16 )
          {
            v16 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
        }
      }
      v9 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v7 = v6 == 0;
    }
    if ( !v7 )
    {
      v10 = 2LL * *((int *)this + 75);
      if ( !*((_DWORD *)this + 4 * *((int *)this + 75) + 25) || v6 == -2147023673 )
      {
        *((_DWORD *)this + 73) = v6;
        *((_DWORD *)this + 2 * v10 + 27) = 0;
      }
      else if ( v6 < 0 )
      {
        *((_DWORD *)this + 4 * *((int *)this + 75) + 27) = 3;
        v11 = *((_DWORD *)this + 75);
        if ( *((_DWORD *)this + 4 * v11 + 26) == 3 )
        {
          *((_DWORD *)this + 74) = 1;
          *((_DWORD *)this + 72) = v6;
          *((_DWORD *)this + 76) = v11;
        }
      }
    }
    v12 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
LABEL_40:
  v13 = (char *)this + 16 * *((int *)this + 75);
  if ( *((_DWORD *)v13 + 27) == 1 )
  {
    if ( *((_DWORD *)v13 + 25) && *((_DWORD *)this + 75) != 1 && (unsigned int)CAttachmentServices::Continuable(this) )
      *((_DWORD *)v13 + 27) = 4;
    else
      *((_DWORD *)v13 + 27) = 0;
  }
  *((_DWORD *)this + 75) = v3;
}

```

## disassembly

```asm
0x1800022f0  mov     [rsp-28h+arg_18], rbx
0x1800022f5  push    rbp
0x1800022f6  push    rsi
0x1800022f7  push    rdi
0x1800022f8  push    r14
0x1800022fa  push    r15
0x1800022fc  mov     rbp, rsp
0x1800022ff  sub     rsp, 30h
0x180002303  mov     rbx, rcx
0x180002306  cmp     dword ptr [rcx+120h], 0
0x18000230d  jnz     loc_1800025F3
0x180002313  cmp     dword ptr [rcx+124h], 0
0x18000231a  jnz     loc_1800025F3
0x180002320  cmp     dword ptr [rcx+10Ch], 0
0x180002327  jnz     loc_1800025F3
0x18000232d  cmp     dword ptr [rcx+108h], 1
0x180002334  jnz     short loc_180002345
0x180002336  mov     dword ptr [rcx+10Ch], 2
0x180002340  jmp     loc_1800025F3
0x180002345  mov     dword ptr [rcx+10Ch], 1
0x18000234f  mov     r14d, [rcx+12Ch]
0x180002356  mov     dword ptr [rcx+12Ch], 0Ah
0x180002360  xor     r15d, r15d
0x180002363  cmp     [rcx+8], r15d
0x180002367  jz      short loc_18000237B
0x180002369  cmp     [rcx+10h], r15d
0x18000236d  jz      short loc_18000237B
0x18000236f  cmp     [rcx+14h], r15d
0x180002373  jz      loc_1800025B1
0x180002379  jmp     short loc_1800023AF
0x18000237b  mov     dword ptr [rbp+arg_0], r15d
0x18000237f  mov     rdx, [rcx+30h]
0x180002383  test    rdx, rdx
0x180002386  jnz     short loc_18000238C
0x180002388  mov     rdx, [rcx+38h]; unsigned __int16 *
0x18000238c  lea     r9, [rbp+arg_0]; unsigned int *
0x180002390  mov     r8d, 1806h; unsigned int
0x180002396  call    ?_ZoneCheck@CAttachmentServices@@AEAAJPEBGKPEAK@Z; CAttachmentServices::_ZoneCheck(ushort const *,ulong,ulong *)
0x18000239b  cmp     [rbx+5Ch], r15d
0x18000239f  jz      loc_1800025B1
0x1800023a5  cmp     dword ptr [rbp+arg_0], r15d
0x1800023a9  jz      loc_1800025B1
0x1800023af  mov     [rbp+arg_0], r15
0x1800023b3  mov     [rbp+arg_8], r15
0x1800023b7  lea     rax, [rbp+arg_8]
0x1800023bb  mov     [rsp+30h+ppv], rax; void **
0x1800023c0  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; struct _GUID *
0x1800023c7  lea     r8, CLSID_PersistentZoneIdentifier; struct _GUID *
0x1800023ce  call    ?ECFGetClassObject@@YAJPEBUEASYCLASSFACTORY@@HAEBU_GUID@@1PEAPEAX@Z; ECFGetClassObject(EASYCLASSFACTORY const *,int,_GUID const &,_GUID const &,void * *)
0x1800023d3  xor     edx, edx; pUnkOuter
0x1800023d5  test    eax, eax
0x1800023d7  js      short loc_18000240A
0x1800023d9  mov     rdi, [rbp+arg_8]
0x1800023dd  mov     rax, [rdi]
0x1800023e0  lea     r9, [rbp+arg_0]
0x1800023e4  lea     r8, _GUID_eb5e760c_09ef_45c0_b510_70830ce31e6a
0x1800023eb  mov     rcx, rdi
0x1800023ee  mov     rax, [rax+18h]
0x1800023f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f7  mov     esi, eax
0x1800023f9  mov     rax, [rdi]
0x1800023fc  mov     rcx, rdi
0x1800023ff  mov     rax, [rax+10h]
0x180002403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002408  jmp     short loc_18000242F
0x18000240a  lea     rax, [rbp+arg_0]
0x18000240e  mov     [rsp+30h+ppv], rax; ppv
0x180002413  lea     r9, _GUID_eb5e760c_09ef_45c0_b510_70830ce31e6a; riid
0x18000241a  mov     r8d, 1; dwClsContext
0x180002420  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x180002427  call    cs:__imp_CoCreateInstance
0x18000242d  mov     esi, eax
0x18000242f  test    esi, esi
0x180002431  js      loc_180002539
0x180002437  mov     [rbp+arg_8], r15
0x18000243b  mov     rcx, [rbp+arg_0]
0x18000243f  mov     rax, [rcx]
0x180002442  lea     r8, [rbp+arg_8]
0x180002446  lea     rdx, _GUID_31114b0a_accb_4e12_a053_754cb41c1d0f
0x18000244d  mov     rax, [rax]
0x180002450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002455  nop
0x180002456  test    eax, eax
0x180002458  js      short loc_1800024AA
0x18000245a  mov     r8, [rbx+30h]
0x18000245e  test    r8, r8
0x180002461  jz      short loc_180002484
0x180002463  mov     rcx, [rbp+arg_8]
0x180002467  mov     rax, [rcx]
0x18000246a  lea     rdx, aHosturl_0; "HostUrl"
0x180002471  mov     rax, [rax+30h]
0x180002475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000247a  mov     esi, eax
0x18000247c  test    eax, eax
0x18000247e  js      loc_18000251D
0x180002484  mov     r8, [rbx+38h]
0x180002488  test    r8, r8
0x18000248b  jz      short loc_1800024AA
0x18000248d  mov     rcx, [rbp+arg_8]
0x180002491  mov     rax, [rcx]
0x180002494  lea     rdx, aReferrerurl_0; "ReferrerUrl"
0x18000249b  mov     rax, [rax+30h]
0x18000249f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a4  mov     esi, eax
0x1800024a6  test    eax, eax
0x1800024a8  js      short loc_18000251D
0x1800024aa  mov     rcx, [rbp+arg_0]
0x1800024ae  mov     rax, [rcx]
0x1800024b1  mov     edx, [rbx+5Ch]
0x1800024b4  mov     rax, [rax+20h]
0x1800024b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024bd  mov     esi, eax
0x1800024bf  test    eax, eax
0x1800024c1  js      short loc_18000251D
0x1800024c3  mov     [rbp+arg_10], r15
0x1800024c7  mov     rcx, [rbp+arg_0]
0x1800024cb  mov     rax, [rcx]
0x1800024ce  lea     r8, [rbp+arg_10]
0x1800024d2  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x1800024d9  mov     rax, [rax]
0x1800024dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024e1  mov     esi, eax
0x1800024e3  test    eax, eax
0x1800024e5  js      short loc_180002503
0x1800024e7  mov     rcx, [rbp+arg_10]
0x1800024eb  mov     rax, [rcx]
0x1800024ee  mov     r8d, 1
0x1800024f4  mov     rdx, [rbx+28h]
0x1800024f8  mov     rax, [rax+30h]
0x1800024fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002501  mov     esi, eax
0x180002503  mov     rcx, [rbp+arg_10]
0x180002507  test    rcx, rcx
0x18000250a  jz      short loc_18000251D
0x18000250c  mov     [rbp+arg_10], r15
0x180002510  mov     rax, [rcx]
0x180002513  mov     rax, [rax+10h]
0x180002517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000251c  nop
0x18000251d  mov     rcx, [rbp+arg_8]
0x180002521  test    rcx, rcx
0x180002524  jz      short loc_180002537
0x180002526  mov     [rbp+arg_8], r15
0x18000252a  mov     rax, [rcx]
0x18000252d  mov     rax, [rax+10h]
0x180002531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002536  nop
0x180002537  test    esi, esi
0x180002539  jz      short loc_180002597
0x18000253b  movsxd  rcx, dword ptr [rbx+12Ch]
0x180002542  add     rcx, rcx
0x180002545  cmp     dword ptr [rbx+rcx*8+64h], 0
0x18000254a  jz      short loc_18000258C
0x18000254c  cmp     esi, 800704C7h
0x180002552  jz      short loc_18000258C
0x180002554  test    esi, esi
0x180002556  jns     short loc_180002597
0x180002558  mov     dword ptr [rbx+rcx*8+6Ch], 3
0x180002560  movsxd  rcx, dword ptr [rbx+12Ch]
0x180002567  mov     rax, rcx
0x18000256a  add     rax, rax
0x18000256d  cmp     dword ptr [rbx+rax*8+68h], 3
0x180002572  jnz     short loc_180002597
0x180002574  mov     dword ptr [rbx+128h], 1
0x18000257e  mov     [rbx+120h], esi
0x180002584  mov     [rbx+130h], ecx
0x18000258a  jmp     short loc_180002597
0x18000258c  mov     [rbx+124h], esi
0x180002592  mov     [rbx+rcx*8+6Ch], r15d
0x180002597  mov     rcx, [rbp+arg_0]
0x18000259b  test    rcx, rcx
0x18000259e  jz      short loc_1800025B1
0x1800025a0  mov     [rbp+arg_0], r15
0x1800025a4  mov     rax, [rcx]
0x1800025a7  mov     rax, [rax+10h]
0x1800025ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b0  nop
0x1800025b1  movsxd  rcx, dword ptr [rbx+12Ch]
0x1800025b8  mov     rdx, rcx
0x1800025bb  shl     rdx, 4
0x1800025bf  add     rdx, rbx
0x1800025c2  cmp     dword ptr [rdx+6Ch], 1
0x1800025c6  jnz     short loc_1800025EC
0x1800025c8  cmp     dword ptr [rdx+64h], 0
0x1800025cc  jz      short loc_1800025E8
0x1800025ce  cmp     ecx, 1
0x1800025d1  jz      short loc_1800025E8
0x1800025d3  mov     rcx, rbx; this
0x1800025d6  call    ?Continuable@CAttachmentServices@@AEAAHXZ; CAttachmentServices::Continuable(void)
0x1800025db  test    eax, eax
0x1800025dd  jz      short loc_1800025E8
0x1800025df  mov     dword ptr [rdx+6Ch], 4
0x1800025e6  jmp     short loc_1800025EC
0x1800025e8  mov     [rdx+6Ch], r15d
0x1800025ec  mov     [rbx+12Ch], r14d
0x1800025f3  mov     rbx, [rsp+30h+arg_18]
0x1800025f8  add     rsp, 30h
0x1800025fc  pop     r15
0x1800025fe  pop     r14
0x180002600  pop     rdi
0x180002601  pop     rsi
0x180002602  pop     rbp
0x180002603  retn
```
