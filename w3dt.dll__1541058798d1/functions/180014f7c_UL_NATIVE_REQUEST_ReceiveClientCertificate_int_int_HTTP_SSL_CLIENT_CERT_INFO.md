# UL_NATIVE_REQUEST::ReceiveClientCertificate(int,int,_HTTP_SSL_CLIENT_CERT_INFO * *)

- ea: `0x180014f7c`
- end: `0x180015206`
- name: `?ReceiveClientCertificate@UL_NATIVE_REQUEST@@QEAAJHHPEAPEAU_HTTP_SSL_CLIENT_CERT_INFO@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(UL_NATIVE_REQUEST *__hidden this, int, int, struct _HTTP_SSL_CLIENT_CERT_INFO **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800158d0`

## callees

- `0x180012050`
- `0x180014f7c`
- `0x180016072`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001515c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001515c`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x1800150c8`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180015147`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x1800150c8`
- `HTTPAPI!HttpReceiveClientCertificate` at `0x180015147`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015025`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001503b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001510b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015025`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001503b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001510b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180015086`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180015117`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180015086`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180015117`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180014ffd`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800150f4`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180014ffd`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800150f4`

## pseudocode

```c
signed int __fastcall UL_NATIVE_REQUEST::ReceiveClientCertificate(
        UL_NATIVE_REQUEST *this,
        int a2,
        __int64 a3,
        struct _HTTP_SSL_CLIENT_CERT_INFO **a4)
{
  signed int result; // eax
  __int64 v8; // rsi
  __int64 v9; // rax
  struct _HTTP_SSL_CLIENT_CERT_INFO *v10; // rax
  BUFFER *v11; // rbp
  void *Ptr; // rax
  struct _HTTP_SSL_CLIENT_CERT_INFO *v13; // r13
  void *v14; // r12
  ULONG SslClientCertInfoSize; // eax
  ULONG v16; // eax
  signed int v17; // ebx
  ULONG LastError; // eax
  ULONG Size; // eax
  __int64 v20; // rax
  ULONG BytesReceived; // [rsp+90h] [rbp+18h] BYREF
  PSRWLOCK SRWLock; // [rsp+98h] [rbp+20h] BYREF

  BytesReceived = 0;
  SRWLock = 0;
  if ( !a4 )
    return -2147024809;
  *a4 = 0;
  v8 = *((_QWORD *)this + 368);
  v9 = *(_QWORD *)(v8 + 840);
  if ( !v9 )
    return -2147024846;
  v10 = *(struct _HTTP_SSL_CLIENT_CERT_INFO **)(v9 + 32);
  if ( v10 )
  {
    *a4 = v10;
    return 0;
  }
  v11 = (UL_NATIVE_REQUEST *)((char *)this + 2960);
  if ( !BUFFER::Resize((UL_NATIVE_REQUEST *)((char *)this + 2960), 0x5DCu) )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  Ptr = BUFFER::QueryPtr(v11);
  memset_0(Ptr, 0, 0x5DCu);
  v13 = (struct _HTTP_SSL_CLIENT_CERT_INFO *)BUFFER::QueryPtr(v11);
  if ( a2 )
    *((_DWORD *)this + 1) = 4;
  v14 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), &SRWLock);
  if ( v14 )
  {
    if ( a2 )
      _InterlockedIncrement((volatile signed __int32 *)this + 784);
    SslClientCertInfoSize = BUFFER::QuerySize(v11);
    v16 = HttpReceiveClientCertificate(
            v14,
            *(_QWORD *)(*((_QWORD *)this + 368) + 8LL),
            0,
            v13,
            SslClientCertInfoSize,
            &BytesReceived,
            (LPOVERLAPPED)(((unsigned __int64)this + 3104) & -(__int64)(a2 != 0)));
    v17 = v16;
    if ( a2 && v16 != 997 )
      _InterlockedDecrement((volatile signed __int32 *)this + 784);
    if ( v16 == 234 )
    {
      if ( BUFFER::Resize(v11, v13->CertEncodedSize + 32) )
      {
        v13 = (struct _HTTP_SSL_CLIENT_CERT_INFO *)BUFFER::QueryPtr(v11);
        Size = BUFFER::QuerySize(v11);
        LastError = HttpReceiveClientCertificate(v14, *(_QWORD *)(*((_QWORD *)this + 368) + 8LL), 0, v13, Size, 0, 0);
      }
      else
      {
        LastError = GetLastError();
      }
      v17 = LastError;
    }
  }
  else
  {
    v17 = 6;
  }
  ReleaseSRWLockShared(SRWLock);
  if ( a2 )
  {
    if ( v17 == 997 )
    {
LABEL_28:
      v17 = (unsigned __int16)v17 | 0x80070000;
      goto LABEL_29;
    }
    *((_DWORD *)this + 1) = 2;
  }
  if ( v17 > 0 )
    goto LABEL_28;
LABEL_29:
  if ( v17 != -2147023899 )
  {
    *(_DWORD *)(*(_QWORD *)(v8 + 840) + 40LL) = 1;
    if ( v17 == -2147023728 )
    {
      *(_QWORD *)(*(_QWORD *)(v8 + 840) + 32LL) = 0;
    }
    else if ( v17 >= 0 )
    {
      *((_QWORD *)this + 376) = v13->Token;
      *(_QWORD *)(*(_QWORD *)(v8 + 840) + 32LL) = v13;
      v20 = *(_QWORD *)(v8 + 840);
      if ( !*(_DWORD *)(*(_QWORD *)(v20 + 32) + 4LL) )
        *(_QWORD *)(v20 + 32) = 0;
      *a4 = *(struct _HTTP_SSL_CLIENT_CERT_INFO **)(*(_QWORD *)(v8 + 840) + 32LL);
    }
  }
  return v17;
}

```

## disassembly

```asm
0x180014f7c  mov     rax, rsp
0x180014f7f  mov     [rax+8], rbx
0x180014f83  mov     [rax+18h], r8d
0x180014f87  push    rbp
0x180014f88  push    rsi
0x180014f89  push    rdi
0x180014f8a  push    r12
0x180014f8c  push    r13
0x180014f8e  push    r14
0x180014f90  push    r15
0x180014f92  sub     rsp, 40h
0x180014f96  xor     ebx, ebx
0x180014f98  mov     r14, r9
0x180014f9b  mov     [rax+18h], ebx
0x180014f9e  mov     r15d, edx
0x180014fa1  mov     [rax+20h], rbx
0x180014fa5  mov     rdi, rcx
0x180014fa8  test    r9, r9
0x180014fab  jnz     short loc_180014FB7
0x180014fad  mov     eax, 80070057h
0x180014fb2  jmp     loc_1800151EE
0x180014fb7  mov     [r9], rbx
0x180014fba  mov     rsi, [rcx+0B80h]
0x180014fc1  mov     rax, [rsi+348h]
0x180014fc8  test    rax, rax
0x180014fcb  jnz     short loc_180014FD7
0x180014fcd  mov     eax, 80070032h
0x180014fd2  jmp     loc_1800151EE
0x180014fd7  mov     rax, [rax+20h]
0x180014fdb  test    rax, rax
0x180014fde  jz      short loc_180014FEA
0x180014fe0  mov     [r9], rax
0x180014fe3  xor     eax, eax
0x180014fe5  jmp     loc_1800151EE
0x180014fea  lea     rbp, [rcx+0B90h]
0x180014ff1  mov     r12d, 5DCh
0x180014ff7  mov     edx, r12d
0x180014ffa  mov     rcx, rbp
0x180014ffd  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180015003  test    al, al
0x180015005  jnz     short loc_180015022
0x180015007  call    cs:__imp_GetLastError
0x18001500d  test    eax, eax
0x18001500f  jle     loc_1800151EE
0x180015015  movzx   eax, ax
0x180015018  or      eax, 80070000h
0x18001501d  jmp     loc_1800151EE
0x180015022  mov     rcx, rbp
0x180015025  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001502b  mov     r8, r12; Size
0x18001502e  xor     edx, edx; Val
0x180015030  mov     rcx, rax; void *
0x180015033  call    memset_0
0x180015038  mov     rcx, rbp
0x18001503b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015041  mov     r13, rax
0x180015044  test    r15d, r15d
0x180015047  jz      short loc_180015050
0x180015049  mov     dword ptr [rdi+4], 4
0x180015050  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x180015057  lea     rdx, [rsp+78h+SRWLock]; void **
0x18001505f  add     rcx, 2F8h; this
0x180015066  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x18001506b  mov     r12, rax
0x18001506e  test    rax, rax
0x180015071  jz      loc_18001514F
0x180015077  test    r15d, r15d
0x18001507a  jz      short loc_180015083
0x18001507c  lock inc dword ptr [rdi+0C40h]
0x180015083  mov     rcx, rbp
0x180015086  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18001508c  mov     ecx, r15d
0x18001508f  lea     rdx, [rdi+0C20h]
0x180015096  neg     ecx
0x180015098  mov     r9, r13; SslClientCertInfo
0x18001509b  lea     rcx, [rsp+78h+arg_10]
0x1800150a3  sbb     r8, r8
0x1800150a6  and     r8, rdx
0x1800150a9  mov     rdx, [rdi+0B80h]
0x1800150b0  mov     [rsp+78h+Overlapped], r8; Overlapped
0x1800150b5  xor     r8d, r8d; Flags
0x1800150b8  mov     [rsp+78h+BytesReceived], rcx; BytesReceived
0x1800150bd  mov     rcx, r12; RequestQueueHandle
0x1800150c0  mov     [rsp+78h+SslClientCertInfoSize], eax; SslClientCertInfoSize
0x1800150c4  mov     rdx, [rdx+8]; ConnectionId
0x1800150c8  call    cs:__imp_HttpReceiveClientCertificate
0x1800150ce  mov     ebx, eax
0x1800150d0  test    r15d, r15d
0x1800150d3  jz      short loc_1800150E3
0x1800150d5  cmp     eax, 3E5h
0x1800150da  jz      short loc_1800150E3
0x1800150dc  lock dec dword ptr [rdi+0C40h]
0x1800150e3  cmp     eax, 0EAh
0x1800150e8  jnz     short loc_180015154
0x1800150ea  mov     edx, [r13+4]
0x1800150ee  mov     rcx, rbp
0x1800150f1  add     edx, 20h ; ' '
0x1800150f4  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800150fa  test    al, al
0x1800150fc  jnz     short loc_180015108
0x1800150fe  call    cs:__imp_GetLastError
0x180015104  mov     ebx, eax
0x180015106  jmp     short loc_180015154
0x180015108  mov     rcx, rbp
0x18001510b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015111  mov     rcx, rbp
0x180015114  mov     r13, rax
0x180015117  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18001511d  mov     rdx, [rdi+0B80h]
0x180015124  mov     r9, r13; SslClientCertInfo
0x180015127  mov     [rsp+78h+Overlapped], 0; Overlapped
0x180015130  xor     r8d, r8d; Flags
0x180015133  mov     [rsp+78h+BytesReceived], 0; BytesReceived
0x18001513c  mov     rcx, r12; RequestQueueHandle
0x18001513f  mov     [rsp+78h+SslClientCertInfoSize], eax; SslClientCertInfoSize
0x180015143  mov     rdx, [rdx+8]; ConnectionId
0x180015147  call    cs:__imp_HttpReceiveClientCertificate
0x18001514d  jmp     short loc_180015104
0x18001514f  mov     ebx, 6
0x180015154  mov     rcx, [rsp+78h+SRWLock]; SRWLock
0x18001515c  call    cs:__imp_ReleaseSRWLockShared
0x180015162  xor     edx, edx
0x180015164  test    r15d, r15d
0x180015167  jz      short loc_180015178
0x180015169  cmp     ebx, 3E5h
0x18001516f  jz      short loc_18001517C
0x180015171  mov     dword ptr [rdi+4], 2
0x180015178  test    ebx, ebx
0x18001517a  jle     short loc_180015185
0x18001517c  movzx   ebx, bx
0x18001517f  or      ebx, 80070000h
0x180015185  cmp     ebx, 800703E5h
0x18001518b  jz      short loc_1800151EC
0x18001518d  mov     rax, [rsi+348h]
0x180015194  mov     dword ptr [rax+28h], 1
0x18001519b  cmp     ebx, 80070490h
0x1800151a1  jnz     short loc_1800151B0
0x1800151a3  mov     rax, [rsi+348h]
0x1800151aa  mov     [rax+20h], rdx
0x1800151ae  jmp     short loc_1800151EC
0x1800151b0  test    ebx, ebx
0x1800151b2  js      short loc_1800151EC
0x1800151b4  mov     rax, [r13+10h]
0x1800151b8  mov     [rdi+0BC0h], rax
0x1800151bf  mov     rax, [rsi+348h]
0x1800151c6  mov     [rax+20h], r13
0x1800151ca  mov     rax, [rsi+348h]
0x1800151d1  mov     rcx, [rax+20h]
0x1800151d5  cmp     [rcx+4], edx
0x1800151d8  jnz     short loc_1800151DE
0x1800151da  mov     [rax+20h], rdx
0x1800151de  mov     rcx, [rsi+348h]
0x1800151e5  mov     rdx, [rcx+20h]
0x1800151e9  mov     [r14], rdx
0x1800151ec  mov     eax, ebx
0x1800151ee  mov     rbx, [rsp+78h+arg_0]
0x1800151f6  add     rsp, 40h
0x1800151fa  pop     r15
0x1800151fc  pop     r14
0x1800151fe  pop     r13
0x180015200  pop     r12
0x180015202  pop     rdi
0x180015203  pop     rsi
0x180015204  pop     rbp
0x180015205  retn
```
