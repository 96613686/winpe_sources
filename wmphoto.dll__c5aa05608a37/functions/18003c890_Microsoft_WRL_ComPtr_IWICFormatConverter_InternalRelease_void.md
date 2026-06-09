# Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)

- ea: `0x18003c890`
- end: `0x18003c8bd`
- name: `?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003d050`

## callees

- `0x18003c890`
- `0x180044010`

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
0x18003c890  sub     rsp, 28h
0x18003c894  mov     rax, rcx
0x18003c897  xor     edx, edx
0x18003c899  mov     rcx, [rcx]
0x18003c89c  test    rcx, rcx
0x18003c89f  jz      short loc_18003C8B6
0x18003c8a1  mov     [rax], rdx
0x18003c8a4  mov     rax, [rcx]
0x18003c8a7  mov     rax, [rax+10h]
0x18003c8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8b0  nop
0x18003c8b1  add     rsp, 28h
0x18003c8b5  retn
0x18003c8b6  mov     eax, edx
0x18003c8b8  add     rsp, 28h
0x18003c8bc  retn
```
