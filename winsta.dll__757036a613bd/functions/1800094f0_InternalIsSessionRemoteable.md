# InternalIsSessionRemoteable

- ea: `0x1800094f0`
- end: `0x1800097a0`
- name: `InternalIsSessionRemoteable`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180005a70`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008200`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x1800094f0`
- `0x180009d10`
- `0x1800230b8`
- `0x1800230ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000972a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000976f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000972a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000976f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003037e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003037e`
- `RPCRT4!NdrClientCall3` at `0x18000964f`
- `RPCRT4!NdrClientCall3` at `0x18000964f`

## string_xrefs

- `0x1800096c7`: `StringCchCopy failed: %x`

## pseudocode

```c
__int64 __fastcall InternalIsSessionRemoteable(__int64 a1, ULONG SessionId, _BYTE *a3)
{
  unsigned __int8 v5; // bl
  int v6; // esi
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  _WORD *v9; // r9
  __int64 v10; // rcx
  int *v11; // rdx
  __int64 v12; // r10
  __int16 v13; // ax
  int v14; // ebx
  _WORD *v15; // rcx
  unsigned int v16; // edx
  void *v17; // rax
  int Pointer; // ebx
  DWORD v20; // ecx
  DWORD v21; // eax
  unsigned __int16 v22[4]; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v23; // [rsp+40h] [rbp-48h]

  v5 = 0;
  if ( a1 || !a3 )
  {
    v20 = 87;
LABEL_30:
    SetLastError(v20);
    return v5;
  }
  *a3 = 0;
  if ( !TestServiceStarted() )
  {
    v20 = 1352;
    goto LABEL_30;
  }
  v6 = 0;
  *(_QWORD *)v22 = 0;
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
    v23 = v8;
  }
  else
  {
    v8 = 0;
    v23 = 0;
  }
  if ( v8 )
  {
    v6 = 1;
    *(_DWORD *)&v22[2] = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( SessionId == -1 )
    SessionId = NtCurrentPeb()->SessionId;
  if ( !CSmartPublicBinding::operator void *(v22)
    || (v17 = CSmartPublicBinding::operator void *(v22),
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&stru_180032200,
                                  0x12u,
                                  0,
                                  v17,
                                  SessionId,
                                  a3).Pointer,
        Pointer >= 0) )
  {
    v5 = 1;
    if ( v6 )
    {
      if ( v8 )
        CPublicBinding::`scalar deleting destructor'((RPC_BINDING_HANDLE *)v8, v16);
    }
    return v5;
  }
  _DbgPrintMessage(8, "RpcIsTerminalRemote failed: 0x%x in %s", Pointer, "InternalIsSessionRemoteable");
  v21 = ConvertHRESULT2WIN32(Pointer);
  SetLastError(v21);
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
  return 0;
}

```

## disassembly

```asm
0x1800094f0  push    rbx
0x1800094f2  push    rsi
0x1800094f3  push    rdi
0x1800094f4  push    r12
0x1800094f6  push    r14
0x1800094f8  push    r15
0x1800094fa  sub     rsp, 58h
0x1800094fe  mov     r14, r8
0x180009501  mov     r15d, edx
0x180009504  xor     bl, bl
0x180009506  test    rcx, rcx
0x180009509  jnz     loc_1800096DD
0x18000950f  test    r8, r8
0x180009512  jz      loc_1800096DD
0x180009518  mov     [r8], bl
0x18000951b  call    ?TestServiceStarted@@YAHK@Z; TestServiceStarted(ulong)
0x180009520  test    eax, eax
0x180009522  jz      loc_18000974D
0x180009528  xor     r12d, r12d
0x18000952b  mov     esi, r12d
0x18000952e  mov     qword ptr [rsp+88h+var_50], r12
0x180009533  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000953a  mov     ecx, 40h ; '@'; unsigned __int64
0x18000953f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009544  mov     rdi, rax
0x180009547  test    rax, rax
0x18000954a  jz      loc_18000975D
0x180009550  mov     [rax], r12
0x180009553  mov     [rax+8], r12
0x180009557  mov     [rax+10h], r12
0x18000955b  mov     [rax+18h], r12
0x18000955f  mov     [rax+20h], r12
0x180009563  mov     [rax+28h], r12
0x180009567  mov     qword ptr [rax+30h], 1
0x18000956f  mov     [rax+38h], r12
0x180009573  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000957a  mov     ecx, 2; unsigned __int64
0x18000957f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009584  mov     r9, rax
0x180009587  mov     [rdi+28h], rax
0x18000958b  test    rax, rax
0x18000958e  jz      short loc_1800095F1
0x180009590  mov     ecx, 7FFFFFFEh
0x180009595  lea     rdx, dword_18003D0CC
0x18000959c  mov     r10d, 1
0x1800095a2  test    rcx, rcx
0x1800095a5  jz      short loc_1800095C4
0x1800095a7  movzx   eax, word ptr [rdx]
0x1800095aa  test    ax, ax
0x1800095ad  jz      short loc_1800095C4
0x1800095af  add     rdx, 2
0x1800095b3  mov     [r9], ax
0x1800095b7  add     r9, 2
0x1800095bb  dec     rcx
0x1800095be  sub     r10, 1
0x1800095c2  jnz     short loc_1800095A2
0x1800095c4  mov     ebx, 8007007Ah
0x1800095c9  test    r10, r10
0x1800095cc  cmovnz  ebx, r12d
0x1800095d0  lea     rcx, [r9-2]
0x1800095d4  cmovnz  rcx, r9
0x1800095d8  mov     [rcx], r12w
0x1800095dc  jz      loc_1800096BD
0x1800095e2  cmp     [rdi+18h], rsi
0x1800095e6  jnz     short loc_1800095F1
0x1800095e8  cmp     [rdi+30h], esi
0x1800095eb  jz      loc_1800096EA
0x1800095f1  mov     [rsp+88h+var_48], rdi
0x1800095f6  test    rdi, rdi
0x1800095f9  jz      loc_18000976A
0x1800095ff  mov     esi, 1
0x180009604  mov     dword ptr [rsp+88h+var_50+4], esi
0x180009608  cmp     r15d, 0FFFFFFFFh
0x18000960c  jz      loc_18000978B
0x180009612  lea     rcx, [rsp+88h+var_50]; unsigned __int16 *
0x180009617  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000961c  test    rax, rax
0x18000961f  jz      short loc_180009699
0x180009621  lea     rcx, [rsp+88h+var_50]; unsigned __int16 *
0x180009626  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000962b  mov     [rsp+88h+arg_0], r12
0x180009633  mov     [rsp+88h+var_60], r14
0x180009638  mov     [rsp+88h+var_68], r15d
0x18000963d  mov     r9, rax
0x180009640  xor     r8d, r8d; pReturnValue
0x180009643  mov     edx, 12h; nProcNum
0x180009648  lea     rcx, stru_180032200; pProxyInfo
0x18000964f  call    cs:__imp_NdrClientCall3
0x180009655  mov     rbx, rax
0x180009658  mov     [rsp+88h+arg_0], rax
0x180009660  mov     [rsp+88h+var_58], eax
0x180009664  jmp     short loc_180009695
0x180009666  test    eax, eax
0x180009668  jle     short loc_180009672
0x18000966a  movzx   eax, ax
0x18000966d  or      eax, 80070000h
0x180009672  mov     ebx, eax
0x180009674  mov     [rsp+88h+var_58], eax
0x180009678  mov     r8d, eax
0x18000967b  lea     rdx, aRpcisterminalr_0; "RpcIsTerminalRemote threw an exception:"...
0x180009682  mov     ecx, 8; int
0x180009687  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000968c  mov     rdi, [rsp+88h+var_48]
0x180009691  mov     esi, dword ptr [rsp+88h+var_50+4]
0x180009695  test    ebx, ebx
0x180009697  js      short loc_180009706
0x180009699  mov     bl, 1
0x18000969b  test    esi, esi
0x18000969d  jz      short loc_1800096AC
0x18000969f  test    rdi, rdi
0x1800096a2  jz      short loc_1800096AC
0x1800096a4  mov     rcx, rdi; Binding
0x1800096a7  call    ??_GCPublicBinding@@QEAAPEAXI@Z; CPublicBinding::`scalar deleting destructor'(uint)
0x1800096ac  movzx   eax, bl
0x1800096af  add     rsp, 58h
0x1800096b3  pop     r15
0x1800096b5  pop     r14
0x1800096b7  pop     r12
0x1800096b9  pop     rdi
0x1800096ba  pop     rsi
0x1800096bb  pop     rbx
0x1800096bc  retn
0x1800096bd  mov     ecx, ebx; int
0x1800096bf  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800096c4  mov     r8d, ebx
0x1800096c7  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x1800096ce  mov     ecx, 8; int
0x1800096d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800096d8  jmp     loc_1800095F1
0x1800096dd  mov     ecx, 57h ; 'W'; dwErrCode
0x1800096e2  call    cs:__imp_SetLastError
0x1800096e8  jmp     short loc_1800096AC
0x1800096ea  mov     rcx, rdi; this
0x1800096ed  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x1800096f2  cmp     eax, 800706BAh
0x1800096f7  jz      short loc_180009754
0x1800096f9  mov     rcx, rdi; this
0x1800096fc  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180009701  jmp     loc_1800095F1
0x180009706  lea     r9, aInternalissess; "InternalIsSessionRemoteable"
0x18000970d  mov     r8d, ebx
0x180009710  lea     rdx, aRpcisterminalr; "RpcIsTerminalRemote failed: 0x%x in %s"
0x180009717  mov     ecx, 8; int
0x18000971c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009721  mov     ecx, ebx; int
0x180009723  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180009728  mov     ecx, eax; dwErrCode
0x18000972a  call    cs:__imp_SetLastError
0x180009730  xor     bl, bl
0x180009732  lea     rcx, [rsp+88h+var_50]; this
0x180009737  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000973c  movzx   eax, bl
0x18000973f  add     rsp, 58h
0x180009743  pop     r15
0x180009745  pop     r14
0x180009747  pop     r12
0x180009749  pop     rdi
0x18000974a  pop     rsi
0x18000974b  pop     rbx
0x18000974c  retn
0x18000974d  mov     ecx, 548h
0x180009752  jmp     short loc_1800096E2
0x180009754  mov     dword ptr [rdi+34h], 1
0x18000975b  jmp     short loc_1800096F9
0x18000975d  mov     rdi, r12
0x180009760  mov     [rsp+88h+var_48], r12
0x180009765  jmp     loc_1800095F6
0x18000976a  mov     ecx, 0Eh; dwErrCode
0x18000976f  call    cs:__imp_SetLastError
0x180009775  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000977c  mov     ecx, 8; int
0x180009781  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009786  jmp     loc_180009608
0x18000978b  mov     rax, gs:60h
0x180009794  mov     r15d, [rax+2C0h]
0x18000979b  jmp     loc_180009612
0x180030370  push    rbp
0x180030372  sub     rsp, 30h
0x180030376  mov     rbp, rdx
0x180030379  mov     rcx, [rcx]
0x18003037c  mov     ecx, [rcx]; ExceptionCode
0x18003037e  call    cs:__imp_I_RpcExceptionFilter
0x180030384  nop
0x180030385  add     rsp, 30h
0x180030389  pop     rbp
0x18003038a  retn
```
