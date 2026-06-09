# SXWriter::MakeNewTokenTable(void)

- ea: `0x10040a3c0`
- end: `0x10040a465`
- name: `?MakeNewTokenTable@SXWriter@@AEAAXXZ`
- size: `165`
- prototype: `void __fastcall(SXWriter *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100409da0`
- `0x10040a700`

## callees

- `0x100407050`
- `0x1004086f0`
- `0x10040a3c0`
- `0x100424580`

## pseudocode

```c
void __fastcall SXWriter::MakeNewTokenTable(SXWriter *this)
{
  __int64 v2; // rcx
  _BYTE *v3; // rax
  unsigned int v4; // edx
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 10);
  if ( v2 )
  {
    *((_QWORD *)this + 10) = *(_QWORD *)(v2 + 168);
    (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 1);
  }
  else
  {
    *((_QWORD *)this + 10) = 0;
  }
  SXTokenTable::PushTokenTable(*((struct IMalloc **)this + 1), (struct SXTokenTable **)this + 10);
  v3 = (_BYTE *)*((_QWORD *)this + 38);
  if ( v3 == *((_BYTE **)this + 39) )
  {
    SXWriter::writeBuffer(this);
    v3 = (_BYTE *)*((_QWORD *)this + 38);
  }
  *v3 = -23;
  v4 = 0;
  ++*((_QWORD *)this + 38);
  if ( *((_DWORD *)this + 27) )
  {
    do
    {
      v5 = v4++;
      *(_DWORD *)(32 * v5 + *((_QWORD *)this + 14) + 24) = 0;
    }
    while ( v4 < *((_DWORD *)this + 27) );
  }
}

```

## disassembly

```asm
0x10040a3c0  mov     [rsp+arg_0], rbx
0x10040a3c5  mov     [rsp+arg_8], rsi
0x10040a3ca  push    rdi
0x10040a3cb  sub     rsp, 20h
0x10040a3cf  mov     rbx, rcx
0x10040a3d2  xor     esi, esi
0x10040a3d4  mov     rcx, [rcx+50h]
0x10040a3d8  test    rcx, rcx
0x10040a3db  jz      short loc_10040A3F9
0x10040a3dd  mov     rax, [rcx+0A8h]
0x10040a3e4  lea     edx, [rsi+1]
0x10040a3e7  mov     [rbx+50h], rax
0x10040a3eb  mov     rax, [rcx]
0x10040a3ee  mov     rax, [rax]
0x10040a3f1  call    cs:__guard_dispatch_icall_fptr
0x10040a3f7  jmp     short loc_10040A3FD
0x10040a3f9  mov     [rbx+50h], rsi
0x10040a3fd  mov     rcx, [rbx+8]; struct IMalloc *
0x10040a401  lea     rdx, [rbx+50h]; struct SXTokenTable **
0x10040a405  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x10040a40a  mov     rax, [rbx+130h]
0x10040a411  cmp     rax, [rbx+138h]
0x10040a418  jnz     short loc_10040A429
0x10040a41a  mov     rcx, rbx; this
0x10040a41d  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040a422  mov     rax, [rbx+130h]
0x10040a429  mov     byte ptr [rax], 0E9h
0x10040a42c  mov     edx, esi
0x10040a42e  inc     qword ptr [rbx+130h]
0x10040a435  cmp     [rbx+6Ch], edx
0x10040a438  jbe     short loc_10040A455
0x10040a43a  nop     word ptr [rax+rax+00h]
0x10040a440  mov     rax, [rbx+70h]
0x10040a444  mov     ecx, edx
0x10040a446  inc     edx
0x10040a448  shl     rcx, 5
0x10040a44c  mov     [rcx+rax+18h], esi
0x10040a450  cmp     edx, [rbx+6Ch]
0x10040a453  jb      short loc_10040A440
0x10040a455  mov     rbx, [rsp+28h+arg_0]
0x10040a45a  mov     rsi, [rsp+28h+arg_8]
0x10040a45f  add     rsp, 20h
0x10040a463  pop     rdi
0x10040a464  retn
```
