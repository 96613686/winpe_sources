# LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)

- ea: `0x18000b708`
- end: `0x18000b830`
- name: `?CreateListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@AEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL_LIST_MANAGER *this, const unsigned __int16 *, unsigned int, struct LISTENER_CHANNEL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b8e8`

## callees

- `0x180002090`
- `0x18000aa04`
- `0x18000b000`
- `0x18000b708`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000b78e`
- `iisutil!PuDbgPrint` at `0x18000b816`
- `iisutil!PuDbgPrint` at `0x18000b78e`
- `iisutil!PuDbgPrint` at `0x18000b816`

## string_xrefs

- `0x18000b775`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel_list_manager.cxx`
- `0x18000b809`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel_list_manager.cxx`
- `0x18000b76a`: `LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel`
- `0x18000b7fb`: `LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel(
        LISTENER_CHANNEL_LIST_MANAGER *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct LISTENER_CHANNEL **a4)
{
  LISTENER_CHANNEL *v8; // rax
  LISTENER_CHANNEL *v9; // rax
  struct LISTENER_CHANNEL *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx

  v8 = (LISTENER_CHANNEL *)operator new(0x140u);
  if ( v8 && (v9 = LISTENER_CHANNEL::LISTENER_CHANNEL(v8), (v10 = v9) != 0) )
  {
    v11 = LISTENER_CHANNEL::InitializeInstance(v9, a2, a3);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v13 = (_QWORD *)((char *)this + 8);
      v14 = *((_QWORD *)this + 1);
      if ( *(LISTENER_CHANNEL_LIST_MANAGER **)(v14 + 8) != (LISTENER_CHANNEL_LIST_MANAGER *)((char *)this + 8) )
        __fastfail(3u);
      *a4 = v10;
      *((_QWORD *)v10 + 31) = v14;
      v12 = 0;
      *((_QWORD *)v10 + 32) = v13;
      *(_QWORD *)(v14 + 8) = (char *)v10 + 248;
      *v13 = (char *)v10 + 248;
    }
    else
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel_list_manager.cxx",
          642,
          "LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel",
          "Failed initializing the ListenerChannelContext hr = %x \r\n",
          v11);
      (*(void (__fastcall **)(struct LISTENER_CHANNEL *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    return v12;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel_list_manager.cxx",
        627,
        "LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel",
        "Out of memory creating a listenerChannel host hr = %x \r\n",
        -2147024882);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000b708  push    rbx
0x18000b70a  push    rbp
0x18000b70b  push    rsi
0x18000b70c  push    rdi
0x18000b70d  push    r14
0x18000b70f  sub     rsp, 30h
0x18000b713  mov     rsi, rcx
0x18000b716  mov     r14, r9
0x18000b719  mov     ecx, 140h; Size
0x18000b71e  mov     edi, r8d
0x18000b721  mov     rbp, rdx
0x18000b724  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b729  test    rax, rax
0x18000b72c  jz      loc_18000B7DD
0x18000b732  mov     rcx, rax; this
0x18000b735  call    ??0LISTENER_CHANNEL@@QEAA@XZ; LISTENER_CHANNEL::LISTENER_CHANNEL(void)
0x18000b73a  mov     rbx, rax
0x18000b73d  test    rax, rax
0x18000b740  jz      loc_18000B7DD
0x18000b746  mov     r8d, edi; unsigned int
0x18000b749  mov     rdx, rbp; unsigned __int16 *
0x18000b74c  mov     rcx, rax; this
0x18000b74f  call    ?InitializeInstance@LISTENER_CHANNEL@@QEAAJPEBGK@Z; LISTENER_CHANNEL::InitializeInstance(ushort const *,ulong)
0x18000b754  mov     edi, eax
0x18000b756  test    eax, eax
0x18000b758  jns     short loc_18000B7AB
0x18000b75a  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b761  jz      short loc_18000B79A
0x18000b763  mov     rcx, cs:g_pDebug
0x18000b76a  lea     r9, aListenerChanne_2; "LISTENER_CHANNEL_LIST_MANAGER::CreateLi"...
0x18000b771  mov     [rsp+58h+var_30], eax
0x18000b775  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b77c  lea     rax, aFailedInitiali; "Failed initializing the ListenerChannel"...
0x18000b783  mov     r8d, 282h
0x18000b789  mov     [rsp+58h+var_38], rax
0x18000b78e  call    cs:__imp_PuDbgPrint
0x18000b795  nop     dword ptr [rax+rax+00h]
0x18000b79a  mov     rax, [rbx]
0x18000b79d  mov     rcx, rbx
0x18000b7a0  mov     rax, [rax+8]
0x18000b7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7a9  jmp     short loc_18000B7D9
0x18000b7ab  lea     rcx, [rsi+8]
0x18000b7af  mov     rdx, [rcx]
0x18000b7b2  cmp     [rdx+8], rcx
0x18000b7b6  jz      short loc_18000B7BF
0x18000b7b8  mov     ecx, 3
0x18000b7bd  int     29h; Win8: RtlFailFast(ecx)
0x18000b7bf  lea     rax, [rbx+0F8h]
0x18000b7c6  mov     [r14], rbx
0x18000b7c9  mov     [rax], rdx
0x18000b7cc  xor     edi, edi
0x18000b7ce  mov     [rax+8], rcx
0x18000b7d2  mov     [rdx+8], rax
0x18000b7d6  mov     [rcx], rax
0x18000b7d9  mov     eax, edi
0x18000b7db  jmp     short loc_18000B824
0x18000b7dd  test    byte ptr cs:g_dwDebugFlags, 3
0x18000b7e4  mov     ebx, 8007000Eh
0x18000b7e9  jz      short loc_18000B822
0x18000b7eb  lea     rcx, aOutOfMemoryCre; "Out of memory creating a listenerChanne"...
0x18000b7f2  mov     [rsp+58h+var_30], ebx
0x18000b7f6  mov     [rsp+58h+var_38], rcx
0x18000b7fb  lea     r9, aListenerChanne_2; "LISTENER_CHANNEL_LIST_MANAGER::CreateLi"...
0x18000b802  mov     rcx, cs:g_pDebug
0x18000b809  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b810  mov     r8d, 273h
0x18000b816  call    cs:__imp_PuDbgPrint
0x18000b81d  nop     dword ptr [rax+rax+00h]
0x18000b822  mov     eax, ebx
0x18000b824  add     rsp, 30h
0x18000b828  pop     r14
0x18000b82a  pop     rdi
0x18000b82b  pop     rsi
0x18000b82c  pop     rbp
0x18000b82d  pop     rbx
0x18000b82e  retn
```
