# CHttpRequest::HandleRequest(uchar *,ulong)

- ea: `0x1800175c0`
- end: `0x180017da7`
- name: `?HandleRequest@CHttpRequest@@QEAAJPEAEK@Z`
- size: `2023`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800174a0`

## callees

- `0x1800074dc`
- `0x180016740`
- `0x180016978`
- `0x180017060`
- `0x1800175c0`
- `0x180018a60`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x18003d4b0`
- `0x1800520d0`
- `0x1800525fc`
- `0x1800527c4`
- `0x1800529e4`
- `0x180052b14`
- `0x180052d2c`
- `0x180052e90`
- `0x180052f48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001787d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001798c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001787d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001798c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d96`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180017be9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180017be9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800176a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800176a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017bcb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017bcb`

## pseudocode

```c
__int64 __fastcall CHttpRequest::HandleRequest(CHttpRequest *this, unsigned __int8 *a2, unsigned int a3)
{
  bool v3; // zf
  __int64 v6; // rsi
  BOOL v8; // r15d
  unsigned int v9; // r12d
  const unsigned __int16 *v10; // rdx
  unsigned int Win32Error; // r14d
  unsigned __int16 *v12; // rcx
  DWORD FileAttributesW; // eax
  int v14; // ecx
  int v15; // eax
  __int64 v17; // rsi
  int v18; // edi
  char v19; // al
  int v20; // edx
  int v21; // r8d
  const char *v22; // r8
  __int64 v23; // rax
  const char *v24; // rdx
  DWORD LastError; // eax
  STRSAFE_PCNZWCH v26; // rcx
  DWORD v27; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  __int64 v33; // rax
  __int64 v34; // rdi
  _BYTE *v35; // rcx
  char v36; // al
  const char *v37; // rdx
  const WCHAR *v38; // rcx
  HANDLE FileW; // rax
  void *v40; // rdi
  DWORD FileSize; // eax
  unsigned int v42; // r12d
  DWORD v43; // eax
  DWORD v44; // eax
  const unsigned __int16 *v45; // r8
  void *v46; // rdx
  __int64 v47; // [rsp+50h] [rbp-B0h]
  __int64 v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h]
  _BYTE v51[568]; // [rsp+70h] [rbp-90h] BYREF
  int v52; // [rsp+2A8h] [rbp+1A8h]
  int v53; // [rsp+2ACh] [rbp+1ACh]
  __int64 v54; // [rsp+2B0h] [rbp+1B0h]
  __int64 v55; // [rsp+2B8h] [rbp+1B8h]
  _BYTE v56[104]; // [rsp+2C0h] [rbp+1C0h] BYREF
  CHttpRequest *v57; // [rsp+328h] [rbp+228h]
  __int64 v58; // [rsp+330h] [rbp+230h]

  v3 = *((_QWORD *)this + 7) == 0;
  v6 = *((_QWORD *)this + 1);
  v8 = 1;
  v48 = v6;
  v9 = 3;
  v47 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
  *((_DWORD *)this + 42) = 0;
  if ( !v3 || *((_QWORD *)this + 15) || *((_QWORD *)this + 8) || *((_QWORD *)this + 18) )
  {
    Win32Error = -2147467259;
    goto LABEL_19;
  }
  if ( !(unsigned int)CHttpRequest::UpdateVars(this) )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids);
    }
    Win32Error = -2147467259;
    goto LABEL_19;
  }
  if ( *((_DWORD *)this + 54) >= 0x20000u )
  {
    v9 = 8;
    Win32Error = -2147467259;
    *((_DWORD *)this + 42) = 8;
    goto LABEL_19;
  }
  Win32Error = 0;
  if ( a3 )
  {
    Win32Error = CBuffer::RecvToBuf((CHttpRequest *)((char *)this + 24), a2, a3);
    if ( (Win32Error & 0x80000000) != 0 )
      goto LABEL_19;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids, a3);
        v26 = WPP_GLOBAL_Control;
      }
      if ( v26 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x1000) != 0 )
        WPP_SF_s(*((_QWORD *)v26 + 2), 14, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids, *((_QWORD *)this + 3));
    }
  }
  if ( !*((_QWORD *)this + 16) )
  {
    v9 = 5;
    Win32Error = -2147467259;
    *((_DWORD *)this + 42) = 5;
    goto LABEL_19;
  }
  v12 = (unsigned __int16 *)*((_QWORD *)this + 17);
  if ( v12 && wcsstr(v12, v10) )
  {
    Win32Error = -2147467259;
LABEL_30:
    v9 = 5;
LABEL_31:
    *((_DWORD *)this + 42) = v9;
    goto LABEL_19;
  }
  FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 16));
  if ( FileAttributesW == -1 )
  {
    Win32Error = HrFromLastWin32Error();
    LastError = GetLastError();
    if ( LastError == 123 )
      goto LABEL_30;
    v31 = LastError - 2;
    if ( !v31 )
      goto LABEL_30;
    v32 = v31 - 1;
    if ( !v32 )
      goto LABEL_30;
    if ( v32 != 2 )
    {
      v9 = 6;
      goto LABEL_31;
    }
    goto LABEL_56;
  }
  if ( (FileAttributesW & 0x10) != 0 )
  {
    v33 = *((_QWORD *)this + 8);
    v34 = -1;
    do
      v3 = *(_BYTE *)(v33 + v34++ + 1) == 0;
    while ( !v3 );
    v35 = (_BYTE *)(v33 + v34);
    v36 = *(_BYTE *)(v33 + v34 - 1);
    if ( v36 != 47 && v36 != 92 )
    {
      *v35 = 47;
      *(_BYTE *)(*((_QWORD *)this + 8) + v34 + 1) = 0;
      memset_0(v51, 0, sizeof(v51));
      memset_0(v56, 0, sizeof(v56));
      v37 = (const char *)*((_QWORD *)this + 8);
      v49 = v6;
      v58 = 0;
      v50 = v47;
      v3 = *((_DWORD *)this + 27) == 0;
      v52 = 1;
      v57 = this;
      v55 = 0;
      v53 = !v3 + 1;
      v54 = 0;
      *((_DWORD *)this + 42) = 1;
      if ( CHttpResponse::SendRedirect((CHttpResponse *)&v49, v37) )
        Win32Error = HrFromLastWin32Error();
      *(_BYTE *)(v34 + *((_QWORD *)this + 8)) = 0;
      return Win32Error;
    }
    CHttpRequest::MapDirToDefaultPage(this);
  }
  if ( (unsigned int)CHttpRequest::HandleScript(this) )
  {
    v14 = *((_DWORD *)this + 42);
    v15 = Win32Error;
    if ( v14 )
      v15 = -2147467259;
    Win32Error = v15;
    v8 = v14 != 0;
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids);
  if ( *((_DWORD *)this + 55) == 1 )
  {
    v9 = 7;
    Win32Error = -2147467259;
    *((_DWORD *)this + 42) = 7;
    goto LABEL_19;
  }
  if ( (*((_BYTE *)this + 164) & 1) == 0 || (v38 = (const WCHAR *)*((_QWORD *)this + 16)) == 0 )
  {
    v9 = 4;
    Win32Error = -2147467259;
    *((_DWORD *)this + 42) = 4;
    goto LABEL_19;
  }
  FileW = CreateFileW(v38, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v40 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    Win32Error = HrFromLastWin32Error();
    v27 = GetLastError();
    if ( v27 == 123 )
      goto LABEL_30;
    v28 = v27 - 2;
    if ( !v28 )
      goto LABEL_30;
    v29 = v28 - 1;
    if ( !v29 )
      goto LABEL_30;
    if ( v29 != 2 )
    {
      v9 = 6;
      goto LABEL_31;
    }
LABEL_56:
    v9 = 4;
    goto LABEL_31;
  }
  FileSize = GetFileSize(FileW, 0);
  v42 = FileSize;
  if ( FileSize == -1 )
  {
    Win32Error = HrFromLastWin32Error();
    v30 = GetLastError();
    if ( v30 != 123 && (v43 = v30 - 2) != 0 && (v44 = v43 - 1) != 0 )
    {
      if ( v44 == 2 )
        v9 = 4;
      else
        v9 = 6;
    }
    else
    {
      v9 = 5;
    }
  }
  else if ( *((_DWORD *)this + 55) == 4 && CHttpRequest::IsNotModified(this, v40, FileSize) )
  {
    Win32Error = -2147467259;
    v9 = 2;
  }
  else
  {
    if ( *((_DWORD *)this + 54) > 9u )
    {
      memset_0(v51, 0, sizeof(v51));
      memset_0(v56, 0, sizeof(v56));
      v45 = (const unsigned __int16 *)*((_QWORD *)this + 17);
      v49 = v6;
      v58 = 0;
      v46 = v40;
      v50 = v47;
      v3 = *((_DWORD *)this + 27) == 0;
      v52 = 0;
      v57 = this;
      v55 = 0;
      v53 = !v3 + 1;
      v3 = *((_DWORD *)this + 55) == 5;
      v54 = 0;
      if ( v3 )
        v46 = 0;
      *((_DWORD *)this + 42) = 0;
      CHttpResponse::SetBody((CHttpResponse *)&v49, v46, v45, v42);
      if ( CHttpResponse::SendResponse((CHttpResponse *)&v49, 0, 0) )
        Win32Error = HrFromLastWin32Error();
    }
    else
    {
      Win32Error = -2147467259;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids);
      }
    }
    v8 = 0;
    v9 = 0;
  }
  *((_DWORD *)this + 42) = v9;
  if ( v40 )
    CloseHandle(v40);
LABEL_16:
  if ( !v8 )
    return Win32Error;
LABEL_19:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    v17 = (__int64)*(&rgStatus + 3 * v9 + 1);
    v18 = *((_DWORD *)&rgStatus + 6 * v9);
    v19 = GetLastError();
    WPP_SF_ddddds(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v21, a3, v19, v8, v9, v18, v17);
    v6 = v48;
  }
  *((_DWORD *)this + 27) = 0;
  memset_0(v51, 0, sizeof(v51));
  memset_0(v56, 0, sizeof(v56));
  v49 = v6;
  v58 = 0;
  v50 = v47;
  v23 = *((int *)this + 42);
  v52 = v23;
  v53 = 1;
  v57 = this;
  v55 = 0;
  v54 = 0;
  if ( (unsigned int)v23 <= 8 )
  {
    v24 = (const char *)*(&rgStatus + 3 * v23 + 2);
    if ( v24 )
      CHttpResponse::SetBody((CHttpResponse *)&v49, v24, v22);
  }
  if ( !CHttpResponse::SendResponse((CHttpResponse *)&v49, 0, 0) )
    return Win32Error;
  return HrFromLastWin32Error();
}

```

## disassembly

```asm
0x1800175c0  mov     [rsp-8+arg_18], rbx
0x1800175c5  push    rbp
0x1800175c6  push    rsi
0x1800175c7  push    rdi
0x1800175c8  push    r12
0x1800175ca  push    r13
0x1800175cc  push    r14
0x1800175ce  push    r15
0x1800175d0  lea     rbp, [rsp-250h]
0x1800175d8  sub     rsp, 350h
0x1800175df  mov     rax, cs:__security_cookie
0x1800175e6  xor     rax, rsp
0x1800175e9  mov     [rbp+280h+var_40], rax
0x1800175f0  cmp     qword ptr [rcx+38h], 0
0x1800175f5  mov     r13d, r8d
0x1800175f8  mov     rax, [rcx+10h]
0x1800175fc  mov     rdi, rdx
0x1800175ff  mov     rsi, [rcx+8]
0x180017603  mov     rbx, rcx
0x180017606  mov     r15d, 1
0x18001760c  mov     [rsp+380h+var_328], rsi
0x180017611  mov     r12d, 3
0x180017617  mov     rax, [rax+10h]
0x18001761b  mov     [rsp+380h+var_330], rax
0x180017620  mov     dword ptr [rcx+0A8h], 0
0x18001762a  jnz     loc_18001772A
0x180017630  cmp     qword ptr [rcx+78h], 0
0x180017635  jnz     loc_18001772A
0x18001763b  cmp     qword ptr [rcx+40h], 0
0x180017640  jnz     loc_18001772A
0x180017646  cmp     qword ptr [rcx+90h], 0
0x18001764e  jnz     loc_18001772A
0x180017654  call    ?UpdateVars@CHttpRequest@@AEAAHXZ; CHttpRequest::UpdateVars(void)
0x180017659  test    eax, eax
0x18001765b  jz      loc_18001793F
0x180017661  cmp     dword ptr [rbx+0D8h], 20000h
0x18001766b  lea     rax, WPP_GLOBAL_Control
0x180017672  jnb     loc_1800179EF
0x180017678  xor     r14d, r14d
0x18001767b  test    r13d, r13d
0x18001767e  jnz     loc_1800178A4
0x180017684  cmp     qword ptr [rbx+80h], 0
0x18001768c  jz      loc_180017A07
0x180017692  mov     rcx, [rbx+88h]; unsigned __int16 *
0x180017699  test    rcx, rcx
0x18001769c  jnz     loc_18001785F
0x1800176a2  mov     rcx, [rbx+80h]; lpFileName
0x1800176a9  call    cs:__imp_GetFileAttributesW
0x1800176b0  nop     dword ptr [rax+rax+00h]
0x1800176b5  cmp     eax, 0FFFFFFFFh
0x1800176b8  jz      loc_180017875
0x1800176be  test    al, 10h
0x1800176c0  jnz     loc_180017A4C
0x1800176c6  mov     rcx, rbx; this
0x1800176c9  call    ?HandleScript@CHttpRequest@@AEAAHXZ; CHttpRequest::HandleScript(void)
0x1800176ce  test    eax, eax
0x1800176d0  jz      loc_180017B34
0x1800176d6  mov     ecx, [rbx+0A8h]
0x1800176dc  mov     eax, r14d
0x1800176df  test    ecx, ecx
0x1800176e1  mov     r14d, 80004005h
0x1800176e7  cmovnz  eax, r14d
0x1800176eb  xor     r15d, r15d
0x1800176ee  test    ecx, ecx
0x1800176f0  mov     r14d, eax
0x1800176f3  setnz   r15b
0x1800176f7  test    r15d, r15d
0x1800176fa  jnz     short loc_180017730
0x1800176fc  mov     eax, r14d
0x1800176ff  mov     rcx, [rbp+280h+var_40]
0x180017706  xor     rcx, rsp; StackCookie
0x180017709  call    __security_check_cookie
0x18001770e  mov     rbx, [rsp+380h+arg_18]
0x180017716  add     rsp, 350h
0x18001771d  pop     r15
0x18001771f  pop     r14
0x180017721  pop     r13
0x180017723  pop     r12
0x180017725  pop     rdi
0x180017726  pop     rsi
0x180017727  pop     rbp
0x180017728  retn
0x18001772a  mov     r14d, 80004005h
0x180017730  lea     rax, WPP_GLOBAL_Control
0x180017737  mov     rcx, cs:WPP_GLOBAL_Control
0x18001773e  lea     rdi, ?rgStatus@@3PAUSTATUSINFO@@A; STATUSINFO near * rgStatus
0x180017745  cmp     rcx, rax
0x180017748  jz      short loc_1800177A4
0x18001774a  test    dword ptr [rcx+1Ch], 1000h
0x180017751  jz      short loc_1800177A4
0x180017753  mov     eax, r12d
0x180017756  lea     rcx, [rax+rax*2]
0x18001775a  mov     rsi, [rdi+rcx*8+8]
0x18001775f  mov     edi, [rdi+rcx*8]
0x180017762  call    cs:__imp_GetLastError
0x180017769  nop     dword ptr [rax+rax+00h]
0x18001776e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017775  mov     r9d, r13d
0x180017778  mov     [rsp+380h+var_340], rsi
0x18001777d  mov     [rsp+380h+var_348], edi
0x180017781  mov     dword ptr [rsp+380h+hTemplateFile], r12d
0x180017786  mov     rcx, [rcx+10h]
0x18001778a  mov     [rsp+380h+dwFlagsAndAttributes], r15d
0x18001778f  mov     [rsp+380h+dwCreationDisposition], eax
0x180017793  call    WPP_SF_ddddds
0x180017798  mov     rsi, [rsp+380h+var_328]
0x18001779d  lea     rdi, ?rgStatus@@3PAUSTATUSINFO@@A; STATUSINFO near * rgStatus
0x1800177a4  xor     edx, edx; Val
0x1800177a6  mov     dword ptr [rbx+6Ch], 0
0x1800177ad  mov     r8d, 238h; Size
0x1800177b3  lea     rcx, [rsp+380h+var_310]; void *
0x1800177b8  call    memset_0
0x1800177bd  xor     edx, edx; Val
0x1800177bf  lea     rcx, [rbp+280h+var_C0]; void *
0x1800177c6  mov     r8d, 68h ; 'h'; Size
0x1800177cc  call    memset_0
0x1800177d1  xor     eax, eax
0x1800177d3  mov     [rsp+380h+var_320], rsi
0x1800177d8  mov     [rbp+280h+var_50], rax
0x1800177df  mov     rax, [rsp+380h+var_330]
0x1800177e4  mov     [rsp+380h+var_318], rax
0x1800177e9  movsxd  rax, dword ptr [rbx+0A8h]
0x1800177f0  mov     [rbp+280h+var_D8], eax
0x1800177f6  mov     [rbp+280h+var_D4], 1
0x180017800  mov     [rbp+280h+var_58], rbx
0x180017807  mov     [rbp+280h+var_C8], 0
0x180017812  mov     [rbp+280h+var_D0], 0
0x18001781d  test    eax, eax
0x18001781f  js      short loc_18001783E
0x180017821  cmp     eax, 9
0x180017824  jnb     short loc_18001783E
0x180017826  lea     rcx, [rax+rax*2]
0x18001782a  mov     rdx, [rdi+rcx*8+10h]; char *
0x18001782f  test    rdx, rdx
0x180017832  jz      short loc_18001783E
0x180017834  lea     rcx, [rsp+380h+var_320]; this
0x180017839  call    ?SetBody@CHttpResponse@@QEAAXPEBD0@Z; CHttpResponse::SetBody(char const *,char const *)
0x18001783e  xor     r8d, r8d; char *
0x180017841  lea     rcx, [rsp+380h+var_320]; this
0x180017846  xor     edx, edx; char *
0x180017848  call    ?SendResponse@CHttpResponse@@QEAAKPEBD0@Z; CHttpResponse::SendResponse(char const *,char const *)
0x18001784d  test    eax, eax
0x18001784f  jz      loc_1800176FC
0x180017855  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001785a  jmp     loc_1800176FF
0x18001785f  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x180017864  test    rax, rax
0x180017867  jz      loc_1800176A2
0x18001786d  mov     r14d, 80004005h
0x180017873  jmp     short loc_180017892
0x180017875  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001787a  mov     r14d, eax
0x18001787d  call    cs:__imp_GetLastError
0x180017884  nop     dword ptr [rax+rax+00h]
0x180017889  cmp     eax, 7Bh ; '{'
0x18001788c  jnz     loc_180017A1F
0x180017892  mov     r12d, 5
0x180017898  mov     [rbx+0A8h], r12d
0x18001789f  jmp     loc_180017730
0x1800178a4  lea     rcx, [rbx+18h]; this
0x1800178a8  mov     r8d, r13d; unsigned int
0x1800178ab  mov     rdx, rdi; unsigned __int8 *
0x1800178ae  call    ?RecvToBuf@CBuffer@@QEAAJPEAEK@Z; CBuffer::RecvToBuf(uchar *,ulong)
0x1800178b3  mov     r14d, eax
0x1800178b6  test    eax, eax
0x1800178b8  js      loc_180017730
0x1800178be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178c5  lea     rax, WPP_GLOBAL_Control
0x1800178cc  cmp     rcx, rax
0x1800178cf  jz      loc_180017684
0x1800178d5  test    dword ptr [rcx+1Ch], 1000h
0x1800178dc  jz      short loc_180017904
0x1800178de  mov     rcx, [rcx+10h]
0x1800178e2  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x1800178e9  mov     edx, 0Dh
0x1800178ee  mov     r9d, r13d
0x1800178f1  call    WPP_SF_d
0x1800178f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178fd  lea     rax, WPP_GLOBAL_Control
0x180017904  cmp     rcx, rax
0x180017907  jz      loc_180017684
0x18001790d  test    dword ptr [rcx+1Ch], 1000h
0x180017914  jz      loc_180017684
0x18001791a  mov     r9, [rbx+18h]
0x18001791e  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x180017925  mov     rcx, [rcx+10h]
0x180017929  mov     edx, 0Eh
0x18001792e  call    WPP_SF_s
0x180017933  lea     rax, WPP_GLOBAL_Control
0x18001793a  jmp     loc_180017684
0x18001793f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017946  lea     rax, WPP_GLOBAL_Control
0x18001794d  cmp     rcx, rax
0x180017950  jnz     short loc_18001795D
0x180017952  mov     r14d, 80004005h
0x180017958  jmp     loc_180017737
0x18001795d  test    dword ptr [rcx+1Ch], 1000h
0x180017964  jz      short loc_180017952
0x180017966  mov     rcx, [rcx+10h]
0x18001796a  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x180017971  mov     edx, 0Ch
0x180017976  call    WPP_SF_
0x18001797b  lea     rax, WPP_GLOBAL_Control
0x180017982  jmp     short loc_180017952
0x180017984  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180017989  mov     r14d, eax
0x18001798c  call    cs:__imp_GetLastError
0x180017993  nop     dword ptr [rax+rax+00h]
0x180017998  cmp     eax, 7Bh ; '{'
0x18001799b  jz      loc_180017892
0x1800179a1  sub     eax, 2
0x1800179a4  jz      loc_180017892
0x1800179aa  sub     eax, r15d
0x1800179ad  jz      loc_180017892
0x1800179b3  cmp     eax, 2
0x1800179b6  jz      loc_180017A41
0x1800179bc  mov     r12d, 6
0x1800179c2  jmp     loc_180017898
0x1800179c7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800179cc  mov     r14d, eax
0x1800179cf  call    cs:__imp_GetLastError
0x1800179d6  nop     dword ptr [rax+rax+00h]
0x1800179db  cmp     eax, 7Bh ; '{'
0x1800179de  jnz     loc_180017C45
0x1800179e4  mov     r12d, 5
0x1800179ea  jmp     loc_180017D83
0x1800179ef  mov     r12d, 8
0x1800179f5  mov     r14d, 80004005h
0x1800179fb  mov     [rbx+0A8h], r12d
0x180017a02  jmp     loc_180017737
0x180017a07  mov     r12d, 5
0x180017a0d  mov     r14d, 80004005h
0x180017a13  mov     [rbx+0A8h], r12d
0x180017a1a  jmp     loc_180017737
0x180017a1f  sub     eax, 2
0x180017a22  jz      loc_180017892
0x180017a28  sub     eax, r15d
0x180017a2b  jz      loc_180017892
0x180017a31  cmp     eax, 2
0x180017a34  jz      short loc_180017A41
0x180017a36  mov     r12d, 6
0x180017a3c  jmp     loc_180017898
0x180017a41  mov     r12d, 4
0x180017a47  jmp     loc_180017898
0x180017a4c  mov     rax, [rbx+40h]
0x180017a50  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180017a57  cmp     byte ptr [rax+rdi+1], 0
0x180017a5c  lea     rdi, [rdi+1]
0x180017a60  jnz     short loc_180017A57
0x180017a62  lea     rcx, [rax+rdi]
0x180017a66  movzx   eax, byte ptr [rax+rdi-1]
0x180017a6b  cmp     al, 2Fh ; '/'
0x180017a6d  jz      loc_180017B27
0x180017a73  cmp     al, 5Ch ; '\'
0x180017a75  jz      loc_180017B27
0x180017a7b  mov     byte ptr [rcx], 2Fh ; '/'
0x180017a7e  xor     edx, edx; Val
0x180017a80  mov     rax, [rbx+40h]
0x180017a84  lea     rcx, [rsp+380h+var_310]; void *
0x180017a89  mov     r8d, 238h; Size
0x180017a8f  mov     byte ptr [rax+rdi+1], 0
0x180017a94  call    memset_0
0x180017a99  xor     edx, edx; Val
0x180017a9b  lea     rcx, [rbp+280h+var_C0]; void *
0x180017aa2  mov     r8d, 68h ; 'h'; Size
0x180017aa8  call    memset_0
0x180017aad  mov     rdx, [rbx+40h]; char *
0x180017ab1  lea     rcx, [rsp+380h+var_320]; this
0x180017ab6  xor     eax, eax
0x180017ab8  mov     [rsp+380h+var_320], rsi
0x180017abd  mov     [rbp+280h+var_50], rax
0x180017ac4  mov     rax, [rsp+380h+var_330]
0x180017ac9  mov     [rsp+380h+var_318], rax
0x180017ace  xor     eax, eax
0x180017ad0  cmp     [rbx+6Ch], eax
0x180017ad3  mov     [rbp+280h+var_D8], r15d
0x180017ada  setnz   al
0x180017add  mov     [rbp+280h+var_58], rbx
0x180017ae4  inc     eax
0x180017ae6  mov     [rbp+280h+var_C8], 0
0x180017af1  mov     [rbp+280h+var_D4], eax
0x180017af7  mov     [rbp+280h+var_D0], 0
0x180017b02  mov     [rbx+0A8h], r15d
0x180017b09  call    ?SendRedirect@CHttpResponse@@QEAAKPEBD@Z; CHttpResponse::SendRedirect(char const *)
0x180017b0e  test    eax, eax
0x180017b10  jz      short loc_180017B1A
0x180017b12  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180017b17  mov     r14d, eax
0x180017b1a  mov     rax, [rbx+40h]
0x180017b1e  mov     byte ptr [rdi+rax], 0
0x180017b22  jmp     loc_1800176FC
0x180017b27  mov     rcx, rbx; this
0x180017b2a  call    ?MapDirToDefaultPage@CHttpRequest@@AEAAHXZ; CHttpRequest::MapDirToDefaultPage(void)
0x180017b2f  jmp     loc_1800176C6
0x180017b34  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b3b  lea     rax, WPP_GLOBAL_Control
0x180017b42  cmp     rcx, rax
0x180017b45  jz      short loc_180017B6C
0x180017b47  test    dword ptr [rcx+1Ch], 1000h
0x180017b4e  jz      short loc_180017B6C
  ... truncated ...
```
