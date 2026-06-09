# std::unique_ptr<CHostController,std::default_delete<CHostController>>::~unique_ptr<CHostController,std::default_delete<CHostController>>(void)

- ea: `0x1800040e4`
- end: `0x1800040ff`
- name: `??1?$unique_ptr@VCHostController@@U?$default_delete@VCHostController@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800041b4`
- `0x1800105ea`

## callees

- `0x180002434`
- `0x1800040e4`

## pseudocode

```c
void __fastcall std::unique_ptr<CHostController>::~unique_ptr<CHostController>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1800040e4  sub     rsp, 28h
0x1800040e8  mov     rcx, [rcx]; Block
0x1800040eb  test    rcx, rcx
0x1800040ee  jz      short loc_1800040FA
0x1800040f0  mov     edx, 20h ; ' '
0x1800040f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800040fa  add     rsp, 28h
0x1800040fe  retn
```
