# CASFMarker::RemoveMarkerNameByIndex(ushort)

- ea: `0x180029070`
- end: `0x1800290ef`
- name: `?RemoveMarkerNameByIndex@CASFMarker@@UEAAJG@Z`
- size: `127`
- prototype: `__int64 __fastcall(CASFMarker *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x180027e50`
- `0x180028ebc`
- `0x180029070`

## pseudocode

```c
__int64 __fastcall CASFMarker::RemoveMarkerNameByIndex(struct IWMSCriticalSection **this, unsigned __int16 a2)
{
  unsigned int v2; // edi
  unsigned int v4; // ebx
  __int64 v5; // rax
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp+8h] BYREF

  v2 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v8, this[2]);
  if ( this[4] )
  {
    if ( v2 < *((_DWORD *)this + 164) )
    {
      v5 = CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](this + 34, v7, v2);
      operator delete(*(void **)(v5 + 8));
      CTDynArray<CASFMarker::MARKER_NAME_REC,20>::RemoveAt(this + 34, v2);
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
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v8);
  return v4;
}

```

## disassembly

```asm
0x180029070  mov     [rsp+arg_8], rbx
0x180029075  push    rdi
0x180029076  sub     rsp, 30h
0x18002907a  movzx   edi, dx
0x18002907d  mov     rbx, rcx
0x180029080  mov     rdx, [rcx+10h]; struct IWMSCriticalSection *
0x180029084  lea     rcx, [rsp+38h+arg_0]; this
0x180029089  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002908e  cmp     qword ptr [rbx+20h], 0
0x180029093  jnz     short loc_18002909C
0x180029095  mov     ebx, 0C00D07F6h
0x18002909a  jmp     short loc_1800290D8
0x18002909c  cmp     edi, [rbx+290h]
0x1800290a2  jb      short loc_1800290AB
0x1800290a4  mov     ebx, 0C00D07F0h
0x1800290a9  jmp     short loc_1800290D8
0x1800290ab  mov     r8d, edi
0x1800290ae  lea     rdx, [rsp+38h+var_18]
0x1800290b3  lea     rcx, [rbx+110h]
0x1800290ba  call    ??A?$CTDynArray@UMARKER_NAME_REC@CASFMarker@@$0BE@@@QEBA?AUMARKER_NAME_REC@CASFMarker@@K@Z; CTDynArray<CASFMarker::MARKER_NAME_REC,20>::operator[](ulong)
0x1800290bf  mov     rcx, [rax+8]; Block
0x1800290c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800290c8  mov     edx, edi
0x1800290ca  lea     rcx, [rbx+110h]
0x1800290d1  call    ?RemoveAt@?$CTDynArray@UMARKER_NAME_REC@CASFMarker@@$0BE@@@QEAAHKK@Z; CTDynArray<CASFMarker::MARKER_NAME_REC,20>::RemoveAt(ulong,ulong)
0x1800290d6  xor     ebx, ebx
0x1800290d8  lea     rcx, [rsp+38h+arg_0]; this
0x1800290dd  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800290e2  mov     eax, ebx
0x1800290e4  mov     rbx, [rsp+38h+arg_8]
0x1800290e9  add     rsp, 30h
0x1800290ed  pop     rdi
0x1800290ee  retn
```
