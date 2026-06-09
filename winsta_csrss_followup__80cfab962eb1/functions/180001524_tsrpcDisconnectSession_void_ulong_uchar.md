# _tsrpcDisconnectSession(void *,ulong,uchar)

- ea: `0x180001524`
- end: `0x18000168d`
- name: `?_tsrpcDisconnectSession@@YAJPEAXKE@Z`
- size: `361`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180001460`

## callees

- `0x1800013a0`
- `0x180001524`
- `0x180002014`
- `0x1800041a0`
- `0x180005280`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800015b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800015b1`

## string_xrefs

- `0x1800015cc`: `_tsrpcDisconnectSession: Failed to open binding`
- `0x180001684`: `Session.Open failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall _tsrpcDisconnectSession(void *a1, int a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  void *v7; // rax
  int v8; // eax
  int v9; // eax
  unsigned __int16 v10[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+38h] [rbp-C8h]
  __int128 v13; // [rsp+40h] [rbp-C0h]
  __int128 v14; // [rsp+50h] [rbp-B0h]
  __int128 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+70h] [rbp-90h]
  _BYTE v17[208]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+148h] [rbp+48h]

  v11 = 0;
  v12 = -1;
  v18 = 0;
  v16 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  memset_0(v17, 0, sizeof(v17));
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v10, a1, 0);
  if ( CSmartPublicBinding::operator void *(v10) )
  {
    if ( a2 == -1 )
    {
      _DbgPrintMessage(8, "_tsrpcDisconnectSession - SessionId is LOGONID_CURRENT - UNEXPECTED!!");
      v5 = -2147467259;
    }
    else
    {
      v7 = (void *)CSmartPublicBinding::operator void *(v10);
      v8 = CSmartSession::Open((CSmartSession *)&v11, a2, v7);
      v5 = v8;
      if ( v8 < 0 )
      {
        _DbgPrintMessage(8, "Session.Open failed: 0x%x in %s", (unsigned int)v8, "_tsrpcDisconnectSession");
      }
      else
      {
        v9 = CSmartSession::Disconnect((CSmartSession *)&v11);
        v5 = v9;
        if ( v9 < 0 )
          _DbgPrintMessage(8, "Session::Disconnect failed: 0x%x in %s", (unsigned int)v9, "_tsrpcDisconnectSession");
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    _DbgPrintMessage(8, "_tsrpcDisconnectSession: Failed to open binding");
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v10);
  CSmartSession::~CSmartSession((CSmartSession *)&v11);
  return v5;
}

```

## disassembly

```asm
0x180001524  mov     [rsp-8+arg_0], rbx
0x180001529  mov     [rsp-8+arg_10], rdi
0x18000152e  push    rbp
0x18000152f  lea     rbp, [rsp-60h]
0x180001534  sub     rsp, 160h
0x18000153b  mov     rax, cs:__security_cookie
0x180001542  xor     rax, rsp
0x180001545  mov     [rbp+60h+var_10], rax
0x180001549  xorps   xmm0, xmm0
0x18000154c  mov     [rsp+160h+var_130], 0
0x180001555  mov     edi, edx
0x180001557  mov     [rsp+160h+var_128], 0FFFFFFFFh
0x18000155f  mov     rbx, rcx
0x180001562  mov     [rbp+60h+var_18], 0
0x18000156a  xor     eax, eax
0x18000156c  lea     rcx, [rsp+160h+var_E8]; void *
0x180001571  xor     edx, edx; Val
0x180001573  mov     [rsp+160h+var_F0], rax
0x180001578  mov     r8d, 0D0h; Size
0x18000157e  movups  [rsp+160h+var_120], xmm0
0x180001583  movups  [rsp+160h+var_110], xmm0
0x180001588  movups  [rsp+160h+var_100], xmm0
0x18000158d  call    memset_0
0x180001592  xor     r8d, r8d; int
0x180001595  lea     rcx, [rsp+160h+var_140]; this
0x18000159a  mov     rdx, rbx; void *
0x18000159d  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800015a2  lea     rcx, [rsp+160h+var_140]; unsigned __int16 *
0x1800015a7  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800015ac  test    rax, rax
0x1800015af  jnz     short loc_180001615
0x1800015b1  call    cs:__imp_GetLastError
0x1800015b8  nop     dword ptr [rax+rax+00h]
0x1800015bd  mov     ebx, eax
0x1800015bf  test    eax, eax
0x1800015c1  jle     short loc_1800015CC
0x1800015c3  movzx   ebx, ax
0x1800015c6  or      ebx, 80070000h
0x1800015cc  lea     rdx, aTsrpcdisconnec_2; "_tsrpcDisconnectSession: Failed to open"...
0x1800015d3  mov     ecx, 8; int
0x1800015d8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800015dd  lea     rcx, [rsp+160h+var_140]; this
0x1800015e2  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800015e7  lea     rcx, [rsp+160h+var_130]; this
0x1800015ec  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x1800015f1  mov     eax, ebx
0x1800015f3  mov     rcx, [rbp+60h+var_10]
0x1800015f7  xor     rcx, rsp; StackCookie
0x1800015fa  call    __security_check_cookie
0x1800015ff  lea     r11, [rsp+160h+var_s0]
0x180001607  mov     rbx, [r11+10h]
0x18000160b  mov     rdi, [r11+20h]
0x18000160f  mov     rsp, r11
0x180001612  pop     rbp
0x180001613  retn
0x180001615  cmp     edi, 0FFFFFFFFh
0x180001618  jz      short loc_180001669
0x18000161a  lea     rcx, [rsp+160h+var_140]; unsigned __int16 *
0x18000161f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180001624  mov     r8, rax; void *
0x180001627  lea     rcx, [rsp+160h+var_130]; this
0x18000162c  mov     edx, edi; unsigned int
0x18000162e  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x180001633  mov     ebx, eax
0x180001635  test    eax, eax
0x180001637  js      short loc_180001684
0x180001639  lea     rcx, [rsp+160h+var_130]; this
0x18000163e  call    ?Disconnect@CSmartSession@@QEAAJXZ; CSmartSession::Disconnect(void)
0x180001643  mov     ebx, eax
0x180001645  test    eax, eax
0x180001647  jns     short loc_1800015DD
0x180001649  lea     rdx, aSessionDisconn; "Session::Disconnect failed: 0x%x in %s"
0x180001650  lea     r9, aTsrpcdisconnec; "_tsrpcDisconnectSession"
0x180001657  mov     r8d, eax
0x18000165a  mov     ecx, 8; int
0x18000165f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180001664  jmp     loc_1800015DD
0x180001669  lea     rdx, aTsrpcdisconnec_1; "_tsrpcDisconnectSession - SessionId is "...
0x180001670  mov     ecx, 8; int
0x180001675  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000167a  mov     ebx, 80004005h
0x18000167f  jmp     loc_1800015DD
0x180001684  lea     rdx, aSessionOpenFai; "Session.Open failed: 0x%x in %s"
0x18000168b  jmp     short loc_180001650
```
