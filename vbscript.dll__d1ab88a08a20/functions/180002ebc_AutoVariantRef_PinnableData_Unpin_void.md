# AutoVariantRef::PinnableData::Unpin(void)

- ea: `0x180002ebc`
- end: `0x180002f37`
- name: `?Unpin@PinnableData@AutoVariantRef@@QEAAXXZ`
- size: `123`
- prototype: `void __fastcall(AutoVariantRef::PinnableData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fc0`

## callees

- `0x180002ebc`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!SysReleaseString` at `0x180002ecf`
- `OLEAUT32!SysReleaseString` at `0x180002ecf`
- `OLEAUT32!SafeArrayReleaseDescriptor` at `0x180002f2b`
- `OLEAUT32!SafeArrayReleaseData` at `0x180002f16`
- `OLEAUT32!SafeArrayReleaseData` at `0x180002f16`

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
0x180002ebc  push    rbx
0x180002ebe  sub     rsp, 20h
0x180002ec2  mov     rbx, rcx
0x180002ec5  mov     ecx, [rcx]
0x180002ec7  test    ecx, ecx
0x180002ec9  jnz     short loc_180002EE2
0x180002ecb  mov     rcx, [rbx+8]; bstrString
0x180002ecf  call    cs:__imp_SysReleaseString
0x180002ed6  nop     dword ptr [rax+rax+00h]
0x180002edb  add     rsp, 20h
0x180002edf  pop     rbx
0x180002ee0  retn
0x180002ee2  sub     ecx, 1
0x180002ee5  jz      short loc_180002F06
0x180002ee7  cmp     ecx, 1
0x180002eea  jnz     short loc_180002EDB
0x180002eec  mov     rcx, [rbx+10h]
0x180002ef0  test    rcx, rcx
0x180002ef3  jz      short loc_180002EDB
0x180002ef5  mov     rax, [rcx]
0x180002ef8  mov     rax, [rax+10h]
0x180002efc  add     rsp, 20h
0x180002f00  pop     rbx
0x180002f01  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002f06  cmp     qword ptr [rbx+8], 0
0x180002f0b  jz      short loc_180002EDB
0x180002f0d  mov     rcx, [rbx+18h]; pData
0x180002f11  test    rcx, rcx
0x180002f14  jz      short loc_180002F22
0x180002f16  call    cs:__imp_SafeArrayReleaseData
0x180002f1d  nop     dword ptr [rax+rax+00h]
0x180002f22  mov     rcx, [rbx+8]
0x180002f26  add     rsp, 20h
0x180002f2a  pop     rbx
0x180002f2b  jmp     cs:__imp_SafeArrayReleaseDescriptor
```
