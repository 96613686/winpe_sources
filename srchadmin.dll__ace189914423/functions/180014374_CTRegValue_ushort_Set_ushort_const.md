# CTRegValue<ushort *>::Set(ushort * const)

- ea: `0x180014374`
- end: `0x1800143cf`
- name: `?Set@?$CTRegValue@PEAG@@QEAAJQEAG@Z`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012a30`
- `0x180012c00`

## callees

- `0x1800056e0`
- `0x180014374`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x1800143ad`
- `SHLWAPI!SHStrDupW` at `0x1800143ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014395`

## pseudocode

```c
HRESULT __fastcall CTRegValue<unsigned short *>::Set(__int64 a1, const WCHAR *a2)
{
  LPWSTR *v2; // rbx
  void *v4; // rcx
  HRESULT result; // eax

  v2 = (LPWSTR *)(a1 + 32);
  v4 = *(void **)(a1 + 32);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *v2 = 0;
  }
  if ( !a2 )
    return CTRegValue<unsigned short *>::WriteToReg(a1);
  result = SHStrDupW(a2, v2);
  if ( result >= 0 )
    return CTRegValue<unsigned short *>::WriteToReg(a1);
  return result;
}

```

## disassembly

```asm
0x180014374  mov     [rsp+arg_0], rbx
0x180014379  mov     [rsp+arg_8], rsi
0x18001437e  push    rdi
0x18001437f  sub     rsp, 20h
0x180014383  lea     rbx, [rcx+20h]
0x180014387  mov     rsi, rcx
0x18001438a  mov     rcx, [rbx]; pv
0x18001438d  mov     rdi, rdx
0x180014390  test    rcx, rcx
0x180014393  jz      short loc_1800143A2
0x180014395  call    cs:__imp_CoTaskMemFree
0x18001439b  mov     qword ptr [rbx], 0
0x1800143a2  test    rdi, rdi
0x1800143a5  jz      short loc_1800143B7
0x1800143a7  mov     rdx, rbx; ppwsz
0x1800143aa  mov     rcx, rdi; psz
0x1800143ad  call    cs:__imp_SHStrDupW
0x1800143b3  test    eax, eax
0x1800143b5  js      short loc_1800143BF
0x1800143b7  mov     rcx, rsi
0x1800143ba  call    ?WriteToReg@?$CTRegValue@PEAG@@IEAAJXZ; CTRegValue<ushort *>::WriteToReg(void)
0x1800143bf  mov     rbx, [rsp+28h+arg_0]
0x1800143c4  mov     rsi, [rsp+28h+arg_8]
0x1800143c9  add     rsp, 20h
0x1800143cd  pop     rdi
0x1800143ce  retn
```
