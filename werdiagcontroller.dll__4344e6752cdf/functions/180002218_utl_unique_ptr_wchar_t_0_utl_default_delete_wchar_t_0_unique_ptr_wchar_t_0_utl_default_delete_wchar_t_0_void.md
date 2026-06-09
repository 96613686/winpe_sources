# utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::~unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>(void)

- ea: `0x180002218`
- end: `0x18000222e`
- name: `??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006528`
- `0x180006594`

## callees

- `0x180001cd4`
- `0x180002218`

## pseudocode

```c
void __fastcall utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::~unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete[](v1);
}

```

## disassembly

```asm
0x180002218  sub     rsp, 28h
0x18000221c  mov     rcx, [rcx]; void *
0x18000221f  test    rcx, rcx
0x180002222  jz      short loc_180002229
0x180002224  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180002229  add     rsp, 28h
0x18000222d  retn
```
