# GetSessionProtocolLastInputTime(void *,ulong,_PROTOCOLSTATUS *,_LARGE_INTEGER *)

- ea: `0x180007fe0`
- end: `0x180008372`
- name: `?GetSessionProtocolLastInputTime@@YAJPEAXKPEAU_PROTOCOLSTATUS@@PEAT_LARGE_INTEGER@@@Z`
- size: `914`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _PROTOCOLSTATUS *, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003480`
- `0x1800049a0`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x180007fe0`
- `0x1800249e8`
- `0x180024a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008314`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008361`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008361`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800330fe`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800330fe`
- `RPCRT4!NdrClientCall3` at `0x180008150`
- `RPCRT4!NdrClientCall3` at `0x180008150`

## string_xrefs

- `0x1800081d9`: `StringCchCopy failed: %x`
- `0x18000817f`: `RpcGetSessionProtocolLastInputTime failed: 0x%x`
- `0x180008346`: `RpcGetProtocolStatus returned %d bytes, expected %d`

## pseudocode

```c
__int64 __fastcall GetSessionProtocolLastInputTime(
        void *a1,
        int a2,
        struct _PROTOCOLSTATUS *a3,
        union _LARGE_INTEGER *a4)
{
  struct _PROTOCOLSTATUS *v5; // rsi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _WORD *v9; // r9
  __int64 v10; // rcx
  int *v11; // rdx
  __int64 v12; // r10
  __int16 v13; // ax
  int v14; // edi
  _WORD *v15; // rcx
  __int64 v16; // rax
  CLIENT_CALL_RETURN v17; // rbx
  HLOCAL v18; // rcx
  _OWORD *v20; // rax
  __int64 v21; // rdx
  signed int LastError; // eax
  HLOCAL hMem; // [rsp+58h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+60h] [rbp-48h]
  __int64 v25; // [rsp+68h] [rbp-40h] BYREF
  void *v26; // [rsp+70h] [rbp-38h]
  unsigned int v27; // [rsp+B0h] [rbp+8h] BYREF
  struct _PROTOCOLSTATUS *v28; // [rsp+C0h] [rbp+18h]

  v28 = a3;
  v5 = a3;
  hMem = 0;
  v27 = 0;
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
          *v9++ = v13;
          --v10;
          --v12;
        }
        while ( v12 );
        v14 = -2147024774;
        if ( v12 )
          v14 = 0;
        v15 = v9 - 1;
        if ( v12 )
          v15 = v9;
        *v15 = 0;
        if ( v12 )
        {
          if ( !v8[3] && !*((_DWORD *)v8 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((CPublicBinding *)v8) == -2147023174 )
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
    goto LABEL_19;
  }
  v16 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v25);
  v24.Simple = 0;
  v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035078, 9u, 0, v16, a2, 0, &hMem, &v27, a4).Pointer;
  v24.Pointer = v17.Pointer;
  if ( SLODWORD(v17.Simple) < 0 )
  {
LABEL_19:
    v18 = hMem;
    goto LABEL_20;
  }
  v18 = hMem;
  if ( hMem )
  {
    if ( v27 < 0x3F4 )
    {
      _DbgPrintMessage(8, "RpcGetProtocolStatus returned %d bytes, expected %d", v27, 1012);
      LODWORD(v17.Pointer) = -2147024809;
      goto LABEL_19;
    }
    v20 = hMem;
    v21 = 7;
    do
    {
      *(_OWORD *)v5 = *v20;
      *((_OWORD *)v5 + 1) = v20[1];
      *((_OWORD *)v5 + 2) = v20[2];
      *((_OWORD *)v5 + 3) = v20[3];
      *((_OWORD *)v5 + 4) = v20[4];
      *((_OWORD *)v5 + 5) = v20[5];
      *((_OWORD *)v5 + 6) = v20[6];
      *((_OWORD *)v5 + 7) = v20[7];
      v5 = (struct _PROTOCOLSTATUS *)((char *)v5 + 128);
      v20 += 8;
      --v21;
    }
    while ( v21 );
    *(_OWORD *)v5 = *v20;
    *((_OWORD *)v5 + 1) = v20[1];
    *((_OWORD *)v5 + 2) = v20[2];
    *((_OWORD *)v5 + 3) = v20[3];
    *((_OWORD *)v5 + 4) = v20[4];
    *((_OWORD *)v5 + 5) = v20[5];
    *((_OWORD *)v5 + 6) = v20[6];
    *((_DWORD *)v5 + 28) = *((_DWORD *)v20 + 28);
  }
  else
  {
    LODWORD(v17.Pointer) = -2147467261;
  }
LABEL_20:
  if ( v18 )
    LocalFree(v18);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v25);
  return LODWORD(v17.Pointer);
}

```

## disassembly

```asm
0x180007fe0  mov     rax, rsp
0x180007fe3  mov     [rax+10h], rbx
0x180007fe7  mov     [rax+18h], r8
0x180007feb  push    rsi
0x180007fec  push    rdi
0x180007fed  push    r12
0x180007fef  push    r14
0x180007ff1  push    r15
0x180007ff3  sub     rsp, 80h
0x180007ffa  mov     r14, r9
0x180007ffd  mov     rsi, r8
0x180008000  mov     r15d, edx
0x180008003  xor     r12d, r12d
0x180008006  mov     [rax-50h], r12
0x18000800a  mov     [rax+8], r12d
0x18000800e  mov     qword ptr [rax-40h], 1
0x180008016  test    rcx, rcx
0x180008019  jnz     loc_1800082CD
0x18000801f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008026  mov     ecx, 40h ; '@'; unsigned __int64
0x18000802b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008030  mov     rbx, rax
0x180008033  test    rax, rax
0x180008036  jz      loc_180008307
0x18000803c  mov     [rax], r12
0x18000803f  mov     [rax+8], r12
0x180008043  mov     [rax+10h], r12
0x180008047  mov     [rax+18h], r12
0x18000804b  mov     [rax+20h], r12
0x18000804f  mov     [rax+28h], r12
0x180008053  mov     qword ptr [rax+30h], 1
0x18000805b  mov     [rax+38h], r12
0x18000805f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008066  mov     ecx, 2; unsigned __int64
0x18000806b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008070  mov     r9, rax
0x180008073  mov     [rbx+28h], rax
0x180008077  test    rax, rax
0x18000807a  jz      short loc_1800080E0
0x18000807c  mov     ecx, 7FFFFFFEh
0x180008081  lea     rdx, dword_18003FF34
0x180008088  mov     r10d, 1
0x18000808e  xchg    ax, ax
0x180008090  test    rcx, rcx
0x180008093  jz      short loc_1800080B2
0x180008095  movzx   eax, word ptr [rdx]
0x180008098  test    ax, ax
0x18000809b  jz      short loc_1800080B2
0x18000809d  add     rdx, 2
0x1800080a1  mov     [r9], ax
0x1800080a5  add     r9, 2
0x1800080a9  dec     rcx
0x1800080ac  sub     r10, 1
0x1800080b0  jnz     short loc_180008090
0x1800080b2  mov     edi, 8007007Ah
0x1800080b7  test    r10, r10
0x1800080ba  cmovnz  edi, r12d
0x1800080be  lea     rcx, [r9-2]
0x1800080c2  cmovnz  rcx, r9
0x1800080c6  mov     [rcx], r12w
0x1800080ca  jz      loc_1800081CF
0x1800080d0  cmp     [rbx+18h], r12
0x1800080d4  jnz     short loc_1800080E0
0x1800080d6  cmp     [rbx+30h], r12d
0x1800080da  jz      loc_1800081EF
0x1800080e0  mov     [rsp+0A8h+var_38], rbx
0x1800080e5  test    rbx, rbx
0x1800080e8  jz      loc_18000830F
0x1800080ee  mov     [rsp+0A8h+var_3C], 1
0x1800080f6  lea     rcx, [rsp+0A8h+var_40]; unsigned __int16 *
0x1800080fb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180008100  test    rax, rax
0x180008103  jz      loc_1800082D7
0x180008109  lea     rcx, [rsp+0A8h+var_40]; unsigned __int16 *
0x18000810e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180008113  mov     [rsp+0A8h+var_48], r12
0x180008118  mov     [rsp+0A8h+var_68], r14
0x18000811d  lea     rcx, [rsp+0A8h+arg_0]
0x180008125  mov     [rsp+0A8h+var_70], rcx
0x18000812a  lea     rcx, [rsp+0A8h+hMem]
0x18000812f  mov     [rsp+0A8h+var_78], rcx
0x180008134  mov     [rsp+0A8h+var_80], r12d
0x180008139  mov     [rsp+0A8h+var_88], r15d
0x18000813e  mov     r9, rax
0x180008141  xor     r8d, r8d; pReturnValue
0x180008144  mov     edx, 9; nProcNum
0x180008149  lea     rcx, stru_180035078; pProxyInfo
0x180008150  call    cs:__imp_NdrClientCall3
0x180008157  nop     dword ptr [rax+rax+00h]
0x18000815c  mov     rbx, rax
0x18000815f  mov     [rsp+0A8h+var_48], rax
0x180008164  mov     [rsp+0A8h+var_58], eax
0x180008168  jmp     short loc_180008198
0x18000816a  test    eax, eax
0x18000816c  jle     short loc_180008176
0x18000816e  movzx   eax, ax
0x180008171  or      eax, 80070000h
0x180008176  mov     ebx, eax
0x180008178  mov     [rsp+0A8h+var_58], eax
0x18000817c  mov     r8d, eax
0x18000817f  lea     rdx, aRpcgetsessionp; "RpcGetSessionProtocolLastInputTime fail"...
0x180008186  mov     ecx, 8; int
0x18000818b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008190  mov     rsi, [rsp+0A8h+arg_10]
0x180008198  test    ebx, ebx
0x18000819a  jns     short loc_18000820F
0x18000819c  mov     rcx, [rsp+0A8h+hMem]; hMem
0x1800081a1  test    rcx, rcx
0x1800081a4  jnz     loc_180008361
0x1800081aa  lea     rcx, [rsp+0A8h+var_40]; this
0x1800081af  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800081b4  mov     eax, ebx
0x1800081b6  mov     rbx, [rsp+0A8h+arg_8]
0x1800081be  add     rsp, 80h
0x1800081c5  pop     r15
0x1800081c7  pop     r14
0x1800081c9  pop     r12
0x1800081cb  pop     rdi
0x1800081cc  pop     rsi
0x1800081cd  retn
0x1800081cf  mov     ecx, edi; int
0x1800081d1  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800081d6  mov     r8d, edi
0x1800081d9  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x1800081e0  mov     ecx, 8; int
0x1800081e5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800081ea  jmp     loc_1800080E0
0x1800081ef  mov     rcx, rbx; this
0x1800081f2  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x1800081f7  cmp     eax, 800706BAh
0x1800081fc  jz      loc_1800082FB
0x180008202  mov     rcx, rbx; this
0x180008205  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000820a  jmp     loc_1800080E0
0x18000820f  mov     rcx, [rsp+0A8h+hMem]
0x180008214  test    rcx, rcx
0x180008217  jz      loc_180008336
0x18000821d  mov     r8d, [rsp+0A8h+arg_0]
0x180008225  cmp     r8d, 3F4h
0x18000822c  jb      loc_180008340
0x180008232  mov     rax, rcx
0x180008235  mov     edx, 7
0x18000823a  movups  xmm0, xmmword ptr [rax]
0x18000823d  movups  xmmword ptr [rsi], xmm0
0x180008240  movups  xmm1, xmmword ptr [rax+10h]
0x180008244  movups  xmmword ptr [rsi+10h], xmm1
0x180008248  movups  xmm0, xmmword ptr [rax+20h]
0x18000824c  movups  xmmword ptr [rsi+20h], xmm0
0x180008250  movups  xmm1, xmmword ptr [rax+30h]
0x180008254  movups  xmmword ptr [rsi+30h], xmm1
0x180008258  movups  xmm0, xmmword ptr [rax+40h]
0x18000825c  movups  xmmword ptr [rsi+40h], xmm0
0x180008260  movups  xmm1, xmmword ptr [rax+50h]
0x180008264  movups  xmmword ptr [rsi+50h], xmm1
0x180008268  movups  xmm0, xmmword ptr [rax+60h]
0x18000826c  movups  xmmword ptr [rsi+60h], xmm0
0x180008270  movups  xmm1, xmmword ptr [rax+70h]
0x180008274  movups  xmmword ptr [rsi+70h], xmm1
0x180008278  lea     rsi, [rsi+80h]
0x18000827f  lea     rax, [rax+80h]
0x180008286  sub     rdx, 1
0x18000828a  jnz     short loc_18000823A
0x18000828c  movups  xmm0, xmmword ptr [rax]
0x18000828f  movups  xmmword ptr [rsi], xmm0
0x180008292  movups  xmm1, xmmword ptr [rax+10h]
0x180008296  movups  xmmword ptr [rsi+10h], xmm1
0x18000829a  movups  xmm0, xmmword ptr [rax+20h]
0x18000829e  movups  xmmword ptr [rsi+20h], xmm0
0x1800082a2  movups  xmm1, xmmword ptr [rax+30h]
0x1800082a6  movups  xmmword ptr [rsi+30h], xmm1
0x1800082aa  movups  xmm0, xmmword ptr [rax+40h]
0x1800082ae  movups  xmmword ptr [rsi+40h], xmm0
0x1800082b2  movups  xmm1, xmmword ptr [rax+50h]
0x1800082b6  movups  xmmword ptr [rsi+50h], xmm1
0x1800082ba  movups  xmm0, xmmword ptr [rax+60h]
0x1800082be  movups  xmmword ptr [rsi+60h], xmm0
0x1800082c2  mov     eax, [rax+70h]
0x1800082c5  mov     [rsi+70h], eax
0x1800082c8  jmp     loc_1800081A1
0x1800082cd  mov     [rsp+0A8h+var_38], rcx
0x1800082d2  jmp     loc_1800080F6
0x1800082d7  call    cs:__imp_GetLastError
0x1800082de  nop     dword ptr [rax+rax+00h]
0x1800082e3  mov     ebx, eax
0x1800082e5  test    eax, eax
0x1800082e7  jle     loc_18000819C
0x1800082ed  movzx   ebx, ax
0x1800082f0  or      ebx, 80070000h
0x1800082f6  jmp     loc_18000819C
0x1800082fb  mov     dword ptr [rbx+34h], 1
0x180008302  jmp     loc_180008202
0x180008307  mov     rbx, r12
0x18000830a  jmp     loc_1800080E0
0x18000830f  mov     ecx, 0Eh; dwErrCode
0x180008314  call    cs:__imp_SetLastError
0x18000831b  nop     dword ptr [rax+rax+00h]
0x180008320  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180008327  mov     ecx, 8; int
0x18000832c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008331  jmp     loc_1800080F6
0x180008336  mov     ebx, 80004003h
0x18000833b  jmp     loc_1800081A1
0x180008340  mov     r9d, 3F4h
0x180008346  lea     rdx, aRpcgetprotocol; "RpcGetProtocolStatus returned %d bytes,"...
0x18000834d  mov     ecx, 8; int
0x180008352  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008357  mov     ebx, 80070057h
0x18000835c  jmp     loc_18000819C
0x180008361  call    cs:__imp_LocalFree
0x180008368  nop     dword ptr [rax+rax+00h]
0x18000836d  jmp     loc_1800081AA
0x1800330f0  push    rbp
0x1800330f2  sub     rsp, 50h
0x1800330f6  mov     rbp, rdx
0x1800330f9  mov     rcx, [rcx]
0x1800330fc  mov     ecx, [rcx]; ExceptionCode
0x1800330fe  call    cs:__imp_I_RpcExceptionFilter
0x180033105  nop     dword ptr [rax+rax+00h]
0x18003310a  nop
0x18003310b  add     rsp, 50h
0x18003310f  pop     rbp
0x180033110  retn
```
