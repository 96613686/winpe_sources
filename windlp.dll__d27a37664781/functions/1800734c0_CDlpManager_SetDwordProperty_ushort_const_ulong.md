# CDlpManager::SetDwordProperty(ushort const *,ulong)

- ea: `0x1800734c0`
- end: `0x180073747`
- name: `?SetDwordProperty@CDlpManager@@UEAAJPEBGK@Z`
- size: `647`
- prototype: `int(CDlpManager *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x180047440`
- `0x180047c30`
- `0x1800734c0`
- `0x180081010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800735c0`
- `OLEAUT32!__imp_SysAllocString` at `0x1800735c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180073716`
- `OLEAUT32!__imp_SysFreeString` at `0x180073716`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800735ac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800735ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007350f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007350f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073727`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073727`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDlpManager::SetDwordProperty(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r13
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int RecursionCount; // esi
  int v11; // ebx
  __int64 v12; // r12
  OLECHAR *v13; // rax
  int v14; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-38h]
  __int64 cchCount2; // [rsp+28h] [rbp-30h]
  ULONG_PTR *p_SpinCount; // [rsp+38h] [rbp-20h]
  BSTR bstrString; // [rsp+A0h] [rbp+48h] BYREF

  p_SpinCount = &this[8].SpinCount;
  v6 = this + 9;
  EnterCriticalSection(this + 9);
  bstrString = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    if ( !(*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
      goto LABEL_24;
    v8 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
    v9 = 0;
    if ( !v8 )
      goto LABEL_23;
    LODWORD(cchCount2) = -2147024809;
    LODWORD(lpString2) = 1785;
    goto LABEL_21;
  }
  RecursionCount = this[14].RecursionCount;
  v11 = 0;
  if ( !RecursionCount )
  {
LABEL_8:
    v13 = SysAllocString(a2);
    if ( v13 )
    {
      bstrString = v13;
      v7 = CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(&this[14].LockCount, &bstrString);
      if ( v7 >= 0 )
      {
        v7 = CArray<unsigned long,unsigned long,CAdaptorDefault,CPoliciesDefault>::Append(&this[14].LockSemaphore, a3);
        if ( v7 >= 0 || !(*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
          goto LABEL_24;
        v8 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
        v9 = 0;
        if ( !v8 )
        {
LABEL_23:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
          goto LABEL_24;
        }
        LODWORD(cchCount2) = v7;
        LODWORD(lpString2) = 1811;
      }
      else
      {
        if ( !(*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
          goto LABEL_24;
        v8 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
        v9 = 0;
        if ( !v8 )
          goto LABEL_23;
        LODWORD(cchCount2) = v7;
        LODWORD(lpString2) = 1810;
      }
    }
    else
    {
      bstrString = 0;
      v7 = -2147024882;
      if ( !(*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount) )
        goto LABEL_24;
      v8 = (*(__int64 (__fastcall **)(ULONG_PTR *))(this[1].SpinCount + 16))(&this[1].SpinCount);
      v9 = 0;
      if ( !v8 )
        goto LABEL_23;
      LODWORD(cchCount2) = -2147024882;
      LODWORD(lpString2) = 1806;
    }
LABEL_21:
    v14 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v8,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpManager::SetDwordProperty",
            lpString2,
            cchCount2,
            &CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable',
            p_SpinCount);
    v9 = (unsigned int)v14;
    if ( v14 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
    goto LABEL_23;
  }
  while ( 1 )
  {
    v12 = v11;
    if ( CompareStringW(0x409u, 1u, a2, -1, *((PCNZWCH *)this[14].OwningThread + v11), -1) == 2 )
      break;
    if ( ++v11 >= RecursionCount )
      goto LABEL_8;
  }
  v7 = 0;
  *(_DWORD *)(this[14].SpinCount + 4 * v12) = a3;
LABEL_24:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( bstrString )
    SysFreeString(bstrString);
  LeaveCriticalSection(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800734c0  push    rbp
0x1800734c2  push    rbx
0x1800734c3  push    rsi
0x1800734c4  push    rdi
0x1800734c5  push    r12
0x1800734c7  push    r13
0x1800734c9  push    r14
0x1800734cb  push    r15
0x1800734cd  mov     rbp, rsp
0x1800734d0  sub     rsp, 58h
0x1800734d4  mov     r15d, r8d
0x1800734d7  mov     r14, rdx
0x1800734da  mov     rdi, rcx
0x1800734dd  mov     [rbp+var_10], 0
0x1800734e5  xorps   xmm0, xmm0
0x1800734e8  xor     eax, eax
0x1800734ea  movups  [rbp+var_28], xmm0
0x1800734ee  mov     [rbp+var_18], rax
0x1800734f2  lea     rax, [rcx+160h]
0x1800734f9  mov     qword ptr [rbp+var_28+8], rax
0x1800734fd  lea     rcx, ??_7?$CDlpAutoDelayLockT@V?$CDlpAutoExclusiveAcquireLockT@VCEmptyType@@@@@@6B@; const CDlpAutoDelayLockT<CDlpAutoExclusiveAcquireLockT<CEmptyType>>::`vftable'
0x180073504  mov     qword ptr [rbp+var_28], rcx
0x180073508  lea     r13, [rax+8]
0x18007350c  mov     rcx, r13; lpCriticalSection
0x18007350f  call    cs:__imp_EnterCriticalSection
0x180073515  mov     dword ptr [rbp+var_18], 1
0x18007351c  mov     [rbp+bstrString], 0
0x180073524  test    r14, r14
0x180073527  jnz     short loc_180073575
0x180073529  mov     ebx, 80070057h
0x18007352e  mov     rax, [rdi+48h]
0x180073532  lea     rcx, [rdi+48h]
0x180073536  mov     rax, [rax+10h]
0x18007353a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007353f  test    rax, rax
0x180073542  jz      loc_180073705
0x180073548  mov     rax, [rdi+48h]
0x18007354c  lea     rcx, [rdi+48h]
0x180073550  mov     rax, [rax+10h]
0x180073554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073559  xor     ecx, ecx
0x18007355b  test    rax, rax
0x18007355e  jz      loc_180073700
0x180073564  mov     dword ptr [rsp+58h+cchCount2], ebx
0x180073568  mov     dword ptr [rsp+58h+lpString2], 6F9h
0x180073570  jmp     loc_1800736DA
0x180073575  mov     esi, [rdi+23Ch]
0x18007357b  xor     ebx, ebx
0x18007357d  test    esi, esi
0x18007357f  jz      short loc_1800735BD
0x180073581  mov     rax, [rdi+240h]
0x180073588  movsxd  r12, ebx
0x18007358b  mov     rcx, [rax+r12*8]
0x18007358f  mov     dword ptr [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180073597  mov     [rsp+58h+lpString2], rcx; lpString2
0x18007359c  or      r9d, 0FFFFFFFFh; cchCount1
0x1800735a0  mov     r8, r14; lpString1
0x1800735a3  lea     edx, [r9+2]; dwCmpFlags
0x1800735a7  mov     ecx, 409h; Locale
0x1800735ac  call    cs:__imp_CompareStringW
0x1800735b2  cmp     eax, 2
0x1800735b5  jz      short loc_18007361B
0x1800735b7  inc     ebx
0x1800735b9  cmp     ebx, esi
0x1800735bb  jb      short loc_180073581
0x1800735bd  mov     rcx, r14; psz
0x1800735c0  call    cs:__imp_SysAllocString
0x1800735c6  test    rax, rax
0x1800735c9  jnz     short loc_18007362D
0x1800735cb  mov     [rbp+bstrString], rax
0x1800735cf  mov     ebx, 8007000Eh
0x1800735d4  mov     rax, [rdi+48h]
0x1800735d8  lea     rcx, [rdi+48h]
0x1800735dc  mov     rax, [rax+10h]
0x1800735e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735e5  test    rax, rax
0x1800735e8  jz      loc_180073705
0x1800735ee  mov     rax, [rdi+48h]
0x1800735f2  lea     rcx, [rdi+48h]
0x1800735f6  mov     rax, [rax+10h]
0x1800735fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735ff  xor     ecx, ecx
0x180073601  test    rax, rax
0x180073604  jz      loc_180073700
0x18007360a  mov     dword ptr [rsp+58h+cchCount2], ebx
0x18007360e  mov     dword ptr [rsp+58h+lpString2], 70Eh
0x180073616  jmp     loc_1800736DA
0x18007361b  xor     ebx, ebx
0x18007361d  mov     rax, [rdi+250h]
0x180073624  mov     [rax+r12*4], r15d
0x180073628  jmp     loc_180073705
0x18007362d  mov     [rbp+bstrString], rax
0x180073631  lea     rcx, [rdi+238h]
0x180073638  lea     rdx, [rbp+bstrString]
0x18007363c  call    ?Append@?$CArray@VDH_BSTR@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_BSTR@@@Z; CArray<DH_BSTR,DH_BSTR,CAdaptorDefault,CPoliciesDefault>::Append(DH_BSTR const &)
0x180073641  mov     ebx, eax
0x180073643  test    eax, eax
0x180073645  jns     short loc_18007368B
0x180073647  mov     rdx, [rdi+48h]
0x18007364b  lea     rcx, [rdi+48h]
0x18007364f  mov     rax, [rdx+10h]
0x180073653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073658  test    rax, rax
0x18007365b  jz      loc_180073705
0x180073661  mov     rax, [rdi+48h]
0x180073665  lea     rcx, [rdi+48h]
0x180073669  mov     rax, [rax+10h]
0x18007366d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073672  xor     ecx, ecx
0x180073674  test    rax, rax
0x180073677  jz      loc_180073700
0x18007367d  mov     dword ptr [rsp+58h+cchCount2], ebx
0x180073681  mov     dword ptr [rsp+58h+lpString2], 712h
0x180073689  jmp     short loc_1800736DA
0x18007368b  lea     rcx, [rdi+248h]
0x180073692  mov     edx, r15d
0x180073695  call    ?Append@?$CArray@KKVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJK@Z; CArray<ulong,ulong,CAdaptorDefault,CPoliciesDefault>::Append(ulong)
0x18007369a  mov     ebx, eax
0x18007369c  test    eax, eax
0x18007369e  jns     short loc_180073705
0x1800736a0  mov     rax, [rdi+48h]
0x1800736a4  lea     rcx, [rdi+48h]
0x1800736a8  mov     rax, [rax+10h]
0x1800736ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800736b1  test    rax, rax
0x1800736b4  jz      short loc_180073705
0x1800736b6  mov     rax, [rdi+48h]
0x1800736ba  lea     rcx, [rdi+48h]
0x1800736be  mov     rax, [rax+10h]
0x1800736c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800736c7  xor     ecx, ecx
0x1800736c9  test    rax, rax
0x1800736cc  jz      short loc_180073700
0x1800736ce  mov     dword ptr [rsp+58h+cchCount2], ebx
0x1800736d2  mov     dword ptr [rsp+58h+lpString2], 713h
0x1800736da  lea     r9, aCdlpmanagerSet_0; "CDlpManager::SetDwordProperty"
0x1800736e1  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800736e8  mov     edx, 4
0x1800736ed  mov     rcx, rax
0x1800736f0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800736f5  test    eax, eax
0x1800736f7  mov     ecx, eax
0x1800736f9  jns     short loc_180073700
0x1800736fb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180073700  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180073705  mov     ecx, ebx
0x180073707  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007370c  nop
0x18007370d  mov     rcx, [rbp+bstrString]; bstrString
0x180073711  test    rcx, rcx
0x180073714  jz      short loc_18007371D
0x180073716  call    cs:__imp_SysFreeString
0x18007371c  nop
0x18007371d  mov     eax, dword ptr [rbp+var_18]
0x180073720  test    eax, eax
0x180073722  jz      short loc_180073734
0x180073724  mov     rcx, r13; lpCriticalSection
0x180073727  call    cs:__imp_LeaveCriticalSection
0x18007372d  mov     dword ptr [rbp+var_18], 0
0x180073734  mov     eax, ebx
0x180073736  add     rsp, 58h
0x18007373a  pop     r15
0x18007373c  pop     r14
0x18007373e  pop     r13
0x180073740  pop     r12
0x180073742  pop     rdi
0x180073743  pop     rsi
0x180073744  pop     rbx
0x180073745  pop     rbp
0x180073746  retn
```
