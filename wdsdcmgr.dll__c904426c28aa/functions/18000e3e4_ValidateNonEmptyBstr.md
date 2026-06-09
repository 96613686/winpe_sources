# ValidateNonEmptyBstr

- ea: `0x18000e3e4`
- end: `0x18000e452`
- name: `ValidateNonEmptyBstr`
- size: `110`
- prototype: `__int64 __fastcall(BSTR pbstr)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e850`
- `0x18000e8f0`
- `0x18000efb0`
- `0x18000f210`
- `0x18000f2c0`
- `0x18000f390`
- `0x18000f470`
- `0x18000f590`
- `0x18000f650`
- `0x18000f710`
- `0x18000f820`
- `0x18000f9d0`
- `0x18000fae0`
- `0x18000fcc0`
- `0x18000fe40`
- `0x180010020`
- `0x180010180`
- `0x1800102e0`
- `0x1800105d0`
- `0x180010790`
- `0x1800108e0`
- `0x180010a00`
- `0x180010b60`
- `0x180010c80`
- `0x180010da0`
- `0x180011000`
- `0x180011240`

## callees

- `0x18000e3e4`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000e407`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e416`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e42d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e407`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e416`
- `OLEAUT32!__imp_SysStringLen` at `0x18000e42d`

## pseudocode

```c
__int64 __fastcall ValidateNonEmptyBstr(BSTR pbstr)
{
  unsigned int v2; // ebx
  int v3; // esi

  v2 = 1;
  if ( !pbstr || !SysStringLen(pbstr) )
    return 0;
  v3 = 0;
  if ( SysStringLen(pbstr) )
  {
    while ( pbstr[v3] )
    {
      if ( ++v3 >= SysStringLen(pbstr) )
        return v2;
    }
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18000e3e4  mov     [rsp+arg_0], rbx
0x18000e3e9  mov     [rsp+arg_8], rbp
0x18000e3ee  mov     [rsp+arg_10], rsi
0x18000e3f3  push    rdi
0x18000e3f4  sub     rsp, 20h
0x18000e3f8  xor     ebp, ebp
0x18000e3fa  mov     rdi, rcx
0x18000e3fd  mov     ebx, 1
0x18000e402  test    rcx, rcx
0x18000e405  jz      short loc_18000E439
0x18000e407  call    cs:__imp_SysStringLen
0x18000e40d  test    eax, eax
0x18000e40f  jz      short loc_18000E439
0x18000e411  mov     rcx, rdi; pbstr
0x18000e414  mov     esi, ebp
0x18000e416  call    cs:__imp_SysStringLen
0x18000e41c  test    eax, eax
0x18000e41e  jz      short loc_18000E43B
0x18000e420  mov     eax, esi
0x18000e422  cmp     [rdi+rax*2], bp
0x18000e426  jz      short loc_18000E439
0x18000e428  mov     rcx, rdi; pbstr
0x18000e42b  add     esi, ebx
0x18000e42d  call    cs:__imp_SysStringLen
0x18000e433  cmp     esi, eax
0x18000e435  jb      short loc_18000E420
0x18000e437  jmp     short loc_18000E43B
0x18000e439  mov     ebx, ebp
0x18000e43b  mov     rbp, [rsp+28h+arg_8]
0x18000e440  mov     eax, ebx
0x18000e442  mov     rbx, [rsp+28h+arg_0]
0x18000e447  mov     rsi, [rsp+28h+arg_10]
0x18000e44c  add     rsp, 20h
0x18000e450  pop     rdi
0x18000e451  retn
```
