# AddService(ulong,_PROCESS_RECORD *)

- ea: `0x14001b8d8`
- end: `0x14001b95f`
- name: `?AddService@@YAPEAU_SERVICE_RECORD@@KPEAU_PROCESS_RECORD@@@Z`
- size: `135`
- prototype: `struct _SERVICE_RECORD *__fastcall(int, struct _PROCESS_RECORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140009880`
- `0x14001d51c`

## callees

- `0x14001b8d8`
- `0x1400400d6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b8f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001b8f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001b905`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001b905`

## pseudocode

```c
struct _SERVICE_RECORD *__fastcall AddService(int a1, struct _PROCESS_RECORD *a2)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  _QWORD *v7; // rax
  __int64 v8; // rcx

  if ( !a2 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 8u, 0xA0u);
  v6 = v5;
  if ( !v5 )
    return 0;
  memset_0(v5, 0, 0xA0u);
  v7 = (_QWORD *)((char *)a2 + 32);
  v6[8] = a1;
  v8 = *((_QWORD *)a2 + 4);
  if ( *(struct _PROCESS_RECORD **)(v8 + 8) != (struct _PROCESS_RECORD *)((char *)a2 + 32) )
    __fastfail(3u);
  *((_QWORD *)v6 + 1) = v7;
  *(_QWORD *)v6 = v8;
  *(_QWORD *)(v8 + 8) = v6;
  *v7 = v6;
  return (struct _SERVICE_RECORD *)v6;
}

```

## disassembly

```asm
0x14001b8d8  mov     [rsp+arg_0], rbx
0x14001b8dd  mov     [rsp+arg_8], rsi
0x14001b8e2  push    rdi
0x14001b8e3  sub     rsp, 20h
0x14001b8e7  mov     rdi, rdx
0x14001b8ea  mov     esi, ecx
0x14001b8ec  test    rdx, rdx
0x14001b8ef  jz      short loc_14001B94D
0x14001b8f1  call    cs:__imp_GetProcessHeap
0x14001b8f7  mov     edx, 8; dwFlags
0x14001b8fc  mov     r8d, 0A0h; dwBytes
0x14001b902  mov     rcx, rax; hHeap
0x14001b905  call    cs:__imp_HeapAlloc
0x14001b90b  mov     rbx, rax
0x14001b90e  test    rax, rax
0x14001b911  jz      short loc_14001B94D
0x14001b913  xor     edx, edx; Val
0x14001b915  mov     r8d, 0A0h; Size
0x14001b91b  mov     rcx, rax; void *
0x14001b91e  call    memset_0
0x14001b923  lea     rax, [rdi+20h]
0x14001b927  mov     [rbx+20h], esi
0x14001b92a  mov     rcx, [rax]
0x14001b92d  cmp     [rcx+8], rax
0x14001b931  jz      short loc_14001B93A
0x14001b933  mov     ecx, 3
0x14001b938  int     29h; Win8: RtlFailFast(ecx)
0x14001b93a  mov     [rbx+8], rax
0x14001b93e  mov     [rbx], rcx
0x14001b941  mov     [rcx+8], rbx
0x14001b945  mov     [rax], rbx
0x14001b948  mov     rax, rbx
0x14001b94b  jmp     short loc_14001B94F
0x14001b94d  xor     eax, eax
0x14001b94f  mov     rbx, [rsp+28h+arg_0]
0x14001b954  mov     rsi, [rsp+28h+arg_8]
0x14001b959  add     rsp, 20h
0x14001b95d  pop     rdi
0x14001b95e  retn
```
