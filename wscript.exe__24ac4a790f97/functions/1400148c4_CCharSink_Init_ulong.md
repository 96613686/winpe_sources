# CCharSink::Init(ulong)

- ea: `0x1400148c4`
- end: `0x140014952`
- name: `?Init@CCharSink@@QEAAJK@Z`
- size: `142`
- prototype: `__int64 __fastcall(CCharSink *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400057f0`
- `0x14000d298`
- `0x14000f540`
- `0x140011e90`

## callees

- `0x1400148c4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400148ee`
- `KERNEL32!HeapFree` at `0x1400148ee`
- `KERNEL32!HeapAlloc` at `0x140014917`
- `KERNEL32!HeapAlloc` at `0x140014917`
- `KERNEL32!GetProcessHeap` at `0x1400148e0`
- `KERNEL32!GetProcessHeap` at `0x140014909`
- `KERNEL32!GetProcessHeap` at `0x1400148e0`
- `KERNEL32!GetProcessHeap` at `0x140014909`

## pseudocode

```c
__int64 __fastcall CCharSink::Init(CCharSink *this, unsigned int a2)
{
  void *v2; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax
  _WORD *v7; // rax
  _WORD *v8; // rcx
  __int64 result; // rax

  v2 = *(void **)this;
  v4 = a2;
  if ( *(_QWORD *)this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  *((_DWORD *)this + 3) = v4;
  if ( (unsigned __int64)(2 * v4) > 0xFFFFFFFF )
    return 2147942934LL;
  v6 = GetProcessHeap();
  v7 = HeapAlloc(v6, 0, (unsigned int)(2 * v4));
  *(_QWORD *)this = v7;
  v8 = v7;
  *((_DWORD *)this + 2) = 0;
  if ( !v7 )
    return 2147942414LL;
  result = 0;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x1400148c4  mov     [rsp+arg_0], rbx
0x1400148c9  mov     [rsp+arg_8], rsi
0x1400148ce  push    rdi
0x1400148cf  sub     rsp, 20h
0x1400148d3  mov     rsi, [rcx]
0x1400148d6  mov     rdi, rcx
0x1400148d9  mov     ebx, edx
0x1400148db  test    rsi, rsi
0x1400148de  jz      short loc_1400148F4
0x1400148e0  call    cs:__imp_GetProcessHeap
0x1400148e6  mov     r8, rsi; lpMem
0x1400148e9  xor     edx, edx; dwFlags
0x1400148eb  mov     rcx, rax; hHeap
0x1400148ee  call    cs:__imp_HeapFree
0x1400148f4  mov     rax, rbx
0x1400148f7  mov     [rdi+0Ch], ebx
0x1400148fa  add     rax, rax
0x1400148fd  mov     ecx, 0FFFFFFFFh
0x140014902  cmp     rax, rcx
0x140014905  ja      short loc_14001493D
0x140014907  mov     ebx, eax
0x140014909  call    cs:__imp_GetProcessHeap
0x14001490f  mov     r8d, ebx; dwBytes
0x140014912  xor     edx, edx; dwFlags
0x140014914  mov     rcx, rax; hHeap
0x140014917  call    cs:__imp_HeapAlloc
0x14001491d  mov     [rdi], rax
0x140014920  mov     rcx, rax
0x140014923  mov     dword ptr [rdi+8], 0
0x14001492a  test    rax, rax
0x14001492d  jnz     short loc_140014936
0x14001492f  mov     eax, 8007000Eh
0x140014934  jmp     short loc_140014942
0x140014936  xor     eax, eax
0x140014938  mov     [rcx], ax
0x14001493b  jmp     short loc_140014942
0x14001493d  mov     eax, 80070216h
0x140014942  mov     rbx, [rsp+28h+arg_0]
0x140014947  mov     rsi, [rsp+28h+arg_8]
0x14001494c  add     rsp, 20h
0x140014950  pop     rdi
0x140014951  retn
```
