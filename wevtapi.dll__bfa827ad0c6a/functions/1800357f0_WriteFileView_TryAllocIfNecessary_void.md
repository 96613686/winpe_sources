# WriteFileView::TryAllocIfNecessary(void)

- ea: `0x1800357f0`
- end: `0x18003588d`
- name: `?TryAllocIfNecessary@WriteFileView@@QEAAKXZ`
- size: `157`
- prototype: `unsigned int __fastcall(WriteFileView *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800322f0`
- `0x180032704`
- `0x18003459c`
- `0x180035338`

## callees

- `0x180023548`
- `0x1800352b4`
- `0x1800357f0`

## pseudocode

```c
__int64 __fastcall WriteFileView::TryAllocIfNecessary(WriteFileView *this)
{
  unsigned int v2; // edi
  __int64 v4; // rcx

  if ( *((_QWORD *)this + 7) )
    return 0;
  v2 = FileView::TryAllocMemory((WriteFileView *)((char *)this + 8));
  if ( !v2 )
  {
    v4 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 7) = v4;
    *((_QWORD *)this + 42) = this;
    *((_QWORD *)this + 9) = v4 + 128;
    *((_QWORD *)this + 44) = v4 + 384;
    *((_QWORD *)this + 61) = this;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_3150d6ea63e53c8cf0faf274b57ac488_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x1800357f0  mov     [rsp+arg_0], rbx
0x1800357f5  push    rdi
0x1800357f6  sub     rsp, 20h
0x1800357fa  cmp     qword ptr [rcx+38h], 0
0x1800357ff  mov     rbx, rcx
0x180035802  jnz     short loc_180035880
0x180035804  add     rcx, 8; this
0x180035808  call    ?TryAllocMemory@FileView@@QEAAKXZ; FileView::TryAllocMemory(void)
0x18003580d  mov     edi, eax
0x18003580f  test    eax, eax
0x180035811  jz      short loc_180035851
0x180035813  mov     rcx, cs:WPP_GLOBAL_Control
0x18003581a  lea     rax, WPP_GLOBAL_Control
0x180035821  cmp     rcx, rax
0x180035824  jz      short loc_18003584D
0x180035826  test    dword ptr [rcx+1Ch], 200h
0x18003582d  jz      short loc_18003584D
0x18003582f  cmp     byte ptr [rcx+19h], 2
0x180035833  jb      short loc_18003584D
0x180035835  mov     rcx, [rcx+10h]
0x180035839  lea     r8, WPP_3150d6ea63e53c8cf0faf274b57ac488_Traceguids
0x180035840  mov     edx, 0Bh
0x180035845  mov     r9d, edi
0x180035848  call    WPP_SF_D
0x18003584d  mov     eax, edi
0x18003584f  jmp     short loc_180035882
0x180035851  mov     rcx, [rbx+18h]
0x180035855  mov     [rbx+38h], rcx
0x180035859  mov     [rbx+150h], rbx
0x180035860  lea     rax, [rcx+80h]
0x180035867  mov     [rbx+48h], rax
0x18003586b  lea     rax, [rcx+180h]
0x180035872  mov     [rbx+160h], rax
0x180035879  mov     [rbx+1E8h], rbx
0x180035880  xor     eax, eax
0x180035882  mov     rbx, [rsp+28h+arg_0]
0x180035887  add     rsp, 20h
0x18003588b  pop     rdi
0x18003588c  retn
```
