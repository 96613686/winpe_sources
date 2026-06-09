# SspiSrvClientCallback

- ea: `0x180002740`
- end: `0x180002832`
- name: `SspiSrvClientCallback`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002740`
- `0x1800033f0`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x18000351a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000351a`
- `RPCRT4!NdrClientCall3` at `0x1800027cc`
- `RPCRT4!NdrClientCall3` at `0x1800027cc`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800027e5`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800027e5`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspiSrvClientCallback(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _OWORD *a6)
{
  CLIENT_CALL_RETURN result; // rax
  __int128 v7; // [rsp+70h] [rbp-48h] BYREF
  _DWORD v8[2]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v9; // [rsp+88h] [rbp-30h]

  v7 = 0;
  v8[0] = *(_DWORD *)a5;
  v8[1] = *(_DWORD *)(a5 + 4);
  v9 = *(_QWORD *)(a5 + 8);
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a1, a2, a3, a4, v8, &v7).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
    *a6 = v7;
  return result;
}

```

## disassembly

```asm
0x180002740  mov     r11, rsp
0x180002743  push    rbx
0x180002744  push    rdi
0x180002745  sub     rsp, 0A8h
0x18000274c  mov     rax, cs:__security_cookie
0x180002753  xor     rax, rsp
0x180002756  mov     [rsp+0B8h+var_28], rax
0x18000275e  mov     r10, r9
0x180002761  mov     r9d, ecx
0x180002764  mov     rdi, [rsp+0B8h+arg_28]
0x18000276c  mov     rcx, [rsp+0B8h+arg_20]
0x180002774  mov     rbx, rdi
0x180002777  mov     [rsp+0B8h+var_58], rbx
0x18000277c  xorps   xmm0, xmm0
0x18000277f  movups  [rsp+0B8h+var_48], xmm0
0x180002784  mov     eax, [rcx]
0x180002786  mov     [r11-38h], eax
0x18000278a  mov     eax, [rcx+4]
0x18000278d  mov     [r11-34h], eax
0x180002791  mov     rax, [rcx+8]
0x180002795  mov     [r11-30h], rax
0x180002799  mov     qword ptr [r11-60h], 0
0x1800027a1  lea     rax, [r11-48h]
0x1800027a5  mov     [r11-78h], rax
0x1800027a9  lea     rax, [r11-38h]
0x1800027ad  mov     [r11-80h], rax
0x1800027b1  mov     [rsp+0B8h+var_88], r10
0x1800027b6  mov     [rsp+0B8h+var_90], r8
0x1800027bb  mov     [rsp+0B8h+var_98], rdx
0x1800027c0  xor     r8d, r8d; pReturnValue
0x1800027c3  xor     edx, edx; nProcNum
0x1800027c5  lea     rcx, pProxyInfo; pProxyInfo
0x1800027cc  call    cs:__imp_NdrClientCall3
0x1800027d3  nop     dword ptr [rax+rax+00h]
0x1800027d8  mov     [rsp+0B8h+var_60], rax
0x1800027dd  mov     [rsp+0B8h+var_68], eax
0x1800027e1  jmp     short loc_1800027FD
0x1800027e3  mov     ecx, eax; Status
0x1800027e5  call    cs:__imp_I_RpcMapWin32Status
0x1800027ec  nop     dword ptr [rax+rax+00h]
0x1800027f1  mov     [rsp+0B8h+var_68], eax
0x1800027f5  mov     rbx, [rsp+0B8h+var_58]
0x1800027fa  mov     rdi, rbx
0x1800027fd  test    eax, eax
0x1800027ff  js      short loc_180002817
0x180002801  mov     ecx, dword ptr [rsp+0B8h+var_48]
0x180002805  mov     [rdi], ecx
0x180002807  mov     ecx, dword ptr [rsp+0B8h+var_48+4]
0x18000280b  mov     [rbx+4], ecx
0x18000280e  mov     rcx, qword ptr [rsp+0B8h+var_48+8]
0x180002813  mov     [rbx+8], rcx
0x180002817  mov     rcx, [rsp+0B8h+var_28]
0x18000281f  xor     rcx, rsp; StackCookie
0x180002822  call    __security_check_cookie
0x180002827  add     rsp, 0A8h
0x18000282e  pop     rdi
0x18000282f  pop     rbx
0x180002830  retn
0x18000350c  push    rbp
0x18000350e  sub     rsp, 50h
0x180003512  mov     rbp, rdx
0x180003515  mov     rcx, [rcx]
0x180003518  mov     ecx, [rcx]; ExceptionCode
0x18000351a  call    cs:__imp_I_RpcExceptionFilter
0x180003521  nop     dword ptr [rax+rax+00h]
0x180003526  nop
0x180003527  add     rsp, 50h
0x18000352b  pop     rbp
0x18000352c  retn
```
