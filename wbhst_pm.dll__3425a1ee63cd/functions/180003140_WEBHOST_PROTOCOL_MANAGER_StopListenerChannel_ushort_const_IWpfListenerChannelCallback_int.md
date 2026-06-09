# WEBHOST_PROTOCOL_MANAGER::StopListenerChannel(ushort const *,IWpfListenerChannelCallback *,int)

- ea: `0x180003140`
- end: `0x1800031f2`
- name: `?StopListenerChannel@WEBHOST_PROTOCOL_MANAGER@@UEAAJPEBGPEAVIWpfListenerChannelCallback@@H@Z`
- size: `178`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *this, const unsigned __int16 *, struct IWpfListenerChannelCallback *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003140`
- `0x180005010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800031e1`
- `iisutil!PuDbgPrint` at `0x1800031e1`

## string_xrefs

- `0x1800031d5`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x18000317d`: `Failed the Get Protocol ListenerChannel Id hr = %x \n`
- `0x1800031ca`: `WEBHOST_PROTOCOL_MANAGER::StopListenerChannel`
- `0x1800031b6`: `Failed the StopProcessProtocolListenerChannel call hr = %x \n`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::StopListenerChannel(
        WEBHOST_PROTOCOL_MANAGER *this,
        const unsigned __int16 *a2,
        struct IWpfListenerChannelCallback *a3,
        unsigned int a4)
{
  __int64 v4; // rax
  int v8; // ebx
  const char *v9; // rax
  __int64 v10; // r8
  unsigned int v12; // [rsp+70h] [rbp+18h] BYREF

  v4 = *(_QWORD *)a3;
  v12 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IWpfListenerChannelCallback *, unsigned int *))(v4 + 40))(a3, &v12);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 7) + 32LL))(
           *((_QWORD *)this + 7),
           a2,
           v12,
           a4);
    if ( v8 < 0 && (g_dwDebugFlags & 3) != 0 )
    {
      v9 = "Failed the StopProcessProtocolListenerChannel call hr = %x \r\n";
      v10 = 841;
      goto LABEL_7;
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v9 = "Failed the Get Protocol ListenerChannel Id hr = %x \r\n";
    v10 = 821;
LABEL_7:
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
      v10,
      "WEBHOST_PROTOCOL_MANAGER::StopListenerChannel",
      v9);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003140  push    rbx
0x180003142  push    rbp
0x180003143  push    rsi
0x180003144  push    rdi
0x180003145  sub     rsp, 38h
0x180003149  mov     rax, [r8]
0x18000314c  mov     rsi, rdx
0x18000314f  mov     rbp, rcx
0x180003152  mov     [rsp+58h+arg_10], 0
0x18000315a  lea     rdx, [rsp+58h+arg_10]
0x18000315f  mov     rcx, r8
0x180003162  mov     edi, r9d
0x180003165  mov     rax, [rax+28h]
0x180003169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316e  mov     ebx, eax
0x180003170  test    eax, eax
0x180003172  jns     short loc_18000318C
0x180003174  test    cs:g_dwDebugFlags, 3
0x18000317b  jz      short loc_1800031E7
0x18000317d  lea     rax, aFailedTheGetPr; "Failed the Get Protocol ListenerChannel"...
0x180003184  mov     r8d, 335h
0x18000318a  jmp     short loc_1800031C3
0x18000318c  mov     rcx, [rbp+38h]
0x180003190  mov     r9d, edi
0x180003193  mov     r8d, [rsp+58h+arg_10]
0x180003198  mov     rdx, rsi
0x18000319b  mov     rax, [rcx]
0x18000319e  mov     rax, [rax+20h]
0x1800031a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a7  mov     ebx, eax
0x1800031a9  test    eax, eax
0x1800031ab  jns     short loc_1800031E7
0x1800031ad  test    cs:g_dwDebugFlags, 3
0x1800031b4  jz      short loc_1800031E7
0x1800031b6  lea     rax, aFailedTheStopp; "Failed the StopProcessProtocolListenerC"...
0x1800031bd  mov     r8d, 349h
0x1800031c3  mov     rcx, cs:g_pDebug
0x1800031ca  lea     r9, aWebhostProtoco_0; "WEBHOST_PROTOCOL_MANAGER::StopListenerC"...
0x1800031d1  mov     [rsp+58h+var_30], ebx
0x1800031d5  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800031dc  mov     [rsp+58h+var_38], rax
0x1800031e1  call    cs:__imp_PuDbgPrint
0x1800031e7  mov     eax, ebx
0x1800031e9  add     rsp, 38h
0x1800031ed  pop     rdi
0x1800031ee  pop     rsi
0x1800031ef  pop     rbp
0x1800031f0  pop     rbx
0x1800031f1  retn
```
