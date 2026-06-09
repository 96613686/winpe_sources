# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800185dc`
- end: `0x18001862e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800188ec`

## callees

- `0x1800185dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800185e5`

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
0x1800185dc  push    rbx
0x1800185de  sub     rsp, 20h
0x1800185e2  mov     rbx, rcx
0x1800185e5  call    cs:__imp_GetCurrentThreadId
0x1800185eb  mov     r9d, eax
0x1800185ee  mov     ecx, eax
0x1800185f0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800185fa  shr     r9, 2
0x1800185fe  mul     r9
0x180018601  shr     rdx, 3
0x180018605  lea     r8, [rdx+rdx*4]
0x180018609  add     r8, r8
0x18001860c  sub     r9, r8
0x18001860f  mov     rax, [rbx+r9*8]
0x180018613  jmp     short loc_18001861D
0x180018615  cmp     [rax], ecx
0x180018617  jz      short loc_180018628
0x180018619  mov     rax, [rax+8]
0x18001861d  test    rax, rax
0x180018620  jnz     short loc_180018615
0x180018622  add     rsp, 20h
0x180018626  pop     rbx
0x180018627  retn
0x180018628  add     rax, 10h
0x18001862c  jmp     short loc_180018622
```
