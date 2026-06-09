# CWsmTrackingConfig::GetDataSize(void)

- ea: `0x14000aad0`
- end: `0x14000ab0e`
- name: `?GetDataSize@CWsmTrackingConfig@@UEBA?BKXZ`
- size: `62`
- prototype: `unsigned int __fastcall(CWsmTrackingConfig *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000aad0`
- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::GetDataSize(__int64 (__fastcall ***this)(char *))
{
  __int64 v2; // rax
  unsigned int v3; // ecx

  v2 = (**(this - 1))((char *)this - 8);
  v3 = 0;
  if ( v2 && (*(_QWORD *)v2 || *(_QWORD *)(v2 + 8) || *(_DWORD *)(v2 + 16)) )
    return (unsigned int)(*((_DWORD *)this + 4) - *((_DWORD *)this + 2));
  return v3;
}

```

## disassembly

```asm
0x14000aad0  push    rbx
0x14000aad2  sub     rsp, 20h
0x14000aad6  mov     rbx, rcx
0x14000aad9  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000aadd  mov     rax, [rcx]
0x14000aae0  mov     rax, [rax]
0x14000aae3  call    _guard_dispatch_icall
0x14000aae8  xor     ecx, ecx
0x14000aaea  test    rax, rax
0x14000aaed  jz      short loc_14000AB05
0x14000aaef  cmp     [rax], rcx
0x14000aaf2  jnz     short loc_14000AAFF
0x14000aaf4  cmp     [rax+8], rcx
0x14000aaf8  jnz     short loc_14000AAFF
0x14000aafa  cmp     [rax+10h], ecx
0x14000aafd  jz      short loc_14000AB05
0x14000aaff  mov     ecx, [rbx+10h]
0x14000ab02  sub     ecx, [rbx+8]
0x14000ab05  mov     eax, ecx
0x14000ab07  add     rsp, 20h
0x14000ab0b  pop     rbx
0x14000ab0c  retn
```
