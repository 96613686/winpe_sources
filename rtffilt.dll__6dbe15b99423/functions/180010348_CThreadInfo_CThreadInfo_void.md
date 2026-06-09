# CThreadInfo::~CThreadInfo(void)

- ea: `0x180010348`
- end: `0x1800103ae`
- name: `??1CThreadInfo@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(CThreadInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001026c`

## callees

- `0x180010348`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001035a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001035a`

## pseudocode

```c
void __fastcall CThreadInfo::~CThreadInfo(CThreadInfo *this)
{
  HMODULE v2; // rcx
  volatile signed __int32 *v3; // rbx

  v2 = (HMODULE)*((_QWORD *)this + 5);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v3 && _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
    if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
}

```

## disassembly

```asm
0x180010348  push    rbx
0x18001034a  sub     rsp, 20h
0x18001034e  mov     rbx, rcx
0x180010351  mov     rcx, [rcx+28h]; hLibModule
0x180010355  test    rcx, rcx
0x180010358  jz      short loc_180010368
0x18001035a  call    cs:__imp_FreeLibrary
0x180010360  mov     qword ptr [rbx+28h], 0
0x180010368  mov     rbx, [rbx+8]
0x18001036c  test    rbx, rbx
0x18001036f  jz      short loc_1800103A8
0x180010371  or      eax, 0FFFFFFFFh
0x180010374  lock xadd [rbx+8], eax
0x180010379  cmp     eax, 1
0x18001037c  jnz     short loc_1800103A8
0x18001037e  mov     rax, [rbx]
0x180010381  mov     rcx, rbx
0x180010384  mov     rax, [rax]
0x180010387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001038c  or      eax, 0FFFFFFFFh
0x18001038f  lock xadd [rbx+0Ch], eax
0x180010394  cmp     eax, 1
0x180010397  jnz     short loc_1800103A8
0x180010399  mov     rax, [rbx]
0x18001039c  mov     rcx, rbx
0x18001039f  mov     rax, [rax+8]
0x1800103a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103a8  add     rsp, 20h
0x1800103ac  pop     rbx
0x1800103ad  retn
```
