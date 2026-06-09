# CUwfProvider::Begin(bool)

- ea: `0x180017b90`
- end: `0x180017bcc`
- name: `?Begin@CUwfProvider@@QEAAJ_N@Z`
- size: `60`
- prototype: `__int64 __fastcall(CUwfProvider *__hidden this, bool)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180017b80`
- `0x1800181a0`
- `0x180018240`
- `0x1800184b0`
- `0x1800187b0`
- `0x180018830`
- `0x1800188d0`
- `0x180018bf0`
- `0x180018c70`
- `0x180018f50`
- `0x180018fe0`
- `0x180019110`
- `0x180019600`
- `0x1800198d0`
- `0x180019940`
- `0x1800199b0`
- `0x180019d70`
- `0x180019df0`
- `0x180019fa0`
- `0x18001a010`
- `0x18001a1a0`
- `0x18001a240`
- `0x18001a920`
- `0x18001a9a0`
- `0x18001aad4`

## callees

- `0x1800163b0`
- `0x180017b90`

## pseudocode

```c
__int64 __fastcall CUwfProvider::Begin(CUwfProvider *this, bool a2)
{
  int v3; // edx

  v3 = CUwfManagement::Initialize((CUwfProvider *)((char *)this + 8), a2);
  if ( v3 >= 0 )
  {
    if ( this == (CUwfProvider *)-224LL )
    {
      return (unsigned int)-2147467261;
    }
    else
    {
      v3 = 0;
      *((_QWORD *)this + 28) = (char *)this + 88;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017b90  push    rbx
0x180017b92  sub     rsp, 20h
0x180017b96  mov     rbx, rcx
0x180017b99  add     rcx, 8; this
0x180017b9d  call    ?Initialize@CUwfManagement@@QEAAJ_N@Z; CUwfManagement::Initialize(bool)
0x180017ba2  mov     edx, eax
0x180017ba4  test    eax, eax
0x180017ba6  js      short loc_180017BC4
0x180017ba8  lea     r8, [rbx+0E0h]
0x180017baf  test    r8, r8
0x180017bb2  jnz     short loc_180017BBB
0x180017bb4  mov     edx, 80004003h
0x180017bb9  jmp     short loc_180017BC4
0x180017bbb  lea     rax, [rbx+58h]
0x180017bbf  xor     edx, edx
0x180017bc1  mov     [r8], rax
0x180017bc4  mov     eax, edx
0x180017bc6  add     rsp, 20h
0x180017bca  pop     rbx
0x180017bcb  retn
```
