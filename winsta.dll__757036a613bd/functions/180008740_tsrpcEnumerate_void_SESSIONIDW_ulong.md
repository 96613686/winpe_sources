# _tsrpcEnumerate(void *,_SESSIONIDW * *,ulong *)

- ea: `0x180008740`
- end: `0x180008e21`
- name: `?_tsrpcEnumerate@@YAJPEAXPEAPEAU_SESSIONIDW@@PEAK@Z`
- size: `1761`
- prototype: `__int64 __fastcall(_QWORD *, struct _SESSIONIDW **, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x180004bb0`
- `0x180009b30`
- `0x180012b14`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008200`
- `0x180008340`
- `0x180008740`
- `0x180008e30`
- `0x180009ba4`
- `0x180009c10`
- `0x180009c94`
- `0x1800230b8`
- `0x1800230ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008da0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008da0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800089e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800089e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008bea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008bea`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003034e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003034e`
- `RPCRT4!NdrClientCall3` at `0x180008c2f`
- `RPCRT4!NdrClientCall3` at `0x180008c2f`

## string_xrefs

- `0x180008c99`: `StringCchCopy failed: %x`
- `0x180008cbb`: `StringCchCopy failed: %x`
- `0x180008d5c`: `Enum->Open failed: 0x%x in %s`
- `0x180008df6`: `_tsrpcEnumerate: Failed to open binding`

## pseudocode

```c
__int64 __fastcall _tsrpcEnumerate(_QWORD *a1, struct _SESSIONIDW **a2, unsigned int *a3)
{
  _QWORD *v3; // r13
  _QWORD *v4; // rax
  _QWORD *v5; // r12
  _WORD *v6; // rcx
  int *v7; // rbx
  __int64 v8; // rax
  int *v9; // r8
  __int64 v10; // rdx
  __int16 v11; // r9
  int v12; // esi
  _WORD *v13; // rax
  _QWORD *v14; // rax
  _WORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r9
  __int16 v18; // dx
  int v19; // ebx
  _WORD *v20; // rax
  void *v21; // rax
  int v22; // eax
  CLIENT_CALL_RETURN v23; // rbx
  int EnumResult; // eax
  unsigned int v25; // eax
  unsigned __int64 v26; // rsi
  unsigned __int128 v27; // rax
  struct _SESSIONIDW *v28; // r15
  unsigned __int64 v29; // r14
  unsigned int i; // r10d
  __int64 v31; // rdx
  _DWORD *v32; // r8
  __int64 v33; // rcx
  _WORD *v34; // r9
  _WORD *v35; // r8
  unsigned int v36; // esi
  __int64 v37; // r8
  _DWORD *v38; // rdx
  int v39; // ecx
  __int64 v40; // r9
  _WORD *v41; // r11
  __int64 v42; // rcx
  _WORD *v43; // rax
  __int64 v45; // rax
  HLOCAL hMem; // [rsp+48h] [rbp-80h] BYREF
  HLOCAL v47; // [rsp+50h] [rbp-78h] BYREF
  _QWORD *v48; // [rsp+58h] [rbp-70h]
  __int64 v49; // [rsp+60h] [rbp-68h] BYREF
  CLIENT_CALL_RETURN v50; // [rsp+68h] [rbp-60h]
  unsigned __int16 v51[4]; // [rsp+70h] [rbp-58h] BYREF
  _QWORD *v52; // [rsp+78h] [rbp-50h]
  __int64 v53; // [rsp+80h] [rbp-48h] BYREF
  void *v54; // [rsp+88h] [rbp-40h]
  unsigned int v55; // [rsp+D0h] [rbp+8h] BYREF
  struct _SESSIONIDW **v56; // [rsp+D8h] [rbp+10h]
  unsigned int *v57; // [rsp+E0h] [rbp+18h]
  unsigned int v58; // [rsp+E8h] [rbp+20h] BYREF

  v57 = a3;
  v56 = a2;
  v3 = a1;
  hMem = 0;
  v55 = 0;
  v49 = 0;
  v47 = 0;
  v58 = 0;
  *a2 = 0;
  *a3 = 0;
  v53 = 0;
  if ( a1 )
  {
    v5 = a1;
    v48 = a1;
    v54 = a1;
    v7 = &dword_18003D0CC;
  }
  else
  {
    v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v4;
    v48 = v4;
    if ( v4 )
    {
      *v4 = 0;
      v4[1] = 0;
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = 0;
      v4[5] = 0;
      v4[6] = 1;
      v4[7] = 0;
      v6 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v5[5] = v6;
      v7 = &dword_18003D0CC;
      if ( v6 )
      {
        v8 = 2147483646;
        v9 = &dword_18003D0CC;
        v10 = 1;
        do
        {
          if ( !v8 )
            break;
          v11 = *(_WORD *)v9;
          if ( !*(_WORD *)v9 )
            break;
          v9 = (int *)((char *)v9 + 2);
          *v6++ = v11;
          --v8;
          --v10;
        }
        while ( v10 );
        v12 = -2147024774;
        if ( v10 )
          v12 = 0;
        v13 = v6 - 1;
        if ( v10 )
          v13 = v6;
        *v13 = 0;
        if ( v10 )
        {
          if ( !v5[3] && !*((_DWORD *)v5 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v5) == -2147023174 )
              *((_DWORD *)v5 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v5);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v12);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v12);
        }
      }
      v54 = v5;
    }
    else
    {
      v5 = 0;
      v48 = 0;
      v54 = 0;
      v7 = &dword_18003D0CC;
    }
    if ( v5 )
    {
      HIDWORD(v53) = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  *(_QWORD *)v51 = 1;
  if ( v3 )
  {
    v52 = v3;
  }
  else
  {
    v14 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v3 = v14;
    if ( v14 )
    {
      *v14 = 0;
      v14[1] = 0;
      v14[2] = 0;
      v14[3] = 0;
      v14[4] = 0;
      v14[5] = 0;
      v14[6] = 1;
      v14[7] = 0;
      v15 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v3[5] = v15;
      if ( v15 )
      {
        v16 = 2147483646;
        v17 = 1;
        do
        {
          if ( !v16 )
            break;
          v18 = *(_WORD *)v7;
          if ( !*(_WORD *)v7 )
            break;
          v7 = (int *)((char *)v7 + 2);
          *v15++ = v18;
          --v16;
          --v17;
        }
        while ( v17 );
        v19 = -2147024774;
        if ( v17 )
          v19 = 0;
        v20 = v15 - 1;
        if ( v17 )
          v20 = v15;
        *v20 = 0;
        if ( v17 )
        {
          if ( !v3[3] && !*((_DWORD *)v3 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v3) == -2147023174 )
              *((_DWORD *)v3 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v3);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v19);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v19);
        }
      }
      v52 = v3;
    }
    else
    {
      v3 = 0;
      v52 = 0;
    }
    if ( v3 )
    {
      *(_DWORD *)&v51[2] = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( CSmartPublicBinding::operator void *((unsigned __int16 *)&v53) )
  {
    v21 = (void *)CSmartPublicBinding::operator void *((unsigned __int16 *)&v53);
    v22 = CEnum::Open((CEnum *)&v49, v21);
    LODWORD(v23.Pointer) = v22;
    if ( v22 < 0 )
    {
      _DbgPrintMessage(8, "Enum->Open failed: 0x%x in %s", v22, "_tsrpcEnumerate");
    }
    else
    {
      EnumResult = CEnum::GetEnumResult((CEnum *)&v49, 1u, (struct _SESSIONENUM **)&hMem, &v55);
      LODWORD(v23.Pointer) = EnumResult;
      if ( EnumResult < 0 )
      {
        _DbgPrintMessage(8, "GetEnumResult failed: 0x%x in %s", EnumResult, "_tsrpcEnumerate");
      }
      else
      {
        if ( CSmartPublicBinding::operator void *(v51) )
        {
          v45 = CSmartPublicBinding::operator void *(v51);
          v50.Simple = 0;
          v23.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0, 8u, 0, v45, &v47, 1, &v58).Pointer;
          v50.Pointer = v23.Pointer;
        }
        v25 = 76 * (v58 + v55);
        if ( v25 )
        {
          v26 = v25;
          v28 = (struct _SESSIONIDW *)LocalAlloc(0, v25);
          if ( v28 )
          {
            v27 = v26 * (unsigned __int128)0xD79435E50D79435FuLL;
            v29 = v26 / 0x4C;
            for ( i = 0; i < (unsigned int)v29; ++i )
            {
              if ( i >= v55 )
                break;
              v31 = 104LL * i;
              v32 = (_DWORD *)((char *)v28 + 76 * i);
              *v32 = *(_DWORD *)((char *)hMem + v31 + 4);
              v32[18] = *(_DWORD *)((char *)hMem + v31 + 8);
              v33 = 2147483646;
              v34 = (char *)hMem + v31 + 12;
              *((_QWORD *)&v27 + 1) = 33;
              v35 = v32 + 1;
              do
              {
                if ( !v33 )
                  break;
                LOWORD(v27) = *v34;
                if ( !*v34 )
                  break;
                ++v34;
                *v35++ = v27;
                --v33;
                --*((_QWORD *)&v27 + 1);
              }
              while ( *((_QWORD *)&v27 + 1) );
              *(_QWORD *)&v27 = v35 - 1;
              if ( *((_QWORD *)&v27 + 1) )
                *(_QWORD *)&v27 = v35;
              *(_WORD *)v27 = 0;
              LODWORD(v23.Pointer) = -2147024774;
              if ( *((_QWORD *)&v27 + 1) )
                LODWORD(v23.Pointer) = 0;
            }
            v36 = 0;
            if ( i < (unsigned int)v29 )
            {
              do
              {
                if ( v36 >= v58 )
                  break;
                v37 = 80LL * v36;
                v38 = (_DWORD *)((char *)v28 + 76 * i);
                *v38 = *(_DWORD *)((char *)v47 + v37 + 4);
                v39 = 6;
                if ( !*(_DWORD *)((char *)v47 + v37 + 8) )
                  v39 = 8;
                v38[18] = v39;
                v40 = 2147483646;
                v41 = (char *)v47 + v37 + 12;
                v42 = 33;
                *((_QWORD *)&v27 + 1) = v38 + 1;
                do
                {
                  if ( !v40 )
                    break;
                  LOWORD(v27) = *v41;
                  if ( !*v41 )
                    break;
                  ++v41;
                  **((_WORD **)&v27 + 1) = v27;
                  *((_QWORD *)&v27 + 1) += 2LL;
                  --v40;
                  --v42;
                }
                while ( v42 );
                v43 = (_WORD *)(*((_QWORD *)&v27 + 1) - 2LL);
                if ( v42 )
                  v43 = (_WORD *)*((_QWORD *)&v27 + 1);
                *v43 = 0;
                LODWORD(v23.Pointer) = -2147024774;
                if ( v42 )
                  LODWORD(v23.Pointer) = 0;
                ++i;
                ++v36;
              }
              while ( i < (unsigned int)v29 );
              v5 = v48;
            }
            *v56 = v28;
            *v57 = v29;
          }
          else
          {
            LODWORD(v23.Pointer) = -2147024882;
          }
        }
        else
        {
          _DbgPrintMessage(4, "_tsrpcEnumerate: No sessions or listeners could be enumerated on the target");
          LODWORD(v23.Pointer) = 0;
        }
      }
    }
  }
  else
  {
    LODWORD(v23.Pointer) = -2147024882;
    _DbgPrintMessage(8, "_tsrpcEnumerate: Failed to open binding");
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v47 )
    LocalFree(v47);
  if ( *(_DWORD *)&v51[2] && v3 )
    CPublicBinding::`scalar deleting destructor'((RPC_BINDING_HANDLE *)v3, DWORD2(v27));
  if ( HIDWORD(v53) && v5 )
    CPublicBinding::`scalar deleting destructor'((RPC_BINDING_HANDLE *)v5, DWORD2(v27));
  CEnum::~CEnum((CEnum *)&v49);
  return LODWORD(v23.Pointer);
}

```

## disassembly

```asm
0x180008740  mov     rax, rsp
0x180008743  mov     [rax+18h], r8
0x180008747  mov     [rax+10h], rdx
0x18000874b  push    rbx
0x18000874c  push    rsi
0x18000874d  push    rdi
0x18000874e  push    r12
0x180008750  push    r13
0x180008752  push    r14
0x180008754  push    r15
0x180008756  sub     rsp, 90h
0x18000875d  mov     r13, rcx
0x180008760  xor     edi, edi
0x180008762  mov     [rax-80h], rdi
0x180008766  mov     [rax+8], edi
0x180008769  mov     [rax-68h], rdi
0x18000876d  mov     [rax-78h], rdi
0x180008771  mov     [rax+20h], edi
0x180008774  mov     [rdx], rdi
0x180008777  mov     [r8], edi
0x18000877a  mov     [rax-48h], rdi
0x18000877e  test    rcx, rcx
0x180008781  jnz     loc_180008D27
0x180008787  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000878e  mov     ecx, 40h ; '@'; unsigned __int64
0x180008793  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008798  mov     r12, rax
0x18000879b  mov     [rsp+0C8h+var_70], rax
0x1800087a0  test    rax, rax
0x1800087a3  jz      loc_180008D7A
0x1800087a9  mov     [rax], rdi
0x1800087ac  mov     [rax+8], rdi
0x1800087b0  mov     [rax+10h], rdi
0x1800087b4  mov     [rax+18h], rdi
0x1800087b8  mov     [rax+20h], rdi
0x1800087bc  mov     [rax+28h], rdi
0x1800087c0  mov     qword ptr [rax+30h], 1
0x1800087c8  mov     [rax+38h], rdi
0x1800087cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800087d3  mov     ecx, 2; unsigned __int64
0x1800087d8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800087dd  mov     rcx, rax
0x1800087e0  mov     [r12+28h], rax
0x1800087e5  lea     rbx, dword_18003D0CC
0x1800087ec  test    rax, rax
0x1800087ef  jz      short loc_180008852
0x1800087f1  mov     eax, 7FFFFFFEh
0x1800087f6  mov     r8, rbx
0x1800087f9  mov     edx, 1
0x1800087fe  xchg    ax, ax
0x180008800  test    rax, rax
0x180008803  jz      short loc_180008824
0x180008805  movzx   r9d, word ptr [r8]
0x180008809  test    r9w, r9w
0x18000880d  jz      short loc_180008824
0x18000880f  add     r8, 2
0x180008813  mov     [rcx], r9w
0x180008817  add     rcx, 2
0x18000881b  dec     rax
0x18000881e  sub     rdx, 1
0x180008822  jnz     short loc_180008800
0x180008824  mov     esi, 8007007Ah
0x180008829  test    rdx, rdx
0x18000882c  cmovnz  esi, edi
0x18000882f  lea     rax, [rcx-2]
0x180008833  cmovnz  rax, rcx
0x180008837  mov     [rax], di
0x18000883a  jz      loc_180008C8F
0x180008840  cmp     [r12+18h], rdi
0x180008845  jnz     short loc_180008852
0x180008847  cmp     [r12+30h], edi
0x18000884c  jz      loc_180008CEB
0x180008852  mov     esi, 8
0x180008857  mov     [rsp+0C8h+var_40], r12
0x18000885f  test    r12, r12
0x180008862  jz      loc_180008D9B
0x180008868  mov     [rsp+0C8h+var_44], 1
0x180008873  mov     qword ptr [rsp+0C8h+var_58], 1
0x18000887c  test    r13, r13
0x18000887f  jnz     loc_180008D48
0x180008885  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000888c  mov     ecx, 40h ; '@'; unsigned __int64
0x180008891  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008896  mov     r13, rax
0x180008899  test    rax, rax
0x18000889c  jz      loc_180008DC6
0x1800088a2  mov     [rax], rdi
0x1800088a5  mov     [rax+8], rdi
0x1800088a9  mov     [rax+10h], rdi
0x1800088ad  mov     [rax+18h], rdi
0x1800088b1  mov     [rax+20h], rdi
0x1800088b5  mov     [rax+28h], rdi
0x1800088b9  mov     qword ptr [rax+30h], 1
0x1800088c1  mov     [rax+38h], rdi
0x1800088c5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800088cc  mov     ecx, 2; unsigned __int64
0x1800088d1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800088d6  mov     rcx, rax
0x1800088d9  mov     [r13+28h], rax
0x1800088dd  test    rax, rax
0x1800088e0  jz      short loc_18000893D
0x1800088e2  mov     eax, 7FFFFFFEh
0x1800088e7  mov     r9d, 1
0x1800088ed  nop     dword ptr [rax]
0x1800088f0  test    rax, rax
0x1800088f3  jz      short loc_180008911
0x1800088f5  movzx   edx, word ptr [rbx]
0x1800088f8  test    dx, dx
0x1800088fb  jz      short loc_180008911
0x1800088fd  add     rbx, 2
0x180008901  mov     [rcx], dx
0x180008904  add     rcx, 2
0x180008908  dec     rax
0x18000890b  sub     r9, 1
0x18000890f  jnz     short loc_1800088F0
0x180008911  mov     ebx, 8007007Ah
0x180008916  test    r9, r9
0x180008919  cmovnz  ebx, edi
0x18000891c  lea     rax, [rcx-2]
0x180008920  cmovnz  rax, rcx
0x180008924  mov     [rax], di
0x180008927  jz      loc_180008CB1
0x18000892d  cmp     [r13+18h], rdi
0x180008931  jnz     short loc_18000893D
0x180008933  cmp     [r13+30h], edi
0x180008937  jz      loc_180008D07
0x18000893d  mov     [rsp+0C8h+var_50], r13
0x180008942  test    r13, r13
0x180008945  jz      loc_180008DD3
0x18000894b  mov     dword ptr [rsp+0C8h+var_58+4], 1
0x180008953  lea     rcx, [rsp+0C8h+var_48]; unsigned __int16 *
0x18000895b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180008960  test    rax, rax
0x180008963  jz      loc_180008DF1
0x180008969  lea     rcx, [rsp+0C8h+var_48]; unsigned __int16 *
0x180008971  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180008976  mov     rdx, rax; void *
0x180008979  lea     rcx, [rsp+0C8h+var_68]; this
0x18000897e  call    ?Open@CEnum@@QEAAJPEAX@Z; CEnum::Open(void *)
0x180008983  mov     ebx, eax
0x180008985  test    eax, eax
0x180008987  js      loc_180008D52
0x18000898d  lea     r9, [rsp+0C8h+arg_0]; unsigned int *
0x180008995  lea     r8, [rsp+0C8h+hMem]; struct _SESSIONENUM **
0x18000899a  mov     edx, 1; unsigned int
0x18000899f  lea     rcx, [rsp+0C8h+var_68]; this
0x1800089a4  call    ?GetEnumResult@CEnum@@QEAAJKPEAPEAU_SESSIONENUM@@PEAK@Z; CEnum::GetEnumResult(ulong,_SESSIONENUM * *,ulong *)
0x1800089a9  mov     ebx, eax
0x1800089ab  test    eax, eax
0x1800089ad  js      loc_180008CCE
0x1800089b3  lea     rcx, [rsp+0C8h+var_58]; unsigned __int16 *
0x1800089b8  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800089bd  test    rax, rax
0x1800089c0  jnz     loc_180008BF2
0x1800089c6  mov     ecx, [rsp+0C8h+arg_0]
0x1800089cd  add     ecx, [rsp+0C8h+arg_18]
0x1800089d4  imul    eax, ecx, 4Ch ; 'L'
0x1800089d7  test    eax, eax
0x1800089d9  jz      loc_180008E09
0x1800089df  mov     esi, eax
0x1800089e1  mov     edx, eax; uBytes
0x1800089e3  xor     ecx, ecx; uFlags
0x1800089e5  call    cs:__imp_LocalAlloc
0x1800089eb  mov     r15, rax
0x1800089ee  test    rax, rax
0x1800089f1  jz      loc_180008C85
0x1800089f7  mov     rax, 0D79435E50D79435Fh
0x180008a01  mul     rsi
0x180008a04  mov     r14, rdx
0x180008a07  shr     r14, 6
0x180008a0b  mov     r10d, edi
0x180008a0e  test    r14d, r14d
0x180008a11  jz      loc_180008AB5
0x180008a17  nop     word ptr [rax+rax+00000000h]
0x180008a20  cmp     r10d, [rsp+0C8h+arg_0]
0x180008a28  jnb     loc_180008AB5
0x180008a2e  mov     eax, r10d
0x180008a31  imul    rdx, rax, 68h ; 'h'
0x180008a35  imul    r8, rax, 4Ch ; 'L'
0x180008a39  add     r8, r15
0x180008a3c  mov     rax, [rsp+0C8h+hMem]
0x180008a41  mov     ecx, [rdx+rax+4]
0x180008a45  mov     [r8], ecx
0x180008a48  mov     rax, [rsp+0C8h+hMem]
0x180008a4d  mov     ecx, [rdx+rax+8]
0x180008a51  mov     [r8+48h], ecx
0x180008a55  mov     ecx, 7FFFFFFEh
0x180008a5a  mov     r9, [rsp+0C8h+hMem]
0x180008a5f  add     r9, 0Ch
0x180008a63  add     r9, rdx
0x180008a66  mov     edx, 21h ; '!'
0x180008a6b  add     r8, 4
0x180008a6f  nop
0x180008a70  test    rcx, rcx
0x180008a73  jz      short loc_180008A93
0x180008a75  movzx   eax, word ptr [r9]
0x180008a79  test    ax, ax
0x180008a7c  jz      short loc_180008A93
0x180008a7e  add     r9, 2
0x180008a82  mov     [r8], ax
0x180008a86  add     r8, 2
0x180008a8a  dec     rcx
0x180008a8d  sub     rdx, 1
0x180008a91  jnz     short loc_180008A70
0x180008a93  lea     rax, [r8-2]
0x180008a97  test    rdx, rdx
0x180008a9a  cmovnz  rax, r8
0x180008a9e  mov     [rax], di
0x180008aa1  mov     ebx, 8007007Ah
0x180008aa6  cmovnz  ebx, edi
0x180008aa9  inc     r10d
0x180008aac  cmp     r10d, r14d
0x180008aaf  jb      loc_180008A20
0x180008ab5  mov     esi, edi
0x180008ab7  cmp     r10d, r14d
0x180008aba  jnb     loc_180008B70
0x180008ac0  mov     r12d, 8
0x180008ac6  cmp     esi, [rsp+0C8h+arg_18]
0x180008acd  jnb     loc_180008B6B
0x180008ad3  mov     eax, esi
0x180008ad5  lea     r8, [rax+rax*4]
0x180008ad9  shl     r8, 4
0x180008add  mov     eax, r10d
0x180008ae0  imul    rdx, rax, 4Ch ; 'L'
0x180008ae4  add     rdx, r15
0x180008ae7  mov     rax, [rsp+0C8h+var_78]
0x180008aec  mov     ecx, [r8+rax+4]
0x180008af1  mov     [rdx], ecx
0x180008af3  mov     ecx, 6
0x180008af8  mov     rax, [rsp+0C8h+var_78]
0x180008afd  cmp     dword ptr [r8+rax+8], 0
0x180008b03  cmovz   ecx, r12d
0x180008b07  mov     [rdx+48h], ecx
0x180008b0a  mov     r9d, 7FFFFFFEh
0x180008b10  mov     r11, [rsp+0C8h+var_78]
0x180008b15  add     r11, 0Ch
0x180008b19  add     r11, r8
0x180008b1c  mov     ecx, 21h ; '!'
0x180008b21  add     rdx, 4
0x180008b25  test    r9, r9
0x180008b28  jz      short loc_180008B47
0x180008b2a  movzx   eax, word ptr [r11]
0x180008b2e  test    ax, ax
0x180008b31  jz      short loc_180008B47
0x180008b33  add     r11, 2
0x180008b37  mov     [rdx], ax
0x180008b3a  add     rdx, 2
0x180008b3e  dec     r9
0x180008b41  sub     rcx, 1
0x180008b45  jnz     short loc_180008B25
0x180008b47  lea     rax, [rdx-2]
0x180008b4b  test    rcx, rcx
0x180008b4e  cmovnz  rax, rdx
0x180008b52  mov     [rax], di
0x180008b55  mov     ebx, 8007007Ah
0x180008b5a  cmovnz  ebx, edi
0x180008b5d  inc     r10d
0x180008b60  inc     esi
0x180008b62  cmp     r10d, r14d
0x180008b65  jb      loc_180008AC6
0x180008b6b  mov     r12, [rsp+0C8h+var_70]
0x180008b70  mov     rax, [rsp+0C8h+arg_8]
0x180008b78  mov     [rax], r15
0x180008b7b  mov     rax, [rsp+0C8h+arg_10]
0x180008b83  mov     [rax], r14d
0x180008b86  mov     rcx, [rsp+0C8h+hMem]; hMem
0x180008b8b  test    rcx, rcx
0x180008b8e  jz      short loc_180008B96
0x180008b90  call    cs:__imp_LocalFree
0x180008b96  mov     rcx, [rsp+0C8h+var_78]; hMem
0x180008b9b  test    rcx, rcx
0x180008b9e  jnz     short loc_180008BEA
0x180008ba0  cmp     dword ptr [rsp+0C8h+var_58+4], 0
0x180008ba5  jz      short loc_180008BB4
0x180008ba7  test    r13, r13
0x180008baa  jz      short loc_180008BB4
0x180008bac  mov     rcx, r13; Binding
0x180008baf  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x180008bb4  cmp     [rsp+0C8h+var_44], 0
0x180008bbc  jz      short loc_180008BCB
0x180008bbe  test    r12, r12
0x180008bc1  jz      short loc_180008BCB
0x180008bc3  mov     rcx, r12; Binding
0x180008bc6  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x180008bcb  lea     rcx, [rsp+0C8h+var_68]; this
0x180008bd0  call    ??1CEnum@@QEAA@XZ; CEnum::~CEnum(void)
0x180008bd5  mov     eax, ebx
0x180008bd7  add     rsp, 90h
0x180008bde  pop     r15
0x180008be0  pop     r14
0x180008be2  pop     r13
0x180008be4  pop     r12
0x180008be6  pop     rdi
0x180008be7  pop     rsi
0x180008be8  pop     rbx
0x180008be9  retn
0x180008bea  call    cs:__imp_LocalFree
0x180008bf0  jmp     short loc_180008BA0
0x180008bf2  lea     rcx, [rsp+0C8h+var_58]; unsigned __int16 *
0x180008bf7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
  ... truncated ...
```
