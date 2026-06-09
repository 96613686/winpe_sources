# GrowFile::SetFileSize(void *,unsigned __int64)

- ea: `0x18009a4c0`
- end: `0x18009a55a`
- name: `?SetFileSize@GrowFile@@AEAAJPEAX_K@Z`
- size: `154`
- prototype: `int(GrowFile *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180099b08`
- `0x180099e9c`
- `0x180099f38`

## callees

- `0x1800627f0`
- `0x18009a4c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009a4ee`
- `KERNEL32!GetLastError` at `0x18009a51a`
- `KERNEL32!GetLastError` at `0x18009a4ee`
- `KERNEL32!GetLastError` at `0x18009a51a`
- `KERNEL32!SetFilePointerEx` at `0x18009a4e4`
- `KERNEL32!SetFilePointerEx` at `0x18009a4e4`
- `KERNEL32!SetEndOfFile` at `0x18009a510`
- `KERNEL32!SetEndOfFile` at `0x18009a510`

## pseudocode

```c
__int64 __fastcall GrowFile::SetFileSize(GrowFile *this, void *a2, LARGE_INTEGER a3)
{
  signed int LastError; // eax
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  signed int v8; // eax

  if ( !SetFilePointerEx(a2, a3, 0, 0) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = 325;
LABEL_9:
    SBEBasicTracers::EtwTraceError(
      (GrowFile *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp",
      v7,
      v6);
    return v6;
  }
  v6 = 0;
  if ( !SetEndOfFile(a2) )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v7 = 326;
    goto LABEL_9;
  }
  return v6;
}

```

## disassembly

```asm
0x18009a4c0  mov     [rsp+arg_0], rbx
0x18009a4c5  mov     [rsp+arg_8], rsi
0x18009a4ca  push    rdi
0x18009a4cb  sub     rsp, 20h
0x18009a4cf  mov     rax, r8
0x18009a4d2  mov     rdi, rdx
0x18009a4d5  mov     rsi, rcx
0x18009a4d8  mov     rdx, rax; liDistanceToMove
0x18009a4db  mov     rcx, rdi; hFile
0x18009a4de  xor     r9d, r9d; dwMoveMethod
0x18009a4e1  xor     r8d, r8d; lpNewFilePointer
0x18009a4e4  call    cs:__imp_SetFilePointerEx
0x18009a4ea  test    eax, eax
0x18009a4ec  jnz     short loc_18009A50B
0x18009a4ee  call    cs:__imp_GetLastError
0x18009a4f4  mov     ebx, eax
0x18009a4f6  test    eax, eax
0x18009a4f8  jle     short loc_18009A503
0x18009a4fa  movzx   ebx, ax
0x18009a4fd  or      ebx, 80070000h
0x18009a503  mov     r8d, 145h
0x18009a509  jmp     short loc_18009A535
0x18009a50b  mov     rcx, rdi; hFile
0x18009a50e  xor     ebx, ebx
0x18009a510  call    cs:__imp_SetEndOfFile
0x18009a516  test    eax, eax
0x18009a518  jnz     short loc_18009A548
0x18009a51a  call    cs:__imp_GetLastError
0x18009a520  mov     ebx, eax
0x18009a522  test    eax, eax
0x18009a524  jle     short loc_18009A52F
0x18009a526  movzx   ebx, ax
0x18009a529  or      ebx, 80070000h
0x18009a52f  mov     r8d, 146h; unsigned int
0x18009a535  mov     r9d, ebx; unsigned int
0x18009a538  lea     rdx, aMultimediaDsho_1; "multimedia\\dshow\\filters\\sbe\\sal\\g"...
0x18009a53f  lea     rcx, [rsi+58h]; struct CEhEventTracer *
0x18009a543  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x18009a548  mov     rsi, [rsp+28h+arg_8]
0x18009a54d  mov     eax, ebx
0x18009a54f  mov     rbx, [rsp+28h+arg_0]
0x18009a554  add     rsp, 20h
0x18009a558  pop     rdi
0x18009a559  retn
```
