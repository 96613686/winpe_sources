# SxsInstallW

- ea: `0x18005f1f0`
- end: `0x18005f891`
- name: `SxsInstallW`
- size: `1697`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005ea40`
- `0x180061110`
- `0x180063a20`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18001e5d0`
- `0x180020820`
- `0x18002e98c`
- `0x18005c978`
- `0x18005d2b0`
- `0x18005f1f0`
- `0x18005fd00`
- `0x180063114`
- `0x1800681cc`
- `0x180068380`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f79e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f3f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f4b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f685`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f6c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f720`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f788`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f823`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f3f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f4b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f685`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f6c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f720`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f788`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f823`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f4c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005f4c4`

## pseudocode

```c
__int64 __fastcall SxsInstallW(unsigned int *a1)
{
  unsigned int v2; // r15d
  struct ISxsStore *v3; // rsi
  unsigned int v4; // r14d
  const char *v5; // rcx
  _WORD *v6; // rax
  unsigned int v7; // edi
  int v8; // r13d
  _WORD *v9; // rax
  __int64 v10; // rdx
  char **v11; // rcx
  __int64 v12; // rcx
  struct ISxsStore *v13; // r13
  __int64 v14; // r12
  _OWORD *v15; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v17; // rcx
  int v18; // edx
  int v19; // ecx
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // r8d
  int v24; // ecx
  int v25; // edx
  unsigned int v26; // ecx
  __int64 v27; // rdx
  int v28; // ecx
  int v29; // eax
  _BYTE *v30; // rbx
  int RemoteStore; // eax
  int v32; // edi
  int v33; // eax
  int v34; // edi
  int v35; // edx
  int v36; // eax
  int v37; // ebx
  int v38; // ebx
  DWORD LastError; // r12d
  int v40; // edi
  __int64 v42; // [rsp+30h] [rbp-D0h]
  struct ISxsStore *v43; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h]
  _OWORD *v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+50h] [rbp-B0h]
  _BYTE v47[40]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v48[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h]
  int v50; // [rsp+A8h] [rbp-58h] BYREF
  int v51; // [rsp+ACh] [rbp-54h] BYREF
  int v52; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-48h]
  __int64 *v54; // [rsp+C0h] [rbp-40h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  int v56; // [rsp+D0h] [rbp-30h]
  int *v57; // [rsp+D8h] [rbp-28h]
  _BYTE v58[16]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-10h]
  _BYTE v60[16]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v61; // [rsp+1A0h] [rbp+A0h]
  _BYTE v62[176]; // [rsp+240h] [rbp+140h] BYREF

  v55 = 544438355;
  v50 = 0;
  v54 = &qword_180074850;
  v53 = 0;
  v2 = 1;
  v56 = 102;
  v52 = 1;
  v57 = &v50;
  CFrame::BaseEnter((CFrame *)&v52);
  v43 = 0;
  v51 = 0;
  memset(v47, 0, sizeof(v47));
  v3 = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v60);
  v4 = 0;
  memset(v48, 0, sizeof(v48));
  v49 = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v62);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v58);
  if ( !a1 || (v5 = (char *)a1 + *a1, a1 + 4 > (unsigned int *)v5) )
  {
    v56 = 117;
    goto LABEL_100;
  }
  v6 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( !v6 || !*v6 )
  {
    v56 = 119;
    goto LABEL_100;
  }
  v7 = a1[1];
  if ( (v7 & 0xFE0000FF) != 0 )
  {
    v56 = 139;
LABEL_100:
    FusionpTraceParameterCheck(v5);
    SetLastError(0x57u);
    *v57 = 0;
    goto LABEL_101;
  }
  if ( (v7 & 0x100) != 0 && a1 + 8 > (unsigned int *)v5 )
  {
    v56 = 143;
    goto LABEL_100;
  }
  v8 = v7 & 0x80000;
  if ( (v7 & 0x80000) != 0 && a1 + 6 > (unsigned int *)v5 )
  {
    v56 = 144;
    goto LABEL_100;
  }
  if ( (v7 & 0x100000) != 0 && a1 + 10 > (unsigned int *)v5 )
  {
    v56 = 145;
    goto LABEL_100;
  }
  if ( (v7 & 0x10000) != 0 && a1 + 12 > (unsigned int *)v5 )
  {
    v56 = 146;
    goto LABEL_100;
  }
  if ( (v7 & 0x200000) != 0 && a1 + 14 > (unsigned int *)v5 )
  {
    v56 = 147;
    goto LABEL_100;
  }
  if ( (v7 & 0x100) != 0 )
  {
    v9 = (_WORD *)*((_QWORD *)a1 + 3);
    if ( !v9 || !*v9 )
    {
      v56 = 155;
      goto LABEL_100;
    }
  }
  if ( v8 && !*((_QWORD *)a1 + 2) )
  {
    v56 = 178;
    goto LABEL_100;
  }
  if ( (v7 & 0x20000) != 0 && (v7 & 0x100) != 0 )
  {
    v56 = 183;
    goto LABEL_100;
  }
  SetLastError(0);
  if ( (unsigned int)SxspExpandRelativePathToFull(*((LPCWSTR *)a1 + 1), v10, (__int64)v60) )
  {
    v12 = v61;
    v46 = v61;
    if ( v8 )
      v13 = (struct ISxsStore *)*((_QWORD *)a1 + 2);
    else
      v13 = 0;
    if ( (v7 & 0x100) != 0 )
      v14 = *((_QWORD *)a1 + 3);
    else
      v14 = 0;
    if ( (v7 & 0x100000) != 0 )
      v42 = *((_QWORD *)a1 + 4);
    else
      v42 = 0;
    if ( (v7 & 0x10000) != 0 )
      v44 = *((_QWORD *)a1 + 5);
    else
      v44 = 0;
    if ( (v7 & 0x200000) != 0 )
    {
      v15 = (_OWORD *)*((_QWORD *)a1 + 6);
    }
    else
    {
      *(_QWORD *)&v48[0] = 40;
      v49 = 0;
      *(_OWORD *)((char *)v48 + 8) = SXS_INSTALL_REFERENCE_SCHEME_SXS_INSTALL_ASSEMBLY;
      *((_QWORD *)&v48[1] + 1) = 0;
      SetLastError(0);
      ModuleHandleW = GetModuleHandleW(0);
      if ( !(unsigned int)FusionpGetModuleFileName(v17, ModuleHandleW, v58) )
      {
        v11 = off_180074810;
        goto LABEL_34;
      }
      v7 |= 0x200000u;
      v12 = v46;
      v49 = v59;
      v15 = v48;
    }
    v45 = v15;
    if ( (v7 & 0x100) == 0 && (v7 & 0x20000) == 0 )
    {
      v14 = v12;
      v7 |= 0x100u;
    }
    *(_QWORD *)v47 = 40;
    v18 = (v7 >> 3) & 0x40 | 0x800;
    *(_OWORD *)&v47[8] = 0;
    if ( (v7 & 0x400) == 0 )
      v18 = (v7 >> 3) & 0x40;
    v19 = v18 | 2;
    *(_OWORD *)&v47[24] = 0;
    if ( (v7 & 0x4000) == 0 )
      v19 = v18;
    v20 = v19 | 1;
    if ( (v7 & 0x2000) == 0 )
      v20 = v19;
    v21 = v20 | 4;
    if ( (v7 & 0x8000) == 0 )
      v21 = v20;
    v22 = v21 | 0x10;
    if ( (v7 & 0x800) == 0 )
      v22 = v21;
    v23 = v22 | 0x20;
    if ( (v7 & 0x1000) == 0 )
      v23 = v22;
    v24 = v23 | 0x4000;
    if ( (v7 & 0x20000) == 0 )
      v24 = v23;
    v25 = v24 | 0x40000;
    if ( (v7 & 0x800000) == 0 )
      v25 = v24;
    v26 = v25 | 0x8000;
    if ( (v7 & 0x200000) == 0 )
      v26 = v25;
    v27 = v26 | 0x10000;
    if ( (v7 & 0x400000) == 0 )
      v27 = v26;
    v4 = v27 | 0x80000;
    if ( (v7 & 0x1000000) == 0 )
      v4 = v27;
    v28 = v7 & 0x100;
    if ( (v7 & 0x100) != 0 )
    {
      *(_QWORD *)&v47[16] = v14;
      *(_DWORD *)&v47[8] = 1;
    }
    v29 = v28 != 0;
    v30 = (_BYTE *)((unsigned __int64)v47 & -(__int64)(v28 != 0));
    if ( (v7 & 0x100000) != 0 )
    {
      v30 = v47;
      v29 |= 2u;
      *(_QWORD *)&v47[24] = v42;
      *(_DWORD *)&v47[8] = v29;
    }
    if ( (v7 & 0x10000) != 0 )
    {
      v30 = v47;
      v4 |= 0x2000u;
      *(_QWORD *)&v47[32] = v44;
      v29 |= 0x20u;
      *(_DWORD *)&v47[8] = v29;
    }
    if ( (v7 & 0x20000) != 0 )
    {
      v30 = v47;
      *(_DWORD *)&v47[8] = v29 | 0x40;
    }
    if ( (v7 & 0x80000) != 0 )
    {
      v3 = v13;
      (*(void (__fastcall **)(struct ISxsStore *, __int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, v27, 0x10000);
    }
    else
    {
      SetLastError(0);
      RemoteStore = SxspGetRemoteStore(&v43);
      v32 = RemoteStore;
      if ( RemoteStore < 0 )
      {
        FusionpTraceCOMFailure(RemoteStore, byte_18008517D);
        CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v52, v32);
        v3 = v43;
        goto LABEL_101;
      }
      SetLastError(0);
      v3 = v43;
      v33 = (*(__int64 (__fastcall **)(struct ISxsStore *, _QWORD))(*(_QWORD *)v43 + 24LL))(v43, v4);
      v34 = v33;
      if ( v33 < 0 )
      {
        FusionpTraceCOMFailure(v33, byte_18008517D);
        v35 = v34;
LABEL_91:
        CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v52, v35);
        goto LABEL_101;
      }
      v51 = 1;
    }
    if ( v30 )
      v4 |= 0x80u;
    SetLastError(0);
    v36 = (*(__int64 (__fastcall **)(struct ISxsStore *, _QWORD, __int64, _BYTE *, _OWORD *))(*(_QWORD *)v3 + 32LL))(
            v3,
            v4,
            v46,
            v30,
            v45);
    v37 = v36;
    if ( v36 >= 0 )
    {
      v50 = 1;
      goto LABEL_101;
    }
    FusionpTraceCOMFailure(v36, byte_18008517D);
    v35 = v37;
    goto LABEL_91;
  }
  v11 = off_180074830;
LABEL_34:
  *v57 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v11);
LABEL_101:
  v38 = 0;
  LastError = GetLastError();
  if ( v51 )
  {
    v51 = 0;
    v38 = (*(__int64 (__fastcall **)(struct ISxsStore *, _QWORD, int *))(*(_QWORD *)v3 + 40LL))(
            v3,
            v4 & 0x10000 | (v50 != 0 ? 4096 : 8),
            &v51);
    if ( v38 >= 0 && v51 == 2 )
      v38 = -2147021886;
  }
  if ( v3 )
    (*(void (__fastcall **)(struct ISxsStore *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v38 >= 0 )
  {
    v40 = 1;
    SetLastError(LastError);
  }
  else
  {
    v40 = 0;
    FusionpSetLastErrorFromHRESULT(v38);
  }
  if ( !v50 || !v40 )
    v2 = 0;
  v50 = v2;
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v58);
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v62);
  CGenericStringBuffer<64,CUnicodeCharTraits>::~CGenericStringBuffer<64,CUnicodeCharTraits>(v60);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v52);
  return v2;
}

```

## disassembly

```asm
0x18005f1f0  push    rbp
0x18005f1f2  push    rbx
0x18005f1f3  push    rsi
0x18005f1f4  push    rdi
0x18005f1f5  push    r12
0x18005f1f7  push    r13
0x18005f1f9  push    r14
0x18005f1fb  push    r15
0x18005f1fd  lea     rbp, [rsp-208h]
0x18005f205  sub     rsp, 308h
0x18005f20c  mov     rax, cs:__security_cookie
0x18005f213  xor     rax, rsp
0x18005f216  mov     [rbp+240h+var_50], rax
0x18005f21d  xor     r13d, r13d
0x18005f220  mov     [rbp+240h+var_278], 20737853h
0x18005f228  lea     rax, qword_180074850
0x18005f22f  mov     [rbp+240h+var_298], r13d
0x18005f233  mov     [rbp+240h+var_280], rax
0x18005f237  mov     rbx, rcx
0x18005f23a  lea     rax, [rbp+240h+var_298]
0x18005f23e  mov     [rbp+240h+var_288], r13
0x18005f242  lea     r15d, [r13+1]
0x18005f246  mov     [rbp+240h+var_270], 66h ; 'f'
0x18005f24d  lea     rcx, [rbp+240h+var_290]; this
0x18005f251  mov     [rbp+240h+var_290], r15d
0x18005f255  mov     [rbp+240h+var_268], rax
0x18005f259  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005f25e  xorps   xmm0, xmm0
0x18005f261  mov     [rsp+340h+var_308], r13
0x18005f266  xor     eax, eax
0x18005f268  mov     [rbp+240h+var_294], r13d
0x18005f26c  lea     rcx, [rbp+240h+var_1B0]
0x18005f273  mov     [rsp+340h+var_2C8], rax
0x18005f278  movups  [rsp+340h+var_2E8], xmm0
0x18005f27d  mov     esi, r13d
0x18005f280  movups  [rsp+340h+var_2D8], xmm0
0x18005f285  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005f28a  xorps   xmm0, xmm0
0x18005f28d  lea     rcx, [rbp+240h+var_100]
0x18005f294  xor     eax, eax
0x18005f296  mov     r14d, r13d
0x18005f299  movups  [rbp+240h+var_2C0], xmm0
0x18005f29d  mov     [rbp+240h+var_2A0], rax
0x18005f2a1  movups  [rbp+240h+var_2B0], xmm0
0x18005f2a5  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005f2aa  lea     rcx, [rbp+240h+var_260]
0x18005f2ae  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18005f2b3  test    rbx, rbx
0x18005f2b6  jz      loc_18005F777
0x18005f2bc  mov     ecx, [rbx]
0x18005f2be  lea     rax, [rbx+10h]
0x18005f2c2  add     rcx, rbx; char *
0x18005f2c5  cmp     rax, rcx
0x18005f2c8  ja      loc_18005F777
0x18005f2ce  mov     rax, [rbx+8]
0x18005f2d2  test    rax, rax
0x18005f2d5  jz      loc_18005F76E
0x18005f2db  cmp     [rax], r13w
0x18005f2df  jz      loc_18005F76E
0x18005f2e5  mov     edi, [rbx+4]
0x18005f2e8  test    edi, 0FE0000FFh
0x18005f2ee  jz      short loc_18005F2FC
0x18005f2f0  mov     [rbp+240h+var_270], 8Bh
0x18005f2f7  jmp     loc_18005F77E
0x18005f2fc  mov     r12d, edi
0x18005f2ff  and     r12d, 100h
0x18005f306  jz      short loc_18005F31D
0x18005f308  lea     rax, [rbx+20h]
0x18005f30c  cmp     rax, rcx
0x18005f30f  jbe     short loc_18005F31D
0x18005f311  mov     [rbp+240h+var_270], 8Fh
0x18005f318  jmp     loc_18005F77E
0x18005f31d  mov     r13d, edi
0x18005f320  and     r13d, 80000h
0x18005f327  jz      short loc_18005F357
0x18005f329  lea     rax, [rbx+18h]
0x18005f32d  cmp     rax, rcx
0x18005f330  jbe     short loc_18005F357
0x18005f332  mov     [rbp+240h+var_270], 90h
0x18005f339  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x18005f33e  mov     ecx, 57h ; 'W'; dwErrCode
0x18005f343  call    cs:__imp_SetLastError
0x18005f34a  nop     dword ptr [rax+rax+00h]
0x18005f34f  xor     r13d, r13d
0x18005f352  jmp     loc_18005F794
0x18005f357  mov     eax, edi
0x18005f359  and     eax, 100000h
0x18005f35e  mov     dword ptr [rsp+340h+var_310], eax
0x18005f362  jz      short loc_18005F376
0x18005f364  lea     rax, [rbx+28h]
0x18005f368  cmp     rax, rcx
0x18005f36b  jbe     short loc_18005F376
0x18005f36d  mov     [rbp+240h+var_270], 91h
0x18005f374  jmp     short loc_18005F339
0x18005f376  bt      edi, 10h
0x18005f37a  jnb     short loc_18005F38E
0x18005f37c  lea     rax, [rbx+30h]
0x18005f380  cmp     rax, rcx
0x18005f383  jbe     short loc_18005F38E
0x18005f385  mov     [rbp+240h+var_270], 92h
0x18005f38c  jmp     short loc_18005F339
0x18005f38e  bt      edi, 15h
0x18005f392  jnb     short loc_18005F3A6
0x18005f394  lea     rax, [rbx+38h]
0x18005f398  cmp     rax, rcx
0x18005f39b  jbe     short loc_18005F3A6
0x18005f39d  mov     [rbp+240h+var_270], 93h
0x18005f3a4  jmp     short loc_18005F339
0x18005f3a6  xor     r11d, r11d
0x18005f3a9  test    r12d, r12d
0x18005f3ac  jz      short loc_18005F3C9
0x18005f3ae  mov     rax, [rbx+18h]
0x18005f3b2  test    rax, rax
0x18005f3b5  jz      short loc_18005F3BD
0x18005f3b7  cmp     [rax], r11w
0x18005f3bb  jnz     short loc_18005F3C9
0x18005f3bd  mov     [rbp+240h+var_270], 9Bh
0x18005f3c4  jmp     loc_18005F339
0x18005f3c9  test    r13d, r13d
0x18005f3cc  jz      short loc_18005F3E0
0x18005f3ce  cmp     [rbx+10h], r11
0x18005f3d2  jnz     short loc_18005F3E0
0x18005f3d4  mov     [rbp+240h+var_270], 0B2h
0x18005f3db  jmp     loc_18005F339
0x18005f3e0  bt      edi, 11h
0x18005f3e4  jnb     short loc_18005F3F7
0x18005f3e6  test    r12d, r12d
0x18005f3e9  jz      short loc_18005F3F7
0x18005f3eb  mov     [rbp+240h+var_270], 0B7h
0x18005f3f2  jmp     loc_18005F339
0x18005f3f7  xor     ecx, ecx; dwErrCode
0x18005f3f9  call    cs:__imp_SetLastError
0x18005f400  nop     dword ptr [rax+rax+00h]
0x18005f405  mov     rcx, [rbx+8]; lpFileName
0x18005f409  lea     r8, [rbp+240h+var_1B0]
0x18005f410  call    ?SxspExpandRelativePathToFull@@YAHPEBG_KAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; SxspExpandRelativePathToFull(ushort const *,unsigned __int64,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18005f415  xor     r9d, r9d
0x18005f418  test    eax, eax
0x18005f41a  jnz     short loc_18005F437
0x18005f41c  lea     rcx, off_180074830; struct _CALL_SITE_INFO *
0x18005f423  mov     rax, [rbp+240h+var_268]
0x18005f427  mov     [rax], r9d
0x18005f42a  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18005f42f  xor     r13d, r13d
0x18005f432  jmp     loc_18005F79B
0x18005f437  mov     rcx, [rbp+240h+var_1A0]
0x18005f43e  mov     [rsp+340h+var_2F0], rcx
0x18005f443  test    r13d, r13d
0x18005f446  jz      short loc_18005F44E
0x18005f448  mov     r13, [rbx+10h]
0x18005f44c  jmp     short loc_18005F451
0x18005f44e  mov     r13, r9
0x18005f451  test    r12d, r12d
0x18005f454  jz      short loc_18005F45C
0x18005f456  mov     r12, [rbx+18h]
0x18005f45a  jmp     short loc_18005F45F
0x18005f45c  mov     r12, r9
0x18005f45f  cmp     dword ptr [rsp+340h+var_310], r9d
0x18005f464  jz      short loc_18005F471
0x18005f466  mov     rax, [rbx+20h]
0x18005f46a  mov     [rsp+340h+var_310], rax
0x18005f46f  jmp     short loc_18005F476
0x18005f471  mov     [rsp+340h+var_310], r9
0x18005f476  bt      edi, 10h
0x18005f47a  jnb     short loc_18005F487
0x18005f47c  mov     rax, [rbx+28h]
0x18005f480  mov     [rsp+340h+var_300], rax
0x18005f485  jmp     short loc_18005F48C
0x18005f487  mov     [rsp+340h+var_300], r9
0x18005f48c  bt      edi, 15h
0x18005f490  jnb     short loc_18005F498
0x18005f492  mov     rax, [rbx+30h]
0x18005f496  jmp     short loc_18005F504
0x18005f498  movups  xmm0, cs:SXS_INSTALL_REFERENCE_SCHEME_SXS_INSTALL_ASSEMBLY
0x18005f49f  xor     ecx, ecx; dwErrCode
0x18005f4a1  mov     qword ptr [rbp+240h+var_2C0], 28h ; '('
0x18005f4a9  mov     [rbp+240h+var_2A0], r9
0x18005f4ad  movdqu  [rbp+240h+var_2C0+8], xmm0
0x18005f4b2  mov     qword ptr [rbp+240h+var_2B0+8], r9
0x18005f4b6  call    cs:__imp_SetLastError
0x18005f4bd  nop     dword ptr [rax+rax+00h]
0x18005f4c2  xor     ecx, ecx; lpModuleName
0x18005f4c4  call    cs:__imp_GetModuleHandleW
0x18005f4cb  nop     dword ptr [rax+rax+00h]
0x18005f4d0  mov     rdx, rax
0x18005f4d3  lea     r8, [rbp+240h+var_260]
0x18005f4d7  call    ?FusionpGetModuleFileName@@YAHKPEAUHINSTANCE__@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; FusionpGetModuleFileName(ulong,HINSTANCE__ *,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x18005f4dc  xor     r9d, r9d
0x18005f4df  test    eax, eax
0x18005f4e1  jnz     short loc_18005F4EF
0x18005f4e3  lea     rcx, off_180074810; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18005f4ea  jmp     loc_18005F423
0x18005f4ef  mov     rax, [rbp+240h+var_250]
0x18005f4f3  bts     edi, 15h
0x18005f4f7  mov     rcx, [rsp+340h+var_2F0]
0x18005f4fc  mov     [rbp+240h+var_2A0], rax
0x18005f500  lea     rax, [rbp+240h+var_2C0]
0x18005f504  mov     ebx, 100h
0x18005f509  mov     [rsp+340h+var_2F8], rax
0x18005f50e  test    ebx, edi
0x18005f510  jnz     short loc_18005F51D
0x18005f512  bt      edi, 11h
0x18005f516  jb      short loc_18005F51D
0x18005f518  mov     r12, rcx
0x18005f51b  or      edi, ebx
0x18005f51d  mov     r8d, 800h
0x18005f523  mov     qword ptr [rsp+340h+var_2E8], 28h ; '('
0x18005f52c  mov     r11d, 4000h
0x18005f532  mov     r10d, 8000h
0x18005f538  mov     ecx, edi
0x18005f53a  mov     esi, 2000h
0x18005f53f  shr     ecx, 3
0x18005f542  mov     r9d, edi
0x18005f545  and     ecx, 40h
0x18005f548  xorps   xmm0, xmm0
0x18005f54b  mov     edx, ecx
0x18005f54d  xorps   xmm1, xmm1
0x18005f550  or      edx, r8d
0x18005f553  bt      edi, 0Ah
0x18005f557  movdqu  [rsp+340h+var_2E8+8], xmm0
0x18005f55d  cmovnb  edx, ecx
0x18005f560  mov     ecx, edx
0x18005f562  or      ecx, 2
0x18005f565  test    r11d, edi
0x18005f568  movdqu  [rsp+340h+var_2D8+8], xmm1
0x18005f56e  cmovz   ecx, edx
0x18005f571  mov     edx, ecx
0x18005f573  or      edx, r15d
0x18005f576  test    esi, edi
0x18005f578  cmovz   edx, ecx
0x18005f57b  mov     ecx, edx
0x18005f57d  or      ecx, 4
0x18005f580  test    r10d, edi
0x18005f583  cmovz   ecx, edx
0x18005f586  mov     edx, ecx
0x18005f588  or      edx, 10h
0x18005f58b  test    r8d, edi
0x18005f58e  cmovz   edx, ecx
0x18005f591  mov     r8d, edx
0x18005f594  or      r8d, 20h
0x18005f598  bt      edi, 0Ch
0x18005f59c  cmovnb  r8d, edx
0x18005f5a0  mov     ecx, r8d
0x18005f5a3  or      ecx, r11d
0x18005f5a6  xor     r11d, r11d
0x18005f5a9  and     r9d, 20000h
0x18005f5b0  cmovz   ecx, r8d
0x18005f5b4  mov     r8d, 10000h
0x18005f5ba  mov     edx, ecx
0x18005f5bc  bts     edx, 12h
0x18005f5c0  bt      edi, 17h
0x18005f5c4  cmovnb  edx, ecx
0x18005f5c7  mov     ecx, edx
0x18005f5c9  or      ecx, r10d
0x18005f5cc  mov     r10d, 80000h
0x18005f5d2  bt      edi, 15h
0x18005f5d6  cmovnb  ecx, edx
0x18005f5d9  mov     edx, ecx
0x18005f5db  or      edx, r8d
0x18005f5de  bt      edi, 16h
0x18005f5e2  cmovnb  edx, ecx
0x18005f5e5  mov     ecx, edi
0x18005f5e7  mov     r14d, edx
0x18005f5ea  or      r14d, r10d
0x18005f5ed  bt      edi, 18h
0x18005f5f1  cmovnb  r14d, edx
0x18005f5f5  and     ecx, ebx
0x18005f5f7  jz      short loc_18005F603
0x18005f5f9  mov     qword ptr [rsp+340h+var_2D8], r12
0x18005f5fe  mov     dword ptr [rsp+340h+var_2E8+8], r15d
0x18005f603  test    ecx, ecx
0x18005f605  mov     eax, r11d
0x18005f608  setnz   al
0x18005f60b  neg     ecx
0x18005f60d  lea     rcx, [rsp+340h+var_2E8]
0x18005f612  sbb     rbx, rbx
0x18005f615  and     rbx, rcx
0x18005f618  bt      edi, 14h
0x18005f61c  jnb     short loc_18005F634
0x18005f61e  mov     rcx, [rsp+340h+var_310]
0x18005f623  lea     rbx, [rsp+340h+var_2E8]
0x18005f628  or      eax, 2
0x18005f62b  mov     qword ptr [rsp+340h+var_2D8+8], rcx
0x18005f630  mov     dword ptr [rsp+340h+var_2E8+8], eax
0x18005f634  test    r8d, edi
0x18005f637  jz      short loc_18005F652
0x18005f639  mov     rcx, [rsp+340h+var_300]
0x18005f63e  lea     rbx, [rsp+340h+var_2E8]
0x18005f643  or      r14d, esi
0x18005f646  mov     [rsp+340h+var_2C8], rcx
0x18005f64b  or      eax, 20h
0x18005f64e  mov     dword ptr [rsp+340h+var_2E8+8], eax
0x18005f652  test    r9d, r9d
0x18005f655  jz      short loc_18005F663
0x18005f657  or      eax, 40h
0x18005f65a  lea     rbx, [rsp+340h+var_2E8]
0x18005f65f  mov     dword ptr [rsp+340h+var_2E8+8], eax
0x18005f663  test    r10d, edi
0x18005f666  jz      short loc_18005F683
0x18005f668  mov     rax, [r13+0]
  ... truncated ...
```
