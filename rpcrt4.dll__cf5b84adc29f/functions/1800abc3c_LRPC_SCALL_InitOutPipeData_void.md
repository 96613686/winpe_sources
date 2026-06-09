# LRPC_SCALL::InitOutPipeData(void)

- ea: `0x1800abc3c`
- end: `0x1800abe2b`
- name: `?InitOutPipeData@LRPC_SCALL@@AEAAJXZ`
- size: `495`
- prototype: `__int64 __fastcall(LRPC_SCALL *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800abfe0`

## callees

- `0x180023020`
- `0x180066718`
- `0x18009fd58`
- `0x1800a72e0`
- `0x1800abc3c`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800abca1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800abca1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800abc93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800abc93`

## pseudocode

```c
__int64 __fastcall LRPC_SCALL::InitOutPipeData(LRPC_SCALL *this)
{
  DWORD CurrentProcessId; // ebx
  unsigned int CommandLineW; // eax
  int v5; // esi
  _QWORD *v6; // rax
  _QWORD *v7; // r8
  __int64 v8; // rax
  __int64 v9; // rdx
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
    v7 = AllocWrapper(0xB0u);
    if ( v7 )
    {
      v8 = *((_QWORD *)this + 38);
      v9 = *(_QWORD *)(v8 + 56);
      v7[1] = 0;
      v7[2] = 0;
      v7[4] = v7 + 3;
      v7[3] = v7 + 3;
      v7[8] = v8 + 112;
      v7[5] = 0;
      *((_DWORD *)v7 + 12) = 0x10000;
      v7[7] = 0;
      v7[9] = 0;
      v7[11] = v7 + 10;
      v7[10] = v7 + 10;
      *v7 = &LRPC_S_OUT_PIPE::`vftable';
      *((_DWORD *)v7 + 24) = 0;
      v7[13] = v9;
      v7[17] = 0;
      v7[14] = 0;
      v7[15] = 0;
      v7[16] = 0;
      v7[18] = 0;
      v7[19] = 0;
      v7[20] = 0;
      v7[21] = v9;
    }
    else
    {
      v7 = 0;
    }
    *(_QWORD *)(*((_QWORD *)this + 74) + 24LL) = v7;
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
          LRPC_S_IN_OUT_PIPE::`scalar deleting destructor'(v11);
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
0x1800abc3c  push    rbx
0x1800abc3e  push    rbp
0x1800abc3f  push    rsi
0x1800abc40  push    rdi
0x1800abc41  sub     rsp, 58h
0x1800abc45  mov     rax, cs:__security_cookie
0x1800abc4c  xor     rax, rsp
0x1800abc4f  mov     [rsp+78h+var_38], rax
0x1800abc54  xor     ebp, ebp
0x1800abc56  xorps   xmm0, xmm0
0x1800abc59  mov     rbx, rcx
0x1800abc5c  movups  [rsp+78h+var_48], xmm0
0x1800abc61  cmp     [rcx+18h], rbp
0x1800abc65  jnz     short loc_1800ABCDF
0x1800abc67  mov     rax, [rcx+138h]
0x1800abc6e  mov     rcx, [rax]
0x1800abc71  movups  xmm0, xmmword ptr [rcx+54h]
0x1800abc75  lea     ecx, [rbp+2]; unsigned int
0x1800abc78  movdqu  [rsp+78h+var_48], xmm0
0x1800abc7e  call    ?ShouldSkipLogging@@YAHK@Z; ShouldSkipLogging(ulong)
0x1800abc83  test    eax, eax
0x1800abc85  jnz     short loc_1800ABCD5
0x1800abc87  lea     esi, [rbp+1]
0x1800abc8a  test    cs:Microsoft_Windows_RPC_EventsEnableBits, sil
0x1800abc91  jz      short loc_1800ABCD5
0x1800abc93  call    cs:__imp_GetCurrentProcessId
0x1800abc9a  nop     dword ptr [rax+rax+00h]
0x1800abc9f  mov     ebx, eax
0x1800abca1  call    cs:__imp_GetCommandLineW
0x1800abca8  nop     dword ptr [rax+rax+00h]
0x1800abcad  lea     rcx, [rsp+78h+var_48]
0x1800abcb2  mov     r9d, ebx
0x1800abcb5  mov     [rsp+78h+var_50], rcx
0x1800abcba  lea     rdx, RPC_EVENTLOG_SYNC_PIPE_USE_ERR
0x1800abcc1  lea     rcx, aNcalrpc; "ncalrpc"
0x1800abcc8  mov     r8, rax
0x1800abccb  mov     [rsp+78h+var_58], rcx
0x1800abcd0  call    McTemplateU0zdzj_EtwEventWriteTransfer
0x1800abcd5  mov     eax, 6E4h
0x1800abcda  jmp     loc_1800ABE14
0x1800abcdf  mov     esi, ebp
0x1800abce1  cmp     [rcx+250h], rbp
0x1800abce8  jnz     short loc_1800ABD1F
0x1800abcea  mov     ecx, 30h ; '0'; dwBytes
0x1800abcef  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800abcf4  test    rax, rax
0x1800abcf7  jz      loc_1800ABDC0
0x1800abcfd  mov     [rax], ebp
0x1800abcff  mov     esi, 1
0x1800abd04  mov     [rax+8], rbp
0x1800abd08  mov     [rax+20h], rbp
0x1800abd0c  mov     [rax+10h], rbp
0x1800abd10  mov     [rax+18h], rbp
0x1800abd14  mov     [rax+28h], rbp
0x1800abd18  mov     [rbx+250h], rax
0x1800abd1f  mov     ecx, 0B0h; dwBytes
0x1800abd24  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800abd29  mov     r8, rax
0x1800abd2c  test    rax, rax
0x1800abd2f  jz      loc_1800ABDCE
0x1800abd35  mov     rax, [rbx+130h]
0x1800abd3c  lea     rcx, [r8+18h]
0x1800abd40  mov     rdx, [rax+38h]
0x1800abd44  add     rax, 70h ; 'p'
0x1800abd48  mov     [r8+8], rbp
0x1800abd4c  mov     [r8+10h], rbp
0x1800abd50  mov     [rcx+8], rcx
0x1800abd54  mov     [rcx], rcx
0x1800abd57  mov     [r8+40h], rax
0x1800abd5b  lea     rax, [r8+50h]
0x1800abd5f  mov     [r8+28h], rbp
0x1800abd63  mov     dword ptr [r8+30h], 10000h
0x1800abd6b  mov     [r8+38h], rbp
0x1800abd6f  mov     [r8+48h], rbp
0x1800abd73  mov     [rax+8], rax
0x1800abd77  mov     [rax], rax
0x1800abd7a  lea     rax, ??_7LRPC_S_OUT_PIPE@@6B@; const LRPC_S_OUT_PIPE::`vftable'
0x1800abd81  mov     [r8], rax
0x1800abd84  mov     [r8+60h], ebp
0x1800abd88  mov     [r8+68h], rdx
0x1800abd8c  mov     [r8+88h], rbp
0x1800abd93  mov     [r8+70h], rbp
0x1800abd97  mov     [r8+78h], rbp
0x1800abd9b  mov     [r8+80h], rbp
0x1800abda2  mov     [r8+90h], rbp
0x1800abda9  mov     [r8+98h], rbp
0x1800abdb0  mov     [r8+0A0h], rbp
0x1800abdb7  mov     [r8+0A8h], rdx
0x1800abdbe  jmp     short loc_1800ABDD1
0x1800abdc0  mov     [rbx+250h], rbp
0x1800abdc7  mov     edi, 0Eh
0x1800abdcc  jmp     short loc_1800ABE12
0x1800abdce  mov     r8, rbp
0x1800abdd1  mov     rax, [rbx+250h]
0x1800abdd8  mov     [rax+18h], r8
0x1800abddc  mov     rcx, [rbx+250h]; this
0x1800abde3  cmp     [rcx+18h], rbp
0x1800abde7  jnz     short loc_1800ABE05
0x1800abde9  mov     edi, 0Eh
0x1800abdee  test    esi, esi
0x1800abdf0  jz      short loc_1800ABE12
0x1800abdf2  test    rcx, rcx
0x1800abdf5  jz      short loc_1800ABDFC
0x1800abdf7  call    ??_GLRPC_S_IN_OUT_PIPE@@QEAAPEAXI@Z; LRPC_S_IN_OUT_PIPE::`scalar deleting destructor'(uint)
0x1800abdfc  mov     [rbx+250h], rbp
0x1800abe03  jmp     short loc_1800ABE12
0x1800abe05  mov     edi, ebp
0x1800abe07  lock or dword ptr [rbx+0E8h], 100h
0x1800abe12  mov     eax, edi
0x1800abe14  mov     rcx, [rsp+78h+var_38]
0x1800abe19  xor     rcx, rsp; StackCookie
0x1800abe1c  call    __security_check_cookie
0x1800abe21  add     rsp, 58h
0x1800abe25  pop     rdi
0x1800abe26  pop     rsi
0x1800abe27  pop     rbp
0x1800abe28  pop     rbx
0x1800abe29  retn
```
