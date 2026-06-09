# CUnbufferedWriter::FindCurrentOperation(void)

- ea: `0x18000cc7c`
- end: `0x18000cd93`
- name: `?FindCurrentOperation@CUnbufferedWriter@@AEAAPEAUCAsyncOperation@@XZ`
- size: `279`
- prototype: `struct CAsyncOperation *__fastcall(CUnbufferedWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d140`

## callees

- `0x18000cc7c`
- `0x18000cfa8`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x18000cd49`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000cd49`
- `KERNEL32!VirtualAlloc` at `0x18000ccfa`
- `KERNEL32!VirtualAlloc` at `0x18000ccfa`
- `KERNEL32!ReleaseMutex` at `0x18000cd2d`
- `KERNEL32!ReleaseMutex` at `0x18000cd2d`

## pseudocode

```c
struct CAsyncOperation *__fastcall CUnbufferedWriter::FindCurrentOperation(CUnbufferedWriter *this)
{
  __int64 i; // rdx
  struct CAsyncOperation *result; // rax
  __int64 j; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 k; // rdx

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 11); i = (unsigned int)(i + 1) )
  {
    result = (struct CAsyncOperation *)(48 * i + *((_QWORD *)this + 10));
    if ( *((_DWORD *)result + 11) == 1 )
      return result;
  }
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 11); j = (unsigned int)(j + 1) )
  {
    v5 = *((_QWORD *)this + 10);
    v6 = 48 * j;
    if ( !*(_DWORD *)(v5 + 48 * j + 44) )
    {
      *(_DWORD *)(v5 + v6 + 44) = 1;
      *(_DWORD *)(*((_QWORD *)this + 10) + v6 + 40) = 0;
      v7 = *((_QWORD *)this + 10);
      if ( *(_QWORD *)(v7 + v6 + 32) )
        return (struct CAsyncOperation *)(v6 + v7);
      *(_QWORD *)(*((_QWORD *)this + 10) + v6 + 32) = VirtualAlloc(0, *((unsigned int *)this + 10), 0x1000u, 4u);
      v7 = *((_QWORD *)this + 10);
      if ( *(_QWORD *)(v7 + v6 + 32) )
        return (struct CAsyncOperation *)(v6 + v7);
      *(_DWORD *)(v7 + v6 + 44) = 0;
      return 0;
    }
  }
LABEL_13:
  ReleaseMutex(*((HANDLE *)this + 9));
  CUnbufferedWriter::ProcessCompletions(this, -1);
  WaitForSingleObjectEx(*((HANDLE *)this + 9), 0xFFFFFFFF, 1);
  v8 = *((_QWORD *)this + 10);
  for ( k = 0; ; k = (unsigned int)(k + 1) )
  {
    if ( (unsigned int)k >= *((_DWORD *)this + 11) )
      goto LABEL_13;
    if ( !*(_DWORD *)(48 * k + v8 + 44) )
      break;
  }
  *(_DWORD *)(v8 + 44) = 1;
  *(_DWORD *)(*((_QWORD *)this + 10) + 40LL) = 0;
  return (struct CAsyncOperation *)(48 * k + *((_QWORD *)this + 10));
}

```

## disassembly

```asm
0x18000cc7c  mov     [rsp+arg_0], rbx
0x18000cc81  push    rdi
0x18000cc82  sub     rsp, 20h
0x18000cc86  mov     rdi, rcx
0x18000cc89  xor     edx, edx
0x18000cc8b  cmp     edx, [rdi+2Ch]
0x18000cc8e  jnb     short loc_18000CCAD
0x18000cc90  mov     rax, [rdi+50h]
0x18000cc94  lea     rcx, [rdx+rdx*2]
0x18000cc98  shl     rcx, 4
0x18000cc9c  add     rax, rcx
0x18000cc9f  cmp     dword ptr [rax+2Ch], 1
0x18000cca3  jz      loc_18000CD88
0x18000cca9  inc     edx
0x18000ccab  jmp     short loc_18000CC8B
0x18000ccad  xor     ecx, ecx
0x18000ccaf  cmp     ecx, [rdi+2Ch]
0x18000ccb2  jnb     short loc_18000CD26
0x18000ccb4  mov     rax, [rdi+50h]
0x18000ccb8  lea     rbx, [rcx+rcx*2]
0x18000ccbc  shl     rbx, 4
0x18000ccc0  cmp     dword ptr [rax+rbx+2Ch], 0
0x18000ccc5  jz      short loc_18000CCCB
0x18000ccc7  inc     ecx
0x18000ccc9  jmp     short loc_18000CCAF
0x18000cccb  mov     dword ptr [rax+rbx+2Ch], 1
0x18000ccd3  mov     rax, [rdi+50h]
0x18000ccd7  mov     dword ptr [rax+rbx+28h], 0
0x18000ccdf  mov     rax, [rdi+50h]
0x18000cce3  cmp     qword ptr [rax+rbx+20h], 0
0x18000cce9  jnz     short loc_18000CD21
0x18000cceb  mov     edx, [rdi+28h]; dwSize
0x18000ccee  xor     ecx, ecx; lpAddress
0x18000ccf0  mov     r8d, 1000h; flAllocationType
0x18000ccf6  lea     r9d, [rcx+4]; flProtect
0x18000ccfa  call    cs:__imp_VirtualAlloc
0x18000cd00  mov     rcx, [rdi+50h]
0x18000cd04  mov     [rcx+rbx+20h], rax
0x18000cd09  mov     rax, [rdi+50h]
0x18000cd0d  cmp     qword ptr [rax+rbx+20h], 0
0x18000cd13  jnz     short loc_18000CD21
0x18000cd15  mov     dword ptr [rax+rbx+2Ch], 0
0x18000cd1d  xor     eax, eax
0x18000cd1f  jmp     short loc_18000CD88
0x18000cd21  add     rax, rbx
0x18000cd24  jmp     short loc_18000CD88
0x18000cd26  or      ebx, 0FFFFFFFFh
0x18000cd29  mov     rcx, [rdi+48h]; hMutex
0x18000cd2d  call    cs:__imp_ReleaseMutex
0x18000cd33  mov     edx, ebx; unsigned int
0x18000cd35  mov     rcx, rdi; this
0x18000cd38  call    ?ProcessCompletions@CUnbufferedWriter@@QEAAXK@Z; CUnbufferedWriter::ProcessCompletions(ulong)
0x18000cd3d  mov     rcx, [rdi+48h]; hHandle
0x18000cd41  mov     r8d, 1; bAlertable
0x18000cd47  mov     edx, ebx; dwMilliseconds
0x18000cd49  call    cs:__imp_WaitForSingleObjectEx
0x18000cd4f  mov     r8, [rdi+50h]
0x18000cd53  xor     edx, edx
0x18000cd55  cmp     edx, [rdi+2Ch]
0x18000cd58  jnb     short loc_18000CD29
0x18000cd5a  lea     rcx, [rdx+rdx*2]
0x18000cd5e  shl     rcx, 4
0x18000cd62  cmp     dword ptr [rcx+r8+2Ch], 0
0x18000cd68  jz      short loc_18000CD6E
0x18000cd6a  inc     edx
0x18000cd6c  jmp     short loc_18000CD55
0x18000cd6e  mov     dword ptr [r8+2Ch], 1
0x18000cd76  mov     rax, [rdi+50h]
0x18000cd7a  mov     dword ptr [rax+28h], 0
0x18000cd81  mov     rax, [rdi+50h]
0x18000cd85  add     rax, rcx
0x18000cd88  mov     rbx, [rsp+28h+arg_0]
0x18000cd8d  add     rsp, 20h
0x18000cd91  pop     rdi
0x18000cd92  retn
```
