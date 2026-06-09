# URI_LOCK_LIST::Initialize(ushort const *)

- ea: `0x180003aa0`
- end: `0x180003ab6`
- name: `?Initialize@URI_LOCK_LIST@@UEAAJPEBG@Z`
- size: `22`
- prototype: `__int64 __fastcall(URI_LOCK_LIST *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall URI_LOCK_LIST::Initialize(URI_LOCK_LIST *this, const unsigned __int16 *a2)
{
  __int64 result; // rax

  *((_QWORD *)this + 1) = a2;
  result = 0;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 7) = a2;
  *((_QWORD *)this + 94) = a2;
  return result;
}

```

## disassembly

```asm
0x180003aa0  mov     [rcx+8], rdx
0x180003aa4  xor     eax, eax
0x180003aa6  mov     [rcx+20h], rdx
0x180003aaa  mov     [rcx+38h], rdx
0x180003aae  mov     [rcx+2F0h], rdx
0x180003ab5  retn
```
