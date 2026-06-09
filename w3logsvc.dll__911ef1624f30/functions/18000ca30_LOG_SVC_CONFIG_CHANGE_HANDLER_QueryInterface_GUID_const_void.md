# LOG_SVC_CONFIG_CHANGE_HANDLER::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ca30`
- end: `0x18000ca8b`
- name: `?QueryInterface@LOG_SVC_CONFIG_CHANGE_HANDLER@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(LOG_SVC_CONFIG_CHANGE_HANDLER *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ca30`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall LOG_SVC_CONFIG_CHANGE_HANDLER::QueryInterface(
        LOG_SVC_CONFIG_CHANGE_HANDLER *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAppHostChangeHandler.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAppHostChangeHandler.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(LOG_SVC_CONFIG_CHANGE_HANDLER *))(*(_QWORD *)this + 8LL))(this);
  }
  else
  {
    *a3 = 0;
    return (unsigned int)-2147467262;
  }
  return v3;
}

```

## disassembly

```asm
0x18000ca30  push    rbx
0x18000ca32  sub     rsp, 20h
0x18000ca36  mov     rax, [rdx]
0x18000ca39  xor     ebx, ebx
0x18000ca3b  cmp     rax, qword ptr cs:IID_IAppHostChangeHandler.Data1
0x18000ca42  jnz     short loc_18000CA51
0x18000ca44  mov     rax, [rdx+8]
0x18000ca48  cmp     rax, qword ptr cs:IID_IAppHostChangeHandler.Data4
0x18000ca4f  jz      short loc_18000CA6A
0x18000ca51  mov     rax, [rdx]
0x18000ca54  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000ca5b  jnz     short loc_18000CA7B
0x18000ca5d  mov     rax, [rdx+8]
0x18000ca61  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000ca68  jnz     short loc_18000CA7B
0x18000ca6a  mov     [r8], rcx
0x18000ca6d  mov     rax, [rcx]
0x18000ca70  mov     rax, [rax+8]
0x18000ca74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca79  jmp     short loc_18000CA83
0x18000ca7b  mov     [r8], rbx
0x18000ca7e  mov     ebx, 80004002h
0x18000ca83  mov     eax, ebx
0x18000ca85  add     rsp, 20h
0x18000ca89  pop     rbx
0x18000ca8a  retn
```
