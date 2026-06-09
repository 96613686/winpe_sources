# ThreadPoolSetInfo(THREAD_POOL_INFO,unsigned __int64)

- ea: `0x1800013b0`
- end: `0x1800013e5`
- name: `?ThreadPoolSetInfo@@YA_KW4THREAD_POOL_INFO@@_K@Z`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800013b0`

## pseudocode

```c
__int64 __fastcall ThreadPoolSetInfo(int a1, __int64 a2)
{
  __int64 result; // rax

  if ( !g_pThreadPool )
    return a2;
  result = 0;
  if ( a1 )
  {
    if ( a1 == 1 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)g_pThreadPool + 56LL));
      return 1;
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)g_pThreadPool + 56LL));
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800013b0  mov     r8, cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA; THREAD_POOL * g_pThreadPool
0x1800013b7  test    r8, r8
0x1800013ba  jz      short loc_1800013E1
0x1800013bc  xor     eax, eax
0x1800013be  test    ecx, ecx
0x1800013c0  jnz     short loc_1800013CF
0x1800013c2  mov     rax, [r8]
0x1800013c5  lock inc dword ptr [rax+38h]
0x1800013c9  mov     eax, 1
0x1800013ce  retn
0x1800013cf  cmp     ecx, 1
0x1800013d2  jnz     short locret_1800013CE
0x1800013d4  mov     rax, [r8]
0x1800013d7  lock dec dword ptr [rax+38h]
0x1800013db  mov     eax, 1
0x1800013e0  retn
0x1800013e1  mov     rax, rdx
0x1800013e4  retn
```
