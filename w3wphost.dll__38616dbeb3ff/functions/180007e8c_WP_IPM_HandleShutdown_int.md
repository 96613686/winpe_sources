# WP_IPM::HandleShutdown(int)

- ea: `0x180007e8c`
- end: `0x180007f60`
- name: `?HandleShutdown@WP_IPM@@AEAAJH@Z`
- size: `212`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001180`
- `0x180008360`

## callees

- `0x180007e8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007f46`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007f46`
- `iisutil!PuDbgPrint` at `0x180007eda`
- `iisutil!PuDbgPrint` at `0x180007f31`
- `iisutil!PuDbgPrint` at `0x180007eda`
- `iisutil!PuDbgPrint` at `0x180007f31`

## string_xrefs

- `0x180007ed3`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`
- `0x180007f2a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x180007e8c  mov     [rsp+arg_0], rbx
0x180007e91  push    rdi
0x180007e92  sub     rsp, 30h
0x180007e96  mov     eax, cs:g_dwDebugFlags
0x180007e9c  mov     edi, edx
0x180007e9e  test    al, 3
0x180007ea0  mov     rbx, rcx
0x180007ea3  setnz   r8b
0x180007ea7  bt      eax, 13h
0x180007eab  setb    al
0x180007eae  test    al, r8b
0x180007eb1  jz      short loc_180007EE6
0x180007eb3  mov     rcx, cs:g_pDebug
0x180007eba  lea     rax, aHandleShutdown_0; "Handle ******************** Shutdown\n"...
0x180007ec1  lea     r9, aWpIpmHandleshu; "WP_IPM::HandleShutdown"
0x180007ec8  mov     [rsp+38h+var_18], rax
0x180007ecd  mov     r8d, 409h
0x180007ed3  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007eda  call    cs:__imp_PuDbgPrint
0x180007ee1  nop     dword ptr [rax+rax+00h]
0x180007ee6  mov     ecx, 1
0x180007eeb  xor     eax, eax
0x180007eed  lock cmpxchg [rbx+24h], ecx
0x180007ef2  jz      short loc_180007F3F
0x180007ef4  mov     eax, cs:g_dwDebugFlags
0x180007efa  test    al, 3
0x180007efc  setnz   cl
0x180007eff  bt      eax, 13h
0x180007f03  setb    al
0x180007f06  test    al, cl
0x180007f08  jz      short loc_180007F52
0x180007f0a  mov     rcx, cs:g_pDebug
0x180007f11  lea     rax, aIgnoreAddition; "Ignore additional shutdown request\n\n"
0x180007f18  lea     r9, aWpIpmHandleshu; "WP_IPM::HandleShutdown"
0x180007f1f  mov     [rsp+38h+var_18], rax
0x180007f24  mov     r8d, 412h
0x180007f2a  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007f31  call    cs:__imp_PuDbgPrint
0x180007f38  nop     dword ptr [rax+rax+00h]
0x180007f3d  jmp     short loc_180007F52
0x180007f3f  mov     rcx, [rbx+10h]; hEvent
0x180007f43  mov     [rbx+28h], edi
0x180007f46  call    cs:__imp_SetEvent
0x180007f4d  nop     dword ptr [rax+rax+00h]
0x180007f52  mov     rbx, [rsp+38h+arg_0]
0x180007f57  xor     eax, eax
0x180007f59  add     rsp, 30h
0x180007f5d  pop     rdi
0x180007f5e  retn
```
