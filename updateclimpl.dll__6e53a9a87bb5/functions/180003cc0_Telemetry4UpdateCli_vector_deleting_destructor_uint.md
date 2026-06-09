# Telemetry4UpdateCli::`vector deleting destructor'(uint)

- ea: `0x180003cc0`
- end: `0x180003d15`
- name: `??_ETelemetry4UpdateCli@@UEAAPEAXI@Z`
- size: `85`
- prototype: `Telemetry4UpdateCli *__fastcall(Telemetry4UpdateCli *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180003cc0`
- `0x180010334`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003cee`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180003cee`

## pseudocode

```c
Telemetry4UpdateCli *__fastcall Telemetry4UpdateCli::`vector deleting destructor'(Telemetry4UpdateCli *this, char a2)
{
  __int64 v4; // rax
  REGHANDLE v5; // rcx

  *(_QWORD *)this = &wil::TraceLoggingProvider::`vftable';
  if ( *((_BYTE *)this + 16) )
  {
    v4 = *((_QWORD *)this + 1);
    v5 = *(_QWORD *)(v4 + 32);
    *(_QWORD *)(v4 + 32) = 0;
    *(_DWORD *)v4 = 0;
    EventUnregister(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003cc0  mov     [rsp+arg_0], rbx
0x180003cc5  push    rdi
0x180003cc6  sub     rsp, 20h
0x180003cca  mov     edi, edx
0x180003ccc  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x180003cd3  xor     edx, edx
0x180003cd5  mov     [rcx], rax
0x180003cd8  mov     rbx, rcx
0x180003cdb  cmp     [rcx+10h], dl
0x180003cde  jz      short loc_180003CF4
0x180003ce0  mov     rax, [rcx+8]
0x180003ce4  mov     rcx, [rax+20h]; RegHandle
0x180003ce8  mov     [rax+20h], rdx
0x180003cec  mov     [rax], edx
0x180003cee  call    cs:__imp_EventUnregister
0x180003cf4  test    dil, 1
0x180003cf8  jz      short loc_180003D07
0x180003cfa  mov     edx, 20h ; ' '; unsigned __int64
0x180003cff  mov     rcx, rbx; void *
0x180003d02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003d07  mov     rax, rbx
0x180003d0a  mov     rbx, [rsp+28h+arg_0]
0x180003d0f  add     rsp, 20h
0x180003d13  pop     rdi
0x180003d14  retn
```
