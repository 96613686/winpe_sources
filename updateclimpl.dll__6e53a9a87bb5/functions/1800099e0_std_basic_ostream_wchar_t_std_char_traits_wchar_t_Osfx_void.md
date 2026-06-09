# std::basic_ostream<wchar_t,std::char_traits<wchar_t>>::_Osfx(void)

- ea: `0x1800099e0`
- end: `0x180009a31`
- name: `?_Osfx@?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAXXZ`
- size: `81`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008f78`
- `0x180009320`
- `0x180009534`
- `0x18000960c`
- `0x1800096f4`

## callees

- `0x1800097f4`
- `0x1800099e0`
- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall std::wostream::_Osfx(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  result = *a1;
  v3 = *(int *)(*a1 + 4);
  if ( !*(_DWORD *)((char *)a1 + v3 + 16) && (*((_BYTE *)a1 + v3 + 24) & 2) != 0 )
  {
    v4 = *(__int64 *)((char *)a1 + v3 + 72);
    try
    {
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 104LL))(v4);
      if ( (_DWORD)result == -1 )
        result = std::wios::setstate((char *)a1 + *(int *)(*a1 + 4), 4, 0);
    }
    catch ( ... )
    {
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800099e0  push    rbx
0x1800099e2  sub     rsp, 20h
0x1800099e6  mov     rbx, rcx
0x1800099e9  mov     rax, [rcx]
0x1800099ec  movsxd  rcx, dword ptr [rax+4]
0x1800099f0  cmp     dword ptr [rcx+rbx+10h], 0
0x1800099f5  jnz     short loc_180009A2B
0x1800099f7  test    byte ptr [rcx+rbx+18h], 2
0x1800099fc  jz      short loc_180009A2B
0x1800099fe  mov     rcx, [rcx+rbx+48h]
0x180009a03  mov     rax, [rcx]
0x180009a06  mov     rax, [rax+68h]
0x180009a0a  call    _guard_dispatch_icall
0x180009a0f  cmp     eax, 0FFFFFFFFh
0x180009a12  jnz     short loc_180009A2B
0x180009a14  mov     rax, [rbx]
0x180009a17  movsxd  rcx, dword ptr [rax+4]
0x180009a1b  add     rcx, rbx
0x180009a1e  xor     r8d, r8d
0x180009a21  lea     edx, [r8+4]
0x180009a25  call    ?setstate@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAAXH_N@Z; std::wios::setstate(int,bool)
0x180009a2a  nop
0x180009a2b  add     rsp, 20h
0x180009a2f  pop     rbx
0x180009a30  retn
```
