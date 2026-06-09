# CWshEnvProcess::Remove(ushort *)

- ea: `0x18000b840`
- end: `0x18000b890`
- name: `?Remove@CWshEnvProcess@@UEAAJPEAG@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWshEnvProcess *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180005d20`
- `0x18000b840`
- `0x180011010`

## string_xrefs

- `0x18000b86a`: `WshEnvironment.Remove`

## pseudocode

```c
__int64 __fastcall CWshEnvProcess::Remove(CWshEnvProcess *this, unsigned __int16 *a2)
{
  int v3; // eax
  int v4; // ebx

  v3 = (*(__int64 (__fastcall **)(CWshEnvProcess *, unsigned __int16 *, _QWORD))(*(_QWORD *)this + 64LL))(this, a2, 0);
  v4 = 0;
  if ( v3 < 0 )
    v4 = v3;
  if ( v4 < 0 )
    Signal_Exception(&IID_IWshEnvironment, L"WshEnvironment.Remove", 0x100Cu, a2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b840  mov     [rsp+arg_0], rbx
0x18000b845  push    rdi
0x18000b846  sub     rsp, 20h
0x18000b84a  mov     rax, [rcx]
0x18000b84d  xor     r8d, r8d
0x18000b850  mov     rdi, rdx
0x18000b853  mov     rax, [rax+40h]
0x18000b857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b85c  xor     ebx, ebx
0x18000b85e  test    eax, eax
0x18000b860  cmovs   ebx, eax
0x18000b863  test    ebx, ebx
0x18000b865  jns     short loc_18000B883
0x18000b867  mov     r9, rdi
0x18000b86a  lea     rdx, aWshenvironment; "WshEnvironment.Remove"
0x18000b871  mov     r8d, 100Ch; unsigned int
0x18000b877  lea     rcx, IID_IWshEnvironment; struct _GUID *
0x18000b87e  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x18000b883  mov     eax, ebx
0x18000b885  mov     rbx, [rsp+28h+arg_0]
0x18000b88a  add     rsp, 20h
0x18000b88e  pop     rdi
0x18000b88f  retn
```
