# PollingAppDataList::~PollingAppDataList(void)

- ea: `0x1800ed01c`
- end: `0x1800ed0d1`
- name: `??1PollingAppDataList@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(PollingAppDataList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ed99c`

## callees

- `0x1800ed01c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ed0a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ed0a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ed0b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ed0b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed06e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed06e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed092`

## pseudocode

```c
void __fastcall PollingAppDataList::~PollingAppDataList(PollingAppDataList *this)
{
  PollingAppDataList *v2; // rbx
  __int64 v3; // rax
  void *v4; // rcx
  void *v5; // rcx
  __int64 i; // rsi
  void *v7; // rcx
  HANDLE ProcessHeap; // rax

  while ( 1 )
  {
    v2 = *(PollingAppDataList **)this;
    if ( *(PollingAppDataList **)this == this )
      break;
    if ( *((PollingAppDataList **)v2 + 1) != this
      || (v3 = *(_QWORD *)v2, *(PollingAppDataList **)(*(_QWORD *)v2 + 8LL) != v2) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)this = v3;
    *(_QWORD *)(v3 + 8) = this;
    v4 = (void *)*((_QWORD *)v2 + 2);
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *((_QWORD *)v2 + 2) = 0;
    }
    v5 = (void *)*((_QWORD *)v2 + 13);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *((_QWORD *)v2 + 13) = 0;
    }
    for ( i = 0; (unsigned int)i < *((_DWORD *)v2 + 10); i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 5 )
        break;
      v7 = (void *)*((_QWORD *)v2 + i + 6);
      if ( v7 )
      {
        CoTaskMemFree(v7);
        *((_QWORD *)v2 + i + 6) = 0;
      }
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x1800ed01c  push    rbx
0x1800ed01e  push    rbp
0x1800ed01f  push    rsi
0x1800ed020  push    rdi
0x1800ed021  sub     rsp, 28h
0x1800ed025  mov     rdi, rcx
0x1800ed028  mov     rbx, [rdi]
0x1800ed02b  cmp     rbx, rdi
0x1800ed02e  jz      loc_1800ED0C8
0x1800ed034  cmp     [rbx+8], rdi
0x1800ed038  jnz     loc_1800ED0C1
0x1800ed03e  mov     rax, [rbx]
0x1800ed041  cmp     [rax+8], rbx
0x1800ed045  jnz     short loc_1800ED0C1
0x1800ed047  mov     [rdi], rax
0x1800ed04a  mov     [rax+8], rdi
0x1800ed04e  mov     rcx, [rbx+10h]; pv
0x1800ed052  test    rcx, rcx
0x1800ed055  jz      short loc_1800ED065
0x1800ed057  call    cs:__imp_CoTaskMemFree
0x1800ed05d  mov     qword ptr [rbx+10h], 0
0x1800ed065  mov     rcx, [rbx+68h]; pv
0x1800ed069  test    rcx, rcx
0x1800ed06c  jz      short loc_1800ED07C
0x1800ed06e  call    cs:__imp_CoTaskMemFree
0x1800ed074  mov     qword ptr [rbx+68h], 0
0x1800ed07c  xor     esi, esi
0x1800ed07e  cmp     [rbx+28h], esi
0x1800ed081  jbe     short loc_1800ED0A8
0x1800ed083  cmp     esi, 5
0x1800ed086  jnb     short loc_1800ED0A8
0x1800ed088  mov     rcx, [rbx+rsi*8+30h]; pv
0x1800ed08d  test    rcx, rcx
0x1800ed090  jz      short loc_1800ED0A1
0x1800ed092  call    cs:__imp_CoTaskMemFree
0x1800ed098  mov     qword ptr [rbx+rsi*8+30h], 0
0x1800ed0a1  inc     esi
0x1800ed0a3  cmp     esi, [rbx+28h]
0x1800ed0a6  jb      short loc_1800ED083
0x1800ed0a8  call    cs:__imp_GetProcessHeap
0x1800ed0ae  mov     r8, rbx; lpMem
0x1800ed0b1  xor     edx, edx; dwFlags
0x1800ed0b3  mov     rcx, rax; hHeap
0x1800ed0b6  call    cs:__imp_HeapFree
0x1800ed0bc  jmp     loc_1800ED028
0x1800ed0c1  mov     ecx, 3
0x1800ed0c6  int     29h; Win8: RtlFailFast(ecx)
0x1800ed0c8  add     rsp, 28h
0x1800ed0cc  pop     rdi
0x1800ed0cd  pop     rsi
0x1800ed0ce  pop     rbp
0x1800ed0cf  pop     rbx
0x1800ed0d0  retn
```
