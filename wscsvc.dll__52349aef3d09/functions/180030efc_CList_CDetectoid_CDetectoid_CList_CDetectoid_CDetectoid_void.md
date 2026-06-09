# CList<CDetectoid *,CDetectoid *>::~CList<CDetectoid *,CDetectoid *>(void)

- ea: `0x180030efc`
- end: `0x180030f96`
- name: `??1?$CList@PEAVCDetectoid@@PEAV1@@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180029a84`
- `0x180038448`

## callees

- `0x180009f40`
- `0x180029e74`
- `0x180030efc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030f48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030f48`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030f7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030f7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030f27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030f27`

## pseudocode

```c
void __fastcall CList<CDetectoid *,CDetectoid *>::~CList<CDetectoid *,CDetectoid *>(__int64 a1)
{
  _QWORD **HeadPosition; // rdi
  struct _RTL_CRITICAL_SECTION *v3; // rsi

  if ( *(_DWORD *)a1 )
  {
    HeadPosition = (_QWORD **)((__int64 (*)(void))CList<unsigned short *,unsigned short *>::GetHeadPosition)();
    if ( HeadPosition )
    {
      do
      {
        v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
        *HeadPosition[1] = *HeadPosition;
        (*HeadPosition)[1] = HeadPosition[1];
        --*(_DWORD *)(a1 + 48);
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
        operator delete(HeadPosition);
        HeadPosition = (_QWORD **)CList<unsigned short *,unsigned short *>::GetHeadPosition(a1);
      }
      while ( HeadPosition );
    }
    else
    {
      v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
    }
    *(_QWORD *)(a1 + 56) = a1 + 56;
    *(_QWORD *)(a1 + 64) = a1 + 56;
    DeleteCriticalSection(v3);
    *(_DWORD *)a1 = 0;
  }
}

```

## disassembly

```asm
0x180030efc  mov     [rsp+arg_0], rbx
0x180030f01  mov     [rsp+arg_8], rsi
0x180030f06  push    rdi
0x180030f07  sub     rsp, 20h
0x180030f0b  cmp     dword ptr [rcx], 0
0x180030f0e  mov     rbx, rcx
0x180030f11  jz      short loc_180030F86
0x180030f13  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x180030f18  mov     rdi, rax
0x180030f1b  test    rax, rax
0x180030f1e  jz      short loc_180030F68
0x180030f20  lea     rsi, [rbx+8]
0x180030f24  mov     rcx, rsi; lpCriticalSection
0x180030f27  call    cs:__imp_EnterCriticalSection
0x180030f2d  mov     rcx, [rdi+8]
0x180030f31  mov     rax, [rdi]
0x180030f34  mov     [rcx], rax
0x180030f37  mov     rcx, [rdi]
0x180030f3a  mov     rax, [rdi+8]
0x180030f3e  mov     [rcx+8], rax
0x180030f42  mov     rcx, rsi; lpCriticalSection
0x180030f45  dec     dword ptr [rbx+30h]
0x180030f48  call    cs:__imp_LeaveCriticalSection
0x180030f4e  mov     rcx, rdi; Block
0x180030f51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180030f56  mov     rcx, rbx
0x180030f59  call    ?GetHeadPosition@?$CList@PEAGPEAG@@QEBAPEAU_CListElement@@XZ; CList<ushort *,ushort *>::GetHeadPosition(void)
0x180030f5e  mov     rdi, rax
0x180030f61  test    rax, rax
0x180030f64  jnz     short loc_180030F20
0x180030f66  jmp     short loc_180030F6C
0x180030f68  lea     rsi, [rbx+8]
0x180030f6c  lea     rax, [rbx+38h]
0x180030f70  mov     rcx, rsi; lpCriticalSection
0x180030f73  mov     [rax], rax
0x180030f76  mov     [rbx+40h], rax
0x180030f7a  call    cs:__imp_DeleteCriticalSection
0x180030f80  mov     dword ptr [rbx], 0
0x180030f86  mov     rbx, [rsp+28h+arg_0]
0x180030f8b  mov     rsi, [rsp+28h+arg_8]
0x180030f90  add     rsp, 20h
0x180030f94  pop     rdi
0x180030f95  retn
```
