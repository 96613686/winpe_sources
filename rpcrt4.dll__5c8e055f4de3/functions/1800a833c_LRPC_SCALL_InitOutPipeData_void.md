# LRPC_SCALL::InitOutPipeData(void)

- ea: `0x1800a833c`
- end: `0x1800a851e`
- name: `?InitOutPipeData@LRPC_SCALL@@AEAAJXZ`
- size: `482`
- prototype: `__int64 __fastcall(LRPC_SCALL *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a86c0`

## callees

- `0x180021e70`
- `0x180061948`
- `0x18009c3a0`
- `0x1800a3fd4`
- `0x1800a833c`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a839b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800a839b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a8393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a8393`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::InitOutPipeData(LRPC_SCALL *this)
{
  DWORD CurrentProcessId; // ebx
  unsigned int CommandLineW; // eax
  int v5; // esi
  _QWORD *v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // r8
  __int64 v9; // rax
  unsigned int v10; // edi
  LRPC_S_IN_OUT_PIPE *v11; // rcx
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF

  v12 = 0;
  if ( *((_QWORD *)this + 3) )
  {
    v5 = 0;
    if ( !*((_QWORD *)this + 74) )
    {
      v6 = AllocWrapper(0x30u);
      if ( !v6 )
      {
        *((_QWORD *)this + 74) = 0;
        return 14;
      }
      *(_DWORD *)v6 = 0;
      v5 = 1;
      v6[1] = 0;
      v6[4] = 0;
      v6[2] = 0;
      v6[3] = 0;
      v6[5] = 0;
      *((_QWORD *)this + 74) = v6;
    }
    v8 = AllocWrapper(0xB0u);
    if ( v8 )
    {
      v9 = *((_QWORD *)this + 38);
      v7 = *(_QWORD *)(v9 + 56);
      v8[1] = 0;
      v8[2] = 0;
      v8[4] = v8 + 3;
      v8[3] = v8 + 3;
      v8[8] = v9 + 112;
      v8[5] = 0;
      *((_DWORD *)v8 + 12) = 0x10000;
      v8[7] = 0;
      v8[9] = 0;
      v8[11] = v8 + 10;
      v8[10] = v8 + 10;
      *v8 = &LRPC_S_OUT_PIPE::`vftable';
      *((_DWORD *)v8 + 24) = 0;
      v8[13] = v7;
      v8[17] = 0;
      v8[14] = 0;
      v8[15] = 0;
      v8[16] = 0;
      v8[18] = 0;
      v8[19] = 0;
      v8[20] = 0;
      v8[21] = v7;
    }
    else
    {
      v8 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 74) + 24LL) = v8;
    v11 = (LRPC_S_IN_OUT_PIPE *)*((_QWORD *)this + 74);
    if ( *((_QWORD *)v11 + 3) )
    {
      v10 = 0;
      _InterlockedOr((volatile signed __int32 *)this + 58, 0x100u);
    }
    else
    {
      v10 = 14;
      if ( v5 )
      {
        if ( v11 )
          LRPC_S_IN_OUT_PIPE::`scalar deleting destructor'(v11, v7);
        *((_QWORD *)this + 74) = 0;
      }
    }
    return v10;
  }
  v12 = *(_OWORD *)(**((_QWORD **)this + 39) + 84LL);
  if ( !(unsigned int)ShouldSkipLogging(2u) && (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
  {
    CurrentProcessId = GetCurrentProcessId();
    CommandLineW = (unsigned int)GetCommandLineW();
    McTemplateU0zdzj_EtwEventWriteTransfer(
      (unsigned int)L"ncalrpc",
      (unsigned int)RPC_EVENTLOG_SYNC_PIPE_USE_ERR,
      CommandLineW,
      CurrentProcessId,
      (__int64)L"ncalrpc",
      (__int64)&v12);
  }
  return 1764;
}

```

## disassembly

```asm
0x1800a833c  push    rbx
0x1800a833e  push    rbp
0x1800a833f  push    rsi
0x1800a8340  push    rdi
0x1800a8341  sub     rsp, 58h
0x1800a8345  mov     rax, cs:__security_cookie
0x1800a834c  xor     rax, rsp
0x1800a834f  mov     [rsp+78h+var_38], rax
0x1800a8354  xor     ebp, ebp
0x1800a8356  xorps   xmm0, xmm0
0x1800a8359  mov     rbx, rcx
0x1800a835c  movups  [rsp+78h+var_48], xmm0
0x1800a8361  cmp     [rcx+18h], rbp
0x1800a8365  jnz     short loc_1800A83D3
0x1800a8367  mov     rax, [rcx+138h]
0x1800a836e  mov     rcx, [rax]
0x1800a8371  movups  xmm0, xmmword ptr [rcx+54h]
0x1800a8375  lea     ecx, [rbp+2]; unsigned int
0x1800a8378  movdqu  [rsp+78h+var_48], xmm0
0x1800a837e  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800a8383  test    eax, eax
0x1800a8385  jnz     short loc_1800A83C9
0x1800a8387  lea     esi, [rbp+1]
0x1800a838a  test    cs:Microsoft_Windows_RPC_EventsEnableBits, sil
0x1800a8391  jz      short loc_1800A83C9
0x1800a8393  call    cs:__imp_GetCurrentProcessId
0x1800a8399  mov     ebx, eax
0x1800a839b  call    cs:__imp_GetCommandLineW
0x1800a83a1  lea     rcx, [rsp+78h+var_48]
0x1800a83a6  mov     r9d, ebx
0x1800a83a9  mov     [rsp+78h+var_50], rcx
0x1800a83ae  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800a83b5  lea     rcx, aNcalrpc; "ncalrpc"
0x1800a83bc  mov     r8, rax
0x1800a83bf  mov     [rsp+78h+var_58], rcx
0x1800a83c4  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800a83c9  mov     eax, 6E4h
0x1800a83ce  jmp     loc_1800A8508
0x1800a83d3  mov     esi, ebp
0x1800a83d5  cmp     [rcx+250h], rbp
0x1800a83dc  jnz     short loc_1800A8413
0x1800a83de  mov     ecx, 30h ; '0'; dwBytes
0x1800a83e3  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a83e8  test    rax, rax
0x1800a83eb  jz      loc_1800A84B4
0x1800a83f1  mov     [rax], ebp
0x1800a83f3  mov     esi, 1
0x1800a83f8  mov     [rax+8], rbp
0x1800a83fc  mov     [rax+20h], rbp
0x1800a8400  mov     [rax+10h], rbp
0x1800a8404  mov     [rax+18h], rbp
0x1800a8408  mov     [rax+28h], rbp
0x1800a840c  mov     [rbx+250h], rax
0x1800a8413  mov     ecx, 0B0h; dwBytes
0x1800a8418  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a841d  mov     r8, rax
0x1800a8420  test    rax, rax
0x1800a8423  jz      loc_1800A84C2
0x1800a8429  mov     rax, [rbx+130h]
0x1800a8430  lea     rcx, [r8+18h]
0x1800a8434  mov     rdx, [rax+38h]
0x1800a8438  add     rax, 70h ; 'p'
0x1800a843c  mov     [r8+8], rbp
0x1800a8440  mov     [r8+10h], rbp
0x1800a8444  mov     [rcx+8], rcx
0x1800a8448  mov     [rcx], rcx
0x1800a844b  mov     [r8+40h], rax
0x1800a844f  lea     rax, [r8+50h]
0x1800a8453  mov     [r8+28h], rbp
0x1800a8457  mov     dword ptr [r8+30h], 10000h
0x1800a845f  mov     [r8+38h], rbp
0x1800a8463  mov     [r8+48h], rbp
0x1800a8467  mov     [rax+8], rax
0x1800a846b  mov     [rax], rax
0x1800a846e  lea     rax, ??_7LRPC_S_OUT_PIPE@@6B@; const LRPC_S_OUT_PIPE::`vftable'
0x1800a8475  mov     [r8], rax
0x1800a8478  mov     [r8+60h], ebp
0x1800a847c  mov     [r8+68h], rdx
0x1800a8480  mov     [r8+88h], rbp
0x1800a8487  mov     [r8+70h], rbp
0x1800a848b  mov     [r8+78h], rbp
0x1800a848f  mov     [r8+80h], rbp
0x1800a8496  mov     [r8+90h], rbp
0x1800a849d  mov     [r8+98h], rbp
0x1800a84a4  mov     [r8+0A0h], rbp
0x1800a84ab  mov     [r8+0A8h], rdx
0x1800a84b2  jmp     short loc_1800A84C5
0x1800a84b4  mov     [rbx+250h], rbp
0x1800a84bb  mov     edi, 0Eh
0x1800a84c0  jmp     short loc_1800A8506
0x1800a84c2  mov     r8, rbp
0x1800a84c5  mov     rax, [rbx+250h]
0x1800a84cc  mov     [rax+18h], r8
0x1800a84d0  mov     rcx, [rbx+250h]; this
0x1800a84d7  cmp     [rcx+18h], rbp
0x1800a84db  jnz     short loc_1800A84F9
0x1800a84dd  mov     edi, 0Eh
0x1800a84e2  test    esi, esi
0x1800a84e4  jz      short loc_1800A8506
0x1800a84e6  test    rcx, rcx
0x1800a84e9  jz      short loc_1800A84F0
0x1800a84eb  call    ??_GLRPC_S_IN_OUT_PIPE@@QEAAPEAXI@Z; LRPC_S_IN_OUT_PIPE::`scalar deleting destructor'(uint)
0x1800a84f0  mov     [rbx+250h], rbp
0x1800a84f7  jmp     short loc_1800A8506
0x1800a84f9  mov     edi, ebp
0x1800a84fb  lock or dword ptr [rbx+0E8h], 100h
0x1800a8506  mov     eax, edi
0x1800a8508  mov     rcx, [rsp+78h+var_38]
0x1800a850d  xor     rcx, rsp; StackCookie
0x1800a8510  call    __security_check_cookie
0x1800a8515  add     rsp, 58h
0x1800a8519  pop     rdi
0x1800a851a  pop     rsi
0x1800a851b  pop     rbp
0x1800a851c  pop     rbx
0x1800a851d  retn
```
