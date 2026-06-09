# CSecurityInformation::SetSecurity(ulong,void *)

- ea: `0x18000c740`
- end: `0x18000c7d1`
- name: `?SetSecurity@CSecurityInformation@@UEAAJKPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(CSecurityInformation *this, unsigned int, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007950`
- `0x180008950`

## callees

- `0x18000c740`
- `0x18001e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000c772`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18000c772`
- `USER32!SetCursor` at `0x18000c78c`
- `USER32!SetCursor` at `0x18000c7b9`
- `USER32!SetCursor` at `0x18000c78c`
- `USER32!SetCursor` at `0x18000c7b9`
- `USER32!LoadCursorW` at `0x18000c783`
- `USER32!LoadCursorW` at `0x18000c783`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::SetSecurity(CSecurityInformation *this, unsigned int a2, void *a3)
{
  unsigned int v6; // ebx
  HCURSOR CursorW; // rax
  HCURSOR v9; // rbp

  if ( !*((_QWORD *)this + 7) )
    return (unsigned int)-2147418113;
  if ( !a3 )
    return 2147500035LL;
  if ( a2 && IsValidSecurityDescriptor(a3) )
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v9 = SetCursor(CursorW);
    v6 = (*(__int64 (__fastcall **)(CSecurityInformation *, _QWORD, _QWORD, void *))(*(_QWORD *)this + 104LL))(
           this,
           *((_QWORD *)this + 7),
           a2,
           a3);
    if ( v9 != (HCURSOR)-1LL )
      SetCursor(v9);
    return v6;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000c740  push    rbx
0x18000c742  push    rbp
0x18000c743  push    rsi
0x18000c744  push    rdi
0x18000c745  sub     rsp, 38h
0x18000c749  cmp     qword ptr [rcx+38h], 0
0x18000c74e  mov     rbx, r8
0x18000c751  mov     esi, edx
0x18000c753  mov     rdi, rcx
0x18000c756  jnz     short loc_18000C75F
0x18000c758  mov     ebx, 8000FFFFh
0x18000c75d  jmp     short loc_18000C7BF
0x18000c75f  test    rbx, rbx
0x18000c762  jnz     short loc_18000C76B
0x18000c764  mov     eax, 80004003h
0x18000c769  jmp     short loc_18000C7C8
0x18000c76b  test    esi, esi
0x18000c76d  jz      short loc_18000C7C3
0x18000c76f  mov     rcx, rbx; pSecurityDescriptor
0x18000c772  call    cs:__imp_IsValidSecurityDescriptor
0x18000c778  test    eax, eax
0x18000c77a  jz      short loc_18000C7C3
0x18000c77c  mov     edx, 7F02h; lpCursorName
0x18000c781  xor     ecx, ecx; hInstance
0x18000c783  call    cs:__imp_LoadCursorW
0x18000c789  mov     rcx, rax; hCursor
0x18000c78c  call    cs:__imp_SetCursor
0x18000c792  mov     rcx, [rdi]
0x18000c795  mov     r9, rbx
0x18000c798  mov     rdx, [rdi+38h]
0x18000c79c  mov     rbp, rax
0x18000c79f  mov     r8d, esi
0x18000c7a2  mov     rax, [rcx+68h]
0x18000c7a6  mov     rcx, rdi
0x18000c7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ae  mov     ebx, eax
0x18000c7b0  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000c7b4  jz      short loc_18000C7BF
0x18000c7b6  mov     rcx, rbp; hCursor
0x18000c7b9  call    cs:__imp_SetCursor
0x18000c7bf  mov     eax, ebx
0x18000c7c1  jmp     short loc_18000C7C8
0x18000c7c3  mov     eax, 80070057h
0x18000c7c8  add     rsp, 38h
0x18000c7cc  pop     rdi
0x18000c7cd  pop     rsi
0x18000c7ce  pop     rbp
0x18000c7cf  pop     rbx
0x18000c7d0  retn
```
