# NewReplaceToken(int)

- ea: `0x140019adc`
- end: `0x140019b13`
- name: `?NewReplaceToken@@YAPEAU_REPLACE_TOKEN@@H@Z`
- size: `55`
- prototype: `struct _REPLACE_TOKEN *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140019b70`

## callees

- `0x140019adc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019ae4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140019ae4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140019af6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140019af6`

## pseudocode

```c
struct _REPLACE_TOKEN *__fastcall NewReplaceToken(int a1)
{
  HANDLE ProcessHeap; // rax
  struct _REPLACE_TOKEN *result; // rax

  ProcessHeap = GetProcessHeap();
  result = (struct _REPLACE_TOKEN *)HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( result )
  {
    *((_DWORD *)result + 4) = a1;
    *(_QWORD *)((char *)result + 20) = 0;
    *((_DWORD *)result + 7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140019adc  push    rbx
0x140019ade  sub     rsp, 20h
0x140019ae2  mov     ebx, ecx
0x140019ae4  call    cs:__imp_GetProcessHeap
0x140019aea  mov     edx, 8; dwFlags
0x140019aef  mov     rcx, rax; hHeap
0x140019af2  lea     r8d, [rdx+18h]; dwBytes
0x140019af6  call    cs:__imp_HeapAlloc
0x140019afc  xor     ecx, ecx
0x140019afe  test    rax, rax
0x140019b01  jz      short loc_140019B0D
0x140019b03  mov     [rax+10h], ebx
0x140019b06  mov     [rax+14h], rcx
0x140019b0a  mov     [rax+1Ch], ecx
0x140019b0d  add     rsp, 20h
0x140019b11  pop     rbx
0x140019b12  retn
```
