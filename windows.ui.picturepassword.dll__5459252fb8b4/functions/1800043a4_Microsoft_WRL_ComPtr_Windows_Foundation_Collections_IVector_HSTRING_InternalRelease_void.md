# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)

- ea: `0x1800043a4`
- end: `0x1800043c9`
- name: `?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `50`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005d48`
- `0x180005e70`
- `0x180006154`
- `0x1800066bc`
- `0x1800067b8`
- `0x180006880`
- `0x180006a80`
- `0x180006b10`
- `0x180006d54`
- `0x18000772c`
- `0x180007e30`
- `0x180008558`
- `0x18000ad34`
- `0x18000ba44`
- `0x18000ba94`
- `0x18000bb58`
- `0x18000bb80`
- `0x18000bbb0`
- `0x18000be48`
- `0x18000c180`
- `0x18000c2f0`
- `0x18000c558`
- `0x18000c824`
- `0x18000c9dc`
- `0x18000d11c`
- `0x18000d188`
- `0x18000d22c`
- `0x18000d370`
- `0x18000d430`
- `0x18000d4d0`
- `0x18000e850`
- `0x18000edcc`
- `0x18000ee20`
- `0x18000f670`
- `0x1800104d0`
- `0x180011170`
- `0x180011250`
- `0x180011b74`
- `0x180011e88`
- `0x180012068`
- `0x1800121f0`
- `0x180012d7c`
- `0x1800135c8`
- `0x1800136a8`
- `0x180013980`
- `0x180013b88`
- `0x180013cc0`
- `0x180015e38`
- `0x180015f2c`
- `0x180016fac`

## callees

- `0x1800043a4`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x1800043a4  sub     rsp, 28h
0x1800043a8  mov     rdx, rcx
0x1800043ab  xor     eax, eax
0x1800043ad  mov     rcx, [rcx]
0x1800043b0  test    rcx, rcx
0x1800043b3  jz      short loc_1800043C4
0x1800043b5  mov     [rdx], rax
0x1800043b8  mov     rax, [rcx]
0x1800043bb  mov     rax, [rax+10h]
0x1800043bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c4  add     rsp, 28h
0x1800043c8  retn
```
