# WP_IPM::PipeDisconnected(long)

- ea: `0x180008360`
- end: `0x18000840e`
- name: `?PipeDisconnected@WP_IPM@@UEAAXJ@Z`
- size: `174`
- prototype: `void __fastcall(WP_IPM *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007e8c`
- `0x180008360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800083df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800083df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083eb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083eb`
- `iisutil!PuDbgPrint` at `0x1800083b2`
- `iisutil!PuDbgPrint` at `0x1800083b2`

## string_xrefs

- `0x1800083ab`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
void __fastcall WP_IPM::PipeDisconnected(WP_IPM *this, int a2)
{
  if ( a2 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      553,
      "WP_IPM::PipeDisconnected",
      "FSDF");
  if ( !*((_DWORD *)this + 11) && a2 != -2147023901 )
  {
    if ( *((_DWORD *)this + 13) )
      RaiseException(0xC0000005, 0, 0, 0);
    IsDebuggerPresent();
  }
  WP_IPM::HandleShutdown(this, 1);
}

```

## disassembly

```asm
0x180008360  mov     [rsp+arg_0], rbx
0x180008365  push    rdi
0x180008366  sub     rsp, 30h
0x18000836a  mov     edi, edx
0x18000836c  mov     rbx, rcx
0x18000836f  test    edx, edx
0x180008371  jns     short loc_1800083BE
0x180008373  mov     eax, cs:g_dwDebugFlags
0x180008379  test    al, 3
0x18000837b  setnz   r8b
0x18000837f  bt      eax, 13h
0x180008383  setb    al
0x180008386  test    al, r8b
0x180008389  jz      short loc_1800083BE
0x18000838b  mov     rcx, cs:g_pDebug
0x180008392  lea     rax, aFsdf; "FSDF"
0x180008399  lea     r9, aWpIpmPipedisco; "WP_IPM::PipeDisconnected"
0x1800083a0  mov     [rsp+38h+var_18], rax
0x1800083a5  mov     r8d, 229h
0x1800083ab  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800083b2  call    cs:__imp_PuDbgPrint
0x1800083b9  nop     dword ptr [rax+rax+00h]
0x1800083be  cmp     dword ptr [rbx+2Ch], 0
0x1800083c2  jnz     short loc_1800083F7
0x1800083c4  cmp     edi, 800703E3h
0x1800083ca  jz      short loc_1800083F7
0x1800083cc  cmp     dword ptr [rbx+34h], 0
0x1800083d0  jz      short loc_1800083EB
0x1800083d2  xor     r9d, r9d; lpArguments
0x1800083d5  xor     r8d, r8d; nNumberOfArguments
0x1800083d8  xor     edx, edx; dwExceptionFlags
0x1800083da  mov     ecx, 0C0000005h; dwExceptionCode
0x1800083df  call    cs:__imp_RaiseException
0x1800083e6  nop     dword ptr [rax+rax+00h]
0x1800083eb  call    cs:__imp_IsDebuggerPresent
0x1800083f2  nop     dword ptr [rax+rax+00h]
0x1800083f7  mov     edx, 1; int
0x1800083fc  mov     rcx, rbx; this
0x1800083ff  mov     rbx, [rsp+38h+arg_0]
0x180008404  add     rsp, 30h
0x180008408  pop     rdi
0x180008409  jmp     ?HandleShutdown@WP_IPM@@AEAAJH@Z; WP_IPM::HandleShutdown(int)
```
