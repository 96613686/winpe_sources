# CHttpRequest::HandleRequest(uchar *,ulong)

- ea: `0x180002b40`
- end: `0x1800032b5`
- name: `?HandleRequest@CHttpRequest@@QEAAJPEAEK@Z`
- size: `1909`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180002a20`

## callees

- `0x180001d00`
- `0x180001f18`
- `0x180002600`
- `0x180002b40`
- `0x180003dc0`
- `0x18001347c`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x18003ae80`
- `0x18004eb70`
- `0x18004f060`
- `0x18004f228`
- `0x18004f430`
- `0x18004f54c`
- `0x18004f75c`
- `0x18004f8ac`
- `0x18004f954`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ef9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ef9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032aa`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180003103`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180003103`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002c29`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002c29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800030eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800030eb`

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
  __int64 v30; // rax
  __int64 v31; // rdi
  _BYTE *v32; // rcx
  char v33; // al
  const char *v34; // rdx
  const WCHAR *v35; // rcx
  HANDLE FileW; // rax
  void *v37; // rdi
  DWORD FileSize; // eax
  unsigned int v39; // r12d
  DWORD v40; // eax
  DWORD v41; // eax
  const unsigned __int16 *v42; // r8
  void *v43; // rdx
  __int64 v44; // [rsp+50h] [rbp-B0h]
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 v46; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h]
  _BYTE v48[568]; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+2A8h] [rbp+1A8h]
  int v50; // [rsp+2ACh] [rbp+1ACh]
  __int64 v51; // [rsp+2B0h] [rbp+1B0h]
  __int64 v52; // [rsp+2B8h] [rbp+1B8h]
  _BYTE v53[104]; // [rsp+2C0h] [rbp+1C0h] BYREF
  CHttpRequest *v54; // [rsp+328h] [rbp+228h]
  __int64 v55; // [rsp+330h] [rbp+230h]

  v3 = *((_QWORD *)this + 7) == 0;
  v6 = *((_QWORD *)this + 1);
  v8 = 1;
  v45 = v6;
  v9 = 3;
  v44 = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL);
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
    goto LABEL_30;
  }
  FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 16));
  if ( FileAttributesW == -1 )
    goto LABEL_29;
  if ( (FileAttributesW & 0x10) != 0 )
  {
    v30 = *((_QWORD *)this + 8);
    v31 = -1;
    do
      v3 = *(_BYTE *)(v30 + v31++ + 1) == 0;
    while ( !v3 );
    v32 = (_BYTE *)(v30 + v31);
    v33 = *(_BYTE *)(v30 + v31 - 1);
    if ( v33 != 47 && v33 != 92 )
    {
      *v32 = 47;
      *(_BYTE *)(*((_QWORD *)this + 8) + v31 + 1) = 0;
      memset_0(v48, 0, sizeof(v48));
      memset_0(v53, 0, sizeof(v53));
      v34 = (const char *)*((_QWORD *)this + 8);
      v46 = v6;
      v55 = 0;
      v47 = v44;
      v3 = *((_DWORD *)this + 27) == 0;
      v49 = 1;
      v54 = this;
      v52 = 0;
      v50 = !v3 + 1;
      v51 = 0;
      *((_DWORD *)this + 42) = 1;
      if ( CHttpResponse::SendRedirect((CHttpResponse *)&v46, v34) )
        Win32Error = HrFromLastWin32Error();
      *(_BYTE *)(v31 + *((_QWORD *)this + 8)) = 0;
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
  if ( (*((_BYTE *)this + 164) & 1) == 0 || (v35 = (const WCHAR *)*((_QWORD *)this + 16)) == 0 )
  {
    v9 = 4;
    Win32Error = -2147467259;
    *((_DWORD *)this + 42) = 4;
    goto LABEL_19;
  }
  FileW = CreateFileW(v35, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v37 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_29:
    Win32Error = HrFromLastWin32Error();
    LastError = GetLastError();
    if ( LastError != 123 )
    {
      v28 = LastError - 2;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          if ( v29 == 2 )
            v9 = 4;
          else
            v9 = 6;
          goto LABEL_31;
        }
      }
    }
LABEL_30:
    v9 = 5;
LABEL_31:
    *((_DWORD *)this + 42) = v9;
    goto LABEL_19;
  }
  FileSize = GetFileSize(FileW, 0);
  v39 = FileSize;
  if ( FileSize == -1 )
  {
    Win32Error = HrFromLastWin32Error();
    v27 = GetLastError();
    if ( v27 != 123 && (v40 = v27 - 2) != 0 && (v41 = v40 - 1) != 0 )
    {
      if ( v41 == 2 )
        v9 = 4;
      else
        v9 = 6;
    }
    else
    {
      v9 = 5;
    }
  }
  else if ( *((_DWORD *)this + 55) == 4 && CHttpRequest::IsNotModified(this, v37, FileSize) )
  {
    Win32Error = -2147467259;
    v9 = 2;
  }
  else
  {
    if ( *((_DWORD *)this + 54) > 9u )
    {
      memset_0(v48, 0, sizeof(v48));
      memset_0(v53, 0, sizeof(v53));
      v42 = (const unsigned __int16 *)*((_QWORD *)this + 17);
      v46 = v6;
      v55 = 0;
      v43 = v37;
      v47 = v44;
      v3 = *((_DWORD *)this + 27) == 0;
      v49 = 0;
      v54 = this;
      v52 = 0;
      v50 = !v3 + 1;
      v3 = *((_DWORD *)this + 55) == 5;
      v51 = 0;
      if ( v3 )
        v43 = 0;
      *((_DWORD *)this + 42) = 0;
      CHttpResponse::SetBody((CHttpResponse *)&v46, v43, v42, v39);
      if ( CHttpResponse::SendResponse((CHttpResponse *)&v46, 0, 0) )
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
  if ( v37 )
    CloseHandle(v37);
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
    v6 = v45;
  }
  *((_DWORD *)this + 27) = 0;
  memset_0(v48, 0, sizeof(v48));
  memset_0(v53, 0, sizeof(v53));
  v46 = v6;
  v55 = 0;
  v47 = v44;
  v23 = *((int *)this + 42);
  v49 = v23;
  v50 = 1;
  v54 = this;
  v52 = 0;
  v51 = 0;
  if ( (unsigned int)v23 <= 8 )
  {
    v24 = (const char *)*(&rgStatus + 3 * v23 + 2);
    if ( v24 )
      CHttpResponse::SetBody((CHttpResponse *)&v46, v24, v22);
  }
  if ( !CHttpResponse::SendResponse((CHttpResponse *)&v46, 0, 0) )
    return Win32Error;
  return HrFromLastWin32Error();
}

```

## disassembly

```asm
0x180002b40  mov     [rsp-8+arg_18], rbx
0x180002b45  push    rbp
0x180002b46  push    rsi
0x180002b47  push    rdi
0x180002b48  push    r12
0x180002b4a  push    r13
0x180002b4c  push    r14
0x180002b4e  push    r15
0x180002b50  lea     rbp, [rsp-250h]
0x180002b58  sub     rsp, 350h
0x180002b5f  mov     rax, cs:__security_cookie
0x180002b66  xor     rax, rsp
0x180002b69  mov     [rbp+280h+var_40], rax
0x180002b70  cmp     qword ptr [rcx+38h], 0
0x180002b75  mov     r13d, r8d
0x180002b78  mov     rax, [rcx+10h]
0x180002b7c  mov     rdi, rdx
0x180002b7f  mov     rsi, [rcx+8]
0x180002b83  mov     rbx, rcx
0x180002b86  mov     r15d, 1
0x180002b8c  mov     [rsp+380h+var_328], rsi
0x180002b91  mov     r12d, 3
0x180002b97  mov     rax, [rax+10h]
0x180002b9b  mov     [rsp+380h+var_330], rax
0x180002ba0  mov     dword ptr [rcx+0A8h], 0
0x180002baa  jnz     loc_180002CA3
0x180002bb0  cmp     qword ptr [rcx+78h], 0
0x180002bb5  jnz     loc_180002CA3
0x180002bbb  cmp     qword ptr [rcx+40h], 0
0x180002bc0  jnz     loc_180002CA3
0x180002bc6  cmp     qword ptr [rcx+90h], 0
0x180002bce  jnz     loc_180002CA3
0x180002bd4  call    ?UpdateVars@CHttpRequest@@AEAAHXZ; CHttpRequest::UpdateVars(void)
0x180002bd9  test    eax, eax
0x180002bdb  jz      loc_180002EAC
0x180002be1  cmp     dword ptr [rbx+0D8h], 20000h
0x180002beb  lea     rax, WPP_GLOBAL_Control
0x180002bf2  jnb     loc_180002F13
0x180002bf8  xor     r14d, r14d
0x180002bfb  test    r13d, r13d
0x180002bfe  jnz     loc_180002E11
0x180002c04  cmp     qword ptr [rbx+80h], 0
0x180002c0c  jz      loc_180002F2B
0x180002c12  mov     rcx, [rbx+88h]; unsigned __int16 *
0x180002c19  test    rcx, rcx
0x180002c1c  jnz     loc_180002DD2
0x180002c22  mov     rcx, [rbx+80h]; lpFileName
0x180002c29  call    cs:__imp_GetFileAttributesW
0x180002c2f  cmp     eax, 0FFFFFFFFh
0x180002c32  jz      loc_180002DE8
0x180002c38  test    al, 10h
0x180002c3a  jnz     loc_180002F70
0x180002c40  mov     rcx, rbx; this
0x180002c43  call    ?HandleScript@CHttpRequest@@AEAAHXZ; CHttpRequest::HandleScript(void)
0x180002c48  test    eax, eax
0x180002c4a  jz      loc_180003058
0x180002c50  mov     ecx, [rbx+0A8h]
0x180002c56  mov     eax, r14d
0x180002c59  test    ecx, ecx
0x180002c5b  mov     r14d, 80004005h
0x180002c61  cmovnz  eax, r14d
0x180002c65  xor     r15d, r15d
0x180002c68  test    ecx, ecx
0x180002c6a  mov     r14d, eax
0x180002c6d  setnz   r15b
0x180002c71  test    r15d, r15d
0x180002c74  jnz     short loc_180002CA9
0x180002c76  mov     eax, r14d
0x180002c79  mov     rcx, [rbp+280h+var_40]
0x180002c80  xor     rcx, rsp; StackCookie
0x180002c83  call    __security_check_cookie
0x180002c88  mov     rbx, [rsp+380h+arg_18]
0x180002c90  add     rsp, 350h
0x180002c97  pop     r15
0x180002c99  pop     r14
0x180002c9b  pop     r13
0x180002c9d  pop     r12
0x180002c9f  pop     rdi
0x180002ca0  pop     rsi
0x180002ca1  pop     rbp
0x180002ca2  retn
0x180002ca3  mov     r14d, 80004005h
0x180002ca9  lea     rax, WPP_GLOBAL_Control
0x180002cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cb7  lea     rdi, ?rgStatus@@3PAUSTATUSINFO@@A; STATUSINFO near * rgStatus
0x180002cbe  cmp     rcx, rax
0x180002cc1  jz      short loc_180002D17
0x180002cc3  test    dword ptr [rcx+1Ch], 1000h
0x180002cca  jz      short loc_180002D17
0x180002ccc  mov     eax, r12d
0x180002ccf  lea     rcx, [rax+rax*2]
0x180002cd3  mov     rsi, [rdi+rcx*8+8]
0x180002cd8  mov     edi, [rdi+rcx*8]
0x180002cdb  call    cs:__imp_GetLastError
0x180002ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ce8  mov     r9d, r13d
0x180002ceb  mov     [rsp+380h+var_340], rsi
0x180002cf0  mov     [rsp+380h+var_348], edi
0x180002cf4  mov     dword ptr [rsp+380h+hTemplateFile], r12d
0x180002cf9  mov     rcx, [rcx+10h]
0x180002cfd  mov     [rsp+380h+dwFlagsAndAttributes], r15d
0x180002d02  mov     [rsp+380h+dwCreationDisposition], eax
0x180002d06  call    WPP_SF_ddddds
0x180002d0b  mov     rsi, [rsp+380h+var_328]
0x180002d10  lea     rdi, ?rgStatus@@3PAUSTATUSINFO@@A; STATUSINFO near * rgStatus
0x180002d17  xor     edx, edx; Val
0x180002d19  mov     dword ptr [rbx+6Ch], 0
0x180002d20  mov     r8d, 238h; Size
0x180002d26  lea     rcx, [rsp+380h+var_310]; void *
0x180002d2b  call    memset_0
0x180002d30  xor     edx, edx; Val
0x180002d32  lea     rcx, [rbp+280h+var_C0]; void *
0x180002d39  mov     r8d, 68h ; 'h'; Size
0x180002d3f  call    memset_0
0x180002d44  xor     eax, eax
0x180002d46  mov     [rsp+380h+var_320], rsi
0x180002d4b  mov     [rbp+280h+var_50], rax
0x180002d52  mov     rax, [rsp+380h+var_330]
0x180002d57  mov     [rsp+380h+var_318], rax
0x180002d5c  movsxd  rax, dword ptr [rbx+0A8h]
0x180002d63  mov     [rbp+280h+var_D8], eax
0x180002d69  mov     [rbp+280h+var_D4], 1
0x180002d73  mov     [rbp+280h+var_58], rbx
0x180002d7a  mov     [rbp+280h+var_C8], 0
0x180002d85  mov     [rbp+280h+var_D0], 0
0x180002d90  test    eax, eax
0x180002d92  js      short loc_180002DB1
0x180002d94  cmp     eax, 9
0x180002d97  jnb     short loc_180002DB1
0x180002d99  lea     rcx, [rax+rax*2]
0x180002d9d  mov     rdx, [rdi+rcx*8+10h]; char *
0x180002da2  test    rdx, rdx
0x180002da5  jz      short loc_180002DB1
0x180002da7  lea     rcx, [rsp+380h+var_320]; this
0x180002dac  call    ?SetBody@CHttpResponse@@QEAAXPEBD0@Z; CHttpResponse::SetBody(char const *,char const *)
0x180002db1  xor     r8d, r8d; char *
0x180002db4  lea     rcx, [rsp+380h+var_320]; this
0x180002db9  xor     edx, edx; char *
0x180002dbb  call    ?SendResponse@CHttpResponse@@QEAAKPEBD0@Z; CHttpResponse::SendResponse(char const *,char const *)
0x180002dc0  test    eax, eax
0x180002dc2  jz      loc_180002C76
0x180002dc8  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180002dcd  jmp     loc_180002C79
0x180002dd2  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x180002dd7  test    rax, rax
0x180002dda  jz      loc_180002C22
0x180002de0  mov     r14d, 80004005h
0x180002de6  jmp     short loc_180002DFF
0x180002de8  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180002ded  mov     r14d, eax
0x180002df0  call    cs:__imp_GetLastError
0x180002df6  cmp     eax, 7Bh ; '{'
0x180002df9  jnz     loc_180002F43
0x180002dff  mov     r12d, 5
0x180002e05  mov     [rbx+0A8h], r12d
0x180002e0c  jmp     loc_180002CA9
0x180002e11  lea     rcx, [rbx+18h]; this
0x180002e15  mov     r8d, r13d; unsigned int
0x180002e18  mov     rdx, rdi; unsigned __int8 *
0x180002e1b  call    ?RecvToBuf@CBuffer@@QEAAJPEAEK@Z; CBuffer::RecvToBuf(uchar *,ulong)
0x180002e20  mov     r14d, eax
0x180002e23  test    eax, eax
0x180002e25  js      loc_180002CA9
0x180002e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e32  lea     rax, WPP_GLOBAL_Control
0x180002e39  cmp     rcx, rax
0x180002e3c  jz      loc_180002C04
0x180002e42  test    dword ptr [rcx+1Ch], 1000h
0x180002e49  jz      short loc_180002E71
0x180002e4b  mov     rcx, [rcx+10h]
0x180002e4f  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x180002e56  mov     edx, 0Dh
0x180002e5b  mov     r9d, r13d
0x180002e5e  call    WPP_SF_d
0x180002e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e6a  lea     rax, WPP_GLOBAL_Control
0x180002e71  cmp     rcx, rax
0x180002e74  jz      loc_180002C04
0x180002e7a  test    dword ptr [rcx+1Ch], 1000h
0x180002e81  jz      loc_180002C04
0x180002e87  mov     r9, [rbx+18h]
0x180002e8b  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x180002e92  mov     rcx, [rcx+10h]
0x180002e96  mov     edx, 0Eh
0x180002e9b  call    WPP_SF_s
0x180002ea0  lea     rax, WPP_GLOBAL_Control
0x180002ea7  jmp     loc_180002C04
0x180002eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eb3  lea     rax, WPP_GLOBAL_Control
0x180002eba  cmp     rcx, rax
0x180002ebd  jnz     short loc_180002ECA
0x180002ebf  mov     r14d, 80004005h
0x180002ec5  jmp     loc_180002CB0
0x180002eca  test    dword ptr [rcx+1Ch], 1000h
0x180002ed1  jz      short loc_180002EBF
0x180002ed3  mov     rcx, [rcx+10h]
0x180002ed7  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x180002ede  mov     edx, 0Ch
0x180002ee3  call    WPP_SF_
0x180002ee8  lea     rax, WPP_GLOBAL_Control
0x180002eef  jmp     short loc_180002EBF
0x180002ef1  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180002ef6  mov     r14d, eax
0x180002ef9  call    cs:__imp_GetLastError
0x180002eff  cmp     eax, 7Bh ; '{'
0x180002f02  jnz     loc_180003159
0x180002f08  mov     r12d, 5
0x180002f0e  jmp     loc_180003297
0x180002f13  mov     r12d, 8
0x180002f19  mov     r14d, 80004005h
0x180002f1f  mov     [rbx+0A8h], r12d
0x180002f26  jmp     loc_180002CB0
0x180002f2b  mov     r12d, 5
0x180002f31  mov     r14d, 80004005h
0x180002f37  mov     [rbx+0A8h], r12d
0x180002f3e  jmp     loc_180002CB0
0x180002f43  sub     eax, 2
0x180002f46  jz      loc_180002DFF
0x180002f4c  sub     eax, r15d
0x180002f4f  jz      loc_180002DFF
0x180002f55  cmp     eax, 2
0x180002f58  jz      short loc_180002F65
0x180002f5a  mov     r12d, 6
0x180002f60  jmp     loc_180002E05
0x180002f65  mov     r12d, 4
0x180002f6b  jmp     loc_180002E05
0x180002f70  mov     rax, [rbx+40h]
0x180002f74  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180002f7b  cmp     byte ptr [rax+rdi+1], 0
0x180002f80  lea     rdi, [rdi+1]
0x180002f84  jnz     short loc_180002F7B
0x180002f86  lea     rcx, [rax+rdi]
0x180002f8a  movzx   eax, byte ptr [rax+rdi-1]
0x180002f8f  cmp     al, 2Fh ; '/'
0x180002f91  jz      loc_18000304B
0x180002f97  cmp     al, 5Ch ; '\'
0x180002f99  jz      loc_18000304B
0x180002f9f  mov     byte ptr [rcx], 2Fh ; '/'
0x180002fa2  xor     edx, edx; Val
0x180002fa4  mov     rax, [rbx+40h]
0x180002fa8  lea     rcx, [rsp+380h+var_310]; void *
0x180002fad  mov     r8d, 238h; Size
0x180002fb3  mov     byte ptr [rax+rdi+1], 0
0x180002fb8  call    memset_0
0x180002fbd  xor     edx, edx; Val
0x180002fbf  lea     rcx, [rbp+280h+var_C0]; void *
0x180002fc6  mov     r8d, 68h ; 'h'; Size
0x180002fcc  call    memset_0
0x180002fd1  mov     rdx, [rbx+40h]; char *
0x180002fd5  lea     rcx, [rsp+380h+var_320]; this
0x180002fda  xor     eax, eax
0x180002fdc  mov     [rsp+380h+var_320], rsi
0x180002fe1  mov     [rbp+280h+var_50], rax
0x180002fe8  mov     rax, [rsp+380h+var_330]
0x180002fed  mov     [rsp+380h+var_318], rax
0x180002ff2  xor     eax, eax
0x180002ff4  cmp     [rbx+6Ch], eax
0x180002ff7  mov     [rbp+280h+var_D8], r15d
0x180002ffe  setnz   al
0x180003001  mov     [rbp+280h+var_58], rbx
0x180003008  inc     eax
0x18000300a  mov     [rbp+280h+var_C8], 0
0x180003015  mov     [rbp+280h+var_D4], eax
0x18000301b  mov     [rbp+280h+var_D0], 0
0x180003026  mov     [rbx+0A8h], r15d
0x18000302d  call    ?SendRedirect@CHttpResponse@@QEAAKPEBD@Z; CHttpResponse::SendRedirect(char const *)
0x180003032  test    eax, eax
0x180003034  jz      short loc_18000303E
0x180003036  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000303b  mov     r14d, eax
0x18000303e  mov     rax, [rbx+40h]
0x180003042  mov     byte ptr [rdi+rax], 0
0x180003046  jmp     loc_180002C76
0x18000304b  mov     rcx, rbx; this
0x18000304e  call    ?MapDirToDefaultPage@CHttpRequest@@AEAAHXZ; CHttpRequest::MapDirToDefaultPage(void)
0x180003053  jmp     loc_180002C40
0x180003058  mov     rcx, cs:WPP_GLOBAL_Control
0x18000305f  lea     rax, WPP_GLOBAL_Control
0x180003066  cmp     rcx, rax
0x180003069  jz      short loc_180003090
0x18000306b  test    dword ptr [rcx+1Ch], 1000h
0x180003072  jz      short loc_180003090
0x180003074  mov     rcx, [rcx+10h]
0x180003078  lea     r8, WPP_17616c072cb339da1efa148f0bfe4571_Traceguids
0x18000307f  mov     edx, 0Fh
0x180003084  call    WPP_SF_
0x180003089  lea     rax, WPP_GLOBAL_Control
0x180003090  cmp     [rbx+0DCh], r15d
0x180003097  jnz     short loc_1800030B1
0x180003099  mov     r12d, 7
0x18000309f  mov     r14d, 80004005h
0x1800030a5  mov     [rbx+0A8h], r12d
0x1800030ac  jmp     loc_180002CB0
0x1800030b1  test    [rbx+0A4h], r15b
0x1800030b8  jz      loc_180003141
0x1800030be  mov     rcx, [rbx+80h]; lpFileName
0x1800030c5  test    rcx, rcx
0x1800030c8  jz      short loc_180003141
0x1800030ca  mov     [rsp+380h+hTemplateFile], 0; hTemplateFile
0x1800030d3  xor     r9d, r9d; lpSecurityAttributes
  ... truncated ...
```
