# XmlParserTempString::GetCopy(void)

- ea: `0x18001c280`
- end: `0x18001c437`
- name: `?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ`
- size: `439`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001a1c0`
- `0x18004a100`
- `0x18004b8e8`
- `0x18004ca50`

## callees

- `0x18001c280`
- `0x18003b51c`

## import_xrefs

- `msvcrt!malloc` at `0x18001c2d9`
- `msvcrt!malloc` at `0x18001c2d9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c31a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c350`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c31a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001c350`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall XmlParserTempString::GetCopy(__int64 a1, _QWORD *a2)
{
  BSTR v4; // rbx
  char v5; // cl
  const OLECHAR *v6; // rax
  _QWORD *v7; // rax
  void **pExceptionObject; // [rsp+28h] [rbp-40h] BYREF
  char v10; // [rsp+30h] [rbp-38h]
  __int64 *v11; // [rsp+38h] [rbp-30h]
  __int64 v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+48h] [rbp-20h]
  int v14; // [rsp+50h] [rbp-18h]
  __int64 v15; // [rsp+54h] [rbp-14h]

  v4 = 0;
  v5 = *(_BYTE *)(a1 + 1042);
  if ( (v5 & 2) != 0 || (v5 & 1) != 0 || !*(_QWORD *)(a1 + 8) )
  {
    v6 = *(const OLECHAR **)(a1 + 8);
  }
  else
  {
    v6 = SysAllocStringLen(*(const OLECHAR **)(a1 + 8), *(_DWORD *)a1);
    if ( !v6 )
    {
      v10 = 0;
      v11 = &qword_180077320;
      v12 = 0;
      v13 = 0;
      v14 = 14;
      v15 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    *(_QWORD *)(a1 + 8) = v6;
    *(_BYTE *)(a1 + 1042) |= 1u;
    v5 = *(_BYTE *)(a1 + 1042);
  }
  if ( (v5 & 1) != 0 )
  {
    *(_BYTE *)(a1 + 1042) &= ~1u;
    if ( !v6 )
      goto LABEL_7;
    v4 = (BSTR)v6;
  }
  else
  {
    v4 = SysAllocStringLen(v6, *(_DWORD *)a1);
    if ( !v4 )
    {
      v10 = 0;
      v11 = &qword_180077320;
      v12 = 0;
      v13 = 0;
      v14 = 14;
      v15 = -1;
      pExceptionObject = &wmi::GenericException::`vftable';
      throw (wmi::OutOfMemoryException *)&pExceptionObject;
    }
    *(_BYTE *)(a1 + 1042) &= ~1u;
  }
  SysFreeString(0);
LABEL_7:
  v7 = malloc(0x18u);
  if ( !v7 )
  {
    v10 = 0;
    v11 = &qword_180077320;
    v12 = 0;
    v13 = 0;
    v14 = 14;
    v15 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v7[1] = 0;
  *((_DWORD *)v7 + 4) = 1;
  *v7 = v4;
  *a2 = v7;
  SysFreeString(0);
  return a2;
}

```

## disassembly

```asm
0x18001c280  push    rbp
0x18001c282  push    rbx
0x18001c283  push    rsi
0x18001c284  push    rdi
0x18001c285  push    r14
0x18001c287  push    r15
0x18001c289  mov     rbp, rsp
0x18001c28c  sub     rsp, 68h
0x18001c290  mov     rsi, rdx
0x18001c293  mov     rdi, rcx
0x18001c296  xor     r15d, r15d
0x18001c299  mov     ebx, r15d
0x18001c29c  mov     [rbp+arg_0], rbx
0x18001c2a0  movzx   ecx, byte ptr [rcx+412h]
0x18001c2a7  test    cl, 2
0x18001c2aa  jz      loc_18001C335
0x18001c2b0  mov     rax, [rdi+8]
0x18001c2b4  test    cl, 1
0x18001c2b7  jz      short loc_18001C315
0x18001c2b9  and     byte ptr [rdi+412h], 0FEh
0x18001c2c0  test    rax, rax
0x18001c2c3  jz      short loc_18001C2D4
0x18001c2c5  mov     rbx, rax
0x18001c2c8  xor     ecx, ecx; bstrString
0x18001c2ca  call    cs:__imp_SysFreeString
0x18001c2d0  mov     [rbp+arg_0], rbx
0x18001c2d4  mov     ecx, 18h; Size
0x18001c2d9  call    cs:__imp_malloc
0x18001c2df  test    rax, rax
0x18001c2e2  jz      loc_18001C3F5
0x18001c2e8  mov     [rbp+arg_0], rax
0x18001c2ec  mov     [rax+8], r15
0x18001c2f0  mov     dword ptr [rax+10h], 1
0x18001c2f7  mov     [rax], rbx
0x18001c2fa  mov     [rsi], rax
0x18001c2fd  xor     ecx, ecx; bstrString
0x18001c2ff  call    cs:__imp_SysFreeString
0x18001c305  mov     rax, rsi
0x18001c308  add     rsp, 68h
0x18001c30c  pop     r15
0x18001c30e  pop     r14
0x18001c310  pop     rdi
0x18001c311  pop     rsi
0x18001c312  pop     rbx
0x18001c313  pop     rbp
0x18001c314  retn
0x18001c315  mov     edx, [rdi]; ui
0x18001c317  mov     rcx, rax; strIn
0x18001c31a  call    cs:__imp_SysAllocStringLen
0x18001c320  mov     rbx, rax
0x18001c323  test    rax, rax
0x18001c326  jz      loc_18001C3B3
0x18001c32c  and     byte ptr [rdi+412h], 0FEh
0x18001c333  jmp     short loc_18001C2C8
0x18001c335  test    cl, 1
0x18001c338  jnz     loc_18001C2B0
0x18001c33e  mov     rax, [rdi+8]
0x18001c342  test    rax, rax
0x18001c345  jz      loc_18001C2B0
0x18001c34b  mov     edx, [rdi]; ui
0x18001c34d  mov     rcx, rax; strIn
0x18001c350  call    cs:__imp_SysAllocStringLen
0x18001c356  test    rax, rax
0x18001c359  jnz     short loc_18001C39C
0x18001c35b  mov     [rbp+var_38], al
0x18001c35e  lea     rax, qword_180077320
0x18001c365  mov     [rbp+var_30], rax
0x18001c369  mov     [rbp+var_28], r15
0x18001c36d  mov     [rbp+var_20], r15
0x18001c371  mov     [rbp+var_18], 0Eh
0x18001c378  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001c380  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001c387  mov     [rbp+pExceptionObject], rax
0x18001c38b  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001c392  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001c396  call    _CxxThrowException_0
0x18001c39c  mov     [rdi+8], rax
0x18001c3a0  or      byte ptr [rdi+412h], 1
0x18001c3a7  movzx   ecx, byte ptr [rdi+412h]
0x18001c3ae  jmp     loc_18001C2B4
0x18001c3b3  mov     [rbp+var_38], 0
0x18001c3b7  lea     rax, qword_180077320
0x18001c3be  mov     [rbp+var_30], rax
0x18001c3c2  mov     [rbp+var_28], r15
0x18001c3c6  mov     [rbp+var_20], r15
0x18001c3ca  mov     [rbp+var_18], 0Eh
0x18001c3d1  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001c3d9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001c3e0  mov     [rbp+pExceptionObject], rax
0x18001c3e4  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001c3eb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001c3ef  call    _CxxThrowException_0
0x18001c3f5  mov     [rbp+var_38], 0
0x18001c3f9  lea     rax, qword_180077320
0x18001c400  mov     [rbp+var_30], rax
0x18001c404  mov     [rbp+var_28], r15
0x18001c408  mov     [rbp+var_20], r15
0x18001c40c  mov     [rbp+var_18], 0Eh
0x18001c413  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001c41b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001c422  mov     [rbp+pExceptionObject], rax
0x18001c426  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001c42d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001c431  call    _CxxThrowException_0
```
