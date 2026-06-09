# HTTP_USER_REQUEST::_SafeDetachSysReq(void)

- ea: `0x1800250ec`
- end: `0x1800252a4`
- name: `?_SafeDetachSysReq@HTTP_USER_REQUEST@@AEAAXXZ`
- size: `440`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `20`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180024acc`
- `0x1800257a0`
- `0x18002e7ec`
- `0x18002f248`
- `0x18002fd0c`
- `0x180033c14`
- `0x180034dc0`
- `0x180035500`
- `0x1800359d0`
- `0x180035c4c`
- `0x180036058`
- `0x180036e40`
- `0x180037600`
- `0x180037f80`
- `0x180045840`
- `0x1800967f0`
- `0x180099a28`
- `0x180099c50`
- `0x1800b4fcc`
- `0x1800b560c`

## callees

- `0x1800250ec`
- `0x1800252ac`
- `0x18009478c`
- `0x1800a1d10`
- `0x1800b5080`
- `0x1800b81ac`
- `0x1800cf008`
- `0x1800db704`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025119`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025119`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025132`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025132`
- `webio!__imp_WebRemoveHttpRequestInformationRoutine` at `0x180025189`
- `webio!__imp_WebRemoveHttpRequestInformationRoutine` at `0x180025189`

## pseudocode

```c
void __fastcall HTTP_USER_REQUEST::_SafeDetachSysReq(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  WEBIO_REQUEST *SpinCount; // rbx
  bool v4; // zf
  __int128 v5; // [rsp+30h] [rbp-28h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h]

  v1 = this + 6;
  SpinCount = 0;
  EnterCriticalSection(this + 6);
  if ( this[4].SpinCount )
  {
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_qq(
        1025,
        10,
        (unsigned int)WPP_29ecff532d3a35783d73db4432e82274_Traceguids,
        (_DWORD)this,
        this[4].SpinCount);
    v4 = LODWORD(this[266].OwningThread) == 0;
    SpinCount = (WEBIO_REQUEST *)this[4].SpinCount;
    this[4].SpinCount = 0;
    if ( !v4 )
    {
      if ( (xmmword_180107A60 & 2) != 0 )
        WPP_SF_q(1025, 11, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
      WEBIO_REQUEST::UnmarkForPush(SpinCount);
    }
  }
  LeaveCriticalSection(v1);
  if ( SpinCount )
  {
    v5 = 0;
    v6 = 0;
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_qq(
        1025,
        240,
        (unsigned int)WPP_29ecff532d3a35783d73db4432e82274_Traceguids,
        (_DWORD)this,
        (__int64)SpinCount);
    if ( (Microsoft_Windows_WinHttp_DiagnosticsEnableBits & 1) != 0
      && !WEBIO_REQUEST::QueryRequestErrorLogData(SpinCount, (struct _WxHttpDiagErrorContext *)&v5)
      && (_DWORD)v5 )
    {
      HTTP_USER_REQUEST::LogErrorDiagnostics((HTTP_USER_REQUEST *)this, (struct _WxHttpDiagErrorContext *)&v5);
    }
    if ( (xmmword_180107A60 & 2) != 0 )
      WPP_SF_(1025, 241, WPP_29ecff532d3a35783d73db4432e82274_Traceguids);
    WEBIO_REQUEST::CancelRequest(SpinCount, 0x2EF1u);
    WebRemoveHttpRequestInformationRoutine(*((_QWORD *)SpinCount + 23), 0);
    (*(void (__fastcall **)(WEBIO_REQUEST *))(*(_QWORD *)SpinCount + 8LL))(SpinCount);
  }
}

```

## disassembly

```asm
0x1800250ec  mov     [rsp+arg_8], rbx
0x1800250f1  mov     [rsp+arg_10], rsi
0x1800250f6  push    rdi
0x1800250f7  sub     rsp, 50h
0x1800250fb  mov     rax, cs:__security_cookie
0x180025102  xor     rax, rsp
0x180025105  mov     [rsp+58h+var_10], rax
0x18002510a  lea     rsi, [rcx+0F0h]
0x180025111  mov     rdi, rcx
0x180025114  mov     rcx, rsi; lpCriticalSection
0x180025117  xor     ebx, ebx
0x180025119  call    cs:__imp_EnterCriticalSection
0x18002511f  mov     rax, [rdi+0C0h]
0x180025126  test    rax, rax
0x180025129  jnz     loc_1800251BB
0x18002512f  mov     rcx, rsi; lpCriticalSection
0x180025132  call    cs:__imp_LeaveCriticalSection
0x180025138  test    rbx, rbx
0x18002513b  jz      short loc_18002519E
0x18002513d  xorps   xmm0, xmm0
0x180025140  xor     eax, eax
0x180025142  movups  [rsp+58h+var_28], xmm0
0x180025147  mov     [rsp+58h+var_18], rax
0x18002514c  test    byte ptr cs:xmmword_180107A60, 2
0x180025153  jnz     loc_180025212
0x180025159  test    cs:Microsoft_Windows_WinHttp_DiagnosticsEnableBits, 1
0x180025160  jnz     loc_180025258
0x180025166  test    byte ptr cs:xmmword_180107A60, 2
0x18002516d  jnz     loc_180025289
0x180025173  mov     edx, 2EF1h; unsigned int
0x180025178  mov     rcx, rbx; this
0x18002517b  call    ?CancelRequest@WEBIO_REQUEST@@QEAAXK@Z; WEBIO_REQUEST::CancelRequest(ulong)
0x180025180  mov     rcx, [rbx+0B8h]
0x180025187  xor     edx, edx
0x180025189  call    cs:__imp_WebRemoveHttpRequestInformationRoutine
0x18002518f  mov     rax, [rbx]
0x180025192  mov     rcx, rbx
0x180025195  mov     rax, [rax+8]
0x180025199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002519e  mov     rcx, [rsp+58h+var_10]
0x1800251a3  xor     rcx, rsp; StackCookie
0x1800251a6  call    __security_check_cookie
0x1800251ab  mov     rbx, [rsp+58h+arg_8]
0x1800251b0  mov     rsi, [rsp+58h+arg_10]
0x1800251b5  add     rsp, 50h
0x1800251b9  pop     rdi
0x1800251ba  retn
0x1800251bb  test    byte ptr cs:xmmword_180107A60, 2
0x1800251c2  jnz     short loc_180025235
0x1800251c4  cmp     dword ptr [rdi+29A0h], 0
0x1800251cb  mov     rbx, [rdi+0C0h]
0x1800251d2  mov     qword ptr [rdi+0C0h], 0
0x1800251dd  jz      loc_18002512F
0x1800251e3  test    byte ptr cs:xmmword_180107A60, 2
0x1800251ea  jz      short loc_180025205
0x1800251ec  mov     edx, 0Bh
0x1800251f1  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x1800251f8  mov     ecx, 401h
0x1800251fd  mov     r9, rdi
0x180025200  call    WPP_SF_q
0x180025205  mov     rcx, rbx; this
0x180025208  call    ?UnmarkForPush@WEBIO_REQUEST@@QEAAXXZ; WEBIO_REQUEST::UnmarkForPush(void)
0x18002520d  jmp     loc_18002512F
0x180025212  mov     edx, 0F0h
0x180025217  mov     [rsp+58h+var_38], rbx
0x18002521c  mov     ecx, 401h
0x180025221  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180025228  mov     r9, rdi
0x18002522b  call    WPP_SF_qq
0x180025230  jmp     loc_180025159
0x180025235  mov     edx, 0Ah
0x18002523a  mov     [rsp+58h+var_38], rax
0x18002523f  mov     ecx, 401h
0x180025244  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x18002524b  mov     r9, rdi
0x18002524e  call    WPP_SF_qq
0x180025253  jmp     loc_1800251C4
0x180025258  lea     rdx, [rsp+58h+var_28]; struct _WxHttpDiagErrorContext *
0x18002525d  mov     rcx, rbx; this
0x180025260  call    ?QueryRequestErrorLogData@WEBIO_REQUEST@@QEAAKPEAU_WxHttpDiagErrorContext@@@Z; WEBIO_REQUEST::QueryRequestErrorLogData(_WxHttpDiagErrorContext *)
0x180025265  test    eax, eax
0x180025267  jnz     loc_180025166
0x18002526d  cmp     dword ptr [rsp+58h+var_28], eax
0x180025271  jz      loc_180025166
0x180025277  lea     rdx, [rsp+58h+var_28]; struct _WxHttpDiagErrorContext *
0x18002527c  mov     rcx, rdi; this
0x18002527f  call    ?LogErrorDiagnostics@HTTP_USER_REQUEST@@AEAAXPEAU_WxHttpDiagErrorContext@@@Z; HTTP_USER_REQUEST::LogErrorDiagnostics(_WxHttpDiagErrorContext *)
0x180025284  jmp     loc_180025166
0x180025289  mov     edx, 0F1h
0x18002528e  lea     r8, WPP_29ecff532d3a35783d73db4432e82274_Traceguids
0x180025295  mov     ecx, 401h
0x18002529a  call    WPP_SF_
0x18002529f  jmp     loc_180025173
```
