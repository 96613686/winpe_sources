# IDCRLCreateThread(ulong (*)(void *),void *,int)

- ea: `0x180110b60`
- end: `0x180110c78`
- name: `?IDCRLCreateThread@@YAPEAXP6AKPEAX@Z0H@Z`
- size: `280`
- prototype: `void *__fastcall(unsigned int (*)(void *), void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800e7660`

## callees

- `0x180021c10`
- `0x180042174`
- `0x180051320`
- `0x1800a716c`
- `0x180110b38`
- `0x180110b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180110ba8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180110bb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180110bb6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180110bf2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180110c59`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180110bf2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180110c59`

## pseudocode

```c
HANDLE __fastcall IDCRLCreateThread(unsigned int (*a1)(void *), void *a2, void *a3, bool a4)
{
  HANDLE Thread; // rsi
  DWORD LastError; // edi
  HANDLE v6; // rbx
  _QWORD *v8; // rax
  void *v9; // rbx
  unsigned int v10; // edx
  void **v11; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+38h] [rbp-40h]
  __int64 v13; // [rsp+48h] [rbp-30h]

  v13 = 0;
  Thread = 0;
  v11 = &ATL::CAccessToken::`vftable';
  v12 = 0;
  LastError = 14;
  if ( ATL::CAccessToken::GetThreadToken((ATL::CAccessToken *)&v11, 0xEu, a3, a4) )
  {
    v8 = operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
    v9 = v8;
    if ( v8 )
    {
      v8[1] = 0;
      *v8 = CNetworkAddresses::_PublisherLoop;
      v8[2] = &ATL::CAccessToken::`vftable';
      v8[3] = 0;
      v8[4] = 0;
      v8[5] = 0;
      v8[3] = ATL::CAccessToken::Detach((ATL::CAccessToken *)&v11);
      Thread = CreateThread(0, 0, IDCRLReplacmentThread, v9, 0, 0);
      if ( !Thread )
        CIDCRLThreadParam::`scalar deleting destructor'((CIDCRLThreadParam *)v9, v10);
      goto LABEL_5;
    }
    goto LABEL_4;
  }
  if ( GetLastError() == 1008 )
  {
    v6 = CreateThread(0, 0, CNetworkAddresses::_PublisherLoop, 0, 0, 0);
    goto LABEL_6;
  }
  LastError = GetLastError();
  if ( LastError )
LABEL_4:
    SetLastError(LastError);
LABEL_5:
  v6 = Thread;
LABEL_6:
  v11 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v11);
  return v6;
}

```

## disassembly

```asm
0x180110b60  mov     rax, rsp
0x180110b63  push    rbx
0x180110b64  push    rsi
0x180110b65  push    rdi
0x180110b66  push    r14
0x180110b68  sub     rsp, 58h
0x180110b6c  xorps   xmm0, xmm0
0x180110b6f  mov     qword ptr [rax-30h], 0
0x180110b77  xor     esi, esi
0x180110b79  lea     r14, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180110b80  lea     rcx, [rax-48h]; this
0x180110b84  mov     [rax-48h], r14
0x180110b88  movdqu  xmmword ptr [rax-40h], xmm0
0x180110b8d  lea     edi, [rsi+0Eh]
0x180110b90  mov     edx, edi; unsigned int
0x180110b92  call    ?GetThreadToken@CAccessToken@ATL@@QEAA_NKPEAX_N@Z; ATL::CAccessToken::GetThreadToken(ulong,void *,bool)
0x180110b97  test    al, al
0x180110b99  jnz     short loc_180110BFD
0x180110b9b  call    cs:__imp_GetLastError
0x180110ba1  cmp     eax, 3F0h
0x180110ba6  jz      short loc_180110BDB
0x180110ba8  call    cs:__imp_GetLastError
0x180110bae  mov     edi, eax
0x180110bb0  test    eax, eax
0x180110bb2  jz      short loc_180110BBC
0x180110bb4  mov     ecx, edi; dwErrCode
0x180110bb6  call    cs:__imp_SetLastError
0x180110bbc  mov     rbx, rsi
0x180110bbf  lea     rcx, [rsp+78h+var_48]; this
0x180110bc4  mov     [rsp+78h+var_48], r14
0x180110bc9  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180110bce  mov     rax, rbx
0x180110bd1  add     rsp, 58h
0x180110bd5  pop     r14
0x180110bd7  pop     rdi
0x180110bd8  pop     rsi
0x180110bd9  pop     rbx
0x180110bda  retn
0x180110bdb  mov     [rsp+78h+lpThreadId], rsi; lpThreadId
0x180110be0  lea     r8, ?_PublisherLoop@CNetworkAddresses@@CAKPEAX@Z; lpStartAddress
0x180110be7  xor     r9d, r9d; lpParameter
0x180110bea  mov     [rsp+78h+dwCreationFlags], esi; dwCreationFlags
0x180110bee  xor     edx, edx; dwStackSize
0x180110bf0  xor     ecx, ecx; lpThreadAttributes
0x180110bf2  call    cs:__imp_CreateThread
0x180110bf8  mov     rbx, rax
0x180110bfb  jmp     short loc_180110BBF
0x180110bfd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180110c04  mov     ecx, 38h ; '8'; unsigned __int64
0x180110c09  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180110c0e  mov     rbx, rax
0x180110c11  test    rax, rax
0x180110c14  jz      short loc_180110BB4
0x180110c16  mov     [rbx+8], rsi
0x180110c1a  lea     rax, ?_PublisherLoop@CNetworkAddresses@@CAKPEAX@Z; CNetworkAddresses::_PublisherLoop(void *)
0x180110c21  mov     [rbx], rax
0x180110c24  lea     rcx, [rsp+78h+var_48]; this
0x180110c29  mov     [rbx+10h], r14
0x180110c2d  mov     [rbx+18h], rsi
0x180110c31  mov     [rbx+20h], rsi
0x180110c35  mov     [rbx+28h], rsi
0x180110c39  call    ?Detach@CAccessToken@ATL@@QEAAPEAXXZ; ATL::CAccessToken::Detach(void)
0x180110c3e  mov     r9, rbx; lpParameter
0x180110c41  mov     [rsp+78h+lpThreadId], rsi; lpThreadId
0x180110c46  lea     r8, ?IDCRLReplacmentThread@@YAKPEAX@Z; lpStartAddress
0x180110c4d  mov     [rbx+18h], rax
0x180110c51  xor     edx, edx; dwStackSize
0x180110c53  mov     [rsp+78h+dwCreationFlags], esi; dwCreationFlags
0x180110c57  xor     ecx, ecx; lpThreadAttributes
0x180110c59  call    cs:__imp_CreateThread
0x180110c5f  mov     rsi, rax
0x180110c62  test    rax, rax
0x180110c65  jnz     loc_180110BBC
0x180110c6b  mov     rcx, rbx; this
0x180110c6e  call    ??_GCIDCRLThreadParam@@QEAAPEAXI@Z; CIDCRLThreadParam::`scalar deleting destructor'(uint)
0x180110c73  jmp     loc_180110BBC
```
