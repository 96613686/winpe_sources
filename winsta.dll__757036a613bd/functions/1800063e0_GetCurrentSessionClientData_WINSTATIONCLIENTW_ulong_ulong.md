# GetCurrentSessionClientData(_WINSTATIONCLIENTW *,ulong,ulong *)

- ea: `0x1800063e0`
- end: `0x18000679b`
- name: `?GetCurrentSessionClientData@@YAJPEAU_WINSTATIONCLIENTW@@KPEAK@Z`
- size: `955`
- prototype: `__int64 __fastcall(struct _WINSTATIONCLIENTW *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18000b2b0`
- `0x18000c820`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x1800063e0`
- `0x180007890`
- `0x180008150`
- `0x180008200`
- `0x180008340`
- `0x18001f5f8`
- `0x1800230b8`
- `0x1800230ec`
- `0x180024376`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000675f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000675f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000670c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000670c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006632`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006632`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003020e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003020e`
- `RPCRT4!NdrClientCall3` at `0x180006571`
- `RPCRT4!NdrClientCall3` at `0x180006571`

## string_xrefs

- `0x180006670`: `StringCchCopy failed: %x`

## pseudocode

```c
__int64 __fastcall GetCurrentSessionClientData(struct _WINSTATIONCLIENTW *a1, unsigned int a2, unsigned int *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // r12
  _WORD *v9; // rcx
  __int64 v10; // rax
  int *v11; // r8
  __int16 v12; // r9
  int v13; // ebx
  _WORD *v14; // rax
  int v15; // r13d
  _QWORD *v16; // rbx
  void *UnifiedRpcBinding; // rax
  void *RCMBinding; // rax
  CLIENT_CALL_RETURN v19; // rbx
  __int64 v20; // rax
  _BYTE *v21; // rax
  __int64 v22; // rdx
  __int64 v24; // rax
  char *v25; // rdi
  signed int LastError; // eax
  int v27; // [rsp+30h] [rbp-58h]
  HLOCAL hMem[2]; // [rsp+38h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v29; // [rsp+48h] [rbp-40h]
  size_t Size; // [rsp+A8h] [rbp+20h] BYREF

  hMem[0] = 0;
  LODWORD(Size) = 0;
  v6 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v6;
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
    v9 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v8[5] = v9;
    if ( v9 )
    {
      v10 = 2147483646;
      v11 = &dword_18003D0CC;
      v7 = 1;
      do
      {
        if ( !v10 )
          break;
        v12 = *(_WORD *)v11;
        if ( !*(_WORD *)v11 )
          break;
        v11 = (int *)((char *)v11 + 2);
        *v9++ = v12;
        --v10;
        --v7;
      }
      while ( v7 );
      v13 = -2147024774;
      if ( v7 )
        v13 = 0;
      v14 = v9 - 1;
      if ( v7 )
        v14 = v9;
      *v14 = 0;
      if ( v7 )
      {
        if ( !v8[3] && !*((_DWORD *)v8 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v8) == -2147023174 )
            *((_DWORD *)v8 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v8);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v13);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v13);
      }
    }
  }
  else
  {
    v8 = 0;
  }
  hMem[1] = v8;
  if ( v8 )
  {
    v15 = 1;
    v27 = 1;
  }
  else
  {
    v15 = 0;
    v27 = 0;
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  *a3 = 0;
  if ( a2 < 0x8F8 )
  {
    LODWORD(v19.Pointer) = -2147024809;
  }
  else
  {
    v16 = v8 + 3;
    if ( v8 )
    {
      if ( *v16 )
        UnifiedRpcBinding = CPublicBinding::GetUnifiedRpcBinding((CPublicBinding *)v8);
      else
        UnifiedRpcBinding = CPublicBinding::GetRCMBinding((CPublicBinding *)v8);
    }
    else
    {
      UnifiedRpcBinding = 0;
    }
    if ( UnifiedRpcBinding )
    {
      if ( v8 )
      {
        if ( *v16 )
          RCMBinding = CPublicBinding::GetUnifiedRpcBinding((CPublicBinding *)v8);
        else
          RCMBinding = CPublicBinding::GetRCMBinding((CPublicBinding *)v8);
      }
      else
      {
        RCMBinding = 0;
      }
      v29.Simple = 0;
      v19.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180032080, 1u, 0, RCMBinding, hMem, &Size, v27).Pointer;
      v29.Pointer = v19.Pointer;
      if ( LODWORD(v19.Pointer) == -2147022646
        || LODWORD(v19.Pointer) == -2147023174
        || LODWORD(v19.Pointer) == -2147023179 )
      {
        *a3 = a2;
        v20 = a2;
        do
        {
          *(_BYTE *)a1 = 0;
          a1 = (struct _WINSTATIONCLIENTW *)((char *)a1 + 1);
          --v20;
        }
        while ( v20 );
        LODWORD(v19.Pointer) = 0;
      }
      else if ( SLODWORD(v19.Simple) < 0 )
      {
        _DbgPrintMessage(
          8,
          "RpcGetCurrentSessionClientData failed: 0x%x in %s",
          LODWORD(v19.Pointer),
          "GetCurrentSessionClientData");
      }
      else
      {
        if ( (unsigned int)Size < a2 )
          a2 = Size;
        memcpy_0(a1, hMem[0], a2);
        v24 = 30;
        v25 = (char *)a1 + 124;
        do
        {
          *v25++ = 0;
          --v24;
        }
        while ( v24 );
        *a3 = Size;
      }
    }
    else
    {
      LastError = GetLastError();
      LODWORD(v19.Pointer) = LastError;
      if ( LastError > 0 )
        LODWORD(v19.Pointer) = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v21 = hMem[0];
  if ( hMem[0] )
  {
    v22 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v21++ = 0;
        --v22;
      }
      while ( v22 );
    }
    LocalFree(hMem[0]);
  }
  if ( v15 && v8 )
    CPublicBinding::`scalar deleting destructor'((RPC_BINDING_HANDLE *)v8, v7);
  return LODWORD(v19.Pointer);
}

```

## disassembly

```asm
0x1800063e0  mov     rax, rsp
0x1800063e3  mov     [rax+18h], r8
0x1800063e7  mov     [rax+10h], edx
0x1800063ea  mov     [rax+8], rcx
0x1800063ee  push    rbx
0x1800063ef  push    rsi
0x1800063f0  push    rdi
0x1800063f1  push    r12
0x1800063f3  push    r13
0x1800063f5  push    r14
0x1800063f7  push    r15
0x1800063f9  sub     rsp, 50h
0x1800063fd  mov     r14, r8
0x180006400  mov     esi, edx
0x180006402  mov     rdi, rcx
0x180006405  xor     r15d, r15d
0x180006408  mov     [rax-50h], r15
0x18000640c  mov     [rax+20h], r15d
0x180006410  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006417  mov     ecx, 40h ; '@'; unsigned __int64
0x18000641c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006421  mov     r12, rax
0x180006424  test    rax, rax
0x180006427  jz      loc_18000674A
0x18000642d  mov     [rax], r15
0x180006430  mov     [rax+8], r15
0x180006434  mov     [rax+10h], r15
0x180006438  mov     [rax+18h], r15
0x18000643c  mov     [rax+20h], r15
0x180006440  mov     [rax+28h], r15
0x180006444  mov     qword ptr [rax+30h], 1
0x18000644c  mov     [rax+38h], r15
0x180006450  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006457  mov     ecx, 2; unsigned __int64
0x18000645c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006461  mov     rcx, rax
0x180006464  mov     [r12+28h], rax
0x180006469  test    rax, rax
0x18000646c  jz      short loc_1800064D4
0x18000646e  mov     eax, 7FFFFFFEh
0x180006473  lea     r8, dword_18003D0CC
0x18000647a  mov     edx, 1
0x18000647f  nop
0x180006480  test    rax, rax
0x180006483  jz      short loc_1800064A4
0x180006485  movzx   r9d, word ptr [r8]
0x180006489  test    r9w, r9w
0x18000648d  jz      short loc_1800064A4
0x18000648f  add     r8, 2
0x180006493  mov     [rcx], r9w
0x180006497  add     rcx, 2
0x18000649b  dec     rax
0x18000649e  sub     rdx, 1
0x1800064a2  jnz     short loc_180006480
0x1800064a4  mov     ebx, 8007007Ah
0x1800064a9  test    rdx, rdx
0x1800064ac  cmovnz  ebx, r15d
0x1800064b0  lea     rax, [rcx-2]
0x1800064b4  cmovnz  rax, rcx
0x1800064b8  mov     [rax], r15w
0x1800064bc  jz      loc_180006666
0x1800064c2  cmp     [r12+18h], r15
0x1800064c7  jnz     short loc_1800064D4
0x1800064c9  cmp     [r12+30h], r15d
0x1800064ce  jz      loc_180006686
0x1800064d4  mov     [rsp+88h+var_48], r12
0x1800064d9  test    r12, r12
0x1800064dc  jz      loc_180006752
0x1800064e2  mov     r13d, 1
0x1800064e8  mov     [rsp+88h+var_58], r13d
0x1800064ed  mov     [r14], r15d
0x1800064f0  cmp     esi, 8F8h
0x1800064f6  jb      loc_180006732
0x1800064fc  lea     rbx, [r12+18h]
0x180006501  test    r12, r12
0x180006504  jz      loc_18000672A
0x18000650a  mov     rcx, r12; this
0x18000650d  cmp     [rbx], r15
0x180006510  jz      loc_18000665C
0x180006516  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x18000651b  test    rax, rax
0x18000651e  jz      loc_18000670C
0x180006524  test    r12, r12
0x180006527  jz      short loc_180006540
0x180006529  mov     rcx, r12; this
0x18000652c  cmp     qword ptr [rbx], 0
0x180006530  jz      short loc_180006539
0x180006532  call    ?GetUnifiedRpcBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetUnifiedRpcBinding(void)
0x180006537  jmp     short loc_180006543
0x180006539  call    ?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetRCMBinding(void)
0x18000653e  jmp     short loc_180006543
0x180006540  mov     rax, r15
0x180006543  mov     [rsp+88h+var_40], r15
0x180006548  lea     rcx, [rsp+88h+Size]
0x180006550  mov     [rsp+88h+var_60], rcx
0x180006555  lea     rcx, [rsp+88h+hMem]
0x18000655a  mov     [rsp+88h+var_68], rcx
0x18000655f  mov     r9, rax
0x180006562  xor     r8d, r8d; pReturnValue
0x180006565  mov     edx, 1; nProcNum
0x18000656a  lea     rcx, stru_180032080; pProxyInfo
0x180006571  call    cs:__imp_NdrClientCall3
0x180006577  mov     rbx, rax
0x18000657a  mov     [rsp+88h+var_40], rax
0x18000657f  mov     [rsp+88h+var_54], eax
0x180006583  jmp     short loc_1800065CF
0x180006585  test    eax, eax
0x180006587  jle     short loc_180006591
0x180006589  movzx   eax, ax
0x18000658c  or      eax, 80070000h
0x180006591  mov     ebx, eax
0x180006593  mov     [rsp+88h+var_54], eax
0x180006597  mov     r8d, eax
0x18000659a  lea     rdx, aRpcgetcurrents_5; "RpcGetCurrentSessionClientData threw an"...
0x1800065a1  mov     ecx, 8; int
0x1800065a6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800065ab  xor     r15d, r15d
0x1800065ae  mov     r14, [rsp+88h+arg_10]
0x1800065b6  mov     esi, [rsp+88h+arg_8]
0x1800065bd  mov     rdi, [rsp+88h+arg_0]
0x1800065c5  mov     r12, [rsp+88h+var_48]
0x1800065ca  mov     r13d, [rsp+88h+var_58]
0x1800065cf  cmp     ebx, 800708CAh
0x1800065d5  jnz     loc_1800066A6
0x1800065db  mov     [r14], esi
0x1800065de  mov     eax, esi
0x1800065e0  test    esi, esi
0x1800065e2  jz      short loc_1800065FD
0x1800065e4  nop     dword ptr [rax+00h]
0x1800065e8  nop     dword ptr [rax+rax+00000000h]
0x1800065f0  mov     byte ptr [rdi], 0
0x1800065f3  lea     rdi, [rdi+1]
0x1800065f7  sub     rax, 1
0x1800065fb  jnz     short loc_1800065F0
0x1800065fd  mov     ebx, r15d
0x180006600  mov     rax, [rsp+88h+hMem]
0x180006605  test    rax, rax
0x180006608  jz      short loc_180006638
0x18000660a  mov     edx, dword ptr [rsp+88h+Size]
0x180006611  test    rdx, rdx
0x180006614  jz      short loc_18000662D
0x180006616  nop     word ptr [rax+rax+00000000h]
0x180006620  mov     byte ptr [rax], 0
0x180006623  lea     rax, [rax+1]
0x180006627  sub     rdx, 1
0x18000662b  jnz     short loc_180006620
0x18000662d  mov     rcx, [rsp+88h+hMem]; hMem
0x180006632  call    cs:__imp_LocalFree
0x180006638  test    r13d, r13d
0x18000663b  jz      short loc_18000664A
0x18000663d  test    r12, r12
0x180006640  jz      short loc_18000664A
0x180006642  mov     rcx, r12; Binding
0x180006645  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x18000664a  mov     eax, ebx
0x18000664c  add     rsp, 50h
0x180006650  pop     r15
0x180006652  pop     r14
0x180006654  pop     r13
0x180006656  pop     r12
0x180006658  pop     rdi
0x180006659  pop     rsi
0x18000665a  pop     rbx
0x18000665b  retn
0x18000665c  call    ?GetRCMBinding@CPublicBinding@@QEAAPEAXXZ; CPublicBinding::GetRCMBinding(void)
0x180006661  jmp     loc_18000651B
0x180006666  mov     ecx, ebx; int
0x180006668  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000666d  mov     r8d, ebx
0x180006670  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180006677  mov     ecx, 8; int
0x18000667c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006681  jmp     loc_1800064D4
0x180006686  mov     rcx, r12; this
0x180006689  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000668e  cmp     eax, 800706BAh
0x180006693  jz      loc_18000673C
0x180006699  mov     rcx, r12; this
0x18000669c  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x1800066a1  jmp     loc_1800064D4
0x1800066a6  cmp     ebx, 800706BAh
0x1800066ac  jz      loc_1800065DB
0x1800066b2  cmp     ebx, 800706B5h
0x1800066b8  jz      loc_1800065DB
0x1800066be  test    ebx, ebx
0x1800066c0  js      loc_18000677B
0x1800066c6  cmp     dword ptr [rsp+88h+Size], esi
0x1800066cd  cmovb   esi, dword ptr [rsp+88h+Size]
0x1800066d5  mov     r8d, esi; Size
0x1800066d8  mov     rdx, [rsp+88h+hMem]; Src
0x1800066dd  mov     rcx, rdi; void *
0x1800066e0  call    memcpy_0
0x1800066e5  mov     eax, 1Eh
0x1800066ea  add     rdi, 7Ch ; '|'
0x1800066ee  xchg    ax, ax
0x1800066f0  mov     byte ptr [rdi], 0
0x1800066f3  lea     rdi, [rdi+1]
0x1800066f7  sub     rax, 1
0x1800066fb  jnz     short loc_1800066F0
0x1800066fd  mov     eax, dword ptr [rsp+88h+Size]
0x180006704  mov     [r14], eax
0x180006707  jmp     loc_180006600
0x18000670c  call    cs:__imp_GetLastError
0x180006712  mov     ebx, eax
0x180006714  test    eax, eax
0x180006716  jle     loc_180006600
0x18000671c  movzx   ebx, ax
0x18000671f  or      ebx, 80070000h
0x180006725  jmp     loc_180006600
0x18000672a  mov     rax, r15
0x18000672d  jmp     loc_18000651B
0x180006732  mov     ebx, 80070057h
0x180006737  jmp     loc_180006600
0x18000673c  mov     dword ptr [r12+34h], 1
0x180006745  jmp     loc_180006699
0x18000674a  mov     r12, r15
0x18000674d  jmp     loc_1800064D4
0x180006752  mov     r13d, r15d
0x180006755  mov     [rsp+88h+var_58], r15d
0x18000675a  mov     ecx, 0Eh; dwErrCode
0x18000675f  call    cs:__imp_SetLastError
0x180006765  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000676c  mov     ecx, 8; int
0x180006771  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006776  jmp     loc_1800064ED
0x18000677b  lea     r9, aGetcurrentsess_4; "GetCurrentSessionClientData"
0x180006782  mov     r8d, ebx
0x180006785  lea     rdx, aRpcgetcurrents_13; "RpcGetCurrentSessionClientData failed: "...
0x18000678c  mov     ecx, 8; int
0x180006791  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180006796  jmp     loc_180006600
0x180030200  push    rbp
0x180030202  sub     rsp, 30h
0x180030206  mov     rbp, rdx
0x180030209  mov     rcx, [rcx]
0x18003020c  mov     ecx, [rcx]; ExceptionCode
0x18003020e  call    cs:__imp_I_RpcExceptionFilter
0x180030214  nop
0x180030215  add     rsp, 30h
0x180030219  pop     rbp
0x18003021a  retn
```
