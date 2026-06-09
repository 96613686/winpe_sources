# SXWriter::endCDATA(void)

- ea: `0x10040ae60`
- end: `0x10040aed0`
- name: `?endCDATA@SXWriter@@UEAAJXZ`
- size: `112`
- prototype: `__int64 __fastcall(SXWriter *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1004086f0`
- `0x10040ae60`
- `0x100424580`

## pseudocode

```c
__int64 __fastcall SXWriter::endCDATA(SXWriter *this)
{
  _BYTE *v2; // rax
  __int64 result; // rax

  if ( *((_BYTE *)this + 217) )
    (*(void (__fastcall **)(char *, const wchar_t *, _QWORD))(*((_QWORD *)this + 4) + 80LL))(
      (char *)this + 32,
      &qword_10042F910,
      0);
  v2 = (_BYTE *)*((_QWORD *)this + 34);
  if ( v2 == *((_BYTE **)this + 35) )
  {
    SXWriter::writeBuffer((SXWriter *)((char *)this - 32));
    v2 = (_BYTE *)*((_QWORD *)this + 34);
  }
  *v2 = -15;
  ++*((_QWORD *)this + 34);
  result = 0;
  *((_BYTE *)this + 216) = 0;
  return result;
}

```

## disassembly

```asm
0x10040ae60  mov     [rsp+arg_0], rbx
0x10040ae65  push    rdi
0x10040ae66  sub     rsp, 20h
0x10040ae6a  cmp     byte ptr [rcx+0D9h], 0
0x10040ae71  mov     rdi, rcx
0x10040ae74  jz      short loc_10040AE92
0x10040ae76  mov     rax, [rcx+20h]
0x10040ae7a  lea     rdx, qword_10042F910
0x10040ae81  add     rcx, 20h ; ' '
0x10040ae85  xor     r8d, r8d
0x10040ae88  mov     rax, [rax+50h]
0x10040ae8c  call    cs:__guard_dispatch_icall_fptr
0x10040ae92  mov     rax, [rdi+110h]
0x10040ae99  cmp     rax, [rdi+118h]
0x10040aea0  jnz     short loc_10040AEB2
0x10040aea2  lea     rcx, [rdi-20h]; this
0x10040aea6  call    ?writeBuffer@SXWriter@@IEAAXXZ; SXWriter::writeBuffer(void)
0x10040aeab  mov     rax, [rdi+110h]
0x10040aeb2  mov     rbx, [rsp+28h+arg_0]
0x10040aeb7  mov     byte ptr [rax], 0F1h
0x10040aeba  inc     qword ptr [rdi+110h]
0x10040aec1  xor     eax, eax
0x10040aec3  mov     byte ptr [rdi+0D8h], 0
0x10040aeca  add     rsp, 20h
0x10040aece  pop     rdi
0x10040aecf  retn
```
