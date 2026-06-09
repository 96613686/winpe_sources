# CWMFileSinkV1::Write(uchar *,ulong,ulong *)

- ea: `0x18000c1b0`
- end: `0x18000c229`
- name: `?Write@CWMFileSinkV1@@MEAAJPEAEKPEAK@Z`
- size: `121`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005160`

## callees

- `0x18000c1b0`
- `0x18000d140`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18000c204`
- `KERNEL32!WriteFile` at `0x18000c204`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::Write(
        CUnbufferedWriter **this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  int v6; // ebx
  CUnbufferedWriter *v7; // rcx

  *a4 = 0;
  if ( *((_DWORD *)this + 9) && this[1158] )
  {
    v6 = CUnbufferedWriter::SequentialWrite(this[1158], a2, a3);
    if ( v6 >= 0 )
      *a4 = a3;
  }
  else
  {
    v7 = this[24];
    v6 = 0;
    if ( v7 != (CUnbufferedWriter *)-1LL && (!WriteFile(v7, a2, a3, a4, 0) || *a4 != a3) )
      return (unsigned int)-1072889832;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c1b0  mov     [rsp+arg_0], rbx
0x18000c1b5  mov     [rsp+arg_8], rsi
0x18000c1ba  push    rdi
0x18000c1bb  sub     rsp, 30h
0x18000c1bf  mov     dword ptr [r9], 0
0x18000c1c6  mov     rsi, r9
0x18000c1c9  cmp     dword ptr [rcx+24h], 0
0x18000c1cd  mov     edi, r8d
0x18000c1d0  jz      short loc_18000C1F0
0x18000c1d2  mov     rax, [rcx+2430h]
0x18000c1d9  test    rax, rax
0x18000c1dc  jz      short loc_18000C1F0
0x18000c1de  mov     rcx, rax; this
0x18000c1e1  call    ?SequentialWrite@CUnbufferedWriter@@QEAAJPEAEK@Z; CUnbufferedWriter::SequentialWrite(uchar *,ulong)
0x18000c1e6  mov     ebx, eax
0x18000c1e8  test    eax, eax
0x18000c1ea  js      short loc_18000C217
0x18000c1ec  mov     [rsi], edi
0x18000c1ee  jmp     short loc_18000C217
0x18000c1f0  mov     rcx, [rcx+0C0h]; hFile
0x18000c1f7  xor     ebx, ebx
0x18000c1f9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c1fd  jz      short loc_18000C217
0x18000c1ff  mov     [rsp+38h+lpOverlapped], rbx; lpOverlapped
0x18000c204  call    cs:__imp_WriteFile
0x18000c20a  test    eax, eax
0x18000c20c  jz      short loc_18000C212
0x18000c20e  cmp     [rsi], edi
0x18000c210  jz      short loc_18000C217
0x18000c212  mov     ebx, 0C00D0018h
0x18000c217  mov     rsi, [rsp+38h+arg_8]
0x18000c21c  mov     eax, ebx
0x18000c21e  mov     rbx, [rsp+38h+arg_0]
0x18000c223  add     rsp, 30h
0x18000c227  pop     rdi
0x18000c228  retn
```
