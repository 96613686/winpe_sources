# CDebugFilter::CreateObject(void)

- ea: `0x1800202e0`
- end: `0x180020364`
- name: `?CreateObject@CDebugFilter@@SAPEAVILogProvider@@XZ`
- size: `132`
- prototype: `struct ILogProvider *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001144`
- `0x18001ac00`
- `0x1800202e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18002032c`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameA` at `0x18002032c`

## pseudocode

```c
struct ILogProvider *CDebugFilter::CreateObject(void)
{
  CHAR *v0; // rax
  char *v1; // rbx

  v0 = (CHAR *)operator new(0x128u);
  v1 = v0;
  if ( !v0 )
    return 0;
  *(_QWORD *)v0 = &CDebugFilter::`vftable';
  *((_DWORD *)v0 + 2) = -1;
  *((_DWORD *)v0 + 3) = -1;
  *((_DWORD *)v0 + 4) = -1;
  *((_DWORD *)v0 + 5) = -1;
  *((_DWORD *)v0 + 6) = -1;
  *((_DWORD *)v0 + 7) = -1;
  if ( !GetModuleFileNameA(0, v0 + 32, 0x104u) )
    StringCchCopyA(v1 + 32, 0x104u, "<program name unknown>");
  return (struct ILogProvider *)v1;
}

```

## disassembly

```asm
0x1800202e0  mov     [rsp+arg_8], rbx
0x1800202e5  push    rdi
0x1800202e6  sub     rsp, 20h
0x1800202ea  mov     ecx, 128h; Size
0x1800202ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800202f4  mov     [rsp+28h+arg_0], rax
0x1800202f9  mov     rbx, rax
0x1800202fc  test    rax, rax
0x1800202ff  jz      short loc_180020353
0x180020301  lea     rax, ??_7CDebugFilter@@6B@; const CDebugFilter::`vftable'
0x180020308  mov     r8d, 104h; nSize
0x18002030e  mov     [rbx], rax
0x180020311  lea     rdx, [rbx+20h]; lpFilename
0x180020315  or      eax, 0FFFFFFFFh
0x180020318  xor     ecx, ecx; hModule
0x18002031a  mov     [rbx+8], eax
0x18002031d  mov     [rbx+0Ch], eax
0x180020320  mov     [rbx+10h], eax
0x180020323  mov     [rbx+14h], eax
0x180020326  mov     [rbx+18h], eax
0x180020329  mov     [rbx+1Ch], eax
0x18002032c  call    cs:__imp_GetModuleFileNameA
0x180020333  nop     dword ptr [rax+rax+00h]
0x180020338  test    eax, eax
0x18002033a  jnz     short loc_180020355
0x18002033c  lea     r8, aProgramNameUnk; "<program name unknown>"
0x180020343  mov     edx, 104h; unsigned __int64
0x180020348  lea     rcx, [rbx+20h]; char *
0x18002034c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180020351  jmp     short loc_180020355
0x180020353  xor     ebx, ebx
0x180020355  mov     rax, rbx
0x180020358  mov     rbx, [rsp+28h+arg_8]
0x18002035d  add     rsp, 20h
0x180020361  pop     rdi
0x180020362  retn
```
