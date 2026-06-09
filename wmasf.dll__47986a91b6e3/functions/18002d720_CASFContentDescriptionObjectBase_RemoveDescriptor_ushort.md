# CASFContentDescriptionObjectBase::RemoveDescriptor(ushort)

- ea: `0x18002d720`
- end: `0x18002d7b5`
- name: `?RemoveDescriptor@CASFContentDescriptionObjectBase@@UEAAJG@Z`
- size: `149`
- prototype: `__int64 __fastcall(CASFContentDescriptionObjectBase *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x18002d44c`
- `0x18002d6bc`
- `0x18002d720`

## pseudocode

```c
__int64 __fastcall CASFContentDescriptionObjectBase::RemoveDescriptor(
        struct IWMSCriticalSection **this,
        unsigned __int16 a2)
{
  unsigned int v2; // ebx
  unsigned int v4; // ebx
  unsigned int v5; // esi
  __int64 Ptr; // rax
  __int64 v7; // rbx
  void *v8; // rcx
  char v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v10, this[4]);
  if ( this[5] )
  {
    v5 = v2;
    if ( v2 < *((_DWORD *)this + 158) )
    {
      Ptr = CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::GetPtr(this + 10, v2);
      v7 = Ptr;
      if ( Ptr )
      {
        v8 = *(void **)(Ptr + 8);
        if ( v8 )
          operator delete(v8);
        operator delete(*(void **)(v7 + 16));
      }
      CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::RemoveAt(this + 10, v5);
      v4 = 0;
    }
    else
    {
      v4 = -2147024809;
    }
  }
  else
  {
    v4 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v10);
  return v4;
}

```

## disassembly

```asm
0x18002d720  mov     [rsp+arg_8], rbx
0x18002d725  mov     [rsp+arg_10], rsi
0x18002d72a  push    rdi
0x18002d72b  sub     rsp, 20h
0x18002d72f  movzx   ebx, dx
0x18002d732  mov     rdi, rcx
0x18002d735  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002d739  lea     rcx, [rsp+28h+arg_0]; this
0x18002d73e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002d743  cmp     qword ptr [rdi+28h], 0
0x18002d748  jnz     short loc_18002D751
0x18002d74a  mov     ebx, 0C00D07F6h
0x18002d74f  jmp     short loc_18002D799
0x18002d751  mov     esi, ebx
0x18002d753  cmp     ebx, [rdi+278h]
0x18002d759  jb      short loc_18002D762
0x18002d75b  mov     ebx, 80070057h
0x18002d760  jmp     short loc_18002D799
0x18002d762  mov     edx, esi
0x18002d764  lea     rcx, [rdi+50h]
0x18002d768  call    ?GetPtr@?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEAAPEAUCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@K@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::GetPtr(ulong)
0x18002d76d  mov     rbx, rax
0x18002d770  test    rax, rax
0x18002d773  jz      short loc_18002D78C
0x18002d775  mov     rcx, [rax+8]; Block
0x18002d779  test    rcx, rcx
0x18002d77c  jz      short loc_18002D783
0x18002d77e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d783  mov     rcx, [rbx+10h]; Block
0x18002d787  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d78c  mov     edx, esi
0x18002d78e  lea     rcx, [rdi+50h]
0x18002d792  call    ?RemoveAt@?$CTDynArray@UCONTENT_DESCRIPTION_REC@CASFContentDescriptionObjectBase@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFContentDescriptionObjectBase::CONTENT_DESCRIPTION_REC,20>::RemoveAt(ulong,ulong)
0x18002d797  xor     ebx, ebx
0x18002d799  lea     rcx, [rsp+28h+arg_0]; this
0x18002d79e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002d7a3  mov     rsi, [rsp+28h+arg_10]
0x18002d7a8  mov     eax, ebx
0x18002d7aa  mov     rbx, [rsp+28h+arg_8]
0x18002d7af  add     rsp, 20h
0x18002d7b3  pop     rdi
0x18002d7b4  retn
```
