# InitializeEventingClasses(void)

- ea: `0x18000c9fc`
- end: `0x18000cc4f`
- name: `?InitializeEventingClasses@@YAJXZ`
- size: `595`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000c078`

## callees

- `0x18000c9fc`
- `0x18000d8d8`
- `0x180021ae4`
- `0x1800271fc`
- `0x180027b48`
- `0x18002911c`
- `0x180029df0`
- `0x180033698`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ca0c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ca40`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ca0c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ca40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caf7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000cae7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000cae7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000caad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000caad`

## string_xrefs

- `0x18000ca7e`: `SYSTEM\CurrentControlSet\Services\SSDPSRV\Parameters`

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
  unsigned int inited; // eax
  unsigned int v8; // ebx
  LPCSTR v9; // rcx
  __int64 v10; // rdx
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF

  v0 = (DelayedLoadCryptoRandom *)malloc(0x40u);
  if ( !v0 )
  {
    g_pRandomGenerator = 0;
LABEL_24:
    v8 = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      return v8;
    v10 = 10;
LABEL_27:
    WPP_SF_(*((_QWORD *)v9 + 2), v10, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids);
    return v8;
  }
  g_pRandomGenerator = DelayedLoadCryptoRandom::DelayedLoadCryptoRandom(v0);
  if ( !g_pRandomGenerator )
    goto LABEL_24;
  v1 = (BaseHttpListener *)malloc(0x150u);
  v2 = v1;
  if ( !v1 )
  {
    g_pEventHTTPListener = 0;
    v8 = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      return v8;
    v10 = 11;
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
  inited = BaseHttpListener::InitListening(v6, v5, EventingPort);
  v8 = inited;
  if ( inited )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids, inited);
    if ( g_pEventHTTPListener )
      (**(void (__fastcall ***)(BaseHttpListener *, __int64))g_pEventHTTPListener)(g_pEventHTTPListener, 1);
    g_pEventHTTPListener = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18000c9fc  push    rbp
0x18000c9fe  push    rbx
0x18000c9ff  push    rdi
0x18000ca00  mov     rbp, rsp
0x18000ca03  sub     rsp, 40h
0x18000ca07  mov     ecx, 40h ; '@'; Size
0x18000ca0c  call    cs:__imp_malloc
0x18000ca13  nop     dword ptr [rax+rax+00h]
0x18000ca18  test    rax, rax
0x18000ca1b  jz      loc_18000CC06
0x18000ca21  mov     rcx, rax; this
0x18000ca24  call    ??0DelayedLoadCryptoRandom@@QEAA@XZ; DelayedLoadCryptoRandom::DelayedLoadCryptoRandom(void)
0x18000ca29  mov     cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA, rax; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18000ca30  test    rax, rax
0x18000ca33  jz      loc_18000CC11
0x18000ca39  mov     edi, 150h
0x18000ca3e  mov     ecx, edi; Size
0x18000ca40  call    cs:__imp_malloc
0x18000ca47  nop     dword ptr [rax+rax+00h]
0x18000ca4c  mov     rbx, rax
0x18000ca4f  test    rax, rax
0x18000ca52  jz      loc_18000CBD6
0x18000ca58  mov     r8d, edi; Size
0x18000ca5b  xor     edx, edx; Val
0x18000ca5d  mov     rcx, rax; void *
0x18000ca60  call    memset_0
0x18000ca65  mov     rcx, rbx; this
0x18000ca68  call    ??0BaseHttpListener@@QEAA@XZ; BaseHttpListener::BaseHttpListener(void)
0x18000ca6d  lea     rax, ??_7EventHttpListener@@6B@; const EventHttpListener::`vftable'
0x18000ca74  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, rbx; BaseHttpListener * g_pEventHTTPListener
0x18000ca7b  mov     [rbx], rax
0x18000ca7e  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\SS"...
0x18000ca85  lea     rax, [rbp+hKey]
0x18000ca89  mov     [rbp+hKey], 0
0x18000ca91  mov     r9d, 20019h; samDesired
0x18000ca97  mov     [rsp+40h+phkResult], rax; phkResult
0x18000ca9c  xor     r8d, r8d; ulOptions
0x18000ca9f  mov     [rbp+Data], 19000h
0x18000caa6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000caad  call    cs:__imp_RegOpenKeyExA
0x18000cab4  nop     dword ptr [rax+rax+00h]
0x18000cab9  test    eax, eax
0x18000cabb  jnz     short loc_18000CB03
0x18000cabd  mov     rcx, [rbp+hKey]; hKey
0x18000cac1  lea     rax, [rbp+cbData]
0x18000cac5  mov     [rsp+40h+lpcbData], rax; int
0x18000caca  lea     rdx, ValueName; "MaxHttpSize"
0x18000cad1  lea     rax, [rbp+Data]
0x18000cad5  mov     [rbp+cbData], 4
0x18000cadc  xor     r9d, r9d; lpType
0x18000cadf  mov     [rsp+40h+phkResult], rax; int
0x18000cae4  xor     r8d, r8d; lpReserved
0x18000cae7  call    cs:__imp_RegQueryValueExA
0x18000caee  nop     dword ptr [rax+rax+00h]
0x18000caf3  mov     rcx, [rbp+hKey]; hKey
0x18000caf7  call    cs:__imp_RegCloseKey
0x18000cafe  nop     dword ptr [rax+rax+00h]
0x18000cb03  mov     ecx, [rbp+Data]
0x18000cb06  mov     eax, 4000h
0x18000cb0b  cmp     ecx, eax
0x18000cb0d  ja      short loc_18000CB14
0x18000cb0f  mov     ecx, eax
0x18000cb11  mov     [rbp+Data], eax
0x18000cb14  mov     eax, 1000000h
0x18000cb19  cmp     ecx, eax
0x18000cb1b  jb      short loc_18000CB22
0x18000cb1d  mov     ecx, eax
0x18000cb1f  mov     [rbp+Data], eax
0x18000cb22  mov     rax, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x18000cb29  mov     edx, 7FFFFFFFh
0x18000cb2e  cmp     ecx, edx
0x18000cb30  cmova   ecx, edx
0x18000cb33  xchg    ecx, [rax+144h]
0x18000cb39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb40  lea     rdi, WPP_GLOBAL_Control
0x18000cb47  cmp     rcx, rdi
0x18000cb4a  jz      short loc_18000CB6B
0x18000cb4c  test    byte ptr [rcx+1Ch], 8
0x18000cb50  jz      short loc_18000CB6B
0x18000cb52  mov     r9d, [rbp+Data]
0x18000cb56  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000cb5d  mov     rcx, [rcx+10h]
0x18000cb61  mov     edx, 0Ch
0x18000cb66  call    WPP_SF_d
0x18000cb6b  call    ?GetEventingPort@@YAGXZ; GetEventingPort(void)
0x18000cb70  movzx   r8d, ax; unsigned int
0x18000cb74  call    ?InitListening@BaseHttpListener@@QEAAJPEBDKHHHH@Z; BaseHttpListener::InitListening(char const *,ulong,int,int,int,int)
0x18000cb79  mov     ebx, eax
0x18000cb7b  test    eax, eax
0x18000cb7d  jz      loc_18000CC44
0x18000cb83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb8a  cmp     rcx, rdi
0x18000cb8d  jz      short loc_18000CBAD
0x18000cb8f  test    byte ptr [rcx+1Ch], 1
0x18000cb93  jz      short loc_18000CBAD
0x18000cb95  mov     rcx, [rcx+10h]
0x18000cb99  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000cba0  mov     edx, 0Dh
0x18000cba5  mov     r9d, eax
0x18000cba8  call    WPP_SF_d
0x18000cbad  mov     rcx, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x18000cbb4  test    rcx, rcx
0x18000cbb7  jz      short loc_18000CBC9
0x18000cbb9  mov     rax, [rcx]
0x18000cbbc  mov     edx, 1
0x18000cbc1  mov     rax, [rax]
0x18000cbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbc9  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, 0; BaseHttpListener * g_pEventHTTPListener
0x18000cbd4  jmp     short loc_18000CC44
0x18000cbd6  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, 0; BaseHttpListener * g_pEventHTTPListener
0x18000cbe1  mov     ebx, 8007000Eh
0x18000cbe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbed  lea     rdi, WPP_GLOBAL_Control
0x18000cbf4  cmp     rcx, rdi
0x18000cbf7  jz      short loc_18000CC44
0x18000cbf9  test    byte ptr [rcx+1Ch], 1
0x18000cbfd  jz      short loc_18000CC44
0x18000cbff  mov     edx, 0Bh
0x18000cc04  jmp     short loc_18000CC34
0x18000cc06  mov     cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA, 0; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18000cc11  mov     ebx, 8007000Eh
0x18000cc16  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc1d  lea     rdi, WPP_GLOBAL_Control
0x18000cc24  cmp     rcx, rdi
0x18000cc27  jz      short loc_18000CC44
0x18000cc29  test    byte ptr [rcx+1Ch], 1
0x18000cc2d  jz      short loc_18000CC44
0x18000cc2f  mov     edx, 0Ah
0x18000cc34  mov     rcx, [rcx+10h]
0x18000cc38  lea     r8, WPP_8c7621993c4f3bc58a04c2ed1da19d07_Traceguids
0x18000cc3f  call    WPP_SF_
0x18000cc44  mov     eax, ebx
0x18000cc46  add     rsp, 40h
0x18000cc4a  pop     rdi
0x18000cc4b  pop     rbx
0x18000cc4c  pop     rbp
0x18000cc4d  retn
```
