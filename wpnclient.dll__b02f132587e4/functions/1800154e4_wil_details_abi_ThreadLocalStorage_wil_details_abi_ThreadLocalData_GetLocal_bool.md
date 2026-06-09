# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800154e4`
- end: `0x180015536`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014bcc`

## callees

- `0x1800154e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800154ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800154ed`

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
0x1800154e4  push    rbx
0x1800154e6  sub     rsp, 20h
0x1800154ea  mov     rbx, rcx
0x1800154ed  call    cs:__imp_GetCurrentThreadId
0x1800154f3  mov     r9d, eax
0x1800154f6  mov     ecx, eax
0x1800154f8  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180015502  shr     r9, 2
0x180015506  mul     r9
0x180015509  shr     rdx, 3
0x18001550d  lea     r8, [rdx+rdx*4]
0x180015511  add     r8, r8
0x180015514  sub     r9, r8
0x180015517  mov     rax, [rbx+r9*8]
0x18001551b  test    rax, rax
0x18001551e  jz      short loc_18001552E
0x180015520  cmp     [rax], ecx
0x180015522  jz      short loc_18001552A
0x180015524  mov     rax, [rax+8]
0x180015528  jmp     short loc_18001551B
0x18001552a  add     rax, 10h
0x18001552e  add     rsp, 20h
0x180015532  pop     rbx
0x180015533  retn
0x180015534  jmp     short loc_18001552E
```
