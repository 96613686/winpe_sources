# GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18001a8d0`
- end: `0x18001a9aa`
- name: `?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001acac`

## callees

- `0x180007a70`
- `0x180008a90`
- `0x18001728c`
- `0x1800185e8`
- `0x180018d84`
- `0x18001a8d0`
- `0x18001b070`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x18001a931`
- `MobileNetworking!GetPersistentRegPath` at `0x18001a931`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetPersistentRegPathWstring(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  unsigned int PersistentRegPath; // eax
  unsigned int v11; // ebx
  unsigned int v12; // ecx
  int v14; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+28h] [rbp-30h] BYREF

  std::wstring::wstring(v15);
  v4 = 0;
  v5 = 512;
  v14 = 512;
  try
  {
    while ( 1 )
    {
      std::wstring::resize(v15, v5);
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15, v6, v7, v8);
      PersistentRegPath = GetPersistentRegPath(13, L"Policy", &v14, v9);
      v11 = PersistentRegPath;
      if ( PersistentRegPath != 234 )
        break;
      v12 = v4++;
      if ( v12 >= 3 )
        break;
      v5 = v14;
    }
    if ( !PersistentRegPath )
    {
      std::wstring::resize(v15, (unsigned int)(v14 - 1));
      std::wstring::operator=(a3, v15);
    }
    std::wstring::_Tidy_deallocate(v15);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return v11;
}

```

## disassembly

```asm
0x18001a8d0  mov     [rsp+arg_0], rbx
0x18001a8d5  mov     [rsp+arg_8], rsi
0x18001a8da  push    rdi
0x18001a8db  sub     rsp, 50h
0x18001a8df  mov     rax, cs:__security_cookie
0x18001a8e6  xor     rax, rsp
0x18001a8e9  mov     [rsp+58h+var_10], rax
0x18001a8ee  mov     rsi, r8
0x18001a8f1  lea     rcx, [rsp+58h+var_30]
0x18001a8f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a8fb  nop
0x18001a8fc  xor     edi, edi
0x18001a8fe  mov     eax, 200h
0x18001a903  mov     [rsp+58h+var_38], eax
0x18001a907  mov     edx, eax
0x18001a909  lea     rcx, [rsp+58h+var_30]
0x18001a90e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001a913  lea     rcx, [rsp+58h+var_30]
0x18001a918  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a91d  mov     r9, rax
0x18001a920  lea     r8, [rsp+58h+var_38]
0x18001a925  lea     rdx, ?c_szWcmPoliciesRootSubkey@@3QBGB; "Policy"
0x18001a92c  mov     ecx, 0Dh
0x18001a931  call    cs:__imp_GetPersistentRegPath
0x18001a938  nop     dword ptr [rax+rax+00h]
0x18001a93d  mov     ebx, eax
0x18001a93f  cmp     eax, 0EAh
0x18001a944  jnz     short loc_18001A955
0x18001a946  mov     ecx, edi
0x18001a948  inc     edi
0x18001a94a  cmp     ecx, 3
0x18001a94d  jnb     short loc_18001A955
0x18001a94f  mov     eax, [rsp+58h+var_38]
0x18001a953  jmp     short loc_18001A907
0x18001a955  test    eax, eax
0x18001a957  jnz     short loc_18001A977
0x18001a959  mov     edx, [rsp+58h+var_38]
0x18001a95d  dec     edx
0x18001a95f  lea     rcx, [rsp+58h+var_30]
0x18001a964  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001a969  lea     rdx, [rsp+58h+var_30]
0x18001a96e  mov     rcx, rsi
0x18001a971  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001a976  nop
0x18001a977  lea     rcx, [rsp+58h+var_30]
0x18001a97c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a981  nop
0x18001a982  jmp     short loc_18001A98A
0x18001a984  jmp     short $+2
0x18001a986  mov     ebx, [rsp+58h+var_38]
0x18001a98a  mov     eax, ebx
0x18001a98c  mov     rcx, [rsp+58h+var_10]
0x18001a991  xor     rcx, rsp; StackCookie
0x18001a994  call    __security_check_cookie
0x18001a999  mov     rbx, [rsp+58h+arg_0]
0x18001a99e  mov     rsi, [rsp+58h+arg_8]
0x18001a9a3  add     rsp, 50h
0x18001a9a7  pop     rdi
0x18001a9a8  retn
```
