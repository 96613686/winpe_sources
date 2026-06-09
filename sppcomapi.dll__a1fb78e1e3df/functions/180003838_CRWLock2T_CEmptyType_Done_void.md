# CRWLock2T<CEmptyType>::Done(void)

- ea: `0x180003838`
- end: `0x18000389f`
- name: `?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180004950`
- `0x1800049e8`
- `0x180019b4c`
- `0x180019db0`
- `0x180019e48`
- `0x180019ee0`
- `0x180019f78`
- `0x18001a010`
- `0x18001b530`
- `0x18001b6cc`
- `0x18001b864`
- `0x18001ba44`
- `0x18001e0a8`
- `0x18001e3c8`
- `0x18001e460`
- `0x180020e90`
- `0x180038f90`

## callees

- `0x180003838`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003865`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003882`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000384a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000384a`

## pseudocode

```c
__int64 __fastcall CRWLock2T<CEmptyType>::Done(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( *(_DWORD *)a1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    *(_DWORD *)a1 = 0;
  }
  v2 = *(void **)(a1 + 56);
  if ( v2 )
  {
    CloseHandle(v2);
    *(_QWORD *)(a1 + 56) = 0;
  }
  v3 = *(void **)(a1 + 48);
  if ( v3 )
  {
    CloseHandle(v3);
    *(_QWORD *)(a1 + 48) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180003838  push    rbx
0x18000383a  sub     rsp, 20h
0x18000383e  cmp     dword ptr [rcx], 0
0x180003841  mov     rbx, rcx
0x180003844  jz      short loc_18000385C
0x180003846  add     rcx, 8; lpCriticalSection
0x18000384a  call    cs:__imp_DeleteCriticalSection
0x180003851  nop     dword ptr [rax+rax+00h]
0x180003856  mov     dword ptr [rbx], 0
0x18000385c  mov     rcx, [rbx+38h]; hObject
0x180003860  test    rcx, rcx
0x180003863  jz      short loc_180003879
0x180003865  call    cs:__imp_CloseHandle
0x18000386c  nop     dword ptr [rax+rax+00h]
0x180003871  mov     qword ptr [rbx+38h], 0
0x180003879  mov     rcx, [rbx+30h]; hObject
0x18000387d  test    rcx, rcx
0x180003880  jz      short loc_180003896
0x180003882  call    cs:__imp_CloseHandle
0x180003889  nop     dword ptr [rax+rax+00h]
0x18000388e  mov     qword ptr [rbx+30h], 0
0x180003896  xor     eax, eax
0x180003898  add     rsp, 20h
0x18000389c  pop     rbx
0x18000389d  retn
```
