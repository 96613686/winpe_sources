# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800189ac`
- end: `0x1800189fe`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018eac`

## callees

- `0x1800189ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800189b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800189b5`

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
0x1800189ac  push    rbx
0x1800189ae  sub     rsp, 20h
0x1800189b2  mov     rbx, rcx
0x1800189b5  call    cs:__imp_GetCurrentThreadId
0x1800189bb  mov     r9d, eax
0x1800189be  mov     ecx, eax
0x1800189c0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800189ca  shr     r9, 2
0x1800189ce  mul     r9
0x1800189d1  shr     rdx, 3
0x1800189d5  lea     r8, [rdx+rdx*4]
0x1800189d9  add     r8, r8
0x1800189dc  sub     r9, r8
0x1800189df  mov     rax, [rbx+r9*8]
0x1800189e3  jmp     short loc_1800189ED
0x1800189e5  cmp     [rax], ecx
0x1800189e7  jz      short loc_1800189F8
0x1800189e9  mov     rax, [rax+8]
0x1800189ed  test    rax, rax
0x1800189f0  jnz     short loc_1800189E5
0x1800189f2  add     rsp, 20h
0x1800189f6  pop     rbx
0x1800189f7  retn
0x1800189f8  add     rax, 10h
0x1800189fc  jmp     short loc_1800189F2
```
