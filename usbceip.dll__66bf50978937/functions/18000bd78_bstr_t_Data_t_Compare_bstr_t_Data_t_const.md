# _bstr_t::Data_t::Compare(_bstr_t::Data_t const &)

- ea: `0x18000bd78`
- end: `0x18000be0c`
- name: `?Compare@Data_t@_bstr_t@@QEBAHAEBV12@@Z`
- size: `148`
- prototype: `__int64 __fastcall(OLECHAR **this, BSTR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bab4`

## callees

- `0x18000bd78`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000bdab`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bdb6`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bdab`
- `OLEAUT32!__imp_SysStringLen` at `0x18000bdb6`

## pseudocode

```c
__int64 __fastcall _bstr_t::Data_t::Compare(OLECHAR **this, BSTR *a2)
{
  BSTR v2; // rax
  OLECHAR *v4; // rcx
  UINT v7; // ebx
  UINT v8; // eax
  OLECHAR *v9; // r9
  UINT v10; // ecx
  BSTR v11; // r10
  UINT v12; // edx
  int v13; // eax
  int v14; // r8d

  v2 = *a2;
  v4 = *this;
  if ( !v4 )
    return (unsigned int)-(v2 != 0);
  if ( !v2 )
    return 1;
  v7 = SysStringLen(v4);
  v8 = SysStringLen(*a2);
  v9 = *this;
  v10 = v7;
  v11 = *a2;
  v12 = v8;
  if ( v7 > v8 )
    v10 = v8;
  while ( v10 )
  {
    v13 = *v9;
    --v10;
    v14 = *v11;
    ++v9;
    ++v11;
    if ( (_WORD)v13 != (_WORD)v14 )
      return (unsigned int)(v13 - v14);
  }
  if ( v7 >= v12 )
    return v7 != v12;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000bd78  mov     [rsp+arg_0], rbx
0x18000bd7d  mov     [rsp+arg_8], rsi
0x18000bd82  push    rdi
0x18000bd83  sub     rsp, 20h
0x18000bd87  mov     rax, [rdx]
0x18000bd8a  mov     rsi, rcx
0x18000bd8d  mov     rcx, [rcx]; pbstr
0x18000bd90  mov     rdi, rdx
0x18000bd93  test    rcx, rcx
0x18000bd96  jnz     short loc_18000BD9F
0x18000bd98  neg     rax
0x18000bd9b  sbb     eax, eax
0x18000bd9d  jmp     short loc_18000BDFC
0x18000bd9f  test    rax, rax
0x18000bda2  jnz     short loc_18000BDAB
0x18000bda4  mov     eax, 1
0x18000bda9  jmp     short loc_18000BDFC
0x18000bdab  call    cs:__imp_SysStringLen
0x18000bdb1  mov     rcx, [rdi]; pbstr
0x18000bdb4  mov     ebx, eax
0x18000bdb6  call    cs:__imp_SysStringLen
0x18000bdbc  mov     r9, [rsi]
0x18000bdbf  mov     ecx, ebx
0x18000bdc1  mov     r10, [rdi]
0x18000bdc4  cmp     ebx, eax
0x18000bdc6  mov     edx, eax
0x18000bdc8  cmova   ecx, eax
0x18000bdcb  test    ecx, ecx
0x18000bdcd  jz      short loc_18000BDEC
0x18000bdcf  movzx   eax, word ptr [r9]
0x18000bdd3  dec     ecx
0x18000bdd5  movzx   r8d, word ptr [r10]
0x18000bdd9  add     r9, 2
0x18000bddd  add     r10, 2
0x18000bde1  cmp     ax, r8w
0x18000bde5  jz      short loc_18000BDCB
0x18000bde7  sub     eax, r8d
0x18000bdea  jmp     short loc_18000BDFC
0x18000bdec  cmp     ebx, edx
0x18000bdee  jnb     short loc_18000BDF5
0x18000bdf0  or      eax, 0FFFFFFFFh
0x18000bdf3  jmp     short loc_18000BDFC
0x18000bdf5  xor     eax, eax
0x18000bdf7  cmp     ebx, edx
0x18000bdf9  setnz   al
0x18000bdfc  mov     rbx, [rsp+28h+arg_0]
0x18000be01  mov     rsi, [rsp+28h+arg_8]
0x18000be06  add     rsp, 20h
0x18000be0a  pop     rdi
0x18000be0b  retn
```
