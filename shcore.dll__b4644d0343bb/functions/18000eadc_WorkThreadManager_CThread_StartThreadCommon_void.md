# WorkThreadManager::CThread::StartThreadCommon(void)

- ea: `0x18000eadc`
- end: `0x18000ecfd`
- name: `?StartThreadCommon@CThread@WorkThreadManager@@QEAAJXZ`
- size: `545`
- prototype: `__int64 __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e834`
- `0x18000e988`

## callees

- `0x18000eadc`
- `0x18000f784`
- `0x180053bd8`
- `0x180054368`
- `0x18005bb30`
- `0x180068d9c`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eca3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eca3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ec85`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ec85`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000eb04`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000eb04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000eb39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecab`

## string_xrefs

- `0x18000eb49`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000eb6b`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WorkThreadManager::CThread::StartThreadCommon(
        WorkThreadManager::CThread *this,
        __int64 a2,
        __int64 a3)
{
  int inited; // eax
  int LastErrorFailHr; // ebx
  wil::details *v6; // rcx
  HANDLE Event; // rbp
  wil::details *v8; // rsi
  DWORD LastError; // ebx
  void *v10; // rdx
  __int64 v11; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rcx
  HMODULE v21; // rsi
  DWORD v22; // ebx
  int v23; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  LOBYTE(a2) = 0;
  inited = wil::init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___((__int64)this, a2, a3);
  LastErrorFailHr = inited;
  if ( inited < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)inited,
      v23);
    v11 = 654;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)LastErrorFailHr,
      v23);
    return (unsigned int)LastErrorFailHr;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v8 = (wil::details *)*((_QWORD *)this + 13);
    if ( v8 )
    {
      LastError = GetLastError();
      wil::details::CloseHandle(v8, v10);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 13) = Event;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
    if ( LastErrorFailHr < 0 )
    {
      v11 = 656;
      goto LABEL_8;
    }
  }
  v13 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  if ( v13 )
  {
    v15 = *((_QWORD *)this + 13);
    *v13 = &CRefThread::`vftable';
    v13[1] = (char *)this + 132;
    *((_DWORD *)v13 + 4) = 0;
    v13[3] = v15;
    *((_DWORD *)this + 33) = 1;
  }
  else
  {
    v14 = 0;
  }
  v16 = *((_QWORD *)this + 14);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  *((_QWORD *)this + 14) = v14;
  if ( !v14 )
  {
    LastErrorFailHr = -2147024882;
    v11 = 659;
    goto LABEL_8;
  }
  v17 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( v17 )
  {
    v19 = *((_QWORD *)this + 13);
    *v17 = &CRefThread::`vftable';
    v17[1] = (char *)this + 84;
    *((_DWORD *)v17 + 4) = 0;
    v17[3] = v19;
    *((_DWORD *)this + 21) = 1;
  }
  else
  {
    v18 = 0;
  }
  v20 = *((_QWORD *)this + 15);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  *((_QWORD *)this + 15) = v18;
  if ( !v18 )
  {
    LastErrorFailHr = -2147024882;
    v11 = 662;
    goto LABEL_8;
  }
  *((_QWORD *)this + 17) = *((_QWORD *)this + 14);
  *((_DWORD *)this + 32) = (*((_DWORD *)this + 19) | (*((_DWORD *)this + 18) << 24)) + 1;
  v21 = (HMODULE)*((_QWORD *)this + 8);
  if ( v21 )
  {
    v22 = GetLastError();
    FreeLibrary(v21);
    SetLastError(v22);
  }
  *((_QWORD *)this + 8) = 0;
  GetModuleHandleExW(4u, (LPCWSTR)SHTaskPoolQueueTask, (HMODULE *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x18000eadc  push    rbx
0x18000eade  push    rbp
0x18000eadf  push    rsi
0x18000eae0  push    rdi
0x18000eae1  push    r15; int
0x18000eae3  sub     rsp, 20h
0x18000eae7  mov     rdi, rcx
0x18000eaea  xor     dl, dl
0x18000eaec  call    wil__init_once_nothrow__lambda_4d618c0176c5f0f37bb52e96518a1ec6___
0x18000eaf1  mov     ebx, eax
0x18000eaf3  test    eax, eax
0x18000eaf5  js      short loc_18000EB41
0x18000eaf7  mov     r9d, 1F0003h; dwDesiredAccess
0x18000eafd  xor     r8d, r8d; dwFlags
0x18000eb00  xor     edx, edx; lpName
0x18000eb02  xor     ecx, ecx; lpEventAttributes
0x18000eb04  call    cs:__imp_CreateEventExW
0x18000eb0a  mov     rbp, rax
0x18000eb0d  test    rax, rax
0x18000eb10  jz      short loc_18000EB86
0x18000eb12  call    cs:__imp_GetLastError
0x18000eb18  mov     rsi, [rdi+68h]
0x18000eb1c  test    rsi, rsi
0x18000eb1f  jnz     short loc_18000EB27
0x18000eb21  mov     [rdi+68h], rbp
0x18000eb25  jmp     short loc_18000EB95
0x18000eb27  call    cs:__imp_GetLastError
0x18000eb2d  mov     ebx, eax
0x18000eb2f  mov     rcx, rsi; this
0x18000eb32  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000eb37  mov     ecx, ebx; dwErrCode
0x18000eb39  call    cs:__imp_SetLastError
0x18000eb3f  jmp     short loc_18000EB21
0x18000eb41  mov     rcx, [rsp+48h]; this
0x18000eb46  mov     r9d, ebx; char *
0x18000eb49  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000eb50  mov     edx, 70h ; 'p'; void *
0x18000eb55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb5a  mov     edx, 28Eh
0x18000eb5f  jmp     short loc_18000EB6B
0x18000eb61  mov     ebx, 8007000Eh
0x18000eb66  mov     edx, 296h; void *
0x18000eb6b  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000eb72  mov     r9d, ebx; char *
0x18000eb75  mov     rcx, [rsp+48h]; this
0x18000eb7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eb7f  mov     eax, ebx
0x18000eb81  jmp     loc_18000EC8D
0x18000eb86  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000eb8b  mov     ebx, eax
0x18000eb8d  test    eax, eax
0x18000eb8f  js      loc_18000ECC2
0x18000eb95  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000eb9c  mov     ebp, 20h ; ' '
0x18000eba1  mov     ecx, ebp; unsigned __int64
0x18000eba3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000eba8  mov     rbx, rax
0x18000ebab  lea     r15, ??_7CRefThread@@6B@; const CRefThread::`vftable'
0x18000ebb2  lea     esi, [rbp-1Fh]
0x18000ebb5  test    rax, rax
0x18000ebb8  jz      loc_18000ECCC
0x18000ebbe  mov     rdx, [rdi+68h]
0x18000ebc2  mov     [rax], r15
0x18000ebc5  lea     rcx, [rdi+84h]
0x18000ebcc  mov     [rax+8], rcx
0x18000ebd0  mov     dword ptr [rax+10h], 0
0x18000ebd7  mov     [rax+18h], rdx
0x18000ebdb  mov     [rcx], esi
0x18000ebdd  mov     rcx, [rdi+70h]
0x18000ebe1  test    rcx, rcx
0x18000ebe4  jnz     loc_18000ECD3
0x18000ebea  mov     [rdi+70h], rbx
0x18000ebee  test    rbx, rbx
0x18000ebf1  jz      loc_18000ECB3
0x18000ebf7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ebfe  mov     rcx, rbp; unsigned __int64
0x18000ec01  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ec06  mov     rbx, rax
0x18000ec09  test    rax, rax
0x18000ec0c  jz      loc_18000ECE4
0x18000ec12  mov     rdx, [rdi+68h]
0x18000ec16  mov     [rax], r15
0x18000ec19  lea     rcx, [rdi+54h]
0x18000ec1d  mov     [rax+8], rcx
0x18000ec21  mov     dword ptr [rax+10h], 0
0x18000ec28  mov     [rax+18h], rdx
0x18000ec2c  mov     [rcx], esi
0x18000ec2e  mov     rcx, [rdi+78h]
0x18000ec32  test    rcx, rcx
0x18000ec35  jnz     loc_18000ECEB
0x18000ec3b  mov     [rdi+78h], rbx
0x18000ec3f  test    rbx, rbx
0x18000ec42  jz      loc_18000EB61
0x18000ec48  mov     rax, [rdi+70h]
0x18000ec4c  mov     [rdi+88h], rax
0x18000ec53  mov     eax, [rdi+48h]
0x18000ec56  shl     eax, 18h
0x18000ec59  or      eax, [rdi+4Ch]
0x18000ec5c  add     eax, esi
0x18000ec5e  mov     [rdi+80h], eax
0x18000ec64  mov     rsi, [rdi+40h]
0x18000ec68  test    rsi, rsi
0x18000ec6b  jnz     short loc_18000EC98
0x18000ec6d  mov     qword ptr [rdi+40h], 0
0x18000ec75  lea     r8, [rdi+40h]; phModule
0x18000ec79  lea     rdx, SHTaskPoolQueueTask; lpModuleName
0x18000ec80  mov     ecx, 4; dwFlags
0x18000ec85  call    cs:__imp_GetModuleHandleExW
0x18000ec8b  xor     eax, eax
0x18000ec8d  add     rsp, 20h
0x18000ec91  pop     r15
0x18000ec93  pop     rdi
0x18000ec94  pop     rsi
0x18000ec95  pop     rbp
0x18000ec96  pop     rbx
0x18000ec97  retn
0x18000ec98  call    cs:__imp_GetLastError
0x18000ec9e  mov     ebx, eax
0x18000eca0  mov     rcx, rsi; hLibModule
0x18000eca3  call    cs:__imp_FreeLibrary
0x18000eca9  mov     ecx, ebx; dwErrCode
0x18000ecab  call    cs:__imp_SetLastError
0x18000ecb1  jmp     short loc_18000EC6D
0x18000ecb3  mov     ebx, 8007000Eh
0x18000ecb8  mov     edx, 293h
0x18000ecbd  jmp     loc_18000EB6B
0x18000ecc2  mov     edx, 290h
0x18000ecc7  jmp     loc_18000EB6B
0x18000eccc  xor     ebx, ebx
0x18000ecce  jmp     loc_18000EBDD
0x18000ecd3  mov     rax, [rcx]
0x18000ecd6  mov     rax, [rax+10h]
0x18000ecda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecdf  jmp     loc_18000EBEA
0x18000ece4  xor     ebx, ebx
0x18000ece6  jmp     loc_18000EC2E
0x18000eceb  mov     rax, [rcx]
0x18000ecee  mov     rax, [rax+10h]
0x18000ecf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecf7  jmp     loc_18000EC3B
```
