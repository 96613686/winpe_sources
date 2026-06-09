# CRegRpcEndpoint::AccessCheck(void)

- ea: `0x1800157c0`
- end: `0x1800158b7`
- name: `?AccessCheck@CRegRpcEndpoint@@QEAAKXZ`
- size: `247`
- prototype: `__int64 __fastcall(CRegRpcEndpoint *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800049b4`

## callees

- `0x1800157c0`
- `0x180015b70`
- `0x180015c50`
- `0x180015e4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001582a`
- `KERNEL32!GetLastError` at `0x18001582a`
- `KERNEL32!CloseHandle` at `0x180015898`
- `KERNEL32!CloseHandle` at `0x180015898`
- `KERNEL32!GetCurrentThread` at `0x1800157fb`
- `KERNEL32!GetCurrentThread` at `0x1800157fb`
- `ADVAPI32!OpenThreadToken` at `0x18001581a`
- `ADVAPI32!OpenThreadToken` at `0x18001581a`

## pseudocode

```c
__int64 __fastcall CRegRpcEndpoint::AccessCheck(CRegRpcEndpoint *this)
{
  unsigned int v1; // ebx
  _DWORD *v3; // rsi
  HANDLE CurrentThread; // rax
  CRegRpcEndpoint *v5; // rcx
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  TokenHandle = 0;
  if ( (*((_BYTE *)this + 80) & 2) == 0 )
  {
    v3 = (_DWORD *)((char *)this + 1820);
    if ( *((_QWORD *)this + 226) || *v3 )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x80000008, 1, &TokenHandle) )
      {
        if ( !*((_QWORD *)this + 226)
          || (v1 = CRegRpcEndpoint::SecDescAccessCheck(this, TokenHandle),
              !(unsigned int)ElValidateWin32_7(v1, v9, v10, 505)) )
        {
          if ( *v3 )
          {
            v1 = CRegRpcEndpoint::LocalAdminAccessCheck(v5, TokenHandle);
            ElValidateWin32_7(v1, v11, v12, 515);
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v1 = ElValidateWin32_7(LastError, v7, v8, 495);
      }
      if ( TokenHandle )
        CloseHandle(TokenHandle);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800157c0  mov     [rsp+arg_8], rbx
0x1800157c5  mov     [rsp+arg_10], rsi
0x1800157ca  push    rdi
0x1800157cb  sub     rsp, 20h
0x1800157cf  xor     ebx, ebx
0x1800157d1  mov     rdi, rcx
0x1800157d4  and     [rsp+28h+TokenHandle], rbx
0x1800157d9  test    byte ptr [rcx+50h], 2
0x1800157dd  jnz     loc_1800158A4
0x1800157e3  lea     rsi, [rcx+71Ch]
0x1800157ea  cmp     [rcx+710h], rbx
0x1800157f1  jnz     short loc_1800157FB
0x1800157f3  cmp     [rsi], ebx
0x1800157f5  jz      loc_1800158A4
0x1800157fb  call    cs:__imp_GetCurrentThread
0x180015802  nop     dword ptr [rax+rax+00h]
0x180015807  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001580c  mov     edx, 80000008h; DesiredAccess
0x180015811  mov     rcx, rax; ThreadHandle
0x180015814  mov     r8d, 1; OpenAsSelf
0x18001581a  call    cs:__imp_OpenThreadToken
0x180015821  nop     dword ptr [rax+rax+00h]
0x180015826  test    eax, eax
0x180015828  jnz     short loc_180015847
0x18001582a  call    cs:__imp_GetLastError
0x180015831  nop     dword ptr [rax+rax+00h]
0x180015836  mov     ecx, eax
0x180015838  mov     r9d, 1EFh
0x18001583e  call    ElValidateWin32_7
0x180015843  mov     ebx, eax
0x180015845  jmp     short loc_18001588E
0x180015847  cmp     [rdi+710h], rbx
0x18001584e  jz      short loc_180015870
0x180015850  mov     rdx, [rsp+28h+TokenHandle]; void *
0x180015855  mov     rcx, rdi; this
0x180015858  call    ?SecDescAccessCheck@CRegRpcEndpoint@@AEAAKPEAX@Z; CRegRpcEndpoint::SecDescAccessCheck(void *)
0x18001585d  mov     r9d, 1F9h
0x180015863  mov     ecx, eax
0x180015865  mov     ebx, eax
0x180015867  call    ElValidateWin32_7
0x18001586c  test    eax, eax
0x18001586e  jnz     short loc_18001588E
0x180015870  cmp     dword ptr [rsi], 0
0x180015873  jz      short loc_18001588E
0x180015875  mov     rdx, [rsp+28h+TokenHandle]; void *
0x18001587a  call    ?LocalAdminAccessCheck@CRegRpcEndpoint@@AEAAKPEAX@Z; CRegRpcEndpoint::LocalAdminAccessCheck(void *)
0x18001587f  mov     r9d, 203h
0x180015885  mov     ecx, eax
0x180015887  mov     ebx, eax
0x180015889  call    ElValidateWin32_7
0x18001588e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180015893  test    rcx, rcx
0x180015896  jz      short loc_1800158A4
0x180015898  call    cs:__imp_CloseHandle
0x18001589f  nop     dword ptr [rax+rax+00h]
0x1800158a4  mov     rsi, [rsp+28h+arg_10]
0x1800158a9  mov     eax, ebx
0x1800158ab  mov     rbx, [rsp+28h+arg_8]
0x1800158b0  add     rsp, 20h
0x1800158b4  pop     rdi
0x1800158b5  retn
```
