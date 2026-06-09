# WxGetLocalIpAddresses(ulong,int,_SOCKET_ADDRESS_LIST * *)

- ea: `0x18004da60`
- end: `0x18004dea9`
- name: `?WxGetLocalIpAddresses@@YAJKHPEAPEAU_SOCKET_ADDRESS_LIST@@@Z`
- size: `1097`
- prototype: `__int64 __fastcall(unsigned int, int, struct _SOCKET_ADDRESS_LIST **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004d730`
- `0x180085310`

## callees

- `0x18004da60`
- `0x1800569d0`
- `0x180071200`
- `0x1800722f0`
- `0x180072c70`
- `0x180095dbc`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004dca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004de80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004dca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004de80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004dbd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004dccc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004dbd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004dccc`
- `WS2_32!WSAIoctl` at `0x18004dc43`
- `WS2_32!WSAIoctl` at `0x18004dd21`
- `WS2_32!WSAIoctl` at `0x18004dd6c`
- `WS2_32!WSAIoctl` at `0x18004dc43`
- `WS2_32!WSAIoctl` at `0x18004dd21`
- `WS2_32!WSAIoctl` at `0x18004dd6c`
- `WS2_32!__imp_closesocket` at `0x18004ddf3`
- `WS2_32!__imp_closesocket` at `0x18004ddf3`
- `WS2_32!__imp_setsockopt` at `0x18004db7e`
- `WS2_32!__imp_setsockopt` at `0x18004db7e`
- `WS2_32!__imp_socket` at `0x18004db25`
- `WS2_32!__imp_socket` at `0x18004db25`
- `WS2_32!__imp_WSAGetLastError` at `0x18004dc60`
- `WS2_32!__imp_WSAGetLastError` at `0x18004dc60`
- `WS2_32!__imp_WSAStartup` at `0x18004dad7`
- `WS2_32!__imp_WSAStartup` at `0x18004dad7`
- `WS2_32!__imp_WSACleanup` at `0x18004ddff`
- `WS2_32!__imp_WSACleanup` at `0x18004ddff`

## pseudocode

```c
__int64 __fastcall WxGetLocalIpAddresses(__int64 a1, int a2, struct _SOCKET_ADDRESS_LIST **a3)
{
  struct _SOCKET_ADDRESS_LIST *v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  signed int v8; // edi
  int v9; // ebp
  SOCKET v10; // rax
  SOCKET v11; // rsi
  int Error; // eax
  int v13; // eax
  struct _SOCKET_ADDRESS_LIST *v14; // rax
  struct _SOCKET_ADDRESS_LIST *v15; // rax
  int v16; // eax
  int v17; // eax
  DWORD cbBytesReturned; // [rsp+58h] [rbp-1E0h] BYREF
  char optval[4]; // [rsp+5Ch] [rbp-1DCh] BYREF
  struct WSAData WSAData; // [rsp+60h] [rbp-1D8h] BYREF

  v5 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  *(_DWORD *)optval = 0;
  cbBytesReturned = 0;
  if ( (BYTE3(xmmword_1800AD720) & 0x20) != 0 )
    WPP_SF_dl(v6);
  *a3 = 0;
  v7 = WSAStartup(0x202u, &WSAData);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = 0;
    goto LABEL_10;
  }
  v9 = 1;
  v10 = socket(23, 1, 6);
  v11 = v10;
  if ( v10 == -1 )
  {
    Error = WxWSAGetLastError();
    v8 = Error;
    if ( Error > 0 )
      v8 = (unsigned __int16)Error | 0x80070000;
LABEL_10:
    if ( !v9 )
      goto LABEL_46;
    goto LABEL_45;
  }
  if ( setsockopt(v10, 41, 27, optval, 4) )
  {
    v13 = WxWSAGetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_44;
  }
  cbBytesReturned = 512;
  if ( g_fWxHeapExtensionInitialized )
    v14 = (struct _SOCKET_ADDRESS_LIST *)((__int64 (__fastcall *)(__int64))qword_1800AE528)(512);
  else
    v14 = (struct _SOCKET_ADDRESS_LIST *)HeapAlloc(g_hWxProcessHeap, 0, 0x200u);
  v5 = v14;
  if ( !v14 )
  {
    v8 = -2147024882;
LABEL_43:
    v5 = 0;
    goto LABEL_44;
  }
  if ( WSAIoctl(v11, 0x48000016u, 0, 0, v14, cbBytesReturned, &cbBytesReturned, 0, 0) )
  {
    while ( WSAGetLastError() == 10014 )
    {
      if ( v5 )
      {
        if ( g_fWxHeapExtensionInitialized )
          g_WxHeapExtensionInterfaces(v5);
        else
          HeapFree(g_hWxProcessHeap, 0, v5);
      }
      if ( g_fWxHeapExtensionInitialized )
        v15 = (struct _SOCKET_ADDRESS_LIST *)((__int64 (__fastcall *)(_QWORD))qword_1800AE528)(cbBytesReturned);
      else
        v15 = (struct _SOCKET_ADDRESS_LIST *)HeapAlloc(g_hWxProcessHeap, 0, cbBytesReturned);
      v5 = v15;
      if ( !v15 )
      {
        v8 = -2147024882;
        goto LABEL_43;
      }
      if ( !WSAIoctl(v11, 0x48000016u, 0, 0, v15, cbBytesReturned, &cbBytesReturned, 0, 0) )
        goto LABEL_32;
    }
    v17 = WxWSAGetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_44;
  }
LABEL_32:
  if ( a2 && WSAIoctl(v11, 0xC8000019, v5, cbBytesReturned, v5, cbBytesReturned, &cbBytesReturned, 0, 0) == -1 )
  {
    v16 = WxWSAGetLastError();
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_44;
  }
  v8 = WxConvertIpv6DualToIpv4(v5, 1);
  if ( v8 >= 0 )
  {
    *a3 = v5;
    goto LABEL_43;
  }
LABEL_44:
  closesocket(v11);
LABEL_45:
  WSACleanup();
LABEL_46:
  if ( (BYTE3(xmmword_1800AD720) & 0x20) != 0 )
    WPP_SF_d(1053, 11, WPP_0fbe4a4032d831b898f5353ebda9d1fe_Traceguids, (unsigned int)v8);
  if ( v5 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v5);
    else
      HeapFree(g_hWxProcessHeap, 0, v5);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004da60  mov     r11, rsp
0x18004da63  push    rbx
0x18004da64  push    rdi
0x18004da65  sub     rsp, 228h
0x18004da6c  mov     rax, cs:__security_cookie
0x18004da73  xor     rax, rsp
0x18004da76  mov     [rsp+238h+var_38], rax
0x18004da7e  mov     [r11-18h], r12
0x18004da82  lea     rcx, [rsp+238h+WSAData]; void *
0x18004da87  mov     [r11-20h], r14
0x18004da8b  xor     r12d, r12d
0x18004da8e  mov     [r11-28h], r15
0x18004da92  mov     r14d, edx
0x18004da95  mov     r15, r8
0x18004da98  mov     [rsp+238h+var_1E4], r12d
0x18004da9d  mov     r8d, 198h; Size
0x18004daa3  xor     edx, edx; Val
0x18004daa5  mov     ebx, r12d
0x18004daa8  call    memset_0
0x18004daad  mov     dword ptr [rsp+238h+optval], r12d
0x18004dab2  mov     [rsp+238h+cbBytesReturned], r12d
0x18004dab7  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004dabe  jz      short loc_18004DACA
0x18004dac0  mov     [rsp+238h+optlen], r14d
0x18004dac5  call    WPP_SF_dl
0x18004daca  mov     ecx, 202h; wVersionRequested
0x18004dacf  mov     [r15], r12
0x18004dad2  lea     rdx, [rsp+238h+WSAData]; lpWSAData
0x18004dad7  call    cs:__imp_WSAStartup
0x18004dade  nop     dword ptr [rax+rax+00h]
0x18004dae3  mov     edi, eax
0x18004dae5  test    eax, eax
0x18004dae7  jle     short loc_18004DAF2
0x18004dae9  movzx   edi, ax
0x18004daec  or      edi, 80070000h
0x18004daf2  mov     [rsp+238h+arg_0], rbp
0x18004dafa  mov     [rsp+238h+arg_8], rsi
0x18004db02  test    edi, edi
0x18004db04  jns     short loc_18004DB13
0x18004db06  mov     ebp, r12d
0x18004db09  mov     [rsp+238h+var_1E4], 163h
0x18004db11  jmp     short loc_18004DB56
0x18004db13  mov     ebp, 1
0x18004db18  mov     r8d, 6; protocol
0x18004db1e  mov     edx, ebp; type
0x18004db20  mov     ecx, 17h; af
0x18004db25  call    cs:__imp_socket
0x18004db2c  nop     dword ptr [rax+rax+00h]
0x18004db31  mov     rsi, rax
0x18004db34  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004db38  jnz     short loc_18004DB63
0x18004db3a  call    WxWSAGetLastError
0x18004db3f  mov     edi, eax
0x18004db41  test    eax, eax
0x18004db43  jle     short loc_18004DB4E
0x18004db45  movzx   edi, ax
0x18004db48  or      edi, 80070000h
0x18004db4e  mov     [rsp+238h+var_1E4], 169h
0x18004db56  test    ebp, ebp
0x18004db58  jz      loc_18004DE0B
0x18004db5e  jmp     loc_18004DDFF
0x18004db63  lea     r9, [rsp+238h+optval]; optval
0x18004db68  mov     [rsp+238h+optlen], 4; optlen
0x18004db70  mov     edx, 29h ; ')'; level
0x18004db75  mov     r8d, 1Bh; optname
0x18004db7b  mov     rcx, rsi; s
0x18004db7e  call    cs:__imp_setsockopt
0x18004db85  nop     dword ptr [rax+rax+00h]
0x18004db8a  test    eax, eax
0x18004db8c  jz      short loc_18004DBAF
0x18004db8e  call    WxWSAGetLastError
0x18004db93  mov     edi, eax
0x18004db95  test    eax, eax
0x18004db97  jle     short loc_18004DBA2
0x18004db99  movzx   edi, ax
0x18004db9c  or      edi, 80070000h
0x18004dba2  mov     [rsp+238h+var_1E4], 171h
0x18004dbaa  jmp     loc_18004DDF0
0x18004dbaf  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, ebx; int g_fWxHeapExtensionInitialized
0x18004dbb5  mov     [rsp+238h+cbBytesReturned], 200h
0x18004dbbd  mov     [rsp+238h+var_1E4], r12d
0x18004dbc2  jnz     short loc_18004DBE1
0x18004dbc4  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18004dbcb  xor     edx, edx; dwFlags
0x18004dbcd  mov     r8d, 200h; dwBytes
0x18004dbd3  call    cs:__imp_HeapAlloc
0x18004dbda  nop     dword ptr [rax+rax+00h]
0x18004dbdf  jmp     short loc_18004DBF2
0x18004dbe1  mov     rax, cs:qword_1800AE528
0x18004dbe8  mov     ecx, 200h
0x18004dbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbf2  mov     rbx, rax
0x18004dbf5  test    rax, rax
0x18004dbf8  jnz     short loc_18004DC14
0x18004dbfa  mov     [rsp+238h+var_1E4], 34h ; '4'
0x18004dc02  mov     edi, 8007000Eh
0x18004dc07  mov     [rsp+238h+var_1E4], 175h
0x18004dc0f  jmp     loc_18004DDED
0x18004dc14  mov     [rsp+238h+lpCompletionRoutine], r12; lpCompletionRoutine
0x18004dc19  lea     rax, [rsp+238h+cbBytesReturned]
0x18004dc1e  mov     [rsp+238h+lpOverlapped], r12; lpOverlapped
0x18004dc23  xor     r9d, r9d; cbInBuffer
0x18004dc26  mov     [rsp+238h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18004dc2b  xor     r8d, r8d; lpvInBuffer
0x18004dc2e  mov     eax, [rsp+238h+cbBytesReturned]
0x18004dc32  mov     edx, 48000016h; dwIoControlCode
0x18004dc37  mov     [rsp+238h+cbOutBuffer], eax; cbOutBuffer
0x18004dc3b  mov     rcx, rsi; s
0x18004dc3e  mov     qword ptr [rsp+238h+optlen], rbx; lpvOutBuffer
0x18004dc43  call    cs:__imp_WSAIoctl
0x18004dc4a  nop     dword ptr [rax+rax+00h]
0x18004dc4f  test    eax, eax
0x18004dc51  jz      loc_18004DD35
0x18004dc57  nop     word ptr [rax+rax+00000000h]
0x18004dc60  call    cs:__imp_WSAGetLastError
0x18004dc67  nop     dword ptr [rax+rax+00h]
0x18004dc6c  cmp     eax, 271Eh
0x18004dc71  jnz     loc_18004DDB2
0x18004dc77  test    rbx, rbx
0x18004dc7a  jz      short loc_18004DCAE
0x18004dc7c  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x18004dc83  jz      short loc_18004DC96
0x18004dc85  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18004dc8c  mov     rcx, rbx
0x18004dc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc94  jmp     short loc_18004DCAE
0x18004dc96  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18004dc9d  mov     r8, rbx; lpMem
0x18004dca0  xor     edx, edx; dwFlags
0x18004dca2  call    cs:__imp_HeapFree
0x18004dca9  nop     dword ptr [rax+rax+00h]
0x18004dcae  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r12d; int g_fWxHeapExtensionInitialized
0x18004dcb5  mov     ecx, [rsp+238h+cbBytesReturned]
0x18004dcb9  mov     [rsp+238h+var_1E4], r12d
0x18004dcbe  jnz     short loc_18004DCDA
0x18004dcc0  mov     r8d, ecx; dwBytes
0x18004dcc3  xor     edx, edx; dwFlags
0x18004dcc5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18004dccc  call    cs:__imp_HeapAlloc
0x18004dcd3  nop     dword ptr [rax+rax+00h]
0x18004dcd8  jmp     short loc_18004DCE6
0x18004dcda  mov     rax, cs:qword_1800AE528
0x18004dce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dce6  mov     rbx, rax
0x18004dce9  test    rax, rax
0x18004dcec  jz      loc_18004DD9B
0x18004dcf2  mov     [rsp+238h+lpCompletionRoutine], r12; lpCompletionRoutine
0x18004dcf7  lea     rax, [rsp+238h+cbBytesReturned]
0x18004dcfc  mov     [rsp+238h+lpOverlapped], r12; lpOverlapped
0x18004dd01  xor     r9d, r9d; cbInBuffer
0x18004dd04  mov     [rsp+238h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18004dd09  xor     r8d, r8d; lpvInBuffer
0x18004dd0c  mov     eax, [rsp+238h+cbBytesReturned]
0x18004dd10  mov     edx, 48000016h; dwIoControlCode
0x18004dd15  mov     [rsp+238h+cbOutBuffer], eax; cbOutBuffer
0x18004dd19  mov     rcx, rsi; s
0x18004dd1c  mov     qword ptr [rsp+238h+optlen], rbx; lpvOutBuffer
0x18004dd21  call    cs:__imp_WSAIoctl
0x18004dd28  nop     dword ptr [rax+rax+00h]
0x18004dd2d  test    eax, eax
0x18004dd2f  jnz     loc_18004DC60
0x18004dd35  test    r14d, r14d
0x18004dd38  jz      loc_18004DDD0
0x18004dd3e  mov     r9d, [rsp+238h+cbBytesReturned]; cbInBuffer
0x18004dd43  lea     rax, [rsp+238h+cbBytesReturned]
0x18004dd48  mov     [rsp+238h+lpCompletionRoutine], r12; lpCompletionRoutine
0x18004dd4d  mov     r8, rbx; lpvInBuffer
0x18004dd50  mov     [rsp+238h+lpOverlapped], r12; lpOverlapped
0x18004dd55  mov     edx, 0C8000019h; dwIoControlCode
0x18004dd5a  mov     [rsp+238h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18004dd5f  mov     rcx, rsi; s
0x18004dd62  mov     [rsp+238h+cbOutBuffer], r9d; cbOutBuffer
0x18004dd67  mov     qword ptr [rsp+238h+optlen], rbx; lpvOutBuffer
0x18004dd6c  call    cs:__imp_WSAIoctl
0x18004dd73  nop     dword ptr [rax+rax+00h]
0x18004dd78  cmp     eax, 0FFFFFFFFh
0x18004dd7b  jnz     short loc_18004DDD0
0x18004dd7d  call    WxWSAGetLastError
0x18004dd82  mov     edi, eax
0x18004dd84  test    eax, eax
0x18004dd86  jle     short loc_18004DD91
0x18004dd88  movzx   edi, ax
0x18004dd8b  or      edi, 80070000h
0x18004dd91  mov     [rsp+238h+var_1E4], 1A3h
0x18004dd99  jmp     short loc_18004DDF0
0x18004dd9b  mov     [rsp+238h+var_1E4], 34h ; '4'
0x18004dda3  mov     edi, 8007000Eh
0x18004dda8  mov     [rsp+238h+var_1E4], 18Ch
0x18004ddb0  jmp     short loc_18004DDED
0x18004ddb2  call    WxWSAGetLastError
0x18004ddb7  mov     edi, eax
0x18004ddb9  test    eax, eax
0x18004ddbb  jle     short loc_18004DDC6
0x18004ddbd  movzx   edi, ax
0x18004ddc0  or      edi, 80070000h
0x18004ddc6  mov     [rsp+238h+var_1E4], 189h
0x18004ddce  jmp     short loc_18004DDF0
0x18004ddd0  mov     edx, ebp; int
0x18004ddd2  mov     rcx, rbx; struct _SOCKET_ADDRESS_LIST *
0x18004ddd5  call    ?WxConvertIpv6DualToIpv4@@YAJPEAU_SOCKET_ADDRESS_LIST@@H@Z; WxConvertIpv6DualToIpv4(_SOCKET_ADDRESS_LIST *,int)
0x18004ddda  mov     edi, eax
0x18004dddc  test    eax, eax
0x18004ddde  jns     short loc_18004DDEA
0x18004dde0  mov     [rsp+238h+var_1E4], 1A8h
0x18004dde8  jmp     short loc_18004DDF0
0x18004ddea  mov     [r15], rbx
0x18004dded  mov     rbx, r12
0x18004ddf0  mov     rcx, rsi; s
0x18004ddf3  call    cs:__imp_closesocket
0x18004ddfa  nop     dword ptr [rax+rax+00h]
0x18004ddff  call    cs:__imp_WSACleanup
0x18004de06  nop     dword ptr [rax+rax+00h]
0x18004de0b  test    byte ptr cs:xmmword_1800AD720+3, 20h
0x18004de12  mov     r15, [rsp+238h+var_28]
0x18004de1a  mov     r14, [rsp+238h+var_20]
0x18004de22  mov     r12, [rsp+238h+var_18]
0x18004de2a  mov     rsi, [rsp+238h+arg_8]
0x18004de32  mov     rbp, [rsp+238h+arg_0]
0x18004de3a  jz      short loc_18004DE55
0x18004de3c  mov     edx, 0Bh
0x18004de41  lea     r8, WPP_0fbe4a4032d831b898f5353ebda9d1fe_Traceguids
0x18004de48  mov     ecx, 41Dh
0x18004de4d  mov     r9d, edi
0x18004de50  call    WPP_SF_d
0x18004de55  test    rbx, rbx
0x18004de58  jz      short loc_18004DE8C
0x18004de5a  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x18004de61  jz      short loc_18004DE74
0x18004de63  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18004de6a  mov     rcx, rbx
0x18004de6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de72  jmp     short loc_18004DE8C
0x18004de74  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18004de7b  mov     r8, rbx; lpMem
0x18004de7e  xor     edx, edx; dwFlags
0x18004de80  call    cs:__imp_HeapFree
0x18004de87  nop     dword ptr [rax+rax+00h]
0x18004de8c  mov     eax, edi
0x18004de8e  mov     rcx, [rsp+238h+var_38]
0x18004de96  xor     rcx, rsp; StackCookie
0x18004de99  call    __security_check_cookie
0x18004de9e  add     rsp, 228h
0x18004dea5  pop     rdi
0x18004dea6  pop     rbx
0x18004dea7  retn
```
