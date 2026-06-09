# CASFMutualExclusionObjectBase::RemoveAll(void)

- ea: `0x1800239f0`
- end: `0x180023b12`
- name: `?RemoveAll@CASFMutualExclusionObjectBase@@UEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(CASFMutualExclusionObjectBase *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800049b8`
- `0x18000d138`
- `0x18001dc98`
- `0x180022510`
- `0x18002257c`
- `0x1800225b0`
- `0x1800239f0`

## pseudocode

```c
__int64 __fastcall CASFMutualExclusionObjectBase::RemoveAll(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int i; // ebp
  unsigned int v4; // r14d
  CASFMutualExclusionObjectBase::EXCLUSION_REC *v5; // rsi
  __int64 v6; // rax
  unsigned int v7; // edx
  unsigned int v8; // ebx
  __int64 v9; // rax
  _BYTE v11[72]; // [rsp+20h] [rbp-48h] BYREF
  char v12; // [rsp+70h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v12, this[4]);
  if ( this[5] )
  {
    for ( i = 0; i < *((_DWORD *)this + 74); ++i )
    {
      v4 = 0;
      v5 = (CASFMutualExclusionObjectBase::EXCLUSION_REC *)CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](
                                                             this + 10,
                                                             i);
      if ( *((_DWORD *)v5 + 120) )
      {
        do
        {
          v6 = CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[]((char *)v5 + 96, v11, v4);
          operator delete(*(void **)(v6 + 8));
          ++v4;
        }
        while ( v4 < *((_DWORD *)v5 + 120) );
      }
      CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList((char *)v5 + 96);
      *((_DWORD *)v5 + 120) = 0;
      CTSparseBlock<unsigned long,unsigned short,20,0>::FreeList(v5);
      *((_DWORD *)v5 + 22) = 0;
      CASFMutualExclusionObjectBase::EXCLUSION_REC::`scalar deleting destructor'(v5, v7);
    }
    CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)(this + 10));
    v8 = 0;
    for ( *((_DWORD *)this + 74) = 0; v8 < *((_DWORD *)this + 172); ++v8 )
    {
      v9 = CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](this + 38, v11, v8);
      operator delete(*(void **)(v9 + 8));
    }
    CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList(this + 38);
    v2 = 0;
    *((_DWORD *)this + 172) = 0;
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v12);
  return v2;
}

```

## disassembly

```asm
0x1800239f0  push    rbx
0x1800239f2  push    rbp
0x1800239f3  push    rsi
0x1800239f4  push    rdi
0x1800239f5  push    r14
0x1800239f7  push    r15
0x1800239f9  sub     rsp, 38h
0x1800239fd  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180023a01  mov     rdi, rcx
0x180023a04  lea     rcx, [rsp+68h+arg_0]; this
0x180023a09  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180023a0e  cmp     qword ptr [rdi+28h], 0
0x180023a13  jnz     short loc_180023A1F
0x180023a15  mov     ebx, 0C00D07F6h
0x180023a1a  jmp     loc_180023AF9
0x180023a1f  xor     ebp, ebp
0x180023a21  cmp     [rdi+128h], ebp
0x180023a27  jbe     short loc_180023A9D
0x180023a29  mov     edx, ebp
0x180023a2b  lea     rcx, [rdi+50h]
0x180023a2f  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180023a34  xor     r14d, r14d
0x180023a37  mov     rsi, rax
0x180023a3a  cmp     [rax+1E0h], r14d
0x180023a41  jbe     short loc_180023A69
0x180023a43  mov     r8d, r14d
0x180023a46  lea     rdx, [rsp+68h+var_48]
0x180023a4b  lea     rcx, [rsi+60h]
0x180023a4f  call    ??A?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBA?AUNAME_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](ulong)
0x180023a54  mov     rcx, [rax+8]; Block
0x180023a58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023a5d  inc     r14d
0x180023a60  cmp     r14d, [rsi+1E0h]
0x180023a67  jb      short loc_180023A43
0x180023a69  lea     rcx, [rsi+60h]
0x180023a6d  call    ?FreeList@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList(int)
0x180023a72  mov     rcx, rsi
0x180023a75  mov     dword ptr [rsi+1E0h], 0
0x180023a7f  call    ?FreeList@?$CTSparseBlock@KG$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,ushort,20,0>::FreeList(int)
0x180023a84  mov     rcx, rsi; this
0x180023a87  mov     dword ptr [rsi+58h], 0
0x180023a8e  call    ??_GEXCLUSION_REC@CASFMutualExclusionObjectBase@@QEAAPEAXI@Z; CASFMutualExclusionObjectBase::EXCLUSION_REC::`scalar deleting destructor'(uint)
0x180023a93  inc     ebp
0x180023a95  cmp     ebp, [rdi+128h]
0x180023a9b  jb      short loc_180023A29
0x180023a9d  lea     rcx, [rdi+50h]
0x180023aa1  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x180023aa6  xor     ebx, ebx
0x180023aa8  mov     dword ptr [rdi+128h], 0
0x180023ab2  cmp     [rdi+2B0h], ebx
0x180023ab8  jbe     short loc_180023AE1
0x180023aba  mov     r8d, ebx
0x180023abd  lea     rdx, [rsp+68h+var_48]
0x180023ac2  lea     rcx, [rdi+130h]
0x180023ac9  call    ??A?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBA?AUNAME_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](ulong)
0x180023ace  mov     rcx, [rax+8]; Block
0x180023ad2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023ad7  inc     ebx
0x180023ad9  cmp     ebx, [rdi+2B0h]
0x180023adf  jb      short loc_180023ABA
0x180023ae1  lea     rcx, [rdi+130h]
0x180023ae8  call    ?FreeList@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList(int)
0x180023aed  xor     ebx, ebx
0x180023aef  mov     dword ptr [rdi+2B0h], 0
0x180023af9  lea     rcx, [rsp+68h+arg_0]; this
0x180023afe  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023b03  mov     eax, ebx
0x180023b05  add     rsp, 38h
0x180023b09  pop     r15
0x180023b0b  pop     r14
0x180023b0d  pop     rdi
0x180023b0e  pop     rsi
0x180023b0f  pop     rbp
0x180023b10  pop     rbx
0x180023b11  retn
```
