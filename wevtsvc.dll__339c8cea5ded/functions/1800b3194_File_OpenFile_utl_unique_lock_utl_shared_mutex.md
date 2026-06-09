# File::OpenFile(utl::unique_lock<utl::shared_mutex> &)

- ea: `0x1800b3194`
- end: `0x1800b37fa`
- name: `?OpenFile@File@@AEAAXAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `1638`
- prototype: `char __fastcall(File *this)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800b223c`
- `0x1800b29b8`

## callees

- `0x180009260`
- `0x18000a180`
- `0x18000b154`
- `0x18003420c`
- `0x18005ff90`
- `0x180074c10`
- `0x180077ad0`
- `0x18007f4dc`
- `0x180092008`
- `0x180098c50`
- `0x1800b241c`
- `0x1800b3194`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b358c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b358c`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800b3391`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800b33c3`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800b33fa`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800b3391`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800b33c3`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800b33fa`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800b32d3`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800b32d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b32b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b32b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall File::OpenFile(File *this)
{
  const WCHAR *v2; // rcx
  char v3; // r14
  HANDLE FileW; // rax
  int IsCreated; // eax
  bool v6; // di
  HANDLE v7; // r14
  DWORD v8; // r14d
  DWORD LastError; // eax
  __int64 v10; // rdx
  DWORD v11; // r15d
  __int64 v12; // r14
  int v13; // r14d
  unsigned int v14; // r14d
  PVOID *v15; // rcx
  _QWORD v17[2]; // [rsp+40h] [rbp-40h] BYREF
  __int128 pExceptionObject; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+60h] [rbp-20h]
  int v20; // [rsp+68h] [rbp-18h]
  __int64 v21; // [rsp+6Ch] [rbp-14h]
  char v22; // [rsp+74h] [rbp-Ch]
  File *v23; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE v24; // [rsp+D0h] [rbp+50h] BYREF
  HANDLE v25; // [rsp+D8h] [rbp+58h] BYREF

  *((_BYTE *)this + 827) = 0;
  *((_DWORD *)this + 203) = 0;
  *((_QWORD *)this + 97) = -1;
  *((_QWORD *)this + 98) = -1;
  *((_QWORD *)this + 21) = -1;
  *((_QWORD *)this + 102) = 0;
  *((_BYTE *)this + 826) = 0;
  *((_BYTE *)this + 838) = 0;
  *((_QWORD *)this + 96) = -1;
  v2 = (const WCHAR *)*((_QWORD *)this + 85);
  if ( v2 == *((const WCHAR **)this + 86) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 87);
    }
    pExceptionObject = 0;
    v19 = 0;
    v20 = 87;
    v21 = 0x144FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v3 = *((_BYTE *)this + 825) & 4;
  FileW = CreateFileW(v2, v3 != 0 ? 0x80000000 : -1073741824, 1u, 0, 3u, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 672, FileW);
  if ( (unsigned __int64)(*((_QWORD *)this + 84) + 1LL) <= 1 )
  {
    LastError = GetLastError();
    if ( v3 )
    {
      v14 = LastError;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
          LastError,
          *((_QWORD *)this + 85));
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !v14 )
        v14 = 1287;
      if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x8000) != 0 && *((_BYTE *)v15 + 25) >= 2u )
        WPP_SF_d(v15[2], 25, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v14);
      pExceptionObject = 0;
      v19 = 0;
      v20 = v14;
      v21 = 0x1E8FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v11 = LastError;
    *((_BYTE *)this + 832) = 1;
    if ( (*((_BYTE *)this + 825) & 8) != 0
      || !(unsigned __int8)AreAnyRestrictionsEnabled(512, v10)
      || (v12 = *((_QWORD *)this + 89),
          v17[0] = v12,
          v17[1] = (*((_QWORD *)this + 90) - v12) >> 1,
          LOBYTE(IsCreated) = IsCoreChannel(v17),
          (_BYTE)IsCreated) )
    {
      if ( (*((_BYTE *)this + 825) & 8) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            &WPP_d3d936efbc913e3641017ad303784371_Traceguids,
            *((_QWORD *)this + 85));
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
          v11,
          *((_QWORD *)this + 85));
      }
      IsCreated = File::EnsureFileIsCreated(this);
      v13 = IsCreated;
      if ( IsCreated )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
            IsCreated,
            *((_QWORD *)this + 85));
        }
        *(_QWORD *)&pExceptionObject = &byte_1800EC961;
        *((_QWORD *)&pExceptionObject + 1) = 0;
        v19 = 0;
        v20 = v13;
        v21 = -1;
        v22 = 0;
        throw (EvtException *)&pExceptionObject;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      LOBYTE(IsCreated) = WPP_SF_S(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            20,
                            &WPP_d3d936efbc913e3641017ad303784371_Traceguids,
                            v12);
    }
  }
  else
  {
    if ( GetFileType(*((HANDLE *)this + 84)) != 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 4300);
      }
      pExceptionObject = 0;
      v19 = 0;
      v20 = 4300;
      v21 = 0x157FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v23 = this;
    LOBYTE(IsCreated) = File::OpenFile_::_11_::_lambda_1_::operator()(&v23);
    if ( (*((_BYTE *)this + 136) & 1) != 0 )
    {
      v6 = (*((_BYTE *)this + 825) & 0x10) == 0;
      if ( v3 && (*((_BYTE *)this + 825) & 0x10) == 0 )
      {
        v7 = ReOpenFile(*((HANDLE *)this + 84), 0x80000000, 3u, 0);
        v17[0] = v7;
        if ( (unsigned __int64)v7 + 1 <= 1 )
        {
          v6 = 0;
          *((_BYTE *)this + 825) |= 0x10u;
        }
        else
        {
          tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 672, 0);
          v25 = ReOpenFile(v7, 0xC0000000, 1u, 0);
          if ( (unsigned __int64)v25 + 1 <= 1 )
          {
            v24 = ReOpenFile(v7, 0x80000000, 1u, 0);
            if ( (unsigned __int64)v24 + 1 <= 1 )
            {
              v8 = GetLastError();
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  18,
                  (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
                  v8,
                  *((_QWORD *)this + 85));
              }
              *(_QWORD *)&pExceptionObject = &byte_1800EC961;
              *((_QWORD *)&pExceptionObject + 1) = 0;
              v19 = 0;
              v20 = v8;
              v21 = -1;
              v22 = 0;
              throw (EvtException *)&pExceptionObject;
            }
            tlx::unique_any<tlx::file_handle_traits>::operator=((char *)this + 672, &v24);
            v6 = 0;
            *((_BYTE *)this + 825) |= 0x10u;
            File::OpenFile_::_11_::_lambda_1_::operator()(&v23);
            tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v24);
          }
          else
          {
            tlx::unique_any<tlx::file_handle_traits>::operator=((char *)this + 672, &v25);
            File::OpenFile_::_11_::_lambda_1_::operator()(&v23);
          }
          tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v25);
        }
        tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(v17);
      }
      LOBYTE(IsCreated) = File::Recover(this);
      if ( !v6 )
      {
        LOBYTE(IsCreated) = *((_BYTE *)this + 824);
        if ( (IsCreated & 0xE) == 0 )
        {
          if ( (_BYTE)IsCreated )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 1500);
            }
            pExceptionObject = 0;
            v19 = 0;
            v20 = 1500;
            v21 = 0x1BBFFFFFFFFLL;
            throw (EvtException *)&pExceptionObject;
          }
        }
      }
    }
    *((_BYTE *)this + 829) = 1;
  }
  return IsCreated;
}

```

## disassembly

```asm
0x1800b3194  mov     [rsp-38h+arg_8], rbx
0x1800b3199  push    rbp
0x1800b319a  push    rsi
0x1800b319b  push    rdi
0x1800b319c  push    r12
0x1800b319e  push    r13
0x1800b31a0  push    r14
0x1800b31a2  push    r15
0x1800b31a4  mov     rbp, rsp
0x1800b31a7  sub     rsp, 80h
0x1800b31ae  mov     r12, rdx
0x1800b31b1  mov     rbx, rcx
0x1800b31b4  xor     r13d, r13d
0x1800b31b7  mov     [rcx+33Bh], r13b
0x1800b31be  mov     [rcx+32Ch], r13d
0x1800b31c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b31c9  mov     [rcx+308h], rax
0x1800b31d0  mov     [rcx+310h], rax
0x1800b31d7  mov     [rcx+0A8h], rax
0x1800b31de  mov     [rcx+330h], r13
0x1800b31e5  mov     [rcx+33Ah], r13b
0x1800b31ec  mov     [rcx+346h], r13b
0x1800b31f3  mov     [rcx+300h], rax
0x1800b31fa  mov     rcx, [rcx+2A8h]; lpFileName
0x1800b3201  cmp     rcx, [rbx+2B0h]
0x1800b3208  jnz     short loc_1800B3274
0x1800b320a  lea     rdi, WPP_GLOBAL_Control
0x1800b3211  lea     ebx, [rax+58h]
0x1800b3214  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b321b  cmp     rcx, rdi
0x1800b321e  jz      short loc_1800B3246
0x1800b3220  mov     esi, 8000h
0x1800b3225  test    [rcx+1Ch], esi
0x1800b3228  jz      short loc_1800B3246
0x1800b322a  cmp     byte ptr [rcx+19h], 2
0x1800b322e  jb      short loc_1800B3246
0x1800b3230  lea     edx, [rax+0Dh]
0x1800b3233  mov     r9d, ebx
0x1800b3236  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b323d  mov     rcx, [rcx+10h]
0x1800b3241  call    WPP_SF_d
0x1800b3246  xorps   xmm0, xmm0
0x1800b3249  movdqu  [rbp+pExceptionObject], xmm0
0x1800b324e  mov     [rbp+var_20], r13
0x1800b3252  mov     [rbp+var_18], ebx
0x1800b3255  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x1800b325c  mov     dword ptr [rbp+var_14+4], 144h
0x1800b3263  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b326a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b326e  call    _CxxThrowException_0
0x1800b3274  mov     r14b, [rbx+339h]
0x1800b327b  and     r14b, 4
0x1800b327f  lea     rsi, [rbx+2A0h]
0x1800b3286  mov     al, r14b
0x1800b3289  neg     al
0x1800b328b  sbb     edx, edx
0x1800b328d  mov     eax, 0C0000000h
0x1800b3292  and     edx, eax
0x1800b3294  add     edx, eax; dwDesiredAccess
0x1800b3296  mov     [rsp+80h+hTemplateFile], r13; hTemplateFile
0x1800b329b  mov     [rsp+80h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800b32a0  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1800b32a8  xor     r9d, r9d; lpSecurityAttributes
0x1800b32ab  lea     r15d, [r9+1]
0x1800b32af  mov     r8d, r15d; dwShareMode
0x1800b32b2  call    cs:__imp_CreateFileW
0x1800b32b8  mov     rdx, rax
0x1800b32bb  mov     rcx, rsi
0x1800b32be  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800b32c3  mov     rcx, [rsi]; hFile
0x1800b32c6  lea     rax, [rcx+1]
0x1800b32ca  cmp     rax, r15
0x1800b32cd  jbe     loc_1800B358C
0x1800b32d3  call    cs:__imp_GetFileType
0x1800b32d9  cmp     eax, r15d
0x1800b32dc  jz      short loc_1800B334B
0x1800b32de  lea     rdi, WPP_GLOBAL_Control
0x1800b32e5  mov     ebx, 10CCh
0x1800b32ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b32f1  cmp     rcx, rdi
0x1800b32f4  jz      short loc_1800B331D
0x1800b32f6  mov     esi, 8000h
0x1800b32fb  test    [rcx+1Ch], esi
0x1800b32fe  jz      short loc_1800B331D
0x1800b3300  cmp     byte ptr [rcx+19h], 2
0x1800b3304  jb      short loc_1800B331D
0x1800b3306  lea     edx, [r15+0Ch]
0x1800b330a  mov     r9d, ebx
0x1800b330d  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b3314  mov     rcx, [rcx+10h]
0x1800b3318  call    WPP_SF_d
0x1800b331d  xorps   xmm0, xmm0
0x1800b3320  movdqu  [rbp+pExceptionObject], xmm0
0x1800b3325  mov     [rbp+var_20], r13
0x1800b3329  mov     [rbp+var_18], ebx
0x1800b332c  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x1800b3333  mov     dword ptr [rbp+var_14+4], 157h
0x1800b333a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b3341  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b3345  call    _CxxThrowException_0
0x1800b334b  mov     [rbp+arg_0], rbx
0x1800b334f  lea     rcx, [rbp+arg_0]
0x1800b3353  call    _File__OpenFile____11____lambda_1___operator__
0x1800b3358  test    [rbx+88h], r15b
0x1800b335f  jz      loc_1800B356A
0x1800b3365  mov     al, [rbx+339h]
0x1800b336b  and     al, 10h
0x1800b336d  setz    dil
0x1800b3371  test    r14b, r14b
0x1800b3374  jz      loc_1800B34DB
0x1800b337a  test    al, al
0x1800b337c  jnz     loc_1800B34DB
0x1800b3382  xor     r9d, r9d; dwFlagsAndAttributes
0x1800b3385  mov     edx, 80000000h; dwDesiredAccess
0x1800b338a  lea     r8d, [r9+3]; dwShareMode
0x1800b338e  mov     rcx, [rsi]; hOriginalFile
0x1800b3391  call    cs:__imp_ReOpenFile
0x1800b3397  mov     r14, rax
0x1800b339a  mov     [rbp+var_40], rax
0x1800b339e  lea     rcx, [rax+1]
0x1800b33a2  cmp     rcx, r15
0x1800b33a5  jbe     loc_1800B34C8
0x1800b33ab  xor     edx, edx
0x1800b33ad  mov     rcx, rsi
0x1800b33b0  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800b33b5  xor     r9d, r9d; dwFlagsAndAttributes
0x1800b33b8  mov     r8d, r15d; dwShareMode
0x1800b33bb  mov     edx, 0C0000000h; dwDesiredAccess
0x1800b33c0  mov     rcx, r14; hOriginalFile
0x1800b33c3  call    cs:__imp_ReOpenFile
0x1800b33c9  mov     [rbp+arg_18], rax
0x1800b33cd  inc     rax
0x1800b33d0  cmp     rax, r15
0x1800b33d3  jbe     short loc_1800B33EC
0x1800b33d5  lea     rdx, [rbp+arg_18]
0x1800b33d9  mov     rcx, rsi
0x1800b33dc  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800b33e1  lea     rcx, [rbp+arg_0]
0x1800b33e5  call    _File__OpenFile____11____lambda_1___operator__
0x1800b33ea  jmp     short loc_1800B3436
0x1800b33ec  xor     r9d, r9d; dwFlagsAndAttributes
0x1800b33ef  mov     r8d, r15d; dwShareMode
0x1800b33f2  mov     edx, 80000000h; dwDesiredAccess
0x1800b33f7  mov     rcx, r14; hOriginalFile
0x1800b33fa  call    cs:__imp_ReOpenFile
0x1800b3400  mov     [rbp+arg_10], rax
0x1800b3404  inc     rax
0x1800b3407  cmp     rax, r15
0x1800b340a  jbe     short loc_1800B3444
0x1800b340c  lea     rdx, [rbp+arg_10]
0x1800b3410  mov     rcx, rsi
0x1800b3413  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800b3418  mov     dil, r13b
0x1800b341b  or      byte ptr [rbx+339h], 10h
0x1800b3422  lea     rcx, [rbp+arg_0]
0x1800b3426  call    _File__OpenFile____11____lambda_1___operator__
0x1800b342b  nop
0x1800b342c  lea     rcx, [rbp+arg_10]
0x1800b3430  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b3435  nop
0x1800b3436  lea     rcx, [rbp+arg_18]
0x1800b343a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b343f  jmp     loc_1800B34D2
0x1800b3444  call    cs:__imp_GetLastError
0x1800b344a  mov     r14d, eax
0x1800b344d  lea     rdi, WPP_GLOBAL_Control
0x1800b3454  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b345b  cmp     rcx, rdi
0x1800b345e  jz      short loc_1800B3494
0x1800b3460  mov     esi, 8000h
0x1800b3465  test    [rcx+1Ch], esi
0x1800b3468  jz      short loc_1800B3494
0x1800b346a  cmp     byte ptr [rcx+19h], 2
0x1800b346e  jb      short loc_1800B3494
0x1800b3470  mov     edx, 12h
0x1800b3475  mov     rax, [rbx+2A8h]
0x1800b347c  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x1800b3481  mov     r9d, r14d
0x1800b3484  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b348b  mov     rcx, [rcx+10h]
0x1800b348f  call    WPP_SF_dS
0x1800b3494  lea     rax, byte_1800EC961
0x1800b349b  mov     qword ptr [rbp+pExceptionObject], rax
0x1800b349f  mov     qword ptr [rbp+pExceptionObject+8], r13
0x1800b34a3  mov     [rbp+var_20], r13
0x1800b34a7  mov     [rbp+var_18], r14d
0x1800b34ab  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800b34b3  mov     [rbp+var_C], r13b
0x1800b34b7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b34be  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b34c2  call    _CxxThrowException_0
0x1800b34c8  mov     dil, r13b
0x1800b34cb  or      byte ptr [rbx+339h], 10h
0x1800b34d2  lea     rcx, [rbp+var_40]
0x1800b34d6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b34db  mov     r8, r12
0x1800b34de  mov     dl, dil
0x1800b34e1  mov     rcx, rbx; this
0x1800b34e4  call    ?Recover@File@@AEAAX_NAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::Recover(bool,utl::unique_lock<utl::shared_mutex> &)
0x1800b34e9  test    dil, dil
0x1800b34ec  jnz     short loc_1800B356A
0x1800b34ee  mov     al, [rbx+338h]
0x1800b34f4  test    al, 0Eh
0x1800b34f6  jnz     short loc_1800B356A
0x1800b34f8  test    al, al
0x1800b34fa  jz      short loc_1800B356A
0x1800b34fc  lea     rdi, WPP_GLOBAL_Control
0x1800b3503  mov     ebx, 5DCh
0x1800b3508  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b350f  cmp     rcx, rdi
0x1800b3512  jz      short loc_1800B353C
0x1800b3514  mov     esi, 8000h
0x1800b3519  test    [rcx+1Ch], esi
0x1800b351c  jz      short loc_1800B353C
0x1800b351e  cmp     byte ptr [rcx+19h], 2
0x1800b3522  jb      short loc_1800B353C
0x1800b3524  mov     edx, 13h
0x1800b3529  mov     r9d, ebx
0x1800b352c  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b3533  mov     rcx, [rcx+10h]
0x1800b3537  call    WPP_SF_d
0x1800b353c  xorps   xmm0, xmm0
0x1800b353f  movdqu  [rbp+pExceptionObject], xmm0
0x1800b3544  mov     [rbp+var_20], r13
0x1800b3548  mov     [rbp+var_18], ebx
0x1800b354b  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x1800b3552  mov     dword ptr [rbp+var_14+4], 1BBh
0x1800b3559  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800b3560  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800b3564  call    _CxxThrowException_0
0x1800b356a  mov     [rbx+33Dh], r15b
0x1800b3571  mov     rbx, [rsp+80h+arg_8]
0x1800b3579  add     rsp, 80h
0x1800b3580  pop     r15
0x1800b3582  pop     r14
0x1800b3584  pop     r13
0x1800b3586  pop     r12
0x1800b3588  pop     rdi
0x1800b3589  pop     rsi
0x1800b358a  pop     rbp
0x1800b358b  retn
0x1800b358c  call    cs:__imp_GetLastError
0x1800b3592  test    r14b, r14b
0x1800b3595  jnz     loc_1800B3746
0x1800b359b  mov     r15d, eax
0x1800b359e  mov     byte ptr [rbx+340h], 1
0x1800b35a5  test    byte ptr [rbx+339h], 8
0x1800b35ac  jnz     loc_1800B3635
0x1800b35b2  mov     ecx, 200h
0x1800b35b7  call    ?AreAnyRestrictionsEnabled@@YA_NW4FeatureRestrictions@@@Z; AreAnyRestrictionsEnabled(FeatureRestrictions)
0x1800b35bc  test    al, al
0x1800b35be  jz      short loc_1800B3635
0x1800b35c0  mov     r14, [rbx+2C8h]
0x1800b35c7  mov     [rbp+var_40], r14
0x1800b35cb  mov     rax, [rbx+2D0h]
0x1800b35d2  sub     rax, r14
0x1800b35d5  sar     rax, 1
0x1800b35d8  mov     [rbp+var_38], rax
0x1800b35dc  lea     rcx, [rbp+var_40]
0x1800b35e0  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1800b35e5  test    al, al
0x1800b35e7  jnz     short loc_1800B3635
0x1800b35e9  lea     rdi, WPP_GLOBAL_Control
0x1800b35f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b35f7  cmp     rcx, rdi
0x1800b35fa  jz      loc_1800B3571
0x1800b3600  mov     esi, 8000h
0x1800b3605  test    [rcx+1Ch], esi
0x1800b3608  jz      loc_1800B3571
0x1800b360e  cmp     byte ptr [rcx+19h], 4
0x1800b3612  jb      loc_1800B3571
0x1800b3618  mov     edx, 14h
0x1800b361d  mov     r9, r14
0x1800b3620  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b3627  mov     rcx, [rcx+10h]
0x1800b362b  call    WPP_SF_S
0x1800b3630  jmp     loc_1800B3571
0x1800b3635  mov     esi, 8000h
0x1800b363a  test    byte ptr [rbx+339h], 8
0x1800b3641  jnz     short loc_1800B3687
0x1800b3643  lea     rdi, WPP_GLOBAL_Control
0x1800b364a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3651  cmp     rcx, rdi
0x1800b3654  jz      short loc_1800B36C1
0x1800b3656  test    [rcx+1Ch], esi
0x1800b3659  jz      short loc_1800B36C1
0x1800b365b  cmp     byte ptr [rcx+19h], 4
0x1800b365f  jb      short loc_1800B36C1
0x1800b3661  mov     edx, 15h
0x1800b3666  mov     rax, [rbx+2A8h]
0x1800b366d  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x1800b3672  mov     r9d, r15d
0x1800b3675  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800b367c  mov     rcx, [rcx+10h]
0x1800b3680  call    WPP_SF_dS
0x1800b3685  jmp     short loc_1800B36C1
0x1800b3687  lea     rdi, WPP_GLOBAL_Control
0x1800b368e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b3695  cmp     rcx, rdi
0x1800b3698  jz      short loc_1800B36C1
  ... truncated ...
```
