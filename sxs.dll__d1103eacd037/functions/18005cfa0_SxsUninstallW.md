# SxsUninstallW

- ea: `0x18005cfa0`
- end: `0x18005d2a9`
- name: `SxsUninstallW`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800614a0`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18002e98c`
- `0x18002fffc`
- `0x18005c978`
- `0x18005cfa0`
- `0x18005d2b0`
- `0x18005fb10`
- `0x180063114`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d247`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d0e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d150`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d18f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d234`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d26b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d0e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d150`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d18f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d234`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d26b`

## pseudocode

```c
__int64 __fastcall SxsUninstallW(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rcx
  struct ISxsStore *v5; // rdi
  unsigned __int64 v6; // rdx
  __int64 *v7; // rsi
  _WORD *v8; // rax
  __int64 v9; // rax
  _OWORD *v10; // rsi
  int RemoteStore; // eax
  int v12; // edi
  int v13; // eax
  int v14; // ebx
  int v15; // eax
  DWORD LastError; // ebx
  unsigned int v17; // ebx
  int v19; // [rsp+30h] [rbp-49h] BYREF
  struct ISxsStore *v20; // [rsp+38h] [rbp-41h] BYREF
  _OWORD v21[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v22; // [rsp+60h] [rbp-19h]
  int v23; // [rsp+68h] [rbp-11h] BYREF
  int v24; // [rsp+6Ch] [rbp-Dh] BYREF
  int v25; // [rsp+70h] [rbp-9h] BYREF
  __int64 v26; // [rsp+78h] [rbp-1h]
  __int64 *v27; // [rsp+80h] [rbp+7h]
  __int64 v28; // [rsp+88h] [rbp+Fh]
  int v29; // [rsp+90h] [rbp+17h]
  int *v30; // [rsp+98h] [rbp+1Fh]

  v25 = 1;
  v27 = &qword_180076C60;
  v28 = 544438355;
  v30 = &v23;
  v23 = 0;
  v26 = 0;
  v29 = 51;
  CFrame::BaseEnter((CFrame *)&v25);
  v20 = 0;
  v22 = 0;
  v19 = 1;
  v5 = 0;
  v24 = 0;
  memset(v21, 0, sizeof(v21));
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    v29 = 66;
LABEL_37:
    FusionpTraceParameterCheck((const char *)v4);
    SetLastError(0x57u);
    *v30 = 0;
    goto LABEL_38;
  }
  v6 = a1 + *(_QWORD *)a1;
  if ( a1 + 12 > v6 || (v7 = (__int64 *)(a1 + 24), a1 + 24 > v6) )
  {
    v29 = 68;
    goto LABEL_37;
  }
  v4 = *(unsigned int *)(a1 + 8);
  if ( (v4 & 0xFFFFFFFE) != 0 )
  {
    v29 = 74;
    goto LABEL_37;
  }
  v4 &= 1u;
  if ( (_DWORD)v4 && (a1 + 32 > v6 || !*v7) )
  {
    v29 = 82;
    goto LABEL_37;
  }
  v8 = *(_WORD **)(a1 + 16);
  if ( !v8 || !*v8 )
  {
    v29 = 87;
    goto LABEL_37;
  }
  if ( (_DWORD)v4 )
  {
    v4 = *v7;
    v9 = *(_QWORD *)(*v7 + 8) - SXS_INSTALL_REFERENCE_SCHEME_OSINSTALL;
    if ( !v9 )
      v9 = *(_QWORD *)(v4 + 16) + 0x6A4EB8377FFFD278LL;
    if ( !v9 )
    {
      v29 = 95;
      goto LABEL_37;
    }
  }
  SetLastError(0);
  if ( !(unsigned int)SxspDoesMSIStillNeedAssembly(*(const unsigned __int16 **)(a1 + 16), &v19) )
  {
    *v30 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076C40);
    goto LABEL_38;
  }
  if ( v19 )
    goto LABEL_34;
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
  {
    v10 = (_OWORD *)*v7;
  }
  else
  {
    *(_QWORD *)&v21[0] = 40;
    v10 = v21;
    v22 = 0;
    *(_OWORD *)((char *)v21 + 8) = SXS_INSTALL_REFERENCE_SCHEME_SXS_INSTALL_ASSEMBLY;
    *((_QWORD *)&v21[1] + 1) = 0;
  }
  SetLastError(0);
  RemoteStore = SxspGetRemoteStore(&v20);
  v12 = RemoteStore;
  if ( RemoteStore < 0 )
  {
    FusionpTraceCOMFailure(RemoteStore, byte_18008517D);
    CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v25, v12);
    v5 = v20;
    goto LABEL_38;
  }
  SetLastError(0);
  v5 = v20;
  v13 = (*(__int64 (__fastcall **)(struct ISxsStore *, _QWORD, _QWORD, _OWORD *, int *))(*(_QWORD *)v20 + 48LL))(
          v20,
          0,
          *(_QWORD *)(a1 + 16),
          v10,
          &v24);
  v14 = v13;
  if ( v13 < 0 )
  {
    FusionpTraceCOMFailure(v13, byte_18008517D);
    CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v25, v14);
    goto LABEL_38;
  }
  v15 = v24;
  if ( a2 )
    *a2 = v24;
  if ( v15 != 2 )
  {
LABEL_34:
    v23 = 1;
  }
  else
  {
    CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v25, -2147021886);
    FusionpTraceCOMFailureOrigination((const struct _CALL_SITE_INFO *)off_180076C20, 0x80070BC2);
  }
LABEL_38:
  LastError = GetLastError();
  if ( v5 )
    (*(void (__fastcall **)(struct ISxsStore *))(*(_QWORD *)v5 + 16LL))(v5);
  SetLastError(LastError);
  v17 = v23;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v25);
  return v17;
}

```

## disassembly

```asm
0x18005cfa0  mov     [rsp-8+arg_10], rbx
0x18005cfa5  push    rbp
0x18005cfa6  push    rsi
0x18005cfa7  push    rdi
0x18005cfa8  push    r14
0x18005cfaa  push    r15
0x18005cfac  lea     rbp, [rsp-37h]
0x18005cfb1  sub     rsp, 0B0h
0x18005cfb8  mov     rax, cs:__security_cookie
0x18005cfbf  xor     rax, rsp
0x18005cfc2  mov     [rbp+57h+var_30], rax
0x18005cfc6  lea     rax, qword_180076C60
0x18005cfcd  mov     [rbp+57h+var_60], 1
0x18005cfd4  mov     [rbp+57h+var_50], rax
0x18005cfd8  mov     rbx, rcx
0x18005cfdb  lea     rax, [rbp+57h+var_68]
0x18005cfdf  mov     [rbp+57h+var_48], 20737853h
0x18005cfe7  xor     r15d, r15d
0x18005cfea  mov     [rbp+57h+var_38], rax
0x18005cfee  lea     rcx, [rbp+57h+var_60]; this
0x18005cff2  mov     [rbp+57h+var_68], r15d
0x18005cff6  mov     r14, rdx
0x18005cff9  mov     [rbp+57h+var_58], r15
0x18005cffd  mov     [rbp+57h+var_40], 33h ; '3'
0x18005d004  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005d009  xor     eax, eax
0x18005d00b  mov     [rbp+57h+var_98], r15
0x18005d00f  mov     [rbp+57h+var_70], rax
0x18005d013  xorps   xmm0, xmm0
0x18005d016  mov     [rbp+57h+var_A0], 1
0x18005d01d  mov     edi, r15d
0x18005d020  mov     [rbp+57h+var_64], r15d
0x18005d024  movups  [rbp+57h+var_90], xmm0
0x18005d028  movups  [rbp+57h+var_80], xmm0
0x18005d02c  test    r14, r14
0x18005d02f  jz      short loc_18005D034
0x18005d031  mov     [r14], r15d
0x18005d034  test    rbx, rbx
0x18005d037  jnz     short loc_18005D045
0x18005d039  mov     [rbp+57h+var_40], 42h ; 'B'
0x18005d040  jmp     loc_18005D22A
0x18005d045  mov     rdx, [rbx]
0x18005d048  lea     rax, [rbx+0Ch]
0x18005d04c  add     rdx, rbx
0x18005d04f  cmp     rax, rdx
0x18005d052  ja      loc_18005D223
0x18005d058  lea     rsi, [rbx+18h]
0x18005d05c  cmp     rsi, rdx
0x18005d05f  ja      loc_18005D223
0x18005d065  mov     ecx, [rbx+8]
0x18005d068  test    ecx, 0FFFFFFFEh
0x18005d06e  jz      short loc_18005D07C
0x18005d070  mov     [rbp+57h+var_40], 4Ah ; 'J'
0x18005d077  jmp     loc_18005D22A
0x18005d07c  and     ecx, 1
0x18005d07f  jz      short loc_18005D09B
0x18005d081  lea     rax, [rbx+20h]
0x18005d085  cmp     rax, rdx
0x18005d088  ja      short loc_18005D08F
0x18005d08a  cmp     [rsi], r15
0x18005d08d  jnz     short loc_18005D09B
0x18005d08f  mov     [rbp+57h+var_40], 52h ; 'R'
0x18005d096  jmp     loc_18005D22A
0x18005d09b  mov     rax, [rbx+10h]
0x18005d09f  test    rax, rax
0x18005d0a2  jz      loc_18005D21A
0x18005d0a8  cmp     [rax], r15w
0x18005d0ac  jz      loc_18005D21A
0x18005d0b2  test    ecx, ecx
0x18005d0b4  jz      short loc_18005D0E2
0x18005d0b6  mov     rcx, [rsi]
0x18005d0b9  mov     rax, [rcx+8]
0x18005d0bd  sub     rax, cs:SXS_INSTALL_REFERENCE_SCHEME_OSINSTALL
0x18005d0c4  jnz     short loc_18005D0D1
0x18005d0c6  mov     rax, [rcx+10h]
0x18005d0ca  sub     rax, cs:qword_180089180
0x18005d0d1  test    rax, rax
0x18005d0d4  jnz     short loc_18005D0E2
0x18005d0d6  mov     [rbp+57h+var_40], 5Fh ; '_'
0x18005d0dd  jmp     loc_18005D22A
0x18005d0e2  xor     ecx, ecx; dwErrCode
0x18005d0e4  call    cs:__imp_SetLastError
0x18005d0eb  nop     dword ptr [rax+rax+00h]
0x18005d0f0  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18005d0f4  lea     rdx, [rbp+57h+var_A0]; int *
0x18005d0f8  call    ?SxspDoesMSIStillNeedAssembly@@YAHPEBGAEAH@Z; SxspDoesMSIStillNeedAssembly(ushort const *,int &)
0x18005d0fd  test    eax, eax
0x18005d0ff  jnz     short loc_18005D119
0x18005d101  mov     rax, [rbp+57h+var_38]
0x18005d105  lea     rcx, off_180076C40; struct _CALL_SITE_INFO *
0x18005d10c  mov     [rax], r15d
0x18005d10f  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005d114  jmp     loc_18005D247
0x18005d119  cmp     [rbp+57h+var_A0], r15d
0x18005d11d  jnz     loc_18005D211
0x18005d123  test    byte ptr [rbx+8], 1
0x18005d127  jz      short loc_18005D12E
0x18005d129  mov     rsi, [rsi]
0x18005d12c  jmp     short loc_18005D14E
0x18005d12e  movups  xmm0, cs:SXS_INSTALL_REFERENCE_SCHEME_SXS_INSTALL_ASSEMBLY
0x18005d135  mov     qword ptr [rbp+57h+var_90], 28h ; '('
0x18005d13d  lea     rsi, [rbp+57h+var_90]
0x18005d141  mov     [rbp+57h+var_70], r15
0x18005d145  movdqu  [rbp+57h+var_90+8], xmm0
0x18005d14a  mov     qword ptr [rbp+57h+var_80+8], r15
0x18005d14e  xor     ecx, ecx; dwErrCode
0x18005d150  call    cs:__imp_SetLastError
0x18005d157  nop     dword ptr [rax+rax+00h]
0x18005d15c  lea     rcx, [rbp+57h+var_98]; struct ISxsStore **
0x18005d160  call    ?SxspGetRemoteStore@@YAJPEAPEAUISxsStore@@@Z; SxspGetRemoteStore(ISxsStore * *)
0x18005d165  mov     edi, eax
0x18005d167  test    eax, eax
0x18005d169  jns     short loc_18005D18D
0x18005d16b  lea     rdx, byte_18008517D; char *
0x18005d172  mov     ecx, eax; int
0x18005d174  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18005d179  mov     edx, edi; int
0x18005d17b  lea     rcx, [rbp+57h+var_60]; this
0x18005d17f  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005d184  mov     rdi, [rbp+57h+var_98]
0x18005d188  jmp     loc_18005D247
0x18005d18d  xor     ecx, ecx; dwErrCode
0x18005d18f  call    cs:__imp_SetLastError
0x18005d196  nop     dword ptr [rax+rax+00h]
0x18005d19b  mov     rdi, [rbp+57h+var_98]
0x18005d19f  lea     rcx, [rbp+57h+var_64]
0x18005d1a3  mov     r8, [rbx+10h]
0x18005d1a7  mov     r9, rsi
0x18005d1aa  mov     [rsp+0D0h+var_B0], rcx
0x18005d1af  xor     edx, edx
0x18005d1b1  mov     rcx, rdi
0x18005d1b4  mov     rax, [rdi]
0x18005d1b7  mov     rax, [rax+30h]
0x18005d1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1c0  mov     ebx, eax
0x18005d1c2  test    eax, eax
0x18005d1c4  jns     short loc_18005D1E1
0x18005d1c6  lea     rdx, byte_18008517D; char *
0x18005d1cd  mov     ecx, eax; int
0x18005d1cf  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18005d1d4  mov     edx, ebx; int
0x18005d1d6  lea     rcx, [rbp+57h+var_60]; this
0x18005d1da  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005d1df  jmp     short loc_18005D247
0x18005d1e1  mov     eax, [rbp+57h+var_64]
0x18005d1e4  test    r14, r14
0x18005d1e7  jz      short loc_18005D1EC
0x18005d1e9  mov     [r14], eax
0x18005d1ec  cmp     eax, 2
0x18005d1ef  jnz     short loc_18005D211
0x18005d1f1  mov     ebx, 80070BC2h
0x18005d1f6  lea     rcx, [rbp+57h+var_60]; this
0x18005d1fa  mov     edx, ebx; int
0x18005d1fc  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x18005d201  mov     edx, ebx; int
0x18005d203  lea     rcx, off_180076C20; struct _CALL_SITE_INFO *
0x18005d20a  call    ?FusionpTraceCOMFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@J@Z; FusionpTraceCOMFailureOrigination(_CALL_SITE_INFO const &,long)
0x18005d20f  jmp     short loc_18005D247
0x18005d211  mov     [rbp+57h+var_68], 1
0x18005d218  jmp     short loc_18005D247
0x18005d21a  mov     [rbp+57h+var_40], 57h ; 'W'
0x18005d221  jmp     short loc_18005D22A
0x18005d223  mov     [rbp+57h+var_40], 44h ; 'D'
0x18005d22a  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18005d22f  mov     ecx, 57h ; 'W'; dwErrCode
0x18005d234  call    cs:__imp_SetLastError
0x18005d23b  nop     dword ptr [rax+rax+00h]
0x18005d240  mov     rax, [rbp+57h+var_38]
0x18005d244  mov     [rax], r15d
0x18005d247  call    cs:__imp_GetLastError
0x18005d24e  nop     dword ptr [rax+rax+00h]
0x18005d253  mov     ebx, eax
0x18005d255  test    rdi, rdi
0x18005d258  jz      short loc_18005D269
0x18005d25a  mov     rdx, [rdi]
0x18005d25d  mov     rcx, rdi
0x18005d260  mov     rax, [rdx+10h]
0x18005d264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d269  mov     ecx, ebx; dwErrCode
0x18005d26b  call    cs:__imp_SetLastError
0x18005d272  nop     dword ptr [rax+rax+00h]
0x18005d277  mov     ebx, [rbp+57h+var_68]
0x18005d27a  lea     rcx, [rbp+57h+var_60]; this
0x18005d27e  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18005d283  mov     eax, ebx
0x18005d285  mov     rcx, [rbp+57h+var_30]
0x18005d289  xor     rcx, rsp; StackCookie
0x18005d28c  call    __security_check_cookie
0x18005d291  mov     rbx, [rsp+0D0h+arg_10]
0x18005d299  add     rsp, 0B0h
0x18005d2a0  pop     r15
0x18005d2a2  pop     r14
0x18005d2a4  pop     rdi
0x18005d2a5  pop     rsi
0x18005d2a6  pop     rbp
0x18005d2a7  retn
```
