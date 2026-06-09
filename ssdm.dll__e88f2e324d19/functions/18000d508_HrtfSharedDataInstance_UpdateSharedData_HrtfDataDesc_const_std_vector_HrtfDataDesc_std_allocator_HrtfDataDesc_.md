# HrtfSharedDataInstance::UpdateSharedData(HrtfDataDesc const &,std::vector<HrtfDataDesc,std::allocator<HrtfDataDesc>> const &)

- ea: `0x18000d508`
- end: `0x18000d5c8`
- name: `?UpdateSharedData@HrtfSharedDataInstance@@QEAAXAEBUHrtfDataDesc@@AEBV?$vector@UHrtfDataDesc@@V?$allocator@UHrtfDataDesc@@@std@@@std@@@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800054f8`

## callees

- `0x1800056e4`
- `0x18000d4a8`
- `0x18000d508`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000d5aa`

## pseudocode

```c
BOOL __fastcall HrtfSharedDataInstance::UpdateSharedData(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  const char *v5; // r9
  __int64 v7; // r8
  __int64 v8; // rsi
  void *v9; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = (const char *)(0x6DB6DB6DB6DB6DB7LL * ((__int64)(a3[1] - *a3) >> 3));
  if ( (const char *)((__int64)(*(_QWORD *)(a1 + 40) - *(_QWORD *)(a1 + 32)) >> 3) != v5 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x9D,
      (unsigned int)"avcore\\xaudio\\hrtf\\ssdm\\lib\\shareddatainstance.cpp",
      v5);
  SharedMemory::Update(*(_QWORD *)(a1 + 16), (__int64)(a2 + 8));
  v7 = *(_QWORD *)(a1 + 32);
  if ( (*(_QWORD *)(a1 + 40) - v7) >> 3 )
  {
    v8 = 0;
    do
    {
      SharedMemory::Update(*(_QWORD *)(v7 + 8 * v8), *a3 + 32LL + 56LL * (unsigned int)v8);
      v7 = *(_QWORD *)(a1 + 32);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < (unsigned __int64)((*(_QWORD *)(a1 + 40) - v7) >> 3) );
  }
  v9 = *(void **)a1;
  *(_DWORD *)(a1 + 8) = *a2;
  return SetEvent(v9);
}

```

## disassembly

```asm
0x18000d508  push    rbx
0x18000d50a  push    rsi
0x18000d50b  push    rdi
0x18000d50c  push    r14
0x18000d50e  sub     rsp, 28h
0x18000d512  mov     r9, [r8+8]
0x18000d516  mov     rax, 6DB6DB6DB6DB6DB7h
0x18000d520  sub     r9, [r8]
0x18000d523  mov     r14, r8
0x18000d526  sar     r9, 3
0x18000d52a  mov     rdi, rdx
0x18000d52d  imul    r9, rax; char *
0x18000d531  mov     rax, [rcx+28h]
0x18000d535  mov     rbx, rcx
0x18000d538  sub     rax, [rcx+20h]
0x18000d53c  sar     rax, 3
0x18000d540  cmp     rax, r9
0x18000d543  jnz     short loc_18000D5B1
0x18000d545  mov     rcx, [rcx+10h]
0x18000d549  add     rdx, 20h ; ' '
0x18000d54d  call    ?Update@SharedMemory@@QEAAXAEBV?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@@Z; SharedMemory::Update(std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>> const &)
0x18000d552  mov     r8, [rbx+20h]
0x18000d556  mov     rax, [rbx+28h]
0x18000d55a  sub     rax, r8
0x18000d55d  sar     rax, 3
0x18000d561  test    rax, rax
0x18000d564  jz      short loc_18000D599
0x18000d566  xor     esi, esi
0x18000d568  mov     rax, [r14]
0x18000d56b  mov     ecx, esi
0x18000d56d  add     rax, 20h ; ' '
0x18000d571  imul    rdx, rcx, 38h ; '8'
0x18000d575  mov     rcx, [r8+rsi*8]
0x18000d579  add     rdx, rax
0x18000d57c  call    ?Update@SharedMemory@@QEAAXAEBV?$vector@EV?$AlignedAllocator@E$0BA@@AlignedStore@@@std@@@Z; SharedMemory::Update(std::vector<uchar,AlignedStore::AlignedAllocator<uchar,16>> const &)
0x18000d581  mov     r8, [rbx+20h]
0x18000d585  inc     esi
0x18000d587  mov     rcx, [rbx+28h]
0x18000d58b  sub     rcx, r8
0x18000d58e  mov     eax, esi
0x18000d590  sar     rcx, 3
0x18000d594  cmp     rax, rcx
0x18000d597  jb      short loc_18000D568
0x18000d599  mov     eax, [rdi]
0x18000d59b  mov     rcx, [rbx]
0x18000d59e  mov     [rbx+8], eax
0x18000d5a1  add     rsp, 28h
0x18000d5a5  pop     r14
0x18000d5a7  pop     rdi
0x18000d5a8  pop     rsi
0x18000d5a9  pop     rbx
0x18000d5aa  jmp     cs:__imp_SetEvent
0x18000d5b1  mov     rcx, [rsp+48h]; this
0x18000d5b6  lea     r8, aAvcoreXaudioHr_2; "avcore\\xaudio\\hrtf\\ssdm\\lib\\shared"...
0x18000d5bd  mov     edx, 9Dh; void *
0x18000d5c2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
