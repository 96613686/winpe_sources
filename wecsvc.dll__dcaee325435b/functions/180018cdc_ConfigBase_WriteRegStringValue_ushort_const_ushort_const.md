# ConfigBase::WriteRegStringValue(ushort const *,ushort const *)

- ea: `0x180018cdc`
- end: `0x180018d42`
- name: `?WriteRegStringValue@ConfigBase@@IEBAXPEBG0@Z`
- size: `102`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800165c0`

## callees

- `0x180003810`
- `0x1800062d4`
- `0x180012b94`
- `0x18001fe50`

## pseudocode

```c
void __fastcall ConfigBase::WriteRegStringValue(HKEY *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v5[4]; // [rsp+20h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v5, (__int64)a3);
  RegWriteStringValue(this[2], a2, v5);
  std::wstring::_Tidy(v5, 1, 0);
}

```

## disassembly

```asm
0x180018cdc  mov     [rsp+arg_18], rbx
0x180018ce1  push    rdi
0x180018ce2  sub     rsp, 50h
0x180018ce6  mov     rax, cs:__security_cookie
0x180018ced  xor     rax, rsp
0x180018cf0  mov     [rsp+58h+var_18], rax
0x180018cf5  mov     rdi, rdx
0x180018cf8  mov     rbx, rcx
0x180018cfb  mov     rdx, r8
0x180018cfe  lea     rcx, [rsp+58h+var_38]
0x180018d03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018d08  nop
0x180018d09  lea     r8, [rsp+58h+var_38]
0x180018d0e  mov     rdx, rdi
0x180018d11  mov     rcx, [rbx+10h]
0x180018d15  call    ?RegWriteStringValue@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegWriteStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x180018d1a  nop
0x180018d1b  xor     r8d, r8d
0x180018d1e  mov     dl, 1
0x180018d20  lea     rcx, [rsp+58h+var_38]
0x180018d25  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018d2a  mov     rcx, [rsp+58h+var_18]
0x180018d2f  xor     rcx, rsp; StackCookie
0x180018d32  call    __security_check_cookie
0x180018d37  mov     rbx, [rsp+58h+arg_18]
0x180018d3c  add     rsp, 50h
0x180018d40  pop     rdi
0x180018d41  retn
```
