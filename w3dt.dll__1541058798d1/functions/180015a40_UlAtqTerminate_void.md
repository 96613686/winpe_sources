# UlAtqTerminate(void)

- ea: `0x180015a40`
- end: `0x180015aa9`
- name: `?UlAtqTerminate@@YAXXZ`
- size: `105`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180014588`
- `0x1800153c8`
- `0x180015434`
- `0x180015a40`
- `0x180015bc0`

## import_xrefs

- `HTTPAPI!HttpTerminate` at `0x180015a89`
- `HTTPAPI!HttpTerminate` at `0x180015a89`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180015a96`
- `iisutil!PuDeleteDebugPrintsObject` at `0x180015a96`

## pseudocode

```c
void UlAtqTerminate(void)
{
  WP_CONTEXT *v0; // rbx
  unsigned int v1; // edx

  v0 = g_pwpContext;
  if ( g_pwpContext )
  {
    UL_DISCONNECT_CONTEXT::Terminate();
    UL_NATIVE_REQUEST::Terminate();
    UL_CONTROL_CHANNEL::Cleanup((WP_CONTEXT *)((char *)v0 + 784));
    if ( g_pwpContext )
      WP_CONTEXT::`scalar deleting destructor'(g_pwpContext, v1);
    g_pwpContext = 0;
  }
  HttpTerminate(1u, 0);
  g_pDebug = PuDeleteDebugPrintsObject(g_pDebug);
}

```

## disassembly

```asm
0x180015a40  push    rbx
0x180015a42  sub     rsp, 20h
0x180015a46  mov     rbx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x180015a4d  test    rbx, rbx
0x180015a50  jz      short loc_180015A84
0x180015a52  call    ?Terminate@UL_DISCONNECT_CONTEXT@@SAXXZ; UL_DISCONNECT_CONTEXT::Terminate(void)
0x180015a57  call    ?Terminate@UL_NATIVE_REQUEST@@SAXXZ; UL_NATIVE_REQUEST::Terminate(void)
0x180015a5c  lea     rcx, [rbx+310h]; this
0x180015a63  call    ?Cleanup@UL_CONTROL_CHANNEL@@QEAAKXZ; UL_CONTROL_CHANNEL::Cleanup(void)
0x180015a68  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; this
0x180015a6f  test    rcx, rcx
0x180015a72  jz      short loc_180015A79
0x180015a74  call    ??_GWP_CONTEXT@@QEAAPEAXI@Z; WP_CONTEXT::`scalar deleting destructor'(uint)
0x180015a79  mov     cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA, 0; WP_CONTEXT * g_pwpContext
0x180015a84  xor     edx, edx; pReserved
0x180015a86  lea     ecx, [rdx+1]; Flags
0x180015a89  call    cs:__imp_HttpTerminate
0x180015a8f  mov     rcx, cs:g_pDebug
0x180015a96  call    cs:__imp_PuDeleteDebugPrintsObject
0x180015a9c  mov     cs:g_pDebug, rax
0x180015aa3  add     rsp, 20h
0x180015aa7  pop     rbx
0x180015aa8  retn
```
