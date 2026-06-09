# CAssemblyCache::InstallAssembly(ulong,ushort const *,_FUSION_INSTALL_REFERENCE_ const *)

- ea: `0x180061110`
- end: `0x18006128f`
- name: `?InstallAssembly@CAssemblyCache@@UEAAJKPEBGPEBU_FUSION_INSTALL_REFERENCE_@@@Z`
- size: `383`
- prototype: `int(CAssemblyCache *__hidden this, unsigned int, const unsigned __int16 *, const struct _FUSION_INSTALL_REFERENCE_ *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18002ff90`
- `0x18005cc58`
- `0x18005d2b0`
- `0x18005f1f0`
- `0x180061110`
- `0x180061350`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800611d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800611d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061211`

## pseudocode

```c
__int64 __fastcall CAssemblyCache::InstallAssembly(
        CAssemblyCache *this,
        int a2,
        const unsigned __int16 *a3,
        const struct _FUSION_INSTALL_REFERENCE_ *a4)
{
  const char *v7; // rcx
  char **v8; // rcx
  unsigned int v9; // ebx
  unsigned int v11; // [rsp+20h] [rbp-59h] BYREF
  __int128 v12; // [rsp+24h] [rbp-55h]
  __int128 v13; // [rsp+34h] [rbp-45h]
  _BYTE v14[20]; // [rsp+44h] [rbp-35h] BYREF
  int v15; // [rsp+58h] [rbp-21h] BYREF
  int v16; // [rsp+60h] [rbp-19h] BYREF
  __int64 v17; // [rsp+68h] [rbp-11h]
  __int64 *v18; // [rsp+70h] [rbp-9h]
  __int64 v19; // [rsp+78h] [rbp-1h]
  int v20; // [rsp+80h] [rbp+7h]
  unsigned int *v21; // [rsp+88h] [rbp+Fh]
  int v22; // [rsp+90h] [rbp+17h] BYREF
  __int128 v23; // [rsp+94h] [rbp+1Bh]
  __int128 v24; // [rsp+A4h] [rbp+2Bh]
  int v25; // [rsp+B4h] [rbp+3Bh]

  v15 = 0;
  v18 = &qword_1800762C0;
  v16 = 1;
  v21 = (unsigned int *)&v15;
  v17 = 0;
  v19 = 544438355;
  v20 = 232;
  CFrame::BaseEnter((CFrame *)&v16);
  v11 = 56;
  v22 = 40;
  v25 = 0;
  v12 = 0;
  v13 = 0;
  memset(v14, 0, sizeof(v14));
  v23 = 0;
  v24 = 0;
  if ( !a3 || a2 )
  {
    v20 = 237;
    FusionpTraceParameterCheck(v7);
    *v21 = -2147024809;
    goto LABEL_13;
  }
  *(_QWORD *)((char *)&v12 + 4) = a3;
  if ( a4 )
  {
    LODWORD(v12) = 0x200000;
    SetLastError(0);
    if ( !(unsigned int)SxspTranslateReferenceFrom(a4, (struct tagSXS_INSTALL_REFERENCEW *)&v22) )
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v16);
      v8 = off_1800762A0;
      goto LABEL_7;
    }
    *(_QWORD *)&v14[12] = &v22;
  }
  else
  {
    LODWORD(v12) = 0x20000;
  }
  SetLastError(0);
  if ( (unsigned int)SxsInstallW(&v11) )
  {
    *v21 = 0;
    goto LABEL_13;
  }
  CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v16);
  v8 = off_180076280;
LABEL_7:
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
LABEL_13:
  v9 = *v21;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v16);
  return v9;
}

```

## disassembly

```asm
0x180061110  mov     [rsp-8+arg_0], rbx
0x180061115  push    rbp
0x180061116  push    rsi
0x180061117  push    rdi
0x180061118  lea     rbp, [rsp-47h]
0x18006111d  sub     rsp, 0C0h
0x180061124  mov     rax, cs:__security_cookie
0x18006112b  xor     rax, rsp
0x18006112e  mov     [rbp+57h+var_18], rax
0x180061132  lea     rax, qword_1800762C0
0x180061139  mov     [rbp+57h+var_78], 0
0x180061140  mov     [rbp+57h+var_60], rax
0x180061144  lea     rcx, [rbp+57h+var_70]; this
0x180061148  lea     rax, [rbp+57h+var_78]
0x18006114c  mov     [rbp+57h+var_70], 1
0x180061153  mov     [rbp+57h+var_48], rax
0x180061157  mov     rbx, r9
0x18006115a  mov     rdi, r8
0x18006115d  mov     [rbp+57h+var_68], 0
0x180061165  mov     esi, edx
0x180061167  mov     [rbp+57h+var_58], 20737853h
0x18006116f  mov     [rbp+57h+var_50], 0E8h
0x180061176  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18006117b  xorps   xmm0, xmm0
0x18006117e  mov     [rbp+57h+var_B0], 38h ; '8'
0x180061185  xor     eax, eax
0x180061187  mov     [rbp+57h+var_40], 28h ; '('
0x18006118e  mov     [rbp+57h+var_7C], eax
0x180061191  mov     [rbp+57h+var_1C], eax
0x180061194  movups  [rbp+57h+var_AC], xmm0
0x180061198  movups  [rbp+57h+var_9C], xmm0
0x18006119c  movups  [rbp+57h+var_8C], xmm0
0x1800611a0  movups  [rbp+57h+var_3C], xmm0
0x1800611a4  movups  [rbp+57h+var_2C], xmm0
0x1800611a8  test    rdi, rdi
0x1800611ab  jz      loc_180061248
0x1800611b1  test    esi, esi
0x1800611b3  jnz     loc_180061248
0x1800611b9  mov     qword ptr [rbp+57h+var_AC+4], rdi
0x1800611bd  test    rbx, rbx
0x1800611c0  jnz     short loc_1800611CB
0x1800611c2  mov     dword ptr [rbp+57h+var_AC], 20000h
0x1800611c9  jmp     short loc_18006120F
0x1800611cb  xor     ecx, ecx; dwErrCode
0x1800611cd  mov     dword ptr [rbp+57h+var_AC], 200000h
0x1800611d4  call    cs:__imp_SetLastError
0x1800611db  nop     dword ptr [rax+rax+00h]
0x1800611e0  lea     rdx, [rbp+57h+var_40]; struct tagSXS_INSTALL_REFERENCEW *
0x1800611e4  mov     rcx, rbx; struct _FUSION_INSTALL_REFERENCE_ *
0x1800611e7  call    ?SxspTranslateReferenceFrom@@YAHPEBU_FUSION_INSTALL_REFERENCE_@@AEAUtagSXS_INSTALL_REFERENCEW@@@Z; SxspTranslateReferenceFrom(_FUSION_INSTALL_REFERENCE_ const *,tagSXS_INSTALL_REFERENCEW &)
0x1800611ec  test    eax, eax
0x1800611ee  jnz     short loc_180061207
0x1800611f0  lea     rcx, [rbp+57h+var_70]; this
0x1800611f4  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x1800611f9  lea     rcx, off_1800762A0; struct _CALL_SITE_INFO *
0x180061200  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180061205  jmp     short loc_18006125E
0x180061207  lea     rax, [rbp+57h+var_40]
0x18006120b  mov     qword ptr [rbp+57h+var_8C+0Ch], rax
0x18006120f  xor     ecx, ecx; dwErrCode
0x180061211  call    cs:__imp_SetLastError
0x180061218  nop     dword ptr [rax+rax+00h]
0x18006121d  lea     rcx, [rbp+57h+var_B0]
0x180061221  call    SxsInstallW
0x180061226  test    eax, eax
0x180061228  jnz     short loc_18006123C
0x18006122a  lea     rcx, [rbp+57h+var_70]; this
0x18006122e  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180061233  lea     rcx, off_180076280; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18006123a  jmp     short loc_180061200
0x18006123c  mov     rax, [rbp+57h+var_48]
0x180061240  mov     dword ptr [rax], 0
0x180061246  jmp     short loc_18006125E
0x180061248  mov     [rbp+57h+var_50], 0EDh
0x18006124f  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180061254  mov     rax, [rbp+57h+var_48]
0x180061258  mov     dword ptr [rax], 80070057h
0x18006125e  mov     rax, [rbp+57h+var_48]
0x180061262  lea     rcx, [rbp+57h+var_70]; this
0x180061266  mov     ebx, [rax]
0x180061268  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x18006126d  mov     eax, ebx
0x18006126f  mov     rcx, [rbp+57h+var_18]
0x180061273  xor     rcx, rsp; StackCookie
0x180061276  call    __security_check_cookie
0x18006127b  mov     rbx, [rsp+0D0h+arg_0]
0x180061283  add     rsp, 0C0h
0x18006128a  pop     rdi
0x18006128b  pop     rsi
0x18006128c  pop     rbp
0x18006128d  retn
```
