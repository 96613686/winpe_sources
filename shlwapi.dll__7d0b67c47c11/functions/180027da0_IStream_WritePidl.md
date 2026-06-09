# IStream_WritePidl

- ea: `0x180027da0`
- end: `0x180027e0d`
- name: `IStream_WritePidl`
- size: `109`
- prototype: `HRESULT __stdcall(IStream *pstm, LPCITEMIDLIST pidlWrite)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012550`
- `0x180027da0`

## import_xrefs

- `SHELL32!__imp_ILGetSize` at `0x180027dc2`
- `SHELL32!__imp_ILGetSize` at `0x180027dc2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180027dda`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180027def`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180027dda`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180027def`

## pseudocode

```c
HRESULT __stdcall IStream_WritePidl(IStream *pstm, LPCITEMIDLIST pidlWrite)
{
  HRESULT result; // eax
  ULONG pv; // [rsp+20h] [rbp-18h] BYREF

  pv = ILGetSize(pidlWrite);
  result = IStream_Write(pstm, &pv, 4u);
  if ( result >= 0 )
    return IStream_Write(pstm, pidlWrite, pv);
  return result;
}

```

## disassembly

```asm
0x180027da0  mov     [rsp+arg_10], rbx
0x180027da5  push    rdi
0x180027da6  sub     rsp, 30h
0x180027daa  mov     rax, cs:__security_cookie
0x180027db1  xor     rax, rsp
0x180027db4  mov     [rsp+38h+var_10], rax
0x180027db9  mov     rbx, rcx
0x180027dbc  mov     rdi, rdx
0x180027dbf  mov     rcx, rdx; pidl
0x180027dc2  call    cs:__imp_ILGetSize
0x180027dc8  mov     r8d, 4; cb
0x180027dce  lea     rdx, [rsp+38h+pv]; pv
0x180027dd3  mov     rcx, rbx; pstm
0x180027dd6  mov     [rsp+38h+pv], eax
0x180027dda  call    cs:__imp_IStream_Write
0x180027de0  test    eax, eax
0x180027de2  js      short loc_180027DF5
0x180027de4  mov     r8d, [rsp+38h+pv]; cb
0x180027de9  mov     rdx, rdi; pv
0x180027dec  mov     rcx, rbx; pstm
0x180027def  call    cs:__imp_IStream_Write
0x180027df5  mov     rcx, [rsp+38h+var_10]
0x180027dfa  xor     rcx, rsp; StackCookie
0x180027dfd  call    __security_check_cookie
0x180027e02  mov     rbx, [rsp+38h+arg_10]
0x180027e07  add     rsp, 30h
0x180027e0b  pop     rdi
0x180027e0c  retn
```
