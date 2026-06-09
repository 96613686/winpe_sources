# CSafeArray::GetRawData(void *,int)

- ea: `0x180016160`
- end: `0x1800161e0`
- name: `?GetRawData@CSafeArray@@QEAAHPEAXH@Z`
- size: `128`
- prototype: `int(CSafeArray *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800160e0`

## callees

- `0x180016160`
- `0x18002ee96`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180016196`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180016196`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800161be`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800161be`

## pseudocode

```c
__int64 __fastcall CSafeArray::GetRawData(CSafeArray *this, void *a2, int a3)
{
  SAFEARRAY *v5; // rcx
  HRESULT v6; // ebx
  void *Src; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 5) * (*(_DWORD *)this + 1) > a3 )
    return 1;
  v5 = (SAFEARRAY *)*((_QWORD *)this + 4);
  Src = 0;
  v6 = SafeArrayAccessData(v5, &Src);
  if ( v6 >= 0 )
  {
    memcpy_0(a2, Src, *((_DWORD *)this + 5) * (*(_DWORD *)this + 1));
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 4));
  }
  return (unsigned int)v6 >> 31;
}

```

## disassembly

```asm
0x180016160  mov     rax, rsp
0x180016163  mov     [rax+10h], rbx
0x180016167  mov     [rax+18h], rsi
0x18001616b  push    rdi
0x18001616c  sub     rsp, 20h
0x180016170  mov     r9d, [rcx]
0x180016173  mov     rsi, rdx
0x180016176  inc     r9d
0x180016179  mov     rdi, rcx
0x18001617c  imul    r9d, [rcx+14h]
0x180016181  cmp     r9d, r8d
0x180016184  jg      short loc_1800161D9
0x180016186  mov     rcx, [rcx+20h]; psa
0x18001618a  lea     rdx, [rax+8]; ppvData
0x18001618e  mov     qword ptr [rax+8], 0
0x180016196  call    cs:__imp_SafeArrayAccessData
0x18001619c  mov     ebx, eax
0x18001619e  test    eax, eax
0x1800161a0  js      short loc_1800161C4
0x1800161a2  mov     ecx, [rdi]
0x1800161a4  mov     rdx, [rsp+28h+Src]; Src
0x1800161a9  inc     ecx
0x1800161ab  imul    ecx, [rdi+14h]
0x1800161af  movsxd  r8, ecx; Size
0x1800161b2  mov     rcx, rsi; void *
0x1800161b5  call    memcpy_0
0x1800161ba  mov     rcx, [rdi+20h]; psa
0x1800161be  call    cs:__imp_SafeArrayUnaccessData
0x1800161c4  shr     ebx, 1Fh
0x1800161c7  mov     eax, ebx
0x1800161c9  mov     rbx, [rsp+28h+arg_8]
0x1800161ce  mov     rsi, [rsp+28h+arg_10]
0x1800161d3  add     rsp, 20h
0x1800161d7  pop     rdi
0x1800161d8  retn
0x1800161d9  mov     eax, 1
0x1800161de  jmp     short loc_1800161C9
```
