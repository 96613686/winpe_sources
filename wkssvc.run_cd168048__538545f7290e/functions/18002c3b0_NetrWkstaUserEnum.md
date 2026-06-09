# NetrWkstaUserEnum

- ea: `0x18002c3b0`
- end: `0x18002c4b3`
- name: `NetrWkstaUserEnum`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000a240`
- `0x18000b860`
- `0x18000d584`
- `0x18002c3b0`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18002c494`
- `SspiCli!LsaFreeReturnBuffer` at `0x18002c494`

## string_xrefs

- `0x18002c404`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaUserEnum(__int64 a1, __int64 a2, int a3, _DWORD *a4, __int64 a5)
{
  bool v5; // cc
  __int64 result; // rax
  __int64 v10; // rcx
  _QWORD *v11; // r9
  _DWORD *v12; // rax
  unsigned int v13; // ebx
  PVOID Buffer; // [rsp+58h] [rbp+10h] BYREF

  v5 = *(_DWORD *)a2 <= 1u;
  Buffer = 0;
  if ( !v5 )
    return 124;
  if ( !*(_QWORD *)(a2 + 8) )
    return 87;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  result = WsLsaEnumUsers(&Buffer);
  if ( !(_DWORD)result )
  {
    if ( Buffer )
    {
      v10 = *(_QWORD *)(a2 + 8);
      v11 = (_QWORD *)(v10 + 8);
      if ( *((_DWORD *)Buffer + 1) )
      {
        v13 = WsEnumUserInfo(*(_DWORD *)a2, a3, (_DWORD)Buffer, (_DWORD)v11, v10, (__int64)a4, a5);
      }
      else
      {
        *v11 = 0;
        v12 = *(_DWORD **)(a2 + 8);
        v13 = 0;
        *v12 = 0;
        *a4 = 0;
      }
      LsaFreeReturnBuffer(Buffer);
      return v13;
    }
    else
    {
      return 31;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c3b0  mov     [rsp+arg_0], rbx
0x18002c3b5  mov     [rsp+arg_10], rsi
0x18002c3ba  push    rdi
0x18002c3bb  sub     rsp, 40h
0x18002c3bf  cmp     dword ptr [rdx], 1
0x18002c3c2  mov     rdi, r9
0x18002c3c5  mov     esi, r8d
0x18002c3c8  mov     [rsp+48h+Buffer], 0
0x18002c3d1  mov     rbx, rdx
0x18002c3d4  jbe     short loc_18002C3E0
0x18002c3d6  mov     eax, 7Ch ; '|'
0x18002c3db  jmp     loc_18002C4A2
0x18002c3e0  cmp     qword ptr [rdx+8], 0
0x18002c3e5  jnz     short loc_18002C3F1
0x18002c3e7  mov     eax, 57h ; 'W'
0x18002c3ec  jmp     loc_18002C4A2
0x18002c3f1  mov     rax, cs:ConfigurationInfoSd
0x18002c3f8  lea     rcx, WsConfigInfoMapping
0x18002c3ff  mov     [rsp+48h+var_18], rcx
0x18002c404  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002c40b  mov     dword ptr [rsp+48h+var_20], 4
0x18002c413  mov     [rsp+48h+var_28], rax
0x18002c418  call    NetpAccessCheckAndAuditEx
0x18002c41d  test    eax, eax
0x18002c41f  jz      short loc_18002C428
0x18002c421  mov     eax, 5
0x18002c426  jmp     short loc_18002C4A2
0x18002c428  lea     rcx, [rsp+48h+Buffer]; ProtocolReturnBuffer
0x18002c42d  call    WsLsaEnumUsers
0x18002c432  test    eax, eax
0x18002c434  jnz     short loc_18002C4A2
0x18002c436  mov     r8, [rsp+48h+Buffer]
0x18002c43b  test    r8, r8
0x18002c43e  jnz     short loc_18002C446
0x18002c440  lea     eax, [r8+1Fh]
0x18002c444  jmp     short loc_18002C4A2
0x18002c446  cmp     dword ptr [r8+4], 0
0x18002c44b  mov     rcx, [rbx+8]
0x18002c44f  lea     r9, [rcx+8]
0x18002c453  jnz     short loc_18002C470
0x18002c455  mov     qword ptr [r9], 0
0x18002c45c  mov     rax, [rbx+8]
0x18002c460  xor     ebx, ebx
0x18002c462  mov     dword ptr [rax], 0
0x18002c468  mov     dword ptr [rdi], 0
0x18002c46e  jmp     short loc_18002C48F
0x18002c470  mov     rax, [rsp+48h+arg_20]
0x18002c475  mov     edx, esi
0x18002c477  mov     [rsp+48h+var_18], rax
0x18002c47c  mov     [rsp+48h+var_20], rdi
0x18002c481  mov     [rsp+48h+var_28], rcx
0x18002c486  mov     ecx, [rbx]
0x18002c488  call    WsEnumUserInfo
0x18002c48d  mov     ebx, eax
0x18002c48f  mov     rcx, [rsp+48h+Buffer]; Buffer
0x18002c494  call    cs:__imp_LsaFreeReturnBuffer
0x18002c49b  nop     dword ptr [rax+rax+00h]
0x18002c4a0  mov     eax, ebx
0x18002c4a2  mov     rbx, [rsp+48h+arg_0]
0x18002c4a7  mov     rsi, [rsp+48h+arg_10]
0x18002c4ac  add     rsp, 40h
0x18002c4b0  pop     rdi
0x18002c4b1  retn
```
