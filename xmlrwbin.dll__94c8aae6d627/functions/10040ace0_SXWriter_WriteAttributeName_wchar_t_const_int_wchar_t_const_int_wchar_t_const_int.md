# SXWriter::WriteAttributeName(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x10040ace0`
- end: `0x10040ad9b`
- name: `?WriteAttributeName@SXWriter@@AEAAXPEB_WH0H0H@Z`
- size: `187`
- prototype: `void __usercall(SXWriter *__hidden this@<rcx>, const wchar_t *@<rdx>, int@<r8d>, const wchar_t *@<r9>, int, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x10040ab90`
- `0x10040ac70`

## callees

- `0x100407330`
- `0x1004086f0`
- `0x100409840`
- `0x100409da0`
- `0x10040ace0`

## pseudocode

```c
void __fastcall SXWriter::WriteAttributeName(
        SXWriter *this,
        wchar_t *a2,
        int a3,
        wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7)
{
  unsigned int v8; // eax
  _BYTE *v9; // rax
  unsigned int v10; // edx
  __int128 v11; // [rsp+50h] [rbp-38h] BYREF
  __int64 v12; // [rsp+60h] [rbp-28h]

  if ( a5 <= 0 || a7 <= a5 )
    v8 = a7 - a5;
  else
    v8 = a7 - a5 - 1;
  v12 = 0;
  v11 = 0;
  SXWriter::getUnitokenFromNames(this, a2, a3, a6, v8, a4, a5, (unsigned int *)&a5, (struct Unitoken *)&v11);
  v9 = (_BYTE *)*((_QWORD *)this + 38);
  if ( v9 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v9 = (_BYTE *)*((_QWORD *)this + 38);
  }
  v10 = a5;
  *v9 = -10;
  ++*((_QWORD *)this + 38);
  SXWriter::WriteMb32(this, v10);
  WriterHandleEntry::~WriterHandleEntry((WriterHandleEntry *)&v11);
}

```

## disassembly

```asm
0x10040ace0  push    rbx
0x10040ace2  sub     rsp, 80h
0x10040ace9  mov     eax, [rsp+88h+arg_30]
0x10040acf0  mov     rbx, rcx
0x10040acf3  mov     ecx, [rsp+88h+arg_20]
0x10040acfa  test    ecx, ecx
0x10040acfc  jle     short loc_10040AD08
0x10040acfe  cmp     eax, ecx
0x10040ad00  jle     short loc_10040AD08
0x10040ad02  sub     eax, ecx
0x10040ad04  dec     eax
0x10040ad06  jmp     short loc_10040AD0A
0x10040ad08  sub     eax, ecx
0x10040ad0a  lea     r10, [rsp+88h+var_38]
0x10040ad0f  mov     [rsp+88h+var_28], 0
0x10040ad18  mov     [rsp+88h+var_48], r10; struct Unitoken *
0x10040ad1d  xorps   xmm0, xmm0
0x10040ad20  lea     r10, [rsp+88h+arg_20]
0x10040ad28  mov     [rsp+88h+var_50], r10; unsigned int *
0x10040ad2d  mov     [rsp+88h+var_58], ecx; int
0x10040ad31  mov     rcx, rbx; this
0x10040ad34  mov     [rsp+88h+var_60], r9; wchar_t *
0x10040ad39  mov     r9, [rsp+88h+arg_28]; wchar_t *
0x10040ad41  movdqu  [rsp+88h+var_38], xmm0
0x10040ad47  mov     [rsp+88h+var_68], eax; int
0x10040ad4b  call    ?getUnitokenFromNames@SXWriter@@AEAAXPEB_WH0H0HPEAKPEAVUnitoken@@@Z; SXWriter::getUnitokenFromNames(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ulong *,Unitoken *)
0x10040ad50  mov     rax, [rbx+130h]
0x10040ad57  cmp     rax, [rbx+138h]
0x10040ad5e  jnz     short loc_10040AD6F
0x10040ad60  mov     rcx, rbx; this
0x10040ad63  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040ad68  mov     rax, [rbx+130h]
0x10040ad6f  mov     edx, [rsp+88h+arg_20]; unsigned int
0x10040ad76  mov     rcx, rbx; this
0x10040ad79  mov     byte ptr [rax], 0F6h
0x10040ad7c  inc     qword ptr [rbx+130h]
0x10040ad83  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x10040ad88  lea     rcx, [rsp+88h+var_38]; this
0x10040ad8d  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x10040ad92  add     rsp, 80h
0x10040ad99  pop     rbx
0x10040ad9a  retn
```
