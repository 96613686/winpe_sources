# p9fs::Socket::Reset(unsigned __int64)

- ea: `0x18002b720`
- end: `0x18002b8f8`
- name: `?Reset@Socket@p9fs@@QEAAX_K@Z`
- size: `472`
- prototype: `void(p9fs::Socket *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180023f74`
- `0x180025e40`
- `0x180027950`

## callees

- `0x180004120`
- `0x180004c80`
- `0x18001c75c`
- `0x1800286fc`
- `0x180028fdc`
- `0x18002b720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b76a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b7ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b860`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b76a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b7ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002b860`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b757`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b842`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002b7a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002b858`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002b890`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002b7a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002b858`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18002b890`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002b79d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002b84f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002b887`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002b79d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002b84f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18002b887`
- `WS2_32!__imp_closesocket` at `0x18002b762`
- `WS2_32!__imp_closesocket` at `0x18002b762`
- `WS2_32!__imp_getsockname` at `0x18002b7ed`
- `WS2_32!__imp_getsockname` at `0x18002b7ed`

## string_xrefs

- `0x18002b8c6`: `onecore\vm\dv\storage\plan9\dll\windows\p9windows.cpp`
- `0x18002b8e6`: `onecore\vm\dv\storage\plan9\dll\windows\p9windows.cpp`

## pseudocode

```c
void __fastcall p9fs::Socket::Reset(p9fs::Socket *this, void *a2)
{
  SOCKET v2; // rbp
  DWORD LastError; // ebx
  char *v6; // rdi
  struct _TP_IO *v7; // rsi
  DWORD v8; // ebx
  const char *v9; // r9
  char *v10; // rax
  char *v11; // rdi
  char *v12; // rsi
  struct _TP_IO *v13; // rbp
  __int64 v14; // r14
  DWORD v15; // ebx
  struct _TP_IO *v16; // rbx
  PTP_IO pio[2]; // [rsp+20h] [rbp-D8h] BYREF
  char v18; // [rsp+30h] [rbp-C8h] BYREF
  int namelen[4]; // [rsp+40h] [rbp-B8h] BYREF
  struct sockaddr name; // [rsp+50h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v2 = *((_QWORD *)this + 1);
  if ( v2 != -1 )
  {
    LastError = GetLastError();
    closesocket(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = a2;
  if ( a2 == (void *)-1LL )
  {
    v6 = (char *)this + 16;
    if ( v6 != &v18 )
    {
      v7 = *(struct _TP_IO **)v6;
      if ( *(_QWORD *)v6 )
      {
        v8 = GetLastError();
        WaitForThreadpoolIoCallbacks(v7, 0);
        CloseThreadpoolIo(v7);
        SetLastError(v8);
      }
      *(_QWORD *)v6 = 0;
    }
    *((_QWORD *)v6 + 1) = 0;
  }
  else
  {
    memset_0(&name, 0, 0x80u);
    namelen[0] = 128;
    if ( getsockname((SOCKET)a2, &name, namelen) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9windows.cpp",
        v9);
    if ( ((name.sa_family - 2) & 0xFFDF) != 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9windows.cpp",
        (const char *)0x80070057LL,
        (int)pio[0]);
    *((_BYTE *)this + 32) = name.sa_family == 2;
    v10 = (char *)p9fs::CoroutineIoIssuer::CoroutineIoIssuer(pio, a2);
    v11 = (char *)this + 16;
    v12 = v10;
    if ( v11 != v10 )
    {
      v13 = *(struct _TP_IO **)v11;
      v14 = *(_QWORD *)v10;
      if ( *(_QWORD *)v11 )
      {
        v15 = GetLastError();
        WaitForThreadpoolIoCallbacks(v13, 0);
        CloseThreadpoolIo(v13);
        SetLastError(v15);
      }
      *(_QWORD *)v11 = v14;
      *(_QWORD *)v12 = 0;
    }
    v16 = pio[0];
    *((_QWORD *)v11 + 1) = *((_QWORD *)v12 + 1);
    if ( v16 )
    {
      WaitForThreadpoolIoCallbacks(v16, 0);
      CloseThreadpoolIo(v16);
    }
  }
}

```

## disassembly

```asm
0x18002b720  mov     [rsp+arg_10], rbx
0x18002b725  mov     [rsp+arg_18], rbp
0x18002b72a  push    rsi
0x18002b72b  push    rdi
0x18002b72c  push    r14
0x18002b72e  sub     rsp, 0E0h
0x18002b735  mov     rax, cs:__security_cookie
0x18002b73c  xor     rax, rsp
0x18002b73f  mov     [rsp+0F8h+var_28], rax
0x18002b747  mov     rbp, [rcx+8]
0x18002b74b  mov     rsi, rdx
0x18002b74e  mov     rdi, rcx
0x18002b751  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18002b755  jz      short loc_18002B770
0x18002b757  call    cs:__imp_GetLastError
0x18002b75d  mov     rcx, rbp; s
0x18002b760  mov     ebx, eax
0x18002b762  call    cs:__imp_closesocket
0x18002b768  mov     ecx, ebx; dwErrCode
0x18002b76a  call    cs:__imp_SetLastError
0x18002b770  mov     [rdi+8], rsi
0x18002b774  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002b778  jnz     short loc_18002B7C8
0x18002b77a  add     rdi, 10h
0x18002b77e  lea     rax, [rsp+0F8h+var_C8]
0x18002b783  cmp     rdi, rax
0x18002b786  jz      short loc_18002B7BB
0x18002b788  mov     rsi, [rdi]
0x18002b78b  test    rsi, rsi
0x18002b78e  jz      short loc_18002B7B4
0x18002b790  call    cs:__imp_GetLastError
0x18002b796  xor     edx, edx; fCancelPendingCallbacks
0x18002b798  mov     rcx, rsi; pio
0x18002b79b  mov     ebx, eax
0x18002b79d  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18002b7a3  mov     rcx, rsi; pio
0x18002b7a6  call    cs:__imp_CloseThreadpoolIo
0x18002b7ac  mov     ecx, ebx; dwErrCode
0x18002b7ae  call    cs:__imp_SetLastError
0x18002b7b4  mov     qword ptr [rdi], 0
0x18002b7bb  mov     qword ptr [rdi+8], 0
0x18002b7c3  jmp     loc_18002B896
0x18002b7c8  mov     ebx, 80h
0x18002b7cd  lea     rcx, [rsp+0F8h+name]; void *
0x18002b7d2  mov     r8d, ebx; Size
0x18002b7d5  xor     edx, edx; Val
0x18002b7d7  call    memset_0
0x18002b7dc  lea     r8, [rsp+0F8h+namelen]; namelen
0x18002b7e1  mov     [rsp+0F8h+namelen], ebx
0x18002b7e5  lea     rdx, [rsp+0F8h+name]; name
0x18002b7ea  mov     rcx, rsi; s
0x18002b7ed  call    cs:__imp_getsockname
0x18002b7f3  test    eax, eax
0x18002b7f5  jnz     loc_18002B8DE
0x18002b7fb  movzx   eax, [rsp+0F8h+name.sa_family]
0x18002b800  mov     ecx, 0FFDFh
0x18002b805  sub     ax, 2
0x18002b809  test    cx, ax
0x18002b80c  jnz     loc_18002B8BE
0x18002b812  cmp     [rsp+0F8h+name.sa_family], 2
0x18002b818  lea     rcx, [rsp+0F8h+pio]; pv
0x18002b81d  mov     rdx, rsi; FileHandle
0x18002b820  setz    al
0x18002b823  mov     [rdi+20h], al
0x18002b826  call    ??0CoroutineIoIssuer@p9fs@@QEAA@PEAX@Z; p9fs::CoroutineIoIssuer::CoroutineIoIssuer(void *)
0x18002b82b  add     rdi, 10h
0x18002b82f  mov     rsi, rax
0x18002b832  cmp     rdi, rax
0x18002b835  jz      short loc_18002B870
0x18002b837  mov     rbp, [rdi]
0x18002b83a  mov     r14, [rax]
0x18002b83d  test    rbp, rbp
0x18002b840  jz      short loc_18002B866
0x18002b842  call    cs:__imp_GetLastError
0x18002b848  xor     edx, edx; fCancelPendingCallbacks
0x18002b84a  mov     rcx, rbp; pio
0x18002b84d  mov     ebx, eax
0x18002b84f  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18002b855  mov     rcx, rbp; pio
0x18002b858  call    cs:__imp_CloseThreadpoolIo
0x18002b85e  mov     ecx, ebx; dwErrCode
0x18002b860  call    cs:__imp_SetLastError
0x18002b866  mov     [rdi], r14
0x18002b869  mov     qword ptr [rsi], 0
0x18002b870  mov     rbx, [rsp+0F8h+pio]
0x18002b875  mov     rax, [rsi+8]
0x18002b879  mov     [rdi+8], rax
0x18002b87d  test    rbx, rbx
0x18002b880  jz      short loc_18002B896
0x18002b882  xor     edx, edx; fCancelPendingCallbacks
0x18002b884  mov     rcx, rbx; pio
0x18002b887  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18002b88d  mov     rcx, rbx; pio
0x18002b890  call    cs:__imp_CloseThreadpoolIo
0x18002b896  mov     rcx, [rsp+0F8h+var_28]
0x18002b89e  xor     rcx, rsp; StackCookie
0x18002b8a1  call    __security_check_cookie
0x18002b8a6  lea     r11, [rsp+0F8h+var_18]
0x18002b8ae  mov     rbx, [r11+30h]
0x18002b8b2  mov     rbp, [r11+38h]
0x18002b8b6  mov     rsp, r11
0x18002b8b9  pop     r14
0x18002b8bb  pop     rdi
0x18002b8bc  pop     rsi
0x18002b8bd  retn
0x18002b8be  mov     rcx, [rsp+0F8h]; this
0x18002b8c6  lea     r8, aOnecoreVmDvSto_9; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002b8cd  mov     r9d, 80070057h; char *
0x18002b8d3  mov     edx, 4Eh ; 'N'; void *
0x18002b8d8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002b8de  mov     rcx, [rsp+0F8h]; this
0x18002b8e6  lea     r8, aOnecoreVmDvSto_9; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18002b8ed  mov     edx, 4Dh ; 'M'; void *
0x18002b8f2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
