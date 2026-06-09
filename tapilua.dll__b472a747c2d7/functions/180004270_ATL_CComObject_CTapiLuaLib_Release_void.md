# ATL::CComObject<CTapiLuaLib>::Release(void)

- ea: `0x180004270`
- end: `0x1800042cd`
- name: `?Release@?$CComObject@VCTapiLuaLib@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001494`
- `0x180004270`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTapiLuaLib>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v2; // ebx

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v2 = v1 - 1;
    a1[2] = v2;
    if ( !v2 )
    {
      _InterlockedIncrement(&dword_18000A288);
      if ( a1 )
      {
        a1[2] = 1;
        *(_QWORD *)a1 = &ATL::CComObject<CTapiLuaLib>::`vftable';
        _InterlockedDecrement(&dword_18000A288);
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_18000A288);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180004270  push    rbx
0x180004272  sub     rsp, 20h
0x180004276  mov     ebx, [rcx+8]
0x180004279  cmp     ebx, 7FFFFFFFh
0x18000427f  jnz     short loc_180004288
0x180004281  mov     ebx, 7FFFFFFEh
0x180004286  jmp     short loc_1800042C5
0x180004288  sub     ebx, 1
0x18000428b  mov     [rcx+8], ebx
0x18000428e  jnz     short loc_1800042C5
0x180004290  lock inc cs:dword_18000A288
0x180004297  test    rcx, rcx
0x18000429a  jz      short loc_1800042BE
0x18000429c  lea     rax, ??_7?$CComObject@VCTapiLuaLib@@@ATL@@6B@; const ATL::CComObject<CTapiLuaLib>::`vftable'
0x1800042a3  mov     dword ptr [rcx+8], 1
0x1800042aa  mov     [rcx], rax
0x1800042ad  mov     edx, 10h; unsigned __int64
0x1800042b2  lock dec cs:dword_18000A288
0x1800042b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800042be  lock dec cs:dword_18000A288
0x1800042c5  mov     eax, ebx
0x1800042c7  add     rsp, 20h
0x1800042cb  pop     rbx
0x1800042cc  retn
```
