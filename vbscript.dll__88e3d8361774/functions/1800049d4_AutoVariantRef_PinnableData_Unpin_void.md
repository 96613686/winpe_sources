# AutoVariantRef::PinnableData::Unpin(void)

- ea: `0x1800049d4`
- end: `0x180004a3d`
- name: `?Unpin@PinnableData@AutoVariantRef@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(AutoVariantRef::PinnableData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800051f0`

## callees

- `0x1800049d4`
- `0x180077010`

## import_xrefs

- `OLEAUT32!SysReleaseString` at `0x1800049e7`
- `OLEAUT32!SysReleaseString` at `0x1800049e7`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180004a36`
- `OLEAUT32!SafeArrayReleaseData` at `0x180004a27`
- `OLEAUT32!SafeArrayReleaseData` at `0x180004a27`

## pseudocode

```c
void __fastcall AutoVariantRef::PinnableData::Unpin(AutoVariantRef::PinnableData *this)
{
  int v2; // ecx
  int v3; // ecx
  __int64 v4; // rcx
  void *v5; // rcx

  v2 = *(_DWORD *)this;
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( v3 )
    {
      if ( v3 == 1 )
      {
        v4 = *((_QWORD *)this + 2);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
    }
    else if ( *((_QWORD *)this + 1) )
    {
      v5 = (void *)*((_QWORD *)this + 3);
      if ( v5 )
        SafeArrayReleaseData(v5);
      SafeArrayReleaseDescriptor(*((SAFEARRAY **)this + 1));
    }
  }
  else
  {
    SysReleaseString(*((BSTR *)this + 1));
  }
}

```

## disassembly

```asm
0x1800049d4  push    rbx
0x1800049d6  sub     rsp, 20h
0x1800049da  mov     rbx, rcx
0x1800049dd  mov     ecx, [rcx]
0x1800049df  test    ecx, ecx
0x1800049e1  jnz     short loc_1800049F3
0x1800049e3  mov     rcx, [rbx+8]; bstrString
0x1800049e7  call    cs:__imp_SysReleaseString
0x1800049ed  add     rsp, 20h
0x1800049f1  pop     rbx
0x1800049f2  retn
0x1800049f3  sub     ecx, 1
0x1800049f6  jz      short loc_180004A17
0x1800049f8  cmp     ecx, 1
0x1800049fb  jnz     short loc_1800049ED
0x1800049fd  mov     rcx, [rbx+10h]
0x180004a01  test    rcx, rcx
0x180004a04  jz      short loc_1800049ED
0x180004a06  mov     rax, [rcx]
0x180004a09  mov     rax, [rax+10h]
0x180004a0d  add     rsp, 20h
0x180004a11  pop     rbx
0x180004a12  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004a17  cmp     qword ptr [rbx+8], 0
0x180004a1c  jz      short loc_1800049ED
0x180004a1e  mov     rcx, [rbx+18h]; pData
0x180004a22  test    rcx, rcx
0x180004a25  jz      short loc_180004A2D
0x180004a27  call    cs:__imp_SafeArrayReleaseData
0x180004a2d  mov     rcx, [rbx+8]
0x180004a31  add     rsp, 20h
0x180004a35  pop     rbx
0x180004a36  jmp     cs:__imp_SafeArrayReleaseDescriptor
```
