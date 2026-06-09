# DoRpcInitialize(void)

- ea: `0x1800036fc`
- end: `0x18000385f`
- name: `?DoRpcInitialize@@YAPEAXXZ`
- size: `355`
- prototype: `RPC_BINDING_HANDLE(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800044c0`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x1800036fc`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x180003736`
- `RPCRT4!RpcStringBindingComposeW` at `0x180003736`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180003752`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180003752`
- `RPCRT4!RpcStringFreeW` at `0x18000375e`
- `RPCRT4!RpcStringFreeW` at `0x18000375e`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180003787`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180003787`

## pseudocode

```c
RPC_BINDING_HANDLE DoRpcInitialize(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  unsigned int v2; // ebx
  _BYTE pExceptionObject[64]; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+80h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+88h] [rbp+18h] BYREF

  String = 0;
  v0 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"wecsvc", 0, &String);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, v0);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      v1,
      "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
      31);
    throw (wmi::GenericException *)pExceptionObject;
  }
  Binding = 0;
  v2 = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids, v2);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      v2,
      "admin\\wmi\\events\\forwarding\\collector\\api\\evcoll.cpp",
      41);
    throw (wmi::GenericException *)pExceptionObject;
  }
  RpcBindingSetAuthInfoW(Binding, 0, 6u, 0xAu, 0, 0);
  return Binding;
}

```

## disassembly

```asm
0x1800036fc  mov     [rsp-8+arg_10], rbx
0x180003701  push    rbp
0x180003702  mov     rbp, rsp
0x180003705  sub     rsp, 70h
0x180003709  lea     rax, [rbp+String]
0x18000370d  mov     [rbp+String], 0
0x180003715  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18000371a  lea     r9, ServiceName; "wecsvc"
0x180003721  xor     r8d, r8d; NetworkAddr
0x180003724  mov     [rsp+70h+Options], 0; Options
0x18000372d  lea     rdx, ProtSeq; "ncalrpc"
0x180003734  xor     ecx, ecx; ObjUuid
0x180003736  call    cs:__imp_RpcStringBindingComposeW
0x18000373c  mov     ebx, eax
0x18000373e  test    eax, eax
0x180003740  jnz     short loc_18000379F
0x180003742  mov     rcx, [rbp+String]; StringBinding
0x180003746  lea     rdx, [rbp+Binding]; Binding
0x18000374a  mov     [rbp+Binding], 0
0x180003752  call    cs:__imp_RpcBindingFromStringBindingW
0x180003758  lea     rcx, [rbp+String]; String
0x18000375c  mov     ebx, eax
0x18000375e  call    cs:__imp_RpcStringFreeW
0x180003764  test    ebx, ebx
0x180003766  jnz     loc_1800037FF
0x18000376c  mov     rcx, [rbp+Binding]; Binding
0x180003770  lea     r9d, [rbx+0Ah]; AuthnSvc
0x180003774  mov     dword ptr [rsp+70h+StringBinding], ebx; AuthzSvc
0x180003778  lea     r8d, [rbx+6]; AuthnLevel
0x18000377c  xor     edx, edx; ServerPrincName
0x18000377e  mov     [rsp+70h+Options], 0; AuthIdentity
0x180003787  call    cs:__imp_RpcBindingSetAuthInfoW
0x18000378d  mov     rax, [rbp+Binding]
0x180003791  mov     rbx, [rsp+70h+arg_10]
0x180003799  add     rsp, 70h
0x18000379d  pop     rbp
0x18000379e  retn
0x18000379f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037a6  lea     rdx, WPP_GLOBAL_Control
0x1800037ad  cmp     rcx, rdx
0x1800037b0  jz      short loc_1800037D6
0x1800037b2  test    byte ptr [rcx+1Ch], 1
0x1800037b6  jz      short loc_1800037D6
0x1800037b8  cmp     byte ptr [rcx+19h], 2
0x1800037bc  jb      short loc_1800037D6
0x1800037be  mov     rcx, [rcx+10h]
0x1800037c2  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x1800037c9  mov     edx, 0Ah
0x1800037ce  mov     r9d, ebx
0x1800037d1  call    WPP_SF_D
0x1800037d6  mov     r9d, 1Fh; int
0x1800037dc  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x1800037e3  mov     edx, ebx; unsigned int
0x1800037e5  lea     rcx, [rbp+pExceptionObject]; this
0x1800037e9  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x1800037ee  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800037f5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800037f9  call    _CxxThrowException_0
0x1800037ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180003806  lea     rdx, WPP_GLOBAL_Control
0x18000380d  cmp     rcx, rdx
0x180003810  jz      short loc_180003836
0x180003812  test    byte ptr [rcx+1Ch], 1
0x180003816  jz      short loc_180003836
0x180003818  cmp     byte ptr [rcx+19h], 2
0x18000381c  jb      short loc_180003836
0x18000381e  mov     rcx, [rcx+10h]
0x180003822  lea     r8, WPP_ad46ba0b25a435688d5858c8a9a9bb6f_Traceguids
0x180003829  mov     edx, 0Bh
0x18000382e  mov     r9d, ebx
0x180003831  call    WPP_SF_D
0x180003836  mov     r9d, 29h ; ')'; int
0x18000383c  lea     r8, aAdminWmiEvents_1; "admin\\wmi\\events\\forwarding\\collect"...
0x180003843  mov     edx, ebx; unsigned int
0x180003845  lea     rcx, [rbp+pExceptionObject]; this
0x180003849  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000384e  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180003855  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003859  call    _CxxThrowException_0
```
