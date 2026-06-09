# CThemeManagerAPIRequest::Execute_ProcessLoadTheme(CAPIDispatchSync *)

- ea: `0x18000aefc`
- end: `0x18000b178`
- name: `?Execute_ProcessLoadTheme@CThemeManagerAPIRequest@@AEAAJPEAVCAPIDispatchSync@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(CThemeManagerAPIRequest *__hidden this, struct CAPIDispatchSync *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180002270`

## callees

- `0x180002940`
- `0x180002e40`
- `0x180003088`
- `0x180004430`
- `0x1800045a0`
- `0x18000674c`
- `0x180006890`
- `0x1800069f4`
- `0x18000aefc`
- `0x18000cfa8`
- `0x18000d094`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af48`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b095`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000b095`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000afec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000afec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b117`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b125`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b031`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b117`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b125`

## pseudocode

```c
__int64 __fastcall CThemeManagerAPIRequest::Execute_ProcessLoadTheme(
        CThemeManagerAPIRequest *this,
        struct CAPIDispatchSync *a2)
{
  struct CLoaderProcess *v3; // rsi
  void *v4; // r12
  void *v6; // r14
  void *v7; // rcx
  int Error; // ebx
  int LoaderProcess; // eax
  const unsigned __int16 *v10; // r9
  unsigned int v11; // r8d
  const unsigned __int16 *v12; // rdx
  BOOL v13; // eax
  unsigned __int16 *v14; // r8
  struct LOADTHEME_STRINGS *v15; // r14
  DWORD v16; // eax
  DWORD v17; // eax
  CCriticalSection *v18; // rcx
  int v19; // eax
  struct CLoaderProcess *v20; // rsi
  void *v21; // rcx
  void *v22; // r14
  unsigned int bAlertable; // [rsp+20h] [rbp-30h]
  const unsigned __int16 *v25; // [rsp+28h] [rbp-28h]
  unsigned int v26; // [rsp+30h] [rbp-20h]
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  struct CLoaderProcess *v28; // [rsp+90h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+48h] BYREF
  struct LOADTHEME_STRINGS *lpMem; // [rsp+A0h] [rbp+50h] BYREF
  void *v31; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  v28 = 0;
  v31 = 0;
  CCriticalSection::Acquire(CThemeManagerAPIRequest::s_pLock);
  v6 = *(void **)(*((_QWORD *)this + 17) + 96LL);
  if ( a2 && (v7 = (void *)*((_QWORD *)a2 + 6)) != 0 && WaitForSingleObject(v7, 0) != 258 )
  {
    Error = -1073741769;
  }
  else
  {
    LoaderProcess = CThemeManagerSessionData::GetLoaderProcess(*((CThemeManagerSessionData **)this + 19), &v28);
    v3 = v28;
    Error = LoaderProcess;
    if ( LoaderProcess >= 0 )
    {
      if ( *(_QWORD *)v28 )
      {
        Error = -1073741790;
      }
      else
      {
        Error = CThemeManagerAPIRequest::ImpersonateClientIfRequired(this);
        if ( Error >= 0 )
        {
          v10 = (const unsigned __int16 *)*((_QWORD *)this + 11);
          v11 = *((_DWORD *)this + 20);
          v12 = (const unsigned __int16 *)*((_QWORD *)this + 9);
          v26 = *((_DWORD *)this + 28);
          v25 = (const unsigned __int16 *)*((_QWORD *)this + 13);
          bAlertable = *((_DWORD *)this + 24);
          lpMem = 0;
          Error = _AllocAndMapThemeStrings(v6, v12, v11, v10, bAlertable, v25, v26, &lpMem);
          if ( Error >= 0 )
          {
            TokenHandle = 0;
            v13 = OpenProcessToken(v6, 0xFu, &TokenHandle);
            v15 = lpMem;
            if ( v13 )
            {
              Error = CLoaderProcess::Create(
                        v3,
                        TokenHandle,
                        v14,
                        *(const unsigned __int16 **)lpMem,
                        *((LPCWSTR *)lpMem + 1),
                        *((LPCWSTR *)lpMem + 2),
                        *((_DWORD *)this + 29),
                        &v31);
              CloseHandle(TokenHandle);
              v4 = v31;
            }
            else
            {
              Error = CStatusCode::StatusCodeOfLastError();
            }
            _FreeThemeStrings(v15);
          }
        }
      }
    }
  }
  CCriticalSection::Release(CThemeManagerAPIRequest::s_pLock);
  *((_DWORD *)this + 18) = -2147467259;
  if ( Error < 0 )
  {
    *((_DWORD *)this + 18) = Error | 0x10000000;
  }
  else
  {
    Handles[0] = v4;
    Handles[1] = CAPIDispatchSync::GetServiceStoppingEvent(a2);
    Error = -1073741248;
    v16 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xEA60u, 0);
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 == 257 )
        {
          Error = 258;
          *((_DWORD *)v3 + 20) = 268435714;
        }
      }
      else
      {
        Error = -1073741769;
      }
    }
    else
    {
      Error = 0;
    }
    v18 = CThemeManagerAPIRequest::s_pLock;
    *((_DWORD *)this + 18) = Error | 0x10000000;
    CCriticalSection::Acquire(v18);
    v19 = CThemeManagerSessionData::GetLoaderProcess(*((CThemeManagerSessionData **)this + 19), &v28);
    if ( v19 < 0 )
    {
      Error = v19;
      *((_DWORD *)this + 18) = v19 | 0x10000000;
    }
    else
    {
      v20 = v28;
      v21 = (void *)*((_QWORD *)v28 + 8);
      v22 = (void *)*((_QWORD *)v28 + 9);
      *((_QWORD *)v28 + 8) = 0;
      *((_QWORD *)v20 + 9) = 0;
      if ( Error >= 0 )
        *((_DWORD *)this + 18) = *((_DWORD *)v20 + 20);
      if ( v21 )
        CloseHandle(v21);
      if ( v22 )
        CloseHandle(v22);
      if ( Error != 258 )
        CLoaderProcess::Clear(v20, 1);
    }
    CCriticalSection::Release(CThemeManagerAPIRequest::s_pLock);
  }
  *((_DWORD *)this + 6) = 7340104;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000aefc  push    rbp
0x18000aefe  push    rbx
0x18000aeff  push    rsi
0x18000af00  push    rdi
0x18000af01  push    r12
0x18000af03  push    r14
0x18000af05  push    r15
0x18000af07  mov     rbp, rsp
0x18000af0a  sub     rsp, 50h
0x18000af0e  mov     rdi, rcx
0x18000af11  xor     esi, esi
0x18000af13  mov     rcx, cs:?s_pLock@CThemeManagerAPIRequest@@0PEAVCCriticalSection@@EA; this
0x18000af1a  xor     r12d, r12d
0x18000af1d  mov     [rbp+arg_0], rsi
0x18000af21  mov     r15, rdx
0x18000af24  mov     [rbp+arg_18], r12
0x18000af28  call    ?Acquire@CCriticalSection@@QEAAXXZ; CCriticalSection::Acquire(void)
0x18000af2d  mov     rax, [rdi+88h]
0x18000af34  mov     r14, [rax+60h]
0x18000af38  test    r15, r15
0x18000af3b  jz      short loc_18000AF5F
0x18000af3d  mov     rcx, [r15+30h]; hHandle
0x18000af41  test    rcx, rcx
0x18000af44  jz      short loc_18000AF5F
0x18000af46  xor     edx, edx; dwMilliseconds
0x18000af48  call    cs:__imp_WaitForSingleObject
0x18000af4e  cmp     eax, 102h
0x18000af53  jz      short loc_18000AF5F
0x18000af55  mov     ebx, 0C0000037h
0x18000af5a  jmp     loc_18000B04C
0x18000af5f  mov     rcx, [rdi+98h]; this
0x18000af66  lea     rdx, [rbp+arg_0]; struct CLoaderProcess **
0x18000af6a  call    ?GetLoaderProcess@CThemeManagerSessionData@@QEAAJPEAPEAVCLoaderProcess@@@Z; CThemeManagerSessionData::GetLoaderProcess(CLoaderProcess * *)
0x18000af6f  mov     rsi, [rbp+arg_0]
0x18000af73  mov     ebx, eax
0x18000af75  test    eax, eax
0x18000af77  js      loc_18000B04C
0x18000af7d  cmp     [rsi], r12
0x18000af80  jz      short loc_18000AF8C
0x18000af82  mov     ebx, 0C0000022h
0x18000af87  jmp     loc_18000B04C
0x18000af8c  mov     rcx, rdi; this
0x18000af8f  call    ?ImpersonateClientIfRequired@CThemeManagerAPIRequest@@AEAAJXZ; CThemeManagerAPIRequest::ImpersonateClientIfRequired(void)
0x18000af94  mov     ebx, eax
0x18000af96  test    eax, eax
0x18000af98  js      loc_18000B04C
0x18000af9e  mov     r9, [rdi+58h]; unsigned __int16 *
0x18000afa2  lea     rax, [rbp+lpMem]
0x18000afa6  mov     r8d, [rdi+50h]; unsigned int
0x18000afaa  mov     rcx, r14; hProcess
0x18000afad  mov     rdx, [rdi+48h]; unsigned __int16 *
0x18000afb1  mov     [rsp+50h+var_18], rax; struct LOADTHEME_STRINGS **
0x18000afb6  mov     eax, [rdi+70h]
0x18000afb9  mov     [rsp+50h+var_20], eax; unsigned int
0x18000afbd  mov     rax, [rdi+68h]
0x18000afc1  mov     [rsp+50h+var_28], rax; unsigned __int16 *
0x18000afc6  mov     eax, [rdi+60h]
0x18000afc9  mov     [rsp+50h+bAlertable], eax; unsigned int
0x18000afcd  mov     [rbp+lpMem], r12
0x18000afd1  call    ?_AllocAndMapThemeStrings@@YAJPEAXPEBGI1I1IPEAPEAULOADTHEME_STRINGS@@@Z; _AllocAndMapThemeStrings(void *,ushort const *,uint,ushort const *,uint,ushort const *,uint,LOADTHEME_STRINGS * *)
0x18000afd6  mov     ebx, eax
0x18000afd8  test    eax, eax
0x18000afda  js      short loc_18000B04C
0x18000afdc  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000afe0  mov     [rbp+TokenHandle], r12
0x18000afe4  mov     edx, 0Fh; DesiredAccess
0x18000afe9  mov     rcx, r14; ProcessHandle
0x18000afec  call    cs:__imp_OpenProcessToken
0x18000aff2  mov     r14, [rbp+lpMem]
0x18000aff6  test    eax, eax
0x18000aff8  jz      short loc_18000B03D
0x18000affa  mov     r9, [r14]; unsigned __int16 *
0x18000affd  lea     rax, [rbp+arg_18]
0x18000b001  mov     rdx, [rbp+TokenHandle]; hToken
0x18000b005  mov     rcx, rsi; this
0x18000b008  mov     [rsp+50h+var_18], rax; void **
0x18000b00d  mov     eax, [rdi+74h]
0x18000b010  mov     [rsp+50h+var_20], eax; unsigned int
0x18000b014  mov     rax, [r14+10h]
0x18000b018  mov     [rsp+50h+var_28], rax; LPCWSTR
0x18000b01d  mov     rax, [r14+8]
0x18000b021  mov     qword ptr [rsp+50h+bAlertable], rax; lpString
0x18000b026  call    ?Create@CLoaderProcess@@QEAAJPEAXPEAGPEBG22KPEAPEAX@Z; CLoaderProcess::Create(void *,ushort *,ushort const *,ushort const *,ushort const *,ulong,void * *)
0x18000b02b  mov     rcx, [rbp+TokenHandle]; hObject
0x18000b02f  mov     ebx, eax
0x18000b031  call    cs:__imp_CloseHandle
0x18000b037  mov     r12, [rbp+arg_18]
0x18000b03b  jmp     short loc_18000B044
0x18000b03d  call    ?StatusCodeOfLastError@CStatusCode@@SAJXZ; CStatusCode::StatusCodeOfLastError(void)
0x18000b042  mov     ebx, eax
0x18000b044  mov     rcx, r14; lpMem
0x18000b047  call    ?_FreeThemeStrings@@YAXPEAULOADTHEME_STRINGS@@@Z; _FreeThemeStrings(LOADTHEME_STRINGS *)
0x18000b04c  mov     rcx, cs:?s_pLock@CThemeManagerAPIRequest@@0PEAVCCriticalSection@@EA; this
0x18000b053  call    ?Release@CCriticalSection@@QEAAXXZ; CCriticalSection::Release(void)
0x18000b058  mov     dword ptr [rdi+48h], 80004005h
0x18000b05f  test    ebx, ebx
0x18000b061  js      loc_18000B157
0x18000b067  mov     rcx, r15; struct CAPIDispatchSync *
0x18000b06a  mov     [rbp+Handles], r12
0x18000b06e  call    ?GetServiceStoppingEvent@CAPIDispatchSync@@SAPEAXPEAV1@@Z; CAPIDispatchSync::GetServiceStoppingEvent(CAPIDispatchSync *)
0x18000b073  xor     r8d, r8d; bWaitAll
0x18000b076  mov     [rbp+var_8], rax
0x18000b07a  mov     r9d, 0EA60h; dwMilliseconds
0x18000b080  mov     [rsp+50h+bAlertable], 0; bAlertable
0x18000b088  lea     rdx, [rbp+Handles]; lpHandles
0x18000b08c  mov     ebx, 0C0000240h
0x18000b091  lea     ecx, [r8+2]; nCount
0x18000b095  call    cs:__imp_WaitForMultipleObjectsEx
0x18000b09b  test    eax, eax
0x18000b09d  jz      short loc_18000B0BE
0x18000b09f  sub     eax, 1
0x18000b0a2  jz      short loc_18000B0B7
0x18000b0a4  cmp     eax, 101h
0x18000b0a9  jnz     short loc_18000B0C0
0x18000b0ab  lea     ebx, [rax+1]
0x18000b0ae  mov     dword ptr [rsi+50h], 10000102h
0x18000b0b5  jmp     short loc_18000B0C0
0x18000b0b7  mov     ebx, 0C0000037h
0x18000b0bc  jmp     short loc_18000B0C0
0x18000b0be  xor     ebx, ebx
0x18000b0c0  mov     rcx, cs:?s_pLock@CThemeManagerAPIRequest@@0PEAVCCriticalSection@@EA; this
0x18000b0c7  mov     eax, ebx
0x18000b0c9  mov     esi, 10000000h
0x18000b0ce  or      eax, esi
0x18000b0d0  mov     [rdi+48h], eax
0x18000b0d3  call    ?Acquire@CCriticalSection@@QEAAXXZ; CCriticalSection::Acquire(void)
0x18000b0d8  mov     rcx, [rdi+98h]; this
0x18000b0df  lea     rdx, [rbp+arg_0]; struct CLoaderProcess **
0x18000b0e3  call    ?GetLoaderProcess@CThemeManagerSessionData@@QEAAJPEAPEAVCLoaderProcess@@@Z; CThemeManagerSessionData::GetLoaderProcess(CLoaderProcess * *)
0x18000b0e8  test    eax, eax
0x18000b0ea  js      short loc_18000B142
0x18000b0ec  mov     rsi, [rbp+arg_0]
0x18000b0f0  mov     rcx, [rsi+40h]; hObject
0x18000b0f4  mov     r14, [rsi+48h]
0x18000b0f8  mov     qword ptr [rsi+40h], 0
0x18000b100  mov     qword ptr [rsi+48h], 0
0x18000b108  test    ebx, ebx
0x18000b10a  js      short loc_18000B112
0x18000b10c  mov     eax, [rsi+50h]
0x18000b10f  mov     [rdi+48h], eax
0x18000b112  test    rcx, rcx
0x18000b115  jz      short loc_18000B11D
0x18000b117  call    cs:__imp_CloseHandle
0x18000b11d  test    r14, r14
0x18000b120  jz      short loc_18000B12B
0x18000b122  mov     rcx, r14; hObject
0x18000b125  call    cs:__imp_CloseHandle
0x18000b12b  cmp     ebx, 102h
0x18000b131  jz      short loc_18000B149
0x18000b133  mov     edx, 1; int
0x18000b138  mov     rcx, rsi; this
0x18000b13b  call    ?Clear@CLoaderProcess@@QEAAXH@Z; CLoaderProcess::Clear(int)
0x18000b140  jmp     short loc_18000B149
0x18000b142  mov     ebx, eax
0x18000b144  or      eax, esi
0x18000b146  mov     [rdi+48h], eax
0x18000b149  mov     rcx, cs:?s_pLock@CThemeManagerAPIRequest@@0PEAVCCriticalSection@@EA; this
0x18000b150  call    ?Release@CCriticalSection@@QEAAXXZ; CCriticalSection::Release(void)
0x18000b155  jmp     short loc_18000B160
0x18000b157  mov     eax, ebx
0x18000b159  bts     eax, 1Ch
0x18000b15d  mov     [rdi+48h], eax
0x18000b160  mov     dword ptr [rdi+18h], 700048h
0x18000b167  mov     eax, ebx
0x18000b169  add     rsp, 50h
0x18000b16d  pop     r15
0x18000b16f  pop     r14
0x18000b171  pop     r12
0x18000b173  pop     rdi
0x18000b174  pop     rsi
0x18000b175  pop     rbx
0x18000b176  pop     rbp
0x18000b177  retn
```
