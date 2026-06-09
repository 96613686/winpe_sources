# AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)

- ea: `0x140009e54`
- end: `0x14000a050`
- name: `?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z`
- size: `508`
- prototype: `void __fastcall(struct _ASL_LOG *, const char *, size_t)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x14000b83c`

## callees

- `0x14000163e`
- `0x14000164a`
- `0x140002206`
- `0x140009b9c`
- `0x140009d90`
- `0x140009e54`
- `0x14002e3e2`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x140009fb7`
- `KERNEL32!OutputDebugStringA` at `0x140009fb7`
- `ntdll!RtlAllocateHeap` at `0x140009f0e`
- `ntdll!RtlAllocateHeap` at `0x140009f0e`
- `ntdll!RtlEnterCriticalSection` at `0x140009e83`
- `ntdll!RtlEnterCriticalSection` at `0x14000a003`
- `ntdll!RtlEnterCriticalSection` at `0x140009e83`
- `ntdll!RtlEnterCriticalSection` at `0x14000a003`
- `ntdll!RtlLeaveCriticalSection` at `0x140009f88`
- `ntdll!RtlLeaveCriticalSection` at `0x14000a039`
- `ntdll!RtlLeaveCriticalSection` at `0x140009f88`
- `ntdll!RtlLeaveCriticalSection` at `0x14000a039`
- `ntdll!RtlReAllocateHeap` at `0x140009f2e`
- `ntdll!RtlReAllocateHeap` at `0x140009f2e`

## pseudocode

```c
void __fastcall AslLogpWriteLog(struct _ASL_LOG *a1, const char *a2, size_t a3)
{
  DWORD v4; // r13d
  const char *v6; // rbp
  size_t v7; // rsi
  size_t v8; // rcx
  __int64 v9; // rdx
  size_t v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // r14
  unsigned __int64 v13; // rax
  void *v14; // r8
  void *v15; // rcx
  SIZE_T v16; // r14
  PVOID v17; // rax
  PVOID Heap; // r15
  size_t v19; // rax
  size_t v20; // rcx
  size_t v21; // rax
  char *StdHandle_0; // rax

  v4 = a3;
  v6 = a2;
  v7 = a3;
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = 0;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  if ( *(_DWORD *)(*(_QWORD *)a1 + 76LL) )
  {
    v8 = *(unsigned int *)(*(_QWORD *)a1 + 76LL);
    if ( v7 > v8 )
    {
      v6 = &v6[v7 - v8];
      v7 = (unsigned int)v8;
    }
    v9 = *((unsigned int *)a1 + 38);
    if ( v9 + v7 > v8 )
      AslLogpRollStream((struct _RTL_MEMORY_STREAM *)((char *)a1 + 144), v7 + v9 - v8);
  }
  if ( v7 )
  {
    v10 = *((_QWORD *)a1 + 22);
    v11 = v10 + v7;
    if ( v10 + v7 >= v10 )
    {
      if ( v11 <= *((_QWORD *)a1 + 20) )
        goto LABEL_16;
      v12 = *((_QWORD *)a1 + 21) - 1LL;
      v13 = v12 + v11;
      if ( v12 + v11 >= v11 )
      {
        v14 = (void *)*((_QWORD *)a1 + 23);
        v15 = (void *)*((_QWORD *)a1 + 18);
        v16 = v13 & ~v12;
        if ( v14 )
        {
          Heap = RtlReAllocateHeap(v15, 0, v14, v16);
        }
        else
        {
          v17 = RtlAllocateHeap(v15, 0, v16);
          Heap = v17;
          if ( v17 )
            memset_0(v17, 0, v16);
        }
        if ( Heap )
        {
          *((_QWORD *)a1 + 23) = Heap;
          *((_QWORD *)a1 + 20) = v16;
LABEL_16:
          memcpy_0((void *)(*((_QWORD *)a1 + 22) + *((_QWORD *)a1 + 23)), v6, v7);
          v19 = *((_QWORD *)a1 + 22);
          v20 = v19 + v7;
          if ( v19 + v7 < v19 )
          {
            *((_QWORD *)a1 + 22) = -1;
          }
          else
          {
            *((_QWORD *)a1 + 22) = v20;
            v21 = *((_QWORD *)a1 + 19);
            if ( v21 <= v20 )
              v21 = v20;
            *((_QWORD *)a1 + 19) = v21;
          }
        }
      }
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  *(_QWORD *)(*(_QWORD *)a1 + 64LL) = *((_QWORD *)a1 + 23);
  *(_DWORD *)(*(_QWORD *)a1 + 72LL) = *((_DWORD *)a1 + 38);
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 1) != 0 )
    OutputDebugStringA(a2);
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 0x100) != 0 )
  {
    StdHandle_0 = (char *)GetStdHandle_0(0xFFFFFFF5);
    if ( (unsigned __int64)(StdHandle_0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WriteFile_0(StdHandle_0, a2, v7, 0, 0);
  }
  if ( (*(_BYTE *)(*(_QWORD *)a1 + 80LL) & 4) != 0 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
    AslLogpAppendLog(
      (const unsigned __int16 *)a1 + 96,
      a2,
      v4,
      (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 8) != 0,
      (*(_DWORD *)(*(_QWORD *)a1 + 80LL) & 0x20) != 0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 104));
  }
}

```

## disassembly

```asm
0x140009e54  push    rbx
0x140009e56  push    rbp
0x140009e57  push    rsi
0x140009e58  push    rdi
0x140009e59  push    r12
0x140009e5b  push    r13
0x140009e5d  push    r14
0x140009e5f  push    r15
0x140009e61  sub     rsp, 38h
0x140009e65  mov     rax, [rcx]
0x140009e68  mov     rdi, rcx
0x140009e6b  add     rcx, 68h ; 'h'; CriticalSection
0x140009e6f  mov     r13, r8
0x140009e72  mov     r12, rdx
0x140009e75  mov     rbp, rdx
0x140009e78  mov     rsi, r8
0x140009e7b  mov     qword ptr [rax+40h], 0
0x140009e83  call    cs:__imp_RtlEnterCriticalSection
0x140009e89  mov     rax, [rdi]
0x140009e8c  lea     rbx, [rdi+90h]
0x140009e93  cmp     dword ptr [rax+4Ch], 0
0x140009e97  jz      short loc_140009EC3
0x140009e99  mov     ecx, [rax+4Ch]
0x140009e9c  cmp     rsi, rcx
0x140009e9f  jbe     short loc_140009EA9
0x140009ea1  sub     rbp, rcx
0x140009ea4  add     rbp, rsi
0x140009ea7  mov     esi, ecx
0x140009ea9  mov     edx, [rbx+8]
0x140009eac  lea     rax, [rdx+rsi]
0x140009eb0  cmp     rax, rcx
0x140009eb3  jbe     short loc_140009EC3
0x140009eb5  sub     rdx, rcx
0x140009eb8  mov     rcx, rbx; struct _RTL_MEMORY_STREAM *
0x140009ebb  add     rdx, rsi; unsigned __int64
0x140009ebe  call    ?AslLogpRollStream@@YAXPEAU_RTL_MEMORY_STREAM@@_K@Z; AslLogpRollStream(_RTL_MEMORY_STREAM *,unsigned __int64)
0x140009ec3  test    rsi, rsi
0x140009ec6  jz      loc_140009F81
0x140009ecc  mov     rax, [rbx+20h]
0x140009ed0  lea     rcx, [rax+rsi]
0x140009ed4  cmp     rcx, rax
0x140009ed7  jb      loc_140009F81
0x140009edd  cmp     rcx, [rbx+10h]
0x140009ee1  jbe     short loc_140009F44
0x140009ee3  mov     r14, [rbx+18h]
0x140009ee7  dec     r14
0x140009eea  lea     rax, [r14+rcx]
0x140009eee  cmp     rax, rcx
0x140009ef1  jb      loc_140009F81
0x140009ef7  mov     r8, [rbx+28h]; Ptr
0x140009efb  not     r14
0x140009efe  mov     rcx, [rbx]; Heap
0x140009f01  and     r14, rax
0x140009f04  xor     edx, edx; Flags
0x140009f06  test    r8, r8
0x140009f09  jnz     short loc_140009F2B
0x140009f0b  mov     r8, r14; Size
0x140009f0e  call    cs:__imp_RtlAllocateHeap
0x140009f14  mov     r15, rax
0x140009f17  test    rax, rax
0x140009f1a  jz      short loc_140009F37
0x140009f1c  mov     r8, r14; Size
0x140009f1f  xor     edx, edx; Val
0x140009f21  mov     rcx, rax; void *
0x140009f24  call    memset_0
0x140009f29  jmp     short loc_140009F37
0x140009f2b  mov     r9, r14; Size
0x140009f2e  call    cs:__imp_RtlReAllocateHeap
0x140009f34  mov     r15, rax
0x140009f37  test    r15, r15
0x140009f3a  jz      short loc_140009F81
0x140009f3c  mov     [rbx+28h], r15
0x140009f40  mov     [rbx+10h], r14
0x140009f44  mov     rcx, [rbx+28h]
0x140009f48  mov     r8, rsi; Size
0x140009f4b  add     rcx, [rbx+20h]; void *
0x140009f4f  mov     rdx, rbp; Src
0x140009f52  call    memcpy_0
0x140009f57  mov     rax, [rbx+20h]
0x140009f5b  lea     rcx, [rax+rsi]
0x140009f5f  cmp     rcx, rax
0x140009f62  jb      short loc_140009F79
0x140009f64  mov     [rbx+20h], rcx
0x140009f68  mov     rax, [rbx+8]
0x140009f6c  cmp     rax, rcx
0x140009f6f  cmovbe  rax, rcx
0x140009f73  mov     [rbx+8], rax
0x140009f77  jmp     short loc_140009F81
0x140009f79  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x140009f81  lea     rbx, [rdi+68h]
0x140009f85  mov     rcx, rbx; CriticalSection
0x140009f88  call    cs:__imp_RtlLeaveCriticalSection
0x140009f8e  mov     rax, [rdi+0B8h]
0x140009f95  mov     bpl, 1
0x140009f98  mov     rcx, [rdi]
0x140009f9b  mov     [rcx+40h], rax
0x140009f9f  mov     eax, [rdi+98h]
0x140009fa5  mov     rcx, [rdi]
0x140009fa8  mov     [rcx+48h], eax
0x140009fab  mov     rax, [rdi]
0x140009fae  test    [rax+50h], bpl
0x140009fb2  jz      short loc_140009FBD
0x140009fb4  mov     rcx, r12; lpOutputString
0x140009fb7  call    cs:__imp_OutputDebugStringA
0x140009fbd  mov     rax, [rdi]
0x140009fc0  test    dword ptr [rax+50h], 100h
0x140009fc7  jz      short loc_140009FF7
0x140009fc9  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140009fce  call    GetStdHandle_0
0x140009fd3  lea     rcx, [rax-1]
0x140009fd7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140009fdb  ja      short loc_140009FF7
0x140009fdd  mov     r8d, esi; nNumberOfBytesToWrite
0x140009fe0  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x140009fe9  xor     r9d, r9d; lpNumberOfBytesWritten
0x140009fec  mov     rdx, r12; lpBuffer
0x140009fef  mov     rcx, rax; hFile
0x140009ff2  call    WriteFile_0
0x140009ff7  mov     rax, [rdi]
0x140009ffa  test    byte ptr [rax+50h], 4
0x140009ffe  jz      short loc_14000A03F
0x14000a000  mov     rcx, rbx; CriticalSection
0x14000a003  call    cs:__imp_RtlEnterCriticalSection
0x14000a009  mov     rax, [rdi]
0x14000a00c  lea     rcx, [rdi+0C0h]; unsigned __int16 *
0x14000a013  mov     r8, r13; unsigned __int64
0x14000a016  mov     rdx, r12; char *
0x14000a019  mov     r9d, [rax+50h]
0x14000a01d  mov     eax, r9d
0x14000a020  shr     eax, 5
0x14000a023  shr     r9d, 3
0x14000a027  and     al, bpl
0x14000a02a  and     r9b, bpl; unsigned __int8
0x14000a02d  mov     byte ptr [rsp+78h+lpOverlapped], al; unsigned __int8
0x14000a031  call    ?AslLogpAppendLog@@YAJPEBGPEBD_KEE@Z; AslLogpAppendLog(ushort const *,char const *,unsigned __int64,uchar,uchar)
0x14000a036  mov     rcx, rbx; CriticalSection
0x14000a039  call    cs:__imp_RtlLeaveCriticalSection
0x14000a03f  add     rsp, 38h
0x14000a043  pop     r15
0x14000a045  pop     r14
0x14000a047  pop     r13
0x14000a049  pop     r12
0x14000a04b  pop     rdi
0x14000a04c  pop     rsi
0x14000a04d  pop     rbp
0x14000a04e  pop     rbx
0x14000a04f  retn
```
