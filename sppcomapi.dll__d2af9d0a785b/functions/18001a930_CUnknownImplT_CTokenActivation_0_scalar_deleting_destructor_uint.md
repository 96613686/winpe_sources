# CUnknownImplT<CTokenActivation,0>::`scalar deleting destructor'(uint)

- ea: `0x18001a930`
- end: `0x18001a978`
- name: `??_G?$CUnknownImplT@VCTokenActivation@@$0A@@@UEAAPEAXI@Z`
- size: `72`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001a404`
- `0x18001a930`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a949`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a95d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a95d`

## pseudocode

```c
CTokenActivation *__fastcall CUnknownImplT<CTokenActivation,0>::`scalar deleting destructor'(
        CTokenActivation *lpMem,
        char a2)
{
  HANDLE ProcessHeap; // rax

  CTokenActivation::~CTokenActivation(lpMem);
  if ( (a2 & 1) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return lpMem;
}

```

## disassembly

```asm
0x18001a930  mov     [rsp+arg_0], rbx
0x18001a935  push    rdi
0x18001a936  sub     rsp, 20h
0x18001a93a  mov     ebx, edx
0x18001a93c  mov     rdi, rcx
0x18001a93f  call    ??1CTokenActivation@@UEAA@XZ; CTokenActivation::~CTokenActivation(void)
0x18001a944  test    bl, 1
0x18001a947  jz      short loc_18001A969
0x18001a949  call    cs:__imp_GetProcessHeap
0x18001a950  nop     dword ptr [rax+rax+00h]
0x18001a955  mov     r8, rdi; lpMem
0x18001a958  xor     edx, edx; dwFlags
0x18001a95a  mov     rcx, rax; hHeap
0x18001a95d  call    cs:__imp_HeapFree
0x18001a964  nop     dword ptr [rax+rax+00h]
0x18001a969  mov     rbx, [rsp+28h+arg_0]
0x18001a96e  mov     rax, rdi
0x18001a971  add     rsp, 20h
0x18001a975  pop     rdi
0x18001a976  retn
```
