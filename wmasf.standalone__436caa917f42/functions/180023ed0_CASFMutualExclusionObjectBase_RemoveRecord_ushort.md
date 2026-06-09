# CASFMutualExclusionObjectBase::RemoveRecord(ushort)

- ea: `0x180023ed0`
- end: `0x180023fba`
- name: `?RemoveRecord@CASFMutualExclusionObjectBase@@UEAAJG@Z`
- size: `234`
- prototype: `__int64 __fastcall(CASFMutualExclusionObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000d138`
- `0x18001dc98`
- `0x180022510`
- `0x18002257c`
- `0x1800225b0`
- `0x180023ed0`
- `0x1800241c8`

## pseudocode

```c
__int64 __fastcall CASFMutualExclusionObjectBase::RemoveRecord(struct IWMSCriticalSection **this, unsigned __int16 a2)
{
  unsigned int v2; // edi
  unsigned int v4; // ebx
  unsigned int v5; // esi
  char *v6; // rbp
  CASFMutualExclusionObjectBase::EXCLUSION_REC *v7; // rdi
  int v8; // ebx
  unsigned int i; // ebx
  __int64 v10; // rax
  unsigned int v11; // edx
  _BYTE v13[56]; // [rsp+20h] [rbp-38h] BYREF
  char v14; // [rsp+60h] [rbp+8h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v14, this[4]);
  if ( this[5] )
  {
    v5 = v2;
    if ( v2 < *((_DWORD *)this + 74) )
    {
      v6 = (char *)(this + 10);
      v7 = (CASFMutualExclusionObjectBase::EXCLUSION_REC *)CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](
                                                             this + 10,
                                                             v2);
      if ( v5 + 1 <= *((_DWORD *)this + 74) )
      {
        v8 = 0;
        do
        {
          if ( (int)CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::RemoveValue(
                      v6,
                      v5) < 0 )
            break;
          --*((_DWORD *)v6 + 54);
          ++v8;
        }
        while ( !v8 );
      }
      for ( i = 0; i < *((_DWORD *)v7 + 120); ++i )
      {
        v10 = CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[]((char *)v7 + 96, v13, i);
        operator delete(*(void **)(v10 + 8));
      }
      CTSparseBlock<unsigned long,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList((char *)v7 + 96);
      *((_DWORD *)v7 + 120) = 0;
      CTSparseBlock<unsigned long,unsigned short,20,0>::FreeList(v7);
      *((_DWORD *)v7 + 22) = 0;
      CASFMutualExclusionObjectBase::EXCLUSION_REC::`scalar deleting destructor'(v7, v11);
      v4 = 0;
    }
    else
    {
      v4 = -1072887824;
    }
  }
  else
  {
    v4 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v14);
  return v4;
}

```

## disassembly

```asm
0x180023ed0  push    rbx
0x180023ed2  push    rbp
0x180023ed3  push    rsi
0x180023ed4  push    rdi
0x180023ed5  sub     rsp, 38h
0x180023ed9  movzx   edi, dx
0x180023edc  mov     rbx, rcx
0x180023edf  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180023ee3  lea     rcx, [rsp+58h+arg_0]; this
0x180023ee8  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180023eed  cmp     qword ptr [rbx+28h], 0
0x180023ef2  jnz     short loc_180023EFE
0x180023ef4  mov     ebx, 0C00D07F6h
0x180023ef9  jmp     loc_180023FA5
0x180023efe  mov     esi, edi
0x180023f00  cmp     edi, [rbx+128h]
0x180023f06  jb      short loc_180023F12
0x180023f08  mov     ebx, 0C00D07F0h
0x180023f0d  jmp     loc_180023FA5
0x180023f12  lea     rbp, [rbx+50h]
0x180023f16  mov     edx, esi
0x180023f18  mov     rcx, rbp
0x180023f1b  call    ??A?$CTDynArray@PEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBAPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::EXCLUSION_REC *,20>::operator[](ulong)
0x180023f20  mov     rdi, rax
0x180023f23  lea     eax, [rsi+1]
0x180023f26  cmp     eax, [rbp+0D8h]
0x180023f2c  ja      short loc_180023F4B
0x180023f2e  xor     ebx, ebx
0x180023f30  mov     edx, esi
0x180023f32  mov     rcx, rbp
0x180023f35  call    ?RemoveValue@?$CTSparseBlock@KPEAUEXCLUSION_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFMutualExclusionObjectBase::EXCLUSION_REC *,20,0>::RemoveValue(ulong)
0x180023f3a  test    eax, eax
0x180023f3c  js      short loc_180023F4B
0x180023f3e  dec     dword ptr [rbp+0D8h]
0x180023f44  inc     ebx
0x180023f46  cmp     ebx, 1
0x180023f49  jb      short loc_180023F30
0x180023f4b  xor     ebx, ebx
0x180023f4d  cmp     [rdi+1E0h], ebx
0x180023f53  jbe     short loc_180023F79
0x180023f55  mov     r8d, ebx
0x180023f58  lea     rdx, [rsp+58h+var_38]
0x180023f5d  lea     rcx, [rdi+60h]
0x180023f61  call    ??A?$CTDynArray@UNAME_REC@CASFMutualExclusionObjectBase@@$0BE@@@QEBA?AUNAME_REC@CASFMutualExclusionObjectBase@@K@Z; CTDynArray<CASFMutualExclusionObjectBase::NAME_REC,20>::operator[](ulong)
0x180023f66  mov     rcx, [rax+8]; Block
0x180023f6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023f6f  inc     ebx
0x180023f71  cmp     ebx, [rdi+1E0h]
0x180023f77  jb      short loc_180023F55
0x180023f79  lea     rcx, [rdi+60h]
0x180023f7d  call    ?FreeList@?$CTSparseBlock@KUNAME_REC@CASFMutualExclusionObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFMutualExclusionObjectBase::NAME_REC,20,0>::FreeList(int)
0x180023f82  mov     rcx, rdi
0x180023f85  mov     dword ptr [rdi+1E0h], 0
0x180023f8f  call    ?FreeList@?$CTSparseBlock@KG$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,ushort,20,0>::FreeList(int)
0x180023f94  mov     rcx, rdi; this
0x180023f97  mov     dword ptr [rdi+58h], 0
0x180023f9e  call    ??_GEXCLUSION_REC@CASFMutualExclusionObjectBase@@QEAAPEAXI@Z; CASFMutualExclusionObjectBase::EXCLUSION_REC::`scalar deleting destructor'(uint)
0x180023fa3  xor     ebx, ebx
0x180023fa5  lea     rcx, [rsp+58h+arg_0]; this
0x180023faa  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180023faf  mov     eax, ebx
0x180023fb1  add     rsp, 38h
0x180023fb5  pop     rdi
0x180023fb6  pop     rsi
0x180023fb7  pop     rbp
0x180023fb8  pop     rbx
0x180023fb9  retn
```
