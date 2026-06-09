# _tsrpcEnumerate(void *,_SESSIONIDW * *,ulong *)

- ea: `0x180006ed0`
- end: `0x180007595`
- name: `?_tsrpcEnumerate@@YAJPEAXPEAPEAU_SESSIONIDW@@PEAK@Z`
- size: `1733`
- prototype: `__int64 __fastcall(void *, struct _SESSIONIDW **, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x180002600`
- `0x180008380`
- `0x180013994`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x180006ed0`
- `0x1800075a0`
- `0x1800083fc`
- `0x180008494`
- `0x180008508`
- `0x1800249e8`
- `0x180024a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000750b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007544`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000750b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007544`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000716e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000716e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007315`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000735f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007315`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000735f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003309e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003309e`
- `RPCRT4!NdrClientCall3` at `0x1800073ab`
- `RPCRT4!NdrClientCall3` at `0x1800073ab`

## string_xrefs

- `0x18000741a`: `StringCchCopy failed: %x`
- `0x18000743e`: `StringCchCopy failed: %x`
- `0x1800074da`: `Enum->Open failed: 0x%x in %s`
- `0x180007569`: `_tsrpcEnumerate: Failed to open binding`

## pseudocode

```c
__int64 __fastcall _tsrpcEnumerate(void *a1, struct _SESSIONIDW **a2, unsigned int *a3)
{
  unsigned int *v3; // r12
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _WORD *v8; // rcx
  int *v9; // rsi
  __int64 v10; // rax
  int *v11; // r8
  __int64 v12; // rdx
  __int16 v13; // r9
  int v14; // r14d
  _WORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  _WORD *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r9
  __int16 v21; // dx
  int v22; // esi
  _WORD *v23; // rax
  void *v24; // rax
  int v25; // eax
  CLIENT_CALL_RETURN v26; // rbx
  int EnumResult; // eax
  unsigned int v28; // eax
  unsigned __int64 v29; // rsi
  struct _SESSIONIDW *v30; // r15
  unsigned __int64 v31; // r14
  unsigned int i; // r10d
  __int64 v33; // rdx
  _DWORD *v34; // r8
  __int64 v35; // rcx
  __int16 *v36; // r9
  __int64 v37; // rdx
  _WORD *v38; // r8
  __int16 v39; // ax
  _WORD *v40; // rax
  unsigned int v41; // esi
  __int64 v42; // r8
  _DWORD *v43; // rdx
  int v44; // ecx
  __int64 v45; // r9
  __int16 *v46; // r11
  __int64 v47; // rcx
  _WORD *v48; // rdx
  __int16 v49; // ax
  _WORD *v50; // rax
  __int64 v52; // rax
  HLOCAL hMem; // [rsp+48h] [rbp-80h] BYREF
  HLOCAL v54; // [rsp+50h] [rbp-78h] BYREF
  __int64 v55; // [rsp+58h] [rbp-70h] BYREF
  CLIENT_CALL_RETURN v56; // [rsp+60h] [rbp-68h]
  unsigned __int16 v57[4]; // [rsp+68h] [rbp-60h] BYREF
  void *v58; // [rsp+70h] [rbp-58h]
  __int64 v59; // [rsp+78h] [rbp-50h] BYREF
  void *v60; // [rsp+80h] [rbp-48h]
  unsigned int v61; // [rsp+D0h] [rbp+8h] BYREF
  struct _SESSIONIDW **v62; // [rsp+D8h] [rbp+10h]
  unsigned int *v63; // [rsp+E0h] [rbp+18h]
  unsigned int v64; // [rsp+E8h] [rbp+20h] BYREF

  v63 = a3;
  v62 = a2;
  v3 = a3;
  hMem = 0;
  v61 = 0;
  v55 = 0;
  v54 = 0;
  v64 = 0;
  *a2 = 0;
  *a3 = 0;
  v59 = 0;
  if ( a1 )
  {
    v60 = a1;
    v9 = &dword_18003FF34;
  }
  else
  {
    v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      *v6 = 0;
      v6[1] = 0;
      v6[2] = 0;
      v6[3] = 0;
      v6[4] = 0;
      v6[5] = 0;
      v6[6] = 1;
      v6[7] = 0;
      v8 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v7[5] = v8;
      v9 = &dword_18003FF34;
      if ( v8 )
      {
        v10 = 2147483646;
        v11 = &dword_18003FF34;
        v12 = 1;
        do
        {
          if ( !v10 )
            break;
          v13 = *(_WORD *)v11;
          if ( !*(_WORD *)v11 )
            break;
          v11 = (int *)((char *)v11 + 2);
          *v8++ = v13;
          --v10;
          --v12;
        }
        while ( v12 );
        v14 = -2147024774;
        if ( v12 )
          v14 = 0;
        v15 = v8 - 1;
        if ( v12 )
          v15 = v8;
        *v15 = 0;
        if ( v12 )
        {
          if ( !v7[3] && !*((_DWORD *)v7 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v7) == -2147023174 )
              *((_DWORD *)v7 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v7);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v14);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v14);
        }
      }
    }
    else
    {
      v7 = 0;
      v9 = &dword_18003FF34;
    }
    v60 = v7;
    if ( v7 )
    {
      HIDWORD(v59) = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  *(_QWORD *)v57 = 1;
  if ( a1 )
  {
    v58 = a1;
  }
  else
  {
    v16 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v16;
    if ( v16 )
    {
      *v16 = 0;
      v16[1] = 0;
      v16[2] = 0;
      v16[3] = 0;
      v16[4] = 0;
      v16[5] = 0;
      v16[6] = 1;
      v16[7] = 0;
      v18 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v17[5] = v18;
      if ( v18 )
      {
        v19 = 2147483646;
        v20 = 1;
        do
        {
          if ( !v19 )
            break;
          v21 = *(_WORD *)v9;
          if ( !*(_WORD *)v9 )
            break;
          v9 = (int *)((char *)v9 + 2);
          *v18++ = v21;
          --v19;
          --v20;
        }
        while ( v20 );
        v22 = -2147024774;
        if ( v20 )
          v22 = 0;
        v23 = v18 - 1;
        if ( v20 )
          v23 = v18;
        *v23 = 0;
        if ( v20 )
        {
          if ( !v17[3] && !*((_DWORD *)v17 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v17) == -2147023174 )
              *((_DWORD *)v17 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v17);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v22);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v22);
        }
      }
    }
    else
    {
      v17 = 0;
    }
    v58 = v17;
    if ( v17 )
    {
      *(_DWORD *)&v57[2] = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( CSmartPublicBinding::operator void *((unsigned __int16 *)&v59) )
  {
    v24 = (void *)CSmartPublicBinding::operator void *((unsigned __int16 *)&v59);
    v25 = CEnum::Open((CEnum *)&v55, v24);
    LODWORD(v26.Pointer) = v25;
    if ( v25 < 0 )
    {
      _DbgPrintMessage(8, "Enum->Open failed: 0x%x in %s", v25, "_tsrpcEnumerate");
    }
    else
    {
      EnumResult = CEnum::GetEnumResult((CEnum *)&v55, 1u, (struct _SESSIONENUM **)&hMem, &v61);
      LODWORD(v26.Pointer) = EnumResult;
      if ( EnumResult < 0 )
      {
        _DbgPrintMessage(8, "GetEnumResult failed: 0x%x in %s", EnumResult, "_tsrpcEnumerate");
      }
      else
      {
        if ( CSmartPublicBinding::operator void *(v57) )
        {
          v52 = CSmartPublicBinding::operator void *(v57);
          v56.Simple = 0;
          v26.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035078, 8u, 0, v52, &v54, 1, &v64).Pointer;
          v56.Pointer = v26.Pointer;
        }
        v28 = 76 * (v64 + v61);
        if ( v28 )
        {
          v29 = v28;
          v30 = (struct _SESSIONIDW *)LocalAlloc(0, v28);
          if ( v30 )
          {
            v31 = v29 / 0x4C;
            for ( i = 0; i < (unsigned int)v31; ++i )
            {
              if ( i >= v61 )
                break;
              v33 = 104LL * i;
              v34 = (_DWORD *)((char *)v30 + 76 * i);
              *v34 = *(_DWORD *)((char *)hMem + v33 + 4);
              v34[18] = *(_DWORD *)((char *)hMem + v33 + 8);
              v35 = 2147483646;
              v36 = (__int16 *)((char *)hMem + v33 + 12);
              v37 = 33;
              v38 = v34 + 1;
              do
              {
                if ( !v35 )
                  break;
                v39 = *v36;
                if ( !*v36 )
                  break;
                ++v36;
                *v38++ = v39;
                --v35;
                --v37;
              }
              while ( v37 );
              v40 = v38 - 1;
              if ( v37 )
                v40 = v38;
              *v40 = 0;
              LODWORD(v26.Pointer) = -2147024774;
              if ( v37 )
                LODWORD(v26.Pointer) = 0;
            }
            v41 = 0;
            if ( i < (unsigned int)v31 )
            {
              do
              {
                if ( v41 >= v64 )
                  break;
                v42 = 80LL * v41;
                v43 = (_DWORD *)((char *)v30 + 76 * i);
                *v43 = *(_DWORD *)((char *)v54 + v42 + 4);
                v44 = 6;
                if ( !*(_DWORD *)((char *)v54 + v42 + 8) )
                  v44 = 8;
                v43[18] = v44;
                v45 = 2147483646;
                v46 = (__int16 *)((char *)v54 + v42 + 12);
                v47 = 33;
                v48 = v43 + 1;
                do
                {
                  if ( !v45 )
                    break;
                  v49 = *v46;
                  if ( !*v46 )
                    break;
                  ++v46;
                  *v48++ = v49;
                  --v45;
                  --v47;
                }
                while ( v47 );
                v50 = v48 - 1;
                if ( v47 )
                  v50 = v48;
                *v50 = 0;
                LODWORD(v26.Pointer) = -2147024774;
                if ( v47 )
                  LODWORD(v26.Pointer) = 0;
                ++i;
                ++v41;
              }
              while ( i < (unsigned int)v31 );
              v3 = v63;
            }
            *a2 = v30;
            *v3 = v31;
          }
          else
          {
            LODWORD(v26.Pointer) = -2147024882;
          }
        }
        else
        {
          _DbgPrintMessage(4, "_tsrpcEnumerate: No sessions or listeners could be enumerated on the target");
          LODWORD(v26.Pointer) = 0;
        }
      }
    }
  }
  else
  {
    LODWORD(v26.Pointer) = -2147024882;
    _DbgPrintMessage(8, "_tsrpcEnumerate: Failed to open binding");
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v54 )
    LocalFree(v54);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v57);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v59);
  CEnum::~CEnum((CEnum *)&v55);
  return LODWORD(v26.Pointer);
}

```

## disassembly

```asm
0x180006ed0  mov     rax, rsp
0x180006ed3  mov     [rax+18h], r8
0x180006ed7  mov     [rax+10h], rdx
0x180006edb  push    rbx
0x180006edc  push    rsi
0x180006edd  push    rdi
0x180006ede  push    r12
0x180006ee0  push    r13
0x180006ee2  push    r14
0x180006ee4  push    r15
0x180006ee6  sub     rsp, 90h
0x180006eed  mov     r12, r8
0x180006ef0  mov     r13, rdx
0x180006ef3  mov     r15, rcx
0x180006ef6  xor     edi, edi
0x180006ef8  mov     [rax-80h], rdi
0x180006efc  mov     [rax+8], edi
0x180006eff  mov     [rax-70h], rdi
0x180006f03  mov     [rax-78h], rdi
0x180006f07  mov     [rax+20h], edi
0x180006f0a  mov     [rdx], rdi
0x180006f0d  mov     [r8], edi
0x180006f10  mov     [rax-50h], rdi
0x180006f14  test    rcx, rcx
0x180006f17  jnz     loc_1800074AC
0x180006f1d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006f24  mov     ecx, 40h ; '@'; unsigned __int64
0x180006f29  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006f2e  mov     rbx, rax
0x180006f31  test    rax, rax
0x180006f34  jz      loc_1800074F7
0x180006f3a  mov     [rax], rdi
0x180006f3d  mov     [rax+8], rdi
0x180006f41  mov     [rax+10h], rdi
0x180006f45  mov     [rax+18h], rdi
0x180006f49  mov     [rax+20h], rdi
0x180006f4d  mov     [rax+28h], rdi
0x180006f51  mov     qword ptr [rax+30h], 1
0x180006f59  mov     [rax+38h], rdi
0x180006f5d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006f64  mov     ecx, 2; unsigned __int64
0x180006f69  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006f6e  mov     rcx, rax
0x180006f71  mov     [rbx+28h], rax
0x180006f75  lea     rsi, dword_18003FF34
0x180006f7c  test    rax, rax
0x180006f7f  jz      short loc_180006FE1
0x180006f81  mov     eax, 7FFFFFFEh
0x180006f86  mov     r8, rsi
0x180006f89  mov     edx, 1
0x180006f8e  xchg    ax, ax
0x180006f90  test    rax, rax
0x180006f93  jz      short loc_180006FB4
0x180006f95  movzx   r9d, word ptr [r8]
0x180006f99  test    r9w, r9w
0x180006f9d  jz      short loc_180006FB4
0x180006f9f  add     r8, 2
0x180006fa3  mov     [rcx], r9w
0x180006fa7  add     rcx, 2
0x180006fab  dec     rax
0x180006fae  sub     rdx, 1
0x180006fb2  jnz     short loc_180006F90
0x180006fb4  mov     r14d, 8007007Ah
0x180006fba  test    rdx, rdx
0x180006fbd  cmovnz  r14d, edi
0x180006fc1  lea     rax, [rcx-2]
0x180006fc5  cmovnz  rax, rcx
0x180006fc9  mov     [rax], di
0x180006fcc  jz      loc_18000740F
0x180006fd2  cmp     [rbx+18h], rdi
0x180006fd6  jnz     short loc_180006FE1
0x180006fd8  cmp     [rbx+30h], edi
0x180006fdb  jz      loc_180007470
0x180006fe1  mov     r14d, 8
0x180006fe7  mov     [rsp+0C8h+var_48], rbx
0x180006fef  test    rbx, rbx
0x180006ff2  jz      loc_180007506
0x180006ff8  mov     [rsp+0C8h+var_4C], 1
0x180007000  mov     qword ptr [rsp+0C8h+var_60], 1
0x180007009  test    r15, r15
0x18000700c  jnz     loc_1800074C6
0x180007012  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007019  mov     ecx, 40h ; '@'; unsigned __int64
0x18000701e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007023  mov     rbx, rax
0x180007026  test    rax, rax
0x180007029  jz      loc_180007537
0x18000702f  mov     [rax], rdi
0x180007032  mov     [rax+8], rdi
0x180007036  mov     [rax+10h], rdi
0x18000703a  mov     [rax+18h], rdi
0x18000703e  mov     [rax+20h], rdi
0x180007042  mov     [rax+28h], rdi
0x180007046  mov     qword ptr [rax+30h], 1
0x18000704e  mov     [rax+38h], rdi
0x180007052  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007059  mov     ecx, 2; unsigned __int64
0x18000705e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007063  mov     rcx, rax
0x180007066  mov     [rbx+28h], rax
0x18000706a  test    rax, rax
0x18000706d  jz      short loc_1800070CC
0x18000706f  mov     eax, 7FFFFFFEh
0x180007074  mov     r9d, 1
0x18000707a  nop     word ptr [rax+rax+00h]
0x180007080  test    rax, rax
0x180007083  jz      short loc_1800070A1
0x180007085  movzx   edx, word ptr [rsi]
0x180007088  test    dx, dx
0x18000708b  jz      short loc_1800070A1
0x18000708d  add     rsi, 2
0x180007091  mov     [rcx], dx
0x180007094  add     rcx, 2
0x180007098  dec     rax
0x18000709b  sub     r9, 1
0x18000709f  jnz     short loc_180007080
0x1800070a1  mov     esi, 8007007Ah
0x1800070a6  test    r9, r9
0x1800070a9  cmovnz  esi, edi
0x1800070ac  lea     rax, [rcx-2]
0x1800070b0  cmovnz  rax, rcx
0x1800070b4  mov     [rax], di
0x1800070b7  jz      loc_180007434
0x1800070bd  cmp     [rbx+18h], rdi
0x1800070c1  jnz     short loc_1800070CC
0x1800070c3  cmp     [rbx+30h], edi
0x1800070c6  jz      loc_18000748C
0x1800070cc  mov     [rsp+0C8h+var_58], rbx
0x1800070d1  test    rbx, rbx
0x1800070d4  jz      loc_18000753F
0x1800070da  mov     dword ptr [rsp+0C8h+var_60+4], 1
0x1800070e2  lea     rcx, [rsp+0C8h+var_50]; unsigned __int16 *
0x1800070e7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800070ec  test    rax, rax
0x1800070ef  jz      loc_180007564
0x1800070f5  lea     rcx, [rsp+0C8h+var_50]; unsigned __int16 *
0x1800070fa  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800070ff  mov     rdx, rax; void *
0x180007102  lea     rcx, [rsp+0C8h+var_70]; this
0x180007107  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x18000710c  mov     ebx, eax
0x18000710e  test    eax, eax
0x180007110  js      loc_1800074D0
0x180007116  lea     r9, [rsp+0C8h+arg_0]; unsigned int *
0x18000711e  lea     r8, [rsp+0C8h+hMem]; struct _SESSIONENUM **
0x180007123  mov     edx, 1; unsigned int
0x180007128  lea     rcx, [rsp+0C8h+var_70]; this
0x18000712d  call    ?GetEnumResult@CEnum@@QEAAJKPEAPEAU_SESSIONENUM@@PEAK@Z; CEnum::GetEnumResult(ulong,_SESSIONENUM * *,ulong *)
0x180007132  mov     ebx, eax
0x180007134  test    eax, eax
0x180007136  js      loc_180007452
0x18000713c  lea     rcx, [rsp+0C8h+var_60]; unsigned __int16 *
0x180007141  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180007146  test    rax, rax
0x180007149  jnz     loc_18000736D
0x18000714f  mov     ecx, [rsp+0C8h+arg_0]
0x180007156  add     ecx, [rsp+0C8h+arg_18]
0x18000715d  imul    eax, ecx, 4Ch ; 'L'
0x180007160  test    eax, eax
0x180007162  jz      loc_18000757D
0x180007168  mov     esi, eax
0x18000716a  mov     edx, eax; uBytes
0x18000716c  xor     ecx, ecx; uFlags
0x18000716e  call    cs:__imp_LocalAlloc
0x180007175  nop     dword ptr [rax+rax+00h]
0x18000717a  mov     r15, rax
0x18000717d  test    rax, rax
0x180007180  jz      loc_180007405
0x180007186  mov     rax, 0D79435E50D79435Fh
0x180007190  mul     rsi
0x180007193  mov     r14, rdx
0x180007196  shr     r14, 6
0x18000719a  mov     r10d, edi
0x18000719d  test    r14d, r14d
0x1800071a0  jz      loc_180007245
0x1800071a6  nop     word ptr [rax+rax+00000000h]
0x1800071b0  cmp     r10d, [rsp+0C8h+arg_0]
0x1800071b8  jnb     loc_180007245
0x1800071be  mov     eax, r10d
0x1800071c1  imul    rdx, rax, 68h ; 'h'
0x1800071c5  imul    r8, rax, 4Ch ; 'L'
0x1800071c9  add     r8, r15
0x1800071cc  mov     rax, [rsp+0C8h+hMem]
0x1800071d1  mov     ecx, [rdx+rax+4]
0x1800071d5  mov     [r8], ecx
0x1800071d8  mov     rax, [rsp+0C8h+hMem]
0x1800071dd  mov     ecx, [rdx+rax+8]
0x1800071e1  mov     [r8+48h], ecx
0x1800071e5  mov     ecx, 7FFFFFFEh
0x1800071ea  mov     r9, [rsp+0C8h+hMem]
0x1800071ef  add     r9, 0Ch
0x1800071f3  add     r9, rdx
0x1800071f6  mov     edx, 21h ; '!'
0x1800071fb  add     r8, 4
0x1800071ff  nop
0x180007200  test    rcx, rcx
0x180007203  jz      short loc_180007223
0x180007205  movzx   eax, word ptr [r9]
0x180007209  test    ax, ax
0x18000720c  jz      short loc_180007223
0x18000720e  add     r9, 2
0x180007212  mov     [r8], ax
0x180007216  add     r8, 2
0x18000721a  dec     rcx
0x18000721d  sub     rdx, 1
0x180007221  jnz     short loc_180007200
0x180007223  lea     rax, [r8-2]
0x180007227  test    rdx, rdx
0x18000722a  cmovnz  rax, r8
0x18000722e  mov     [rax], di
0x180007231  mov     ebx, 8007007Ah
0x180007236  cmovnz  ebx, edi
0x180007239  inc     r10d
0x18000723c  cmp     r10d, r14d
0x18000723f  jb      loc_1800071B0
0x180007245  mov     esi, edi
0x180007247  cmp     r10d, r14d
0x18000724a  jnb     loc_180007303
0x180007250  mov     r12d, 8
0x180007256  cmp     esi, [rsp+0C8h+arg_18]
0x18000725d  jnb     loc_1800072FB
0x180007263  mov     eax, esi
0x180007265  lea     r8, [rax+rax*4]
0x180007269  shl     r8, 4
0x18000726d  mov     eax, r10d
0x180007270  imul    rdx, rax, 4Ch ; 'L'
0x180007274  add     rdx, r15
0x180007277  mov     rax, [rsp+0C8h+var_78]
0x18000727c  mov     ecx, [r8+rax+4]
0x180007281  mov     [rdx], ecx
0x180007283  mov     ecx, 6
0x180007288  mov     rax, [rsp+0C8h+var_78]
0x18000728d  cmp     dword ptr [r8+rax+8], 0
0x180007293  cmovz   ecx, r12d
0x180007297  mov     [rdx+48h], ecx
0x18000729a  mov     r9d, 7FFFFFFEh
0x1800072a0  mov     r11, [rsp+0C8h+var_78]
0x1800072a5  add     r11, 0Ch
0x1800072a9  add     r11, r8
0x1800072ac  mov     ecx, 21h ; '!'
0x1800072b1  add     rdx, 4
0x1800072b5  test    r9, r9
0x1800072b8  jz      short loc_1800072D7
0x1800072ba  movzx   eax, word ptr [r11]
0x1800072be  test    ax, ax
0x1800072c1  jz      short loc_1800072D7
0x1800072c3  add     r11, 2
0x1800072c7  mov     [rdx], ax
0x1800072ca  add     rdx, 2
0x1800072ce  dec     r9
0x1800072d1  sub     rcx, 1
0x1800072d5  jnz     short loc_1800072B5
0x1800072d7  lea     rax, [rdx-2]
0x1800072db  test    rcx, rcx
0x1800072de  cmovnz  rax, rdx
0x1800072e2  mov     [rax], di
0x1800072e5  mov     ebx, 8007007Ah
0x1800072ea  cmovnz  ebx, edi
0x1800072ed  inc     r10d
0x1800072f0  inc     esi
0x1800072f2  cmp     r10d, r14d
0x1800072f5  jb      loc_180007256
0x1800072fb  mov     r12, [rsp+0C8h+arg_10]
0x180007303  mov     [r13+0], r15
0x180007307  mov     [r12], r14d
0x18000730b  mov     rcx, [rsp+0C8h+hMem]; hMem
0x180007310  test    rcx, rcx
0x180007313  jz      short loc_180007321
0x180007315  call    cs:__imp_LocalFree
0x18000731c  nop     dword ptr [rax+rax+00h]
0x180007321  mov     rcx, [rsp+0C8h+var_78]; hMem
0x180007326  test    rcx, rcx
0x180007329  jnz     short loc_18000735F
0x18000732b  lea     rcx, [rsp+0C8h+var_60]; this
0x180007330  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180007335  lea     rcx, [rsp+0C8h+var_50]; this
0x18000733a  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000733f  lea     rcx, [rsp+0C8h+var_70]; this
0x180007344  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x180007349  mov     eax, ebx
0x18000734b  add     rsp, 90h
0x180007352  pop     r15
0x180007354  pop     r14
0x180007356  pop     r13
0x180007358  pop     r12
0x18000735a  pop     rdi
0x18000735b  pop     rsi
0x18000735c  pop     rbx
0x18000735d  retn
0x18000735f  call    cs:__imp_LocalFree
0x180007366  nop     dword ptr [rax+rax+00h]
0x18000736b  jmp     short loc_18000732B
0x18000736d  lea     rcx, [rsp+0C8h+var_60]; unsigned __int16 *
0x180007372  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180007377  mov     [rsp+0C8h+var_68], rdi
0x18000737c  lea     rcx, [rsp+0C8h+arg_18]
0x180007384  mov     [rsp+0C8h+var_98], rcx
0x180007389  mov     [rsp+0C8h+var_A0], 1
0x180007391  lea     rcx, [rsp+0C8h+var_78]
0x180007396  mov     [rsp+0C8h+var_A8], rcx
  ... truncated ...
```
