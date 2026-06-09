# _tsrpcDisconnectSession(void *,ulong,uchar)

- ea: `0x180011458`
- end: `0x1800115ba`
- name: `?_tsrpcDisconnectSession@@YAJPEAXKE@Z`
- size: `354`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800113a0`

## callees

- `0x1800039e8`
- `0x180005c30`
- `0x180007030`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x180011458`
- `0x1800115c0`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114e5`

## string_xrefs

- `0x1800114fa`: `_tsrpcDisconnectSession: Failed to open binding`
- `0x1800115b1`: `Session.Open failed: 0x%x in %s`

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
0x180011458  mov     [rsp-8+arg_0], rbx
0x18001145d  mov     [rsp-8+arg_10], rdi
0x180011462  push    rbp
0x180011463  lea     rbp, [rsp-60h]
0x180011468  sub     rsp, 160h
0x18001146f  mov     rax, cs:__security_cookie
0x180011476  xor     rax, rsp
0x180011479  mov     [rbp+60h+var_10], rax
0x18001147d  xorps   xmm0, xmm0
0x180011480  mov     [rsp+160h+var_130], 0
0x180011489  mov     edi, edx
0x18001148b  mov     [rsp+160h+var_128], 0FFFFFFFFh
0x180011493  mov     rbx, rcx
0x180011496  mov     [rbp+60h+var_18], 0
0x18001149e  xor     eax, eax
0x1800114a0  lea     rcx, [rsp+160h+var_E8]; void *
0x1800114a5  xor     edx, edx; Val
0x1800114a7  mov     [rsp+160h+var_F0], rax
0x1800114ac  mov     r8d, 0D0h; Size
0x1800114b2  movups  [rsp+160h+var_120], xmm0
0x1800114b7  movups  [rsp+160h+var_110], xmm0
0x1800114bc  movups  [rsp+160h+var_100], xmm0
0x1800114c1  call    memset_0
0x1800114c6  xor     r8d, r8d; int
0x1800114c9  lea     rcx, [rsp+160h+var_140]; this
0x1800114ce  mov     rdx, rbx; void *
0x1800114d1  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800114d6  lea     rcx, [rsp+160h+var_140]; unsigned __int16 *
0x1800114db  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800114e0  test    rax, rax
0x1800114e3  jnz     short loc_180011542
0x1800114e5  call    cs:__imp_GetLastError
0x1800114eb  mov     ebx, eax
0x1800114ed  test    eax, eax
0x1800114ef  jle     short loc_1800114FA
0x1800114f1  movzx   ebx, ax
0x1800114f4  or      ebx, 80070000h
0x1800114fa  lea     rdx, aTsrpcdisconnec_2; "_tsrpcDisconnectSession: Failed to open"...
0x180011501  mov     ecx, 8; int
0x180011506  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001150b  lea     rcx, [rsp+160h+var_140]; this
0x180011510  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180011515  lea     rcx, [rsp+160h+var_130]; this
0x18001151a  call    ??1CSmartSession@@QEAA@XZ; CSmartSession::~CSmartSession(void)
0x18001151f  mov     eax, ebx
0x180011521  mov     rcx, [rbp+60h+var_10]
0x180011525  xor     rcx, rsp; StackCookie
0x180011528  call    __security_check_cookie
0x18001152d  lea     r11, [rsp+160h+var_s0]
0x180011535  mov     rbx, [r11+10h]
0x180011539  mov     rdi, [r11+20h]
0x18001153d  mov     rsp, r11
0x180011540  pop     rbp
0x180011541  retn
0x180011542  cmp     edi, 0FFFFFFFFh
0x180011545  jz      short loc_180011596
0x180011547  lea     rcx, [rsp+160h+var_140]; unsigned __int16 *
0x18001154c  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180011551  mov     r8, rax; void *
0x180011554  lea     rcx, [rsp+160h+var_130]; this
0x180011559  mov     edx, edi; unsigned int
0x18001155b  call    ?Open@CSmartSession@@QEAAJKPEAX@Z; CSmartSession::Open(ulong,void *)
0x180011560  mov     ebx, eax
0x180011562  test    eax, eax
0x180011564  js      short loc_1800115B1
0x180011566  lea     rcx, [rsp+160h+var_130]; this
0x18001156b  call    ?Disconnect@CSmartSession@@QEAAJXZ; CSmartSession::Disconnect(void)
0x180011570  mov     ebx, eax
0x180011572  test    eax, eax
0x180011574  jns     short loc_18001150B
0x180011576  lea     rdx, aSessionDisconn; "Session::Disconnect failed: 0x%x in %s"
0x18001157d  lea     r9, aTsrpcdisconnec; "_tsrpcDisconnectSession"
0x180011584  mov     r8d, eax
0x180011587  mov     ecx, 8; int
0x18001158c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180011591  jmp     loc_18001150B
0x180011596  lea     rdx, aTsrpcdisconnec_1; "_tsrpcDisconnectSession - SessionId is "...
0x18001159d  mov     ecx, 8; int
0x1800115a2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800115a7  mov     ebx, 80004005h
0x1800115ac  jmp     loc_18001150B
0x1800115b1  lea     rdx, aSessionOpenFai; "Session.Open failed: 0x%x in %s"
0x1800115b8  jmp     short loc_18001157D
```
