# WofFindOrCreateHandleContext

- ea: `0x140032cd8`
- end: `0x140032dd5`
- name: `WofFindOrCreateHandleContext`
- size: `253`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140023ec4`
- `0x140032bb0`
- `0x1400338e0`

## callees

- `0x1400119c0`
- `0x140032cd8`

## import_xrefs

- `FLTMGR!FltSetStreamHandleContext` at `0x140032d86`
- `FLTMGR!FltSetStreamHandleContext` at `0x140032d86`
- `FLTMGR!FltReleaseContext` at `0x140032d9d`
- `FLTMGR!FltReleaseContext` at `0x140032d9d`
- `FLTMGR!FltAllocateContext` at `0x140032d24`
- `FLTMGR!FltAllocateContext` at `0x140032d24`

## pseudocode

```c
NTSTATUS __fastcall WofFindOrCreateHandleContext(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        _QWORD *a4)
{
  NTSTATUS result; // eax
  _QWORD *v8; // rax
  NTSTATUS v9; // ebx
  PFLT_CONTEXT v10; // rax
  PFLT_CONTEXT NewContext; // [rsp+30h] [rbp-18h] BYREF
  PFLT_CONTEXT OldContext; // [rsp+38h] [rbp-10h] BYREF

  NewContext = 0;
  OldContext = 0;
  result = FltAllocateContext(WofGlobal, 0x10u, (unsigned int)dword_140018444 + 56LL, PagedPool, &NewContext);
  if ( result >= 0 )
  {
    memset(NewContext, 0, (unsigned int)dword_140018444 + 56LL);
    v8 = (char *)NewContext + 24;
    *((_QWORD *)NewContext + 4) = (char *)NewContext + 24;
    *v8 = v8;
    *((_DWORD *)NewContext + 1) = -1;
    v9 = FltSetStreamHandleContext(Instance, FileObject, FLT_SET_CONTEXT_KEEP_IF_EXISTS, NewContext, &OldContext);
    if ( v9 >= 0 )
    {
      v10 = NewContext;
    }
    else
    {
      FltReleaseContext(NewContext);
      if ( v9 != -1071906814 )
        return v9;
      v10 = OldContext;
      v9 = 0;
    }
    *a4 = v10;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x140032cd8  mov     r11, rsp
0x140032cdb  mov     [r11+8], rbx
0x140032cdf  mov     [r11+10h], rsi
0x140032ce3  push    rdi
0x140032ce4  sub     rsp, 40h
0x140032ce8  mov     r8d, cs:dword_140018444
0x140032cef  lea     rax, [r11-18h]
0x140032cf3  mov     rbx, rdx
0x140032cf6  mov     qword ptr [r11-18h], 0
0x140032cfe  mov     edx, 10h; ContextType
0x140032d03  mov     qword ptr [r11-10h], 0
0x140032d0b  mov     rdi, r9
0x140032d0e  mov     [r11-28h], rax
0x140032d12  mov     rsi, rcx
0x140032d15  add     r8, 38h ; '8'; ContextSize
0x140032d19  mov     rcx, cs:WofGlobal; Filter
0x140032d20  lea     r9d, [rdx-0Fh]; PoolType
0x140032d24  call    cs:__imp_FltAllocateContext
0x140032d2b  nop     dword ptr [rax+rax+00h]
0x140032d30  test    eax, eax
0x140032d32  js      loc_140032DC4
0x140032d38  mov     r8d, cs:dword_140018444
0x140032d3f  xor     edx, edx; Val
0x140032d41  mov     rcx, [rsp+48h+NewContext]; void *
0x140032d46  add     r8, 38h ; '8'; Size
0x140032d4a  call    memset
0x140032d4f  mov     rax, [rsp+48h+NewContext]
0x140032d54  mov     r8d, 1; Operation
0x140032d5a  add     rax, 18h
0x140032d5e  mov     rdx, rbx; FileObject
0x140032d61  mov     rcx, rsi; Instance
0x140032d64  mov     [rax+8], rax
0x140032d68  mov     [rax], rax
0x140032d6b  mov     rax, [rsp+48h+NewContext]
0x140032d70  mov     dword ptr [rax+4], 0FFFFFFFFh
0x140032d77  lea     rax, [rsp+48h+var_10]
0x140032d7c  mov     r9, [rsp+48h+NewContext]; NewContext
0x140032d81  mov     [rsp+48h+OldContext], rax; OldContext
0x140032d86  call    cs:__imp_FltSetStreamHandleContext
0x140032d8d  nop     dword ptr [rax+rax+00h]
0x140032d92  mov     ebx, eax
0x140032d94  test    eax, eax
0x140032d96  jns     short loc_140032DBA
0x140032d98  mov     rcx, [rsp+48h+NewContext]; Context
0x140032d9d  call    cs:__imp_FltReleaseContext
0x140032da4  nop     dword ptr [rax+rax+00h]
0x140032da9  cmp     ebx, 0C01C0002h
0x140032daf  jnz     short loc_140032DC2
0x140032db1  mov     rax, [rsp+48h+var_10]
0x140032db6  xor     ebx, ebx
0x140032db8  jmp     short loc_140032DBF
0x140032dba  mov     rax, [rsp+48h+NewContext]
0x140032dbf  mov     [rdi], rax
0x140032dc2  mov     eax, ebx
0x140032dc4  mov     rbx, [rsp+48h+arg_0]
0x140032dc9  mov     rsi, [rsp+48h+arg_8]
0x140032dce  add     rsp, 40h
0x140032dd2  pop     rdi
0x140032dd3  retn
```
