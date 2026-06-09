# THREAD_POOL::SetInfo(THREAD_POOL_INFO,unsigned __int64)

- ea: `0x1800013f0`
- end: `0x180001416`
- name: `?SetInfo@THREAD_POOL@@QEAA_KW4THREAD_POOL_INFO@@_K@Z`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013f0`

## pseudocode

```c
__int64 __fastcall THREAD_POOL::SetInfo(__int64 a1, int a2)
{
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)a1 + 56LL));
      return 1;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a1 + 56LL));
    return 1;
  }
}

```

## disassembly

```asm
0x1800013f0  test    edx, edx
0x1800013f2  jnz     short loc_180001401
0x1800013f4  mov     rax, [rcx]
0x1800013f7  lock inc dword ptr [rax+38h]
0x1800013fb  mov     eax, 1
0x180001400  retn
0x180001401  cmp     edx, 1
0x180001404  jnz     short loc_180001413
0x180001406  mov     rax, [rcx]
0x180001409  lock dec dword ptr [rax+38h]
0x18000140d  mov     eax, 1
0x180001412  retn
0x180001413  xor     eax, eax
0x180001415  retn
```
