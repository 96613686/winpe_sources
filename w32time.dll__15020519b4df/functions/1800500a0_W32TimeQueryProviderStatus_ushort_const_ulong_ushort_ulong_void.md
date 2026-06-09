# W32TimeQueryProviderStatus(ushort const *,ulong,ushort *,ulong,void * *)

- ea: `0x1800500a0`
- end: `0x1800503d1`
- name: `?W32TimeQueryProviderStatus@@YAJPEBGKPEAGKPEAPEAX@Z`
- size: `817`
- prototype: `__int64 __usercall@<rax>(RPC_WSTR NetworkAddr@<rcx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800508d0`
- `0x1800508f0`

## callees

- `0x180029ad0`
- `0x1800500a0`
- `0x180050dc8`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180050153`
- `RPCRT4!RpcStringFreeW` at `0x180050226`
- `RPCRT4!RpcStringFreeW` at `0x1800502f5`
- `RPCRT4!RpcStringFreeW` at `0x180050153`
- `RPCRT4!RpcStringFreeW` at `0x180050226`
- `RPCRT4!RpcStringFreeW` at `0x1800502f5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050140`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050213`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800502e2`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050140`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180050213`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800502e2`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050120`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800501f3`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800502c6`
- `RPCRT4!RpcStringBindingComposeW` at `0x180050120`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800501f3`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800502c6`
- `RPCRT4!RpcBindingFree` at `0x1800501ad`
- `RPCRT4!RpcBindingFree` at `0x180050280`
- `RPCRT4!RpcBindingFree` at `0x18005033b`
- `RPCRT4!RpcBindingFree` at `0x1800501ad`
- `RPCRT4!RpcBindingFree` at `0x180050280`
- `RPCRT4!RpcBindingFree` at `0x18005033b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800503a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800503b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800503a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800503b7`

## pseudocode

```c
__int64 __fastcall W32TimeQueryProviderStatus(
        RPC_WSTR NetworkAddr,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        void **a5)
{
  unsigned int ProviderStatus; // ebx
  _QWORD *v10; // rdx
  void *v11; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+40h] [rbp-38h] BYREF
  HLOCAL hMem[6]; // [rsp+48h] [rbp-30h] BYREF

  Binding = 0;
  hMem[0] = 0;
  String = 0;
  if ( !a5 )
    return 2147942487LL;
  ProviderStatus = 1717;
  if ( !NetworkAddr )
  {
    ProviderStatus = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"W32TIME_ALT", 0, &String);
    if ( !ProviderStatus )
    {
      ProviderStatus = RpcBindingFromStringBindingW(String, &Binding);
      RpcStringFreeW(&String);
      SetMyRpcSecurity(Binding);
      if ( !ProviderStatus )
      {
        ProviderStatus = c_W32TimeQueryProviderStatus(Binding, a2, a3, hMem);
        RpcBindingFree(&Binding);
      }
    }
  }
  if ( ProviderStatus == 1717 || ProviderStatus == 1722 )
  {
    ProviderStatus = RpcStringBindingComposeW(
                       0,
                       (RPC_WSTR)L"ncacn_np",
                       NetworkAddr,
                       (RPC_WSTR)L"\\PIPE\\W32TIME",
                       0,
                       &String);
    if ( !ProviderStatus )
    {
      ProviderStatus = RpcBindingFromStringBindingW(String, &Binding);
      RpcStringFreeW(&String);
      SetMyRpcSecurity(Binding);
      if ( !ProviderStatus )
      {
        ProviderStatus = c_W32TimeQueryProviderStatus(Binding, a2, a3, hMem);
        RpcBindingFree(&Binding);
      }
    }
  }
  if ( ProviderStatus != 1717 && ProviderStatus != 1722 )
    goto LABEL_17;
  ProviderStatus = RpcStringBindingComposeW(
                     0,
                     (RPC_WSTR)L"ncacn_np",
                     NetworkAddr,
                     (RPC_WSTR)L"\\PIPE\\W32TIME_ALT",
                     0,
                     &String);
  if ( ProviderStatus )
    goto LABEL_17;
  ProviderStatus = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  SetMyRpcSecurity(Binding);
  if ( !ProviderStatus )
  {
    ProviderStatus = c_W32TimeQueryProviderStatus(Binding, a2, a3, hMem);
    RpcBindingFree(&Binding);
LABEL_17:
    if ( !ProviderStatus && hMem[0] )
    {
      if ( a4 == *(_DWORD *)hMem[0] && a4 <= 1 )
      {
        v10 = hMem[0];
        *a5 = (void *)*((_QWORD *)hMem[0] + 1);
        v10[1] = 0;
      }
      else
      {
        ProviderStatus = 1804;
      }
    }
  }
  if ( hMem[0] )
  {
    v11 = (void *)*((_QWORD *)hMem[0] + 1);
    if ( v11 )
      LocalFree(v11);
    LocalFree(hMem[0]);
  }
  return ProviderStatus;
}

```

## disassembly

```asm
0x1800500a0  mov     rax, rsp
0x1800500a3  mov     [rax+20h], r9d
0x1800500a7  mov     [rax+18h], r8
0x1800500ab  mov     [rax+10h], edx
0x1800500ae  mov     [rax+8], rcx
0x1800500b2  push    rbx
0x1800500b3  push    rsi
0x1800500b4  push    r14
0x1800500b6  push    r15
0x1800500b8  sub     rsp, 58h
0x1800500bc  mov     r14, r8
0x1800500bf  mov     r15d, edx
0x1800500c2  mov     rsi, rcx
0x1800500c5  mov     qword ptr [rax-40h], 0
0x1800500cd  mov     qword ptr [rax-30h], 0
0x1800500d5  mov     qword ptr [rax-38h], 0
0x1800500dd  cmp     [rsp+78h+arg_20], 0
0x1800500e6  jnz     short loc_1800500F2
0x1800500e8  mov     eax, 80070057h
0x1800500ed  jmp     loc_1800503C5
0x1800500f2  mov     ebx, 6B5h
0x1800500f7  test    rcx, rcx
0x1800500fa  jnz     loc_1800501B9
0x180050100  lea     rax, [rsp+78h+String]
0x180050105  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18005010a  mov     [rsp+78h+Options], rcx; Options
0x18005010f  lea     r9, aW32timeAlt; "W32TIME_ALT"
0x180050116  xor     r8d, r8d; NetworkAddr
0x180050119  lea     rdx, Protseq; "ncalrpc"
0x180050120  call    cs:__imp_RpcStringBindingComposeW
0x180050127  nop     dword ptr [rax+rax+00h]
0x18005012c  mov     ebx, eax
0x18005012e  test    eax, eax
0x180050130  jnz     loc_1800501B9
0x180050136  lea     rdx, [rsp+78h+Binding]; Binding
0x18005013b  mov     rcx, [rsp+78h+String]; StringBinding
0x180050140  call    cs:__imp_RpcBindingFromStringBindingW
0x180050147  nop     dword ptr [rax+rax+00h]
0x18005014c  mov     ebx, eax
0x18005014e  lea     rcx, [rsp+78h+String]; String
0x180050153  call    cs:__imp_RpcStringFreeW
0x18005015a  nop     dword ptr [rax+rax+00h]
0x18005015f  mov     rcx, [rsp+78h+Binding]; Binding
0x180050164  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x180050169  test    ebx, ebx
0x18005016b  jnz     short loc_1800501B9
0x18005016d  lea     r9, [rsp+78h+hMem]
0x180050172  mov     r8, r14
0x180050175  mov     edx, r15d
0x180050178  mov     rcx, [rsp+78h+Binding]
0x18005017d  call    c_W32TimeQueryProviderStatus
0x180050182  mov     ebx, eax
0x180050184  mov     [rsp+78h+var_48], eax
0x180050188  jmp     short loc_1800501A8
0x18005018a  mov     ebx, eax
0x18005018c  mov     [rsp+78h+var_48], eax
0x180050190  mov     r14, [rsp+78h+arg_10]
0x180050198  mov     r15d, [rsp+78h+arg_8]
0x1800501a0  mov     rsi, [rsp+78h+arg_0]
0x1800501a8  lea     rcx, [rsp+78h+Binding]; Binding
0x1800501ad  call    cs:__imp_RpcBindingFree
0x1800501b4  nop     dword ptr [rax+rax+00h]
0x1800501b9  cmp     ebx, 6B5h
0x1800501bf  jz      short loc_1800501CD
0x1800501c1  cmp     ebx, 6BAh
0x1800501c7  jnz     loc_18005028C
0x1800501cd  lea     rax, [rsp+78h+String]
0x1800501d2  mov     [rsp+78h+StringBinding], rax; StringBinding
0x1800501d7  mov     [rsp+78h+Options], 0; Options
0x1800501e0  lea     r9, Endpoint; "\\PIPE\\W32TIME"
0x1800501e7  mov     r8, rsi; NetworkAddr
0x1800501ea  lea     rdx, ProtSeq; "ncacn_np"
0x1800501f1  xor     ecx, ecx; ObjUuid
0x1800501f3  call    cs:__imp_RpcStringBindingComposeW
0x1800501fa  nop     dword ptr [rax+rax+00h]
0x1800501ff  mov     ebx, eax
0x180050201  test    eax, eax
0x180050203  jnz     loc_18005028C
0x180050209  lea     rdx, [rsp+78h+Binding]; Binding
0x18005020e  mov     rcx, [rsp+78h+String]; StringBinding
0x180050213  call    cs:__imp_RpcBindingFromStringBindingW
0x18005021a  nop     dword ptr [rax+rax+00h]
0x18005021f  mov     ebx, eax
0x180050221  lea     rcx, [rsp+78h+String]; String
0x180050226  call    cs:__imp_RpcStringFreeW
0x18005022d  nop     dword ptr [rax+rax+00h]
0x180050232  mov     rcx, [rsp+78h+Binding]; Binding
0x180050237  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x18005023c  test    ebx, ebx
0x18005023e  jnz     short loc_18005028C
0x180050240  lea     r9, [rsp+78h+hMem]
0x180050245  mov     r8, r14
0x180050248  mov     edx, r15d
0x18005024b  mov     rcx, [rsp+78h+Binding]
0x180050250  call    c_W32TimeQueryProviderStatus
0x180050255  mov     ebx, eax
0x180050257  mov     [rsp+78h+var_48], eax
0x18005025b  jmp     short loc_18005027B
0x18005025d  mov     ebx, eax
0x18005025f  mov     [rsp+78h+var_48], eax
0x180050263  mov     r14, [rsp+78h+arg_10]
0x18005026b  mov     r15d, [rsp+78h+arg_8]
0x180050273  mov     rsi, [rsp+78h+arg_0]
0x18005027b  lea     rcx, [rsp+78h+Binding]; Binding
0x180050280  call    cs:__imp_RpcBindingFree
0x180050287  nop     dword ptr [rax+rax+00h]
0x18005028c  cmp     ebx, 6B5h
0x180050292  jz      short loc_1800502A0
0x180050294  cmp     ebx, 6BAh
0x18005029a  jnz     loc_180050347
0x1800502a0  lea     rax, [rsp+78h+String]
0x1800502a5  mov     [rsp+78h+StringBinding], rax; StringBinding
0x1800502aa  mov     [rsp+78h+Options], 0; Options
0x1800502b3  lea     r9, aPipeW32timeAlt; "\\PIPE\\W32TIME_ALT"
0x1800502ba  mov     r8, rsi; NetworkAddr
0x1800502bd  lea     rdx, ProtSeq; "ncacn_np"
0x1800502c4  xor     ecx, ecx; ObjUuid
0x1800502c6  call    cs:__imp_RpcStringBindingComposeW
0x1800502cd  nop     dword ptr [rax+rax+00h]
0x1800502d2  mov     ebx, eax
0x1800502d4  test    eax, eax
0x1800502d6  jnz     short loc_180050347
0x1800502d8  lea     rdx, [rsp+78h+Binding]; Binding
0x1800502dd  mov     rcx, [rsp+78h+String]; StringBinding
0x1800502e2  call    cs:__imp_RpcBindingFromStringBindingW
0x1800502e9  nop     dword ptr [rax+rax+00h]
0x1800502ee  mov     ebx, eax
0x1800502f0  lea     rcx, [rsp+78h+String]; String
0x1800502f5  call    cs:__imp_RpcStringFreeW
0x1800502fc  nop     dword ptr [rax+rax+00h]
0x180050301  mov     rcx, [rsp+78h+Binding]; Binding
0x180050306  call    ?SetMyRpcSecurity@@YAJPEAX@Z; SetMyRpcSecurity(void *)
0x18005030b  test    ebx, ebx
0x18005030d  jnz     loc_180050393
0x180050313  lea     r9, [rsp+78h+hMem]
0x180050318  mov     r8, r14
0x18005031b  mov     edx, r15d
0x18005031e  mov     rcx, [rsp+78h+Binding]
0x180050323  call    c_W32TimeQueryProviderStatus
0x180050328  mov     ebx, eax
0x18005032a  mov     [rsp+78h+var_48], eax
0x18005032e  jmp     short loc_180050336
0x180050330  mov     ebx, eax
0x180050332  mov     [rsp+78h+var_48], eax
0x180050336  lea     rcx, [rsp+78h+Binding]; Binding
0x18005033b  call    cs:__imp_RpcBindingFree
0x180050342  nop     dword ptr [rax+rax+00h]
0x180050347  test    ebx, ebx
0x180050349  jnz     short loc_180050393
0x18005034b  mov     rax, [rsp+78h+hMem]
0x180050350  test    rax, rax
0x180050353  jz      short loc_180050393
0x180050355  mov     eax, [rax]
0x180050357  cmp     [rsp+78h+arg_18], eax
0x18005035e  jz      short loc_180050367
0x180050360  mov     ebx, 70Ch
0x180050365  jmp     short loc_180050393
0x180050367  mov     eax, [rsp+78h+arg_18]
0x18005036e  test    eax, eax
0x180050370  jz      short loc_180050377
0x180050372  cmp     eax, 1
0x180050375  jnz     short loc_180050360
0x180050377  mov     rdx, [rsp+78h+hMem]
0x18005037c  mov     rax, [rsp+78h+arg_20]
0x180050384  mov     rcx, [rdx+8]
0x180050388  mov     [rax], rcx
0x18005038b  mov     qword ptr [rdx+8], 0
0x180050393  mov     rax, [rsp+78h+hMem]
0x180050398  test    rax, rax
0x18005039b  jz      short loc_1800503C3
0x18005039d  mov     rcx, [rax+8]; hMem
0x1800503a1  test    rcx, rcx
0x1800503a4  jz      short loc_1800503B2
0x1800503a6  call    cs:__imp_LocalFree
0x1800503ad  nop     dword ptr [rax+rax+00h]
0x1800503b2  mov     rcx, [rsp+78h+hMem]; hMem
0x1800503b7  call    cs:__imp_LocalFree
0x1800503be  nop     dword ptr [rax+rax+00h]
0x1800503c3  mov     eax, ebx
0x1800503c5  add     rsp, 58h
0x1800503c9  pop     r15
0x1800503cb  pop     r14
0x1800503cd  pop     rsi
0x1800503ce  pop     rbx
0x1800503cf  retn
```
