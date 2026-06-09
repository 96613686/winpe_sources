# CSWbemSecurity::AdjustTokenPrivileges(void *,CSWbemPrivilegeSet *)

- ea: `0x180001b78`
- end: `0x180001d04`
- name: `?AdjustTokenPrivileges@CSWbemSecurity@@SAHPEAXPEAVCSWbemPrivilegeSet@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct CSWbemPrivilegeSet *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800036e0`
- `0x180006850`
- `0x180008230`
- `0x180008800`

## callees

- `0x180001b78`
- `0x180013920`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001cfc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180001cf3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180001cf3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001be9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001be9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001c8c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001c8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemSecurity::AdjustTokenPrivileges(HANDLE TokenHandle, struct CSWbemPrivilegeSet *a2)
{
  unsigned int v4; // r12d
  struct _TOKEN_PRIVILEGES *v5; // r15
  DWORD v6; // ebp
  __int64 v7; // rbx
  _QWORD *v8; // rsi
  LUID v9; // rdi
  __int64 v10; // rdx
  __int64 i; // rax
  __int16 v13; // [rsp+78h] [rbp+10h] BYREF
  int v14; // [rsp+80h] [rbp+18h] BYREF

  v4 = 0;
  if ( a2 )
  {
    (*(void (__fastcall **)(struct CSWbemPrivilegeSet *))(*(_QWORD *)a2 + 8LL))(a2);
    v14 = 0;
    (*(void (__fastcall **)(struct CSWbemPrivilegeSet *, int *))(*(_QWORD *)a2 + 72LL))(a2, &v14);
    if ( v14 )
    {
      v5 = (struct _TOKEN_PRIVILEGES *)CWin32DefaultArena::WbemMemAlloc(12LL * v14 + 16);
      if ( v5 )
      {
        v6 = 0;
        v7 = **((_QWORD **)a2 + 14);
        while ( v7 != *((_QWORD *)a2 + 14) )
        {
          v8 = *(_QWORD **)(v7 + 40);
          (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          v9 = (LUID)v8[13];
          v13 = 0;
          (*(void (__fastcall **)(_QWORD *, __int16 *))(*v8 + 56LL))(v8, &v13);
          v10 = v6;
          v5->Privileges[v10].Luid = v9;
          v5->Privileges[v10].Attributes = (v13 == -1) + 1;
          ++v6;
          (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
          if ( !*(_BYTE *)(v7 + 25) )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v7 + 16) + 25LL) )
            {
              for ( i = *(_QWORD *)(v7 + 8); !*(_BYTE *)(i + 25) && v7 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
                v7 = i;
            }
            else
            {
              i = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
            }
            v7 = i;
          }
        }
        if ( v6 )
        {
          v5->PrivilegeCount = v6;
          v4 = AdjustTokenPrivileges(TokenHandle, 0, v5, 0, 0, 0);
          GetLastError();
        }
        CWin32DefaultArena::WbemMemFree(v5);
      }
    }
    (*(void (__fastcall **)(struct CSWbemPrivilegeSet *))(*(_QWORD *)a2 + 16LL))(a2);
  }
  return v4;
}

```

## disassembly

```asm
0x180001b78  mov     [rsp+arg_0], rbx
0x180001b7d  push    rbp
0x180001b7e  push    rsi
0x180001b7f  push    rdi
0x180001b80  push    r12
0x180001b82  push    r13
0x180001b84  push    r14
0x180001b86  push    r15
0x180001b88  sub     rsp, 30h
0x180001b8c  mov     r14, rdx
0x180001b8f  mov     r13, rcx
0x180001b92  xor     edi, edi
0x180001b94  mov     r12d, edi
0x180001b97  test    rdx, rdx
0x180001b9a  jz      loc_180001CA2
0x180001ba0  mov     rax, [rdx]
0x180001ba3  mov     rcx, rdx
0x180001ba6  mov     rax, [rax+8]
0x180001baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001baf  mov     [rsp+68h+arg_10], edi
0x180001bb6  mov     rax, [r14]
0x180001bb9  lea     rdx, [rsp+68h+arg_10]
0x180001bc1  mov     rcx, r14
0x180001bc4  mov     rax, [rax+48h]
0x180001bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bcd  movsxd  rax, [rsp+68h+arg_10]
0x180001bd5  test    eax, eax
0x180001bd7  jz      loc_180001C93
0x180001bdd  lea     rcx, [rax+rax*2]
0x180001be1  lea     rcx, ds:10h[rcx*4]
0x180001be9  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180001bef  mov     r15, rax
0x180001bf2  test    rax, rax
0x180001bf5  jz      loc_180001C93
0x180001bfb  mov     ebp, edi
0x180001bfd  mov     rbx, [r14+70h]
0x180001c01  mov     rbx, [rbx]
0x180001c04  cmp     rbx, [r14+70h]
0x180001c08  jz      short loc_180001C85
0x180001c0a  mov     rsi, [rbx+28h]
0x180001c0e  mov     rax, [rsi]
0x180001c11  mov     rcx, rsi
0x180001c14  mov     rax, [rax+8]
0x180001c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c1d  mov     rdi, [rsi+68h]
0x180001c21  xor     eax, eax
0x180001c23  mov     [rsp+68h+arg_8], ax
0x180001c28  mov     rax, [rsi]
0x180001c2b  lea     rdx, [rsp+68h+arg_8]
0x180001c30  mov     rcx, rsi
0x180001c33  mov     rax, [rax+38h]
0x180001c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c3c  mov     eax, ebp
0x180001c3e  lea     rdx, [rax+rax*2]
0x180001c42  mov     [r15+rdx*4+4], rdi
0x180001c47  xor     edi, edi
0x180001c49  mov     eax, edi
0x180001c4b  or      ecx, 0FFFFFFFFh
0x180001c4e  cmp     cx, [rsp+68h+arg_8]
0x180001c53  setz    al
0x180001c56  inc     eax
0x180001c58  mov     [r15+rdx*4+0Ch], eax
0x180001c5d  inc     ebp
0x180001c5f  mov     rax, [rsi]
0x180001c62  mov     rcx, rsi
0x180001c65  mov     rax, [rax+10h]
0x180001c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c6e  cmp     [rbx+19h], dil
0x180001c72  jnz     short loc_180001C04
0x180001c74  mov     rcx, [rbx+10h]
0x180001c78  cmp     [rcx+19h], dil
0x180001c7c  jnz     short loc_180001CBA
0x180001c7e  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBW4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min(std::_Tree_node<std::pair<WbemPrivilegeEnum const,CSWbemPrivilege *>,void *> *)
0x180001c83  jmp     short loc_180001CD3
0x180001c85  test    ebp, ebp
0x180001c87  jnz     short loc_180001CDB
0x180001c89  mov     rcx, r15
0x180001c8c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180001c92  nop
0x180001c93  mov     rcx, [r14]
0x180001c96  mov     rax, [rcx+10h]
0x180001c9a  mov     rcx, r14
0x180001c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ca2  mov     eax, r12d
0x180001ca5  mov     rbx, [rsp+68h+arg_0]
0x180001caa  add     rsp, 30h
0x180001cae  pop     r15
0x180001cb0  pop     r14
0x180001cb2  pop     r13
0x180001cb4  pop     r12
0x180001cb6  pop     rdi
0x180001cb7  pop     rsi
0x180001cb8  pop     rbp
0x180001cb9  retn
0x180001cba  mov     rax, [rbx+8]
0x180001cbe  jmp     short loc_180001CCD
0x180001cc0  cmp     rbx, [rax+10h]
0x180001cc4  jnz     short loc_180001CD3
0x180001cc6  mov     rbx, rax
0x180001cc9  mov     rax, [rax+8]
0x180001ccd  cmp     [rax+19h], dil
0x180001cd1  jz      short loc_180001CC0
0x180001cd3  mov     rbx, rax
0x180001cd6  jmp     loc_180001C04
0x180001cdb  mov     [r15], ebp
0x180001cde  mov     [rsp+68h+ReturnLength], rdi; ReturnLength
0x180001ce3  mov     [rsp+68h+PreviousState], rdi; PreviousState
0x180001ce8  xor     r9d, r9d; BufferLength
0x180001ceb  mov     r8, r15; NewState
0x180001cee  xor     edx, edx; DisableAllPrivileges
0x180001cf0  mov     rcx, r13; TokenHandle
0x180001cf3  call    cs:__imp_AdjustTokenPrivileges
0x180001cf9  mov     r12d, eax
0x180001cfc  call    cs:__imp_GetLastError
0x180001d02  jmp     short loc_180001C89
```
