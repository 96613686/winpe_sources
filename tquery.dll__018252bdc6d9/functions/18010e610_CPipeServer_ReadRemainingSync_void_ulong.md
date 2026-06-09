# CPipeServer::ReadRemainingSync(void *,ulong &)

- ea: `0x18010e610`
- end: `0x18010e7a9`
- name: `?ReadRemainingSync@CPipeServer@@QEAAPEAEPEAXAEAK@Z`
- size: `409`
- prototype: `char *__fastcall(HANDLE *this, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180072360`

## callees

- `0x180073748`
- `0x180096740`
- `0x18010e610`
- `0x180147154`
- `0x180189280`
- `0x1801895b0`
- `0x180189cce`
- `0x18018e8cb`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010e725`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010e784`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010e784`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18010e71b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18010e71b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18010e741`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18010e741`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x18010e651`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x18010e651`

## string_xrefs

- `0x18010e678`: `[Proxy] peek says no more to read\n`

## pseudocode

```c
char *__fastcall CPipeServer::ReadRemainingSync(HANDLE *this, void *a2, unsigned int *a3)
{
  const char *v6; // r9
  unsigned __int64 v8; // rcx
  unsigned int v9; // ebx
  char *v10; // r14
  const wchar_t *v11; // r9
  HANDLE v12; // rbx
  const char *v13; // r9
  const char *v14; // r9
  struct _SECURITY_ATTRIBUTES *lpTotalBytesAvail; // [rsp+20h] [rbp-50h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-40h] BYREF
  int v17; // [rsp+40h] [rbp-30h]
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD BytesLeftThisMessage; // [rsp+A0h] [rbp+30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+B8h] [rbp+48h] BYREF

  BytesLeftThisMessage = 0;
  if ( !PeekNamedPipe(this[4], 0, 0, 0, 0, &BytesLeftThisMessage) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      v6);
  if ( BytesLeftThisMessage )
  {
    v8 = *a3 + BytesLeftThisMessage;
    v17 = v8;
    v9 = v8;
    v10 = (char *)operator new[](v8);
    hObject[1] = v10;
    memset_0(v10, 0, v9);
    memcpy_0(v10, a2, *a3);
    hObject[0] = 0;
    CEventSem::InternalCreate((CEventSem *)hObject, 1u, 0, v11, lpTotalBytesAvail);
    memset(&Overlapped, 0, 24);
    v12 = hObject[0];
    Overlapped.hEvent = hObject[0];
    NumberOfBytesRead = 0;
    if ( !ReadFile(this[4], &v10[*a3], BytesLeftThisMessage, &NumberOfBytesRead, &Overlapped) )
    {
      if ( GetLastError() != 997 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2BE,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
          v13);
      if ( !GetOverlappedResult(this[4], &Overlapped, &NumberOfBytesRead, 1) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2B9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
          v14);
    }
    *a3 += BytesLeftThisMessage;
    if ( v12 )
      CloseHandle(v12);
    operator delete(0);
    return v10;
  }
  else
  {
    SearchIndexerDebug::Warning(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const wchar_t *)0x2A6,
      (unsigned int)L"[Proxy] peek says no more to read\n",
      (const wchar_t *)v6);
    return 0;
  }
}

```

## disassembly

```asm
0x18010e610  mov     [rsp-28h+arg_8], rbx
0x18010e615  push    rbp
0x18010e616  push    rsi
0x18010e617  push    rdi
0x18010e618  push    r14
0x18010e61a  push    r15
0x18010e61c  mov     rbp, rsp
0x18010e61f  sub     rsp, 70h
0x18010e623  mov     rdi, r8
0x18010e626  mov     r15, rdx
0x18010e629  mov     rsi, rcx
0x18010e62c  mov     [rbp+BytesLeftThisMessage], 0
0x18010e633  lea     rax, [rbp+BytesLeftThisMessage]
0x18010e637  mov     [rsp+70h+lpBytesLeftThisMessage], rax; lpBytesLeftThisMessage
0x18010e63c  mov     [rsp+70h+lpTotalBytesAvail], 0; struct _SECURITY_ATTRIBUTES *
0x18010e645  xor     r9d, r9d; lpBytesRead
0x18010e648  xor     r8d, r8d; nBufferSize
0x18010e64b  xor     edx, edx; lpBuffer
0x18010e64d  mov     rcx, [rcx+20h]; hNamedPipe
0x18010e651  call    cs:__imp_PeekNamedPipe
0x18010e657  test    eax, eax
0x18010e659  jnz     short loc_18010E671
0x18010e65b  mov     rcx, [rbp+28h]; this
0x18010e65f  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010e666  mov     edx, 2A1h; void *
0x18010e66b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010e671  mov     ecx, [rbp+BytesLeftThisMessage]
0x18010e674  test    ecx, ecx
0x18010e676  jnz     short loc_18010E697
0x18010e678  lea     r8, aProxyPeekSaysN; "[Proxy] peek says no more to read\n"
0x18010e67f  mov     edx, 2A6h; wchar_t *
0x18010e684  lea     rcx, aOnecoreuapBase_192; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010e68b  call    ?Warning@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Warning(wchar_t const *,uint,wchar_t const *,...)
0x18010e690  xor     eax, eax
0x18010e692  jmp     loc_18010E795
0x18010e697  add     ecx, [rdi]; unsigned __int64
0x18010e699  mov     [rbp+var_30], ecx
0x18010e69c  mov     ebx, ecx
0x18010e69e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010e6a3  mov     r14, rax
0x18010e6a6  mov     [rbp+var_38], rax
0x18010e6aa  mov     r8d, ebx; Size
0x18010e6ad  xor     edx, edx; Val
0x18010e6af  mov     rcx, rax; void *
0x18010e6b2  call    memset_0
0x18010e6b7  nop
0x18010e6b8  mov     r8d, [rdi]; Size
0x18010e6bb  mov     rdx, r15; Src
0x18010e6be  mov     rcx, r14; void *
0x18010e6c1  call    memcpy_0
0x18010e6c6  mov     [rbp+hObject], 0
0x18010e6ce  xor     r8d, r8d; unsigned int
0x18010e6d1  lea     r15d, [r8+1]
0x18010e6d5  mov     edx, r15d; unsigned int
0x18010e6d8  lea     rcx, [rbp+hObject]; this
0x18010e6dc  call    ?InternalCreate@CEventSem@@IEAAXKKPEB_WQEAU_SECURITY_ATTRIBUTES@@@Z; CEventSem::InternalCreate(ulong,ulong,wchar_t const *,_SECURITY_ATTRIBUTES * const)
0x18010e6e1  nop
0x18010e6e2  mov     [rbp+Overlapped.Internal], 0
0x18010e6ea  xorps   xmm0, xmm0
0x18010e6ed  movdqu  xmmword ptr [rbp+Overlapped.InternalHigh], xmm0
0x18010e6f2  mov     rbx, [rbp+hObject]
0x18010e6f6  mov     [rbp+Overlapped.hEvent], rbx
0x18010e6fa  mov     [rbp+NumberOfBytesRead], 0
0x18010e701  mov     edx, [rdi]
0x18010e703  add     rdx, r14; lpBuffer
0x18010e706  lea     rax, [rbp+Overlapped]
0x18010e70a  mov     [rsp+70h+lpTotalBytesAvail], rax; lpOverlapped
0x18010e70f  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18010e713  mov     r8d, [rbp+BytesLeftThisMessage]; nNumberOfBytesToRead
0x18010e717  mov     rcx, [rsi+20h]; hFile
0x18010e71b  call    cs:__imp_ReadFile
0x18010e721  test    eax, eax
0x18010e723  jnz     short loc_18010E777
0x18010e725  call    cs:__imp_GetLastError
0x18010e72b  cmp     eax, 3E5h
0x18010e730  jnz     short loc_18010E761
0x18010e732  mov     r9d, r15d; bWait
0x18010e735  lea     r8, [rbp+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x18010e739  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x18010e73d  mov     rcx, [rsi+20h]; hFile
0x18010e741  call    cs:__imp_GetOverlappedResult
0x18010e747  test    eax, eax
0x18010e749  jnz     short loc_18010E777
0x18010e74b  mov     rcx, [rbp+28h]; this
0x18010e74f  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010e756  mov     edx, 2B9h; void *
0x18010e75b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010e761  mov     rcx, [rbp+28h]; this
0x18010e765  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010e76c  mov     edx, 2BEh; void *
0x18010e771  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010e777  mov     eax, [rbp+BytesLeftThisMessage]
0x18010e77a  add     [rdi], eax
0x18010e77c  test    rbx, rbx
0x18010e77f  jz      short loc_18010E78B
0x18010e781  mov     rcx, rbx; hObject
0x18010e784  call    cs:__imp_CloseHandle
0x18010e78a  nop
0x18010e78b  xor     ecx, ecx; Block
0x18010e78d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010e792  mov     rax, r14
0x18010e795  mov     rbx, [rsp+70h+arg_8]
0x18010e79d  add     rsp, 70h
0x18010e7a1  pop     r15
0x18010e7a3  pop     r14
0x18010e7a5  pop     rdi
0x18010e7a6  pop     rsi
0x18010e7a7  pop     rbp
0x18010e7a8  retn
```
