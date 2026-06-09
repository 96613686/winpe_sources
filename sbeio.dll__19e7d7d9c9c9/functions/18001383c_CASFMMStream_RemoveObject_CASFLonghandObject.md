# CASFMMStream::RemoveObject(CASFLonghandObject *)

- ea: `0x18001383c`
- end: `0x180013910`
- name: `?RemoveObject@CASFMMStream@@QEAAJPEAVCASFLonghandObject@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(CASFMMStream *__hidden this, struct CASFLonghandObject *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011dc4`

## callees

- `0x18001383c`
- `0x18001fbac`
- `0x180029c00`

## pseudocode

```c
__int64 __fastcall CASFMMStream::RemoveObject(CASFMMStream *this, struct CASFLonghandObject *a2)
{
  CVPtrList *v4; // rdi
  unsigned int v5; // ecx
  CASFLonghandObject **i; // rax
  CASFLonghandObject **v7; // rbx

  if ( !a2 )
    return 2147942487LL;
  switch ( *((_DWORD *)a2 + 2) )
  {
    case 0x66:
      *((_QWORD *)this + 77) = 0;
      break;
    case 0x6D:
      *((_QWORD *)this + 78) = 0;
      break;
    case 0x76:
      *((_QWORD *)this + 79) = 0;
      break;
    case 0x77:
      *((_QWORD *)this + 80) = 0;
      break;
    case 0x7E:
      *((_QWORD *)this + 82) = 0;
      break;
    case 0x83:
      *((_QWORD *)this + 81) = 0;
      break;
  }
  v4 = (CASFMMStream *)((char *)this + 168);
  v5 = -2147467259;
  for ( i = (CASFLonghandObject **)*((_QWORD *)this + 74); ; i = (CASFLonghandObject **)i[1] )
  {
    v7 = i;
    if ( !i )
      break;
    if ( a2 == *i )
    {
      CASFLonghandObject::Release(*i);
      CVPtrList::RemoveAt(v4, v7);
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001383c  mov     [rsp+arg_0], rbx
0x180013841  push    rdi
0x180013842  sub     rsp, 20h
0x180013846  mov     r8, rcx
0x180013849  test    rdx, rdx
0x18001384c  jnz     short loc_180013858
0x18001384e  mov     eax, 80070057h
0x180013853  jmp     loc_180013905
0x180013858  mov     ecx, [rdx+8]
0x18001385b  sub     ecx, 66h ; 'f'
0x18001385e  jz      short loc_1800138BA
0x180013860  sub     ecx, 7
0x180013863  jz      short loc_1800138AD
0x180013865  sub     ecx, 9
0x180013868  jz      short loc_1800138A0
0x18001386a  sub     ecx, 1
0x18001386d  jz      short loc_180013893
0x18001386f  sub     ecx, 7
0x180013872  jz      short loc_180013886
0x180013874  cmp     ecx, 5
0x180013877  jnz     short loc_1800138C5
0x180013879  mov     qword ptr [r8+288h], 0
0x180013884  jmp     short loc_1800138C5
0x180013886  mov     qword ptr [r8+290h], 0
0x180013891  jmp     short loc_1800138C5
0x180013893  mov     qword ptr [r8+280h], 0
0x18001389e  jmp     short loc_1800138C5
0x1800138a0  mov     qword ptr [r8+278h], 0
0x1800138ab  jmp     short loc_1800138C5
0x1800138ad  mov     qword ptr [r8+270h], 0
0x1800138b8  jmp     short loc_1800138C5
0x1800138ba  mov     qword ptr [r8+268h], 0
0x1800138c5  lea     rdi, [r8+0A8h]
0x1800138cc  mov     ecx, 80004005h
0x1800138d1  mov     rax, [rdi+1A8h]
0x1800138d8  mov     rbx, rax
0x1800138db  test    rax, rax
0x1800138de  jz      short loc_180013903
0x1800138e0  mov     r8, [rax]
0x1800138e3  cmp     rdx, r8
0x1800138e6  jz      short loc_1800138EE
0x1800138e8  mov     rax, [rax+8]
0x1800138ec  jmp     short loc_1800138D8
0x1800138ee  mov     rcx, r8; this
0x1800138f1  call    ?Release@CASFLonghandObject@@QEAAKXZ; CASFLonghandObject::Release(void)
0x1800138f6  mov     rdx, rbx; void *
0x1800138f9  mov     rcx, rdi; this
0x1800138fc  call    ?RemoveAt@CVPtrList@@QEAAXPEAX@Z; CVPtrList::RemoveAt(void *)
0x180013901  xor     ecx, ecx
0x180013903  mov     eax, ecx
0x180013905  mov     rbx, [rsp+28h+arg_0]
0x18001390a  add     rsp, 20h
0x18001390e  pop     rdi
0x18001390f  retn
```
