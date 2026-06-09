# InitializeEventingClasses(void)

- ea: `0x18000b064`
- end: `0x18000b298`
- name: `?InitializeEventingClasses@@YAJXZ`
- size: `564`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000a768`

## callees

- `0x18000b064`
- `0x18000be04`
- `0x180020598`
- `0x1800255a8`
- `0x180025e20`
- `0x18002735c`
- `0x180028000`
- `0x180030f50`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b074`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b0a2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b074`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000b0a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b147`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b147`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b13d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b13d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b109`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000b109`

## string_xrefs

- `0x18000b0da`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`

## pseudocode

```c
__int64 InitializeEventingClasses(void)
{
  DelayedLoadCryptoRandom *v0; // rax
  BaseHttpListener *v1; // rax
  BaseHttpListener *v2; // rbx
  unsigned __int32 v3; // ecx
  unsigned __int16 EventingPort; // ax
  const char *v5; // rdx
  BaseHttpListener *v6; // rcx
  int v7; // r9d
  unsigned int inited; // eax
  unsigned int v9; // ebx
  LPCSTR v10; // rcx
  __int64 v11; // rdx
  int phkResult; // [rsp+20h] [rbp-20h]
  int lpcbData; // [rsp+28h] [rbp-18h]
  int v15; // [rsp+30h] [rbp-10h]
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF

  v0 = (DelayedLoadCryptoRandom *)malloc(0x40u);
  if ( !v0 )
  {
    g_pRandomGenerator = 0;
LABEL_24:
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      return v9;
    v11 = 10;
LABEL_27:
    WPP_SF_(*((_QWORD *)v10 + 2), v11, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
    return v9;
  }
  g_pRandomGenerator = DelayedLoadCryptoRandom::DelayedLoadCryptoRandom(v0);
  if ( !g_pRandomGenerator )
    goto LABEL_24;
  v1 = (BaseHttpListener *)malloc(0x150u);
  v2 = v1;
  if ( !v1 )
  {
    g_pEventHTTPListener = 0;
    v9 = -2147024882;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      return v9;
    v11 = 11;
    goto LABEL_27;
  }
  memset_0(v1, 0, 0x150u);
  BaseHttpListener::BaseHttpListener(v2);
  g_pEventHTTPListener = v2;
  *(_QWORD *)v2 = &EventHttpListener::`vftable';
  hKey = 0;
  Data = 102400;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "SYSTEM\\CurrentControlSet\\Services\\SSDPSRV\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    RegQueryValueExA(hKey, "MaxHttpSize", 0, 0, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
  }
  v3 = Data;
  if ( Data <= 0x4000 )
  {
    v3 = 0x4000;
    Data = 0x4000;
  }
  if ( v3 >= 0x1000000 )
  {
    v3 = 0x1000000;
    Data = 0x1000000;
  }
  _InterlockedExchange((volatile __int32 *)g_pEventHTTPListener + 81, v3);
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, Data);
  EventingPort = GetEventingPort();
  inited = BaseHttpListener::InitListening(v6, v5, EventingPort, v7, phkResult, lpcbData, v15);
  v9 = inited;
  if ( inited )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, inited);
    if ( g_pEventHTTPListener )
      (**(void (__fastcall ***)(BaseHttpListener *, __int64))g_pEventHTTPListener)(g_pEventHTTPListener, 1);
    g_pEventHTTPListener = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000b064  push    rbp
0x18000b066  push    rbx
0x18000b067  push    rdi
0x18000b068  mov     rbp, rsp
0x18000b06b  sub     rsp, 40h
0x18000b06f  mov     ecx, 40h ; '@'; Size
0x18000b074  call    cs:__imp_malloc
0x18000b07a  test    rax, rax
0x18000b07d  jz      loc_18000B250
0x18000b083  mov     rcx, rax; this
0x18000b086  call    ??0DelayedLoadCryptoRandom@@QEAA@XZ; DelayedLoadCryptoRandom::DelayedLoadCryptoRandom(void)
0x18000b08b  mov     cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA, rax; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18000b092  test    rax, rax
0x18000b095  jz      loc_18000B25B
0x18000b09b  mov     edi, 150h
0x18000b0a0  mov     ecx, edi; Size
0x18000b0a2  call    cs:__imp_malloc
0x18000b0a8  mov     rbx, rax
0x18000b0ab  test    rax, rax
0x18000b0ae  jz      loc_18000B220
0x18000b0b4  mov     r8d, edi; Size
0x18000b0b7  xor     edx, edx; Val
0x18000b0b9  mov     rcx, rax; void *
0x18000b0bc  call    memset_0
0x18000b0c1  mov     rcx, rbx; this
0x18000b0c4  call    ??0BaseHttpListener@@QEAA@XZ; BaseHttpListener::BaseHttpListener(void)
0x18000b0c9  lea     rax, ??_7EventHttpListener@@6B@; const EventHttpListener::`vftable'
0x18000b0d0  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, rbx; BaseHttpListener * g_pEventHTTPListener
0x18000b0d7  mov     [rbx], rax
0x18000b0da  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x18000b0e1  lea     rax, [rbp+hKey]
0x18000b0e5  mov     [rbp+hKey], 0
0x18000b0ed  mov     r9d, 20019h; samDesired
0x18000b0f3  mov     [rsp+40h+phkResult], rax; phkResult
0x18000b0f8  xor     r8d, r8d; ulOptions
0x18000b0fb  mov     [rbp+Data], 19000h
0x18000b102  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b109  call    cs:__imp_RegOpenKeyExA
0x18000b10f  test    eax, eax
0x18000b111  jnz     short loc_18000B14D
0x18000b113  mov     rcx, [rbp+hKey]; hKey
0x18000b117  lea     rax, [rbp+cbData]
0x18000b11b  mov     [rsp+40h+lpcbData], rax; int
0x18000b120  lea     rdx, ValueName; "MaxHttpSize"
0x18000b127  lea     rax, [rbp+Data]
0x18000b12b  mov     [rbp+cbData], 4
0x18000b132  xor     r9d, r9d; lpType
0x18000b135  mov     [rsp+40h+phkResult], rax; int
0x18000b13a  xor     r8d, r8d; lpReserved
0x18000b13d  call    cs:__imp_RegQueryValueExA
0x18000b143  mov     rcx, [rbp+hKey]; hKey
0x18000b147  call    cs:__imp_RegCloseKey
0x18000b14d  mov     ecx, [rbp+Data]
0x18000b150  mov     eax, 4000h
0x18000b155  cmp     ecx, eax
0x18000b157  ja      short loc_18000B15E
0x18000b159  mov     ecx, eax
0x18000b15b  mov     [rbp+Data], eax
0x18000b15e  mov     eax, 1000000h
0x18000b163  cmp     ecx, eax
0x18000b165  jb      short loc_18000B16C
0x18000b167  mov     ecx, eax
0x18000b169  mov     [rbp+Data], eax
0x18000b16c  mov     rax, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x18000b173  mov     edx, 7FFFFFFFh
0x18000b178  cmp     ecx, edx
0x18000b17a  cmova   ecx, edx
0x18000b17d  xchg    ecx, [rax+144h]
0x18000b183  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b18a  lea     rdi, WPP_GLOBAL_Control
0x18000b191  cmp     rcx, rdi
0x18000b194  jz      short loc_18000B1B5
0x18000b196  test    byte ptr [rcx+1Ch], 8
0x18000b19a  jz      short loc_18000B1B5
0x18000b19c  mov     r9d, [rbp+Data]
0x18000b1a0  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000b1a7  mov     rcx, [rcx+10h]
0x18000b1ab  mov     edx, 0Ch
0x18000b1b0  call    WPP_SF_d
0x18000b1b5  call    ?GetEventingPort@@YAGXZ; GetEventingPort(void)
0x18000b1ba  movzx   r8d, ax; unsigned int
0x18000b1be  call    ?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z; BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)
0x18000b1c3  mov     ebx, eax
0x18000b1c5  test    eax, eax
0x18000b1c7  jz      loc_18000B28E
0x18000b1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1d4  cmp     rcx, rdi
0x18000b1d7  jz      short loc_18000B1F7
0x18000b1d9  test    byte ptr [rcx+1Ch], 1
0x18000b1dd  jz      short loc_18000B1F7
0x18000b1df  mov     rcx, [rcx+10h]
0x18000b1e3  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000b1ea  mov     edx, 0Dh
0x18000b1ef  mov     r9d, eax
0x18000b1f2  call    WPP_SF_d
0x18000b1f7  mov     rcx, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x18000b1fe  test    rcx, rcx
0x18000b201  jz      short loc_18000B213
0x18000b203  mov     rax, [rcx]
0x18000b206  mov     edx, 1
0x18000b20b  mov     rax, [rax]
0x18000b20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b213  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, 0; BaseHttpListener * g_pEventHTTPListener
0x18000b21e  jmp     short loc_18000B28E
0x18000b220  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, 0; BaseHttpListener * g_pEventHTTPListener
0x18000b22b  mov     ebx, 8007000Eh
0x18000b230  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b237  lea     rdi, WPP_GLOBAL_Control
0x18000b23e  cmp     rcx, rdi
0x18000b241  jz      short loc_18000B28E
0x18000b243  test    byte ptr [rcx+1Ch], 1
0x18000b247  jz      short loc_18000B28E
0x18000b249  mov     edx, 0Bh
0x18000b24e  jmp     short loc_18000B27E
0x18000b250  mov     cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA, 0; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18000b25b  mov     ebx, 8007000Eh
0x18000b260  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b267  lea     rdi, WPP_GLOBAL_Control
0x18000b26e  cmp     rcx, rdi
0x18000b271  jz      short loc_18000B28E
0x18000b273  test    byte ptr [rcx+1Ch], 1
0x18000b277  jz      short loc_18000B28E
0x18000b279  mov     edx, 0Ah
0x18000b27e  mov     rcx, [rcx+10h]
0x18000b282  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000b289  call    WPP_SF_
0x18000b28e  mov     eax, ebx
0x18000b290  add     rsp, 40h
0x18000b294  pop     rdi
0x18000b295  pop     rbx
0x18000b296  pop     rbp
0x18000b297  retn
```
