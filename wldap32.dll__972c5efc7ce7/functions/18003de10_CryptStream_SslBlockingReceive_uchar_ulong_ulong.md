# CryptStream::SslBlockingReceive(uchar *,ulong,ulong *)

- ea: `0x18003de10`
- end: `0x18003df35`
- name: `?SslBlockingReceive@CryptStream@@QEAAKPEAEKPEAK@Z`
- size: `293`
- prototype: `unsigned int(CryptStream *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003d78c`
- `0x18003df3c`

## callees

- `0x1800037a8`
- `0x180034510`
- `0x180034e6c`
- `0x18003de10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003dee3`
- `WS2_32!__imp_recv` at `0x18003deb1`
- `WS2_32!__imp_recv` at `0x18003deb1`
- `WS2_32!__imp_select` at `0x18003de8c`
- `WS2_32!__imp_select` at `0x18003de8c`

## string_xrefs

- `0x18003def2`: `ldapSslBlockingRecv thread 0x%x has connection 0x%x as down.\n`

## pseudocode

```c
__int64 __fastcall CryptStream::SslBlockingReceive(CryptStream *this, char *a2, int a3, unsigned int *a4)
{
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rbx
  DWORD CurrentThreadId; // eax
  struct timeval timeout; // [rsp+30h] [rbp-258h] BYREF
  fd_set readfds; // [rsp+40h] [rbp-248h] BYREF

  memset_0(&readfds.fd_count + 1, 0, 0x204u);
  v8 = *((_QWORD *)this + 2);
  readfds.fd_count = 0;
  timeout = (struct timeval)30LL;
  readfds.fd_array[0] = *(_QWORD *)(v8 + 904);
  readfds.fd_count = 1;
  if ( select(0, &readfds, 0, 0, &timeout) != 1 )
    return 85;
  v9 = recv(*(_QWORD *)(*((_QWORD *)this + 2) + 904LL), a2, a3, 0);
  if ( v9 == -1 )
    return 85;
  if ( v9 )
  {
    *a4 = v9;
    return 0;
  }
  else
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x80u) != 0LL )
    {
      v10 = *((_QWORD *)this + 2);
      CurrentThreadId = GetCurrentThreadId();
      LDAPClientPrint(128, "ldapSslBlockingRecv thread 0x%x has connection 0x%x as down.\n", CurrentThreadId, v10);
    }
    return 81;
  }
}

```

## disassembly

```asm
0x18003de10  push    rbx
0x18003de12  push    rbp
0x18003de13  push    rsi
0x18003de14  push    rdi
0x18003de15  sub     rsp, 268h
0x18003de1c  mov     rax, cs:__security_cookie
0x18003de23  xor     rax, rsp
0x18003de26  mov     [rsp+288h+var_38], rax
0x18003de2e  mov     ebp, r8d
0x18003de31  mov     rsi, rdx
0x18003de34  mov     rbx, rcx
0x18003de37  xor     edx, edx; Val
0x18003de39  mov     r8d, 204h; Size
0x18003de3f  lea     rcx, [rsp+288h+readfds+4]; void *
0x18003de44  mov     rdi, r9
0x18003de47  call    memset_0
0x18003de4c  mov     rax, [rbx+10h]
0x18003de50  lea     rdx, [rsp+288h+readfds]; readfds
0x18003de55  mov     [rsp+288h+readfds.fd_count], 0
0x18003de5d  xor     r9d, r9d; exceptfds
0x18003de60  mov     qword ptr [rsp+288h+var_258.tv_sec], 1Eh
0x18003de69  xor     r8d, r8d; writefds
0x18003de6c  mov     rcx, [rax+388h]
0x18003de73  lea     rax, [rsp+288h+var_258]
0x18003de78  mov     [rsp+288h+readfds.fd_array], rcx
0x18003de7d  xor     ecx, ecx; nfds
0x18003de7f  mov     [rsp+288h+readfds.fd_count], 1
0x18003de87  mov     [rsp+288h+timeout], rax; timeout
0x18003de8c  call    cs:__imp_select
0x18003de93  nop     dword ptr [rax+rax+00h]
0x18003de98  cmp     eax, 1
0x18003de9b  jnz     short loc_18003DF13
0x18003de9d  mov     rcx, [rbx+10h]
0x18003dea1  xor     r9d, r9d; flags
0x18003dea4  mov     r8d, ebp; len
0x18003dea7  mov     rdx, rsi; buf
0x18003deaa  mov     rcx, [rcx+388h]; s
0x18003deb1  call    cs:__imp_recv
0x18003deb8  nop     dword ptr [rax+rax+00h]
0x18003debd  cmp     eax, 0FFFFFFFFh
0x18003dec0  jz      short loc_18003DF13
0x18003dec2  test    eax, eax
0x18003dec4  jnz     short loc_18003DF0D
0x18003dec6  cmp     cs:g_fTracingOn, eax
0x18003decc  jz      short loc_18003DF06
0x18003dece  cmp     cs:g_fProviderEnabled, eax
0x18003ded4  jz      short loc_18003DF06
0x18003ded6  test    byte ptr cs:g_ulTraceFlags, 80h
0x18003dedd  jz      short loc_18003DF06
0x18003dedf  mov     rbx, [rbx+10h]
0x18003dee3  call    cs:__imp_GetCurrentThreadId
0x18003deea  nop     dword ptr [rax+rax+00h]
0x18003deef  mov     r9, rbx
0x18003def2  lea     rdx, aLdapsslblockin; "ldapSslBlockingRecv thread 0x%x has con"...
0x18003def9  mov     r8d, eax
0x18003defc  mov     ecx, 80h
0x18003df01  call    LDAPClientPrint
0x18003df06  mov     eax, 51h ; 'Q'
0x18003df0b  jmp     short loc_18003DF18
0x18003df0d  mov     [rdi], eax
0x18003df0f  xor     eax, eax
0x18003df11  jmp     short loc_18003DF18
0x18003df13  mov     eax, 55h ; 'U'
0x18003df18  mov     rcx, [rsp+288h+var_38]
0x18003df20  xor     rcx, rsp; StackCookie
0x18003df23  call    __security_check_cookie
0x18003df28  add     rsp, 268h
0x18003df2f  pop     rdi
0x18003df30  pop     rsi
0x18003df31  pop     rbp
0x18003df32  pop     rbx
0x18003df33  retn
```
