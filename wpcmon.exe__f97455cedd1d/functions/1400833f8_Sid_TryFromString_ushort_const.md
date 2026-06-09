# Sid::TryFromString(ushort const *)

- ea: `0x1400833f8`
- end: `0x140083610`
- name: `?TryFromString@Sid@@SA?AV?$Optional@VSid@@@@PEBG@Z`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140082c2c`

## callees

- `0x140005530`
- `0x140006308`
- `0x14000ccac`
- `0x14002f828`
- `0x1400604d4`
- `0x14008273c`
- `0x1400833f8`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!CopySid` at `0x1400834ea`
- `ADVAPI32!CopySid` at `0x1400834ea`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140083478`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140083478`
- `KERNEL32!LocalFree` at `0x140083519`
- `KERNEL32!LocalFree` at `0x140083519`
- `KERNEL32!SetLastError` at `0x1400835e0`
- `KERNEL32!SetLastError` at `0x1400835e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Sid::TryFromString(__int64 a1, const WCHAR *a2)
{
  BOOL v4; // ebx
  _BYTE *v5; // rdx
  PSID v6; // rcx
  __int64 v7; // r8
  unsigned __int64 v8; // rdx
  void **v9; // rdi
  __int64 v10; // rbx
  PSID pSourceSid; // [rsp+20h] [rbp-E0h] BYREF
  PSID v13[3]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v14[9]; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD pDestinationSid[4]; // [rsp+90h] [rbp-70h] BYREF
  int v16; // [rsp+D0h] [rbp-30h]
  void *v17[2]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v18; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v19; // [rsp+F0h] [rbp-10h]
  PSID Sid; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v21[56]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE *v22; // [rsp+140h] [rbp+40h]

  v13[0] = (PSID)a1;
  if ( !a2 || !*a2 )
  {
    SetLastError(0x57u);
    *(_QWORD *)(a1 + 112) = 0;
    return a1;
  }
  pSourceSid = 0;
  v14[0] = &std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable';
  v14[1] = &pSourceSid;
  v14[7] = v14;
  stdext::GetPointer<void *>::GetPointer<void *>(&Sid, v14);
  v4 = ConvertStringSidToSidW(a2, &Sid);
  if ( v22 )
  {
    v13[0] = Sid;
    (*(void (__fastcall **)(_BYTE *, PSID *))(*(_QWORD *)v22 + 16LL))(v22, v13);
    if ( v22 )
    {
      v5 = v21;
      LOBYTE(v5) = v22 != v21;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v22 + 32LL))(v22, v5);
    }
  }
  if ( v4 )
  {
    Sid::Sid((Sid *)pDestinationSid);
    if ( !CopySid(0x44u, pDestinationSid, pSourceSid) )
    {
      *(_QWORD *)(a1 + 112) = 0;
      std::wstring::~wstring((char **)v17);
      v6 = pSourceSid;
      if ( !pSourceSid )
        return a1;
      goto LABEL_11;
    }
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    if ( v8 > v19 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v17, v8, v7, a2);
    }
    else
    {
      v9 = v17;
      if ( v19 > 7 )
        v9 = (void **)v17[0];
      v18 = v8;
      v10 = 2 * v8;
      memmove_0(v9, a2, 2 * v8);
      *(_WORD *)((char *)v9 + v10) = 0;
    }
    *(_OWORD *)(a1 + 8) = pDestinationSid[0];
    *(_OWORD *)(a1 + 24) = pDestinationSid[1];
    *(_OWORD *)(a1 + 40) = pDestinationSid[2];
    *(_OWORD *)(a1 + 56) = pDestinationSid[3];
    *(_DWORD *)(a1 + 72) = v16;
    *(void **)(a1 + 80) = v17[0];
    *(void **)(a1 + 88) = v17[1];
    *(_QWORD *)(a1 + 96) = v18;
    *(_QWORD *)(a1 + 104) = v19;
    v18 = 0;
    v19 = 7;
    LOWORD(v17[0]) = 0;
    *(_QWORD *)(a1 + 112) = a1 + 8;
    std::wstring::~wstring((char **)v17);
  }
  else
  {
    *(_QWORD *)(a1 + 112) = 0;
  }
  v6 = pSourceSid;
LABEL_11:
  if ( v6 )
    LocalFree(v6);
  return a1;
}

```

## disassembly

```asm
0x1400833f8  mov     [rsp-8+arg_10], rbx
0x1400833fd  push    rbp
0x1400833fe  push    rsi
0x1400833ff  push    rdi
0x140083400  push    r14
0x140083402  push    r15
0x140083404  lea     rbp, [rsp-60h]
0x140083409  sub     rsp, 160h
0x140083410  mov     rax, cs:__security_cookie
0x140083417  xor     rax, rsp
0x14008341a  mov     [rbp+80h+var_30], rax
0x14008341e  mov     r14, rdx
0x140083421  mov     rsi, rcx
0x140083424  mov     [rsp+180h+var_150], rcx
0x140083429  xor     r15d, r15d
0x14008342c  test    rdx, rdx
0x14008342f  jz      loc_1400835DB
0x140083435  cmp     [rdx], r15w
0x140083439  jz      loc_1400835DB
0x14008343f  mov     [rsp+180h+pSourceSid], r15
0x140083444  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1a0a9a37411416c90e606832c1826ed5_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable'
0x14008344b  mov     [rsp+180h+var_138], rax
0x140083450  lea     rax, [rsp+180h+pSourceSid]
0x140083455  mov     [rsp+180h+var_130], rax
0x14008345a  lea     rax, [rsp+180h+var_138]
0x14008345f  mov     [rbp+80h+var_100], rax
0x140083463  lea     rdx, [rsp+180h+var_138]
0x140083468  lea     rcx, [rbp+80h+Sid]
0x14008346c  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x140083471  lea     rdx, [rbp+80h+Sid]; Sid
0x140083475  mov     rcx, r14; StringSid
0x140083478  call    cs:__imp_ConvertStringSidToSidW
0x14008347e  mov     ebx, eax
0x140083480  mov     rcx, [rbp+80h+var_40]
0x140083484  test    rcx, rcx
0x140083487  jz      short loc_1400834C3
0x140083489  mov     rax, [rbp+80h+Sid]
0x14008348d  mov     [rsp+180h+var_150], rax
0x140083492  mov     rax, [rcx]
0x140083495  lea     rdx, [rsp+180h+var_150]
0x14008349a  mov     rax, [rax+10h]
0x14008349e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400834a3  mov     rcx, [rbp+80h+var_40]
0x1400834a7  test    rcx, rcx
0x1400834aa  jz      short loc_1400834C3
0x1400834ac  mov     rax, [rcx]
0x1400834af  lea     rdx, [rbp+80h+var_78]
0x1400834b3  cmp     rcx, rdx
0x1400834b6  setnz   dl
0x1400834b9  mov     rax, [rax+20h]
0x1400834bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400834c2  nop
0x1400834c3  test    ebx, ebx
0x1400834c5  jnz     short loc_1400834D2
0x1400834c7  mov     [rsi+70h], r15
0x1400834cb  mov     rcx, [rsp+180h+pSourceSid]
0x1400834d0  jmp     short loc_140083510
0x1400834d2  lea     rcx, [rbp+80h+pDestinationSid]; this
0x1400834d6  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x1400834db  nop
0x1400834dc  mov     r8, [rsp+180h+pSourceSid]; pSourceSid
0x1400834e1  lea     rdx, [rbp+80h+pDestinationSid]; pDestinationSid
0x1400834e5  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1400834ea  call    cs:__imp_CopySid
0x1400834f0  test    eax, eax
0x1400834f2  jnz     short loc_140083524
0x1400834f4  mov     [rsi+70h], r15
0x1400834f8  lea     rcx, [rbp+80h+var_A8]
0x1400834fc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140083501  nop
0x140083502  mov     rcx, [rsp+180h+pSourceSid]; hMem
0x140083507  test    rcx, rcx
0x14008350a  jz      loc_1400835EA
0x140083510  test    rcx, rcx
0x140083513  jz      loc_1400835EA
0x140083519  call    cs:__imp_LocalFree
0x14008351f  jmp     loc_1400835EA
0x140083524  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140083528  inc     rdx
0x14008352b  cmp     [r14+rdx*2], r15w
0x140083530  jnz     short loc_140083528
0x140083532  cmp     rdx, [rbp+80h+var_90]
0x140083536  ja      short loc_140083563
0x140083538  lea     rdi, [rbp+80h+var_A8]
0x14008353c  cmp     [rbp+80h+var_90], 7
0x140083541  cmova   rdi, [rbp+80h+var_A8]
0x140083546  mov     [rbp+80h+var_98], rdx
0x14008354a  lea     rbx, [rdx+rdx]
0x14008354e  mov     r8, rbx; Size
0x140083551  mov     rdx, r14; Src
0x140083554  mov     rcx, rdi; void *
0x140083557  call    memmove_0
0x14008355c  mov     [rbx+rdi], r15w
0x140083561  jmp     short loc_14008356F
0x140083563  mov     r9, r14
0x140083566  lea     rcx, [rbp+80h+var_A8]
0x14008356a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x14008356f  lea     rcx, [rsi+8]
0x140083573  movaps  xmm0, [rbp+80h+pDestinationSid]
0x140083577  movups  xmmword ptr [rcx], xmm0
0x14008357a  movaps  xmm1, [rbp+80h+var_E0]
0x14008357e  movups  xmmword ptr [rcx+10h], xmm1
0x140083582  movaps  xmm0, [rbp+80h+var_D0]
0x140083586  movups  xmmword ptr [rcx+20h], xmm0
0x14008358a  movaps  xmm1, [rbp+80h+var_C0]
0x14008358e  movups  xmmword ptr [rcx+30h], xmm1
0x140083592  mov     eax, [rbp+80h+var_B0]
0x140083595  mov     [rcx+40h], eax
0x140083598  mov     rax, [rbp+80h+var_A8]
0x14008359c  mov     [rcx+48h], rax
0x1400835a0  mov     rax, [rbp+80h+var_A0]
0x1400835a4  mov     [rcx+50h], rax
0x1400835a8  mov     rax, [rbp+80h+var_98]
0x1400835ac  mov     [rcx+58h], rax
0x1400835b0  mov     rax, [rbp+80h+var_90]
0x1400835b4  mov     [rcx+60h], rax
0x1400835b8  mov     [rbp+80h+var_98], r15
0x1400835bc  mov     [rbp+80h+var_90], 7
0x1400835c4  mov     word ptr [rbp+80h+var_A8], r15w
0x1400835c9  mov     [rsi+70h], rcx
0x1400835cd  lea     rcx, [rbp+80h+var_A8]
0x1400835d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400835d6  jmp     loc_1400834CB
0x1400835db  mov     ecx, 57h ; 'W'; dwErrCode
0x1400835e0  call    cs:__imp_SetLastError
0x1400835e6  mov     [rsi+70h], r15
0x1400835ea  mov     rax, rsi
0x1400835ed  mov     rcx, [rbp+80h+var_30]
0x1400835f1  xor     rcx, rsp; StackCookie
0x1400835f4  call    __security_check_cookie
0x1400835f9  mov     rbx, [rsp+180h+arg_10]
0x140083601  add     rsp, 160h
0x140083608  pop     r15
0x14008360a  pop     r14
0x14008360c  pop     rdi
0x14008360d  pop     rsi
0x14008360e  pop     rbp
0x14008360f  retn
```
