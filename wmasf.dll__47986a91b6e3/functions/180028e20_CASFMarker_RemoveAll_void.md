# CASFMarker::RemoveAll(void)

- ea: `0x180028e20`
- end: `0x180028eb6`
- name: `?RemoveAll@CASFMarker@@UEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(CASFMarker *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800049b8`
- `0x18000d138`
- `0x180027e50`
- `0x180028e20`

## pseudocode

```c
__int64 __fastcall CASFMarker::RemoveAll(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // ebp
  unsigned int i; // esi
  __int64 v5; // rax
  _BYTE v7[56]; // [rsp+20h] [rbp-38h] BYREF
  char v8; // [rsp+60h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v8, this[2]);
  if ( this[4] )
  {
    v3 = *((_DWORD *)this + 164);
    for ( i = 0; i < v3; ++i )
    {
      v5 = CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](this + 34, v7, i);
      operator delete(*(void **)(v5 + 8));
    }
    CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList(this + 34);
    *((_DWORD *)this + 164) = 0;
    CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)(this + 6));
    *((_DWORD *)this + 66) = 0;
    v2 = 0;
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v8);
  return v2;
}

```

## disassembly

```asm
0x180028e20  push    rbx
0x180028e22  push    rbp
0x180028e23  push    rsi
0x180028e24  push    rdi
0x180028e25  sub     rsp, 38h
0x180028e29  mov     rdx, [rcx+10h]; struct IWMSCriticalSection *
0x180028e2d  mov     rbx, rcx
0x180028e30  lea     rcx, [rsp+58h+arg_0]; this
0x180028e35  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180028e3a  cmp     qword ptr [rbx+20h], 0
0x180028e3f  jnz     short loc_180028E48
0x180028e41  mov     ebx, 0C00D07F6h
0x180028e46  jmp     short loc_180028EA1
0x180028e48  mov     ebp, [rbx+290h]
0x180028e4e  lea     rdi, [rbx+110h]
0x180028e55  xor     esi, esi
0x180028e57  test    ebp, ebp
0x180028e59  jz      short loc_180028E7A
0x180028e5b  mov     r8d, esi
0x180028e5e  lea     rdx, [rsp+58h+var_38]
0x180028e63  mov     rcx, rdi
0x180028e66  call    ??A?$CTDynArray@UMARKER_NAME_REC@CASFMarker@@$0BE@@@QEBA?AUMARKER_NAME_REC@CASFMarker@@K@Z; CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](ulong)
0x180028e6b  mov     rcx, [rax+8]; Block
0x180028e6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028e74  inc     esi
0x180028e76  cmp     esi, ebp
0x180028e78  jb      short loc_180028E5B
0x180028e7a  mov     rcx, rdi
0x180028e7d  call    ?FreeList@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList(int)
0x180028e82  lea     rcx, [rbx+30h]
0x180028e86  mov     dword ptr [rdi+180h], 0
0x180028e90  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x180028e95  mov     dword ptr [rbx+108h], 0
0x180028e9f  xor     ebx, ebx
0x180028ea1  lea     rcx, [rsp+58h+arg_0]; this
0x180028ea6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180028eab  mov     eax, ebx
0x180028ead  add     rsp, 38h
0x180028eb1  pop     rdi
0x180028eb2  pop     rsi
0x180028eb3  pop     rbp
0x180028eb4  pop     rbx
0x180028eb5  retn
```
