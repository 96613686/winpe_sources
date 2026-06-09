# Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)

- ea: `0x18003d0a0`
- end: `0x18003d0cf`
- name: `?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003d7c0`

## callees

- `0x18003d0a0`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( !v2 )
    return 0;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x18003d0a0  sub     rsp, 28h
0x18003d0a4  mov     rax, rcx
0x18003d0a7  xor     edx, edx
0x18003d0a9  mov     rcx, [rcx]
0x18003d0ac  test    rcx, rcx
0x18003d0af  jz      short loc_18003D0C7
0x18003d0b1  mov     [rax], rdx
0x18003d0b4  mov     rax, [rcx]
0x18003d0b7  mov     rax, [rax+10h]
0x18003d0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0c0  nop
0x18003d0c1  add     rsp, 28h
0x18003d0c5  retn
0x18003d0c7  mov     eax, edx
0x18003d0c9  add     rsp, 28h
0x18003d0cd  retn
```
