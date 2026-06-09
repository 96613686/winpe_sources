# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140008aa0`
- end: `0x140008b1c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008614`

## callees

- `0x140008aa0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008ad3`
- `KERNEL32!HeapFree` at `0x140008b04`
- `KERNEL32!HeapFree` at `0x140008ad3`
- `KERNEL32!HeapFree` at `0x140008b04`
- `KERNEL32!GetProcessHeap` at `0x140008ac5`
- `KERNEL32!GetProcessHeap` at `0x140008af6`
- `KERNEL32!GetProcessHeap` at `0x140008ac5`
- `KERNEL32!GetProcessHeap` at `0x140008af6`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x140008aa0  push    rbx
0x140008aa2  push    rbp
0x140008aa3  push    rsi
0x140008aa4  push    rdi
0x140008aa5  sub     rsp, 28h
0x140008aa9  movzx   eax, word ptr [rcx+20h]
0x140008aad  mov     rsi, rcx
0x140008ab0  mov     rdi, [rcx+18h]
0x140008ab4  lea     rbp, [rax+rax*4]
0x140008ab8  shl     rbp, 4
0x140008abc  add     rbp, rdi
0x140008abf  jmp     short loc_140008AED
0x140008ac1  mov     rbx, [rdi+40h]
0x140008ac5  call    cs:__imp_GetProcessHeap
0x140008acb  mov     r8, rbx; lpMem
0x140008ace  xor     edx, edx; dwFlags
0x140008ad0  mov     rcx, rax; hHeap
0x140008ad3  call    cs:__imp_HeapFree
0x140008ad9  mov     qword ptr [rdi+40h], 0
0x140008ae1  mov     qword ptr [rdi+48h], 0
0x140008ae9  add     rdi, 50h ; 'P'
0x140008aed  cmp     rdi, rbp
0x140008af0  jnz     short loc_140008AC1
0x140008af2  mov     rbx, [rsi+18h]
0x140008af6  call    cs:__imp_GetProcessHeap
0x140008afc  mov     r8, rbx; lpMem
0x140008aff  xor     edx, edx; dwFlags
0x140008b01  mov     rcx, rax; hHeap
0x140008b04  call    cs:__imp_HeapFree
0x140008b0a  xor     eax, eax
0x140008b0c  mov     [rsi+20h], eax
0x140008b0f  mov     [rsi+18h], rax
0x140008b13  add     rsp, 28h
0x140008b17  pop     rdi
0x140008b18  pop     rsi
0x140008b19  pop     rbp
0x140008b1a  pop     rbx
0x140008b1b  retn
```
