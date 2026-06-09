# WinStationNegotiateSession

- ea: `0x180012820`
- end: `0x180012a69`
- name: `WinStationNegotiateSession`
- size: `585`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004330`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180012820`
- `0x1800249e8`
- `0x180025cc6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800129a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800129a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012a4e`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800335ad`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800335ad`
- `RPCRT4!NdrClientCall3` at `0x180012919`
- `RPCRT4!NdrClientCall3` at `0x180012919`

## string_xrefs

- `0x1800129ca`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationNegotiateSession(__int64 a1, __int64 a2, _DWORD *a3, _DWORD *a4, _QWORD *a5, _DWORD *a6)
{
  _QWORD *v10; // r13
  _DWORD *v11; // r12
  CPublicBinding *v12; // rax
  void *v13; // rax
  DWORD LastError; // edi
  size_t v16; // rsi
  HLOCAL v17; // rax
  __int64 v18; // [rsp+48h] [rbp-50h] BYREF
  CPublicBinding *v19; // [rsp+50h] [rbp-48h]
  void *Src[2]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v21; // [rsp+68h] [rbp-30h]
  CLIENT_CALL_RETURN v22; // [rsp+A8h] [rbp+10h] BYREF
  _DWORD *v23; // [rsp+B0h] [rbp+18h]
  _DWORD *v24; // [rsp+B8h] [rbp+20h]

  v24 = a4;
  v23 = a3;
  *a3 = 0;
  *a4 = 0;
  v10 = a5;
  *a5 = 0;
  v11 = a6;
  *a6 = 0;
  *(_OWORD *)Src = 0;
  v21 = 0;
  v18 = 0;
  LODWORD(v22.Pointer) = 0;
  v12 = (CPublicBinding *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
    v12 = CPublicBinding::CPublicBinding(v12, 0, 0, (unsigned int *)&v22);
  v19 = v12;
  if ( v12 )
  {
    HIDWORD(v18) = 1;
  }
  else
  {
    SetLastError(0xEu);
    _DbgPrintMessage(8, "new CPublicBinding");
  }
  if ( CSmartPublicBinding::operator void *((unsigned __int16 *)&v18) )
  {
    v13 = CSmartPublicBinding::operator void *((unsigned __int16 *)&v18);
    v22.Simple = 0;
    v22.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351D0, 5u, 0, v13, a1, a2, Src).Pointer;
    LastError = ConvertHRESULT2WIN32(v22.Simple);
    if ( !LastError )
    {
      if ( HIDWORD(Src[0]) && Src[1] )
      {
        v16 = 4LL * HIDWORD(Src[0]);
        if ( v16 < HIDWORD(Src[0]) || v16 < 4 )
        {
          LastError = 534;
          goto LABEL_9;
        }
        v17 = LocalAlloc(0x40u, 4LL * HIDWORD(Src[0]));
        *v10 = v17;
        if ( v17 )
        {
          memcpy_0(v17, Src[1], v16);
          *a4 = HIDWORD(Src[0]);
        }
        else
        {
          LastError = 8;
        }
        LocalFree(Src[1]);
      }
      *a3 = Src[0];
      *v11 = v21;
    }
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
  }
LABEL_9:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)&v18);
  return LastError;
}

```

## disassembly

```asm
0x180012820  mov     r11, rsp
0x180012823  mov     [r11+8], rsi
0x180012827  mov     [r11+20h], r9
0x18001282b  mov     [r11+18h], r8
0x18001282f  push    rdi
0x180012830  push    r12
0x180012832  push    r13
0x180012834  push    r14
0x180012836  push    r15
0x180012838  sub     rsp, 70h
0x18001283c  mov     r15, r9
0x18001283f  mov     r14, r8
0x180012842  mov     rdi, rdx
0x180012845  mov     rsi, rcx
0x180012848  mov     dword ptr [r8], 0
0x18001284f  mov     dword ptr [r9], 0
0x180012856  mov     r13, [rsp+98h+arg_20]
0x18001285e  mov     qword ptr [r13+0], 0
0x180012866  mov     r12, [rsp+98h+arg_28]
0x18001286e  mov     dword ptr [r12], 0
0x180012876  xorps   xmm0, xmm0
0x180012879  xor     eax, eax
0x18001287b  movups  xmmword ptr [rsp+98h+Src], xmm0
0x180012880  mov     [r11-30h], rax
0x180012884  mov     [r11-50h], rax
0x180012888  mov     [r11+10h], eax
0x18001288c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012893  lea     ecx, [rax+40h]; unsigned __int64
0x180012896  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001289b  test    rax, rax
0x18001289e  jz      short loc_1800128B5
0x1800128a0  lea     r9, [rsp+98h+arg_8]; unsigned int *
0x1800128a8  xor     r8d, r8d; int
0x1800128ab  xor     edx, edx; unsigned __int16 *
0x1800128ad  mov     rcx, rax; this
0x1800128b0  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x1800128b5  mov     [rsp+98h+var_48], rax
0x1800128ba  test    rax, rax
0x1800128bd  jz      loc_1800129A3
0x1800128c3  mov     [rsp+98h+var_4C], 1
0x1800128cb  lea     rcx, [rsp+98h+var_50]; unsigned __int16 *
0x1800128d0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800128d5  test    rax, rax
0x1800128d8  jz      loc_1800129CA
0x1800128de  lea     rcx, [rsp+98h+var_50]; unsigned __int16 *
0x1800128e3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800128e8  mov     [rsp+98h+arg_8], 0
0x1800128f4  lea     rcx, [rsp+98h+Src]
0x1800128f9  mov     [rsp+98h+var_68], rcx
0x1800128fe  mov     [rsp+98h+var_70], rdi
0x180012903  mov     [rsp+98h+var_78], rsi
0x180012908  mov     r9, rax
0x18001290b  xor     r8d, r8d; pReturnValue
0x18001290e  lea     edx, [r8+5]; nProcNum
0x180012912  lea     rcx, stru_1800351D0; pProxyInfo
0x180012919  call    cs:__imp_NdrClientCall3
0x180012920  nop     dword ptr [rax+rax+00h]
0x180012925  mov     [rsp+98h+arg_8], rax
0x18001292d  mov     ecx, eax; int
0x18001292f  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180012934  mov     edi, eax
0x180012936  mov     [rsp+98h+var_58], eax
0x18001293a  jmp     short loc_180012962
0x18001293c  mov     edi, eax
0x18001293e  mov     [rsp+98h+var_58], eax
0x180012942  mov     r12, [rsp+98h+arg_28]
0x18001294a  mov     r13, [rsp+98h+arg_20]
0x180012952  mov     r15, [rsp+98h+arg_18]
0x18001295a  mov     r14, [rsp+98h+arg_10]
0x180012962  test    edi, edi
0x180012964  jnz     short loc_18001297B
0x180012966  cmp     dword ptr [rsp+98h+Src+4], edi
0x18001296a  jnz     short loc_1800129EB
0x18001296c  mov     eax, dword ptr [rsp+98h+Src]
0x180012970  mov     [r14], eax
0x180012973  mov     eax, dword ptr [rsp+98h+var_30]
0x180012977  mov     [r12], eax
0x18001297b  lea     rcx, [rsp+98h+var_50]; this
0x180012980  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180012985  mov     eax, edi
0x180012987  mov     rsi, [rsp+98h+arg_0]
0x18001298f  add     rsp, 70h
0x180012993  pop     r15
0x180012995  pop     r14
0x180012997  pop     r13
0x180012999  pop     r12
0x18001299b  pop     rdi
0x18001299c  retn
0x18001299e  jmp     loc_1800128B5
0x1800129a3  mov     ecx, 0Eh; dwErrCode
0x1800129a8  call    cs:__imp_SetLastError
0x1800129af  nop     dword ptr [rax+rax+00h]
0x1800129b4  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800129bb  mov     ecx, 8; int
0x1800129c0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800129c5  jmp     loc_1800128CB
0x1800129ca  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800129d1  mov     ecx, 8; int
0x1800129d6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800129db  call    cs:__imp_GetLastError
0x1800129e2  nop     dword ptr [rax+rax+00h]
0x1800129e7  mov     edi, eax
0x1800129e9  jmp     short loc_18001297B
0x1800129eb  cmp     [rsp+98h+Src+8], 0
0x1800129f1  jz      loc_18001296C
0x1800129f7  mov     eax, dword ptr [rsp+98h+Src+4]
0x1800129fb  lea     rsi, ds:0[rax*4]
0x180012a03  cmp     rsi, rax
0x180012a06  jb      short loc_180012A5F
0x180012a08  cmp     rsi, 4
0x180012a0c  jb      short loc_180012A5F
0x180012a0e  mov     rdx, rsi; uBytes
0x180012a11  mov     ecx, 40h ; '@'; uFlags
0x180012a16  call    cs:__imp_LocalAlloc
0x180012a1d  nop     dword ptr [rax+rax+00h]
0x180012a22  mov     [r13+0], rax
0x180012a26  test    rax, rax
0x180012a29  jz      short loc_180012A44
0x180012a2b  mov     r8, rsi; Size
0x180012a2e  mov     rdx, [rsp+98h+Src+8]; Src
0x180012a33  mov     rcx, rax; void *
0x180012a36  call    memcpy_0
0x180012a3b  mov     eax, dword ptr [rsp+98h+Src+4]
0x180012a3f  mov     [r15], eax
0x180012a42  jmp     short loc_180012A49
0x180012a44  mov     edi, 8
0x180012a49  mov     rcx, [rsp+98h+Src+8]; hMem
0x180012a4e  call    cs:__imp_LocalFree
0x180012a55  nop     dword ptr [rax+rax+00h]
0x180012a5a  jmp     loc_18001296C
0x180012a5f  mov     edi, 216h
0x180012a64  jmp     loc_18001297B
0x18003359f  push    rbp
0x1800335a1  sub     rsp, 40h
0x1800335a5  mov     rbp, rdx
0x1800335a8  mov     rcx, [rcx]
0x1800335ab  mov     ecx, [rcx]; ExceptionCode
0x1800335ad  call    cs:__imp_I_RpcExceptionFilter
0x1800335b4  nop     dword ptr [rax+rax+00h]
0x1800335b9  nop
0x1800335ba  add     rsp, 40h
0x1800335be  pop     rbp
0x1800335bf  retn
```
