# CProfileAccounts::FindByRID(ulong,IPropertyStore * *)

- ea: `0x180007bf0`
- end: `0x180007caa`
- name: `?FindByRID@CProfileAccounts@@UEAAJKPEAPEAUIPropertyStore@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(CProfileAccounts *__hidden this, unsigned int, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007970`
- `0x180007bf0`
- `0x180007cb0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180007c58`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180007c58`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180007c66`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180007c66`

## pseudocode

```c
int __fastcall CProfileAccounts::FindByRID(CProfileAccounts *this, int a2, struct IPropertyStore **a3)
{
  int result; // eax
  int i; // ebx
  __int64 v8; // rax
  int v9; // ecx
  void *v10; // rdi
  DWORD v11; // eax
  PUCHAR SidSubAuthorityCount; // rax

  if ( !a3 )
    return -2147024809;
  *a3 = 0;
  result = CProfileAccounts::_Init(this);
  if ( result >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      v8 = *((_QWORD *)this + 2);
      v9 = v8 ? *(_DWORD *)v8 : 0;
      if ( i >= v9 )
        break;
      v10 = *(void **)(*(_QWORD *)(v8 + 8) + 8LL * i);
      v11 = 0;
      if ( v10 )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(v10);
        v11 = *GetSidSubAuthority(v10, (unsigned int)*SidSubAuthorityCount - 1);
      }
      if ( v11 == a2 )
        return CSGetProfilePropertyStore(v10, a3);
    }
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180007bf0  mov     [rsp+arg_10], rbp
0x180007bf5  mov     [rsp+arg_18], rsi
0x180007bfa  push    r14
0x180007bfc  sub     rsp, 20h
0x180007c00  mov     r14, r8
0x180007c03  mov     ebp, edx
0x180007c05  mov     rsi, rcx
0x180007c08  test    r8, r8
0x180007c0b  jz      loc_180007CA3
0x180007c11  mov     qword ptr [r8], 0
0x180007c18  call    ?_Init@CProfileAccounts@@AEAAJXZ; CProfileAccounts::_Init(void)
0x180007c1d  test    eax, eax
0x180007c1f  js      short loc_180007C8B
0x180007c21  mov     [rsp+28h+arg_0], rbx
0x180007c26  xor     ebx, ebx
0x180007c28  mov     [rsp+28h+arg_8], rdi
0x180007c2d  nop     dword ptr [rax]
0x180007c30  mov     rax, [rsi+10h]
0x180007c34  test    rax, rax
0x180007c37  jz      short loc_180007C3D
0x180007c39  mov     ecx, [rax]
0x180007c3b  jmp     short loc_180007C3F
0x180007c3d  xor     ecx, ecx
0x180007c3f  cmp     ebx, ecx
0x180007c41  jge     short loc_180007C9C
0x180007c43  mov     rax, [rax+8]
0x180007c47  movsxd  rcx, ebx
0x180007c4a  mov     rdi, [rax+rcx*8]
0x180007c4e  xor     eax, eax
0x180007c50  test    rdi, rdi
0x180007c53  jz      short loc_180007C6E
0x180007c55  mov     rcx, rdi; pSid
0x180007c58  call    cs:__imp_GetSidSubAuthorityCount
0x180007c5e  mov     rcx, rdi; pSid
0x180007c61  movzx   edx, byte ptr [rax]
0x180007c64  dec     edx; nSubAuthority
0x180007c66  call    cs:__imp_GetSidSubAuthority
0x180007c6c  mov     eax, [rax]
0x180007c6e  cmp     eax, ebp
0x180007c70  jz      short loc_180007C76
0x180007c72  inc     ebx
0x180007c74  jmp     short loc_180007C30
0x180007c76  mov     rdx, r14
0x180007c79  mov     rcx, rdi; pSourceSid
0x180007c7c  call    CSGetProfilePropertyStore
0x180007c81  mov     rdi, [rsp+28h+arg_8]
0x180007c86  mov     rbx, [rsp+28h+arg_0]
0x180007c8b  mov     rbp, [rsp+28h+arg_10]
0x180007c90  mov     rsi, [rsp+28h+arg_18]
0x180007c95  add     rsp, 20h
0x180007c99  pop     r14
0x180007c9b  retn
0x180007c9c  mov     eax, 80070057h
0x180007ca1  jmp     short loc_180007C81
0x180007ca3  mov     eax, 80070057h
0x180007ca8  jmp     short loc_180007C8B
```
