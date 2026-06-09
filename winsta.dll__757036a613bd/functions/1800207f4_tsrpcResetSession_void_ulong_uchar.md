# _tsrpcResetSession(void *,ulong,uchar)

- ea: `0x1800207f4`
- end: `0x180020adc`
- name: `?_tsrpcResetSession@@YAJPEAXKE@Z`
- size: `744`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1800281d0`

## callees

- `0x1800039e8`
- `0x180003ad4`
- `0x180003b48`
- `0x1800046ec`
- `0x180005c30`
- `0x180007030`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800207f4`
- `0x180020b7c`
- `0x180021d70`
- `0x1800227f0`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020891`
- `RPCRT4!NdrClientCall3` at `0x180020a70`
- `RPCRT4!NdrClientCall3` at `0x180020a70`

## string_xrefs

- `0x1800208a6`: `_tsrpcResetSession - Failed to open binding`
- `0x180020918`: `_tsrpcResetSession - Failed to open RCM binding`
- `0x1800209f8`: `Session.Open failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall _tsrpcResetSession(void *a1, unsigned int a2, char a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v8; // eax
  void *v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  void *v13; // rax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  __int64 v18; // [rsp+40h] [rbp-1B8h] BYREF
  unsigned __int16 v19[4]; // [rsp+48h] [rbp-1B0h] BYREF
  unsigned __int16 v20[12]; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 v21; // [rsp+70h] [rbp-188h] BYREF
  int v22; // [rsp+78h] [rbp-180h]
  __int128 v23; // [rsp+80h] [rbp-178h]
  __int128 v24; // [rsp+90h] [rbp-168h]
  __int128 v25; // [rsp+A0h] [rbp-158h]
  __int64 v26; // [rsp+B0h] [rbp-148h]
  _QWORD v27[27]; // [rsp+B8h] [rbp-140h] BYREF
  unsigned __int16 v28[40]; // [rsp+190h] [rbp-68h] BYREF

  v21 = 0;
  v22 = -1;
  v27[26] = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  memset_0(v27, 0, 0xD0u);
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v20, a1, 0);
  if ( CSmartPublicBinding::operator void *(v20) )
  {
    if ( a2 == -1 )
    {
      _DbgPrintMessage(8, "_tsrpcResetSession - SessionId is LOGONID_CURRENT - UNEXPECTED!!");
      v7 = -2147467259;
    }
    else if ( a2 < 0x10000 )
    {
      v13 = (void *)CSmartPublicBinding::operator void *(v20);
      v14 = CSmartSession::Open((CSmartSession *)&v21, a2, v13);
      v7 = v14;
      if ( v14 >= 0 )
      {
        v15 = CSmartSession::Logoff((CSmartSession *)&v21);
        v7 = v15;
        LODWORD(v18) = v15;
        if ( v15 >= 0 )
        {
          if ( a3 )
          {
            v16 = CSmartPublicBinding::operator void *(v20);
            *(CLIENT_CALL_RETURN *)v19 = NdrClientCall3(
                                           (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                           0,
                                           0,
                                           v16,
                                           a2,
                                           8,
                                           120000);
          }
        }
        else
        {
          _DbgPrintMessage(8, "Session::Logoff failed: 0x%x in %s", (unsigned int)v15, "_tsrpcResetSession");
        }
      }
      else
      {
        _DbgPrintMessage(8, "Session.Open failed: 0x%x in %s", (unsigned int)v14, "_tsrpcResetSession");
      }
    }
    else
    {
      CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v19, a1, 1);
      v18 = 0;
      if ( CSmartPublicBinding::operator void *(v19) )
      {
        v8 = _tsrpcSessionNameFromLogonId(a1, a2, v28);
        v7 = v8;
        if ( v8 >= 0 )
        {
          v9 = (void *)CSmartPublicBinding::operator void *(v19);
          v10 = CListener::Open((CListener *)&v18, v9, v28);
          v7 = v10;
          if ( v10 >= 0 )
          {
            v11 = CListener::Stop((CListener *)&v18);
            v7 = v11;
            if ( v11 >= 0 )
            {
              v12 = CListener::Start((CListener *)&v18);
              v7 = v12;
              if ( v12 < 0 )
                _DbgPrintMessage(8, "Listener.Start failed: 0x%x in %s", (unsigned int)v12, "_tsrpcResetSession");
            }
            else
            {
              _DbgPrintMessage(8, "Listener.Stop failed: 0x%x in %s", (unsigned int)v11, "_tsrpcResetSession");
            }
          }
          else
          {
            _DbgPrintMessage(8, "Listener.Initialize failed: 0x%x in %s", (unsigned int)v10, "_tsrpcResetSession");
          }
        }
        else
        {
          _DbgPrintMessage(8, "_tsrpcSessionNameFromLogonId failed: 0x%x in %s", (unsigned int)v8, "_tsrpcResetSession");
        }
      }
      else
      {
        v7 = -2147024882;
        _DbgPrintMessage(8, "_tsrpcResetSession - Failed to open RCM binding");
      }
      CListener::~CListener((CListener *)&v18);
      CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v19);
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "_tsrpcResetSession - Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v20);
  CSmartSession::~CSmartSession((CSmartSession *)&v21);
  return v7;
}

```

## disassembly

```asm
0x1800207f4  mov     r11, rsp
0x1800207f7  mov     [r11+18h], rbx
0x1800207fb  mov     [r11+20h], rsi
0x1800207ff  push    rdi
0x180020800  sub     rsp, 1F0h
0x180020807  mov     rax, cs:__security_cookie
0x18002080e  xor     rax, rsp
0x180020811  mov     [rsp+1F8h+var_18], rax
0x180020819  mov     sil, r8b
0x18002081c  mov     edi, edx
0x18002081e  mov     rbx, rcx
0x180020821  mov     [rsp+1F8h+var_188], 0
0x18002082a  mov     [rsp+1F8h+var_180], 0FFFFFFFFh
0x180020832  mov     qword ptr [r11-70h], 0
0x18002083a  xorps   xmm0, xmm0
0x18002083d  xor     eax, eax
0x18002083f  movups  [rsp+1F8h+var_178], xmm0
0x180020847  movups  [rsp+1F8h+var_168], xmm0
0x18002084f  movups  [rsp+1F8h+var_158], xmm0
0x180020857  mov     [r11-148h], rax
0x18002085e  xor     edx, edx; Val
0x180020860  mov     r8d, 0D0h; Size
0x180020866  lea     rcx, [r11-140h]; void *
0x18002086d  call    memset_0
0x180020872  xor     r8d, r8d; int
0x180020875  mov     rdx, rbx; void *
0x180020878  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18002087d  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180020882  lea     rcx, [rsp+1F8h+var_1A0]; unsigned __int16 *
0x180020887  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002088c  test    rax, rax
0x18002088f  jnz     short loc_1800208BC
0x180020891  call    cs:__imp_GetLastError
0x180020897  mov     ebx, eax
0x180020899  test    eax, eax
0x18002089b  jle     short loc_1800208A6
0x18002089d  movzx   ebx, ax
0x1800208a0  or      ebx, 80070000h
0x1800208a6  lea     rdx, aTsrpcresetsess_3; "_tsrpcResetSession - Failed to open bin"...
0x1800208ad  mov     ecx, 8; int
0x1800208b2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800208b7  jmp     loc_180020AA1
0x1800208bc  cmp     edi, 0FFFFFFFFh
0x1800208bf  jnz     short loc_1800208DC
0x1800208c1  lea     rdx, aTsrpcresetsess; "_tsrpcResetSession - SessionId is LOGON"...
0x1800208c8  mov     ecx, 8; int
0x1800208cd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800208d2  mov     ebx, 80004005h
0x1800208d7  jmp     loc_180020AA1
0x1800208dc  cmp     edi, 10000h
0x1800208e2  jb      loc_1800209D9
0x1800208e8  mov     r8d, 1; int
0x1800208ee  mov     rdx, rbx; void *
0x1800208f1  lea     rcx, [rsp+1F8h+var_1B0]; this
0x1800208f6  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800208fb  mov     [rsp+1F8h+var_1B8], 0
0x180020904  lea     rcx, [rsp+1F8h+var_1B0]; unsigned __int16 *
0x180020909  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002090e  test    rax, rax
0x180020911  jnz     short loc_180020940
0x180020913  mov     ebx, 8007000Eh
0x180020918  lea     rdx, aTsrpcresetsess_0; "_tsrpcResetSession - Failed to open RCM"...
0x18002091f  lea     ecx, [rax+8]; int
0x180020922  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020927  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18002092c  call    ??1CListener@@QEAA@XZ; CListener::~CListener(void)
0x180020931  lea     rcx, [rsp+1F8h+var_1B0]; this
0x180020936  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x18002093b  jmp     loc_180020AA1
0x180020940  lea     r8, [rsp+1F8h+var_68]; unsigned __int16 *
0x180020948  mov     edx, edi; unsigned int
0x18002094a  mov     rcx, rbx; void *
0x18002094d  call    ?_tsrpcSessionNameFromLogonId@@YAJPEAXKPEAG@Z; _tsrpcSessionNameFromLogonId(void *,ulong,ushort *)
0x180020952  mov     ebx, eax
0x180020954  test    eax, eax
0x180020956  jns     short loc_180020975
0x180020958  lea     rdx, aTsrpcsessionna_0; "_tsrpcSessionNameFromLogonId failed: 0x"...
0x18002095f  mov     r8d, eax
0x180020962  lea     r9, aTsrpcresetsess_1; "_tsrpcResetSession"
0x180020969  mov     ecx, 8; int
0x18002096e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020973  jmp     short loc_180020927
0x180020975  lea     rcx, [rsp+1F8h+var_1B0]; unsigned __int16 *
0x18002097a  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002097f  mov     rdx, rax; void *
0x180020982  lea     r8, [rsp+1F8h+var_68]; unsigned __int16 *
0x18002098a  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18002098f  call    ?Open@CListener@@QEAAJPEAXPEAG@Z; CListener::Open(void *,ushort *)
0x180020994  mov     ebx, eax
0x180020996  test    eax, eax
0x180020998  jns     short loc_1800209A3
0x18002099a  lea     rdx, aListenerInitia; "Listener.Initialize failed: 0x%x in %s"
0x1800209a1  jmp     short loc_18002095F
0x1800209a3  lea     rcx, [rsp+1F8h+var_1B8]; this
0x1800209a8  call    ?Stop@CListener@@QEAAJXZ; CListener::Stop(void)
0x1800209ad  mov     ebx, eax
0x1800209af  test    eax, eax
0x1800209b1  jns     short loc_1800209BC
0x1800209b3  lea     rdx, aListenerStopFa; "Listener.Stop failed: 0x%x in %s"
0x1800209ba  jmp     short loc_18002095F
0x1800209bc  lea     rcx, [rsp+1F8h+var_1B8]; this
0x1800209c1  call    ?Start@CListener@@QEAAJXZ; CListener::Start(void)
0x1800209c6  mov     ebx, eax
0x1800209c8  test    eax, eax
0x1800209ca  jns     loc_180020927
0x1800209d0  lea     rdx, aListenerStartF; "Listener.Start failed: 0x%x in %s"
0x1800209d7  jmp     short loc_18002095F
0x1800209d9  lea     rcx, [rsp+1F8h+var_1A0]; unsigned __int16 *
0x1800209de  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800209e3  mov     r8, rax; void *
0x1800209e6  mov     edx, edi; unsigned int
0x1800209e8  lea     rcx, [rsp+1F8h+var_188]; this
0x1800209ed  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x1800209f2  mov     ebx, eax
0x1800209f4  test    eax, eax
0x1800209f6  jns     short loc_180020A18
0x1800209f8  lea     rdx, aSessionOpenFai; "Session.Open failed: 0x%x in %s"
0x1800209ff  mov     r8d, eax
0x180020a02  lea     r9, aTsrpcresetsess_1; "_tsrpcResetSession"
0x180020a09  mov     ecx, 8; int
0x180020a0e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020a13  jmp     loc_180020AA1
0x180020a18  lea     rcx, [rsp+1F8h+var_188]; this
0x180020a1d  call    ?Logoff@CSmartSession@@QEAAJXZ; CSmartSession::Logoff(void)
0x180020a22  mov     ebx, eax
0x180020a24  mov     dword ptr [rsp+1F8h+var_1B8], eax
0x180020a28  test    eax, eax
0x180020a2a  jns     short loc_180020A35
0x180020a2c  lea     rdx, aSessionLogoffF; "Session::Logoff failed: 0x%x in %s"
0x180020a33  jmp     short loc_1800209FF
0x180020a35  test    sil, sil
0x180020a38  jz      short loc_180020AA1
0x180020a3a  lea     rcx, [rsp+1F8h+var_1A0]; unsigned __int16 *
0x180020a3f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180020a44  mov     qword ptr [rsp+1F8h+var_1B0], 0
0x180020a4d  mov     [rsp+1F8h+var_1C8], 1D4C0h
0x180020a55  mov     [rsp+1F8h+var_1D0], 8
0x180020a5d  mov     [rsp+1F8h+var_1D8], edi
0x180020a61  mov     r9, rax
0x180020a64  xor     r8d, r8d; pReturnValue
0x180020a67  xor     edx, edx; nProcNum
0x180020a69  lea     rcx, pProxyInfo; pProxyInfo
0x180020a70  call    cs:__imp_NdrClientCall3
0x180020a76  mov     qword ptr [rsp+1F8h+var_1B0], rax
0x180020a7b  jmp     short loc_180020AA1
0x180020a7d  test    eax, eax
0x180020a7f  jle     short loc_180020A89
0x180020a81  movzx   eax, ax
0x180020a84  or      eax, 80070000h
0x180020a89  mov     r8d, eax
0x180020a8c  lea     rdx, aRpcwaitforsess; "RpcWaitForSessionState( State_Down ) fa"...
0x180020a93  mov     ecx, 8; int
0x180020a98  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180020a9d  mov     ebx, dword ptr [rsp+1F8h+var_1B8]
0x180020aa1  lea     rcx, [rsp+1F8h+var_1A0]; this
0x180020aa6  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180020aab  lea     rcx, [rsp+1F8h+var_188]; this
0x180020ab0  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180020ab5  mov     eax, ebx
0x180020ab7  mov     rcx, [rsp+1F8h+var_18]
0x180020abf  xor     rcx, rsp; StackCookie
0x180020ac2  call    __security_check_cookie
0x180020ac7  lea     r11, [rsp+1F8h+var_8]
0x180020acf  mov     rbx, [r11+20h]
0x180020ad3  mov     rsi, [r11+28h]
0x180020ad7  mov     rsp, r11
0x180020ada  pop     rdi
0x180020adb  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
