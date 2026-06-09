# IDCRLCreateThread(ulong (*)(void *),void *,int)

- ea: `0x180053d58`
- end: `0x180053e8c`
- name: `?IDCRLCreateThread@@YAPEAXP6AKPEAX@Z0H@Z`
- size: `308`
- prototype: `void *__fastcall(LPTHREAD_START_ROUTINE lpStartAddress, void *lpParameter, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800372d0`
- `0x180041248`

## callees

- `0x1800032dc`
- `0x180053c60`
- `0x180053c90`
- `0x180053cf8`
- `0x180053d58`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053da2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053e69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053e69`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180053dc8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180053e4a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180053dc8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180053e4a`

## pseudocode

```c
HANDLE __fastcall IDCRLCreateThread(LPTHREAD_START_ROUTINE lpStartAddress, void *lpParameter, void *a3, bool a4)
{
  HANDLE Thread; // rbx
  DWORD LastError; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rbx
  void **v12; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+38h] [rbp-40h]
  __int64 v14; // [rsp+48h] [rbp-30h]

  v14 = 0;
  v12 = &ATL::CAccessToken::`vftable';
  v13 = 0;
  Thread = 0;
  if ( ATL::CAccessToken::GetThreadToken((ATL::CAccessToken *)&v12, (unsigned int)lpParameter, a3, a4) )
  {
    v8 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      LastError = 14;
LABEL_10:
      SetLastError(LastError);
      goto LABEL_11;
    }
    *v8 = lpStartAddress;
    v8[1] = lpParameter;
    v8[2] = &ATL::CAccessToken::`vftable';
    v8[3] = 0;
    v8[4] = 0;
    v8[5] = 0;
    v10 = v13;
    *(_QWORD *)&v13 = 0;
    ((void (__fastcall *)(void ***))v12[1])(&v12);
    v9[3] = v10;
    Thread = CreateThread(0, 0, IDCRLReplacmentThread, v9, 0, 0);
    if ( !Thread )
      CIDCRLThreadParam::`scalar deleting destructor'((CIDCRLThreadParam *)v9);
  }
  else if ( GetLastError() == 1008 )
  {
    Thread = CreateThread(0, 0, lpStartAddress, lpParameter, 0, 0);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_10;
  }
LABEL_11:
  v12 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v12);
  return Thread;
}

```

## disassembly

```asm
0x180053d58  mov     rax, rsp
0x180053d5b  push    rbx
0x180053d5c  push    rbp
0x180053d5d  push    rsi
0x180053d5e  push    rdi
0x180053d5f  push    r15
0x180053d61  sub     rsp, 50h
0x180053d65  mov     rbp, rcx
0x180053d68  mov     qword ptr [rax-30h], 0
0x180053d70  xorps   xmm0, xmm0
0x180053d73  lea     r15, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180053d7a  lea     rcx, [rax-48h]; this
0x180053d7e  mov     [rax-48h], r15
0x180053d82  movdqu  xmmword ptr [rax-40h], xmm0
0x180053d87  mov     rsi, rdx
0x180053d8a  xor     ebx, ebx
0x180053d8c  call    ?GetThreadToken@CAccessToken@ATL@@QEAA_NKPEAX_N@Z; ATL::CAccessToken::GetThreadToken(ulong,void *,bool)
0x180053d91  test    al, al
0x180053d93  jnz     short loc_180053DD6
0x180053d95  call    cs:__imp_GetLastError
0x180053d9b  cmp     eax, 3F0h
0x180053da0  jz      short loc_180053DB5
0x180053da2  call    cs:__imp_GetLastError
0x180053da8  test    eax, eax
0x180053daa  jz      loc_180053E6F
0x180053db0  jmp     loc_180053E67
0x180053db5  mov     [rsp+78h+lpThreadId], rbx; lpThreadId
0x180053dba  mov     r9, rsi; lpParameter
0x180053dbd  mov     r8, rbp; lpStartAddress
0x180053dc0  mov     [rsp+78h+dwCreationFlags], ebx; dwCreationFlags
0x180053dc4  xor     edx, edx; dwStackSize
0x180053dc6  xor     ecx, ecx; lpThreadAttributes
0x180053dc8  call    cs:__imp_CreateThread
0x180053dce  mov     rbx, rax
0x180053dd1  jmp     loc_180053E6F
0x180053dd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180053ddd  mov     ecx, 38h ; '8'; unsigned __int64
0x180053de2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180053de7  mov     rdi, rax
0x180053dea  test    rax, rax
0x180053ded  jz      short loc_180053E62
0x180053def  mov     [rax], rbp
0x180053df2  mov     [rax+8], rsi
0x180053df6  mov     [rax+10h], r15
0x180053dfa  mov     [rax+18h], rbx
0x180053dfe  mov     [rax+20h], rbx
0x180053e02  mov     [rax+28h], rbx
0x180053e06  mov     rcx, [rsp+78h+var_48]
0x180053e0b  mov     rbx, qword ptr [rsp+78h+var_40]
0x180053e10  mov     qword ptr [rsp+78h+var_40], 0
0x180053e19  mov     rax, [rcx+8]
0x180053e1d  lea     rcx, [rsp+78h+var_48]
0x180053e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e27  mov     r9, rdi; lpParameter
0x180053e2a  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x180053e33  lea     r8, ?IDCRLReplacmentThread@@YAKPEAX@Z; lpStartAddress
0x180053e3a  mov     [rdi+18h], rbx
0x180053e3e  xor     edx, edx; dwStackSize
0x180053e40  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180053e48  xor     ecx, ecx; lpThreadAttributes
0x180053e4a  call    cs:__imp_CreateThread
0x180053e50  mov     rbx, rax
0x180053e53  test    rax, rax
0x180053e56  jnz     short loc_180053E6F
0x180053e58  mov     rcx, rdi; this
0x180053e5b  call    ??_GCIDCRLThreadParam@@QEAAPEAXI@Z; CIDCRLThreadParam::`scalar deleting destructor'(uint)
0x180053e60  jmp     short loc_180053E6F
0x180053e62  mov     eax, 0Eh
0x180053e67  mov     ecx, eax; dwErrCode
0x180053e69  call    cs:__imp_SetLastError
0x180053e6f  lea     rcx, [rsp+78h+var_48]; this
0x180053e74  mov     [rsp+78h+var_48], r15
0x180053e79  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180053e7e  mov     rax, rbx
0x180053e81  add     rsp, 50h
0x180053e85  pop     r15
0x180053e87  pop     rdi
0x180053e88  pop     rsi
0x180053e89  pop     rbp
0x180053e8a  pop     rbx
0x180053e8b  retn
```
