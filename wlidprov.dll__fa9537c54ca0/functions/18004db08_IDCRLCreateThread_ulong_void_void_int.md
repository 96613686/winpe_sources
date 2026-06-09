# IDCRLCreateThread(ulong (*)(void *),void *,int)

- ea: `0x18004db08`
- end: `0x18004dc50`
- name: `?IDCRLCreateThread@@YAPEAXP6AKPEAX@Z0H@Z`
- size: `328`
- prototype: `void *__fastcall(LPTHREAD_START_ROUTINE lpStartAddress, void *lpParameter, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e0a0`
- `0x180037c80`

## callees

- `0x180012ac0`
- `0x180016170`
- `0x18001ca08`
- `0x18004dae0`
- `0x18004db08`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dc2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004dc2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db66`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004db8c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004dc0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004db8c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004dc0e`

## pseudocode

```c
HANDLE __fastcall IDCRLCreateThread(LPTHREAD_START_ROUTINE lpStartAddress, void *lpParameter, void *a3, bool a4)
{
  HANDLE Thread; // rax
  HANDLE v7; // rbx
  DWORD LastError; // eax
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  __int64 v11; // rbx
  unsigned int v12; // edx
  void **v14; // [rsp+30h] [rbp-48h] BYREF
  __int128 v15; // [rsp+38h] [rbp-40h]
  __int64 v16; // [rsp+48h] [rbp-30h]

  v16 = 0;
  v14 = &ATL::CAccessToken::`vftable';
  v15 = 0;
  if ( !(_DWORD)a3 )
  {
    Thread = CreateThread(0, 0, lpStartAddress, lpParameter, 0, 0);
LABEL_8:
    v7 = Thread;
    goto LABEL_14;
  }
  v7 = 0;
  if ( ATL::CAccessToken::GetThreadToken((ATL::CAccessToken *)&v14, (unsigned int)lpParameter, a3, a4) )
  {
    v9 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      LastError = 14;
      goto LABEL_13;
    }
    *v9 = lpStartAddress;
    v9[1] = lpParameter;
    v9[2] = &ATL::CAccessToken::`vftable';
    v9[3] = 0;
    v9[4] = 0;
    v9[5] = 0;
    v11 = v15;
    *(_QWORD *)&v15 = 0;
    ((void (__fastcall *)(void ***))v14[1])(&v14);
    v10[3] = v11;
    v7 = CreateThread(0, 0, IDCRLReplacmentThread, v10, 0, 0);
    if ( !v7 )
      CIDCRLThreadParam::`scalar deleting destructor'((CIDCRLThreadParam *)v10, v12);
  }
  else
  {
    if ( GetLastError() == 1008 )
    {
      Thread = CreateThread(0, 0, lpStartAddress, lpParameter, 0, 0);
      goto LABEL_8;
    }
    LastError = GetLastError();
    if ( LastError )
LABEL_13:
      SetLastError(LastError);
  }
LABEL_14:
  v14 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v14);
  return v7;
}

```

## disassembly

```asm
0x18004db08  mov     rax, rsp
0x18004db0b  push    rbx
0x18004db0c  push    rbp
0x18004db0d  push    rsi
0x18004db0e  push    rdi
0x18004db0f  push    r15
0x18004db11  sub     rsp, 50h
0x18004db15  mov     qword ptr [rax-30h], 0
0x18004db1d  lea     r15, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18004db24  mov     [rax-48h], r15
0x18004db28  xorps   xmm0, xmm0
0x18004db2b  mov     rsi, rdx
0x18004db2e  mov     rbp, rcx
0x18004db31  movdqu  xmmword ptr [rax-40h], xmm0
0x18004db36  test    r8d, r8d
0x18004db39  jnz     short loc_18004DB49
0x18004db3b  mov     qword ptr [rax-50h], 0
0x18004db43  mov     [rax-58h], r8d
0x18004db47  jmp     short loc_18004DB82
0x18004db49  lea     rcx, [rsp+78h+var_48]; this
0x18004db4e  xor     ebx, ebx
0x18004db50  call    ?GetThreadToken@CAccessToken@ATL@@QEAA_NKPEAX_N@Z; ATL::CAccessToken::GetThreadToken(ulong,void *,bool)
0x18004db55  test    al, al
0x18004db57  jnz     short loc_18004DB9A
0x18004db59  call    cs:__imp_GetLastError
0x18004db5f  cmp     eax, 3F0h
0x18004db64  jz      short loc_18004DB79
0x18004db66  call    cs:__imp_GetLastError
0x18004db6c  test    eax, eax
0x18004db6e  jz      loc_18004DC33
0x18004db74  jmp     loc_18004DC2B
0x18004db79  mov     [rsp+78h+lpThreadId], rbx; lpThreadId
0x18004db7e  mov     [rsp+78h+dwCreationFlags], ebx; dwCreationFlags
0x18004db82  mov     r9, rsi; lpParameter
0x18004db85  mov     r8, rbp; lpStartAddress
0x18004db88  xor     edx, edx; dwStackSize
0x18004db8a  xor     ecx, ecx; lpThreadAttributes
0x18004db8c  call    cs:__imp_CreateThread
0x18004db92  mov     rbx, rax
0x18004db95  jmp     loc_18004DC33
0x18004db9a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004dba1  mov     ecx, 38h ; '8'; unsigned __int64
0x18004dba6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004dbab  mov     rdi, rax
0x18004dbae  test    rax, rax
0x18004dbb1  jz      short loc_18004DC26
0x18004dbb3  mov     [rax], rbp
0x18004dbb6  mov     [rax+8], rsi
0x18004dbba  mov     [rax+10h], r15
0x18004dbbe  mov     [rax+18h], rbx
0x18004dbc2  mov     [rax+20h], rbx
0x18004dbc6  mov     [rax+28h], rbx
0x18004dbca  mov     rcx, [rsp+78h+var_48]
0x18004dbcf  mov     rbx, qword ptr [rsp+78h+var_40]
0x18004dbd4  mov     qword ptr [rsp+78h+var_40], 0
0x18004dbdd  mov     rax, [rcx+8]
0x18004dbe1  lea     rcx, [rsp+78h+var_48]
0x18004dbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbeb  mov     r9, rdi; lpParameter
0x18004dbee  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x18004dbf7  lea     r8, ?IDCRLReplacmentThread@@YAKPEAX@Z; lpStartAddress
0x18004dbfe  mov     [rdi+18h], rbx
0x18004dc02  xor     edx, edx; dwStackSize
0x18004dc04  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x18004dc0c  xor     ecx, ecx; lpThreadAttributes
0x18004dc0e  call    cs:__imp_CreateThread
0x18004dc14  mov     rbx, rax
0x18004dc17  test    rax, rax
0x18004dc1a  jnz     short loc_18004DC33
0x18004dc1c  mov     rcx, rdi; this
0x18004dc1f  call    ??_GCIDCRLThreadParam@@QEAAPEAXI@Z; CIDCRLThreadParam::`scalar deleting destructor'(uint)
0x18004dc24  jmp     short loc_18004DC33
0x18004dc26  mov     eax, 0Eh
0x18004dc2b  mov     ecx, eax; dwErrCode
0x18004dc2d  call    cs:__imp_SetLastError
0x18004dc33  lea     rcx, [rsp+78h+var_48]; this
0x18004dc38  mov     [rsp+78h+var_48], r15
0x18004dc3d  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x18004dc42  mov     rax, rbx
0x18004dc45  add     rsp, 50h
0x18004dc49  pop     r15
0x18004dc4b  pop     rdi
0x18004dc4c  pop     rsi
0x18004dc4d  pop     rbp
0x18004dc4e  pop     rbx
0x18004dc4f  retn
```
