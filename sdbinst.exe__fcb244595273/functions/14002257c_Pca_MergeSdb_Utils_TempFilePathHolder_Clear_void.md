# Pca::MergeSdb::Utils::TempFilePathHolder::Clear(void)

- ea: `0x14002257c`
- end: `0x1400225d1`
- name: `?Clear@TempFilePathHolder@Utils@MergeSdb@Pca@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140024958`

## callees

- `0x14002257c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140022596`
- `KERNEL32!GetLastError` at `0x140022596`
- `KERNEL32!GetProcessHeap` at `0x14002259e`
- `KERNEL32!GetProcessHeap` at `0x14002259e`
- `KERNEL32!SetLastError` at `0x1400225b4`
- `KERNEL32!SetLastError` at `0x1400225b4`
- `KERNEL32!HeapFree` at `0x1400225ac`
- `KERNEL32!HeapFree` at `0x1400225ac`

## pseudocode

```c
void __fastcall Pca::MergeSdb::Utils::TempFilePathHolder::Clear(void **this)
{
  void *v1; // rsi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax

  v1 = *this;
  if ( *this )
  {
    LastError = GetLastError();
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    SetLastError(LastError);
  }
  *this = 0;
}

```

## disassembly

```asm
0x14002257c  mov     [rsp+arg_0], rbx
0x140022581  mov     [rsp+arg_8], rsi
0x140022586  push    rdi
0x140022587  sub     rsp, 20h
0x14002258b  mov     rsi, [rcx]
0x14002258e  mov     rdi, rcx
0x140022591  test    rsi, rsi
0x140022594  jz      short loc_1400225BA
0x140022596  call    cs:__imp_GetLastError
0x14002259c  mov     ebx, eax
0x14002259e  call    cs:__imp_GetProcessHeap
0x1400225a4  mov     r8, rsi; lpMem
0x1400225a7  xor     edx, edx; dwFlags
0x1400225a9  mov     rcx, rax; hHeap
0x1400225ac  call    cs:__imp_HeapFree
0x1400225b2  mov     ecx, ebx; dwErrCode
0x1400225b4  call    cs:__imp_SetLastError
0x1400225ba  mov     rbx, [rsp+28h+arg_0]
0x1400225bf  mov     rsi, [rsp+28h+arg_8]
0x1400225c4  mov     qword ptr [rdi], 0
0x1400225cb  add     rsp, 20h
0x1400225cf  pop     rdi
0x1400225d0  retn
```
