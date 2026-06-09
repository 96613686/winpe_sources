# WinStationGetCurrentSessionCapabilities

- ea: `0x1800090a0`
- end: `0x18000934a`
- name: `WinStationGetCurrentSessionCapabilities`
- size: `682`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x180008590`
- `0x1800090a0`
- `0x1800249e8`
- `0x180024a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009254`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009328`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009254`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092d4`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033230`
- `RPCRT4!I_RpcExceptionFilter` at `0x180033230`
- `RPCRT4!NdrClientCall3` at `0x1800091ea`
- `RPCRT4!NdrClientCall3` at `0x1800091ea`

## string_xrefs

- `0x18000926d`: `StringCchCopy failed: %x`

## pseudocode

```c
char __fastcall WinStationGetCurrentSessionCapabilities(int a1, _DWORD *a2)
{
  char v4; // di
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _WORD *v7; // rcx
  __int64 v8; // rax
  int *v9; // r8
  __int64 v10; // rdx
  __int16 v11; // r9
  int v12; // r14d
  _WORD *v13; // rax
  void *v14; // rax
  int Pointer; // ebx
  DWORD v17; // ecx
  DWORD v18; // eax
  signed int LastError; // eax
  unsigned __int16 v20[4]; // [rsp+38h] [rbp-40h] BYREF
  _QWORD *v21; // [rsp+40h] [rbp-38h]

  v4 = 0;
  *a2 = 0;
  if ( !TestServiceStarted() )
  {
    v17 = 1352;
LABEL_22:
    SetLastError(v17);
    return v4;
  }
  if ( a1 != 1 )
  {
    v17 = 87;
    goto LABEL_22;
  }
  *(_QWORD *)v20 = 0;
  v5 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    v5[2] = 0;
    v5[3] = 0;
    v5[4] = 0;
    v5[5] = 0;
    v5[6] = 1;
    v5[7] = 0;
    v7 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
    v6[5] = v7;
    if ( v7 )
    {
      v8 = 2147483646;
      v9 = &dword_18003FF34;
      v10 = 1;
      do
      {
        if ( !v8 )
          break;
        v11 = *(_WORD *)v9;
        if ( !*(_WORD *)v9 )
          break;
        v9 = (int *)((char *)v9 + 2);
        *v7++ = v11;
        --v8;
        --v10;
      }
      while ( v10 );
      v12 = v10 == 0 ? 0x8007007A : 0;
      v13 = v7 - 1;
      if ( v10 )
        v13 = v7;
      *v13 = 0;
      if ( v10 )
      {
        if ( !v6[3] && !*((_DWORD *)v6 + 12) )
        {
          if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v6) == -2147023174 )
            *((_DWORD *)v6 + 13) = 1;
          CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v6);
        }
      }
      else
      {
        ConvertHRESULT2WIN32(v12);
        _DbgPrintMessage(8, "StringCchCopy failed: %x", v12);
      }
    }
  }
  else
  {
    v6 = 0;
  }
  v21 = v6;
  if ( v6 )
  {
    *(_DWORD *)&v20[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *(v20) )
  {
    v14 = CSmartPublicBinding::operator void *(v20);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035230, 3u, 0, v14, 1, a2).Pointer;
    if ( Pointer < 0 )
    {
      _DbgPrintMessage(
        8,
        "RpcGetCurrentSessionCapabilities failed: 0x%x in %s",
        Pointer,
        "WinStationGetCurrentSessionCapabilities");
      v18 = ConvertHRESULT2WIN32(Pointer);
      SetLastError(v18);
    }
    else
    {
      v4 = 1;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "Can't bind to local LSM, error code 0x%08x", LastError);
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v20);
  return v4;
}

```

## disassembly

```asm
0x1800090a0  push    rbx
0x1800090a2  push    rdi
0x1800090a3  push    r14
0x1800090a5  push    r15
0x1800090a7  sub     rsp, 58h
0x1800090ab  mov     r15, rdx
0x1800090ae  mov     ebx, ecx
0x1800090b0  xor     edi, edi
0x1800090b2  mov     [rdx], edi
0x1800090b4  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x1800090b9  test    eax, eax
0x1800090bb  jz      loc_18000924F
0x1800090c1  cmp     ebx, 1
0x1800090c4  jnz     loc_180009305
0x1800090ca  mov     qword ptr [rsp+78h+var_40], rdi
0x1800090cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800090d6  lea     ecx, [rdi+40h]; unsigned __int64
0x1800090d9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800090de  mov     rbx, rax
0x1800090e1  test    rax, rax
0x1800090e4  jz      loc_18000931B
0x1800090ea  mov     [rax], rdi
0x1800090ed  mov     [rax+8], rdi
0x1800090f1  mov     [rax+10h], rdi
0x1800090f5  mov     [rax+18h], rdi
0x1800090f9  mov     [rax+20h], rdi
0x1800090fd  mov     [rax+28h], rdi
0x180009101  mov     qword ptr [rax+30h], 1
0x180009109  mov     [rax+38h], rdi
0x18000910d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009114  lea     ecx, [rdi+2]; unsigned __int64
0x180009117  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000911c  mov     rcx, rax
0x18000911f  mov     [rbx+28h], rax
0x180009123  test    rax, rax
0x180009126  jz      short loc_180009191
0x180009128  mov     eax, 7FFFFFFEh
0x18000912d  lea     r8, dword_18003FF34
0x180009134  lea     edx, [rdi+1]
0x180009137  test    rax, rax
0x18000913a  jz      short loc_18000915B
0x18000913c  movzx   r9d, word ptr [r8]
0x180009140  test    r9w, r9w
0x180009144  jz      short loc_18000915B
0x180009146  add     r8, 2
0x18000914a  mov     [rcx], r9w
0x18000914e  add     rcx, 2
0x180009152  dec     rax
0x180009155  sub     rdx, 1
0x180009159  jnz     short loc_180009137
0x18000915b  mov     rax, rdx
0x18000915e  neg     rax
0x180009161  sbb     r14d, r14d
0x180009164  not     r14d
0x180009167  and     r14d, 8007007Ah
0x18000916e  lea     rax, [rcx-2]
0x180009172  test    rdx, rdx
0x180009175  cmovnz  rax, rcx
0x180009179  mov     [rax], di
0x18000917c  jz      loc_180009262
0x180009182  cmp     [rbx+18h], rdi
0x180009186  jnz     short loc_180009191
0x180009188  cmp     [rbx+30h], edi
0x18000918b  jz      loc_180009283
0x180009191  mov     [rsp+78h+var_38], rbx
0x180009196  test    rbx, rbx
0x180009199  jz      loc_180009323
0x18000919f  mov     dword ptr [rsp+78h+var_40+4], 1
0x1800091a7  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x1800091ac  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800091b1  test    rax, rax
0x1800091b4  jz      loc_1800092D4
0x1800091ba  lea     rcx, [rsp+78h+var_40]; unsigned __int16 *
0x1800091bf  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800091c4  mov     [rsp+78h+arg_8], rdi
0x1800091cc  mov     [rsp+78h+var_50], r15
0x1800091d1  mov     [rsp+78h+var_58], 1
0x1800091d9  mov     r9, rax
0x1800091dc  xor     r8d, r8d; pReturnValue
0x1800091df  lea     edx, [r8+3]; nProcNum
0x1800091e3  lea     rcx, stru_180035230; pProxyInfo
0x1800091ea  call    cs:__imp_NdrClientCall3
0x1800091f1  nop     dword ptr [rax+rax+00h]
0x1800091f6  mov     rbx, rax
0x1800091f9  mov     [rsp+78h+arg_8], rax
0x180009201  mov     [rsp+78h+var_48], eax
0x180009205  jmp     short loc_18000922F
0x180009207  test    eax, eax
0x180009209  jle     short loc_180009213
0x18000920b  movzx   eax, ax
0x18000920e  or      eax, 80070000h
0x180009213  mov     ebx, eax
0x180009215  mov     [rsp+78h+var_48], eax
0x180009219  mov     r8d, eax
0x18000921c  lea     rdx, aRpcgetcurrents_11; "RpcGetCurrentSessionCapabilities threw "...
0x180009223  mov     ecx, 8; int
0x180009228  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000922d  xor     edi, edi
0x18000922f  test    ebx, ebx
0x180009231  js      short loc_18000929F
0x180009233  mov     dil, 1
0x180009236  lea     rcx, [rsp+78h+var_40]; this
0x18000923b  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180009240  mov     al, dil
0x180009243  add     rsp, 58h
0x180009247  pop     r15
0x180009249  pop     r14
0x18000924b  pop     rdi
0x18000924c  pop     rbx
0x18000924d  retn
0x18000924f  mov     ecx, 548h; dwErrCode
0x180009254  call    cs:__imp_SetLastError
0x18000925b  nop     dword ptr [rax+rax+00h]
0x180009260  jmp     short loc_180009240
0x180009262  mov     ecx, r14d; int
0x180009265  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000926a  mov     r8d, r14d
0x18000926d  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180009274  mov     ecx, 8; int
0x180009279  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000927e  jmp     loc_180009191
0x180009283  mov     rcx, rbx; this
0x180009286  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000928b  cmp     eax, 800706BAh
0x180009290  jz      short loc_18000930F
0x180009292  mov     rcx, rbx; this
0x180009295  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000929a  jmp     loc_180009191
0x18000929f  lea     r9, aWinstationgetc_4; "WinStationGetCurrentSessionCapabilities"
0x1800092a6  mov     r8d, ebx
0x1800092a9  lea     rdx, aRpcgetcurrents_7; "RpcGetCurrentSessionCapabilities failed"...
0x1800092b0  mov     ecx, 8; int
0x1800092b5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800092ba  mov     ecx, ebx; int
0x1800092bc  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800092c1  mov     ecx, eax; dwErrCode
0x1800092c3  call    cs:__imp_SetLastError
0x1800092ca  nop     dword ptr [rax+rax+00h]
0x1800092cf  jmp     loc_180009236
0x1800092d4  call    cs:__imp_GetLastError
0x1800092db  nop     dword ptr [rax+rax+00h]
0x1800092e0  test    eax, eax
0x1800092e2  jle     short loc_1800092EC
0x1800092e4  movzx   eax, ax
0x1800092e7  or      eax, 80070000h
0x1800092ec  mov     r8d, eax
0x1800092ef  lea     rdx, aCanTBindToLoca; "Can't bind to local LSM, error code 0x%"...
0x1800092f6  mov     ecx, 8; int
0x1800092fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009300  jmp     loc_180009236
0x180009305  mov     ecx, 57h ; 'W'
0x18000930a  jmp     loc_180009254
0x18000930f  mov     dword ptr [rbx+34h], 1
0x180009316  jmp     loc_180009292
0x18000931b  mov     rbx, rdi
0x18000931e  jmp     loc_180009191
0x180009323  mov     ecx, 0Eh; dwErrCode
0x180009328  call    cs:__imp_SetLastError
0x18000932f  nop     dword ptr [rax+rax+00h]
0x180009334  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000933b  mov     ecx, 8; int
0x180009340  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009345  jmp     loc_1800091A7
0x180033222  push    rbp
0x180033224  sub     rsp, 30h
0x180033228  mov     rbp, rdx
0x18003322b  mov     rcx, [rcx]
0x18003322e  mov     ecx, [rcx]; ExceptionCode
0x180033230  call    cs:__imp_I_RpcExceptionFilter
0x180033237  nop     dword ptr [rax+rax+00h]
0x18003323c  nop
0x18003323d  add     rsp, 30h
0x180033241  pop     rbp
0x180033242  retn
```
