# HTTP2WinHttpTransportChannel::Send(HTTP2SendContext *)

- ea: `0x180017e90`
- end: `0x180017ffc`
- name: `?Send@HTTP2WinHttpTransportChannel@@UEAAJPEAVHTTP2SendContext@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(HTTP2WinHttpTransportChannel *__hidden this, struct HTTP2SendContext *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018010`

## callees

- `0x180017e90`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180017f12`
- `ntdll!RtlLeaveCriticalSection` at `0x180017f4f`
- `ntdll!RtlLeaveCriticalSection` at `0x180017f12`
- `ntdll!RtlLeaveCriticalSection` at `0x180017f4f`
- `ntdll!RtlEnterCriticalSection` at `0x180017ed1`
- `ntdll!RtlEnterCriticalSection` at `0x180017ed1`
- `KERNEL32!GetLastError` at `0x180017fb4`
- `KERNEL32!GetLastError` at `0x180017fb4`
- `RPCRT4!I_RpcLogEvent` at `0x180017ec4`
- `RPCRT4!I_RpcLogEvent` at `0x180017f3f`
- `RPCRT4!I_RpcLogEvent` at `0x180017f8b`
- `RPCRT4!I_RpcLogEvent` at `0x180017fe4`
- `RPCRT4!I_RpcLogEvent` at `0x180017ec4`
- `RPCRT4!I_RpcLogEvent` at `0x180017f3f`
- `RPCRT4!I_RpcLogEvent` at `0x180017f8b`
- `RPCRT4!I_RpcLogEvent` at `0x180017fe4`
- `WINHTTP!WinHttpWriteData` at `0x180017fa0`
- `WINHTTP!WinHttpWriteData` at `0x180017fa0`

## pseudocode

```c
__int64 __fastcall HTTP2WinHttpTransportChannel::Send(HTTP2WinHttpTransportChannel *this, struct HTTP2SendContext *a2)
{
  struct HTTP2SendContext *v2; // rdi
  HTTP2WinHttpTransportChannel *v3; // rbx
  HTTP2WinHttpTransportChannel *v4; // r8
  HTTP2WinHttpTransportChannel **v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-28h]

  v2 = a2;
  v3 = this;
  v4 = this;
  v15 = (int)a2;
  LOBYTE(a2) = 111;
  LOBYTE(this) = 50;
  I_RpcLogEvent(this, a2, v4, 16842773, v15, 0, 0);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)v3 + 104));
  if ( (int)++*((_DWORD *)v3 + 48) <= 1 )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v3 + 104));
    v9 = *((_QWORD *)v3 + 9);
    *((_DWORD *)v3 + 45) = 6;
    LOBYTE(v10) = 111;
    *((_QWORD *)v3 + 23) = v2;
    LOBYTE(v11) = 50;
    I_RpcLogEvent(v11, v10, v9, 25624598, *((_DWORD *)v2 + 14), 0, 0);
    if ( WinHttpWriteData(*((HINTERNET *)v3 + 9), *((LPCVOID *)v2 + 6), *((_DWORD *)v2 + 14), 0) )
    {
      v14 = 0;
    }
    else
    {
      *((_DWORD *)v3 + 45) = 3;
      GetLastError();
      v14 = -1073606646;
    }
    LOBYTE(v12) = 111;
    LOBYTE(v13) = 50;
    I_RpcLogEvent(v13, v12, v3, 65557, v14, 0, 0);
    return v14;
  }
  else
  {
    v5 = (HTTP2WinHttpTransportChannel **)*((_QWORD *)v3 + 19);
    if ( *v5 != (HTTP2WinHttpTransportChannel *)((char *)v3 + 144) )
      __fastfail(3u);
    *((_QWORD *)v2 + 9) = (char *)v3 + 144;
    *((_QWORD *)v2 + 10) = v5;
    *v5 = (struct HTTP2SendContext *)((char *)v2 + 72);
    *((_QWORD *)v3 + 19) = (char *)v2 + 72;
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)v3 + 104));
    LOBYTE(v6) = 111;
    LOBYTE(v7) = 50;
    I_RpcLogEvent(v7, v6, v3, 65557, *((_DWORD *)v3 + 48), 0, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180017e90  mov     rax, rsp
0x180017e93  mov     [rax+8], rbx
0x180017e97  mov     [rax+10h], rsi
0x180017e9b  push    rdi
0x180017e9c  sub     rsp, 40h
0x180017ea0  mov     rdi, rdx
0x180017ea3  mov     dword ptr [rax-18h], 0
0x180017eaa  mov     rbx, rcx
0x180017ead  mov     dword ptr [rax-20h], 0
0x180017eb4  mov     r8, rcx
0x180017eb7  mov     [rax-28h], edi
0x180017eba  mov     dl, 6Fh ; 'o'
0x180017ebc  mov     cl, 32h ; '2'
0x180017ebe  mov     r9d, 1010015h
0x180017ec4  call    cs:__imp_I_RpcLogEvent
0x180017eca  lea     rsi, [rbx+68h]
0x180017ece  mov     rcx, rsi; CriticalSection
0x180017ed1  call    cs:__imp_RtlEnterCriticalSection
0x180017ed7  inc     dword ptr [rbx+0C0h]
0x180017edd  cmp     dword ptr [rbx+0C0h], 1
0x180017ee4  jle     short loc_180017F4C
0x180017ee6  lea     rcx, [rbx+90h]
0x180017eed  mov     rdx, [rcx+8]
0x180017ef1  cmp     [rdx], rcx
0x180017ef4  jz      short loc_180017EFD
0x180017ef6  mov     ecx, 3
0x180017efb  int     29h; Win8: RtlFailFast(ecx)
0x180017efd  lea     rax, [rdi+48h]
0x180017f01  mov     [rax], rcx
0x180017f04  mov     [rax+8], rdx
0x180017f08  mov     [rdx], rax
0x180017f0b  mov     [rcx+8], rax
0x180017f0f  mov     rcx, rsi; CriticalSection
0x180017f12  call    cs:__imp_RtlLeaveCriticalSection
0x180017f18  mov     eax, [rbx+0C0h]
0x180017f1e  mov     r9d, 10015h
0x180017f24  mov     [rsp+48h+var_18], 0
0x180017f2c  mov     r8, rbx
0x180017f2f  mov     [rsp+48h+var_20], 0
0x180017f37  mov     dl, 6Fh ; 'o'
0x180017f39  mov     cl, 32h ; '2'
0x180017f3b  mov     [rsp+48h+var_28], eax
0x180017f3f  call    cs:__imp_I_RpcLogEvent
0x180017f45  xor     eax, eax
0x180017f47  jmp     loc_180017FEC
0x180017f4c  mov     rcx, rsi; CriticalSection
0x180017f4f  call    cs:__imp_RtlLeaveCriticalSection
0x180017f55  mov     r8, [rbx+48h]
0x180017f59  mov     r9d, 1870016h
0x180017f5f  mov     dword ptr [rbx+0B4h], 6
0x180017f69  mov     dl, 6Fh ; 'o'
0x180017f6b  mov     [rbx+0B8h], rdi
0x180017f72  mov     cl, 32h ; '2'
0x180017f74  mov     eax, [rdi+38h]
0x180017f77  mov     [rsp+48h+var_18], 0
0x180017f7f  mov     [rsp+48h+var_20], 0
0x180017f87  mov     [rsp+48h+var_28], eax
0x180017f8b  call    cs:__imp_I_RpcLogEvent
0x180017f91  mov     r8d, [rdi+38h]; dwNumberOfBytesToWrite
0x180017f95  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x180017f98  mov     rdx, [rdi+30h]; lpBuffer
0x180017f9c  mov     rcx, [rbx+48h]; hRequest
0x180017fa0  call    cs:__imp_WinHttpWriteData
0x180017fa6  test    eax, eax
0x180017fa8  jnz     short loc_180017FC1
0x180017faa  mov     dword ptr [rbx+0B4h], 3
0x180017fb4  call    cs:__imp_GetLastError
0x180017fba  mov     edi, 0C002100Ah
0x180017fbf  jmp     short loc_180017FC3
0x180017fc1  xor     edi, edi
0x180017fc3  mov     [rsp+48h+var_18], 0
0x180017fcb  mov     r9d, 10015h
0x180017fd1  mov     [rsp+48h+var_20], 0
0x180017fd9  mov     r8, rbx
0x180017fdc  mov     dl, 6Fh ; 'o'
0x180017fde  mov     [rsp+48h+var_28], edi
0x180017fe2  mov     cl, 32h ; '2'
0x180017fe4  call    cs:__imp_I_RpcLogEvent
0x180017fea  mov     eax, edi
0x180017fec  mov     rbx, [rsp+48h+arg_0]
0x180017ff1  mov     rsi, [rsp+48h+arg_8]
0x180017ff6  add     rsp, 40h
0x180017ffa  pop     rdi
0x180017ffb  retn
```
