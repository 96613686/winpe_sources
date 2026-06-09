# WP_IPM::PipeDisconnected(long)

- ea: `0x180007b50`
- end: `0x180007bec`
- name: `?PipeDisconnected@WP_IPM@@UEAAXJ@Z`
- size: `156`
- prototype: `void __fastcall(WP_IPM *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800076d8`
- `0x180007b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007bc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007bc9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007bcf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007bcf`
- `iisutil!PuDbgPrint` at `0x180007ba2`
- `iisutil!PuDbgPrint` at `0x180007ba2`

## string_xrefs

- `0x180007b9b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

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
0x180007b50  mov     [rsp+arg_0], rbx
0x180007b55  push    rdi
0x180007b56  sub     rsp, 30h
0x180007b5a  mov     edi, edx
0x180007b5c  mov     rbx, rcx
0x180007b5f  test    edx, edx
0x180007b61  jns     short loc_180007BA8
0x180007b63  mov     eax, cs:g_dwDebugFlags
0x180007b69  test    al, 3
0x180007b6b  setnz   r8b
0x180007b6f  bt      eax, 13h
0x180007b73  setb    al
0x180007b76  test    al, r8b
0x180007b79  jz      short loc_180007BA8
0x180007b7b  mov     rcx, cs:g_pDebug
0x180007b82  lea     rax, aFsdf; "FSDF"
0x180007b89  lea     r9, aWpIpmPipedisco; "WP_IPM::PipeDisconnected"
0x180007b90  mov     [rsp+38h+var_18], rax
0x180007b95  mov     r8d, 229h
0x180007b9b  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007ba2  call    cs:__imp_PuDbgPrint
0x180007ba8  cmp     dword ptr [rbx+2Ch], 0
0x180007bac  jnz     short loc_180007BD5
0x180007bae  cmp     edi, 800703E3h
0x180007bb4  jz      short loc_180007BD5
0x180007bb6  cmp     dword ptr [rbx+34h], 0
0x180007bba  jz      short loc_180007BCF
0x180007bbc  xor     r9d, r9d; lpArguments
0x180007bbf  xor     r8d, r8d; nNumberOfArguments
0x180007bc2  xor     edx, edx; dwExceptionFlags
0x180007bc4  mov     ecx, 0C0000005h; dwExceptionCode
0x180007bc9  call    cs:__imp_RaiseException
0x180007bcf  call    cs:__imp_IsDebuggerPresent
0x180007bd5  mov     edx, 1; int
0x180007bda  mov     rcx, rbx; this
0x180007bdd  mov     rbx, [rsp+38h+arg_0]
0x180007be2  add     rsp, 30h
0x180007be6  pop     rdi
0x180007be7  jmp     ?HandleShutdown@WP_IPM@@AEAAJH@Z; WP_IPM::HandleShutdown(int)
```
