# StringCbPrintfA

- ea: `0x180003040`
- end: `0x1800030c5`
- name: `StringCbPrintfA`
- size: `133`
- prototype: `HRESULT(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800017c0`
- `0x1800030d0`
- `0x180003530`
- `0x1800046c0`

## callees

- `0x180003040`
- `0x1800044b8`

## pseudocode

```c
HRESULT StringCbPrintfA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszFormat, ...)
{
  HRESULT result; // eax
  size_t v5; // rdi
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, pszFormat);
  if ( !cbDest )
    return -2147024809;
  if ( cbDest <= 0x7FFFFFFF )
  {
    v5 = cbDest - 1;
    v6 = vsnprintf(pszDest, cbDest - 1, pszFormat, ArgList);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      pszDest[v5] = 0;
      return -2147024774;
    }
    else
    {
      result = 0;
      if ( v7 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003040  mov     [rsp+arg_10], r8
0x180003045  mov     qword ptr [rsp+ArgList], r9
0x18000304a  push    rbx
0x18000304b  sub     rsp, 40h
0x18000304f  mov     rbx, rcx
0x180003052  test    rdx, rdx
0x180003055  jz      short loc_1800030B2
0x180003057  cmp     rdx, 7FFFFFFFh
0x18000305e  jbe     short loc_180003067
0x180003060  mov     eax, 80070057h
0x180003065  jmp     short loc_1800030BC
0x180003067  mov     [rsp+48h+var_10], rdi
0x18000306c  lea     r9, [rsp+48h+ArgList]; ArgList
0x180003071  lea     rdi, [rdx-1]
0x180003075  mov     [rsp+48h+var_28], 0
0x18000307e  mov     rdx, rdi; BufferCount
0x180003081  call    _vsnprintf
0x180003086  test    eax, eax
0x180003088  js      short loc_18000309E
0x18000308a  movsxd  rcx, eax
0x18000308d  cmp     rcx, rdi
0x180003090  ja      short loc_18000309E
0x180003092  xor     eax, eax
0x180003094  cmp     rcx, rdi
0x180003097  jnz     short loc_1800030A7
0x180003099  mov     [rdi+rbx], al
0x18000309c  jmp     short loc_1800030A7
0x18000309e  mov     byte ptr [rdi+rbx], 0
0x1800030a2  mov     eax, 8007007Ah
0x1800030a7  mov     rdi, [rsp+48h+var_10]
0x1800030ac  add     rsp, 40h
0x1800030b0  pop     rbx
0x1800030b1  retn
0x1800030b2  mov     eax, 80070057h
0x1800030b7  test    rdx, rdx
0x1800030ba  jz      short loc_1800030BF
0x1800030bc  mov     byte ptr [rcx], 0
0x1800030bf  add     rsp, 40h
0x1800030c3  pop     rbx
0x1800030c4  retn
```
