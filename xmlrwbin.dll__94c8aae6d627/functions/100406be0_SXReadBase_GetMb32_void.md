# SXReadBase::GetMb32(void)

- ea: `0x100406be0`
- end: `0x100406d2a`
- name: `?GetMb32@SXReadBase@@IEAAKXZ`
- size: `330`
- prototype: `__int64 __fastcall(SXReadBase *this)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x100404f80`
- `0x100405a70`
- `0x10040edb0`
- `0x10040f590`
- `0x10040f700`
- `0x10040f9a0`
- `0x10040fbf0`
- `0x10040ff60`
- `0x100410010`
- `0x1004101e0`

## callees

- `0x100401350`
- `0x100406be0`
- `0x100411160`

## pseudocode

```c
__int64 __fastcall SXReadBase::GetMb32(SXReadBase *this)
{
  unsigned __int8 *v2; // rax
  unsigned int v3; // ecx
  unsigned __int8 *v4; // rax
  unsigned int v5; // edi
  int v6; // edi
  _BYTE *v7; // rax
  _BYTE *v8; // rdx
  _BYTE *v9; // rax
  _BYTE *v10; // rdx
  _BYTE *v11; // rax
  _BYTE *v12; // rdx
  unsigned __int8 *v13; // rax
  int v14; // ecx

  if ( *((_QWORD *)this + 178) == *((_QWORD *)this + 179) && !SXReadBase::Pull(this) )
    goto LABEL_18;
  v2 = (unsigned __int8 *)*((_QWORD *)this + 178);
  v3 = *v2;
  v4 = v2 + 1;
  *((_QWORD *)this + 178) = v4;
  v5 = v3;
  if ( (v3 & 0x80u) != 0 )
  {
    v6 = v3 & 0x7F;
    if ( v4 == *((unsigned __int8 **)this + 179) && !SXReadBase::Pull(this) )
      goto LABEL_18;
    v7 = (_BYTE *)*((_QWORD *)this + 178);
    v8 = v7 + 1;
    LOBYTE(v7) = *v7;
    *((_QWORD *)this + 178) = v8;
    v5 = (((unsigned __int8)v7 & 0x7F) << 7) | v6;
    if ( (char)v7 < 0 )
    {
      if ( v8 == *((_BYTE **)this + 179) && !SXReadBase::Pull(this) )
        goto LABEL_18;
      v9 = (_BYTE *)*((_QWORD *)this + 178);
      v10 = v9 + 1;
      LOBYTE(v9) = *v9;
      *((_QWORD *)this + 178) = v10;
      v5 |= ((unsigned __int8)v9 & 0x7F) << 14;
      if ( (char)v9 < 0 )
      {
        if ( v10 == *((_BYTE **)this + 179) && !SXReadBase::Pull(this) )
          goto LABEL_18;
        v11 = (_BYTE *)*((_QWORD *)this + 178);
        v12 = v11 + 1;
        LOBYTE(v11) = *v11;
        *((_QWORD *)this + 178) = v12;
        v5 |= ((unsigned __int8)v11 & 0x7F) << 21;
        if ( (char)v11 < 0 )
        {
          if ( v12 != *((_BYTE **)this + 179) || SXReadBase::Pull(this) )
          {
            v13 = (unsigned __int8 *)*((_QWORD *)this + 178);
            v14 = *v13;
            *((_QWORD *)this + 178) = v13 + 1;
            if ( (v14 & 0xF0) == 0 )
            {
              v5 |= v14 << 28;
              return v5;
            }
          }
LABEL_18:
          MXRRaiseException(-2147467259);
          JUMPOUT(0x100406D29LL);
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x100406be0  mov     [rsp+arg_0], rbx
0x100406be5  push    rdi
0x100406be6  sub     rsp, 20h
0x100406bea  mov     rax, [rcx+598h]
0x100406bf1  mov     rbx, rcx
0x100406bf4  cmp     [rcx+590h], rax
0x100406bfb  jnz     short loc_100406C0A
0x100406bfd  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x100406c02  test    al, al
0x100406c04  jz      loc_100406D1F
0x100406c0a  mov     rax, [rbx+590h]
0x100406c11  movzx   ecx, byte ptr [rax]
0x100406c14  inc     rax
0x100406c17  mov     [rbx+590h], rax
0x100406c1e  mov     edi, ecx
0x100406c20  test    cl, cl
0x100406c22  jns     loc_100406D12
0x100406c28  and     edi, 7Fh
0x100406c2b  cmp     rax, [rbx+598h]
0x100406c32  jnz     short loc_100406C44
0x100406c34  mov     rcx, rbx; this
0x100406c37  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x100406c3c  test    al, al
0x100406c3e  jz      loc_100406D1F
0x100406c44  mov     rax, [rbx+590h]
0x100406c4b  movzx   ecx, byte ptr [rax]
0x100406c4e  lea     rdx, [rax+1]
0x100406c52  mov     eax, ecx
0x100406c54  mov     [rbx+590h], rdx
0x100406c5b  and     eax, 7Fh
0x100406c5e  shl     eax, 7
0x100406c61  or      edi, eax
0x100406c63  test    cl, cl
0x100406c65  jns     loc_100406D12
0x100406c6b  cmp     rdx, [rbx+598h]
0x100406c72  jnz     short loc_100406C84
0x100406c74  mov     rcx, rbx; this
0x100406c77  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x100406c7c  test    al, al
0x100406c7e  jz      loc_100406D1F
0x100406c84  mov     rax, [rbx+590h]
0x100406c8b  movzx   ecx, byte ptr [rax]
0x100406c8e  lea     rdx, [rax+1]
0x100406c92  mov     eax, ecx
0x100406c94  mov     [rbx+590h], rdx
0x100406c9b  and     eax, 7Fh
0x100406c9e  shl     eax, 0Eh
0x100406ca1  or      edi, eax
0x100406ca3  test    cl, cl
0x100406ca5  jns     short loc_100406D12
0x100406ca7  cmp     rdx, [rbx+598h]
0x100406cae  jnz     short loc_100406CBC
0x100406cb0  mov     rcx, rbx; this
0x100406cb3  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x100406cb8  test    al, al
0x100406cba  jz      short loc_100406D1F
0x100406cbc  mov     rax, [rbx+590h]
0x100406cc3  movzx   ecx, byte ptr [rax]
0x100406cc6  lea     rdx, [rax+1]
0x100406cca  mov     eax, ecx
0x100406ccc  mov     [rbx+590h], rdx
0x100406cd3  and     eax, 7Fh
0x100406cd6  shl     eax, 15h
0x100406cd9  or      edi, eax
0x100406cdb  test    cl, cl
0x100406cdd  jns     short loc_100406D12
0x100406cdf  cmp     rdx, [rbx+598h]
0x100406ce6  jnz     short loc_100406CF4
0x100406ce8  mov     rcx, rbx; this
0x100406ceb  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x100406cf0  test    al, al
0x100406cf2  jz      short loc_100406D1F
0x100406cf4  mov     rax, [rbx+590h]
0x100406cfb  movzx   ecx, byte ptr [rax]
0x100406cfe  inc     rax
0x100406d01  mov     [rbx+590h], rax
0x100406d08  test    cl, 0F0h
0x100406d0b  jnz     short loc_100406D1F
0x100406d0d  shl     ecx, 1Ch
0x100406d10  or      edi, ecx
0x100406d12  mov     rbx, [rsp+28h+arg_0]
0x100406d17  mov     eax, edi
0x100406d19  add     rsp, 20h
0x100406d1d  pop     rdi
0x100406d1e  retn
0x100406d1f  mov     ecx, 80004005h; int
0x100406d24  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
