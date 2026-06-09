# SXWriter::WriteQNameHandleData(QNAME_TRIPLE *)

- ea: `0x100409320`
- end: `0x1004093c0`
- name: `?WriteQNameHandleData@SXWriter@@AEAAXPEAUQNAME_TRIPLE@@@Z`
- size: `160`
- prototype: `void __fastcall(SXWriter *__hidden this, struct QNAME_TRIPLE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1004089c0`
- `0x1004093d0`

## callees

- `0x100407330`
- `0x1004086f0`
- `0x100409320`
- `0x100409840`
- `0x100409da0`

## pseudocode

```c
void __fastcall SXWriter::WriteQNameHandleData(SXWriter *this, struct QNAME_TRIPLE *a2)
{
  wchar_t *v2; // r9
  int v3; // r8d
  unsigned int v5; // eax
  wchar_t *v6; // rdx
  _BYTE *v7; // rax
  unsigned int v8; // edx
  wchar_t *v9; // [rsp+28h] [rbp-60h]
  unsigned int v10; // [rsp+30h] [rbp-58h]
  __int128 v11; // [rsp+50h] [rbp-38h] BYREF
  __int64 v12; // [rsp+60h] [rbp-28h]
  unsigned int v13; // [rsp+90h] [rbp+8h] BYREF

  v2 = (wchar_t *)*((_QWORD *)a2 + 2);
  v3 = *((_DWORD *)a2 + 2);
  v10 = *((_DWORD *)a2 + 10);
  v9 = (wchar_t *)*((_QWORD *)a2 + 4);
  v5 = *((_DWORD *)a2 + 6);
  v6 = *(wchar_t **)a2;
  v11 = 0;
  v12 = 0;
  SXWriter::getUnitokenFromNames(this, v6, v3, v2, v5, v9, v10, &v13, (struct Unitoken *)&v11);
  v7 = (_BYTE *)*((_QWORD *)this + 38);
  if ( v7 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v7 = (_BYTE *)*((_QWORD *)this + 38);
  }
  v8 = v13;
  *v7 = -116;
  ++*((_QWORD *)this + 38);
  SXWriter::WriteMb32(this, v8);
  WriterHandleEntry::~WriterHandleEntry((WriterHandleEntry *)&v11);
}

```

## disassembly

```asm
0x100409320  mov     r11, rsp
0x100409323  push    rbx
0x100409324  sub     rsp, 80h
0x10040932b  mov     r9, [rdx+10h]; wchar_t *
0x10040932f  lea     rax, [r11-38h]
0x100409333  mov     r8d, [rdx+8]; int
0x100409337  xorps   xmm0, xmm0
0x10040933a  mov     [r11-48h], rax
0x10040933e  mov     rbx, rcx
0x100409341  lea     rax, [r11+8]
0x100409345  mov     [r11-50h], rax
0x100409349  mov     eax, [rdx+28h]
0x10040934c  mov     [rsp+88h+var_58], eax; int
0x100409350  mov     rax, [rdx+20h]
0x100409354  mov     [r11-60h], rax
0x100409358  mov     eax, [rdx+18h]
0x10040935b  mov     rdx, [rdx]; wchar_t *
0x10040935e  movdqu  [rsp+88h+var_38], xmm0
0x100409364  mov     qword ptr [r11-28h], 0
0x10040936c  mov     [rsp+88h+var_68], eax; int
0x100409370  call    ?getUnitokenFromNames@SXWriter@@AEAAXPEB_WH0H0HPEAKPEAVUnitoken@@@Z; SXWriter::getUnitokenFromNames(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ulong *,Unitoken *)
0x100409375  mov     rax, [rbx+130h]
0x10040937c  cmp     rax, [rbx+138h]
0x100409383  jnz     short loc_100409394
0x100409385  mov     rcx, rbx; this
0x100409388  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040938d  mov     rax, [rbx+130h]
0x100409394  mov     edx, [rsp+88h+arg_0]; unsigned int
0x10040939b  mov     rcx, rbx; this
0x10040939e  mov     byte ptr [rax], 8Ch
0x1004093a1  inc     qword ptr [rbx+130h]
0x1004093a8  call    ?WriteMb32@SXWriter@@IEAAXK@Z; SXWriter::WriteMb32(ulong)
0x1004093ad  lea     rcx, [rsp+88h+var_38]; this
0x1004093b2  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x1004093b7  add     rsp, 80h
0x1004093be  pop     rbx
0x1004093bf  retn
```
