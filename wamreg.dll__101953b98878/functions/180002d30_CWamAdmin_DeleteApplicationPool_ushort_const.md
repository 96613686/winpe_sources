# CWamAdmin::DeleteApplicationPool(ushort const *)

- ea: `0x180002d30`
- end: `0x180002e75`
- name: `?DeleteApplicationPool@CWamAdmin@@UEAAJPEBG@Z`
- size: `325`
- prototype: `__int64 __fastcall(CWamAdmin *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180002d30`
- `0x180002e7c`
- `0x180007010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002e60`
- `OLEAUT32!__imp_SysFreeString` at `0x180002e60`
- `OLEAUT32!__imp_SysStringLen` at `0x180002dad`
- `OLEAUT32!__imp_SysStringLen` at `0x180002dad`

## pseudocode

```c
__int64 __fastcall CWamAdmin::DeleteApplicationPool(CWamAdmin *this, const unsigned __int16 *a2)
{
  int v4; // ebx
  LPVOID v5; // rsi
  int v7; // [rsp+68h] [rbp+28h] BYREF
  BSTR pbstr; // [rsp+70h] [rbp+30h] BYREF

  v7 = 0;
  pbstr = 0;
  if ( a2 )
  {
    v4 = DoesAppPoolExist(a2, &v7);
    if ( v4 >= 0 )
    {
      if ( v7 )
      {
        v4 = (*(__int64 (__fastcall **)(CWamAdmin *, const unsigned __int16 *, BSTR *))(*(_QWORD *)this + 56LL))(
               this,
               a2,
               &pbstr);
        if ( v4 >= 0 )
        {
          if ( SysStringLen(pbstr) < 2 || *pbstr || pbstr[1] )
          {
            v4 = -2147020589;
          }
          else
          {
            v5 = WamRegMetabaseConfig::m_pMetabase;
            v7 = 0;
            v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                            + 136LL))(
                   WamRegMetabaseConfig::m_pMetabase,
                   0,
                   L"/LM/W3SVC/AppPools/");
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *))(*(_QWORD *)v5 + 32LL))(
                     v5,
                     (unsigned int)v7,
                     a2);
              if ( v4 >= 0 )
                v4 = 0;
            }
            if ( v7 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 144LL))(v5);
            if ( v4 >= 0 )
              v4 = 0;
          }
        }
      }
      else
      {
        v4 = -2147023728;
      }
    }
    if ( pbstr )
      SysFreeString(pbstr);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002d30  mov     [rsp-18h+arg_0], rbx
0x180002d35  push    rbp
0x180002d36  push    rsi
0x180002d37  push    rdi
0x180002d38  mov     rbp, rsp
0x180002d3b  sub     rsp, 40h
0x180002d3f  mov     [rbp+arg_8], 0
0x180002d46  mov     rdi, rdx
0x180002d49  mov     [rbp+pbstr], 0
0x180002d51  mov     rsi, rcx
0x180002d54  test    rdx, rdx
0x180002d57  jnz     short loc_180002D63
0x180002d59  mov     ebx, 80070057h
0x180002d5e  jmp     loc_180002E66
0x180002d63  lea     rdx, [rbp+arg_8]; int *
0x180002d67  mov     rcx, rdi; unsigned __int16 *
0x180002d6a  call    ?DoesAppPoolExist@@YAJPEBGPEAH@Z; DoesAppPoolExist(ushort const *,int *)
0x180002d6f  mov     ebx, eax
0x180002d71  test    eax, eax
0x180002d73  js      loc_180002E57
0x180002d79  cmp     [rbp+arg_8], 0
0x180002d7d  jnz     short loc_180002D89
0x180002d7f  mov     ebx, 80070490h
0x180002d84  jmp     loc_180002E57
0x180002d89  mov     rax, [rsi]
0x180002d8c  lea     r8, [rbp+pbstr]
0x180002d90  mov     rdx, rdi
0x180002d93  mov     rcx, rsi
0x180002d96  mov     rax, [rax+38h]
0x180002d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d9f  mov     ebx, eax
0x180002da1  test    eax, eax
0x180002da3  js      loc_180002E57
0x180002da9  mov     rcx, [rbp+pbstr]; pbstr
0x180002dad  call    cs:__imp_SysStringLen
0x180002db3  mov     r9d, 2
0x180002db9  cmp     eax, r9d
0x180002dbc  jb      loc_180002E52
0x180002dc2  mov     rcx, [rbp+pbstr]
0x180002dc6  xor     eax, eax
0x180002dc8  cmp     ax, [rcx]
0x180002dcb  jnz     loc_180002E52
0x180002dd1  cmp     ax, [rcx+2]
0x180002dd5  jnz     short loc_180002E52
0x180002dd7  mov     rsi, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180002dde  lea     rcx, [rbp+arg_8]
0x180002de2  mov     [rbp+arg_8], eax
0x180002de5  lea     r8, aLmW3svcApppool; "/LM/W3SVC/AppPools/"
0x180002dec  mov     [rsp+40h+var_18], rcx
0x180002df1  xor     edx, edx
0x180002df3  mov     rcx, rsi
0x180002df6  mov     [rsp+40h+var_20], 7530h
0x180002dfe  mov     rax, [rsi]
0x180002e01  mov     rax, [rax+88h]
0x180002e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e0d  mov     ebx, eax
0x180002e0f  test    eax, eax
0x180002e11  js      short loc_180002E31
0x180002e13  mov     rax, [rsi]
0x180002e16  mov     r8, rdi
0x180002e19  mov     edx, [rbp+arg_8]
0x180002e1c  mov     rcx, rsi
0x180002e1f  mov     rax, [rax+20h]
0x180002e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e28  mov     ebx, eax
0x180002e2a  xor     eax, eax
0x180002e2c  test    ebx, ebx
0x180002e2e  cmovns  ebx, eax
0x180002e31  mov     edx, [rbp+arg_8]
0x180002e34  test    edx, edx
0x180002e36  jz      short loc_180002E4A
0x180002e38  mov     rax, [rsi]
0x180002e3b  mov     rcx, rsi
0x180002e3e  mov     rax, [rax+90h]
0x180002e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4a  test    ebx, ebx
0x180002e4c  js      short loc_180002E57
0x180002e4e  xor     ebx, ebx
0x180002e50  jmp     short loc_180002E57
0x180002e52  mov     ebx, 800710D3h
0x180002e57  mov     rcx, [rbp+pbstr]; bstrString
0x180002e5b  test    rcx, rcx
0x180002e5e  jz      short loc_180002E66
0x180002e60  call    cs:__imp_SysFreeString
0x180002e66  mov     eax, ebx
0x180002e68  mov     rbx, [rsp+40h+arg_0]
0x180002e6d  add     rsp, 40h
0x180002e71  pop     rdi
0x180002e72  pop     rsi
0x180002e73  pop     rbp
0x180002e74  retn
```
