# GetClientData(void *,ulong,_WINSTATIONCLIENTW *,ulong,ulong *)

- ea: `0x1800016c8`
- end: `0x180001a08`
- name: `?GetClientData@@YAJPEAXKPEAU_WINSTATIONCLIENTW@@KPEAK@Z`
- size: `832`
- prototype: `int(void *, unsigned int, struct _WINSTATIONCLIENTW *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180009dec`

## callees

- `0x1800016c8`
- `0x1800032b4`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800066d0`
- `0x1800075a0`
- `0x1800249e8`
- `0x180024a1c`
- `0x180025cc6`
- `0x180032be6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800019c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800019c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800017ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001838`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032d69`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032d69`
- `RPCRT4!NdrClientCall3` at `0x1800018c0`
- `RPCRT4!NdrClientCall3` at `0x1800018c0`

## string_xrefs

- `0x180001870`: `StringCchCopy failed: %x`

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
        v12 = &dword_18003FF34;
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
  v18.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180035078, 0, 0, v22, a2, &hMem, &Size).Pointer;
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
0x1800016c8  mov     rax, rsp
0x1800016cb  mov     [rax+10h], rbx
0x1800016cf  mov     [rax+20h], r9d
0x1800016d3  mov     [rax+18h], r8
0x1800016d7  push    rsi
0x1800016d8  push    rdi
0x1800016d9  push    r12
0x1800016db  push    r13
0x1800016dd  push    r15
0x1800016df  sub     rsp, 70h
0x1800016e3  mov     r15d, r9d
0x1800016e6  mov     r12, r8
0x1800016e9  mov     r13d, edx
0x1800016ec  xor     esi, esi
0x1800016ee  mov     [rax-50h], rsi
0x1800016f2  mov     [rax+8], esi
0x1800016f5  mov     qword ptr [rax-40h], 1
0x1800016fd  test    rcx, rcx
0x180001700  jnz     loc_1800019A6
0x180001706  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000170d  lea     ecx, [rsi+40h]; unsigned __int64
0x180001710  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001715  mov     rbx, rax
0x180001718  test    rax, rax
0x18000171b  jz      loc_1800019B9
0x180001721  mov     [rax], rsi
0x180001724  mov     [rax+8], rsi
0x180001728  mov     [rax+10h], rsi
0x18000172c  mov     [rax+18h], rsi
0x180001730  mov     [rax+20h], rsi
0x180001734  mov     [rax+28h], rsi
0x180001738  mov     qword ptr [rax+30h], 1
0x180001740  mov     [rax+38h], rsi
0x180001744  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000174b  lea     ecx, [rsi+2]; unsigned __int64
0x18000174e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180001753  mov     rcx, rax
0x180001756  mov     [rbx+28h], rax
0x18000175a  test    rax, rax
0x18000175d  jz      short loc_1800017C5
0x18000175f  mov     eax, 7FFFFFFEh
0x180001764  lea     r8, dword_18003FF34
0x18000176b  lea     edx, [rsi+1]
0x18000176e  test    rax, rax
0x180001771  jz      short loc_180001792
0x180001773  movzx   r9d, word ptr [r8]
0x180001777  test    r9w, r9w
0x18000177b  jz      short loc_180001792
0x18000177d  add     r8, 2
0x180001781  mov     [rcx], r9w
0x180001785  add     rcx, 2
0x180001789  dec     rax
0x18000178c  sub     rdx, 1
0x180001790  jnz     short loc_18000176E
0x180001792  mov     rax, rdx
0x180001795  neg     rax
0x180001798  sbb     edi, edi
0x18000179a  not     edi
0x18000179c  and     edi, 8007007Ah
0x1800017a2  lea     rax, [rcx-2]
0x1800017a6  test    rdx, rdx
0x1800017a9  cmovnz  rax, rcx
0x1800017ad  mov     [rax], si
0x1800017b0  jz      loc_180001866
0x1800017b6  cmp     [rbx+18h], rsi
0x1800017ba  jnz     short loc_1800017C5
0x1800017bc  cmp     [rbx+30h], esi
0x1800017bf  jz      loc_180001975
0x1800017c5  mov     [rsp+98h+var_38], rbx
0x1800017ca  test    rbx, rbx
0x1800017cd  jz      loc_1800019C1
0x1800017d3  mov     [rsp+98h+var_3C], 1
0x1800017db  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x1800017e0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800017e5  test    rax, rax
0x1800017e8  jnz     loc_180001886
0x1800017ee  call    cs:__imp_GetLastError
0x1800017f5  nop     dword ptr [rax+rax+00h]
0x1800017fa  mov     ebx, eax
0x1800017fc  test    eax, eax
0x1800017fe  jle     short loc_180001809
0x180001800  movzx   ebx, ax
0x180001803  or      ebx, 80070000h
0x180001809  test    ebx, ebx
0x18000180b  jns     loc_18000193C
0x180001811  mov     rax, [rsp+98h+hMem]
0x180001816  test    rax, rax
0x180001819  jz      short loc_180001844
0x18000181b  mov     ecx, dword ptr [rsp+98h+Size]
0x180001822  test    rcx, rcx
0x180001825  jz      short loc_180001833
0x180001827  mov     [rax], sil
0x18000182a  inc     rax
0x18000182d  sub     rcx, 1
0x180001831  jnz     short loc_180001827
0x180001833  mov     rcx, [rsp+98h+hMem]; hMem
0x180001838  call    cs:__imp_LocalFree
0x18000183f  nop     dword ptr [rax+rax+00h]
0x180001844  lea     rcx, [rsp+98h+var_40]; this
0x180001849  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000184e  mov     eax, ebx
0x180001850  mov     rbx, [rsp+98h+arg_8]
0x180001858  add     rsp, 70h
0x18000185c  pop     r15
0x18000185e  pop     r13
0x180001860  pop     r12
0x180001862  pop     rdi
0x180001863  pop     rsi
0x180001864  retn
0x180001866  mov     ecx, edi; int
0x180001868  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18000186d  mov     r8d, edi
0x180001870  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180001877  mov     ecx, 8; int
0x18000187c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001881  jmp     loc_1800017C5
0x180001886  lea     rcx, [rsp+98h+var_40]; unsigned __int16 *
0x18000188b  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180001890  mov     [rsp+98h+var_48], rsi
0x180001895  lea     rcx, [rsp+98h+Size]
0x18000189d  mov     [rsp+98h+var_68], rcx
0x1800018a2  lea     rcx, [rsp+98h+hMem]
0x1800018a7  mov     [rsp+98h+var_70], rcx
0x1800018ac  mov     [rsp+98h+var_78], r13d
0x1800018b1  mov     r9, rax
0x1800018b4  xor     r8d, r8d; pReturnValue
0x1800018b7  xor     edx, edx; nProcNum
0x1800018b9  lea     rcx, stru_180035078; pProxyInfo
0x1800018c0  call    cs:__imp_NdrClientCall3
0x1800018c7  nop     dword ptr [rax+rax+00h]
0x1800018cc  mov     rbx, rax
0x1800018cf  mov     [rsp+98h+var_48], rax
0x1800018d4  mov     [rsp+98h+var_58], eax
0x1800018d8  jmp     short loc_180001912
0x1800018da  test    eax, eax
0x1800018dc  jle     short loc_1800018E6
0x1800018de  movzx   eax, ax
0x1800018e1  or      eax, 80070000h
0x1800018e6  mov     ebx, eax
0x1800018e8  mov     [rsp+98h+var_58], eax
0x1800018ec  mov     r8d, eax
0x1800018ef  lea     rdx, aRpcgetclientda_0; "RpcGetClientData threw an exception: 0x"...
0x1800018f6  mov     ecx, 8; int
0x1800018fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001900  xor     esi, esi
0x180001902  mov     r15d, [rsp+98h+arg_18]
0x18000190a  mov     r12, [rsp+98h+arg_10]
0x180001912  cmp     ebx, 800708CAh
0x180001918  jnz     short loc_180001991
0x18000191a  mov     rax, [rsp+98h+arg_20]
0x180001922  mov     [rax], r15d
0x180001925  mov     r8d, r15d; Size
0x180001928  xor     edx, edx; Val
0x18000192a  mov     rcx, r12; void *
0x18000192d  call    memset_0
0x180001932  mov     ebx, esi
0x180001934  test    ebx, ebx
0x180001936  js      loc_1800019E8
0x18000193c  mov     rax, [rsp+98h+hMem]
0x180001941  test    rax, rax
0x180001944  jz      loc_180001811
0x18000194a  mov     edi, dword ptr [rsp+98h+Size]
0x180001951  cmp     edi, r15d
0x180001954  cmovb   r15d, edi
0x180001958  mov     r8d, r15d; Size
0x18000195b  mov     rdx, rax; Src
0x18000195e  mov     rcx, r12; void *
0x180001961  call    memcpy_0
0x180001966  mov     rax, [rsp+98h+arg_20]
0x18000196e  mov     [rax], edi
0x180001970  jmp     loc_180001811
0x180001975  mov     rcx, rbx; this
0x180001978  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x18000197d  cmp     eax, 800706BAh
0x180001982  jz      short loc_1800019B0
0x180001984  mov     rcx, rbx; this
0x180001987  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x18000198c  jmp     loc_1800017C5
0x180001991  cmp     ebx, 800706BAh
0x180001997  jz      short loc_18000191A
0x180001999  cmp     ebx, 800706B5h
0x18000199f  jnz     short loc_180001934
0x1800019a1  jmp     loc_18000191A
0x1800019a6  mov     [rsp+98h+var_38], rcx
0x1800019ab  jmp     loc_1800017DB
0x1800019b0  mov     dword ptr [rbx+34h], 1
0x1800019b7  jmp     short loc_180001984
0x1800019b9  mov     rbx, rsi
0x1800019bc  jmp     loc_1800017C5
0x1800019c1  mov     ecx, 0Eh; dwErrCode
0x1800019c6  call    cs:__imp_SetLastError
0x1800019cd  nop     dword ptr [rax+rax+00h]
0x1800019d2  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800019d9  mov     ecx, 8; int
0x1800019de  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800019e3  jmp     loc_1800017DB
0x1800019e8  lea     r9, aGetclientdata; "GetClientData"
0x1800019ef  mov     r8d, ebx
0x1800019f2  lea     rdx, aRpcgetclientda; "RpcGetClientData failed: 0x%x in %s"
0x1800019f9  mov     ecx, 8; int
0x1800019fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001a03  jmp     loc_180001809
0x180032d5b  push    rbp
0x180032d5d  sub     rsp, 40h
0x180032d61  mov     rbp, rdx
0x180032d64  mov     rcx, [rcx]
0x180032d67  mov     ecx, [rcx]; ExceptionCode
0x180032d69  call    cs:__imp_I_RpcExceptionFilter
0x180032d70  nop     dword ptr [rax+rax+00h]
0x180032d75  nop
0x180032d76  add     rsp, 40h
0x180032d7a  pop     rbp
0x180032d7b  retn
```
