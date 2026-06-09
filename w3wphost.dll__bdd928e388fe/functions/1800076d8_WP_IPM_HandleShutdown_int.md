# WP_IPM::HandleShutdown(int)

- ea: `0x1800076d8`
- end: `0x180007799`
- name: `?HandleShutdown@WP_IPM@@AEAAJH@Z`
- size: `193`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001170`
- `0x180007b50`

## callees

- `0x1800076d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007786`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007786`
- `iisutil!PuDbgPrint` at `0x180007726`
- `iisutil!PuDbgPrint` at `0x180007777`
- `iisutil!PuDbgPrint` at `0x180007726`
- `iisutil!PuDbgPrint` at `0x180007777`

## string_xrefs

- `0x18000771f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180007770`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleShutdown(WP_IPM *this, int a2)
{
  void *v4; // rcx

  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      1033,
      "WP_IPM::HandleShutdown",
      "Handle ******************** Shutdown\n\n");
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 0) )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
        1042,
        "WP_IPM::HandleShutdown",
        "Ignore additional shutdown request\n\n");
  }
  else
  {
    v4 = (void *)*((_QWORD *)this + 2);
    *((_DWORD *)this + 10) = a2;
    SetEvent(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800076d8  mov     [rsp+arg_0], rbx
0x1800076dd  push    rdi
0x1800076de  sub     rsp, 30h
0x1800076e2  mov     eax, cs:g_dwDebugFlags
0x1800076e8  mov     edi, edx
0x1800076ea  test    al, 3
0x1800076ec  mov     rbx, rcx
0x1800076ef  setnz   r8b
0x1800076f3  bt      eax, 13h
0x1800076f7  setb    al
0x1800076fa  test    al, r8b
0x1800076fd  jz      short loc_18000772C
0x1800076ff  mov     rcx, cs:g_pDebug
0x180007706  lea     rax, aHandleShutdown_0; "Handle ******************** Shutdown\n"...
0x18000770d  lea     r9, aWpIpmHandleshu; "WP_IPM::HandleShutdown"
0x180007714  mov     [rsp+38h+var_18], rax
0x180007719  mov     r8d, 409h
0x18000771f  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007726  call    cs:__imp_PuDbgPrint
0x18000772c  mov     ecx, 1
0x180007731  xor     eax, eax
0x180007733  lock cmpxchg [rbx+24h], ecx
0x180007738  jz      short loc_18000777F
0x18000773a  mov     eax, cs:g_dwDebugFlags
0x180007740  test    al, 3
0x180007742  setnz   cl
0x180007745  bt      eax, 13h
0x180007749  setb    al
0x18000774c  test    al, cl
0x18000774e  jz      short loc_18000778C
0x180007750  mov     rcx, cs:g_pDebug
0x180007757  lea     rax, aIgnoreAddition; "Ignore additional shutdown request\n\n"
0x18000775e  lea     r9, aWpIpmHandleshu; "WP_IPM::HandleShutdown"
0x180007765  mov     [rsp+38h+var_18], rax
0x18000776a  mov     r8d, 412h
0x180007770  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007777  call    cs:__imp_PuDbgPrint
0x18000777d  jmp     short loc_18000778C
0x18000777f  mov     rcx, [rbx+10h]; hEvent
0x180007783  mov     [rbx+28h], edi
0x180007786  call    cs:__imp_SetEvent
0x18000778c  mov     rbx, [rsp+38h+arg_0]
0x180007791  xor     eax, eax
0x180007793  add     rsp, 30h
0x180007797  pop     rdi
0x180007798  retn
```
