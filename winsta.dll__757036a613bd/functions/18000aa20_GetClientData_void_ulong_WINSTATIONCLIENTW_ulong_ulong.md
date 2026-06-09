# GetClientData(void *,ulong,_WINSTATIONCLIENTW *,ulong,ulong *)

- ea: `0x18000aa20`
- end: `0x18000ad47`
- name: `?GetClientData@@YAJPEAXKPEAU_WINSTATIONCLIENTW@@KPEAK@Z`
- size: `807`
- prototype: `int(void *, unsigned int, struct _WINSTATIONCLIENTW *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000ce54`

## callees

- `0x180005374`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008340`
- `0x180008e30`
- `0x18000aa20`
- `0x1800230b8`
- `0x1800230ec`
- `0x180024376`
- `0x18002fe06`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ad0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab8a`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800304e6`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800304e6`
- `RPCRT4!NdrClientCall3` at `0x18000ac0b`
- `RPCRT4!NdrClientCall3` at `0x18000ac0b`

## string_xrefs

- `0x18000abbb`: `StringCchCopy failed: %x`

## pseudocode

```c
__int64 __fastcall GetClientData(void *a1, int a2, struct _WINSTATIONCLIENTW *a3, unsigned int a4, unsigned int *a5)
{
  unsigned int v5; // r15d
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _WORD *v10; // rcx
  __int64 v11; // rax
  int *v12; // r8
  __int64 v13; // rdx
  __int16 v14; // r9
  int v15; // edi
  _WORD *v16; // rax
  signed int LastError; // eax
  CLIENT_CALL_RETURN v18; // rbx
  _BYTE *v19; // rax
  __int64 v20; // rcx
  void *v22; // rax
  unsigned int v23; // edi
  HLOCAL hMem; // [rsp+48h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v25; // [rsp+50h] [rbp-48h]
  __int64 v26; // [rsp+58h] [rbp-40h] BYREF
  void *v27; // [rsp+60h] [rbp-38h]
  size_t Size; // [rsp+A0h] [rbp+8h] BYREF
  struct _WINSTATIONCLIENTW *v29; // [rsp+B0h] [rbp+18h]
  unsigned int v30; // [rsp+B8h] [rbp+20h]

  v30 = a4;
  v29 = a3;
  v5 = a4;
  hMem = 0;
  LODWORD(Size) = 0;
  v26 = 1;
  if ( a1 )
  {
    v27 = a1;
  }
  else
  {
    v8 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      v8[2] = 0;
      v8[3] = 0;
      v8[4] = 0;
      v8[5] = 0;
      v8[6] = 1;
      v8[7] = 0;
      v10 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v9[5] = v10;
      if ( v10 )
      {
        v11 = 2147483646;
        v12 = &dword_18003D0CC;
        v13 = 1;
        do
        {
          if ( !v11 )
            break;
          v14 = *(_WORD *)v12;
          if ( !*(_WORD *)v12 )
            break;
          v12 = (int *)((char *)v12 + 2);
          *v10++ = v14;
          --v11;
          --v13;
        }
        while ( v13 );
        v15 = v13 == 0 ? 0x8007007A : 0;
        v16 = v10 - 1;
        if ( v13 )
          v16 = v10;
        *v16 = 0;
        if ( v13 )
        {
          if ( !v9[3] && !*((_DWORD *)v9 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v9) == -2147023174 )
              *((_DWORD *)v9 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v9);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v15);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v15);
        }
      }
    }
    else
    {
      v9 = 0;
    }
    v27 = v9;
    if ( v9 )
    {
      HIDWORD(v26) = 1;
    }
    else
    {
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
  }
  if ( !CSmartPublicBinding::operator void *((unsigned __int16 *)&v26) )
  {
    LastError = GetLastError();
    LODWORD(v18.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v18.Pointer) = (unsigned __int16)LastError | 0x80070000;
LABEL_18:
    if ( SLODWORD(v18.Simple) < 0 )
      goto LABEL_19;
    goto LABEL_28;
  }
  v22 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v26);
  v25.Simple = 0;
  v18.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0, 0, 0, v22, a2, &hMem, &Size).Pointer;
  v25.Pointer = v18.Pointer;
  if ( LODWORD(v18.Pointer) == -2147022646 || LODWORD(v18.Pointer) == -2147023174 || LODWORD(v18.Pointer) == -2147023179 )
  {
    *a5 = v5;
    memset_0(a3, 0, v5);
    LODWORD(v18.Pointer) = 0;
  }
  if ( SLODWORD(v18.Simple) < 0 )
  {
    _DbgPrintMessage(8, "RpcGetClientData failed: 0x%x in %s", LODWORD(v18.Pointer), "GetClientData");
    goto LABEL_18;
  }
LABEL_28:
  if ( hMem )
  {
    v23 = Size;
    if ( (unsigned int)Size < v5 )
      v5 = Size;
    memcpy_0(a3, hMem, v5);
    *a5 = v23;
  }
LABEL_19:
  v19 = hMem;
  if ( hMem )
  {
    v20 = (unsigned int)Size;
    if ( (_DWORD)Size )
    {
      do
      {
        *v19++ = 0;
        --v20;
      }
      while ( v20 );
    }
    LocalFree(hMem);
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v26);
  return LODWORD(v18.Pointer);
}

```

## disassembly

```asm
0x18000aa20  mov     rax, rsp
0x18000aa23  mov     [rax+10h], rbx
0x18000aa27  mov     [rax+20h], r9d
0x18000aa2b  mov     [rax+18h], r8
0x18000aa2f  push    rsi
0x18000aa30  push    rdi
0x18000aa31  push    r12
0x18000aa33  push    r13
0x18000aa35  push    r15
0x18000aa37  sub     rsp, 70h
0x18000aa3b  mov     r15d, r9d
0x18000aa3e  mov     r12, r8
0x18000aa41  mov     r13d, edx
0x18000aa44  xor     esi, esi
0x18000aa46  mov     [rax-50h], rsi
0x18000aa4a  mov     [rax+8], esi
0x18000aa4d  mov     qword ptr [rax-40h], 1
0x18000aa55  test    rcx, rcx
0x18000aa58  jnz     loc_18000ACEB
0x18000aa5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aa65  lea     ecx, [rsi+40h]; unsigned __int64
0x18000aa68  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aa6d  mov     rbx, rax
0x18000aa70  test    rax, rax
0x18000aa73  jz      loc_18000ACFE
0x18000aa79  mov     [rax], rsi
0x18000aa7c  mov     [rax+8], rsi
0x18000aa80  mov     [rax+10h], rsi
0x18000aa84  mov     [rax+18h], rsi
0x18000aa88  mov     [rax+20h], rsi
0x18000aa8c  mov     [rax+28h], rsi
0x18000aa90  mov     qword ptr [rax+30h], 1
0x18000aa98  mov     [rax+38h], rsi
0x18000aa9c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aaa3  lea     ecx, [rsi+2]; unsigned __int64
0x18000aaa6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000aaab  mov     rcx, rax
0x18000aaae  mov     [rbx+28h], rax
0x18000aab2  test    rax, rax
0x18000aab5  jz      short loc_18000AB1D
0x18000aab7  mov     eax, 7FFFFFFEh
0x18000aabc  lea     r8, dword_18003D0CC
0x18000aac3  lea     edx, [rsi+1]
0x18000aac6  test    rax, rax
0x18000aac9  jz      short loc_18000AAEA
0x18000aacb  movzx   r9d, word ptr [r8]
0x18000aacf  test    r9w, r9w
0x18000aad3  jz      short loc_18000AAEA
0x18000aad5  add     r8, 2
0x18000aad9  mov     [rcx], r9w
0x18000aadd  add     rcx, 2
0x18000aae1  dec     rax
0x18000aae4  sub     rdx, 1
0x18000aae8  jnz     short loc_18000AAC6
0x18000aaea  mov     rax, rdx
0x18000aaed  neg     rax
0x18000aaf0  sbb     edi, edi
0x18000aaf2  not     edi
0x18000aaf4  and     edi, 8007007Ah
0x18000aafa  lea     rax, [rcx-2]
0x18000aafe  test    rdx, rdx
0x18000ab01  cmovnz  rax, rcx
0x18000ab05  mov     [rax], si
0x18000ab08  jz      loc_18000ABB1
0x18000ab0e  cmp     [rbx+18h], rsi
0x18000ab12  jnz     short loc_18000AB1D
0x18000ab14  cmp     [rbx+30h], esi
0x18000ab17  jz      loc_18000ACBA
0x18000ab1d  mov     [rsp+98h+var_38], rbx
0x18000ab22  test    rbx, rbx
0x18000ab25  jz      loc_18000AD06
0x18000ab2b  mov     [rsp+98h+var_3C], 1
0x18000ab33  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x18000ab38  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000ab3d  test    rax, rax
0x18000ab40  jnz     loc_18000ABD1
0x18000ab46  call    cs:__imp_GetLastError
0x18000ab4c  mov     ebx, eax
0x18000ab4e  test    eax, eax
0x18000ab50  jle     short loc_18000AB5B
0x18000ab52  movzx   ebx, ax
0x18000ab55  or      ebx, 80070000h
0x18000ab5b  test    ebx, ebx
0x18000ab5d  jns     loc_18000AC81
0x18000ab63  mov     rax, [rsp+98h+hMem]
0x18000ab68  test    rax, rax
0x18000ab6b  jz      short loc_18000AB90
0x18000ab6d  mov     ecx, dword ptr [rsp+98h+Size]
0x18000ab74  test    rcx, rcx
0x18000ab77  jz      short loc_18000AB85
0x18000ab79  mov     [rax], sil
0x18000ab7c  inc     rax
0x18000ab7f  sub     rcx, 1
0x18000ab83  jnz     short loc_18000AB79
0x18000ab85  mov     rcx, [rsp+98h+hMem]; hMem
0x18000ab8a  call    cs:__imp_LocalFree
0x18000ab90  lea     rcx, [rsp+98h+var_40]; this
0x18000ab95  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000ab9a  mov     eax, ebx
0x18000ab9c  mov     rbx, [rsp+98h+arg_8]
0x18000aba4  add     rsp, 70h
0x18000aba8  pop     r15
0x18000abaa  pop     r13
0x18000abac  pop     r12
0x18000abae  pop     rdi
0x18000abaf  pop     rsi
0x18000abb0  retn
0x18000abb1  mov     ecx, edi; int
0x18000abb3  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000abb8  mov     r8d, edi
0x18000abbb  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x18000abc2  mov     ecx, 8; int
0x18000abc7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000abcc  jmp     loc_18000AB1D
0x18000abd1  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x18000abd6  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000abdb  mov     [rsp+98h+var_48], rsi
0x18000abe0  lea     rcx, [rsp+98h+Size]
0x18000abe8  mov     [rsp+98h+var_68], rcx
0x18000abed  lea     rcx, [rsp+98h+hMem]
0x18000abf2  mov     [rsp+98h+var_70], rcx
0x18000abf7  mov     [rsp+98h+var_78], r13d
0x18000abfc  mov     r9, rax
0x18000abff  xor     r8d, r8d; pReturnValue
0x18000ac02  xor     edx, edx; nProcNum
0x18000ac04  lea     rcx, stru_1800320E0; pProxyInfo
0x18000ac0b  call    cs:__imp_NdrClientCall3
0x18000ac11  mov     rbx, rax
0x18000ac14  mov     [rsp+98h+var_48], rax
0x18000ac19  mov     [rsp+98h+var_58], eax
0x18000ac1d  jmp     short loc_18000AC57
0x18000ac1f  test    eax, eax
0x18000ac21  jle     short loc_18000AC2B
0x18000ac23  movzx   eax, ax
0x18000ac26  or      eax, 80070000h
0x18000ac2b  mov     ebx, eax
0x18000ac2d  mov     [rsp+98h+var_58], eax
0x18000ac31  mov     r8d, eax
0x18000ac34  lea     rdx, aRpcgetclientda_0; "RpcGetClientData threw an exception: 0x"...
0x18000ac3b  mov     ecx, 8; int
0x18000ac40  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ac45  xor     esi, esi
0x18000ac47  mov     r15d, [rsp+98h+arg_18]
0x18000ac4f  mov     r12, [rsp+98h+arg_10]
0x18000ac57  cmp     ebx, 800708CAh
0x18000ac5d  jnz     short loc_18000ACD6
0x18000ac5f  mov     rax, [rsp+98h+arg_20]
0x18000ac67  mov     [rax], r15d
0x18000ac6a  mov     r8d, r15d; Size
0x18000ac6d  xor     edx, edx; Val
0x18000ac6f  mov     rcx, r12; void *
0x18000ac72  call    memset_0
0x18000ac77  mov     ebx, esi
0x18000ac79  test    ebx, ebx
0x18000ac7b  js      loc_18000AD27
0x18000ac81  mov     rax, [rsp+98h+hMem]
0x18000ac86  test    rax, rax
0x18000ac89  jz      loc_18000AB63
0x18000ac8f  mov     edi, dword ptr [rsp+98h+Size]
0x18000ac96  cmp     edi, r15d
0x18000ac99  cmovb   r15d, edi
0x18000ac9d  mov     r8d, r15d; Size
0x18000aca0  mov     rdx, rax; Src
0x18000aca3  mov     rcx, r12; void *
0x18000aca6  call    memcpy_0
0x18000acab  mov     rax, [rsp+98h+arg_20]
0x18000acb3  mov     [rax], edi
0x18000acb5  jmp     loc_18000AB63
0x18000acba  mov     rcx, rbx; this
0x18000acbd  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000acc2  cmp     eax, 800706BAh
0x18000acc7  jz      short loc_18000ACF5
0x18000acc9  mov     rcx, rbx; this
0x18000accc  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000acd1  jmp     loc_18000AB1D
0x18000acd6  cmp     ebx, 800706BAh
0x18000acdc  jz      short loc_18000AC5F
0x18000acde  cmp     ebx, 800706B5h
0x18000ace4  jnz     short loc_18000AC79
0x18000ace6  jmp     loc_18000AC5F
0x18000aceb  mov     [rsp+98h+var_38], rcx
0x18000acf0  jmp     loc_18000AB33
0x18000acf5  mov     dword ptr [rbx+34h], 1
0x18000acfc  jmp     short loc_18000ACC9
0x18000acfe  mov     rbx, rsi
0x18000ad01  jmp     loc_18000AB1D
0x18000ad06  mov     ecx, 0Eh; dwErrCode
0x18000ad0b  call    cs:__imp_SetLastError
0x18000ad11  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000ad18  mov     ecx, 8; int
0x18000ad1d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ad22  jmp     loc_18000AB33
0x18000ad27  lea     r9, aGetclientdata; "GetClientData"
0x18000ad2e  mov     r8d, ebx
0x18000ad31  lea     rdx, aRpcgetclientda; "RpcGetClientData failed: 0x%x in %s"
0x18000ad38  mov     ecx, 8; int
0x18000ad3d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000ad42  jmp     loc_18000AB5B
0x1800304d8  push    rbp
0x1800304da  sub     rsp, 40h
0x1800304de  mov     rbp, rdx
0x1800304e1  mov     rcx, [rcx]
0x1800304e4  mov     ecx, [rcx]; ExceptionCode
0x1800304e6  call    cs:__imp_I_RpcExceptionFilter
0x1800304ec  nop
0x1800304ed  add     rsp, 40h
0x1800304f1  pop     rbp
0x1800304f2  retn
```
