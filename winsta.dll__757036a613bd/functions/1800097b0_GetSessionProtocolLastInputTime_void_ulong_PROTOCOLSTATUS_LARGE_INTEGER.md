# GetSessionProtocolLastInputTime(void *,ulong,_PROTOCOLSTATUS *,_LARGE_INTEGER *)

- ea: `0x1800097b0`
- end: `0x180009b29`
- name: `?GetSessionProtocolLastInputTime@@YAJPEAXKPEAU_PROTOCOLSTATUS@@PEAT_LARGE_INTEGER@@@Z`
- size: `889`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _PROTOCOLSTATUS *, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800067b0`
- `0x18000ad50`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x1800097b0`
- `0x1800230b8`
- `0x1800230ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ad7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009aa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009b1e`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800303ae`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800303ae`
- `RPCRT4!NdrClientCall3` at `0x180009920`
- `RPCRT4!NdrClientCall3` at `0x180009920`

## string_xrefs

- `0x1800099a2`: `StringCchCopy failed: %x`
- `0x180009949`: `RpcGetSessionProtocolLastInputTime failed: 0x%x`
- `0x180009b03`: `RpcGetProtocolStatus returned %d bytes, expected %d`

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
    goto LABEL_19;
  }
  v16 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v25);
  v24.Simple = 0;
  v17.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0, 9u, 0, v16, a2, 0, &hMem, &v27, a4).Pointer;
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
0x1800097b0  mov     rax, rsp
0x1800097b3  mov     [rax+10h], rbx
0x1800097b7  mov     [rax+18h], r8
0x1800097bb  push    rsi
0x1800097bc  push    rdi
0x1800097bd  push    r12
0x1800097bf  push    r14
0x1800097c1  push    r15
0x1800097c3  sub     rsp, 80h
0x1800097ca  mov     r14, r9
0x1800097cd  mov     rsi, r8
0x1800097d0  mov     r15d, edx
0x1800097d3  xor     r12d, r12d
0x1800097d6  mov     [rax-50h], r12
0x1800097da  mov     [rax+8], r12d
0x1800097de  mov     qword ptr [rax-40h], 1
0x1800097e6  test    rcx, rcx
0x1800097e9  jnz     loc_180009A96
0x1800097ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800097f6  mov     ecx, 40h ; '@'; unsigned __int64
0x1800097fb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009800  mov     rbx, rax
0x180009803  test    rax, rax
0x180009806  jz      loc_180009ACA
0x18000980c  mov     [rax], r12
0x18000980f  mov     [rax+8], r12
0x180009813  mov     [rax+10h], r12
0x180009817  mov     [rax+18h], r12
0x18000981b  mov     [rax+20h], r12
0x18000981f  mov     [rax+28h], r12
0x180009823  mov     qword ptr [rax+30h], 1
0x18000982b  mov     [rax+38h], r12
0x18000982f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009836  mov     ecx, 2; unsigned __int64
0x18000983b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009840  mov     r9, rax
0x180009843  mov     [rbx+28h], rax
0x180009847  test    rax, rax
0x18000984a  jz      short loc_1800098B0
0x18000984c  mov     ecx, 7FFFFFFEh
0x180009851  lea     rdx, dword_18003D0CC
0x180009858  mov     r10d, 1
0x18000985e  xchg    ax, ax
0x180009860  test    rcx, rcx
0x180009863  jz      short loc_180009882
0x180009865  movzx   eax, word ptr [rdx]
0x180009868  test    ax, ax
0x18000986b  jz      short loc_180009882
0x18000986d  add     rdx, 2
0x180009871  mov     [r9], ax
0x180009875  add     r9, 2
0x180009879  dec     rcx
0x18000987c  sub     r10, 1
0x180009880  jnz     short loc_180009860
0x180009882  mov     edi, 8007007Ah
0x180009887  test    r10, r10
0x18000988a  cmovnz  edi, r12d
0x18000988e  lea     rcx, [r9-2]
0x180009892  cmovnz  rcx, r9
0x180009896  mov     [rcx], r12w
0x18000989a  jz      loc_180009998
0x1800098a0  cmp     [rbx+18h], r12
0x1800098a4  jnz     short loc_1800098B0
0x1800098a6  cmp     [rbx+30h], r12d
0x1800098aa  jz      loc_1800099B8
0x1800098b0  mov     [rsp+0A8h+var_38], rbx
0x1800098b5  test    rbx, rbx
0x1800098b8  jz      loc_180009AD2
0x1800098be  mov     [rsp+0A8h+var_3C], 1
0x1800098c6  lea     rcx, [rsp+0A8h+var_40]; unsigned __int16 *
0x1800098cb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800098d0  test    rax, rax
0x1800098d3  jz      loc_180009AA0
0x1800098d9  lea     rcx, [rsp+0A8h+var_40]; unsigned __int16 *
0x1800098de  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800098e3  mov     [rsp+0A8h+var_48], r12
0x1800098e8  mov     [rsp+0A8h+var_68], r14
0x1800098ed  lea     rcx, [rsp+0A8h+arg_0]
0x1800098f5  mov     [rsp+0A8h+var_70], rcx
0x1800098fa  lea     rcx, [rsp+0A8h+hMem]
0x1800098ff  mov     [rsp+0A8h+var_78], rcx
0x180009904  mov     [rsp+0A8h+var_80], r12d
0x180009909  mov     [rsp+0A8h+var_88], r15d
0x18000990e  mov     r9, rax
0x180009911  xor     r8d, r8d; pReturnValue
0x180009914  mov     edx, 9; nProcNum
0x180009919  lea     rcx, stru_1800320E0; pProxyInfo
0x180009920  call    cs:__imp_NdrClientCall3
0x180009926  mov     rbx, rax
0x180009929  mov     [rsp+0A8h+var_48], rax
0x18000992e  mov     [rsp+0A8h+var_58], eax
0x180009932  jmp     short loc_180009962
0x180009934  test    eax, eax
0x180009936  jle     short loc_180009940
0x180009938  movzx   eax, ax
0x18000993b  or      eax, 80070000h
0x180009940  mov     ebx, eax
0x180009942  mov     [rsp+0A8h+var_58], eax
0x180009946  mov     r8d, eax
0x180009949  lea     rdx, aRpcgetsessionp; "RpcGetSessionProtocolLastInputTime fail"...
0x180009950  mov     ecx, 8; int
0x180009955  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000995a  mov     rsi, [rsp+0A8h+arg_10]
0x180009962  test    ebx, ebx
0x180009964  jns     short loc_1800099D8
0x180009966  mov     rcx, [rsp+0A8h+hMem]; hMem
0x18000996b  test    rcx, rcx
0x18000996e  jnz     loc_180009B1E
0x180009974  lea     rcx, [rsp+0A8h+var_40]; this
0x180009979  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000997e  mov     eax, ebx
0x180009980  mov     rbx, [rsp+0A8h+arg_8]
0x180009988  add     rsp, 80h
0x18000998f  pop     r15
0x180009991  pop     r14
0x180009993  pop     r12
0x180009995  pop     rdi
0x180009996  pop     rsi
0x180009997  retn
0x180009998  mov     ecx, edi; int
0x18000999a  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000999f  mov     r8d, edi
0x1800099a2  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x1800099a9  mov     ecx, 8; int
0x1800099ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800099b3  jmp     loc_1800098B0
0x1800099b8  mov     rcx, rbx; this
0x1800099bb  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x1800099c0  cmp     eax, 800706BAh
0x1800099c5  jz      loc_180009ABE
0x1800099cb  mov     rcx, rbx; this
0x1800099ce  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x1800099d3  jmp     loc_1800098B0
0x1800099d8  mov     rcx, [rsp+0A8h+hMem]
0x1800099dd  test    rcx, rcx
0x1800099e0  jz      loc_180009AF3
0x1800099e6  mov     r8d, [rsp+0A8h+arg_0]
0x1800099ee  cmp     r8d, 3F4h
0x1800099f5  jb      loc_180009AFD
0x1800099fb  mov     rax, rcx
0x1800099fe  mov     edx, 7
0x180009a03  movups  xmm0, xmmword ptr [rax]
0x180009a06  movups  xmmword ptr [rsi], xmm0
0x180009a09  movups  xmm1, xmmword ptr [rax+10h]
0x180009a0d  movups  xmmword ptr [rsi+10h], xmm1
0x180009a11  movups  xmm0, xmmword ptr [rax+20h]
0x180009a15  movups  xmmword ptr [rsi+20h], xmm0
0x180009a19  movups  xmm1, xmmword ptr [rax+30h]
0x180009a1d  movups  xmmword ptr [rsi+30h], xmm1
0x180009a21  movups  xmm0, xmmword ptr [rax+40h]
0x180009a25  movups  xmmword ptr [rsi+40h], xmm0
0x180009a29  movups  xmm1, xmmword ptr [rax+50h]
0x180009a2d  movups  xmmword ptr [rsi+50h], xmm1
0x180009a31  movups  xmm0, xmmword ptr [rax+60h]
0x180009a35  movups  xmmword ptr [rsi+60h], xmm0
0x180009a39  movups  xmm1, xmmword ptr [rax+70h]
0x180009a3d  movups  xmmword ptr [rsi+70h], xmm1
0x180009a41  lea     rsi, [rsi+80h]
0x180009a48  lea     rax, [rax+80h]
0x180009a4f  sub     rdx, 1
0x180009a53  jnz     short loc_180009A03
0x180009a55  movups  xmm0, xmmword ptr [rax]
0x180009a58  movups  xmmword ptr [rsi], xmm0
0x180009a5b  movups  xmm1, xmmword ptr [rax+10h]
0x180009a5f  movups  xmmword ptr [rsi+10h], xmm1
0x180009a63  movups  xmm0, xmmword ptr [rax+20h]
0x180009a67  movups  xmmword ptr [rsi+20h], xmm0
0x180009a6b  movups  xmm1, xmmword ptr [rax+30h]
0x180009a6f  movups  xmmword ptr [rsi+30h], xmm1
0x180009a73  movups  xmm0, xmmword ptr [rax+40h]
0x180009a77  movups  xmmword ptr [rsi+40h], xmm0
0x180009a7b  movups  xmm1, xmmword ptr [rax+50h]
0x180009a7f  movups  xmmword ptr [rsi+50h], xmm1
0x180009a83  movups  xmm0, xmmword ptr [rax+60h]
0x180009a87  movups  xmmword ptr [rsi+60h], xmm0
0x180009a8b  mov     eax, [rax+70h]
0x180009a8e  mov     [rsi+70h], eax
0x180009a91  jmp     loc_18000996B
0x180009a96  mov     [rsp+0A8h+var_38], rcx
0x180009a9b  jmp     loc_1800098C6
0x180009aa0  call    cs:__imp_GetLastError
0x180009aa6  mov     ebx, eax
0x180009aa8  test    eax, eax
0x180009aaa  jle     loc_180009966
0x180009ab0  movzx   ebx, ax
0x180009ab3  or      ebx, 80070000h
0x180009ab9  jmp     loc_180009966
0x180009abe  mov     dword ptr [rbx+34h], 1
0x180009ac5  jmp     loc_1800099CB
0x180009aca  mov     rbx, r12
0x180009acd  jmp     loc_1800098B0
0x180009ad2  mov     ecx, 0Eh; dwErrCode
0x180009ad7  call    cs:__imp_SetLastError
0x180009add  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180009ae4  mov     ecx, 8; int
0x180009ae9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009aee  jmp     loc_1800098C6
0x180009af3  mov     ebx, 80004003h
0x180009af8  jmp     loc_18000996B
0x180009afd  mov     r9d, 3F4h
0x180009b03  lea     rdx, aRpcgetprotocol; "RpcGetProtocolStatus returned %d bytes,"...
0x180009b0a  mov     ecx, 8; int
0x180009b0f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009b14  mov     ebx, 80070057h
0x180009b19  jmp     loc_180009966
0x180009b1e  call    cs:__imp_LocalFree
0x180009b24  jmp     loc_180009974
0x1800303a0  push    rbp
0x1800303a2  sub     rsp, 50h
0x1800303a6  mov     rbp, rdx
0x1800303a9  mov     rcx, [rcx]
0x1800303ac  mov     ecx, [rcx]; ExceptionCode
0x1800303ae  call    cs:__imp_I_RpcExceptionFilter
0x1800303b4  nop
0x1800303b5  add     rsp, 50h
0x1800303b9  pop     rbp
0x1800303ba  retn
```
