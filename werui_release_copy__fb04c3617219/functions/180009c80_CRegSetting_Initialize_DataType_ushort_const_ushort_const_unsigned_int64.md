# CRegSetting::Initialize(_DataType,ushort const *,ushort const *,unsigned __int64)

- ea: `0x180009c80`
- end: `0x180009ce9`
- name: `?Initialize@CRegSetting@@QEAAJW4_DataType@@PEBG1_K@Z`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a8f4`
- `0x18000b334`
- `0x1800148a8`

## callees

- `0x1800096a8`
- `0x180009c80`

## pseudocode

```c
__int64 __fastcall CRegSetting::Initialize(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax

  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a1 + 32,
                           a3)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a1 + 64,
                           a4) )
  {
    return 2147500037LL;
  }
  *(_QWORD *)(a1 + 96) = a5;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 8);
  result = 0;
  *(_WORD *)a1 = 256;
  *(_DWORD *)(a1 + 4) = a2;
  return result;
}

```

## disassembly

```asm
0x180009c80  mov     [rsp+arg_0], rbx
0x180009c85  mov     [rsp+arg_8], rsi
0x180009c8a  push    rdi
0x180009c8b  sub     rsp, 20h
0x180009c8f  mov     edi, edx
0x180009c91  mov     rbx, rcx
0x180009c94  add     rcx, 20h ; ' '
0x180009c98  mov     rdx, r8
0x180009c9b  mov     rsi, r9
0x180009c9e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180009ca3  test    al, al
0x180009ca5  jz      short loc_180009CD4
0x180009ca7  lea     rcx, [rbx+40h]
0x180009cab  mov     rdx, rsi
0x180009cae  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180009cb3  test    al, al
0x180009cb5  jz      short loc_180009CD4
0x180009cb7  mov     rax, [rsp+28h+arg_20]
0x180009cbc  mov     [rbx+60h], rax
0x180009cc0  mov     rax, [rbx+8]
0x180009cc4  mov     [rbx+10h], rax
0x180009cc8  xor     eax, eax
0x180009cca  mov     word ptr [rbx], 100h
0x180009ccf  mov     [rbx+4], edi
0x180009cd2  jmp     short loc_180009CD9
0x180009cd4  mov     eax, 80004005h
0x180009cd9  mov     rbx, [rsp+28h+arg_0]
0x180009cde  mov     rsi, [rsp+28h+arg_8]
0x180009ce3  add     rsp, 20h
0x180009ce7  pop     rdi
0x180009ce8  retn
```
