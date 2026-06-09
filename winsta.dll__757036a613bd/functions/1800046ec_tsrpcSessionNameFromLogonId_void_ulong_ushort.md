# _tsrpcSessionNameFromLogonId(void *,ulong,ushort *)

- ea: `0x1800046ec`
- end: `0x180004a27`
- name: `?_tsrpcSessionNameFromLogonId@@YAJPEAXKPEAG@Z`
- size: `827`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004450`
- `0x1800207f4`

## callees

- `0x1800039e8`
- `0x1800046ec`
- `0x180005c30`
- `0x180006040`
- `0x180007030`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000498a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000498a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030110`
- `RPCRT4!I_RpcExceptionFilter` at `0x180030110`
- `RPCRT4!NdrClientCall3` at `0x1800048b4`
- `RPCRT4!NdrClientCall3` at `0x1800048b4`

## string_xrefs

- `0x18000499f`: `_tsrpcSessionNameFromLogonId: Failed to open LSM binding`
- `0x180004a11`: `Session::Open failed: 0x%x in %s`
- `0x1800049f4`: `_tsrpcSessionNameFromLogonId: Failed to open RCM binding`

## pseudocode

```c
__int64 __fastcall _tsrpcSessionNameFromLogonId(void *a1, unsigned int a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rsi
  CLIENT_CALL_RETURN v6; // rbx
  void *v7; // rax
  int v8; // eax
  int TerminalName; // eax
  __int64 v11; // rax
  unsigned int v12; // edx
  HLOCAL v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int16 *v16; // r9
  __int64 v17; // rcx
  unsigned __int16 v18; // r10
  unsigned __int16 *v19; // rax
  _DWORD v20[4]; // [rsp+40h] [rbp-198h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-188h] BYREF
  unsigned __int16 v22[8]; // [rsp+58h] [rbp-180h] BYREF
  CLIENT_CALL_RETURN v23; // [rsp+68h] [rbp-170h]
  unsigned __int16 *v24; // [rsp+70h] [rbp-168h]
  unsigned __int16 v25[12]; // [rsp+78h] [rbp-160h] BYREF
  __int64 v26; // [rsp+90h] [rbp-148h] BYREF
  int v27; // [rsp+98h] [rbp-140h]
  __int128 v28; // [rsp+A0h] [rbp-138h]
  __int128 v29; // [rsp+B0h] [rbp-128h]
  __int128 v30; // [rsp+C0h] [rbp-118h]
  __int64 v31; // [rsp+D0h] [rbp-108h]
  _QWORD v32[27]; // [rsp+D8h] [rbp-100h] BYREF

  v3 = a3;
  v20[2] = a2;
  v24 = a3;
  LODWORD(v6.Pointer) = -2147024882;
  v26 = 0;
  v27 = -1;
  v32[26] = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(v32, 0, 0xD0u);
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v25, a1, 0);
  if ( CSmartPublicBinding::operator void *(v25) )
  {
    if ( a2 == -1 )
    {
      _DbgPrintMessage(8, "_tsrpcSessionNameFromLogonId - LogonId is LOGONID_CURRENT - UNEXPECTED!!");
      LODWORD(v6.Pointer) = -2147467259;
    }
    else if ( a2 >= 0x10000 )
    {
      CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v22, a1, 1);
      hMem = 0;
      v20[0] = 0;
      if ( CSmartPublicBinding::operator void *(v22) )
      {
        v11 = CSmartPublicBinding::operator void *(v22);
        v23.Simple = 0;
        v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0, 8u, 0, v11, &hMem, 1, v20).Pointer;
        v23.Pointer = v6.Pointer;
        v20[1] = v6.Pointer;
        if ( SLODWORD(v6.Simple) < 0 )
        {
          _DbgPrintMessage(
            8,
            "RcpGetAllListeners failed: 0x%x in %s",
            LODWORD(v6.Pointer),
            "_tsrpcSessionNameFromLogonId");
        }
        else
        {
          v12 = 0;
          v13 = hMem;
          while ( v12 < v20[0] )
          {
            v14 = 80LL * v12;
            if ( *(_DWORD *)((char *)hMem + v14 + 4) == a2 )
            {
              v15 = 2147483646;
              v16 = (unsigned __int16 *)((char *)hMem + v14 + 12);
              v17 = 32;
              do
              {
                if ( !v15 )
                  break;
                v18 = *v16;
                if ( !*v16 )
                  break;
                ++v16;
                *v3++ = v18;
                --v15;
                --v17;
              }
              while ( v17 );
              v19 = v3 - 1;
              if ( v17 )
                v19 = v3;
              *v19 = 0;
              LODWORD(v6.Pointer) = v17 == 0 ? 0x8007007A : 0;
              break;
            }
            ++v12;
          }
          if ( v12 == v20[0] )
            LODWORD(v6.Pointer) = -2147017874;
          if ( v13 )
            LocalFree(v13);
        }
      }
      else
      {
        _DbgPrintMessage(8, "_tsrpcSessionNameFromLogonId: Failed to open RCM binding");
      }
      CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v22);
    }
    else
    {
      v7 = (void *)CSmartPublicBinding::operator void *(v25);
      v8 = CSmartSession::Open((CSmartSession *)&v26, a2, v7);
      if ( v8 == -2147024894 )
        v8 = -2147017874;
      LODWORD(v6.Pointer) = v8;
      if ( v8 < 0 )
      {
        _DbgPrintMessage(8, "Session::Open failed: 0x%x in %s", v8, "_tsrpcSessionNameFromLogonId");
      }
      else
      {
        TerminalName = CSmartSession::GetTerminalName((CSmartSession *)&v26, v3);
        if ( TerminalName == -2147024891 )
          TerminalName = -2147017874;
        LODWORD(v6.Pointer) = TerminalName;
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "_tsrpcSessionNameFromLogonId: Failed to open LSM binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v25);
  CSmartSession::~CSmartSession((CSmartSession *)&v26);
  return LODWORD(v6.Pointer);
}

```

## disassembly

```asm
0x1800046ec  mov     r11, rsp
0x1800046ef  mov     [r11+8], rbx
0x1800046f3  mov     [r11+20h], rsi
0x1800046f7  push    rdi
0x1800046f8  push    r14
0x1800046fa  push    r15
0x1800046fc  sub     rsp, 1C0h
0x180004703  mov     rax, cs:__security_cookie
0x18000470a  xor     rax, rsp
0x18000470d  mov     [rsp+1D8h+var_28], rax
0x180004715  mov     rsi, r8
0x180004718  mov     r14d, edx
0x18000471b  mov     r15, rcx
0x18000471e  mov     [rsp+1D8h+var_190], edx
0x180004722  mov     [rsp+1D8h+var_168], r8
0x180004727  mov     ebx, 8007000Eh
0x18000472c  xor     edi, edi
0x18000472e  mov     [r11-148h], rdi
0x180004735  mov     [rsp+1D8h+var_140], 0FFFFFFFFh
0x180004740  mov     [r11-30h], rdi
0x180004744  xorps   xmm0, xmm0
0x180004747  xor     eax, eax
0x180004749  movups  [rsp+1D8h+var_138], xmm0
0x180004751  movups  [rsp+1D8h+var_128], xmm0
0x180004759  movups  [rsp+1D8h+var_118], xmm0
0x180004761  mov     [r11-108h], rax
0x180004768  xor     edx, edx; Val
0x18000476a  mov     r8d, 0D0h; Size
0x180004770  lea     rcx, [r11-100h]; void *
0x180004777  call    memset_0
0x18000477c  xor     r8d, r8d; int
0x18000477f  mov     rdx, r15; void *
0x180004782  lea     rcx, [rsp+1D8h+var_160]; this
0x180004787  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18000478c  lea     rcx, [rsp+1D8h+var_160]; unsigned __int16 *
0x180004791  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180004796  test    rax, rax
0x180004799  jz      loc_18000499F
0x18000479f  cmp     r14d, 0FFFFFFFFh
0x1800047a3  jz      loc_1800049D9
0x1800047a9  cmp     r14d, 10000h
0x1800047b0  jnb     loc_180004849
0x1800047b6  lea     rcx, [rsp+1D8h+var_160]; unsigned __int16 *
0x1800047bb  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800047c0  mov     r8, rax; void *
0x1800047c3  mov     edx, r14d; unsigned int
0x1800047c6  lea     rcx, [rsp+1D8h+var_148]; this
0x1800047ce  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x1800047d3  mov     r14d, 80071B6Eh
0x1800047d9  cmp     eax, 80070002h
0x1800047de  cmovz   eax, r14d
0x1800047e2  mov     ebx, eax
0x1800047e4  test    eax, eax
0x1800047e6  js      loc_180004A07
0x1800047ec  mov     rdx, rsi; unsigned __int16 *
0x1800047ef  lea     rcx, [rsp+1D8h+var_148]; this
0x1800047f7  call    ?GetTerminalName@CSmartSession@@QEAAJPEAG@Z; CSmartSession::GetTerminalName(ushort *)
0x1800047fc  cmp     eax, 80070005h
0x180004801  cmovz   eax, r14d
0x180004805  mov     ebx, eax
0x180004807  lea     rcx, [rsp+1D8h+var_160]; this
0x18000480c  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180004811  lea     rcx, [rsp+1D8h+var_148]; this
0x180004819  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x18000481e  mov     eax, ebx
0x180004820  mov     rcx, [rsp+1D8h+var_28]
0x180004828  xor     rcx, rsp; StackCookie
0x18000482b  call    __security_check_cookie
0x180004830  lea     r11, [rsp+1D8h+var_18]
0x180004838  mov     rbx, [r11+20h]
0x18000483c  mov     rsi, [r11+38h]
0x180004840  mov     rsp, r11
0x180004843  pop     r15
0x180004845  pop     r14
0x180004847  pop     rdi
0x180004848  retn
0x180004849  mov     r8d, 1; int
0x18000484f  mov     rdx, r15; void *
0x180004852  lea     rcx, [rsp+1D8h+var_180]; this
0x180004857  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18000485c  mov     [rsp+1D8h+hMem], rdi
0x180004861  mov     [rsp+1D8h+var_198], edi
0x180004865  lea     rcx, [rsp+1D8h+var_180]; unsigned __int16 *
0x18000486a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18000486f  test    rax, rax
0x180004872  jz      loc_1800049F4
0x180004878  lea     rcx, [rsp+1D8h+var_180]; unsigned __int16 *
0x18000487d  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180004882  mov     [rsp+1D8h+var_170], rdi
0x180004887  lea     rcx, [rsp+1D8h+var_198]
0x18000488c  mov     [rsp+1D8h+var_1A8], rcx
0x180004891  mov     [rsp+1D8h+var_1B0], 1
0x180004899  lea     rcx, [rsp+1D8h+hMem]
0x18000489e  mov     [rsp+1D8h+var_1B8], rcx
0x1800048a3  mov     r9, rax
0x1800048a6  xor     r8d, r8d; pReturnValue
0x1800048a9  lea     edx, [r8+8]; nProcNum
0x1800048ad  lea     rcx, stru_1800320E0; pProxyInfo
0x1800048b4  call    cs:__imp_NdrClientCall3
0x1800048ba  mov     rbx, rax
0x1800048bd  mov     [rsp+1D8h+var_170], rax
0x1800048c2  mov     [rsp+1D8h+var_194], eax
0x1800048c6  jmp     short loc_1800048FA
0x1800048c8  test    eax, eax
0x1800048ca  jle     short loc_1800048D4
0x1800048cc  movzx   eax, ax
0x1800048cf  or      eax, 80070000h
0x1800048d4  mov     ebx, eax
0x1800048d6  mov     [rsp+1D8h+var_194], eax
0x1800048da  mov     r8d, eax
0x1800048dd  lea     rdx, aRcpgetallliste; "RcpGetAllListeners threw an exception: "...
0x1800048e4  mov     ecx, 8; int
0x1800048e9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800048ee  xor     edi, edi
0x1800048f0  mov     r14d, [rsp+1D8h+var_190]
0x1800048f5  mov     rsi, [rsp+1D8h+var_168]
0x1800048fa  test    ebx, ebx
0x1800048fc  js      loc_1800049B5
0x180004902  mov     edx, edi
0x180004904  mov     r8, [rsp+1D8h+hMem]
0x180004909  cmp     edx, [rsp+1D8h+var_198]
0x18000490d  jnb     short loc_180004974
0x18000490f  mov     eax, edx
0x180004911  lea     rcx, [rax+rax*4]
0x180004915  shl     rcx, 4
0x180004919  cmp     [rcx+r8+4], r14d
0x18000491e  jnz     loc_1800049D2
0x180004924  mov     eax, 7FFFFFFEh
0x180004929  lea     r9, [r8+0Ch]
0x18000492d  add     r9, rcx
0x180004930  mov     ecx, 20h ; ' '
0x180004935  test    rax, rax
0x180004938  jz      short loc_180004959
0x18000493a  movzx   r10d, word ptr [r9]
0x18000493e  test    r10w, r10w
0x180004942  jz      short loc_180004959
0x180004944  add     r9, 2
0x180004948  mov     [rsi], r10w
0x18000494c  add     rsi, 2
0x180004950  dec     rax
0x180004953  sub     rcx, 1
0x180004957  jnz     short loc_180004935
0x180004959  lea     rax, [rsi-2]
0x18000495d  test    rcx, rcx
0x180004960  cmovnz  rax, rsi
0x180004964  mov     [rax], di
0x180004967  neg     rcx
0x18000496a  sbb     ebx, ebx
0x18000496c  not     ebx
0x18000496e  and     ebx, 8007007Ah
0x180004974  mov     r14d, 80071B6Eh
0x18000497a  cmp     edx, [rsp+1D8h+var_198]
0x18000497e  cmovz   ebx, r14d
0x180004982  test    r8, r8
0x180004985  jz      short loc_180004990
0x180004987  mov     rcx, r8; hMem
0x18000498a  call    cs:__imp_LocalFree
0x180004990  lea     rcx, [rsp+1D8h+var_180]; this
0x180004995  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18000499a  jmp     loc_180004807
0x18000499f  lea     rdx, aTsrpcsessionna; "_tsrpcSessionNameFromLogonId: Failed to"...
0x1800049a6  mov     ecx, 8; int
0x1800049ab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800049b0  jmp     loc_180004807
0x1800049b5  lea     r9, aTsrpcsessionna_2; "_tsrpcSessionNameFromLogonId"
0x1800049bc  mov     r8d, ebx
0x1800049bf  lea     rdx, aRcpgetallliste_0; "RcpGetAllListeners failed: 0x%x in %s"
0x1800049c6  mov     ecx, 8; int
0x1800049cb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800049d0  jmp     short loc_180004990
0x1800049d2  inc     edx
0x1800049d4  jmp     loc_180004909
0x1800049d9  lea     rdx, aTsrpcsessionna_1; "_tsrpcSessionNameFromLogonId - LogonId "...
0x1800049e0  mov     ecx, 8; int
0x1800049e5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800049ea  mov     ebx, 80004005h
0x1800049ef  jmp     loc_180004807
0x1800049f4  lea     rdx, aTsrpcsessionna_3; "_tsrpcSessionNameFromLogonId: Failed to"...
0x1800049fb  mov     ecx, 8; int
0x180004a00  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004a05  jmp     short loc_180004990
0x180004a07  lea     r9, aTsrpcsessionna_2; "_tsrpcSessionNameFromLogonId"
0x180004a0e  mov     r8d, eax
0x180004a11  lea     rdx, aSessionOpenFai_0; "Session::Open failed: 0x%x in %s"
0x180004a18  mov     ecx, 8; int
0x180004a1d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004a22  jmp     loc_180004807
0x180030102  push    rbp
0x180030104  sub     rsp, 40h
0x180030108  mov     rbp, rdx
0x18003010b  mov     rcx, [rcx]
0x18003010e  mov     ecx, [rcx]; ExceptionCode
0x180030110  call    cs:__imp_I_RpcExceptionFilter
0x180030116  nop
0x180030117  add     rsp, 40h
0x18003011b  pop     rbp
0x18003011c  retn
```
