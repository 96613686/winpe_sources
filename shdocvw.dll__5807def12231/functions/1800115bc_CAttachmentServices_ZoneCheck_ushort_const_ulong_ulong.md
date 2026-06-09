# CAttachmentServices::_ZoneCheck(ushort const *,ulong,ulong *)

- ea: `0x1800115bc`
- end: `0x180011762`
- name: `?_ZoneCheck@CAttachmentServices@@AEAAJPEBGKPEAK@Z`
- size: `422`
- prototype: `__int64 __fastcall(CAttachmentServices *this, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800022f0`
- `0x180011148`

## callees

- `0x1800068d8`
- `0x180006bd4`
- `0x180010084`
- `0x1800115bc`
- `0x180012224`

## import_xrefs

- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x1800116d3`
- `SHLWAPI!__imp_ZoneCheckUrlExW` at `0x1800116d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800115f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800115f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011703`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011703`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011749`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011749`

## pseudocode

```c
__int64 __fastcall CAttachmentServices::_ZoneCheck(
        CAttachmentServices *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  const wchar_t *v10; // rcx
  int v12; // ecx
  const unsigned __int16 *v13; // rdi
  int v14; // eax
  int v15; // eax
  struct IUnknown *v16; // rdx
  unsigned int v17; // r8d
  unsigned int v18; // ebp
  int v19; // [rsp+40h] [rbp-58h] BYREF
  RTL_SRWLOCK *v20; // [rsp+48h] [rbp-50h]
  RTL_SRWLOCK *v21; // [rsp+A0h] [rbp+8h] BYREF

  v8 = -1;
  if ( *((_DWORD *)this + 2) )
  {
    AcquireSRWLockShared(&CAttachmentServices::s_lastCheckedZonePathLock);
    v21 = &CAttachmentServices::s_lastCheckedZonePathLock;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = (const wchar_t *)&CAttachmentServices::s_lastCheckedZonePath;
    if ( *(&N + 1) > 7 )
      v10 = CAttachmentServices::s_lastCheckedZonePath;
    if ( N == v9 && (!N || !wmemcmp(v10, a2, N)) && CAttachmentServices::s_lastCheckedZoneAction == a3 )
    {
      *a4 = CAttachmentServices::s_lastCheckedZonePolicy;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v21);
      return 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v21);
  }
  v19 = 0;
  v12 = *((_DWORD *)this + 3) != 0 ? 1025 : 5121;
  v13 = L"about:untrusted";
  if ( a2 )
    v13 = a2;
  *a4 = 3;
  v14 = v12 | 0x100;
  if ( a2 )
    v14 = v12;
  v15 = ((__int64 (__fastcall *)(const unsigned __int16 *, unsigned int *, __int64, int *, int, unsigned int, int, _QWORD))ZoneCheckUrlExW)(
          v13,
          a4,
          4,
          &v19,
          4,
          a3,
          v14,
          0);
  v18 = v15;
  *a4 &= 0xFu;
  if ( *((_DWORD *)this + 2) && v15 >= 0 )
  {
    LODWORD(v21) = 0;
    SHMapUrlToZone(v13, v16, v17, (unsigned int *)&v21);
    AcquireSRWLockExclusive(&CAttachmentServices::s_lastCheckedZonePathLock);
    v20 = &CAttachmentServices::s_lastCheckedZonePathLock;
    do
      ++v8;
    while ( v13[v8] );
    std::wstring::_Assign<unsigned short>(&CAttachmentServices::s_lastCheckedZonePath, v13, v8);
    CAttachmentServices::s_lastCheckedZonePolicy = *a4;
    CAttachmentServices::s_lastCheckedZoneAction = a3;
    CAttachmentServices::s_lastCheckedZone = (unsigned int)v21;
    ReleaseSRWLockExclusive(&CAttachmentServices::s_lastCheckedZonePathLock);
  }
  return v18;
}

```

## disassembly

```asm
0x1800115bc  push    rbx
0x1800115be  push    rbp
0x1800115bf  push    rsi
0x1800115c0  push    rdi
0x1800115c1  push    r12
0x1800115c3  push    r13
0x1800115c5  push    r14
0x1800115c7  push    r15
0x1800115c9  sub     rsp, 58h
0x1800115cd  mov     rsi, r9
0x1800115d0  mov     r14d, r8d
0x1800115d3  mov     rbp, rdx
0x1800115d6  mov     r15, rcx
0x1800115d9  lea     r13, ?s_lastCheckedZonePathLock@CAttachmentServices@@0Vsrwlock@wil@@A; wil::srwlock CAttachmentServices::s_lastCheckedZonePathLock
0x1800115e0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800115e4  xor     r12d, r12d
0x1800115e7  cmp     [rcx+8], r12d
0x1800115eb  jz      loc_180011676
0x1800115f1  mov     rcx, r13; SRWLock
0x1800115f4  call    cs:__imp_AcquireSRWLockShared
0x1800115fa  mov     [rsp+98h+arg_0], r13
0x180011602  mov     rax, rbx
0x180011605  inc     rax
0x180011608  cmp     [rbp+rax*2+0], r12w
0x18001160e  jnz     short loc_180011605
0x180011610  mov     r8, qword ptr cs:N; N
0x180011617  lea     rcx, ?s_lastCheckedZonePath@CAttachmentServices@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CAttachmentServices::s_lastCheckedZonePath
0x18001161e  cmp     qword ptr cs:N+8, 7
0x180011626  cmova   rcx, cs:?s_lastCheckedZonePath@CAttachmentServices@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; S1
0x18001162e  cmp     r8, rax
0x180011631  jnz     short loc_180011669
0x180011633  test    r8, r8
0x180011636  jz      short loc_180011644
0x180011638  mov     rdx, rbp; S2
0x18001163b  call    wmemcmp
0x180011640  test    eax, eax
0x180011642  jnz     short loc_180011669
0x180011644  cmp     cs:?s_lastCheckedZoneAction@CAttachmentServices@@0KA, r14d; ulong CAttachmentServices::s_lastCheckedZoneAction
0x18001164b  jnz     short loc_180011669
0x18001164d  mov     eax, cs:?s_lastCheckedZonePolicy@CAttachmentServices@@0KA; ulong CAttachmentServices::s_lastCheckedZonePolicy
0x180011653  mov     [rsi], eax
0x180011655  lea     rcx, [rsp+98h+arg_0]
0x18001165d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011662  xor     eax, eax
0x180011664  jmp     loc_180011751
0x180011669  lea     rcx, [rsp+98h+arg_0]
0x180011671  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011676  mov     [rsp+98h+var_58], r12d
0x18001167b  mov     eax, [r15+0Ch]
0x18001167f  neg     eax
0x180011681  sbb     ecx, ecx
0x180011683  and     ecx, 0FFFFF000h
0x180011689  add     ecx, 1401h
0x18001168f  lea     rdi, aAboutUntrusted; "about:untrusted"
0x180011696  test    rbp, rbp
0x180011699  cmovnz  rdi, rbp
0x18001169d  mov     dword ptr [rsi], 3
0x1800116a3  mov     eax, ecx
0x1800116a5  bts     eax, 8
0x1800116a9  test    rbp, rbp
0x1800116ac  cmovnz  eax, ecx
0x1800116af  mov     [rsp+98h+var_60], r12
0x1800116b4  mov     [rsp+98h+var_68], eax
0x1800116b8  mov     [rsp+98h+var_70], r14d
0x1800116bd  mov     r8d, 4
0x1800116c3  mov     [rsp+98h+var_78], r8d
0x1800116c8  lea     r9, [rsp+98h+var_58]
0x1800116cd  mov     rdx, rsi
0x1800116d0  mov     rcx, rdi
0x1800116d3  call    cs:__imp_ZoneCheckUrlExW
0x1800116d9  mov     ebp, eax
0x1800116db  and     dword ptr [rsi], 0Fh
0x1800116de  cmp     [r15+8], r12d
0x1800116e2  jz      short loc_18001174F
0x1800116e4  test    eax, eax
0x1800116e6  js      short loc_18001174F
0x1800116e8  mov     dword ptr [rsp+98h+arg_0], r12d
0x1800116f0  lea     r9, [rsp+98h+arg_0]; unsigned int *
0x1800116f8  mov     rcx, rdi; unsigned __int16 *
0x1800116fb  call    ?SHMapUrlToZone@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZone(ushort const *,IUnknown *,ulong,ulong *)
0x180011700  mov     rcx, r13; SRWLock
0x180011703  call    cs:__imp_AcquireSRWLockExclusive
0x180011709  mov     [rsp+98h+var_50], r13
0x18001170e  inc     rbx
0x180011711  cmp     [rdi+rbx*2], r12w
0x180011716  jnz     short loc_18001170E
0x180011718  mov     r8, rbx
0x18001171b  mov     rdx, rdi
0x18001171e  lea     rcx, ?s_lastCheckedZonePath@CAttachmentServices@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring CAttachmentServices::s_lastCheckedZonePath
0x180011725  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001172a  mov     eax, [rsi]
0x18001172c  mov     cs:?s_lastCheckedZonePolicy@CAttachmentServices@@0KA, eax; ulong CAttachmentServices::s_lastCheckedZonePolicy
0x180011732  mov     cs:?s_lastCheckedZoneAction@CAttachmentServices@@0KA, r14d; ulong CAttachmentServices::s_lastCheckedZoneAction
0x180011739  mov     eax, dword ptr [rsp+98h+arg_0]
0x180011740  mov     cs:?s_lastCheckedZone@CAttachmentServices@@0KA, eax; ulong CAttachmentServices::s_lastCheckedZone
0x180011746  mov     rcx, r13; SRWLock
0x180011749  call    cs:__imp_ReleaseSRWLockExclusive
0x18001174f  mov     eax, ebp
0x180011751  add     rsp, 58h
0x180011755  pop     r15
0x180011757  pop     r14
0x180011759  pop     r13
0x18001175b  pop     r12
0x18001175d  pop     rdi
0x18001175e  pop     rsi
0x18001175f  pop     rbp
0x180011760  pop     rbx
0x180011761  retn
```
