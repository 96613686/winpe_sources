# XmlParserTempString::GetCopy(void)

- ea: `0x18001d3f0`
- end: `0x18001d5c9`
- name: `?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ`
- size: `473`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001b390`
- `0x18004dcb0`
- `0x18004f508`
- `0x180050690`

## callees

- `0x18001d3f0`
- `0x18003e88c`

## import_xrefs

- `msvcrt!malloc` at `0x18001d44f`
- `msvcrt!malloc` at `0x18001d44f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d49d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d4dc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d49d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001d4dc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d43a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d47b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d43a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d47b`

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
      v11 = &qword_18007B2F0;
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
      v11 = &qword_18007B2F0;
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
    v11 = &qword_18007B2F0;
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
0x18001d3f0  push    rbp
0x18001d3f2  push    rbx
0x18001d3f3  push    rsi
0x18001d3f4  push    rdi
0x18001d3f5  push    r14
0x18001d3f7  push    r15
0x18001d3f9  mov     rbp, rsp
0x18001d3fc  sub     rsp, 68h
0x18001d400  mov     rsi, rdx
0x18001d403  mov     rdi, rcx
0x18001d406  xor     r15d, r15d
0x18001d409  mov     ebx, r15d
0x18001d40c  mov     [rbp+arg_0], rbx
0x18001d410  movzx   ecx, byte ptr [rcx+412h]
0x18001d417  test    cl, 2
0x18001d41a  jz      loc_18001D4C1
0x18001d420  mov     rax, [rdi+8]
0x18001d424  test    cl, 1
0x18001d427  jz      short loc_18001D498
0x18001d429  and     byte ptr [rdi+412h], 0FEh
0x18001d430  test    rax, rax
0x18001d433  jz      short loc_18001D44A
0x18001d435  mov     rbx, rax
0x18001d438  xor     ecx, ecx; bstrString
0x18001d43a  call    cs:__imp_SysFreeString
0x18001d441  nop     dword ptr [rax+rax+00h]
0x18001d446  mov     [rbp+arg_0], rbx
0x18001d44a  mov     ecx, 18h; Size
0x18001d44f  call    cs:__imp_malloc
0x18001d456  nop     dword ptr [rax+rax+00h]
0x18001d45b  test    rax, rax
0x18001d45e  jz      loc_18001D587
0x18001d464  mov     [rbp+arg_0], rax
0x18001d468  mov     [rax+8], r15
0x18001d46c  mov     dword ptr [rax+10h], 1
0x18001d473  mov     [rax], rbx
0x18001d476  mov     [rsi], rax
0x18001d479  xor     ecx, ecx; bstrString
0x18001d47b  call    cs:__imp_SysFreeString
0x18001d482  nop     dword ptr [rax+rax+00h]
0x18001d487  mov     rax, rsi
0x18001d48a  add     rsp, 68h
0x18001d48e  pop     r15
0x18001d490  pop     r14
0x18001d492  pop     rdi
0x18001d493  pop     rsi
0x18001d494  pop     rbx
0x18001d495  pop     rbp
0x18001d496  retn
0x18001d498  mov     edx, [rdi]; ui
0x18001d49a  mov     rcx, rax; strIn
0x18001d49d  call    cs:__imp_SysAllocStringLen
0x18001d4a4  nop     dword ptr [rax+rax+00h]
0x18001d4a9  mov     rbx, rax
0x18001d4ac  test    rax, rax
0x18001d4af  jz      loc_18001D545
0x18001d4b5  and     byte ptr [rdi+412h], 0FEh
0x18001d4bc  jmp     loc_18001D438
0x18001d4c1  test    cl, 1
0x18001d4c4  jnz     loc_18001D420
0x18001d4ca  mov     rax, [rdi+8]
0x18001d4ce  test    rax, rax
0x18001d4d1  jz      loc_18001D420
0x18001d4d7  mov     edx, [rdi]; ui
0x18001d4d9  mov     rcx, rax; strIn
0x18001d4dc  call    cs:__imp_SysAllocStringLen
0x18001d4e3  nop     dword ptr [rax+rax+00h]
0x18001d4e8  test    rax, rax
0x18001d4eb  jnz     short loc_18001D52E
0x18001d4ed  mov     [rbp+var_38], al
0x18001d4f0  lea     rax, qword_18007B2F0
0x18001d4f7  mov     [rbp+var_30], rax
0x18001d4fb  mov     [rbp+var_28], r15
0x18001d4ff  mov     [rbp+var_20], r15
0x18001d503  mov     [rbp+var_18], 0Eh
0x18001d50a  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001d512  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d519  mov     [rbp+pExceptionObject], rax
0x18001d51d  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001d524  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d528  call    _CxxThrowException_0
0x18001d52e  mov     [rdi+8], rax
0x18001d532  or      byte ptr [rdi+412h], 1
0x18001d539  movzx   ecx, byte ptr [rdi+412h]
0x18001d540  jmp     loc_18001D424
0x18001d545  mov     [rbp+var_38], 0
0x18001d549  lea     rax, qword_18007B2F0
0x18001d550  mov     [rbp+var_30], rax
0x18001d554  mov     [rbp+var_28], r15
0x18001d558  mov     [rbp+var_20], r15
0x18001d55c  mov     [rbp+var_18], 0Eh
0x18001d563  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001d56b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d572  mov     [rbp+pExceptionObject], rax
0x18001d576  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001d57d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d581  call    _CxxThrowException_0
0x18001d587  mov     [rbp+var_38], 0
0x18001d58b  lea     rax, qword_18007B2F0
0x18001d592  mov     [rbp+var_30], rax
0x18001d596  mov     [rbp+var_28], r15
0x18001d59a  mov     [rbp+var_20], r15
0x18001d59e  mov     [rbp+var_18], 0Eh
0x18001d5a5  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18001d5ad  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001d5b4  mov     [rbp+pExceptionObject], rax
0x18001d5b8  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001d5bf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d5c3  call    _CxxThrowException_0
```
