# CWsmLogConfig::GetDataSize(void)

- ea: `0x14000aa90`
- end: `0x14000aac9`
- name: `?GetDataSize@CWsmLogConfig@@UEBA?BKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CWsmLogConfig *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000aa90`
- `0x14000f9e0`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::GetDataSize(__int64 (__fastcall ***this)(char *))
{
  _QWORD *v2; // rax
  unsigned int v3; // ecx

  v2 = (_QWORD *)(**(this - 1))((char *)this - 8);
  v3 = 0;
  if ( v2 && *v2 || v2[1] )
    return (unsigned int)(*((_DWORD *)this + 4) - *((_DWORD *)this + 2));
  return v3;
}

```

## disassembly

```asm
0x14000aa90  push    rbx
0x14000aa92  sub     rsp, 20h
0x14000aa96  mov     rbx, rcx
0x14000aa99  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000aa9d  mov     rax, [rcx]
0x14000aaa0  mov     rax, [rax]
0x14000aaa3  call    _guard_dispatch_icall
0x14000aaa8  xor     ecx, ecx
0x14000aaaa  test    rax, rax
0x14000aaad  jz      short loc_14000AAB4
0x14000aaaf  cmp     [rax], rcx
0x14000aab2  jnz     short loc_14000AABA
0x14000aab4  cmp     [rax+8], rcx
0x14000aab8  jbe     short loc_14000AAC0
0x14000aaba  mov     ecx, [rbx+10h]
0x14000aabd  sub     ecx, [rbx+8]
0x14000aac0  mov     eax, ecx
0x14000aac2  add     rsp, 20h
0x14000aac6  pop     rbx
0x14000aac7  retn
```
