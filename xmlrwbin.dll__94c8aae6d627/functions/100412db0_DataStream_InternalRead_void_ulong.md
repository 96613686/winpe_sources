# DataStream::InternalRead(void *,ulong)

- ea: `0x100412db0`
- end: `0x100412e20`
- name: `?InternalRead@DataStream@@AEAAXPEAXK@Z`
- size: `112`
- prototype: `void(DataStream *__hidden this, void *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100412c70`
- `0x100412cc0`

## callees

- `0x100401350`
- `0x100411000`
- `0x100412db0`
- `0x100415d60`

## pseudocode

```c
void __fastcall DataStream::InternalRead(DataStream *this, void *a2, unsigned int a3)
{
  __int64 v4; // rsi
  const void *v5; // rdx

  v4 = a3;
  v5 = (const void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    if ( a3 > *((_DWORD *)this + 6) )
    {
      MXRRaiseException(-1072896679);
      JUMPOUT(0x100412E1FLL);
    }
    memmove(a2, v5, a3);
    *((_QWORD *)this + 2) += v4;
    *((_DWORD *)this + 6) -= v4;
  }
  else
  {
    SXReadBase::GetBytes(*((SXReadBase **)this + 1), (unsigned __int8 *)a2, a3);
    *((_DWORD *)this + 6) -= v4;
  }
}

```

## disassembly

```asm
0x100412db0  mov     [rsp+arg_8], rsi
0x100412db5  push    rdi
0x100412db6  sub     rsp, 20h
0x100412dba  mov     rax, rdx
0x100412dbd  mov     esi, r8d
0x100412dc0  mov     rdx, [rcx+10h]; Src
0x100412dc4  mov     rdi, rcx
0x100412dc7  test    rdx, rdx
0x100412dca  jz      short loc_100412DF8
0x100412dcc  cmp     esi, [rcx+18h]
0x100412dcf  ja      short loc_100412E15
0x100412dd1  mov     r8d, esi; Size
0x100412dd4  mov     [rsp+28h+arg_0], rbx
0x100412dd9  mov     rcx, rax; void *
0x100412ddc  call    memmove
0x100412de1  add     [rdi+10h], rsi
0x100412de5  sub     [rdi+18h], esi
0x100412de8  mov     rbx, [rsp+28h+arg_0]
0x100412ded  mov     rsi, [rsp+28h+arg_8]
0x100412df2  add     rsp, 20h
0x100412df6  pop     rdi
0x100412df7  retn
0x100412df8  mov     rcx, [rcx+8]; this
0x100412dfc  mov     r8d, esi; unsigned int
0x100412dff  mov     rdx, rax; unsigned __int8 *
0x100412e02  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x100412e07  sub     [rdi+18h], esi
0x100412e0a  mov     rsi, [rsp+28h+arg_8]
0x100412e0f  add     rsp, 20h
0x100412e13  pop     rdi
0x100412e14  retn
0x100412e15  mov     ecx, 0C00CE559h; int
0x100412e1a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
