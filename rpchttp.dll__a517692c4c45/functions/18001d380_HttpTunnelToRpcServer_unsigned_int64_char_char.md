# HttpTunnelToRpcServer(unsigned __int64,char *,char *)

- ea: `0x18001d380`
- end: `0x18001d440`
- name: `?HttpTunnelToRpcServer@@YAH_KPEAD1@Z`
- size: `192`
- prototype: `__int64 __fastcall(SOCKET s, char *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18000c1a0`

## callees

- `0x18001d1d8`
- `0x18001d380`
- `0x18001da1c`
- `0x18001da8c`
- `0x180024640`

## string_xrefs

- `0x18001d3f9`: ` HTTP/1.1\nUser-Agent: RPC\nPragma: No-Cache\n\n`

## pseudocode

```c
__int64 __fastcall HttpTunnelToRpcServer(SOCKET s, char *a2, char *a3)
{
  unsigned __int64 v5; // rdx
  const char *v6; // r10
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  char v11[1024]; // [rsp+30h] [rbp-418h] BYREF

  if ( (int)RtlStringCopyWorkerA(v11, 1024, a3, "RPC_CONNECT ") < 0
    || (int)RtlStringCbCatA(v11, v5, v6) < 0
    || (int)RtlStringCbCatA(v11, v7, ":") < 0
    || (int)RtlStringCbCatA(v11, v8, a3) < 0
    || (int)RtlStringCbCatA(v11, v9, " HTTP/1.1\nUser-Agent: RPC\nPragma: No-Cache\n\n") < 0 )
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
0x18001d380  mov     [rsp+arg_18], rbx
0x18001d385  push    rdi
0x18001d386  sub     rsp, 440h
0x18001d38d  mov     rax, cs:__security_cookie
0x18001d394  xor     rax, rsp
0x18001d397  mov     [rsp+448h+var_18], rax
0x18001d39f  mov     r10, rdx
0x18001d3a2  lea     r9, aRpcConnect; "RPC_CONNECT "
0x18001d3a9  mov     rbx, rcx
0x18001d3ac  mov     edx, 400h
0x18001d3b1  lea     rcx, [rsp+448h+var_418]
0x18001d3b6  mov     rdi, r8
0x18001d3b9  call    RtlStringCopyWorkerA
0x18001d3be  test    eax, eax
0x18001d3c0  js      short loc_18001D41D
0x18001d3c2  mov     r8, r10; char *
0x18001d3c5  lea     rcx, [rsp+448h+var_418]; char *
0x18001d3ca  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d3cf  test    eax, eax
0x18001d3d1  js      short loc_18001D41D
0x18001d3d3  lea     r8, asc_1800281B8; ":"
0x18001d3da  lea     rcx, [rsp+448h+var_418]; char *
0x18001d3df  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d3e4  test    eax, eax
0x18001d3e6  js      short loc_18001D41D
0x18001d3e8  mov     r8, rdi; char *
0x18001d3eb  lea     rcx, [rsp+448h+var_418]; char *
0x18001d3f0  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d3f5  test    eax, eax
0x18001d3f7  js      short loc_18001D41D
0x18001d3f9  lea     r8, aHttp11UserAgen; " HTTP/1.1\nUser-Agent: RPC\nPragma: No-"...
0x18001d400  lea     rcx, [rsp+448h+var_418]; char *
0x18001d405  call    ?RtlStringCbCatA@@YAJPEAD_KPEBD@Z; RtlStringCbCatA(char *,unsigned __int64,char const *)
0x18001d40a  test    eax, eax
0x18001d40c  js      short loc_18001D41D
0x18001d40e  lea     rdx, [rsp+448h+var_418]
0x18001d413  mov     rcx, rbx; s
0x18001d416  call    HttpSetupTunnel
0x18001d41b  jmp     short loc_18001D41F
0x18001d41d  xor     eax, eax
0x18001d41f  mov     rcx, [rsp+448h+var_18]
0x18001d427  xor     rcx, rsp; StackCookie
0x18001d42a  call    __security_check_cookie
0x18001d42f  mov     rbx, [rsp+448h+arg_18]
0x18001d437  add     rsp, 440h
0x18001d43e  pop     rdi
0x18001d43f  retn
```
