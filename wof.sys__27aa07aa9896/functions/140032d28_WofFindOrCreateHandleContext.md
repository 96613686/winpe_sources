# WofFindOrCreateHandleContext

- ea: `0x140032d28`
- end: `0x140032e25`
- name: `WofFindOrCreateHandleContext`
- size: `253`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140023ec4`
- `0x140032c00`
- `0x140033930`

## callees

- `0x1400119c0`
- `0x140032d28`

## import_xrefs

- `FLTMGR!FltSetStreamHandleContext` at `0x140032dd6`
- `FLTMGR!FltSetStreamHandleContext` at `0x140032dd6`
- `FLTMGR!FltReleaseContext` at `0x140032ded`
- `FLTMGR!FltReleaseContext` at `0x140032ded`
- `FLTMGR!FltAllocateContext` at `0x140032d74`
- `FLTMGR!FltAllocateContext` at `0x140032d74`

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
0x140032d28  mov     r11, rsp
0x140032d2b  mov     [r11+8], rbx
0x140032d2f  mov     [r11+10h], rsi
0x140032d33  push    rdi
0x140032d34  sub     rsp, 40h
0x140032d38  mov     r8d, cs:dword_140018444
0x140032d3f  lea     rax, [r11-18h]
0x140032d43  mov     rbx, rdx
0x140032d46  mov     qword ptr [r11-18h], 0
0x140032d4e  mov     edx, 10h; ContextType
0x140032d53  mov     qword ptr [r11-10h], 0
0x140032d5b  mov     rdi, r9
0x140032d5e  mov     [r11-28h], rax
0x140032d62  mov     rsi, rcx
0x140032d65  add     r8, 38h ; '8'; ContextSize
0x140032d69  mov     rcx, cs:WofGlobal; Filter
0x140032d70  lea     r9d, [rdx-0Fh]; PoolType
0x140032d74  call    cs:__imp_FltAllocateContext
0x140032d7b  nop     dword ptr [rax+rax+00h]
0x140032d80  test    eax, eax
0x140032d82  js      loc_140032E14
0x140032d88  mov     r8d, cs:dword_140018444
0x140032d8f  xor     edx, edx; Val
0x140032d91  mov     rcx, [rsp+48h+NewContext]; void *
0x140032d96  add     r8, 38h ; '8'; Size
0x140032d9a  call    memset
0x140032d9f  mov     rax, [rsp+48h+NewContext]
0x140032da4  mov     r8d, 1; Operation
0x140032daa  add     rax, 18h
0x140032dae  mov     rdx, rbx; FileObject
0x140032db1  mov     rcx, rsi; Instance
0x140032db4  mov     [rax+8], rax
0x140032db8  mov     [rax], rax
0x140032dbb  mov     rax, [rsp+48h+NewContext]
0x140032dc0  mov     dword ptr [rax+4], 0FFFFFFFFh
0x140032dc7  lea     rax, [rsp+48h+var_10]
0x140032dcc  mov     r9, [rsp+48h+NewContext]; NewContext
0x140032dd1  mov     [rsp+48h+OldContext], rax; OldContext
0x140032dd6  call    cs:__imp_FltSetStreamHandleContext
0x140032ddd  nop     dword ptr [rax+rax+00h]
0x140032de2  mov     ebx, eax
0x140032de4  test    eax, eax
0x140032de6  jns     short loc_140032E0A
0x140032de8  mov     rcx, [rsp+48h+NewContext]; Context
0x140032ded  call    cs:__imp_FltReleaseContext
0x140032df4  nop     dword ptr [rax+rax+00h]
0x140032df9  cmp     ebx, 0C01C0002h
0x140032dff  jnz     short loc_140032E12
0x140032e01  mov     rax, [rsp+48h+var_10]
0x140032e06  xor     ebx, ebx
0x140032e08  jmp     short loc_140032E0F
0x140032e0a  mov     rax, [rsp+48h+NewContext]
0x140032e0f  mov     [rdi], rax
0x140032e12  mov     eax, ebx
0x140032e14  mov     rbx, [rsp+48h+arg_0]
0x140032e19  mov     rsi, [rsp+48h+arg_8]
0x140032e1e  add     rsp, 40h
0x140032e22  pop     rdi
0x140032e23  retn
```
