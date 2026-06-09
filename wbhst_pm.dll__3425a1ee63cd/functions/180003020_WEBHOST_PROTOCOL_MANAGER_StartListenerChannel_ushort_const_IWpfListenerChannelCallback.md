# WEBHOST_PROTOCOL_MANAGER::StartListenerChannel(ushort const *,IWpfListenerChannelCallback *)

- ea: `0x180003020`
- end: `0x180003131`
- name: `?StartListenerChannel@WEBHOST_PROTOCOL_MANAGER@@UEAAJPEBGPEAVIWpfListenerChannelCallback@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this, const unsigned __int16 *, struct IWpfListenerChannelCallback *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180003020`
- `0x180005010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800030d0`
- `iisutil!PuDbgPrint` at `0x180003120`
- `iisutil!PuDbgPrint` at `0x1800030d0`
- `iisutil!PuDbgPrint` at `0x180003120`

## string_xrefs

- `0x1800030b7`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x180003119`: `servercommon\inetsrv\iis\iisrearc\core\webhost_pm\webhost_protocol_manager.cxx`
- `0x1800030ac`: `WEBHOST_PROTOCOL_MANAGER::StartListenerChannel`
- `0x180003107`: `WEBHOST_PROTOCOL_MANAGER::StartListenerChannel`
- `0x1800030be`: `Failed the StartProcessProtocolListenerChannel call hr = %x \n`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::StartListenerChannel(
        WEBHOST_PROTOCOL_MANAGER *this,
        const unsigned __int16 *a2,
        struct IWpfListenerChannelCallback *a3)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  int v8; // edi

  v6 = operator new(0x20u);
  v7 = v6;
  if ( v6 )
  {
    v6[5] = 1;
    *(_QWORD *)v6 = &PMH_LISTENER_CHANNEL_CALLBACK::`vftable';
    v6[2] = 0;
    v6[3] = 0;
    *((_QWORD *)v6 + 3) = a3;
    (**(void (__fastcall ***)(struct IWpfListenerChannelCallback *))a3)(a3);
    v7[4] = 1129072720;
    v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _DWORD *))(**((_QWORD **)this + 7) + 24LL))(
           *((_QWORD *)this + 7),
           a2,
           v7);
    if ( v8 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
        763,
        "WEBHOST_PROTOCOL_MANAGER::StartListenerChannel",
        "Failed the StartProcessProtocolListenerChannel call hr = %x \r\n");
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  else
  {
    v8 = -2147024882;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\webhost_pm\\webhost_protocol_manager.cxx",
        733,
        "WEBHOST_PROTOCOL_MANAGER::StartListenerChannel",
        "Out of memory creating a listenerChannel host hr = %x \r\n");
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003020  push    rbx
0x180003022  push    rbp
0x180003023  push    rsi
0x180003024  push    rdi
0x180003025  sub     rsp, 38h
0x180003029  mov     rbp, rcx
0x18000302c  mov     rdi, r8
0x18000302f  mov     ecx, 20h ; ' '; Size
0x180003034  mov     rsi, rdx
0x180003037  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000303c  mov     rbx, rax
0x18000303f  test    rax, rax
0x180003042  jz      loc_1800030E7
0x180003048  lea     rax, ??_7PMH_LISTENER_CHANNEL_CALLBACK@@6B@; const PMH_LISTENER_CHANNEL_CALLBACK::`vftable'
0x18000304f  mov     dword ptr [rbx+14h], 1
0x180003056  mov     [rbx], rax
0x180003059  mov     dword ptr [rbx+8], 0
0x180003060  mov     dword ptr [rbx+0Ch], 0
0x180003067  mov     [rbx+18h], rdi
0x18000306b  mov     rcx, [rdi]
0x18000306e  mov     rax, [rcx]
0x180003071  mov     rcx, rdi
0x180003074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003079  mov     dword ptr [rbx+10h], 434C4850h
0x180003080  mov     r8, rbx
0x180003083  mov     rcx, [rbp+38h]
0x180003087  mov     rdx, rsi
0x18000308a  mov     rax, [rcx]
0x18000308d  mov     rax, [rax+18h]
0x180003091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003096  mov     edi, eax
0x180003098  test    eax, eax
0x18000309a  jns     short loc_1800030D6
0x18000309c  test    cs:g_dwDebugFlags, 3
0x1800030a3  jz      short loc_1800030D6
0x1800030a5  mov     rcx, cs:g_pDebug
0x1800030ac  lea     r9, aWebhostProtoco_3; "WEBHOST_PROTOCOL_MANAGER::StartListener"...
0x1800030b3  mov     [rsp+58h+var_30], eax
0x1800030b7  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800030be  lea     rax, aFailedTheStart; "Failed the StartProcessProtocolListener"...
0x1800030c5  mov     r8d, 2FBh
0x1800030cb  mov     [rsp+58h+var_38], rax
0x1800030d0  call    cs:__imp_PuDbgPrint
0x1800030d6  mov     rax, [rbx]
0x1800030d9  mov     rcx, rbx
0x1800030dc  mov     rax, [rax+10h]
0x1800030e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e5  jmp     short loc_180003126
0x1800030e7  test    cs:g_dwDebugFlags, 3
0x1800030ee  mov     edi, 8007000Eh
0x1800030f3  jz      short loc_180003126
0x1800030f5  mov     rcx, cs:g_pDebug
0x1800030fc  lea     rax, aOutOfMemoryCre; "Out of memory creating a listenerChanne"...
0x180003103  mov     [rsp+58h+var_30], edi
0x180003107  lea     r9, aWebhostProtoco_3; "WEBHOST_PROTOCOL_MANAGER::StartListener"...
0x18000310e  mov     r8d, 2DDh
0x180003114  mov     [rsp+58h+var_38], rax
0x180003119  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003120  call    cs:__imp_PuDbgPrint
0x180003126  mov     eax, edi
0x180003128  add     rsp, 38h
0x18000312c  pop     rdi
0x18000312d  pop     rsi
0x18000312e  pop     rbp
0x18000312f  pop     rbx
0x180003130  retn
```
