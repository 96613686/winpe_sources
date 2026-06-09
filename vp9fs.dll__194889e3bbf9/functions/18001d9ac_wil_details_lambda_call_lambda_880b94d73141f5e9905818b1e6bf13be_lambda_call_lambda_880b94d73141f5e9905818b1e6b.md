# wil::details::lambda_call__lambda_880b94d73141f5e9905818b1e6bf13be___::_lambda_call__lambda_880b94d73141f5e9905818b1e6bf13be___

- ea: `0x18001d9ac`
- end: `0x18001d9d7`
- name: `wil::details::lambda_call__lambda_880b94d73141f5e9905818b1e6bf13be___::_lambda_call__lambda_880b94d73141f5e9905818b1e6bf13be___`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800323d2`

## callees

- `0x18001d9ac`

## import_xrefs

- `lxutil!LxUtilFsDeleteFile` at `0x18001d9cc`
- `lxutil!LxUtilFsDeleteFile` at `0x18001d9cc`

## pseudocode

```c
__int64 __fastcall wil::details::lambda_call__lambda_880b94d73141f5e9905818b1e6bf13be___::_lambda_call__lambda_880b94d73141f5e9905818b1e6bf13be___(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    return LxUtilFsDeleteFile(**(_QWORD **)(a1 + 8), *(_QWORD *)(*(_QWORD *)a1 + 72LL) + 32LL);
  }
  return result;
}

```

## disassembly

```asm
0x18001d9ac  sub     rsp, 28h
0x18001d9b0  cmp     byte ptr [rcx+10h], 0
0x18001d9b4  jz      short loc_18001D9D2
0x18001d9b6  mov     byte ptr [rcx+10h], 0
0x18001d9ba  mov     rax, [rcx]
0x18001d9bd  mov     rcx, [rcx+8]
0x18001d9c1  mov     rdx, [rax+48h]
0x18001d9c5  mov     rcx, [rcx]
0x18001d9c8  add     rdx, 20h ; ' '
0x18001d9cc  call    cs:__imp_LxUtilFsDeleteFile
0x18001d9d2  add     rsp, 28h
0x18001d9d6  retn
```
