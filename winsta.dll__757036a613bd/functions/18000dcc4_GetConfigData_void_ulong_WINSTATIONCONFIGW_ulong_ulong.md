# GetConfigData(void *,ulong,_WINSTATIONCONFIGW *,ulong,ulong *)

- ea: `0x18000dcc4`
- end: `0x18000e013`
- name: `?GetConfigData@@YAJPEAXKPEAU_WINSTATIONCONFIGW@@KPEAK@Z`
- size: `847`
- prototype: `int(void *, unsigned int, struct _WINSTATIONCONFIGW *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000ce54`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x18000dcc4`
- `0x1800230b8`
- `0x1800230ec`
- `0x180024376`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dde2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000de26`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800305b2`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800305b2`
- `RPCRT4!NdrClientCall3` at `0x18000dec0`
- `RPCRT4!NdrClientCall3` at `0x18000dec0`

## string_xrefs

- `0x18000de4e`: `StringCchCopy failed: %x`
- `0x18000df16`: `RpcGetConfigData threw an exception: 0x%x`
- `0x18000dff3`: `GetConfigData`
- `0x18000dffd`: `RpcGetConfigData failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetConfigData(void *a1, int a2, struct _WINSTATIONCONFIGW *a3, unsigned int a4, unsigned int *a5)
{
  size_t v5; // r14
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _WORD *v9; // rcx
  __int64 v10; // rax
  int *v11; // r8
  __int64 v12; // rdx
  __int16 v13; // r9
  int v14; // edi
  _WORD *v15; // rax
  signed int LastError; // eax
  CLIENT_CALL_RETURN v17; // rbx
  _BYTE *v18; // rax
  __int64 v19; // rcx
  __int64 v21; // rax
  unsigned int v22; // edi
  HLOCAL hMem; // [rsp+48h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+50h] [rbp-48h]
  __int64 v25; // [rsp+58h] [rbp-40h] BYREF
  void *v26; // [rsp+60h] [rbp-38h]
  size_t Size; // [rsp+A0h] [rbp+8h] BYREF
  void *v28; // [rsp+B0h] [rbp+18h]
  size_t v29; // [rsp+B8h] [rbp+20h]

  LODWORD(v29) = a4;
  v28 = a3;
  v5 = a4;
  hMem = 0;
  LODWORD(Size) = 0;
  v25 = 1;
  if ( a1 )
  {
    v26 = a1;
  }
  else
  {
    v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      *v7 = 0;
      v7[1] = 0;
      v7[2] = 0;
      v7[3] = 0;
      v7[4] = 0;
      v7[5] = 0;
      v7[6] = 1;
      v7[7] = 0;
      v9 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v8[5] = v9;
      if ( v9 )
      {
        v10 = 2147483646;
        v11 = &dword_18003D0CC;
        v12 = 1;
        do
        {
          if ( !v10 )
            break;
          v13 = *(_WORD *)v11;
          if ( !*(_WORD *)v11 )
            break;
          v11 = (int *)((char *)v11 + 2);
          *v9++ = v13;
          --v10;
          --v12;
        }
        while ( v12 );
        v14 = v12 == 0 ? 0x8007007A : 0;
        v15 = v9 - 1;
        if ( v12 )
          v15 = v9;
        *v15 = 0;
        if ( v12 )
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
          ConvertHRESULT2WIN32(v14);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v14);
        }
      }
    }
    else
    {
      v8 = 0;
    }
    v26 = v8;
    if ( v8 )
    {
      HIDWORD(v25) = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( !CSmartPublicBinding::operator void *((unsigned __int16 *)&v25) )
  {
    LastError = GetLastError();
    LODWORD(v17.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v17.Pointer) = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    if ( SLODWORD(v17.Simple) < 0 )
      goto LABEL_19;
    goto LABEL_31;
  }
  v21 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v25);
  v24.Simple = 0;
  v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0, 1u, 0, v21, a2, &hMem, &Size).Pointer;
  v24.Pointer = v17.Pointer;
  if ( LODWORD(v17.Pointer) == -2147022646 )
  {
    *a5 = v5;
    memset_0(v28, 0, v5);
    LODWORD(v17.Pointer) = 0;
  }
  if ( SLODWORD(v17.Simple) < 0 )
  {
    _DbgPrintMessage(8, "RpcGetConfigData failed: 0x%x in %s", LODWORD(v17.Pointer), "GetConfigData");
    goto LABEL_18;
  }
LABEL_31:
  if ( hMem )
  {
    v22 = Size;
    if ( (unsigned int)Size < (unsigned int)v5 )
      LODWORD(v5) = Size;
    memcpy_0(v28, hMem, (unsigned int)v5);
    *a5 = v22;
  }
LABEL_19:
  v18 = hMem;
  if ( hMem )
  {
    v19 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v18++ = 0;
        --v19;
      }
      while ( v19 );
    }
    LocalFree(hMem);
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v25);
  return LODWORD(v17.Pointer);
}

```

## disassembly

```asm
0x18000dcc4  mov     rax, rsp
0x18000dcc7  mov     [rax+20h], r9d
0x18000dccb  mov     [rax+18h], r8
0x18000dccf  push    rbx
0x18000dcd0  push    rsi
0x18000dcd1  push    rdi
0x18000dcd2  push    r12
0x18000dcd4  push    r14
0x18000dcd6  sub     rsp, 70h
0x18000dcda  mov     r14d, r9d
0x18000dcdd  mov     r12d, edx
0x18000dce0  xor     esi, esi
0x18000dce2  mov     [rax-50h], rsi
0x18000dce6  mov     [rax+8], esi
0x18000dce9  mov     qword ptr [rax-40h], 1
0x18000dcf1  test    rcx, rcx
0x18000dcf4  jnz     loc_18000DFB4
0x18000dcfa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dd01  lea     ecx, [rsi+40h]; unsigned __int64
0x18000dd04  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dd09  mov     rbx, rax
0x18000dd0c  test    rax, rax
0x18000dd0f  jz      loc_18000DFCA
0x18000dd15  mov     [rax], rsi
0x18000dd18  mov     [rax+8], rsi
0x18000dd1c  mov     [rax+10h], rsi
0x18000dd20  mov     [rax+18h], rsi
0x18000dd24  mov     [rax+20h], rsi
0x18000dd28  mov     [rax+28h], rsi
0x18000dd2c  mov     qword ptr [rax+30h], 1
0x18000dd34  mov     [rax+38h], rsi
0x18000dd38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dd3f  lea     ecx, [rsi+2]; unsigned __int64
0x18000dd42  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000dd47  mov     rcx, rax
0x18000dd4a  mov     [rbx+28h], rax
0x18000dd4e  test    rax, rax
0x18000dd51  jz      short loc_18000DDB9
0x18000dd53  mov     eax, 7FFFFFFEh
0x18000dd58  lea     r8, dword_18003D0CC
0x18000dd5f  lea     edx, [rsi+1]
0x18000dd62  test    rax, rax
0x18000dd65  jz      short loc_18000DD86
0x18000dd67  movzx   r9d, word ptr [r8]
0x18000dd6b  test    r9w, r9w
0x18000dd6f  jz      short loc_18000DD86
0x18000dd71  add     r8, 2
0x18000dd75  mov     [rcx], r9w
0x18000dd79  add     rcx, 2
0x18000dd7d  dec     rax
0x18000dd80  sub     rdx, 1
0x18000dd84  jnz     short loc_18000DD62
0x18000dd86  mov     rax, rdx
0x18000dd89  neg     rax
0x18000dd8c  sbb     edi, edi
0x18000dd8e  not     edi
0x18000dd90  and     edi, 8007007Ah
0x18000dd96  lea     rax, [rcx-2]
0x18000dd9a  test    rdx, rdx
0x18000dd9d  cmovnz  rax, rcx
0x18000dda1  mov     [rax], si
0x18000dda4  jz      loc_18000DE44
0x18000ddaa  cmp     [rbx+18h], rsi
0x18000ddae  jnz     short loc_18000DDB9
0x18000ddb0  cmp     [rbx+30h], esi
0x18000ddb3  jz      loc_18000DE64
0x18000ddb9  mov     [rsp+98h+var_38], rbx
0x18000ddbe  test    rbx, rbx
0x18000ddc1  jz      loc_18000DFD2
0x18000ddc7  mov     [rsp+98h+var_3C], 1
0x18000ddcf  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x18000ddd4  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000ddd9  test    rax, rax
0x18000dddc  jnz     loc_18000DE84
0x18000dde2  call    cs:__imp_GetLastError
0x18000dde8  mov     ebx, eax
0x18000ddea  test    eax, eax
0x18000ddec  jle     short loc_18000DDF7
0x18000ddee  movzx   ebx, ax
0x18000ddf1  or      ebx, 80070000h
0x18000ddf7  test    ebx, ebx
0x18000ddf9  jns     loc_18000DF49
0x18000ddff  mov     rax, [rsp+98h+hMem]
0x18000de04  test    rax, rax
0x18000de07  jz      short loc_18000DE2C
0x18000de09  mov     ecx, dword ptr [rsp+98h+Size]
0x18000de10  test    rcx, rcx
0x18000de13  jz      short loc_18000DE21
0x18000de15  mov     [rax], sil
0x18000de18  inc     rax
0x18000de1b  sub     rcx, 1
0x18000de1f  jnz     short loc_18000DE15
0x18000de21  mov     rcx, [rsp+98h+hMem]; hMem
0x18000de26  call    cs:__imp_LocalFree
0x18000de2c  lea     rcx, [rsp+98h+var_40]; this
0x18000de31  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000de36  mov     eax, ebx
0x18000de38  add     rsp, 70h
0x18000de3c  pop     r14
0x18000de3e  pop     r12
0x18000de40  pop     rdi
0x18000de41  pop     rsi
0x18000de42  pop     rbx
0x18000de43  retn
0x18000de44  mov     ecx, edi; int
0x18000de46  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000de4b  mov     r8d, edi
0x18000de4e  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x18000de55  mov     ecx, 8; int
0x18000de5a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000de5f  jmp     loc_18000DDB9
0x18000de64  mov     rcx, rbx; this
0x18000de67  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000de6c  cmp     eax, 800706BAh
0x18000de71  jz      loc_18000DFBE
0x18000de77  mov     rcx, rbx; this
0x18000de7a  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000de7f  jmp     loc_18000DDB9
0x18000de84  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x18000de89  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000de8e  mov     [rsp+98h+var_48], rsi
0x18000de93  lea     rcx, [rsp+98h+Size]
0x18000de9b  mov     [rsp+98h+var_68], rcx
0x18000dea0  lea     rcx, [rsp+98h+hMem]
0x18000dea5  mov     [rsp+98h+var_70], rcx
0x18000deaa  mov     [rsp+98h+var_78], r12d
0x18000deaf  mov     r9, rax
0x18000deb2  xor     r8d, r8d; pReturnValue
0x18000deb5  lea     edx, [r8+1]; nProcNum
0x18000deb9  lea     rcx, stru_1800320E0; pProxyInfo
0x18000dec0  call    cs:__imp_NdrClientCall3
0x18000dec6  mov     rbx, rax
0x18000dec9  mov     [rsp+98h+var_48], rax
0x18000dece  mov     [rsp+98h+var_58], eax
0x18000ded2  cmp     eax, 800708CAh
0x18000ded7  jnz     short loc_18000DEFC
0x18000ded9  mov     rax, [rsp+98h+arg_20]
0x18000dee1  mov     [rax], r14d
0x18000dee4  mov     r8, r14; Size
0x18000dee7  xor     edx, edx; Val
0x18000dee9  mov     rcx, [rsp+98h+arg_10]; void *
0x18000def1  call    memset_0
0x18000def6  mov     ebx, esi
0x18000def8  mov     [rsp+98h+var_58], ebx
0x18000defc  jmp     short loc_18000DF41
0x18000defe  mov     edi, eax
0x18000df00  test    eax, eax
0x18000df02  jle     short loc_18000DF0D
0x18000df04  movzx   edi, ax
0x18000df07  or      edi, 80070000h
0x18000df0d  mov     ebx, edi
0x18000df0f  mov     [rsp+98h+var_58], ebx
0x18000df13  mov     r8d, edi
0x18000df16  lea     rdx, aRpcgetconfigda; "RpcGetConfigData threw an exception: 0x"...
0x18000df1d  mov     ecx, 8; int
0x18000df22  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000df27  cmp     edi, 800706B5h
0x18000df2d  jz      short loc_18000DF87
0x18000df2f  cmp     edi, 800706BAh
0x18000df35  jz      short loc_18000DF87
0x18000df37  mov     r14d, dword ptr [rsp+98h+arg_18]
0x18000df3f  xor     esi, esi
0x18000df41  test    ebx, ebx
0x18000df43  js      loc_18000DFF3
0x18000df49  mov     rax, [rsp+98h+hMem]
0x18000df4e  test    rax, rax
0x18000df51  jz      loc_18000DDFF
0x18000df57  mov     edi, dword ptr [rsp+98h+Size]
0x18000df5e  cmp     edi, r14d
0x18000df61  cmovb   r14d, edi
0x18000df65  mov     r8d, r14d; Size
0x18000df68  mov     rdx, rax; Src
0x18000df6b  mov     rcx, [rsp+98h+arg_10]; void *
0x18000df73  call    memcpy_0
0x18000df78  mov     rax, [rsp+98h+arg_20]
0x18000df80  mov     [rax], edi
0x18000df82  jmp     loc_18000DDFF
0x18000df87  mov     r14d, dword ptr [rsp+98h+arg_18]
0x18000df8f  mov     rax, [rsp+98h+arg_20]
0x18000df97  mov     [rax], r14d
0x18000df9a  mov     r8d, r14d; Size
0x18000df9d  xor     edx, edx; Val
0x18000df9f  mov     rcx, [rsp+98h+arg_10]; void *
0x18000dfa7  call    memset_0
0x18000dfac  xor     ebx, ebx
0x18000dfae  mov     [rsp+98h+var_58], ebx
0x18000dfb2  jmp     short loc_18000DF3F
0x18000dfb4  mov     [rsp+98h+var_38], rcx
0x18000dfb9  jmp     loc_18000DDCF
0x18000dfbe  mov     dword ptr [rbx+34h], 1
0x18000dfc5  jmp     loc_18000DE77
0x18000dfca  mov     rbx, rsi
0x18000dfcd  jmp     loc_18000DDB9
0x18000dfd2  mov     ecx, 0Eh; dwErrCode
0x18000dfd7  call    cs:__imp_SetLastError
0x18000dfdd  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000dfe4  mov     ecx, 8; int
0x18000dfe9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000dfee  jmp     loc_18000DDCF
0x18000dff3  lea     r9, aGetconfigdata; "GetConfigData"
0x18000dffa  mov     r8d, ebx
0x18000dffd  lea     rdx, aRpcgetconfigda_0; "RpcGetConfigData failed: 0x%x in %s"
0x18000e004  mov     ecx, 8; int
0x18000e009  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e00e  jmp     loc_18000DDF7
0x1800305a4  push    rbp
0x1800305a6  sub     rsp, 40h
0x1800305aa  mov     rbp, rdx
0x1800305ad  mov     rcx, [rcx]
0x1800305b0  mov     ecx, [rcx]; ExceptionCode
0x1800305b2  call    cs:__imp_I_RpcExceptionFilter
0x1800305b8  nop
0x1800305b9  add     rsp, 40h
0x1800305bd  pop     rbp
0x1800305be  retn
```
