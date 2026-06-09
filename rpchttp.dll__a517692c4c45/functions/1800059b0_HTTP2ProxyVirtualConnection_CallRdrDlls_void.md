# HTTP2ProxyVirtualConnection::CallRdrDlls(void)

- ea: `0x1800059b0`
- end: `0x180005adf`
- name: `?CallRdrDlls@HTTP2ProxyVirtualConnection@@IEAAJXZ`
- size: `303`
- prototype: `__int64 __fastcall(HTTP2ProxyVirtualConnection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d934`
- `0x18000db94`

## callees

- `0x1800059b0`
- `0x18001ac1c`
- `0x18001e3d4`
- `0x18001efe8`
- `0x180025010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180005a43`
- `KERNEL32!CompareStringW` at `0x180005a43`
- `RPCRT4!I_RpcFree` at `0x180005a55`
- `RPCRT4!I_RpcFree` at `0x180005a55`

## pseudocode

```c
__int64 __fastcall HTTP2ProxyVirtualConnection::CallRdrDlls(HTTP2ProxyVirtualConnection *this)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  unsigned int v5; // edi
  unsigned __int16 *v6; // rax
  __int64 v7; // rdx
  unsigned __int16 v8; // [rsp+40h] [rbp+8h] BYREF
  HTTP2ChannelPointer *v9; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  v9 = 0;
  v2 = (*(__int64 (__fastcall **)(HTTP2ProxyVirtualConnection *, HTTP2ChannelPointer **))(*(_QWORD *)this + 200LL))(
         this,
         &v9);
  v3 = v2;
  if ( !v2 )
    return 3221360658LL;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*((_QWORD *)this + 46) + 24LL))(
         v2,
         *((_QWORD *)this + 47),
         3);
  if ( !v5 )
  {
    if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)this + 49), -1, *(PCNZWCH *)(*((_QWORD *)this + 47) + 24LL), -1) == 2
      || (I_RpcFree(*((void **)this + 49)),
          v6 = DuplicateString(*(const unsigned __int16 **)(*((_QWORD *)this + 47) + 24LL)),
          (*((_QWORD *)this + 49) = v6) != 0) )
    {
      v5 = EndpointToPortNumber(*(unsigned __int16 **)(*((_QWORD *)this + 47) + 32LL), &v8);
      if ( !v5 )
      {
        v7 = *((_QWORD *)this + 47);
        *((_WORD *)this + 200) = v8;
        v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*((_QWORD *)this + 46) + 24LL))(v3, v7, 4);
      }
    }
    else
    {
      v5 = 14;
    }
  }
  HTTP2ChannelPointer::UnlockChannelPointer(v9);
  return v5;
}

```

## disassembly

```asm
0x1800059b0  mov     r11, rsp
0x1800059b3  mov     [r11+18h], rbx
0x1800059b7  mov     [r11+20h], rsi
0x1800059bb  push    rdi
0x1800059bc  sub     rsp, 30h
0x1800059c0  xor     eax, eax
0x1800059c2  lea     rdx, [r11+10h]
0x1800059c6  mov     [rsp+38h+arg_0], ax
0x1800059cb  mov     rbx, rcx
0x1800059ce  mov     [r11+10h], rax
0x1800059d2  mov     rax, [rcx]
0x1800059d5  mov     rax, [rax+0C8h]
0x1800059dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e1  mov     rsi, rax
0x1800059e4  test    rax, rax
0x1800059e7  jnz     short loc_1800059F3
0x1800059e9  mov     eax, 0C0021012h
0x1800059ee  jmp     loc_180005ACF
0x1800059f3  mov     rax, [rbx+170h]
0x1800059fa  mov     r8d, 3
0x180005a00  mov     rdx, [rbx+178h]
0x180005a07  mov     rcx, rsi
0x180005a0a  mov     rax, [rax+18h]
0x180005a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a13  mov     edi, eax
0x180005a15  test    eax, eax
0x180005a17  jnz     loc_180005AC3
0x180005a1d  mov     rax, [rbx+178h]
0x180005a24  lea     edx, [rdi+1]; dwCmpFlags
0x180005a27  mov     r8, [rbx+188h]; lpString1
0x180005a2e  lea     ecx, [rdi+7Fh]; Locale
0x180005a31  or      r9d, 0FFFFFFFFh; cchCount1
0x180005a35  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180005a3a  mov     rax, [rax+18h]
0x180005a3e  mov     [rsp+38h+lpString2], rax; lpString2
0x180005a43  call    cs:__imp_CompareStringW
0x180005a49  cmp     eax, 2
0x180005a4c  jz      short loc_180005A7C
0x180005a4e  mov     rcx, [rbx+188h]; Object
0x180005a55  call    cs:__imp_I_RpcFree
0x180005a5b  mov     rcx, [rbx+178h]
0x180005a62  mov     rcx, [rcx+18h]; Src
0x180005a66  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x180005a6b  mov     [rbx+188h], rax
0x180005a72  test    rax, rax
0x180005a75  jnz     short loc_180005A7C
0x180005a77  lea     edi, [rax+0Eh]
0x180005a7a  jmp     short loc_180005AC3
0x180005a7c  mov     rcx, [rbx+178h]
0x180005a83  lea     rdx, [rsp+38h+arg_0]; unsigned __int16 *
0x180005a88  mov     rcx, [rcx+20h]; unsigned __int16 *
0x180005a8c  call    ?EndpointToPortNumber@@YAJPEAGAEAG@Z; EndpointToPortNumber(ushort *,ushort &)
0x180005a91  mov     edi, eax
0x180005a93  test    eax, eax
0x180005a95  jnz     short loc_180005AC3
0x180005a97  movzx   eax, [rsp+38h+arg_0]
0x180005a9c  lea     r8d, [rdi+4]
0x180005aa0  mov     rdx, [rbx+178h]
0x180005aa7  mov     rcx, rsi
0x180005aaa  mov     [rbx+190h], ax
0x180005ab1  mov     rax, [rbx+170h]
0x180005ab8  mov     rax, [rax+18h]
0x180005abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ac1  mov     edi, eax
0x180005ac3  mov     rcx, [rsp+38h+arg_8]; this
0x180005ac8  call    ?UnlockChannelPointer@HTTP2ChannelPointer@@QEAAXXZ; HTTP2ChannelPointer::UnlockChannelPointer(void)
0x180005acd  mov     eax, edi
0x180005acf  mov     rbx, [rsp+38h+arg_10]
0x180005ad4  mov     rsi, [rsp+38h+arg_18]
0x180005ad9  add     rsp, 30h
0x180005add  pop     rdi
0x180005ade  retn
```
