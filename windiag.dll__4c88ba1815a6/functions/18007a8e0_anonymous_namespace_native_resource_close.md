# _anonymous_namespace_::native_resource_close

- ea: `0x18007a8e0`
- end: `0x18007a9a3`
- name: `_anonymous_namespace_::native_resource_close`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180008660`
- `0x1800431c0`
- `0x18007a8e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a96c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a96c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a987`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a948`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007a948`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a95a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007a95a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a938`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a938`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::native_resource_close(struct lua_State *a1)
{
  HMODULE *v1; // rdi
  HMODULE v2; // rcx
  __int64 v3; // rbx
  bool v4; // zf

  v1 = (HMODULE *)luaL_checkudata(a1, 1, "native.resource");
  if ( *((char *)v1 + 8) == -1 )
    std::_Variant_dispatcher_std::integer_sequence_unsigned___int64_0___::_Dispatch2_std::pair_void_const___unsigned___int64___lambda_0f2987df398fcf62c701e32323b26f6e__std::variant_std::vector_char_std::allocator_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____unsigned_long___int64_std::pair_void_const___unsigned___int64______1_();
  v2 = *v1;
  if ( *((_BYTE *)v1 + 8) )
  {
    if ( *((_BYTE *)v1 + 8) != 1 )
    {
      if ( *((_BYTE *)v1 + 8) == 2 )
      {
        v3 = 0;
        if ( v2 )
        {
          *v1 = 0;
          FreeLibrary(v2);
        }
      }
      else if ( *((_BYTE *)v1 + 8) == 3 )
      {
        v3 = 0;
        if ( v2 )
        {
          *v1 = 0;
          CloseServiceHandle((SC_HANDLE)v2);
        }
      }
      else
      {
        v3 = 0;
        if ( *((_BYTE *)v1 + 8) == 4 )
        {
          if ( v2 )
          {
            *v1 = 0;
            LocalFree(v2);
          }
        }
        else if ( v2 )
        {
          *v1 = 0;
          RegCloseKey((HKEY)v2);
        }
      }
      goto LABEL_19;
    }
    v3 = -1;
    v4 = v2 == (HMODULE)-1LL;
  }
  else
  {
    v3 = 0;
    v4 = v2 == 0;
  }
  if ( !v4 )
  {
    *v1 = (HMODULE)v3;
    CloseHandle(v2);
  }
LABEL_19:
  *v1 = (HMODULE)v3;
  return 0;
}

```

## disassembly

```asm
0x18007a8e0  mov     [rsp+arg_0], rbx
0x18007a8e5  push    rdi
0x18007a8e6  sub     rsp, 20h
0x18007a8ea  lea     r8, aNativeResource_0; "native.resource"
0x18007a8f1  mov     edx, 1; int
0x18007a8f6  call    ?luaL_checkudata@@YAPEAXPEAUlua_State@@HPEBD@Z; luaL_checkudata(lua_State *,int,char const *)
0x18007a8fb  mov     rdi, rax
0x18007a8fe  movsx   rax, byte ptr [rax+8]
0x18007a903  add     rax, 1
0x18007a907  jz      loc_18007A99D
0x18007a90d  mov     rcx, [rdi]; hObject
0x18007a910  sub     rax, 1
0x18007a914  jz      short loc_18007A97D
0x18007a916  sub     rax, 1
0x18007a91a  jz      short loc_18007A974
0x18007a91c  sub     rax, 1
0x18007a920  jz      short loc_18007A962
0x18007a922  sub     rax, 1
0x18007a926  jz      short loc_18007A950
0x18007a928  xor     ebx, ebx
0x18007a92a  cmp     rax, 1
0x18007a92e  jz      short loc_18007A940
0x18007a930  test    rcx, rcx
0x18007a933  jz      short loc_18007A98D
0x18007a935  mov     [rdi], rbx
0x18007a938  call    cs:__imp_RegCloseKey
0x18007a93e  jmp     short loc_18007A98D
0x18007a940  test    rcx, rcx
0x18007a943  jz      short loc_18007A98D
0x18007a945  mov     [rdi], rbx
0x18007a948  call    cs:__imp_LocalFree
0x18007a94e  jmp     short loc_18007A98D
0x18007a950  xor     ebx, ebx
0x18007a952  test    rcx, rcx
0x18007a955  jz      short loc_18007A98D
0x18007a957  mov     [rdi], rbx
0x18007a95a  call    cs:__imp_CloseServiceHandle
0x18007a960  jmp     short loc_18007A98D
0x18007a962  xor     ebx, ebx
0x18007a964  test    rcx, rcx
0x18007a967  jz      short loc_18007A98D
0x18007a969  mov     [rdi], rbx
0x18007a96c  call    cs:__imp_FreeLibrary
0x18007a972  jmp     short loc_18007A98D
0x18007a974  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007a978  cmp     rcx, rbx
0x18007a97b  jmp     short loc_18007A982
0x18007a97d  xor     ebx, ebx
0x18007a97f  test    rcx, rcx
0x18007a982  jz      short loc_18007A98D
0x18007a984  mov     [rdi], rbx
0x18007a987  call    cs:__imp_CloseHandle
0x18007a98d  mov     [rdi], rbx
0x18007a990  xor     eax, eax
0x18007a992  mov     rbx, [rsp+28h+arg_0]
0x18007a997  add     rsp, 20h
0x18007a99b  pop     rdi
0x18007a99c  retn
0x18007a99d  call    std___Variant_dispatcher_std__integer_sequence_unsigned___int64_0______Dispatch2_std__pair_void_const___unsigned___int64___lambda_0f2987df398fcf62c701e32323b26f6e__std__variant_std__vector_char_std__allocator_char____std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____unsigned_long___int64_std__pair_void_const___unsigned___int64______1_
```
