# CClusterConnection::AttemptCancel(void)

- ea: `0x180034e9c`
- end: `0x180034f50`
- name: `?AttemptCancel@CClusterConnection@@AEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CClusterConnection *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001de04`
- `0x18001e540`

## callees

- `0x1800250b0`
- `0x1800349e8`
- `0x180034e9c`

## import_xrefs

- `RPCRT4!RpcAsyncCancelCall` at `0x180034ec4`
- `RPCRT4!RpcAsyncCancelCall` at `0x180034ec4`

## pseudocode

```c
void __fastcall CClusterConnection::AttemptCancel(CClusterConnection *this)
{
  RPC_STATUS v2; // eax

  if ( *((_DWORD *)this + 53) )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_q(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 21, &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids, this);
    }
  }
  else
  {
    *((_DWORD *)this + 53) = 1;
    v2 = RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 280), 1);
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        20,
        &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids,
        this,
        v2);
    }
  }
}

```

## disassembly

```asm
0x180034e9c  push    rbx
0x180034e9e  sub     rsp, 30h
0x180034ea2  cmp     dword ptr [rcx+0D4h], 0
0x180034ea9  mov     rbx, rcx
0x180034eac  jnz     short loc_180034F12
0x180034eae  mov     dword ptr [rcx+0D4h], 1
0x180034eb8  mov     edx, 1; fAbort
0x180034ebd  add     rcx, 118h; pAsync
0x180034ec4  call    cs:__imp_RpcAsyncCancelCall
0x180034ecb  nop     dword ptr [rax+rax+00h]
0x180034ed0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034ed7  lea     rdx, WPP_witness_GLOBAL_Control
0x180034ede  cmp     rcx, rdx
0x180034ee1  jz      short loc_180034F49
0x180034ee3  test    byte ptr [rcx+1Ch], 1
0x180034ee7  jz      short loc_180034F49
0x180034ee9  cmp     byte ptr [rcx+19h], 3
0x180034eed  jb      short loc_180034F49
0x180034eef  mov     rcx, [rcx+10h]
0x180034ef3  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x180034efa  mov     edx, 14h
0x180034eff  mov     [rsp+38h+var_18], eax
0x180034f03  mov     r9, rbx
0x180034f06  call    WPP_SF_qd
0x180034f0b  add     rsp, 30h
0x180034f0f  pop     rbx
0x180034f10  retn
0x180034f12  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034f19  lea     rdx, WPP_witness_GLOBAL_Control
0x180034f20  cmp     rcx, rdx
0x180034f23  jz      short loc_180034F49
0x180034f25  test    byte ptr [rcx+1Ch], 1
0x180034f29  jz      short loc_180034F49
0x180034f2b  cmp     byte ptr [rcx+19h], 3
0x180034f2f  jb      short loc_180034F49
0x180034f31  mov     rcx, [rcx+10h]
0x180034f35  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x180034f3c  mov     edx, 15h
0x180034f41  mov     r9, rbx
0x180034f44  call    WPP_SF_q
0x180034f49  add     rsp, 30h
0x180034f4d  pop     rbx
0x180034f4e  retn
```
