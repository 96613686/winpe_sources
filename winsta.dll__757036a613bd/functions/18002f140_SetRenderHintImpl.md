# SetRenderHintImpl

- ea: `0x18002f140`
- end: `0x18002f653`
- name: `SetRenderHintImpl`
- size: `1299`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18002da60`

## callees

- `0x18000c368`
- `0x18002ee14`
- `0x18002eea8`
- `0x18002f140`
- `0x18002f65c`
- `0x18002f6a0`
- `0x18002f708`
- `0x18002f794`
- `0x18002f7e8`
- `0x18002f83c`
- `0x18002f894`
- `0x18002fe40`

## import_xrefs

- `msvcrt!rand` at `0x18002f2d7`
- `msvcrt!rand` at `0x18002f2d7`
- `msvcrt!time` at `0x18002f2c8`
- `msvcrt!time` at `0x18002f2c8`
- `msvcrt!srand` at `0x18002f2d1`
- `msvcrt!srand` at `0x18002f2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3c3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002f380`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002f380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002f373`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002f373`
- `RPCRT4!RpcBindingFree` at `0x18002f61a`
- `RPCRT4!RpcBindingFree` at `0x18002f61a`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800308c5`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800308c5`
- `RPCRT4!NdrClientCall3` at `0x18002f52f`
- `RPCRT4!NdrClientCall3` at `0x18002f52f`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18002f1d7`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18002f1d7`

## pseudocode

```c
__int64 __fastcall SetRenderHintImpl(unsigned __int64 *a1, HWND a2, unsigned int a3, int a4, __int64 a5)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v10; // r8
  __int64 v11; // rdx
  CLIENT_CALL_RETURN v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // r8
  unsigned __int64 v18; // rbx
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rdx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  DWORD v25; // edi
  unsigned int v26; // eax
  __int64 v27; // r8
  unsigned __int16 *v28; // rcx
  unsigned int v29; // eax
  int v30; // r8d
  int v31; // edx
  const char *v32; // rcx
  unsigned int v33; // eax
  int v34; // edx
  int v35; // r8d
  unsigned __int64 v36; // rax
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int v40; // eax
  __int64 v41; // r8
  DWORD pSessionId; // [rsp+50h] [rbp-278h] BYREF
  int v44; // [rsp+54h] [rbp-274h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-270h] BYREF
  int Pointer; // [rsp+60h] [rbp-268h]
  CLIENT_CALL_RETURN v47; // [rsp+68h] [rbp-260h]
  unsigned __int16 v48[264]; // [rsp+70h] [rbp-258h] BYREF

  Binding = 0;
  pSessionId = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 17;
LABEL_6:
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v10, CurrentThreadActivityIdPrefix);
LABEL_7:
    LODWORD(v12.Pointer) = -2147024809;
    goto LABEL_68;
  }
  if ( !IsWindow(a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v13, a2);
    }
    goto LABEL_7;
  }
  if ( a3 >= 3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v17, v16, a3);
    }
    goto LABEL_7;
  }
  if ( a3 - 1 <= 1 && (!a2 || a5 && a4 != 16) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 20;
    goto LABEL_6;
  }
  v18 = *a1;
  if ( *a1 )
  {
    v44 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v22 = 22;
      goto LABEL_35;
    }
  }
  else
  {
    v19 = time(0);
    srand(v19);
    v18 = (unsigned __int64)a2 | ((__int64)rand() << 32) | 0x8000000000000000uLL;
    *a1 = v18;
    v44 = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v22 = 21;
LABEL_35:
      WPP_SF_Di(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v21, v20, v18);
    }
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    LastError = GetLastError();
    LODWORD(v12.Pointer) = LastError;
    if ( LastError > 0 )
      LODWORD(v12.Pointer) = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = GetLastError();
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v27, v26, v25);
    }
    goto LABEL_68;
  }
  LODWORD(v12.Pointer) = StringCchPrintfW(v48, 0x104u, L"HintApiRPCEntry#%d", pSessionId);
  if ( SLODWORD(v12.Simple) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 24;
    v32 = "Failed StringCchPrintf";
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, v35, v33, (__int64)v48);
  }
  LODWORD(v12.Pointer) = SetRenderHintRpcBind(v28, v48, &Binding);
  if ( SLODWORD(v12.Simple) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    v31 = 26;
    v32 = "Failed Bind";
LABEL_48:
    WPP_SF_DsD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v30, v29, (__int64)v32, v12.Simple);
    goto LABEL_68;
  }
  v36 = *a1;
  v47.Simple = 0;
  v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18003BE90, 0, 0, Binding, v36, a2, v44, a3, a4, a5).Pointer;
  v47.Pointer = v12.Pointer;
  Pointer = (int)v12.Pointer;
  if ( SLODWORD(v12.Simple) >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v41, v40);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v37 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, v39, v37, v12.Pointer);
  }
LABEL_68:
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( LODWORD(v12.Pointer) == -2147023174 )
    LODWORD(v12.Pointer) = -2147467263;
  return LODWORD(v12.Pointer);
}

```

## disassembly

```asm
0x18002f140  push    rbx
0x18002f142  push    rsi
0x18002f143  push    rdi
0x18002f144  push    r12
0x18002f146  push    r13
0x18002f148  push    r14
0x18002f14a  push    r15
0x18002f14c  sub     rsp, 290h
0x18002f153  mov     rax, cs:__security_cookie
0x18002f15a  xor     rax, rsp
0x18002f15d  mov     [rsp+2C8h+var_48], rax
0x18002f165  mov     r12d, r9d
0x18002f168  mov     r14d, r8d
0x18002f16b  mov     rsi, rdx
0x18002f16e  mov     r15, rcx
0x18002f171  mov     r13, [rsp+2C8h+arg_20]
0x18002f179  mov     [rsp+2C8h+Binding], 0
0x18002f182  mov     [rsp+2C8h+pSessionId], 0
0x18002f18a  test    rcx, rcx
0x18002f18d  jnz     short loc_18002F1D4
0x18002f18f  lea     rdi, WPP_GLOBAL_Control
0x18002f196  mov     rax, cs:WPP_GLOBAL_Control
0x18002f19d  cmp     rax, rdi
0x18002f1a0  jz      short loc_18002F1CA
0x18002f1a2  test    byte ptr [rax+1Ch], 1
0x18002f1a6  jz      short loc_18002F1CA
0x18002f1a8  cmp     byte ptr [rax+19h], 2
0x18002f1ac  jb      short loc_18002F1CA
0x18002f1ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f1b3  lea     edx, [r15+11h]
0x18002f1b7  mov     r9d, eax
0x18002f1ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1c1  mov     rcx, [rcx+10h]
0x18002f1c5  call    WPP_SF_D
0x18002f1ca  mov     ebx, 80070057h
0x18002f1cf  jmp     loc_18002F60D
0x18002f1d4  mov     rcx, rsi; hWnd
0x18002f1d7  call    cs:__imp_IsWindow
0x18002f1dd  test    eax, eax
0x18002f1df  jnz     short loc_18002F21F
0x18002f1e1  lea     rdi, WPP_GLOBAL_Control
0x18002f1e8  mov     rax, cs:WPP_GLOBAL_Control
0x18002f1ef  cmp     rax, rdi
0x18002f1f2  jz      short loc_18002F1CA
0x18002f1f4  test    byte ptr [rax+1Ch], 1
0x18002f1f8  jz      short loc_18002F1CA
0x18002f1fa  cmp     byte ptr [rax+19h], 2
0x18002f1fe  jb      short loc_18002F1CA
0x18002f200  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f205  mov     [rsp+2C8h+var_2A8], rsi
0x18002f20a  mov     r9d, eax
0x18002f20d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f214  mov     rcx, [rcx+10h]
0x18002f218  call    WPP_SF_Dq
0x18002f21d  jmp     short loc_18002F1CA
0x18002f21f  cmp     r14d, 3
0x18002f223  jb      short loc_18002F26B
0x18002f225  lea     rdi, WPP_GLOBAL_Control
0x18002f22c  mov     rax, cs:WPP_GLOBAL_Control
0x18002f233  cmp     rax, rdi
0x18002f236  jz      short loc_18002F1CA
0x18002f238  test    byte ptr [rax+1Ch], 1
0x18002f23c  jz      short loc_18002F1CA
0x18002f23e  cmp     byte ptr [rax+19h], 2
0x18002f242  jb      short loc_18002F1CA
0x18002f244  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f249  mov     edx, 13h
0x18002f24e  mov     dword ptr [rsp+2C8h+var_2A8], r14d
0x18002f253  mov     r9d, eax
0x18002f256  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f25d  mov     rcx, [rcx+10h]
0x18002f261  call    WPP_SF_Dd
0x18002f266  jmp     loc_18002F1CA
0x18002f26b  lea     eax, [r14-1]
0x18002f26f  cmp     eax, 1
0x18002f272  ja      short loc_18002F2BE
0x18002f274  test    rsi, rsi
0x18002f277  jz      short loc_18002F284
0x18002f279  test    r13, r13
0x18002f27c  jz      short loc_18002F2BE
0x18002f27e  cmp     r12d, 10h
0x18002f282  jz      short loc_18002F2BE
0x18002f284  lea     rdi, WPP_GLOBAL_Control
0x18002f28b  mov     rax, cs:WPP_GLOBAL_Control
0x18002f292  cmp     rax, rdi
0x18002f295  jz      loc_18002F1CA
0x18002f29b  test    byte ptr [rax+1Ch], 1
0x18002f29f  jz      loc_18002F1CA
0x18002f2a5  cmp     byte ptr [rax+19h], 2
0x18002f2a9  jb      loc_18002F1CA
0x18002f2af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f2b4  mov     edx, 14h
0x18002f2b9  jmp     loc_18002F1B7
0x18002f2be  mov     rbx, [r15]
0x18002f2c1  test    rbx, rbx
0x18002f2c4  jnz     short loc_18002F32A
0x18002f2c6  xor     ecx, ecx; Time
0x18002f2c8  call    cs:__imp_time
0x18002f2ce  mov     rcx, rax; Seed
0x18002f2d1  call    cs:__imp_srand
0x18002f2d7  call    cs:__imp_rand
0x18002f2dd  movsxd  rbx, eax
0x18002f2e0  shl     rbx, 20h
0x18002f2e4  or      rbx, rsi
0x18002f2e7  mov     rax, 8000000000000000h
0x18002f2f1  or      rbx, rax
0x18002f2f4  mov     [r15], rbx
0x18002f2f7  mov     [rsp+2C8h+var_274], 1
0x18002f2ff  lea     rdi, WPP_GLOBAL_Control
0x18002f306  mov     rax, cs:WPP_GLOBAL_Control
0x18002f30d  cmp     rax, rdi
0x18002f310  jz      short loc_18002F373
0x18002f312  test    byte ptr [rax+1Ch], 1
0x18002f316  jz      short loc_18002F373
0x18002f318  cmp     byte ptr [rax+19h], 2
0x18002f31c  jb      short loc_18002F373
0x18002f31e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f323  mov     edx, 15h
0x18002f328  jmp     short loc_18002F35B
0x18002f32a  mov     [rsp+2C8h+var_274], 0
0x18002f332  lea     rdi, WPP_GLOBAL_Control
0x18002f339  mov     rax, cs:WPP_GLOBAL_Control
0x18002f340  cmp     rax, rdi
0x18002f343  jz      short loc_18002F373
0x18002f345  test    byte ptr [rax+1Ch], 1
0x18002f349  jz      short loc_18002F373
0x18002f34b  cmp     byte ptr [rax+19h], 2
0x18002f34f  jb      short loc_18002F373
0x18002f351  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f356  mov     edx, 16h
0x18002f35b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f362  mov     [rsp+2C8h+var_2A8], rbx
0x18002f367  mov     r9d, eax
0x18002f36a  mov     rcx, [rcx+10h]
0x18002f36e  call    WPP_SF_Di
0x18002f373  call    cs:__imp_GetCurrentProcessId
0x18002f379  mov     ecx, eax; dwProcessId
0x18002f37b  lea     rdx, [rsp+2C8h+pSessionId]; pSessionId
0x18002f380  call    cs:__imp_ProcessIdToSessionId
0x18002f386  test    eax, eax
0x18002f388  jnz     short loc_18002F3F1
0x18002f38a  call    cs:__imp_GetLastError
0x18002f390  mov     ebx, eax
0x18002f392  test    eax, eax
0x18002f394  jle     short loc_18002F39F
0x18002f396  movzx   ebx, ax
0x18002f399  or      ebx, 80070000h
0x18002f39f  mov     rax, cs:WPP_GLOBAL_Control
0x18002f3a6  cmp     rax, rdi
0x18002f3a9  jz      loc_18002F60D
0x18002f3af  test    byte ptr [rax+1Ch], 1
0x18002f3b3  jz      loc_18002F60D
0x18002f3b9  cmp     byte ptr [rax+19h], 2
0x18002f3bd  jb      loc_18002F60D
0x18002f3c3  call    cs:__imp_GetLastError
0x18002f3c9  mov     edi, eax
0x18002f3cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f3d0  mov     edx, 17h
0x18002f3d5  mov     dword ptr [rsp+2C8h+var_2A8], edi
0x18002f3d9  mov     r9d, eax
0x18002f3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3e3  mov     rcx, [rcx+10h]
0x18002f3e7  call    WPP_SF_Dd
0x18002f3ec  jmp     loc_18002F60D
0x18002f3f1  mov     r9d, [rsp+2C8h+pSessionId]
0x18002f3f6  lea     r8, aHintapirpcentr; "HintApiRPCEntry#%d"
0x18002f3fd  mov     edx, 104h; unsigned __int64
0x18002f402  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18002f407  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f40c  mov     ebx, eax
0x18002f40e  test    eax, eax
0x18002f410  jns     short loc_18002F468
0x18002f412  mov     rax, cs:WPP_GLOBAL_Control
0x18002f419  cmp     rax, rdi
0x18002f41c  jz      loc_18002F60D
0x18002f422  test    byte ptr [rax+1Ch], 8
0x18002f426  jz      loc_18002F60D
0x18002f42c  cmp     byte ptr [rax+19h], 2
0x18002f430  jb      loc_18002F60D
0x18002f436  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f43b  mov     edx, 18h
0x18002f440  lea     rcx, aFailedStringcc; "Failed StringCchPrintf"
0x18002f447  mov     dword ptr [rsp+2C8h+var_2A0], ebx
0x18002f44b  mov     [rsp+2C8h+var_2A8], rcx
0x18002f450  mov     r9d, eax
0x18002f453  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f45a  mov     rcx, [rcx+10h]
0x18002f45e  call    WPP_SF_DsD
0x18002f463  jmp     loc_18002F60D
0x18002f468  mov     rax, cs:WPP_GLOBAL_Control
0x18002f46f  cmp     rax, rdi
0x18002f472  jz      short loc_18002F4A2
0x18002f474  test    byte ptr [rax+1Ch], 1
0x18002f478  jz      short loc_18002F4A2
0x18002f47a  cmp     byte ptr [rax+19h], 2
0x18002f47e  jb      short loc_18002F4A2
0x18002f480  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f485  lea     rcx, [rsp+2C8h+var_258]
0x18002f48a  mov     [rsp+2C8h+var_2A8], rcx
0x18002f48f  mov     r9d, eax
0x18002f492  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f499  mov     rcx, [rcx+10h]
0x18002f49d  call    WPP_SF_DS
0x18002f4a2  lea     r8, [rsp+2C8h+Binding]; void **
0x18002f4a7  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18002f4ac  call    ?SetRenderHintRpcBind@@YAJPEAG0PEAPEAX@Z; SetRenderHintRpcBind(ushort *,ushort *,void * *)
0x18002f4b1  mov     ebx, eax
0x18002f4b3  test    eax, eax
0x18002f4b5  jns     short loc_18002F4F1
0x18002f4b7  mov     rax, cs:WPP_GLOBAL_Control
0x18002f4be  cmp     rax, rdi
0x18002f4c1  jz      loc_18002F60D
0x18002f4c7  test    byte ptr [rax+1Ch], 8
0x18002f4cb  jz      loc_18002F60D
0x18002f4d1  cmp     byte ptr [rax+19h], 2
0x18002f4d5  jb      loc_18002F60D
0x18002f4db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f4e0  mov     edx, 1Ah
0x18002f4e5  lea     rcx, aFailedBind; "Failed Bind"
0x18002f4ec  jmp     loc_18002F447
0x18002f4f1  mov     rax, [r15]
0x18002f4f4  mov     [rsp+2C8h+var_260], 0
0x18002f4fd  mov     [rsp+2C8h+var_280], r13
0x18002f502  mov     [rsp+2C8h+var_288], r12d
0x18002f507  mov     [rsp+2C8h+var_290], r14d
0x18002f50c  mov     ecx, [rsp+2C8h+var_274]
0x18002f510  mov     [rsp+2C8h+var_298], ecx
0x18002f514  mov     [rsp+2C8h+var_2A0], rsi
0x18002f519  mov     [rsp+2C8h+var_2A8], rax
0x18002f51e  mov     r9, [rsp+2C8h+Binding]
0x18002f523  xor     r8d, r8d; pReturnValue
0x18002f526  xor     edx, edx; nProcNum
0x18002f528  lea     rcx, stru_18003BE90; pProxyInfo
0x18002f52f  call    cs:__imp_NdrClientCall3
0x18002f535  mov     rbx, rax
0x18002f538  mov     [rsp+2C8h+var_260], rax
0x18002f53d  mov     [rsp+2C8h+var_268], ebx
0x18002f541  test    eax, eax
0x18002f543  jns     short loc_18002F57E
0x18002f545  mov     rax, cs:WPP_GLOBAL_Control
0x18002f54c  cmp     rax, rdi
0x18002f54f  jz      short loc_18002F579
0x18002f551  test    byte ptr [rax+1Ch], 1
0x18002f555  jz      short loc_18002F579
0x18002f557  cmp     byte ptr [rax+19h], 2
0x18002f55b  jb      short loc_18002F579
0x18002f55d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f562  mov     dword ptr [rsp+2C8h+var_2A8], ebx
0x18002f566  mov     r9d, eax
0x18002f569  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f570  mov     rcx, [rcx+10h]
0x18002f574  call    WPP_SF_DDd
0x18002f579  jmp     loc_18002F60D
0x18002f57e  mov     rax, cs:WPP_GLOBAL_Control
0x18002f585  cmp     rax, rdi
0x18002f588  jz      short loc_18002F5B3
0x18002f58a  test    byte ptr [rax+1Ch], 1
0x18002f58e  jz      short loc_18002F5B3
0x18002f590  cmp     byte ptr [rax+19h], 2
0x18002f594  jb      short loc_18002F5B3
0x18002f596  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f59b  mov     edx, 1Ch
0x18002f5a0  mov     r9d, eax
0x18002f5a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5aa  mov     rcx, [rcx+10h]
0x18002f5ae  call    WPP_SF_D
0x18002f5b3  jmp     short loc_18002F60D
0x18002f5b5  mov     edi, eax
0x18002f5b7  test    eax, eax
0x18002f5b9  jg      short loc_18002F5BF
0x18002f5bb  mov     ebx, eax
0x18002f5bd  jmp     short loc_18002F5C8
0x18002f5bf  movzx   ebx, di
0x18002f5c2  or      ebx, 80070000h
0x18002f5c8  mov     [rsp+2C8h+var_268], ebx
0x18002f5cc  lea     rcx, WPP_GLOBAL_Control
0x18002f5d3  mov     rax, cs:WPP_GLOBAL_Control
0x18002f5da  cmp     rax, rcx
0x18002f5dd  jz      short loc_18002F60D
0x18002f5df  test    byte ptr [rax+1Ch], 1
0x18002f5e3  jz      short loc_18002F60D
0x18002f5e5  cmp     byte ptr [rax+19h], 2
0x18002f5e9  jb      short loc_18002F60D
0x18002f5eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002f5f0  mov     edx, 1Dh
0x18002f5f5  mov     dword ptr [rsp+2C8h+var_2A8], edi
0x18002f5f9  mov     r9d, eax
0x18002f5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f603  mov     rcx, [rcx+10h]
0x18002f607  call    WPP_SF_Dd
0x18002f60c  nop
0x18002f60d  cmp     [rsp+2C8h+Binding], 0
0x18002f613  jz      short loc_18002F620
0x18002f615  lea     rcx, [rsp+2C8h+Binding]; Binding
0x18002f61a  call    cs:__imp_RpcBindingFree
0x18002f620  mov     eax, 80004001h
0x18002f625  cmp     ebx, 800706BAh
0x18002f62b  cmovz   ebx, eax
0x18002f62e  mov     eax, ebx
0x18002f630  mov     rcx, [rsp+2C8h+var_48]
  ... truncated ...
```
