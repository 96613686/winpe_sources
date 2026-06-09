# RecordError(long,uint)

- ea: `0x18000f300`
- end: `0x18000f389`
- name: `?RecordError@@YAXJI@Z`
- size: `137`
- prototype: `void __fastcall(int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002660`
- `0x180005850`
- `0x18000f700`
- `0x18000f838`

## callees

- `0x18000f300`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f320`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f320`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f334`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f334`

## pseudocode

```c
void __fastcall RecordError(int a1, int a2)
{
  struct ERROR_RECORD *v3; // rax
  HANDLE ProcessHeap; // rax
  __int64 v6; // rdx
  unsigned int v7; // r8d
  _UNKNOWN *retaddr; // [rsp+28h] [rbp+0h]

  ++g_cErrorsSeen;
  v3 = g_rgErrors;
  if ( g_rgErrors
    || (ProcessHeap = GetProcessHeap(),
        v3 = (struct ERROR_RECORD *)HeapAlloc(ProcessHeap, 8u, 0x640u),
        (g_rgErrors = v3) != 0) )
  {
    v6 = 2LL * g_iNextError++;
    v7 = g_iNextError;
    *((_DWORD *)v3 + 2 * v6) = a1;
    *((_DWORD *)v3 + 2 * v6 + 1) = a2;
    *((_QWORD *)v3 + v6 + 1) = retaddr;
    if ( v7 == 100 )
      g_iNextError = 0;
  }
}

```

## disassembly

```asm
0x18000f300  mov     [rsp+arg_0], rbx
0x18000f305  push    rdi
0x18000f306  sub     rsp, 20h
0x18000f30a  inc     cs:?g_cErrorsSeen@@3IA; uint g_cErrorsSeen
0x18000f310  mov     ebx, edx
0x18000f312  mov     rax, cs:?g_rgErrors@@3PEAUERROR_RECORD@@EA; ERROR_RECORD * g_rgErrors
0x18000f319  mov     edi, ecx
0x18000f31b  test    rax, rax
0x18000f31e  jnz     short loc_18000F346
0x18000f320  call    cs:__imp_GetProcessHeap
0x18000f326  mov     edx, 8; dwFlags
0x18000f32b  mov     r8d, 640h; dwBytes
0x18000f331  mov     rcx, rax; hHeap
0x18000f334  call    cs:__imp_HeapAlloc
0x18000f33a  mov     cs:?g_rgErrors@@3PEAUERROR_RECORD@@EA, rax; ERROR_RECORD * g_rgErrors
0x18000f341  test    rax, rax
0x18000f344  jz      short loc_18000F37E
0x18000f346  mov     r8d, cs:?g_iNextError@@3IA; uint g_iNextError
0x18000f34d  mov     rcx, [rsp+28h]
0x18000f352  mov     edx, r8d
0x18000f355  add     rdx, rdx
0x18000f358  inc     r8d
0x18000f35b  mov     cs:?g_iNextError@@3IA, r8d; uint g_iNextError
0x18000f362  mov     [rax+rdx*8], edi
0x18000f365  mov     [rax+rdx*8+4], ebx
0x18000f369  mov     [rax+rdx*8+8], rcx
0x18000f36e  cmp     r8d, 64h ; 'd'
0x18000f372  jnz     short loc_18000F37E
0x18000f374  mov     cs:?g_iNextError@@3IA, 0; uint g_iNextError
0x18000f37e  mov     rbx, [rsp+28h+arg_0]
0x18000f383  add     rsp, 20h
0x18000f387  pop     rdi
0x18000f388  retn
```
