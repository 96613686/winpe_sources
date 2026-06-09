# T2malloc

- ea: `0x180017ee0`
- end: `0x180017f26`
- name: `T2malloc`
- size: `70`
- prototype: `__int64 __fastcall(SIZE_T dwBytes)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x18001862c`
- `0x1800190a4`
- `0x180019e18`
- `0x18001a2b0`
- `0x18001acbc`
- `0x18001b538`
- `0x18001bc30`
- `0x18001c87c`
- `0x18001d040`
- `0x18001f11c`
- `0x18001f830`
- `0x18001fcb0`
- `0x180021aa4`
- `0x180021d54`
- `0x180022fcc`
- `0x180023380`
- `0x180023434`

## callees

- `0x180017ee0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180017f0d`
- `KERNEL32!HeapAlloc` at `0x180017f0d`
- `KERNEL32!GetProcessHeap` at `0x180017eff`
- `KERNEL32!GetProcessHeap` at `0x180017eff`

## pseudocode

```c
LPVOID __fastcall T2malloc(SIZE_T dwBytes, int a2)
{
  unsigned int v2; // edi
  DWORD v3; // ebx
  HANDLE ProcessHeap; // rax

  if ( (unsigned int)dwBytes > 0x7FFFFFFF )
    return 0;
  v2 = dwBytes;
  v3 = a2 != 0 ? 8 : 0;
  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, v3, v2);
}

```

## disassembly

```asm
0x180017ee0  sub     rsp, 28h
0x180017ee4  cmp     ecx, 7FFFFFFFh
0x180017eea  ja      short loc_180017F22
0x180017eec  mov     [rsp+28h+arg_0], rbx
0x180017ef1  neg     edx
0x180017ef3  mov     [rsp+28h+var_8], rdi
0x180017ef8  sbb     ebx, ebx
0x180017efa  mov     edi, ecx
0x180017efc  and     ebx, 8
0x180017eff  call    cs:__imp_GetProcessHeap
0x180017f05  mov     r8d, edi; dwBytes
0x180017f08  mov     edx, ebx; dwFlags
0x180017f0a  mov     rcx, rax; hHeap
0x180017f0d  call    cs:__imp_HeapAlloc
0x180017f13  mov     rdi, [rsp+28h+var_8]
0x180017f18  mov     rbx, [rsp+28h+arg_0]
0x180017f1d  add     rsp, 28h
0x180017f21  retn
0x180017f22  xor     eax, eax
0x180017f24  jmp     short loc_180017F1D
```
