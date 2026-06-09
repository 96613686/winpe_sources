# CWinTaskHandler::QueryInterface(_GUID const &,void * *)

- ea: `0x180003870`
- end: `0x1800038dc`
- name: `?QueryInterface@CWinTaskHandler@@MEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(CWinTaskHandler *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003870`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::QueryInterface(CWinTaskHandler *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( !a3 )
    return 2147942487LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ITaskHandler.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ITaskHandler.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ITaskHandler.Data4;
  if ( !v4 )
    goto LABEL_10;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v5 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_10:
    *a3 = this;
    (*(void (__fastcall **)(CWinTaskHandler *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x180003870  sub     rsp, 28h
0x180003874  test    r8, r8
0x180003877  jnz     short loc_180003880
0x180003879  mov     eax, 80070057h
0x18000387e  jmp     short loc_1800038D7
0x180003880  mov     rax, [rdx]
0x180003883  sub     rax, qword ptr cs:IID_ITaskHandler.Data1
0x18000388a  jnz     short loc_180003897
0x18000388c  mov     rax, [rdx+8]
0x180003890  sub     rax, qword ptr cs:IID_ITaskHandler.Data4
0x180003897  test    rax, rax
0x18000389a  jz      short loc_1800038C6
0x18000389c  mov     rax, [rdx]
0x18000389f  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800038a6  jnz     short loc_1800038B3
0x1800038a8  mov     rax, [rdx+8]
0x1800038ac  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800038b3  test    rax, rax
0x1800038b6  jz      short loc_1800038C6
0x1800038b8  mov     qword ptr [r8], 0
0x1800038bf  mov     eax, 80004002h
0x1800038c4  jmp     short loc_1800038D7
0x1800038c6  mov     [r8], rcx
0x1800038c9  mov     rax, [rcx]
0x1800038cc  mov     rax, [rax+8]
0x1800038d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d5  xor     eax, eax
0x1800038d7  add     rsp, 28h
0x1800038db  retn
```
