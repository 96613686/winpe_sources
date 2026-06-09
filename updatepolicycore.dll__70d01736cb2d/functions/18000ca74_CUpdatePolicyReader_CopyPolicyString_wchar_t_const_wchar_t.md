# CUpdatePolicyReader::CopyPolicyString(wchar_t const *,wchar_t * *)

- ea: `0x18000ca74`
- end: `0x18000cb3b`
- name: `?CopyPolicyString@CUpdatePolicyReader@@AEAAJPEB_WPEAPEA_W@Z`
- size: `199`
- prototype: `__int64 __fastcall(CUpdatePolicyReader *this, const wchar_t *, wchar_t **)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cb70`
- `0x18000ce50`
- `0x18000ce90`

## callees

- `0x180008ec8`
- `0x18000ca74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb19`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUpdatePolicyReader::CopyPolicyString(CUpdatePolicyReader *this, const wchar_t *a2, wchar_t **a3)
{
  signed int v5; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rsi
  wchar_t *v9; // rax
  void *v10; // r11

  if ( a3 )
  {
    if ( a2 )
    {
      v6 = a2;
      v7 = 0x7FFFFFFF;
      do
      {
        if ( !*v6 )
          break;
        ++v6;
        --v7;
      }
      while ( v7 );
      v5 = v7 == 0 ? 0x80070057 : 0;
      v8 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
      if ( v7 )
      {
        v9 = (wchar_t *)CoTaskMemAlloc(2 * v8 + 2);
        if ( v9 )
        {
          v5 = StringCchCopyW(v9, v8 + 1, a2);
          if ( v5 < 0 )
            CoTaskMemFree(v10);
          else
            *a3 = (wchar_t *)v10;
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ca74  mov     [rsp+arg_0], rbx
0x18000ca79  mov     [rsp+arg_8], rbp
0x18000ca7e  push    rsi
0x18000ca7f  push    rdi
0x18000ca80  push    r14
0x18000ca82  sub     rsp, 20h
0x18000ca86  xor     ebp, ebp
0x18000ca88  mov     r14, r8
0x18000ca8b  mov     rdi, rdx
0x18000ca8e  test    r8, r8
0x18000ca91  jnz     short loc_18000CA9D
0x18000ca93  mov     ebx, 80004003h
0x18000ca98  jmp     loc_18000CB26
0x18000ca9d  test    rdi, rdi
0x18000caa0  jz      short loc_18000CB21
0x18000caa2  mov     edx, 7FFFFFFFh
0x18000caa7  mov     rax, rdi
0x18000caaa  mov     ecx, edx
0x18000caac  cmp     [rax], bp
0x18000caaf  jz      short loc_18000CABB
0x18000cab1  add     rax, 2
0x18000cab5  sub     rcx, 1
0x18000cab9  jnz     short loc_18000CAAC
0x18000cabb  mov     rax, rcx
0x18000cabe  neg     rax
0x18000cac1  mov     rax, rcx
0x18000cac4  sbb     ebx, ebx
0x18000cac6  sub     rdx, rcx
0x18000cac9  not     ebx
0x18000cacb  and     ebx, 80070057h
0x18000cad1  neg     rax
0x18000cad4  sbb     rsi, rsi
0x18000cad7  and     rsi, rdx
0x18000cada  test    rcx, rcx
0x18000cadd  jz      short loc_18000CB26
0x18000cadf  lea     rcx, ds:2[rsi*2]; cb
0x18000cae7  call    cs:__imp_CoTaskMemAlloc
0x18000caed  mov     r11, rax
0x18000caf0  test    rax, rax
0x18000caf3  jnz     short loc_18000CAFC
0x18000caf5  mov     ebx, 8007000Eh
0x18000cafa  jmp     short loc_18000CB26
0x18000cafc  lea     rdx, [rsi+1]; unsigned __int64
0x18000cb00  mov     r8, rdi; wchar_t *
0x18000cb03  mov     rcx, r11; wchar_t *
0x18000cb06  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000cb0b  mov     ebx, eax
0x18000cb0d  test    eax, eax
0x18000cb0f  js      short loc_18000CB16
0x18000cb11  mov     [r14], r11
0x18000cb14  jmp     short loc_18000CB26
0x18000cb16  mov     rcx, r11; pv
0x18000cb19  call    cs:__imp_CoTaskMemFree
0x18000cb1f  jmp     short loc_18000CB26
0x18000cb21  mov     ebx, 80070057h
0x18000cb26  mov     rbp, [rsp+38h+arg_8]
0x18000cb2b  mov     eax, ebx
0x18000cb2d  mov     rbx, [rsp+38h+arg_0]
0x18000cb32  add     rsp, 20h
0x18000cb36  pop     r14
0x18000cb38  pop     rdi
0x18000cb39  pop     rsi
0x18000cb3a  retn
```
