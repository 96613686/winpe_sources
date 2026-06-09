# WinStationIsCurrentSessionRemoteable

- ea: `0x180009350`
- end: `0x1800095a1`
- name: `WinStationIsCurrentSessionRemoteable`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180003f90`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x180008590`
- `0x180009350`
- `0x1800249e8`
- `0x180024a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009542`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009558`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000957f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009542`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009558`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000957f`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033258`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033258`
- `RPCRT4!NdrClientCall3` at `0x18000947e`
- `RPCRT4!NdrClientCall3` at `0x18000947e`

## string_xrefs

- `0x1800094ec`: `StringCchCopy failed: %x`

## pseudocode

```c
char __fastcall WinStationIsCurrentSessionRemoteable(_BYTE *a1)
{
  char v2; // di
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  _WORD *v5; // rcx
  __int64 v6; // rax
  int *v7; // r8
  __int64 v8; // rdx
  __int16 v9; // r9
  int v10; // esi
  _WORD *v11; // rax
  void *v12; // rax
  int Pointer; // ebx
  DWORD v15; // eax
  unsigned __int16 v16[4]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v17; // [rsp+40h] [rbp-38h]

  v2 = 0;
  *a1 = 0;
  if ( TestServiceStarted() )
  {
    *(_QWORD *)v16 = 0;
    v3 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v4 = v3;
    if ( v3 )
    {
      *v3 = 0;
      v3[1] = 0;
      v3[2] = 0;
      v3[3] = 0;
      v3[4] = 0;
      v3[5] = 0;
      v3[6] = 1;
      v3[7] = 0;
      v5 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v4[5] = v5;
      if ( v5 )
      {
        v6 = 2147483646;
        v7 = &dword_18003FF34;
        v8 = 1;
        do
        {
          if ( !v6 )
            break;
          v9 = *(_WORD *)v7;
          if ( !*(_WORD *)v7 )
            break;
          v7 = (int *)((char *)v7 + 2);
          *v5++ = v9;
          --v6;
          --v8;
        }
        while ( v8 );
        v10 = v8 == 0 ? 0x8007007A : 0;
        v11 = v5 - 1;
        if ( v8 )
          v11 = v5;
        *v11 = 0;
        if ( v8 )
        {
          if ( !v4[3] && !*((_DWORD *)v4 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v4) == -2147023174 )
              *((_DWORD *)v4 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v4);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v10);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v10);
        }
      }
    }
    else
    {
      v4 = 0;
    }
    v17 = v4;
    if ( v4 )
    {
      *(_DWORD *)&v16[2] = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
    if ( CSmartPublicBinding::operator void *(v16)
      && (v12 = CSmartPublicBinding::operator void *(v16),
          Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035230, 0, 0, v12, a1).Pointer,
          Pointer < 0) )
    {
      _DbgPrintMessage(
        8,
        "RpcIsCurrentSessionTerminalRemote failed: 0x%x in %s",
        Pointer,
        "WinStationIsCurrentSessionRemoteable");
      v15 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v15);
    }
    else
    {
      v2 = 1;
    }
    CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v16);
  }
  else
  {
    SetLastError(0x548u);
  }
  return v2;
}

```

## disassembly

```asm
0x180009350  push    rbx
0x180009352  push    rsi
0x180009353  push    rdi
0x180009354  push    r14
0x180009356  sub     rsp, 58h
0x18000935a  mov     r14, rcx
0x18000935d  xor     edi, edi
0x18000935f  mov     [rcx], dil
0x180009362  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x180009367  test    eax, eax
0x180009369  jz      loc_180009553
0x18000936f  mov     qword ptr [rsp+78h+var_40], rdi
0x180009374  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000937b  lea     ecx, [rdi+40h]; unsigned __int64
0x18000937e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009383  mov     rbx, rax
0x180009386  test    rax, rax
0x180009389  jz      loc_180009572
0x18000938f  mov     [rax], rdi
0x180009392  mov     [rax+8], rdi
0x180009396  mov     [rax+10h], rdi
0x18000939a  mov     [rax+18h], rdi
0x18000939e  mov     [rax+20h], rdi
0x1800093a2  mov     [rax+28h], rdi
0x1800093a6  mov     qword ptr [rax+30h], 1
0x1800093ae  mov     [rax+38h], rdi
0x1800093b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800093b9  lea     ecx, [rdi+2]; unsigned __int64
0x1800093bc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800093c1  mov     rcx, rax
0x1800093c4  mov     [rbx+28h], rax
0x1800093c8  test    rax, rax
0x1800093cb  jz      short loc_180009433
0x1800093cd  mov     eax, 7FFFFFFEh
0x1800093d2  lea     r8, dword_18003FF34
0x1800093d9  lea     edx, [rdi+1]
0x1800093dc  test    rax, rax
0x1800093df  jz      short loc_180009400
0x1800093e1  movzx   r9d, word ptr [r8]
0x1800093e5  test    r9w, r9w
0x1800093e9  jz      short loc_180009400
0x1800093eb  add     r8, 2
0x1800093ef  mov     [rcx], r9w
0x1800093f3  add     rcx, 2
0x1800093f7  dec     rax
0x1800093fa  sub     rdx, 1
0x1800093fe  jnz     short loc_1800093DC
0x180009400  mov     rax, rdx
0x180009403  neg     rax
0x180009406  sbb     esi, esi
0x180009408  not     esi
0x18000940a  and     esi, 8007007Ah
0x180009410  lea     rax, [rcx-2]
0x180009414  test    rdx, rdx
0x180009417  cmovnz  rax, rcx
0x18000941b  mov     [rax], di
0x18000941e  jz      loc_1800094E2
0x180009424  cmp     [rbx+18h], rdi
0x180009428  jnz     short loc_180009433
0x18000942a  cmp     [rbx+30h], edi
0x18000942d  jz      loc_180009502
0x180009433  mov     [rsp+78h+var_38], rbx
0x180009438  test    rbx, rbx
0x18000943b  jz      loc_18000957A
0x180009441  mov     dword ptr [rsp+78h+var_40+4], 1
0x180009449  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000944e  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180009453  test    rax, rax
0x180009456  jz      short loc_1800094C7
0x180009458  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x18000945d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180009462  mov     [rsp+78h+arg_0], rdi
0x18000946a  mov     [rsp+78h+var_58], r14
0x18000946f  mov     r9, rax
0x180009472  xor     r8d, r8d; pReturnValue
0x180009475  xor     edx, edx; nProcNum
0x180009477  lea     rcx, stru_180035230; pProxyInfo
0x18000947e  call    cs:__imp_NdrClientCall3
0x180009485  nop     dword ptr [rax+rax+00h]
0x18000948a  mov     rbx, rax
0x18000948d  mov     [rsp+78h+arg_0], rax
0x180009495  mov     [rsp+78h+var_48], eax
0x180009499  jmp     short loc_1800094C3
0x18000949b  test    eax, eax
0x18000949d  jle     short loc_1800094A7
0x18000949f  movzx   eax, ax
0x1800094a2  or      eax, 80070000h
0x1800094a7  mov     ebx, eax
0x1800094a9  mov     [rsp+78h+var_48], eax
0x1800094ad  mov     r8d, eax
0x1800094b0  lea     rdx, aRpciscurrentse_0; "RpcIsCurrentSessionTerminalRemote threw"...
0x1800094b7  mov     ecx, 8; int
0x1800094bc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800094c1  xor     edi, edi
0x1800094c3  test    ebx, ebx
0x1800094c5  js      short loc_18000951E
0x1800094c7  mov     dil, 1
0x1800094ca  lea     rcx, [rsp+78h+var_40]; this
0x1800094cf  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800094d4  mov     al, dil
0x1800094d7  add     rsp, 58h
0x1800094db  pop     r14
0x1800094dd  pop     rdi
0x1800094de  pop     rsi
0x1800094df  pop     rbx
0x1800094e0  retn
0x1800094e2  mov     ecx, esi; int
0x1800094e4  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800094e9  mov     r8d, esi
0x1800094ec  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x1800094f3  mov     ecx, 8; int
0x1800094f8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800094fd  jmp     loc_180009433
0x180009502  mov     rcx, rbx; this
0x180009505  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000950a  cmp     eax, 800706BAh
0x18000950f  jz      short loc_180009569
0x180009511  mov     rcx, rbx; this
0x180009514  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180009519  jmp     loc_180009433
0x18000951e  lea     r9, aWinstationiscu_0; "WinStationIsCurrentSessionRemoteable"
0x180009525  mov     r8d, ebx
0x180009528  lea     rdx, aRpciscurrentse; "RpcIsCurrentSessionTerminalRemote faile"...
0x18000952f  mov     ecx, 8; int
0x180009534  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009539  mov     ecx, ebx; int
0x18000953b  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180009540  mov     ecx, eax; dwErrCode
0x180009542  call    cs:__imp_SetLastError
0x180009549  nop     dword ptr [rax+rax+00h]
0x18000954e  jmp     loc_1800094CA
0x180009553  mov     ecx, 548h; dwErrCode
0x180009558  call    cs:__imp_SetLastError
0x18000955f  nop     dword ptr [rax+rax+00h]
0x180009564  jmp     loc_1800094D4
0x180009569  mov     dword ptr [rbx+34h], 1
0x180009570  jmp     short loc_180009511
0x180009572  mov     rbx, rdi
0x180009575  jmp     loc_180009433
0x18000957a  mov     ecx, 0Eh; dwErrCode
0x18000957f  call    cs:__imp_SetLastError
0x180009586  nop     dword ptr [rax+rax+00h]
0x18000958b  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180009592  mov     ecx, 8; int
0x180009597  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000959c  jmp     loc_180009449
0x18003324a  push    rbp
0x18003324c  sub     rsp, 30h
0x180033250  mov     rbp, rdx
0x180033253  mov     rcx, [rcx]
0x180033256  mov     ecx, [rcx]; ExceptionCode
0x180033258  call    cs:__imp_I_RpcExceptionFilter
0x18003325f  nop     dword ptr [rax+rax+00h]
0x180033264  nop
0x180033265  add     rsp, 30h
0x180033269  pop     rbp
0x18003326a  retn
```
