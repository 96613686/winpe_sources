# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18000786c`
- end: `0x1800078c5`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ba4`

## callees

- `0x18000786c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007875`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007875`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(__int64 a1)
{
  DWORD CurrentThreadId; // ecx
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(a1 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
        result;
        result = *(_QWORD *)(result + 8) )
  {
    if ( *(_DWORD *)result == CurrentThreadId )
    {
      result += 16;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000786c  push    rbx
0x18000786e  sub     rsp, 20h
0x180007872  mov     rbx, rcx
0x180007875  call    cs:__imp_GetCurrentThreadId
0x18000787c  nop     dword ptr [rax+rax+00h]
0x180007881  mov     r9d, eax
0x180007884  mov     ecx, eax
0x180007886  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007890  shr     r9, 2
0x180007894  mul     r9
0x180007897  shr     rdx, 3
0x18000789b  lea     r8, [rdx+rdx*4]
0x18000789f  add     r8, r8
0x1800078a2  sub     r9, r8
0x1800078a5  mov     rax, [rbx+r9*8]
0x1800078a9  jmp     short loc_1800078B3
0x1800078ab  cmp     [rax], ecx
0x1800078ad  jz      short loc_1800078BF
0x1800078af  mov     rax, [rax+8]
0x1800078b3  test    rax, rax
0x1800078b6  jnz     short loc_1800078AB
0x1800078b8  add     rsp, 20h
0x1800078bc  pop     rbx
0x1800078bd  retn
0x1800078bf  add     rax, 10h
0x1800078c3  jmp     short loc_1800078B8
```
