# CASFStreamPropertiesObjectEx::AddDataUnitExtensionSystem(_GUID,ushort,uchar *,ulong)

- ea: `0x180017588`
- end: `0x1800176d7`
- name: `?AddDataUnitExtensionSystem@CASFStreamPropertiesObjectEx@@QEAAJU_GUID@@GPEAEK@Z`
- size: `335`
- prototype: `int(CASFStreamPropertiesObjectEx *__hidden this, struct _GUID *__struct_ptr, unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18001a4e0`

## callees

- `0x180001194`
- `0x1800011a0`
- `0x1800011ec`
- `0x18001666c`
- `0x1800174b4`
- `0x180017588`
- `0x18001feb0`
- `0x18002a070`

## pseudocode

```c
__int64 __fastcall CASFStreamPropertiesObjectEx::AddDataUnitExtensionSystem(
        CASFStreamPropertiesObjectEx *this,
        struct _GUID *a2,
        __int16 a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  unsigned __int16 v9; // bx
  char *v10; // rdi
  unsigned int v11; // ebp
  _QWORD *v12; // rax
  __int64 v13; // rcx
  int v14; // ebx
  char *v15; // rax
  char *v16; // rbx
  unsigned int v17; // edi
  __int128 v18; // xmm0
  void *v19; // rax
  void *v20; // rcx

  if ( !a4 && Size )
    return 2147942487LL;
  v9 = 0;
  v10 = (char *)this + 360;
  while ( 1 )
  {
    v11 = v9;
    if ( (unsigned int)v9 >= *((_DWORD *)v10 + 54) )
      break;
    v12 = (_QWORD *)CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::operator[](v10, v9);
    v13 = *(_QWORD *)&a2->Data1 - *v12;
    if ( *(_QWORD *)&a2->Data1 == *v12 )
      v13 = *(_QWORD *)a2->Data4 - v12[1];
    if ( !v13 )
    {
      if ( (unsigned int)v9 + 1 <= *((_DWORD *)v10 + 54) )
      {
        v14 = 0;
        do
        {
          if ( (int)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::RemoveValue(
                      v10,
                      v11) < 0 )
            break;
          --*((_DWORD *)v10 + 54);
          ++v14;
        }
        while ( !v14 );
      }
      break;
    }
    ++v9;
  }
  v15 = (char *)operator new(0x1Eu);
  v16 = v15;
  if ( v15 )
  {
    v18 = (__int128)*a2;
    *((_WORD *)v15 + 8) = a3;
    *(_OWORD *)v15 = v18;
    if ( Size )
    {
      v19 = operator new[](Size);
      *(_QWORD *)(v16 + 18) = v19;
      if ( !v19 )
      {
        v17 = -2147024882;
        goto LABEL_23;
      }
      memcpy_0(v19, a4, Size);
    }
    else
    {
      *(_QWORD *)(v15 + 18) = 0;
    }
    *(_DWORD *)(v16 + 26) = Size;
    if ( (unsigned int)CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::Add(v10, v16) )
      return 0;
    v17 = -2147467259;
LABEL_23:
    v20 = *(void **)(v16 + 18);
    if ( v20 )
    {
      operator delete(v20);
      *(_QWORD *)(v16 + 18) = 0;
    }
    operator delete(v16);
    return v17;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180017588  mov     [rsp+arg_8], rbx
0x18001758d  push    rbp
0x18001758e  push    rsi
0x18001758f  push    rdi
0x180017590  push    r12
0x180017592  push    r13
0x180017594  push    r14
0x180017596  push    r15
0x180017598  sub     rsp, 20h
0x18001759c  mov     esi, dword ptr [rsp+58h+Size]
0x1800175a3  mov     r15, r9
0x1800175a6  movzx   r12d, r8w
0x1800175aa  mov     r14, rdx
0x1800175ad  test    r9, r9
0x1800175b0  jnz     short loc_1800175C0
0x1800175b2  test    esi, esi
0x1800175b4  jz      short loc_1800175C0
0x1800175b6  mov     eax, 80070057h
0x1800175bb  jmp     loc_1800176C2
0x1800175c0  xor     ebx, ebx
0x1800175c2  lea     rdi, [rcx+168h]
0x1800175c9  lea     r13d, [rbx+1]
0x1800175cd  movzx   ebp, bx
0x1800175d0  cmp     ebp, [rdi+0D8h]
0x1800175d6  jnb     short loc_180017626
0x1800175d8  mov     edx, ebp
0x1800175da  mov     rcx, rdi
0x1800175dd  call    ??A?$CTPtrArray@U_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@@@QEBAPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@K@Z; CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::operator[](ulong)
0x1800175e2  mov     rcx, [r14]
0x1800175e5  sub     rcx, [rax]
0x1800175e8  jnz     short loc_1800175F2
0x1800175ea  mov     rcx, [r14+8]
0x1800175ee  sub     rcx, [rax+8]
0x1800175f2  test    rcx, rcx
0x1800175f5  jz      short loc_1800175FD
0x1800175f7  add     bx, r13w
0x1800175fb  jmp     short loc_1800175CD
0x1800175fd  lea     eax, [rbp+1]
0x180017600  cmp     eax, [rdi+0D8h]
0x180017606  ja      short loc_180017626
0x180017608  xor     ebx, ebx
0x18001760a  mov     edx, ebp
0x18001760c  mov     rcx, rdi
0x18001760f  call    ?RemoveValue@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@QEAAJK@Z; CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::RemoveValue(ulong)
0x180017614  test    eax, eax
0x180017616  js      short loc_180017626
0x180017618  dec     dword ptr [rdi+0D8h]
0x18001761e  add     ebx, r13d
0x180017621  cmp     ebx, r13d
0x180017624  jb      short loc_18001760A
0x180017626  mov     r13d, 1Eh
0x18001762c  mov     ecx, r13d; Size
0x18001762f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017634  mov     rbx, rax
0x180017637  test    rax, rax
0x18001763a  jnz     short loc_180017643
0x18001763c  mov     edi, 8007000Eh
0x180017641  jmp     short loc_1800176C0
0x180017643  movaps  xmm0, xmmword ptr [r14]
0x180017647  mov     [rax+10h], r12w
0x18001764c  movdqu  xmmword ptr [rax], xmm0
0x180017650  test    esi, esi
0x180017652  jz      short loc_18001767C
0x180017654  mov     rcx, rsi; unsigned __int64
0x180017657  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001765c  mov     [rbx+12h], rax
0x180017660  test    rax, rax
0x180017663  jnz     short loc_18001766C
0x180017665  mov     edi, 8007000Eh
0x18001766a  jmp     short loc_18001769B
0x18001766c  mov     r8, rsi; Size
0x18001766f  mov     rdx, r15; Src
0x180017672  mov     rcx, rax; void *
0x180017675  call    memcpy_0
0x18001767a  jmp     short loc_180017684
0x18001767c  mov     qword ptr [rax+12h], 0
0x180017684  mov     rdx, rbx
0x180017687  mov     [rbx+1Ah], esi
0x18001768a  mov     rcx, rdi
0x18001768d  call    ?Add@?$CTPtrArray@U_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@@@QEAAHPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@PEAK@Z; CTPtrArray<CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD,20>::Add(CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,ulong *)
0x180017692  test    eax, eax
0x180017694  jnz     short loc_1800176BE
0x180017696  mov     edi, 80004005h
0x18001769b  mov     rcx, [rbx+12h]; void *
0x18001769f  test    rcx, rcx
0x1800176a2  jz      short loc_1800176B1
0x1800176a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800176a9  mov     qword ptr [rbx+12h], 0
0x1800176b1  mov     rdx, r13; unsigned __int64
0x1800176b4  mov     rcx, rbx; void *
0x1800176b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800176bc  jmp     short loc_1800176C0
0x1800176be  xor     edi, edi
0x1800176c0  mov     eax, edi
0x1800176c2  mov     rbx, [rsp+58h+arg_8]
0x1800176c7  add     rsp, 20h
0x1800176cb  pop     r15
0x1800176cd  pop     r14
0x1800176cf  pop     r13
0x1800176d1  pop     r12
0x1800176d3  pop     rdi
0x1800176d4  pop     rsi
0x1800176d5  pop     rbp
0x1800176d6  retn
```
