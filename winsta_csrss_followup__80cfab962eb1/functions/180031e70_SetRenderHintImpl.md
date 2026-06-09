# SetRenderHintImpl

- ea: `0x180031e70`
- end: `0x1800323c0`
- name: `SetRenderHintImpl`
- size: `1360`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18002ff00`

## callees

- `0x18000df38`
- `0x180031b10`
- `0x180031bb8`
- `0x180031e70`
- `0x1800323c8`
- `0x180032414`
- `0x180032480`
- `0x180032514`
- `0x180032570`
- `0x1800325cc`
- `0x180032628`
- `0x180032c20`

## import_xrefs

- `msvcrt!rand` at `0x180032019`
- `msvcrt!rand` at `0x180032019`
- `msvcrt!time` at `0x180031ffe`
- `msvcrt!time` at `0x180031ffe`
- `msvcrt!srand` at `0x18003200d`
- `msvcrt!srand` at `0x18003200d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003211d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003211d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800320ce`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800320ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800320bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800320bb`
- `RPCRT4!RpcBindingFree` at `0x180032380`
- `RPCRT4!RpcBindingFree` at `0x180032380`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800337dd`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800337dd`
- `RPCRT4!NdrClientCall3` at `0x18003228f`
- `RPCRT4!NdrClientCall3` at `0x18003228f`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180031f07`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180031f07`

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
  v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18003EE90, 0, 0, Binding, v36, a2, v44, a3, a4, a5).Pointer;
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
0x180031e70  push    rbx
0x180031e72  push    rsi
0x180031e73  push    rdi
0x180031e74  push    r12
0x180031e76  push    r13
0x180031e78  push    r14
0x180031e7a  push    r15
0x180031e7c  sub     rsp, 290h
0x180031e83  mov     rax, cs:__security_cookie
0x180031e8a  xor     rax, rsp
0x180031e8d  mov     [rsp+2C8h+var_48], rax
0x180031e95  mov     r12d, r9d
0x180031e98  mov     r14d, r8d
0x180031e9b  mov     rsi, rdx
0x180031e9e  mov     r15, rcx
0x180031ea1  mov     r13, [rsp+2C8h+arg_20]
0x180031ea9  mov     [rsp+2C8h+Binding], 0
0x180031eb2  mov     [rsp+2C8h+pSessionId], 0
0x180031eba  test    rcx, rcx
0x180031ebd  jnz     short loc_180031F04
0x180031ebf  lea     rdi, WPP_GLOBAL_Control
0x180031ec6  mov     rax, cs:WPP_GLOBAL_Control
0x180031ecd  cmp     rax, rdi
0x180031ed0  jz      short loc_180031EFA
0x180031ed2  test    byte ptr [rax+1Ch], 1
0x180031ed6  jz      short loc_180031EFA
0x180031ed8  cmp     byte ptr [rax+19h], 2
0x180031edc  jb      short loc_180031EFA
0x180031ede  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031ee3  lea     edx, [r15+11h]
0x180031ee7  mov     r9d, eax
0x180031eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ef1  mov     rcx, [rcx+10h]
0x180031ef5  call    WPP_SF_D
0x180031efa  mov     ebx, 80070057h
0x180031eff  jmp     loc_180032373
0x180031f04  mov     rcx, rsi; hWnd
0x180031f07  call    cs:__imp_IsWindow
0x180031f0e  nop     dword ptr [rax+rax+00h]
0x180031f13  test    eax, eax
0x180031f15  jnz     short loc_180031F55
0x180031f17  lea     rdi, WPP_GLOBAL_Control
0x180031f1e  mov     rax, cs:WPP_GLOBAL_Control
0x180031f25  cmp     rax, rdi
0x180031f28  jz      short loc_180031EFA
0x180031f2a  test    byte ptr [rax+1Ch], 1
0x180031f2e  jz      short loc_180031EFA
0x180031f30  cmp     byte ptr [rax+19h], 2
0x180031f34  jb      short loc_180031EFA
0x180031f36  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031f3b  mov     [rsp+2C8h+var_2A8], rsi
0x180031f40  mov     r9d, eax
0x180031f43  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f4a  mov     rcx, [rcx+10h]
0x180031f4e  call    WPP_SF_Dq
0x180031f53  jmp     short loc_180031EFA
0x180031f55  cmp     r14d, 3
0x180031f59  jb      short loc_180031FA1
0x180031f5b  lea     rdi, WPP_GLOBAL_Control
0x180031f62  mov     rax, cs:WPP_GLOBAL_Control
0x180031f69  cmp     rax, rdi
0x180031f6c  jz      short loc_180031EFA
0x180031f6e  test    byte ptr [rax+1Ch], 1
0x180031f72  jz      short loc_180031EFA
0x180031f74  cmp     byte ptr [rax+19h], 2
0x180031f78  jb      short loc_180031EFA
0x180031f7a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031f7f  mov     edx, 13h
0x180031f84  mov     dword ptr [rsp+2C8h+var_2A8], r14d
0x180031f89  mov     r9d, eax
0x180031f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031f93  mov     rcx, [rcx+10h]
0x180031f97  call    WPP_SF_Dd
0x180031f9c  jmp     loc_180031EFA
0x180031fa1  lea     eax, [r14-1]
0x180031fa5  cmp     eax, 1
0x180031fa8  ja      short loc_180031FF4
0x180031faa  test    rsi, rsi
0x180031fad  jz      short loc_180031FBA
0x180031faf  test    r13, r13
0x180031fb2  jz      short loc_180031FF4
0x180031fb4  cmp     r12d, 10h
0x180031fb8  jz      short loc_180031FF4
0x180031fba  lea     rdi, WPP_GLOBAL_Control
0x180031fc1  mov     rax, cs:WPP_GLOBAL_Control
0x180031fc8  cmp     rax, rdi
0x180031fcb  jz      loc_180031EFA
0x180031fd1  test    byte ptr [rax+1Ch], 1
0x180031fd5  jz      loc_180031EFA
0x180031fdb  cmp     byte ptr [rax+19h], 2
0x180031fdf  jb      loc_180031EFA
0x180031fe5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180031fea  mov     edx, 14h
0x180031fef  jmp     loc_180031EE7
0x180031ff4  mov     rbx, [r15]
0x180031ff7  test    rbx, rbx
0x180031ffa  jnz     short loc_180032072
0x180031ffc  xor     ecx, ecx; Time
0x180031ffe  call    cs:__imp_time
0x180032005  nop     dword ptr [rax+rax+00h]
0x18003200a  mov     rcx, rax; Seed
0x18003200d  call    cs:__imp_srand
0x180032014  nop     dword ptr [rax+rax+00h]
0x180032019  call    cs:__imp_rand
0x180032020  nop     dword ptr [rax+rax+00h]
0x180032025  movsxd  rbx, eax
0x180032028  shl     rbx, 20h
0x18003202c  or      rbx, rsi
0x18003202f  mov     rax, 8000000000000000h
0x180032039  or      rbx, rax
0x18003203c  mov     [r15], rbx
0x18003203f  mov     [rsp+2C8h+var_274], 1
0x180032047  lea     rdi, WPP_GLOBAL_Control
0x18003204e  mov     rax, cs:WPP_GLOBAL_Control
0x180032055  cmp     rax, rdi
0x180032058  jz      short loc_1800320BB
0x18003205a  test    byte ptr [rax+1Ch], 1
0x18003205e  jz      short loc_1800320BB
0x180032060  cmp     byte ptr [rax+19h], 2
0x180032064  jb      short loc_1800320BB
0x180032066  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003206b  mov     edx, 15h
0x180032070  jmp     short loc_1800320A3
0x180032072  mov     [rsp+2C8h+var_274], 0
0x18003207a  lea     rdi, WPP_GLOBAL_Control
0x180032081  mov     rax, cs:WPP_GLOBAL_Control
0x180032088  cmp     rax, rdi
0x18003208b  jz      short loc_1800320BB
0x18003208d  test    byte ptr [rax+1Ch], 1
0x180032091  jz      short loc_1800320BB
0x180032093  cmp     byte ptr [rax+19h], 2
0x180032097  jb      short loc_1800320BB
0x180032099  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003209e  mov     edx, 16h
0x1800320a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320aa  mov     [rsp+2C8h+var_2A8], rbx
0x1800320af  mov     r9d, eax
0x1800320b2  mov     rcx, [rcx+10h]
0x1800320b6  call    WPP_SF_Di
0x1800320bb  call    cs:__imp_GetCurrentProcessId
0x1800320c2  nop     dword ptr [rax+rax+00h]
0x1800320c7  mov     ecx, eax; dwProcessId
0x1800320c9  lea     rdx, [rsp+2C8h+pSessionId]; pSessionId
0x1800320ce  call    cs:__imp_ProcessIdToSessionId
0x1800320d5  nop     dword ptr [rax+rax+00h]
0x1800320da  test    eax, eax
0x1800320dc  jnz     short loc_180032151
0x1800320de  call    cs:__imp_GetLastError
0x1800320e5  nop     dword ptr [rax+rax+00h]
0x1800320ea  mov     ebx, eax
0x1800320ec  test    eax, eax
0x1800320ee  jle     short loc_1800320F9
0x1800320f0  movzx   ebx, ax
0x1800320f3  or      ebx, 80070000h
0x1800320f9  mov     rax, cs:WPP_GLOBAL_Control
0x180032100  cmp     rax, rdi
0x180032103  jz      loc_180032373
0x180032109  test    byte ptr [rax+1Ch], 1
0x18003210d  jz      loc_180032373
0x180032113  cmp     byte ptr [rax+19h], 2
0x180032117  jb      loc_180032373
0x18003211d  call    cs:__imp_GetLastError
0x180032124  nop     dword ptr [rax+rax+00h]
0x180032129  mov     edi, eax
0x18003212b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032130  mov     edx, 17h
0x180032135  mov     dword ptr [rsp+2C8h+var_2A8], edi
0x180032139  mov     r9d, eax
0x18003213c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032143  mov     rcx, [rcx+10h]
0x180032147  call    WPP_SF_Dd
0x18003214c  jmp     loc_180032373
0x180032151  mov     r9d, [rsp+2C8h+pSessionId]
0x180032156  lea     r8, aHintapirpcentr; "HintApiRPCEntry#%d"
0x18003215d  mov     edx, 104h; unsigned __int64
0x180032162  lea     rcx, [rsp+2C8h+var_258]; unsigned __int16 *
0x180032167  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003216c  mov     ebx, eax
0x18003216e  test    eax, eax
0x180032170  jns     short loc_1800321C8
0x180032172  mov     rax, cs:WPP_GLOBAL_Control
0x180032179  cmp     rax, rdi
0x18003217c  jz      loc_180032373
0x180032182  test    byte ptr [rax+1Ch], 8
0x180032186  jz      loc_180032373
0x18003218c  cmp     byte ptr [rax+19h], 2
0x180032190  jb      loc_180032373
0x180032196  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003219b  mov     edx, 18h
0x1800321a0  lea     rcx, aFailedStringcc; "Failed StringCchPrintf"
0x1800321a7  mov     dword ptr [rsp+2C8h+var_2A0], ebx
0x1800321ab  mov     [rsp+2C8h+var_2A8], rcx
0x1800321b0  mov     r9d, eax
0x1800321b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321ba  mov     rcx, [rcx+10h]
0x1800321be  call    WPP_SF_DsD
0x1800321c3  jmp     loc_180032373
0x1800321c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800321cf  cmp     rax, rdi
0x1800321d2  jz      short loc_180032202
0x1800321d4  test    byte ptr [rax+1Ch], 1
0x1800321d8  jz      short loc_180032202
0x1800321da  cmp     byte ptr [rax+19h], 2
0x1800321de  jb      short loc_180032202
0x1800321e0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800321e5  lea     rcx, [rsp+2C8h+var_258]
0x1800321ea  mov     [rsp+2C8h+var_2A8], rcx
0x1800321ef  mov     r9d, eax
0x1800321f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800321f9  mov     rcx, [rcx+10h]
0x1800321fd  call    WPP_SF_DS
0x180032202  lea     r8, [rsp+2C8h+Binding]; void **
0x180032207  lea     rdx, [rsp+2C8h+var_258]; unsigned __int16 *
0x18003220c  call    ?SetRenderHintRpcBind@@YAJPEAG0PEAPEAX@Z; SetRenderHintRpcBind(ushort *,ushort *,void * *)
0x180032211  mov     ebx, eax
0x180032213  test    eax, eax
0x180032215  jns     short loc_180032251
0x180032217  mov     rax, cs:WPP_GLOBAL_Control
0x18003221e  cmp     rax, rdi
0x180032221  jz      loc_180032373
0x180032227  test    byte ptr [rax+1Ch], 8
0x18003222b  jz      loc_180032373
0x180032231  cmp     byte ptr [rax+19h], 2
0x180032235  jb      loc_180032373
0x18003223b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032240  mov     edx, 1Ah
0x180032245  lea     rcx, aFailedBind; "Failed Bind"
0x18003224c  jmp     loc_1800321A7
0x180032251  mov     rax, [r15]
0x180032254  mov     [rsp+2C8h+var_260], 0
0x18003225d  mov     [rsp+2C8h+var_280], r13
0x180032262  mov     [rsp+2C8h+var_288], r12d
0x180032267  mov     [rsp+2C8h+var_290], r14d
0x18003226c  mov     ecx, [rsp+2C8h+var_274]
0x180032270  mov     [rsp+2C8h+var_298], ecx
0x180032274  mov     [rsp+2C8h+var_2A0], rsi
0x180032279  mov     [rsp+2C8h+var_2A8], rax
0x18003227e  mov     r9, [rsp+2C8h+Binding]
0x180032283  xor     r8d, r8d; pReturnValue
0x180032286  xor     edx, edx; nProcNum
0x180032288  lea     rcx, stru_18003EE90; pProxyInfo
0x18003228f  call    cs:__imp_NdrClientCall3
0x180032296  nop     dword ptr [rax+rax+00h]
0x18003229b  mov     rbx, rax
0x18003229e  mov     [rsp+2C8h+var_260], rax
0x1800322a3  mov     [rsp+2C8h+var_268], ebx
0x1800322a7  test    eax, eax
0x1800322a9  jns     short loc_1800322E4
0x1800322ab  mov     rax, cs:WPP_GLOBAL_Control
0x1800322b2  cmp     rax, rdi
0x1800322b5  jz      short loc_1800322DF
0x1800322b7  test    byte ptr [rax+1Ch], 1
0x1800322bb  jz      short loc_1800322DF
0x1800322bd  cmp     byte ptr [rax+19h], 2
0x1800322c1  jb      short loc_1800322DF
0x1800322c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800322c8  mov     dword ptr [rsp+2C8h+var_2A8], ebx
0x1800322cc  mov     r9d, eax
0x1800322cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800322d6  mov     rcx, [rcx+10h]
0x1800322da  call    WPP_SF_DDd
0x1800322df  jmp     loc_180032373
0x1800322e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800322eb  cmp     rax, rdi
0x1800322ee  jz      short loc_180032319
0x1800322f0  test    byte ptr [rax+1Ch], 1
0x1800322f4  jz      short loc_180032319
0x1800322f6  cmp     byte ptr [rax+19h], 2
0x1800322fa  jb      short loc_180032319
0x1800322fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032301  mov     edx, 1Ch
0x180032306  mov     r9d, eax
0x180032309  mov     rcx, cs:WPP_GLOBAL_Control
0x180032310  mov     rcx, [rcx+10h]
0x180032314  call    WPP_SF_D
0x180032319  jmp     short loc_180032373
0x18003231b  mov     edi, eax
0x18003231d  test    eax, eax
0x18003231f  jg      short loc_180032325
0x180032321  mov     ebx, eax
0x180032323  jmp     short loc_18003232E
0x180032325  movzx   ebx, di
0x180032328  or      ebx, 80070000h
0x18003232e  mov     [rsp+2C8h+var_268], ebx
0x180032332  lea     rcx, WPP_GLOBAL_Control
0x180032339  mov     rax, cs:WPP_GLOBAL_Control
0x180032340  cmp     rax, rcx
0x180032343  jz      short loc_180032373
0x180032345  test    byte ptr [rax+1Ch], 1
0x180032349  jz      short loc_180032373
0x18003234b  cmp     byte ptr [rax+19h], 2
0x18003234f  jb      short loc_180032373
0x180032351  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180032356  mov     edx, 1Dh
0x18003235b  mov     dword ptr [rsp+2C8h+var_2A8], edi
0x18003235f  mov     r9d, eax
0x180032362  mov     rcx, cs:WPP_GLOBAL_Control
0x180032369  mov     rcx, [rcx+10h]
0x18003236d  call    WPP_SF_Dd
0x180032372  nop
  ... truncated ...
```
