# HttpTunnelToRpcProxy(unsigned __int64,char *,char *)

- ea: `0x18001d2b8`
- end: `0x18001d378`
- name: `?HttpTunnelToRpcProxy@@YAH_KPEAD1@Z`
- size: `192`
- prototype: `__int64 __fastcall(SOCKET s, char *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18000c1a0`

## callees

- `0x18001d1d8`
- `0x18001d2b8`
- `0x18001da1c`
- `0x18001da8c`
- `0x180024640`

## string_xrefs

- `0x18001d331`: ` HTTP/1.0\nUser-Agent: RPC\nConnection: Keep-Alive\n\n`

## pseudocode

```c
__int64 __fastcall HttpTunnelToRpcProxy(SOCKET s, char *a2, char *a3)
{
  unsigned __int64 v5; // rdx
  const char *v6; // r10
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  char v11[1024]; // [rsp+30h] [rbp-418h] BYREF

  if ( (int)RtlStringCopyWorkerA(v11, 1024, a3, "CONNECT ") < 0
    || (int)RtlStringCbCatA(v11, v5, v6) < 0
    || (int)RtlStringCbCatA(v11, v7, ":") < 0
    || (int)RtlStringCbCatA(v11, v8, a3) < 0
    || (int)RtlStringCbCatA(v11, v9, " HTTP/1.0\r\nUser-Agent: RPC\r\nConnection: Keep-Alive\r\n\r\n") < 0 )
  {
    return 0;
  }
  else
  {
    return HttpSetupTunnel(s);
  }
}

```

## disassembly

```asm
0x18001d2b8  mov     [rsp+arg_18], rbx
0x18001d2bd  push    rdi
0x18001d2be  sub     rsp, 440h
0x18001d2c5  mov     rax, cs:__security_cookie
0x18001d2cc  xor     rax, rsp
0x18001d2cf  mov     [rsp+448h+var_18], rax
0x18001d2d7  mov     r10, rdx
0x18001d2da  lea     r9, aConnect; "CONNECT "
0x18001d2e1  mov     rbx, rcx
0x18001d2e4  mov     edx, 400h
0x18001d2e9  lea     rcx, [rsp+448h+var_418]
0x18001d2ee  mov     rdi, r8
0x18001d2f1  call    RtlStringCopyWorkerA
0x18001d2f6  test    eax, eax
0x18001d2f8  js      short loc_18001D355
0x18001d2fa  mov     r8, r10; char *
0x18001d2fd  lea     rcx, [rsp+448h+var_418]; char *
0x18001d302  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d307  test    eax, eax
0x18001d309  js      short loc_18001D355
0x18001d30b  lea     r8, asc_1800281B8; ":"
0x18001d312  lea     rcx, [rsp+448h+var_418]; char *
0x18001d317  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d31c  test    eax, eax
0x18001d31e  js      short loc_18001D355
0x18001d320  mov     r8, rdi; char *
0x18001d323  lea     rcx, [rsp+448h+var_418]; char *
0x18001d328  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d32d  test    eax, eax
0x18001d32f  js      short loc_18001D355
0x18001d331  lea     r8, aHttp10UserAgen; " HTTP/1.0\r\nUser-Agent: RPC\r\nConnect"...
0x18001d338  lea     rcx, [rsp+448h+var_418]; char *
0x18001d33d  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d342  test    eax, eax
0x18001d344  js      short loc_18001D355
0x18001d346  lea     rdx, [rsp+448h+var_418]
0x18001d34b  mov     rcx, rbx; s
0x18001d34e  call    HttpSetupTunnel
0x18001d353  jmp     short loc_18001D357
0x18001d355  xor     eax, eax
0x18001d357  mov     rcx, [rsp+448h+var_18]
0x18001d35f  xor     rcx, rsp; StackCookie
0x18001d362  call    __security_check_cookie
0x18001d367  mov     rbx, [rsp+448h+arg_18]
0x18001d36f  add     rsp, 440h
0x18001d376  pop     rdi
0x18001d377  retn
```
