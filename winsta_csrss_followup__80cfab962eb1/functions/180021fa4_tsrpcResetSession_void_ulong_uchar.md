# _tsrpcResetSession(void *,ulong,uchar)

- ea: `0x180021fa4`
- end: `0x180022299`
- name: `?_tsrpcResetSession@@YAJPEAXKE@Z`
- size: `757`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180029d20`

## callees

- `0x180002014`
- `0x180002114`
- `0x1800041a0`
- `0x180005280`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x18000ad60`
- `0x18000adc4`
- `0x180021fa4`
- `0x180022340`
- `0x180023614`
- `0x1800240fc`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022041`
- `RPCRT4!NdrClientCall3` at `0x180022226`
- `RPCRT4!NdrClientCall3` at `0x180022226`

## string_xrefs

- `0x18002205c`: `_tsrpcResetSession - Failed to open binding`
- `0x1800220ce`: `_tsrpcResetSession - Failed to open RCM binding`
- `0x1800221ae`: `Session.Open failed: 0x%x in %s`

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
                                           (MIDL_STUBLESS_PROXY_INFO *)&stru_1800352C0,
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
0x180021fa4  mov     r11, rsp
0x180021fa7  mov     [r11+18h], rbx
0x180021fab  mov     [r11+20h], rsi
0x180021faf  push    rdi
0x180021fb0  sub     rsp, 1F0h
0x180021fb7  mov     rax, cs:__security_cookie
0x180021fbe  xor     rax, rsp
0x180021fc1  mov     [rsp+1F8h+var_18], rax
0x180021fc9  mov     sil, r8b
0x180021fcc  mov     edi, edx
0x180021fce  mov     rbx, rcx
0x180021fd1  mov     [rsp+1F8h+var_188], 0
0x180021fda  mov     [rsp+1F8h+var_180], 0FFFFFFFFh
0x180021fe2  mov     qword ptr [r11-70h], 0
0x180021fea  xorps   xmm0, xmm0
0x180021fed  xor     eax, eax
0x180021fef  movups  [rsp+1F8h+var_178], xmm0
0x180021ff7  movups  [rsp+1F8h+var_168], xmm0
0x180021fff  movups  [rsp+1F8h+var_158], xmm0
0x180022007  mov     [r11-148h], rax
0x18002200e  xor     edx, edx; Val
0x180022010  mov     r8d, 0D0h; Size
0x180022016  lea     rcx, [r11-140h]; void *
0x18002201d  call    memset_0
0x180022022  xor     r8d, r8d; int
0x180022025  mov     rdx, rbx; void *
0x180022028  lea     rcx, [rsp+1F8h+var_1A0]; this
0x18002202d  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180022032  lea     rcx, [rsp+1F8h+var_1A0]; unsigned __int16 *
0x180022037  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002203c  test    rax, rax
0x18002203f  jnz     short loc_180022072
0x180022041  call    cs:__imp_GetLastError
0x180022048  nop     dword ptr [rax+rax+00h]
0x18002204d  mov     ebx, eax
0x18002204f  test    eax, eax
0x180022051  jle     short loc_18002205C
0x180022053  movzx   ebx, ax
0x180022056  or      ebx, 80070000h
0x18002205c  lea     rdx, aTsrpcresetsess_3; "_tsrpcResetSession - Failed to open bin"...
0x180022063  mov     ecx, 8; int
0x180022068  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002206d  jmp     loc_18002225D
0x180022072  cmp     edi, 0FFFFFFFFh
0x180022075  jnz     short loc_180022092
0x180022077  lea     rdx, aTsrpcresetsess; "_tsrpcResetSession - SessionId is LOGON"...
0x18002207e  mov     ecx, 8; int
0x180022083  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022088  mov     ebx, 80004005h
0x18002208d  jmp     loc_18002225D
0x180022092  cmp     edi, 10000h
0x180022098  jb      loc_18002218F
0x18002209e  mov     r8d, 1; int
0x1800220a4  mov     rdx, rbx; void *
0x1800220a7  lea     rcx, [rsp+1F8h+var_1B0]; this
0x1800220ac  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800220b1  mov     [rsp+1F8h+var_1B8], 0
0x1800220ba  lea     rcx, [rsp+1F8h+var_1B0]; unsigned __int16 *
0x1800220bf  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800220c4  test    rax, rax
0x1800220c7  jnz     short loc_1800220F6
0x1800220c9  mov     ebx, 8007000Eh
0x1800220ce  lea     rdx, aTsrpcresetsess_0; "_tsrpcResetSession - Failed to open RCM"...
0x1800220d5  lea     ecx, [rax+8]; int
0x1800220d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800220dd  lea     rcx, [rsp+1F8h+var_1B8]; this
0x1800220e2  call    ??1CListener@@QEAA@XZ; CListener::~CListener(void)
0x1800220e7  lea     rcx, [rsp+1F8h+var_1B0]; this
0x1800220ec  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800220f1  jmp     loc_18002225D
0x1800220f6  lea     r8, [rsp+1F8h+var_68]; unsigned __int16 *
0x1800220fe  mov     edx, edi; unsigned int
0x180022100  mov     rcx, rbx; void *
0x180022103  call    ?_tsrpcSessionNameFromLogonId@@YAJPEAXKPEAG@Z; _tsrpcSessionNameFromLogonId(void *,ulong,ushort *)
0x180022108  mov     ebx, eax
0x18002210a  test    eax, eax
0x18002210c  jns     short loc_18002212B
0x18002210e  lea     rdx, aTsrpcsessionna_0; "_tsrpcSessionNameFromLogonId failed: 0x"...
0x180022115  mov     r8d, eax
0x180022118  lea     r9, aTsrpcresetsess_1; "_tsrpcResetSession"
0x18002211f  mov     ecx, 8; int
0x180022124  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022129  jmp     short loc_1800220DD
0x18002212b  lea     rcx, [rsp+1F8h+var_1B0]; unsigned __int16 *
0x180022130  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022135  mov     rdx, rax; void *
0x180022138  lea     r8, [rsp+1F8h+var_68]; unsigned __int16 *
0x180022140  lea     rcx, [rsp+1F8h+var_1B8]; this
0x180022145  call    ?Open@CListener@@QEAAJPEAXPEAG@Z; CListener::Open(void *,ushort *)
0x18002214a  mov     ebx, eax
0x18002214c  test    eax, eax
0x18002214e  jns     short loc_180022159
0x180022150  lea     rdx, aListenerInitia; "Listener.Initialize failed: 0x%x in %s"
0x180022157  jmp     short loc_180022115
0x180022159  lea     rcx, [rsp+1F8h+var_1B8]; this
0x18002215e  call    ?Stop@CListener@@QEAAJXZ; CListener::Stop(void)
0x180022163  mov     ebx, eax
0x180022165  test    eax, eax
0x180022167  jns     short loc_180022172
0x180022169  lea     rdx, aListenerStopFa; "Listener.Stop failed: 0x%x in %s"
0x180022170  jmp     short loc_180022115
0x180022172  lea     rcx, [rsp+1F8h+var_1B8]; this
0x180022177  call    ?Start@CListener@@QEAAJXZ; CListener::Start(void)
0x18002217c  mov     ebx, eax
0x18002217e  test    eax, eax
0x180022180  jns     loc_1800220DD
0x180022186  lea     rdx, aListenerStartF; "Listener.Start failed: 0x%x in %s"
0x18002218d  jmp     short loc_180022115
0x18002218f  lea     rcx, [rsp+1F8h+var_1A0]; unsigned __int16 *
0x180022194  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180022199  mov     r8, rax; void *
0x18002219c  mov     edx, edi; unsigned int
0x18002219e  lea     rcx, [rsp+1F8h+var_188]; this
0x1800221a3  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x1800221a8  mov     ebx, eax
0x1800221aa  test    eax, eax
0x1800221ac  jns     short loc_1800221CE
0x1800221ae  lea     rdx, aSessionOpenFai; "Session.Open failed: 0x%x in %s"
0x1800221b5  mov     r8d, eax
0x1800221b8  lea     r9, aTsrpcresetsess_1; "_tsrpcResetSession"
0x1800221bf  mov     ecx, 8; int
0x1800221c4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800221c9  jmp     loc_18002225D
0x1800221ce  lea     rcx, [rsp+1F8h+var_188]; this
0x1800221d3  call    ?Logoff@CSmartSession@@QEAAJXZ; CSmartSession::Logoff(void)
0x1800221d8  mov     ebx, eax
0x1800221da  mov     dword ptr [rsp+1F8h+var_1B8], eax
0x1800221de  test    eax, eax
0x1800221e0  jns     short loc_1800221EB
0x1800221e2  lea     rdx, aSessionLogoffF; "Session::Logoff failed: 0x%x in %s"
0x1800221e9  jmp     short loc_1800221B5
0x1800221eb  test    sil, sil
0x1800221ee  jz      short loc_18002225D
0x1800221f0  lea     rcx, [rsp+1F8h+var_1A0]; unsigned __int16 *
0x1800221f5  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800221fa  mov     qword ptr [rsp+1F8h+var_1B0], 0
0x180022203  mov     [rsp+1F8h+var_1C8], 1D4C0h
0x18002220b  mov     [rsp+1F8h+var_1D0], 8
0x180022213  mov     [rsp+1F8h+var_1D8], edi
0x180022217  mov     r9, rax
0x18002221a  xor     r8d, r8d; pReturnValue
0x18002221d  xor     edx, edx; nProcNum
0x18002221f  lea     rcx, stru_1800352C0; pProxyInfo
0x180022226  call    cs:__imp_NdrClientCall3
0x18002222d  nop     dword ptr [rax+rax+00h]
0x180022232  mov     qword ptr [rsp+1F8h+var_1B0], rax
0x180022237  jmp     short loc_18002225D
0x180022239  test    eax, eax
0x18002223b  jle     short loc_180022245
0x18002223d  movzx   eax, ax
0x180022240  or      eax, 80070000h
0x180022245  mov     r8d, eax
0x180022248  lea     rdx, aRpcwaitforsess; "RpcWaitForSessionState( State_Down ) fa"...
0x18002224f  mov     ecx, 8; int
0x180022254  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022259  mov     ebx, dword ptr [rsp+1F8h+var_1B8]
0x18002225d  lea     rcx, [rsp+1F8h+var_1A0]; this
0x180022262  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180022267  lea     rcx, [rsp+1F8h+var_188]; this
0x18002226c  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x180022271  mov     eax, ebx
0x180022273  mov     rcx, [rsp+1F8h+var_18]
0x18002227b  xor     rcx, rsp; StackCookie
0x18002227e  call    __security_check_cookie
0x180022283  lea     r11, [rsp+1F8h+var_8]
0x18002228b  mov     rbx, [r11+20h]
0x18002228f  mov     rsi, [r11+28h]
0x180022293  mov     rsp, r11
0x180022296  pop     rdi
0x180022297  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
