# DereferenceReflectorBlock

- ea: `0x180028eb4`
- end: `0x180028f87`
- name: `DereferenceReflectorBlock`
- size: `211`
- prototype: `void __fastcall(char *hMem)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025bf8`
- `0x180028f90`
- `0x180029134`

## callees

- `0x180028eb4`
- `0x1800295fc`

## import_xrefs

- `ntdll!NtClose` at `0x180028f29`
- `ntdll!NtClose` at `0x180028f29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028ef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028ef5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028eca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028eca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028f0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028f19`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028f19`
- `KERNEL32!LocalFree` at `0x180028f64`
- `KERNEL32!LocalFree` at `0x180028f76`
- `KERNEL32!LocalFree` at `0x180028f64`
- `KERNEL32!LocalFree` at `0x180028f76`

## pseudocode

```c
void __fastcall DereferenceReflectorBlock(char *hMem)
{
  __int64 v3; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  void *v7; // rcx
  _QWORD **v8; // rbx
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  _DWORD *v11; // rcx

  if ( (*(_DWORD *)hMem)-- == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_lq(v3, v5, v6, CurrentThreadId, hMem);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(hMem + 16));
    DeleteCriticalSection((LPCRITICAL_SECTION)(hMem + 16));
    v7 = (void *)*((_QWORD *)hMem + 1);
    if ( v7 != (void *)-1LL )
    {
      NtClose(v7);
      *((_QWORD *)hMem + 1) = -1;
    }
    v8 = (_QWORD **)(hMem + 104);
    while ( 1 )
    {
      v9 = *v8;
      if ( *v8 == v8 )
        break;
      if ( (_QWORD **)v9[1] != v8 || (v10 = (_QWORD *)*v9, *(_QWORD **)(*v9 + 8LL) != v9) )
        __fastfail(3u);
      *v8 = v10;
      v11 = v9 - 2;
      v10[1] = v8;
      v11[8] = 0;
      LocalFree(v11);
    }
    LocalFree(hMem);
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(hMem + 16));
  }
}

```

## disassembly

```asm
0x180028eb4  mov     [rsp+arg_8], rbx
0x180028eb9  push    rdi
0x180028eba  sub     rsp, 30h
0x180028ebe  add     dword ptr [rcx], 0FFFFFFFFh
0x180028ec1  mov     rdi, rcx
0x180028ec4  jz      short loc_180028ED5
0x180028ec6  add     rcx, 10h; lpCriticalSection
0x180028eca  call    cs:__imp_LeaveCriticalSection
0x180028ed0  jmp     loc_180028F7C
0x180028ed5  mov     rbx, cs:WPP_GLOBAL_Control
0x180028edc  lea     rax, WPP_GLOBAL_Control
0x180028ee3  cmp     rbx, rax
0x180028ee6  jz      short loc_180028F0B
0x180028ee8  test    dword ptr [rbx+1Ch], 1000h
0x180028eef  jz      short loc_180028F0B
0x180028ef1  mov     rbx, [rbx+10h]
0x180028ef5  call    cs:__imp_GetCurrentThreadId
0x180028efb  mov     rcx, rbx
0x180028efe  mov     [rsp+38h+var_18], rdi
0x180028f03  mov     r9d, eax
0x180028f06  call    WPP_SF_lq
0x180028f0b  lea     rcx, [rdi+10h]; lpCriticalSection
0x180028f0f  call    cs:__imp_LeaveCriticalSection
0x180028f15  lea     rcx, [rdi+10h]; lpCriticalSection
0x180028f19  call    cs:__imp_DeleteCriticalSection
0x180028f1f  mov     rcx, [rdi+8]; Handle
0x180028f23  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180028f27  jz      short loc_180028F37
0x180028f29  call    cs:__imp_NtClose
0x180028f2f  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x180028f37  lea     rbx, [rdi+68h]
0x180028f3b  mov     rcx, [rbx]
0x180028f3e  cmp     rcx, rbx
0x180028f41  jz      short loc_180028F73
0x180028f43  cmp     [rcx+8], rbx
0x180028f47  jnz     short loc_180028F6C
0x180028f49  mov     rax, [rcx]
0x180028f4c  cmp     [rax+8], rcx
0x180028f50  jnz     short loc_180028F6C
0x180028f52  mov     [rbx], rax
0x180028f55  add     rcx, 0FFFFFFFFFFFFFFF0h; hMem
0x180028f59  mov     [rax+8], rbx
0x180028f5d  mov     dword ptr [rcx+20h], 0
0x180028f64  call    cs:__imp_LocalFree
0x180028f6a  jmp     short loc_180028F3B
0x180028f6c  mov     ecx, 3
0x180028f71  int     29h; Win8: RtlFailFast(ecx)
0x180028f73  mov     rcx, rdi; hMem
0x180028f76  call    cs:__imp_LocalFree
0x180028f7c  mov     rbx, [rsp+38h+arg_8]
0x180028f81  add     rsp, 30h
0x180028f85  pop     rdi
0x180028f86  retn
```
