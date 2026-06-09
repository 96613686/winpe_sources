# HTTP_LOG_CONTEXT::Reference(void)

- ea: `0x18000e3d0`
- end: `0x18000e3fa`
- name: `?Reference@HTTP_LOG_CONTEXT@@UEAAXXZ`
- size: `42`
- prototype: `void __fastcall(HTTP_LOG_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000e3d0`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000e3ef`
- `iisutil!WriteRefTraceLog` at `0x18000e3ef`

## pseudocode

```c
void __fastcall HTTP_LOG_CONTEXT::Reference(HTTP_LOG_CONTEXT *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( HTTP_LOG_CONTEXT::sm_pTraceLog )
    WriteRefTraceLog(HTTP_LOG_CONTEXT::sm_pTraceLog, *((unsigned int *)this + 2), this);
}

```

## disassembly

```asm
0x18000e3d0  sub     rsp, 28h
0x18000e3d4  lock inc dword ptr [rcx+8]
0x18000e3d8  cmp     cs:?sm_pTraceLog@HTTP_LOG_CONTEXT@@0PEAU_TRACE_LOG@@EA, 0; _TRACE_LOG * HTTP_LOG_CONTEXT::sm_pTraceLog
0x18000e3e0  jz      short loc_18000E3F5
0x18000e3e2  mov     edx, [rcx+8]
0x18000e3e5  mov     r8, rcx
0x18000e3e8  mov     rcx, cs:?sm_pTraceLog@HTTP_LOG_CONTEXT@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * HTTP_LOG_CONTEXT::sm_pTraceLog
0x18000e3ef  call    cs:__imp_WriteRefTraceLog
0x18000e3f5  add     rsp, 28h
0x18000e3f9  retn
```
