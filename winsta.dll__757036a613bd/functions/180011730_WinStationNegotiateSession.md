# WinStationNegotiateSession

- ea: `0x180011730`
- end: `0x180011956`
- name: `WinStationNegotiateSession`
- size: `550`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180005db0`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180011730`
- `0x1800230b8`
- `0x180024376`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800118b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001190f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001190f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011941`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011941`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800306c7`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800306c7`
- `RPCRT4!NdrClientCall3` at `0x180011829`
- `RPCRT4!NdrClientCall3` at `0x180011829`

## string_xrefs

- `0x1800118cd`: `Failed to open binding`

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
    v22.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800321A0, 5u, 0, v13, a1, a2, Src).Pointer;
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
0x180011730  mov     r11, rsp
0x180011733  mov     [r11+8], rsi
0x180011737  mov     [r11+20h], r9
0x18001173b  mov     [r11+18h], r8
0x18001173f  push    rdi
0x180011740  push    r12
0x180011742  push    r13
0x180011744  push    r14
0x180011746  push    r15
0x180011748  sub     rsp, 70h
0x18001174c  mov     r15, r9
0x18001174f  mov     r14, r8
0x180011752  mov     rdi, rdx
0x180011755  mov     rsi, rcx
0x180011758  mov     dword ptr [r8], 0
0x18001175f  mov     dword ptr [r9], 0
0x180011766  mov     r13, [rsp+98h+arg_20]
0x18001176e  mov     qword ptr [r13+0], 0
0x180011776  mov     r12, [rsp+98h+arg_28]
0x18001177e  mov     dword ptr [r12], 0
0x180011786  xorps   xmm0, xmm0
0x180011789  xor     eax, eax
0x18001178b  movups  xmmword ptr [rsp+98h+Src], xmm0
0x180011790  mov     [r11-30h], rax
0x180011794  mov     [r11-50h], rax
0x180011798  mov     [r11+10h], eax
0x18001179c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800117a3  lea     ecx, [rax+40h]; unsigned __int64
0x1800117a6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800117ab  test    rax, rax
0x1800117ae  jz      short loc_1800117C5
0x1800117b0  lea     r9, [rsp+98h+arg_8]; unsigned int *
0x1800117b8  xor     r8d, r8d; int
0x1800117bb  xor     edx, edx; unsigned __int16 *
0x1800117bd  mov     rcx, rax; this
0x1800117c0  call    ??0CPublicBinding@@QEAA@PEBGHPEAK@Z; CPublicBinding::CPublicBinding(ushort const *,int,ulong *)
0x1800117c5  mov     [rsp+98h+var_48], rax
0x1800117ca  test    rax, rax
0x1800117cd  jz      loc_1800118AC
0x1800117d3  mov     [rsp+98h+var_4C], 1
0x1800117db  lea     rcx, [rsp+98h+var_50]; unsigned __int16 *
0x1800117e0  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800117e5  test    rax, rax
0x1800117e8  jz      loc_1800118CD
0x1800117ee  lea     rcx, [rsp+98h+var_50]; unsigned __int16 *
0x1800117f3  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800117f8  mov     [rsp+98h+arg_8], 0
0x180011804  lea     rcx, [rsp+98h+Src]
0x180011809  mov     [rsp+98h+var_68], rcx
0x18001180e  mov     [rsp+98h+var_70], rdi
0x180011813  mov     [rsp+98h+var_78], rsi
0x180011818  mov     r9, rax
0x18001181b  xor     r8d, r8d; pReturnValue
0x18001181e  lea     edx, [r8+5]; nProcNum
0x180011822  lea     rcx, stru_1800321A0; pProxyInfo
0x180011829  call    cs:__imp_NdrClientCall3
0x18001182f  mov     [rsp+98h+arg_8], rax
0x180011837  mov     ecx, eax; int
0x180011839  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x18001183e  mov     edi, eax
0x180011840  mov     [rsp+98h+var_58], eax
0x180011844  jmp     short loc_18001186C
0x180011846  mov     edi, eax
0x180011848  mov     [rsp+98h+var_58], eax
0x18001184c  mov     r12, [rsp+98h+arg_28]
0x180011854  mov     r13, [rsp+98h+arg_20]
0x18001185c  mov     r15, [rsp+98h+arg_18]
0x180011864  mov     r14, [rsp+98h+arg_10]
0x18001186c  test    edi, edi
0x18001186e  jnz     short loc_180011885
0x180011870  cmp     dword ptr [rsp+98h+Src+4], edi
0x180011874  jnz     short loc_1800118E8
0x180011876  mov     eax, dword ptr [rsp+98h+Src]
0x18001187a  mov     [r14], eax
0x18001187d  mov     eax, dword ptr [rsp+98h+var_30]
0x180011881  mov     [r12], eax
0x180011885  lea     rcx, [rsp+98h+var_50]; this
0x18001188a  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18001188f  mov     eax, edi
0x180011891  mov     rsi, [rsp+98h+arg_0]
0x180011899  add     rsp, 70h
0x18001189d  pop     r15
0x18001189f  pop     r14
0x1800118a1  pop     r13
0x1800118a3  pop     r12
0x1800118a5  pop     rdi
0x1800118a6  retn
0x1800118a7  jmp     loc_1800117C5
0x1800118ac  mov     ecx, 0Eh; dwErrCode
0x1800118b1  call    cs:__imp_SetLastError
0x1800118b7  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x1800118be  mov     ecx, 8; int
0x1800118c3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800118c8  jmp     loc_1800117DB
0x1800118cd  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x1800118d4  mov     ecx, 8; int
0x1800118d9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800118de  call    cs:__imp_GetLastError
0x1800118e4  mov     edi, eax
0x1800118e6  jmp     short loc_180011885
0x1800118e8  cmp     [rsp+98h+Src+8], 0
0x1800118ee  jz      short loc_180011876
0x1800118f0  mov     eax, dword ptr [rsp+98h+Src+4]
0x1800118f4  lea     rsi, ds:0[rax*4]
0x1800118fc  cmp     rsi, rax
0x1800118ff  jb      short loc_18001194C
0x180011901  cmp     rsi, 4
0x180011905  jb      short loc_18001194C
0x180011907  mov     rdx, rsi; uBytes
0x18001190a  mov     ecx, 40h ; '@'; uFlags
0x18001190f  call    cs:__imp_LocalAlloc
0x180011915  mov     [r13+0], rax
0x180011919  test    rax, rax
0x18001191c  jz      short loc_180011937
0x18001191e  mov     r8, rsi; Size
0x180011921  mov     rdx, [rsp+98h+Src+8]; Src
0x180011926  mov     rcx, rax; void *
0x180011929  call    memcpy_0
0x18001192e  mov     eax, dword ptr [rsp+98h+Src+4]
0x180011932  mov     [r15], eax
0x180011935  jmp     short loc_18001193C
0x180011937  mov     edi, 8
0x18001193c  mov     rcx, [rsp+98h+Src+8]; hMem
0x180011941  call    cs:__imp_LocalFree
0x180011947  jmp     loc_180011876
0x18001194c  mov     edi, 216h
0x180011951  jmp     loc_180011885
0x1800306b9  push    rbp
0x1800306bb  sub     rsp, 40h
0x1800306bf  mov     rbp, rdx
0x1800306c2  mov     rcx, [rcx]
0x1800306c5  mov     ecx, [rcx]; ExceptionCode
0x1800306c7  call    cs:__imp_I_RpcExceptionFilter
0x1800306cd  nop
0x1800306ce  add     rsp, 40h
0x1800306d2  pop     rbp
0x1800306d3  retn
```
