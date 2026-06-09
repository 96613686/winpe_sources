# CImpITransactionLocal::StartTransaction(long,ulong,ITransactionOptions *,ulong *)

- ea: `0x383a50390`
- end: `0x383a50864`
- name: `?StartTransaction@CImpITransactionLocal@@UEAAJJKPEAUITransactionOptions@@PEAK@Z`
- size: `1236`
- prototype: `int(CImpITransactionLocal *__hidden this, int, unsigned int, struct ITransactionOptions *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x3838435e0`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x38391afe0`
- `0x3839bd220`
- `0x3839bd770`
- `0x3839d26f0`
- `0x383a50390`
- `0x383a9f290`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x383a504c8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a504c8`
- `RPCRT4!UuidCreate` at `0x383a50668`
- `RPCRT4!UuidCreate` at `0x383a50668`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CImpITransactionLocal::StartTransaction(
        CImpITransactionLocal *this,
        unsigned __int64 a2,
        int a3,
        struct ITransactionOptions *a4,
        unsigned int *a5)
{
  int v7; // r15d
  __int64 v9; // rbx
  __int64 v10; // rbp
  const struct _GUID *v11; // r8
  int inited; // ebx
  char *v13; // rcx
  __int64 v14; // rdx
  const struct _GUID *v15; // r8
  RPC_STATUS v16; // eax
  const struct _GUID *v17; // r8
  struct CErrorData *v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // eax
  void *v21; // rcx
  __int64 v22; // rcx
  __int64 v24; // [rsp+40h] [rbp-148h] BYREF
  __int64 v25; // [rsp+48h] [rbp-140h]
  __int64 v26; // [rsp+50h] [rbp-138h]
  __int64 v27; // [rsp+58h] [rbp-130h]
  UUID Uuid; // [rsp+60h] [rbp-128h] BYREF
  _DWORD Src[12]; // [rsp+70h] [rbp-118h] BYREF
  unsigned __int16 v30[80]; // [rsp+A0h] [rbp-E8h] BYREF

  v27 = -2;
  v7 = a2;
  v24 = -1;
  if ( (bidGblFlags & 4) != 0 && off_383B4ABA8[0] )
    bidScopeEnterW(&v24, off_383B4ABA8[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), (unsigned int)a2);
  if ( (bidGblFlags & 0x40002) == 0x40002
    && (unsigned int)ConstrBidActID(v30, a2)
    && (bidGblFlags & 2) != 0
    && off_383B49C18[0] )
  {
    bidTraceW(off_383B433E8[0], 391168, off_383B49C18[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL));
  }
  v9 = *((_QWORD *)this + 1);
  v10 = *(_QWORD *)(v9 + 840);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v9 + 24) + 32LL) + 8LL))(*(_QWORD *)(v9 + 24) + 32LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v10 + 88) + 32LL) + 8LL))(*(_QWORD *)(v10 + 88) + 32LL);
  v25 = *(_QWORD *)(v9 + 24);
  v26 = *(_QWORD *)(v10 + 88);
  SetErrorInfo(0, 0);
  if ( a3 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B433E8[0], 406569, off_383B49128[0], 2147799051LL);
    inited = CError::PostHResult((CError *)0x8004D00BLL, (int)&IID_ITransactionLocal, v11);
    goto LABEL_52;
  }
  if ( a5 )
    *a5 = 1;
  if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 848LL) & 9) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B433E8[0], 419881, off_383B49128[0], 2147799059LL);
    inited = CError::PostHResult((CError *)0x8004D013LL, (int)&IID_ITransactionLocal, v11);
    goto LABEL_52;
  }
  if ( *(_QWORD *)(v10 + 72) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_26;
    v13 = off_383B433E8[0];
    if ( !off_383B49128[0] )
      goto LABEL_26;
    v14 = 432169;
LABEL_25:
    bidTraceW(v13, v14, off_383B49128[0], 2147799069LL);
LABEL_26:
    inited = CError::PostHResult((CError *)0x8004D01DLL, (int)&IID_ITransactionLocal, v11);
    goto LABEL_52;
  }
  if ( !a4 )
    goto LABEL_34;
  inited = ((__int64 (__fastcall *)(struct ITransactionOptions *, _DWORD *))a4->lpVtbl->GetOptions)(a4, Src);
  if ( inited < 0 )
    goto LABEL_52;
  if ( Src[0] )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B433E8[0], 451625, off_383B49128[0], 2147799063LL);
    inited = CError::PostHResult((CError *)0x8004D017LL, (int)&IID_ITransactionLocal, v15);
  }
  else
  {
LABEL_34:
    v16 = UuidCreate(&Uuid);
    if ( v16 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_26;
      bidTraceHR(off_383B433E8[0], 463881, (unsigned int)v16);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_26;
      v13 = off_383B433E8[0];
      if ( !off_383B49128[0] )
        goto LABEL_26;
      v14 = 464937;
      goto LABEL_25;
    }
    inited = CDBConnection::InitLocalXactMode((CDBConnection *)v10, v7);
    if ( inited >= 0 )
    {
      *(_DWORD *)(*((_QWORD *)this + 1) + 848LL) |= 1u;
      *(_DWORD *)(*((_QWORD *)this + 1) + 872LL) = v7;
      *(UUID *)(*((_QWORD *)this + 1) + 856LL) = Uuid;
      v21 = (void *)(*((_QWORD *)this + 1) + 896LL);
      if ( a4 )
        memcpy(v21, Src, 0x2Cu);
      else
        memset(v21, 0, 0x2Cu);
      inited = 0;
    }
    else
    {
      v19 = -2147467259;
      if ( inited == -2147467259 )
      {
        if ( (bidGblFlags & 2) != 0 )
          v19 = bidTraceHR(off_383B433E8[0], 473097, 2147500037LL);
        CError::PostSqlErrors((CError *)v19, (int)&IID_ITransactionLocal, (const struct _GUID *)(v10 + 136), v18);
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 )
          v20 = bidTraceHR(off_383B433E8[0], 477193, (unsigned int)inited);
        else
          v20 = inited;
        CError::PostHResult((CError *)v20, (int)&IID_ITransactionLocal, v17);
      }
    }
  }
LABEL_52:
  if ( (bidGblFlags & 2) != 0 && off_383B49C10[0] )
    bidTraceW(off_383B433E8[0], 507904, off_383B49C10[0], (unsigned int)inited);
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v26 + 32) + 24LL))(v26 + 32);
    v22 = v25;
LABEL_58:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v22 + 32) + 24LL))(v22 + 32);
    goto LABEL_59;
  }
  v22 = v25;
  if ( v25 )
    goto LABEL_58;
LABEL_59:
  if ( v24 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x383a50390  push    rbx
0x383a50392  push    rbp
0x383a50393  push    rsi
0x383a50394  push    rdi
0x383a50395  push    r12
0x383a50397  push    r14
0x383a50399  push    r15
0x383a5039b  sub     rsp, 150h
0x383a503a2  mov     [rsp+188h+var_130], 0FFFFFFFFFFFFFFFEh
0x383a503ab  mov     rax, cs:__security_cookie
0x383a503b2  xor     rax, rsp
0x383a503b5  mov     [rsp+188h+var_48], rax
0x383a503bd  mov     rsi, r9
0x383a503c0  mov     r12d, r8d
0x383a503c3  mov     r15d, edx
0x383a503c6  mov     rdi, rcx
0x383a503c9  mov     r14, [rsp+188h+arg_20]
0x383a503d1  mov     [rsp+188h+var_148], 0FFFFFFFFFFFFFFFFh
0x383a503da  test    byte ptr cs:_bidGblFlags, 4
0x383a503e1  jz      short loc_383A5041A
0x383a503e3  mov     rax, cs:off_383B4ABA8; "<ITransactionLocal::StartTransaction|OL"...
0x383a503ea  test    rax, rax
0x383a503ed  jz      short loc_383A5041A
0x383a503ef  mov     rax, [rcx+8]
0x383a503f3  mov     [rsp+188h+var_158], r14
0x383a503f8  mov     [rsp+188h+var_160], r9
0x383a503fd  mov     dword ptr [rsp+188h+var_168], r8d
0x383a50402  mov     r9d, edx
0x383a50405  mov     r8d, [rax+34h]
0x383a50409  mov     rdx, cs:off_383B4ABA8; "<ITransactionLocal::StartTransaction|OL"...
0x383a50410  lea     rcx, [rsp+188h+var_148]
0x383a50415  call    _bidScopeEnterW
0x383a5041a  mov     eax, cs:_bidGblFlags
0x383a50420  and     eax, 40002h
0x383a50425  cmp     eax, 40002h
0x383a5042a  jnz     short loc_383A5048B
0x383a5042c  lea     rcx, [rsp+188h+var_E8]; unsigned __int16 *
0x383a50434  call    ?ConstrBidActID@@YAHPEAG_K@Z; ConstrBidActID(ushort *,unsigned __int64)
0x383a50439  test    eax, eax
0x383a5043b  jz      short loc_383A5048B
0x383a5043d  test    byte ptr cs:_bidGblFlags, 2
0x383a50444  jz      short loc_383A5048B
0x383a50446  mov     rax, cs:off_383B49C18; "<CImpITransactionLocal::StartTransactio"...
0x383a5044d  test    rax, rax
0x383a50450  jz      short loc_383A5048B
0x383a50452  mov     rax, [rdi+8]
0x383a50456  lea     rcx, [rsp+188h+var_E8]
0x383a5045e  mov     [rsp+188h+var_160], rcx
0x383a50463  lea     rcx, aSession; "Session"
0x383a5046a  mov     [rsp+188h+var_168], rcx
0x383a5046f  mov     r9d, [rax+34h]
0x383a50473  mov     r8, cs:off_383B49C18; "<CImpITransactionLocal::StartTransactio"...
0x383a5047a  mov     edx, 5F800h
0x383a5047f  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50486  call    _bidTraceW
0x383a5048b  mov     rbx, [rdi+8]
0x383a5048f  mov     rbp, [rbx+348h]
0x383a50496  mov     rcx, [rbx+18h]
0x383a5049a  add     rcx, 20h ; ' '
0x383a5049e  mov     rax, [rcx]
0x383a504a1  call    qword ptr [rax+8]
0x383a504a4  mov     rcx, [rbp+58h]
0x383a504a8  add     rcx, 20h ; ' '
0x383a504ac  mov     rax, [rcx]
0x383a504af  call    qword ptr [rax+8]
0x383a504b2  mov     r11, [rbx+18h]
0x383a504b6  mov     [rsp+188h+var_140], r11
0x383a504bb  mov     rax, [rbp+58h]
0x383a504bf  mov     [rsp+188h+var_138], rax
0x383a504c4  xor     edx, edx; perrinfo
0x383a504c6  xor     ecx, ecx; dwReserved
0x383a504c8  call    cs:__imp_SetErrorInfo
0x383a504ce  test    r12d, r12d
0x383a504d1  jz      short loc_383A50526
0x383a504d3  test    byte ptr cs:_bidGblFlags, 2
0x383a504da  jz      short loc_383A5050E
0x383a504dc  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a504e3  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a504ea  test    rax, rax
0x383a504ed  jz      short loc_383A5050E
0x383a504ef  mov     dword ptr [rsp+188h+var_168], 18Dh
0x383a504f7  mov     r9d, 8004D00Bh
0x383a504fd  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50504  mov     edx, 63429h
0x383a50509  call    _bidTraceW
0x383a5050e  lea     rdx, IID_ITransactionLocal; int
0x383a50515  mov     ecx, 8004D00Bh; this
0x383a5051a  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a5051f  mov     ebx, eax
0x383a50521  jmp     loc_383A507AC
0x383a50526  test    r14, r14
0x383a50529  jz      short loc_383A50532
0x383a5052b  mov     dword ptr [r14], 1
0x383a50532  mov     rax, [rdi+8]
0x383a50536  test    byte ptr [rax+350h], 9
0x383a5053d  jz      short loc_383A50592
0x383a5053f  test    byte ptr cs:_bidGblFlags, 2
0x383a50546  jz      short loc_383A5057A
0x383a50548  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a5054f  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50556  test    rax, rax
0x383a50559  jz      short loc_383A5057A
0x383a5055b  mov     dword ptr [rsp+188h+var_168], 19Ah
0x383a50563  mov     r9d, 8004D013h
0x383a50569  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50570  mov     edx, 66829h
0x383a50575  call    _bidTraceW
0x383a5057a  lea     rdx, IID_ITransactionLocal; int
0x383a50581  mov     ecx, 8004D013h; this
0x383a50586  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a5058b  mov     ebx, eax
0x383a5058d  jmp     loc_383A507AC
0x383a50592  cmp     qword ptr [rbp+48h], 0
0x383a50597  jz      short loc_383A505EC
0x383a50599  test    byte ptr cs:_bidGblFlags, 2
0x383a505a0  jz      short loc_383A505D4
0x383a505a2  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a505a9  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a505b0  test    rax, rax
0x383a505b3  jz      short loc_383A505D4
0x383a505b5  mov     dword ptr [rsp+188h+var_168], 1A6h
0x383a505bd  mov     edx, 69829h
0x383a505c2  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a505c9  mov     r9d, 8004D01Dh
0x383a505cf  call    _bidTraceW
0x383a505d4  lea     rdx, IID_ITransactionLocal; int
0x383a505db  mov     ecx, 8004D01Dh; this
0x383a505e0  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a505e5  mov     ebx, eax
0x383a505e7  jmp     loc_383A507AC
0x383a505ec  test    rsi, rsi
0x383a505ef  jz      short loc_383A50663
0x383a505f1  mov     rax, [rsi]
0x383a505f4  lea     rdx, [rsp+188h+Src]
0x383a505f9  mov     rcx, rsi
0x383a505fc  call    qword ptr [rax+20h]
0x383a505ff  mov     ebx, eax
0x383a50601  test    eax, eax
0x383a50603  js      loc_383A507AC
0x383a50609  cmp     [rsp+188h+Src], 0
0x383a5060e  jz      short loc_383A50663
0x383a50610  test    byte ptr cs:_bidGblFlags, 2
0x383a50617  jz      short loc_383A5064B
0x383a50619  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50620  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50627  test    rax, rax
0x383a5062a  jz      short loc_383A5064B
0x383a5062c  mov     dword ptr [rsp+188h+var_168], 1B9h
0x383a50634  mov     r9d, 8004D017h
0x383a5063a  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a50641  mov     edx, 6E429h
0x383a50646  call    _bidTraceW
0x383a5064b  lea     rdx, IID_ITransactionLocal; int
0x383a50652  mov     ecx, 8004D017h; this
0x383a50657  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a5065c  mov     ebx, eax
0x383a5065e  jmp     loc_383A507AC
0x383a50663  lea     rcx, [rsp+188h+Uuid]; Uuid
0x383a50668  call    cs:__imp_UuidCreate
0x383a5066e  test    eax, eax
0x383a50670  jns     short loc_383A506CD
0x383a50672  mov     ecx, cs:_bidGblFlags
0x383a50678  test    cl, 2
0x383a5067b  jz      loc_383A505D4
0x383a50681  mov     r8d, eax
0x383a50684  mov     edx, 71409h
0x383a50689  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50690  call    _bidTraceHR
0x383a50695  mov     ecx, cs:_bidGblFlags
0x383a5069b  test    cl, 2
0x383a5069e  jz      loc_383A505D4
0x383a506a4  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a506ab  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a506b2  test    rax, rax
0x383a506b5  jz      loc_383A505D4
0x383a506bb  mov     dword ptr [rsp+188h+var_168], 1C6h
0x383a506c3  mov     edx, 71829h
0x383a506c8  jmp     loc_383A505C2
0x383a506cd  mov     edx, r15d; int
0x383a506d0  mov     rcx, rbp; this
0x383a506d3  call    ?InitLocalXactMode@CDBConnection@@QEAAJJ@Z; CDBConnection::InitLocalXactMode(long)
0x383a506d8  mov     ebx, eax
0x383a506da  test    eax, eax
0x383a506dc  jns     short loc_383A5074F
0x383a506de  mov     eax, 80004005h
0x383a506e3  cmp     ebx, eax
0x383a506e5  jnz     short loc_383A5071E
0x383a506e7  test    byte ptr cs:_bidGblFlags, 2
0x383a506ee  jz      short loc_383A50704
0x383a506f0  mov     r8d, eax
0x383a506f3  mov     edx, 73809h
0x383a506f8  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a506ff  call    _bidTraceHR
0x383a50704  lea     r8, [rbp+88h]; struct _GUID *
0x383a5070b  lea     rdx, IID_ITransactionLocal; int
0x383a50712  mov     ecx, eax; this
0x383a50714  call    ?PostSqlErrors@CError@@QEAAJJPEBU_GUID@@PEAVCErrorData@@@Z; CError::PostSqlErrors(long,_GUID const *,CErrorData *)
0x383a50719  jmp     loc_383A507AC
0x383a5071e  test    byte ptr cs:_bidGblFlags, 2
0x383a50725  jz      short loc_383A5073D
0x383a50727  mov     r8d, ebx
0x383a5072a  mov     edx, 74809h
0x383a5072f  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a50736  call    _bidTraceHR
0x383a5073b  jmp     short loc_383A5073F
0x383a5073d  mov     eax, ebx
0x383a5073f  lea     rdx, IID_ITransactionLocal; int
0x383a50746  mov     ecx, eax; this
0x383a50748  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x383a5074d  jmp     short loc_383A507AC
0x383a5074f  mov     rax, [rdi+8]
0x383a50753  or      dword ptr [rax+350h], 1
0x383a5075a  mov     rax, [rdi+8]
0x383a5075e  mov     [rax+368h], r15d
0x383a50765  mov     rcx, [rdi+8]
0x383a50769  mov     rax, qword ptr [rsp+188h+Uuid.Data1]
0x383a5076e  mov     [rcx+358h], rax
0x383a50775  mov     rax, qword ptr [rsp+188h+Uuid.Data4]
0x383a5077a  mov     [rcx+360h], rax
0x383a50781  mov     rcx, [rdi+8]
0x383a50785  mov     r8d, 2Ch ; ','; Size
0x383a5078b  add     rcx, 380h; void *
0x383a50792  test    rsi, rsi
0x383a50795  jz      short loc_383A507A3
0x383a50797  lea     rdx, [rsp+188h+Src]; Src
0x383a5079c  call    memcpy
0x383a507a1  jmp     short loc_383A507AA
0x383a507a3  xor     edx, edx; Val
0x383a507a5  call    memset
0x383a507aa  xor     ebx, ebx
0x383a507ac  test    byte ptr cs:_bidGblFlags, 2
0x383a507b3  jz      short loc_383A507E2
0x383a507b5  mov     rax, cs:off_383B49C10; "<ITransactionLocal::StartTransaction|OL"...
0x383a507bc  test    rax, rax
0x383a507bf  jz      short loc_383A507E2
0x383a507c1  mov     [rsp+188h+var_168], r14
0x383a507c6  mov     r9d, ebx
0x383a507c9  mov     r8, cs:off_383B49C10; "<ITransactionLocal::StartTransaction|OL"...
0x383a507d0  mov     edx, 7C000h
0x383a507d5  mov     rcx, cs:off_383B433E8; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a507dc  call    _bidTraceW
0x383a507e1  nop
0x383a507e2  mov     rcx, [rsp+188h+var_138]
0x383a507e7  test    rcx, rcx
0x383a507ea  jz      short loc_383A507FD
0x383a507ec  add     rcx, 20h ; ' '
0x383a507f0  mov     rax, [rcx]
0x383a507f3  call    qword ptr [rax+18h]
0x383a507f6  mov     rcx, [rsp+188h+var_140]
0x383a507fb  jmp     short loc_383A50807
0x383a507fd  mov     rcx, [rsp+188h+var_140]
0x383a50802  test    rcx, rcx
0x383a50805  jz      short loc_383A50812
0x383a50807  add     rcx, 20h ; ' '
0x383a5080b  mov     rax, [rcx]
0x383a5080e  call    qword ptr [rax+18h]
0x383a50811  nop
0x383a50812  cmp     [rsp+188h+var_148], 0FFFFFFFFFFFFFFFFh
0x383a50818  jz      short loc_383A50840
0x383a5081a  test    byte ptr cs:_bidGblFlags, 4
0x383a50821  jz      short loc_383A50840
0x383a50823  mov     rcx, cs:_bidID
0x383a5082a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383a5082e  jz      short loc_383A50840
0x383a50830  lea     r9, [rsp+188h+var_148]
0x383a50835  xor     r8d, r8d
0x383a50838  xor     edx, edx
0x383a5083a  call    cs:off_383B15058
0x383a50840  mov     eax, ebx
0x383a50842  mov     rcx, [rsp+188h+var_48]
0x383a5084a  xor     rcx, rsp; StackCookie
0x383a5084d  call    __security_check_cookie
0x383a50852  add     rsp, 150h
0x383a50859  pop     r15
0x383a5085b  pop     r14
0x383a5085d  pop     r12
0x383a5085f  pop     rdi
0x383a50860  pop     rsi
0x383a50861  pop     rbp
0x383a50862  pop     rbx
0x383a50863  retn
```
