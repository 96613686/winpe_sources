# CASFMetaDataObjectBase::RemoveAll(void)

- ea: `0x180025e50`
- end: `0x180025ef6`
- name: `?RemoveAll@CASFMetaDataObjectBase@@UEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x180024b8c`
- `0x180024e48`
- `0x180025e50`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::RemoveAll(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // edi
  unsigned int v4; // esi
  char *i; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  _BYTE v9[40]; // [rsp+20h] [rbp-28h] BYREF
  char v10; // [rsp+50h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v10, this[4]);
  if ( this[5] )
  {
    v3 = *((_DWORD *)this + 200);
    v4 = 0;
    for ( i = (char *)(this + 10); v4 < v3; ++v4 )
    {
      v6 = CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](i, v9, v4);
      operator delete(*(void **)(v6 + 8));
      v7 = CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](i, v9, v4);
      operator delete(*(void **)(v7 + 24));
    }
    CTSparseBlock<unsigned long,CASFMetaDataObjectBase::METADATA_REC,20,0>::FreeList(i);
    *((_DWORD *)i + 180) = 0;
    v2 = 0;
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
  return v2;
}

```

## disassembly

```asm
0x180025e50  mov     [rsp+arg_8], rbx
0x180025e55  mov     [rsp+arg_10], rsi
0x180025e5a  push    rdi
0x180025e5b  sub     rsp, 40h
0x180025e5f  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180025e63  mov     rbx, rcx
0x180025e66  lea     rcx, [rsp+48h+arg_0]; this
0x180025e6b  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180025e70  cmp     qword ptr [rbx+28h], 0
0x180025e75  jnz     short loc_180025E7E
0x180025e77  mov     ebx, 0C00D07F6h
0x180025e7c  jmp     short loc_180025EDA
0x180025e7e  mov     edi, [rbx+320h]
0x180025e84  xor     esi, esi
0x180025e86  add     rbx, 50h ; 'P'
0x180025e8a  test    edi, edi
0x180025e8c  jz      short loc_180025EC6
0x180025e8e  mov     r8d, esi
0x180025e91  lea     rdx, [rsp+48h+var_28]
0x180025e96  mov     rcx, rbx
0x180025e99  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180025e9e  mov     rcx, [rax+8]; Block
0x180025ea2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025ea7  mov     r8d, esi
0x180025eaa  lea     rdx, [rsp+48h+var_28]
0x180025eaf  mov     rcx, rbx
0x180025eb2  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180025eb7  mov     rcx, [rax+18h]; Block
0x180025ebb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025ec0  inc     esi
0x180025ec2  cmp     esi, edi
0x180025ec4  jb      short loc_180025E8E
0x180025ec6  mov     rcx, rbx
0x180025ec9  call    ?FreeList@?$CTSparseBlock@KUMETADATA_REC@CASFMetaDataObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFMetaDataObjectBase::METADATA_REC,20,0>::FreeList(int)
0x180025ece  mov     dword ptr [rbx+2D0h], 0
0x180025ed8  xor     ebx, ebx
0x180025eda  lea     rcx, [rsp+48h+arg_0]; this
0x180025edf  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180025ee4  mov     rsi, [rsp+48h+arg_10]
0x180025ee9  mov     eax, ebx
0x180025eeb  mov     rbx, [rsp+48h+arg_8]
0x180025ef0  add     rsp, 40h
0x180025ef4  pop     rdi
0x180025ef5  retn
```
