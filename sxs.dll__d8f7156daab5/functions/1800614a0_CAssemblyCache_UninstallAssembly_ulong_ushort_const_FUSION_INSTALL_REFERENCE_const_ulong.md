# CAssemblyCache::UninstallAssembly(ulong,ushort const *,_FUSION_INSTALL_REFERENCE_ const *,ulong *)

- ea: `0x1800614a0`
- end: `0x180061637`
- name: `?UninstallAssembly@CAssemblyCache@@UEAAJKPEBGPEBU_FUSION_INSTALL_REFERENCE_@@PEAK@Z`
- size: `407`
- prototype: `int(CAssemblyCache *__hidden this, unsigned int, const unsigned __int16 *, const struct _FUSION_INSTALL_REFERENCE_ *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18002ff90`
- `0x18005cc58`
- `0x18005cfa0`
- `0x18005d2b0`
- `0x180061350`
- `0x1800614a0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800615a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800615a6`

## pseudocode

```c
__int64 __fastcall CAssemblyCache::UninstallAssembly(
        CAssemblyCache *this,
        int a2,
        const unsigned __int16 *a3,
        const struct _FUSION_INSTALL_REFERENCE_ *a4,
        unsigned int *a5)
{
  char **v8; // rcx
  unsigned int v9; // ebx
  unsigned int v11; // [rsp+20h] [rbp-61h] BYREF
  __int64 v12; // [rsp+28h] [rbp-59h] BYREF
  __int64 v13; // [rsp+30h] [rbp-51h]
  const unsigned __int16 *v14; // [rsp+38h] [rbp-49h]
  __int128 v15; // [rsp+40h] [rbp-41h]
  int v16; // [rsp+50h] [rbp-31h] BYREF
  int v17; // [rsp+58h] [rbp-29h] BYREF
  __int64 v18; // [rsp+60h] [rbp-21h]
  __int64 *v19; // [rsp+68h] [rbp-19h]
  __int64 v20; // [rsp+70h] [rbp-11h]
  int v21; // [rsp+78h] [rbp-9h]
  unsigned int *v22; // [rsp+80h] [rbp-1h]
  int v23; // [rsp+88h] [rbp+7h] BYREF
  __int128 v24; // [rsp+8Ch] [rbp+Bh]
  __int128 v25; // [rsp+9Ch] [rbp+1Bh]
  int v26; // [rsp+ACh] [rbp+2Bh]

  v19 = &qword_180076380;
  v16 = 0;
  v22 = (unsigned int *)&v16;
  v17 = 1;
  v18 = 0;
  v20 = 544438355;
  v21 = 154;
  CFrame::BaseEnter((CFrame *)&v17);
  v26 = 0;
  v23 = 40;
  v11 = 0;
  v24 = 0;
  v25 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a3 || a2 )
  {
    v21 = 163;
    FusionpTraceParameterCheck((const char *)0x28);
    *v22 = -2147024809;
    goto LABEL_16;
  }
  v13 = 0;
  v12 = 40;
  v14 = a3;
  v15 = 0;
  if ( a4 )
  {
    SetLastError(0);
    if ( !(unsigned int)SxspTranslateReferenceFrom(a4, (struct tagSXS_INSTALL_REFERENCEW *)&v23) )
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v17);
      v8 = off_180076360;
LABEL_8:
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
      goto LABEL_16;
    }
    LODWORD(v13) = 1;
    *(_QWORD *)&v15 = &v23;
  }
  SetLastError(0);
  if ( !(unsigned int)SxsUninstallW((__int64)&v12, &v11) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v17);
    v8 = off_180076340;
    goto LABEL_8;
  }
  if ( a5 )
    *a5 = v11;
  *v22 = 0;
LABEL_16:
  v9 = *v22;
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v17);
  return v9;
}

```

## disassembly

```asm
0x1800614a0  mov     [rsp-8+arg_0], rbx
0x1800614a5  mov     [rsp-8+arg_8], rsi
0x1800614aa  push    rbp
0x1800614ab  push    rdi
0x1800614ac  push    r14
0x1800614ae  lea     rbp, [rsp-3Fh]
0x1800614b3  sub     rsp, 0C0h
0x1800614ba  mov     rax, cs:__security_cookie
0x1800614c1  xor     rax, rsp
0x1800614c4  mov     [rbp+4Fh+var_20], rax
0x1800614c8  mov     rbx, [rbp+4Fh+arg_20]
0x1800614cc  lea     rax, qword_180076380
0x1800614d3  mov     [rbp+4Fh+var_68], rax
0x1800614d7  lea     rcx, [rbp+4Fh+var_78]; this
0x1800614db  lea     rax, [rbp+4Fh+var_80]
0x1800614df  mov     [rbp+4Fh+var_80], 0
0x1800614e6  mov     [rbp+4Fh+var_50], rax
0x1800614ea  mov     rsi, r9
0x1800614ed  mov     rdi, r8
0x1800614f0  mov     [rbp+4Fh+var_78], 1
0x1800614f7  mov     r14d, edx
0x1800614fa  mov     [rbp+4Fh+var_70], 0
0x180061502  mov     [rbp+4Fh+var_60], 20737853h
0x18006150a  mov     [rbp+4Fh+var_58], 9Ah
0x180061511  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180061516  xor     eax, eax
0x180061518  xorps   xmm0, xmm0
0x18006151b  mov     [rbp+4Fh+var_24], eax
0x18006151e  mov     ecx, 28h ; '('; char *
0x180061523  mov     [rbp+4Fh+var_48], ecx
0x180061526  mov     [rbp+4Fh+var_B0], eax
0x180061529  movups  [rbp+4Fh+var_44], xmm0
0x18006152d  movups  [rbp+4Fh+var_34], xmm0
0x180061531  test    rbx, rbx
0x180061534  jz      short loc_180061538
0x180061536  mov     [rbx], eax
0x180061538  test    rdi, rdi
0x18006153b  jz      loc_1800615EB
0x180061541  test    r14d, r14d
0x180061544  jnz     loc_1800615EB
0x18006154a  mov     [rbp+4Fh+var_A0], rax
0x18006154e  mov     [rbp+4Fh+var_A8], rcx
0x180061552  mov     [rbp+4Fh+var_98], rdi
0x180061556  movdqu  [rbp+4Fh+var_90], xmm0
0x18006155b  test    rsi, rsi
0x18006155e  jz      short loc_1800615A4
0x180061560  xor     ecx, ecx; dwErrCode
0x180061562  call    cs:__imp_SetLastError
0x180061569  nop     dword ptr [rax+rax+00h]
0x18006156e  lea     rdx, [rbp+4Fh+var_48]; struct tagSXS_INSTALL_REFERENCEW *
0x180061572  mov     rcx, rsi; struct _FUSION_INSTALL_REFERENCE_ *
0x180061575  call    ?SxspTranslateReferenceFrom@@YAHPEBU_FUSION_INSTALL_REFERENCE_@@AEAUtagSXS_INSTALL_REFERENCEW@@@Z; SxspTranslateReferenceFrom(_FUSION_INSTALL_REFERENCE_ const *,tagSXS_INSTALL_REFERENCEW &)
0x18006157a  test    eax, eax
0x18006157c  jnz     short loc_180061595
0x18006157e  lea     rcx, [rbp+4Fh+var_78]; this
0x180061582  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180061587  lea     rcx, off_180076360; struct _CALL_SITE_INFO *
0x18006158e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180061593  jmp     short loc_180061601
0x180061595  lea     rax, [rbp+4Fh+var_48]
0x180061599  mov     dword ptr [rbp+4Fh+var_A0], 1
0x1800615a0  mov     qword ptr [rbp+4Fh+var_90], rax
0x1800615a4  xor     ecx, ecx; dwErrCode
0x1800615a6  call    cs:__imp_SetLastError
0x1800615ad  nop     dword ptr [rax+rax+00h]
0x1800615b2  lea     rdx, [rbp+4Fh+var_B0]
0x1800615b6  lea     rcx, [rbp+4Fh+var_A8]
0x1800615ba  call    SxsUninstallW
0x1800615bf  test    eax, eax
0x1800615c1  jnz     short loc_1800615D5
0x1800615c3  lea     rcx, [rbp+4Fh+var_78]; this
0x1800615c7  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x1800615cc  lea     rcx, off_180076340; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x1800615d3  jmp     short loc_18006158E
0x1800615d5  test    rbx, rbx
0x1800615d8  jz      short loc_1800615DF
0x1800615da  mov     eax, [rbp+4Fh+var_B0]
0x1800615dd  mov     [rbx], eax
0x1800615df  mov     rax, [rbp+4Fh+var_50]
0x1800615e3  mov     dword ptr [rax], 0
0x1800615e9  jmp     short loc_180061601
0x1800615eb  mov     [rbp+4Fh+var_58], 0A3h
0x1800615f2  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800615f7  mov     rax, [rbp+4Fh+var_50]
0x1800615fb  mov     dword ptr [rax], 80070057h
0x180061601  mov     rax, [rbp+4Fh+var_50]
0x180061605  lea     rcx, [rbp+4Fh+var_78]; this
0x180061609  mov     ebx, [rax]
0x18006160b  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x180061610  mov     eax, ebx
0x180061612  mov     rcx, [rbp+4Fh+var_20]
0x180061616  xor     rcx, rsp; StackCookie
0x180061619  call    __security_check_cookie
0x18006161e  lea     r11, [rsp+0D0h+var_10]
0x180061626  mov     rbx, [r11+20h]
0x18006162a  mov     rsi, [r11+28h]
0x18006162e  mov     rsp, r11
0x180061631  pop     r14
0x180061633  pop     rdi
0x180061634  pop     rbp
0x180061635  retn
```
