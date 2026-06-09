# IMPERSONATION_STACK::Pop(void)

- ea: `0x18001f9ac`
- end: `0x18001fa47`
- name: `?Pop@IMPERSONATION_STACK@@QEAAJXZ`
- size: `155`
- prototype: `__int64 __fastcall(IMPERSONATION_STACK *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001f588`
- `0x18001f76c`

## callees

- `0x180001214`
- `0x18001f9ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fa08`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fa08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa12`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fa2b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fa2b`

## pseudocode

```c
signed int __fastcall IMPERSONATION_STACK::Pop(IMPERSONATION_STACK *this)
{
  IMPERSONATION_STACK *v1; // rdi
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rbx
  signed int result; // eax
  void *v6; // rbx

  v1 = this;
  v2 = *((_QWORD *)this + 1);
  if ( !v2 )
    return -2147024809;
  v3 = *(_DWORD *)(v2 + 16);
  if ( !v3 )
    return -2147024809;
  *(_DWORD *)(v2 + 16) = v3 - 1;
  v4 = *((_QWORD *)v1 + 1);
  if ( *(_DWORD *)(v4 + 16) )
    return 0;
  if ( v4 )
  {
    *((_QWORD *)v1 + 1) = *(_QWORD *)v4;
    *(_QWORD *)v4 = 0;
  }
  operator delete(*((void **)v1 + 1));
  *((_QWORD *)v1 + 1) = v4;
  if ( v4 )
    v1 = (IMPERSONATION_STACK *)(v4 + 8);
  v6 = *(void **)v1;
  if ( RevertToSelf() )
  {
    if ( SetThreadToken(0, v6) )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18001f9ac  mov     [rsp+arg_0], rbx
0x18001f9b1  push    rdi
0x18001f9b2  sub     rsp, 20h
0x18001f9b6  mov     rdi, rcx
0x18001f9b9  mov     rcx, [rcx+8]
0x18001f9bd  test    rcx, rcx
0x18001f9c0  jz      short loc_18001FA37
0x18001f9c2  mov     eax, [rcx+10h]
0x18001f9c5  test    eax, eax
0x18001f9c7  jz      short loc_18001FA37
0x18001f9c9  dec     eax
0x18001f9cb  mov     [rcx+10h], eax
0x18001f9ce  mov     rbx, [rdi+8]
0x18001f9d2  cmp     dword ptr [rbx+10h], 0
0x18001f9d6  jbe     short loc_18001F9DC
0x18001f9d8  xor     eax, eax
0x18001f9da  jmp     short loc_18001FA3C
0x18001f9dc  test    rbx, rbx
0x18001f9df  jz      short loc_18001F9EF
0x18001f9e1  mov     rax, [rbx]
0x18001f9e4  mov     [rdi+8], rax
0x18001f9e8  mov     qword ptr [rbx], 0
0x18001f9ef  mov     rcx, [rdi+8]; Block
0x18001f9f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f9f8  mov     [rdi+8], rbx
0x18001f9fc  test    rbx, rbx
0x18001f9ff  jz      short loc_18001FA05
0x18001fa01  lea     rdi, [rbx+8]
0x18001fa05  mov     rbx, [rdi]
0x18001fa08  call    cs:__imp_RevertToSelf
0x18001fa0e  test    eax, eax
0x18001fa10  jnz     short loc_18001FA26
0x18001fa12  call    cs:__imp_GetLastError
0x18001fa18  test    eax, eax
0x18001fa1a  jle     short loc_18001FA3C
0x18001fa1c  movzx   eax, ax
0x18001fa1f  or      eax, 80070000h
0x18001fa24  jmp     short loc_18001FA3C
0x18001fa26  mov     rdx, rbx; Token
0x18001fa29  xor     ecx, ecx; Thread
0x18001fa2b  call    cs:__imp_SetThreadToken
0x18001fa31  test    eax, eax
0x18001fa33  jnz     short loc_18001F9D8
0x18001fa35  jmp     short loc_18001FA12
0x18001fa37  mov     eax, 80070057h
0x18001fa3c  mov     rbx, [rsp+28h+arg_0]
0x18001fa41  add     rsp, 20h
0x18001fa45  pop     rdi
0x18001fa46  retn
```
