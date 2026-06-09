# std::basic_filebuf<wchar_t,std::char_traits<wchar_t>>::_Endwrite(void)

- ea: `0x18000f5e4`
- end: `0x18000f6c4`
- name: `?_Endwrite@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@IEAA_NXZ`
- size: `224`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e460`
- `0x18000e530`
- `0x18000f6cc`

## callees

- `0x18000f5e4`
- `0x1800102a4`
- `0x180010310`
- `0x1800148e0`

## pseudocode

```c
bool __fastcall std::wfilebuf::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 114) )
    return 1;
  if ( (*(unsigned __int16 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF) == 0xFFFF )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, __int64 *, _BYTE **))(*(_QWORD *)v2 + 64LL))(
         v2,
         a1 + 116,
         v8,
         &v9,
         &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        *(_BYTE *)(a1 + 114) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 114) = 0;
  }
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 114) == 0;
  v6 = v7 - v8;
  if ( v6 == o_fwrite_0(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 114) == 0;
  return 0;
}

```

## disassembly

```asm
0x18000f5e4  mov     [rsp+arg_8], rbx
0x18000f5e9  push    rdi
0x18000f5ea  sub     rsp, 60h
0x18000f5ee  mov     rax, cs:__security_cookie
0x18000f5f5  xor     rax, rsp
0x18000f5f8  mov     [rsp+68h+var_10], rax
0x18000f5fd  cmp     qword ptr [rcx+68h], 0
0x18000f602  mov     rbx, rcx
0x18000f605  jz      short loc_18000F66C
0x18000f607  cmp     byte ptr [rcx+72h], 0
0x18000f60b  jz      short loc_18000F66C
0x18000f60d  mov     rax, [rcx]
0x18000f610  mov     edi, 0FFFFh
0x18000f615  mov     edx, edi
0x18000f617  mov     rax, [rax+18h]
0x18000f61b  call    _guard_dispatch_icall
0x18000f620  cmp     ax, di
0x18000f623  jz      loc_18000F6C0
0x18000f629  mov     rcx, [rbx+68h]
0x18000f62d  lea     r8, [rsp+68h+var_38]
0x18000f632  mov     [rsp+68h+var_38], 0
0x18000f63b  lea     rdx, [rbx+74h]
0x18000f63f  mov     [rsp+68h+var_48], r8
0x18000f644  lea     r9, [rsp+68h+var_10]
0x18000f649  lea     r8, [rsp+68h+var_30]
0x18000f64e  mov     rax, [rcx]
0x18000f651  mov     rax, [rax+40h]
0x18000f655  call    _guard_dispatch_icall
0x18000f65a  test    eax, eax
0x18000f65c  jz      short loc_18000F686
0x18000f65e  sub     eax, 1
0x18000f661  jz      short loc_18000F68A
0x18000f663  cmp     eax, 2
0x18000f666  jnz     short loc_18000F6C0
0x18000f668  mov     byte ptr [rbx+72h], 0
0x18000f66c  mov     al, 1
0x18000f66e  mov     rcx, [rsp+68h+var_10]
0x18000f673  xor     rcx, rsp; StackCookie
0x18000f676  call    __security_check_cookie
0x18000f67b  mov     rbx, [rsp+68h+arg_8]
0x18000f680  add     rsp, 60h
0x18000f684  pop     rdi
0x18000f685  retn
0x18000f686  mov     byte ptr [rbx+72h], 0
0x18000f68a  mov     rdi, [rsp+68h+var_38]
0x18000f68f  lea     rax, [rsp+68h+var_30]
0x18000f694  sub     rdi, rax
0x18000f697  jz      short loc_18000F6B7
0x18000f699  mov     r9, [rbx+80h]
0x18000f6a0  lea     rcx, [rsp+68h+var_30]
0x18000f6a5  mov     r8, rdi
0x18000f6a8  mov     edx, 1
0x18000f6ad  call    _o_fwrite_0
0x18000f6b2  cmp     rdi, rax
0x18000f6b5  jnz     short loc_18000F6C0
0x18000f6b7  cmp     byte ptr [rbx+72h], 0
0x18000f6bb  setz    al
0x18000f6be  jmp     short loc_18000F66E
0x18000f6c0  xor     al, al
0x18000f6c2  jmp     short loc_18000F66E
```
