# tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___

- ea: `0x18002ccf8`
- end: `0x18002cd60`
- name: `tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d1f0`

## callees

- `0x18002ccf8`
- `0x18002dafc`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cd34`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002cd34`

## pseudocode

```c
void __fastcall tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___(
        __int64 **a1)
{
  unsigned int i; // edi
  __int64 v3; // r8
  __int64 v4; // rcx
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  unsigned int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)a1 + 24) )
  {
    for ( i = 0; i < *(_DWORD *)a1[2]; ++i )
    {
      v3 = 32LL * i;
      v4 = **a1;
      v5 = *(const WCHAR **)(v3 + v4);
      if ( v5 != *(const WCHAR **)(v3 + v4 + 8) )
      {
        v6 = RegDeleteKeyW((HKEY)*a1[1], v5);
        if ( v6 )
          wil::details::in1diag3::_Log_Win32(retaddr, v7, v8, (const char *)v6, v9);
      }
    }
  }
}

```

## disassembly

```asm
0x18002ccf8  mov     [rsp+arg_0], rbx
0x18002ccfd  push    rdi; unsigned int
0x18002ccfe  sub     rsp, 20h
0x18002cd02  cmp     byte ptr [rcx+18h], 0
0x18002cd06  mov     rbx, rcx
0x18002cd09  jz      short loc_18002CD55
0x18002cd0b  mov     rax, [rcx+10h]
0x18002cd0f  xor     edi, edi
0x18002cd11  cmp     [rax], edi
0x18002cd13  jbe     short loc_18002CD55
0x18002cd15  mov     rax, [rbx]
0x18002cd18  mov     r8d, edi
0x18002cd1b  shl     r8, 5
0x18002cd1f  mov     rcx, [rax]
0x18002cd22  mov     rdx, [r8+rcx]; lpSubKey
0x18002cd26  cmp     rdx, [r8+rcx+8]
0x18002cd2b  jz      short loc_18002CD4B
0x18002cd2d  mov     rcx, [rbx+8]
0x18002cd31  mov     rcx, [rcx]; hKey
0x18002cd34  call    cs:__imp_RegDeleteKeyW
0x18002cd3a  test    eax, eax
0x18002cd3c  jz      short loc_18002CD4B
0x18002cd3e  mov     rcx, [rsp+28h]; this
0x18002cd43  mov     r9d, eax; char *
0x18002cd46  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002cd4b  mov     rax, [rbx+10h]
0x18002cd4f  inc     edi
0x18002cd51  cmp     edi, [rax]
0x18002cd53  jb      short loc_18002CD15
0x18002cd55  mov     rbx, [rsp+28h+arg_0]
0x18002cd5a  add     rsp, 20h
0x18002cd5e  pop     rdi
0x18002cd5f  retn
```
