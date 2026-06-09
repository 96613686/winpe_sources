# CSecurityInformation::GetSecurity(ulong,void * *,int)

- ea: `0x18000c230`
- end: `0x18000c2af`
- name: `?GetSecurity@CSecurityInformation@@UEAAJKPEAPEAXH@Z`
- size: `127`
- prototype: `__int64 __fastcall(CSecurityInformation *__hidden this, unsigned int, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007250`

## callees

- `0x18000c230`
- `0x18000c444`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::GetSecurity(CSecurityInformation *this, unsigned int a2, void **a3, int a4)
{
  char v5; // bl
  int v8; // ebp

  v5 = a2;
  if ( !a3 || !*((_QWORD *)this + 7) )
    return 2147500035LL;
  if ( !a2 )
    return 2147942487LL;
  *a3 = 0;
  if ( a4 )
  {
    return (unsigned int)-2147467263;
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(CSecurityInformation *, _QWORD, _QWORD, void **))(*(_QWORD *)this + 96LL))(
           this,
           *((_QWORD *)this + 7),
           a2,
           a3);
    if ( v8 >= 0 && (*((_DWORD *)this + 16) & 0x200) != 0 )
      ProtectACLs(v5 & 0xC, *a3);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c230  push    rbx
0x18000c232  push    rbp
0x18000c233  push    rsi
0x18000c234  push    rdi
0x18000c235  sub     rsp, 38h
0x18000c239  mov     rdi, r8
0x18000c23c  mov     ebx, edx
0x18000c23e  mov     rsi, rcx
0x18000c241  test    r8, r8
0x18000c244  jz      short loc_18000C2A1
0x18000c246  cmp     qword ptr [rcx+38h], 0
0x18000c24b  jz      short loc_18000C2A1
0x18000c24d  test    edx, edx
0x18000c24f  jnz     short loc_18000C258
0x18000c251  mov     eax, 80070057h
0x18000c256  jmp     short loc_18000C2A6
0x18000c258  mov     qword ptr [r8], 0
0x18000c25f  test    r9d, r9d
0x18000c262  jz      short loc_18000C26B
0x18000c264  mov     ebp, 80004001h
0x18000c269  jmp     short loc_18000C29D
0x18000c26b  mov     rax, [rcx]
0x18000c26e  mov     r9, rdi
0x18000c271  mov     rdx, [rcx+38h]
0x18000c275  mov     r8d, ebx
0x18000c278  mov     rax, [rax+60h]
0x18000c27c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c281  mov     ebp, eax
0x18000c283  test    eax, eax
0x18000c285  js      short loc_18000C29D
0x18000c287  test    dword ptr [rsi+40h], 200h
0x18000c28e  jz      short loc_18000C29D
0x18000c290  mov     rdx, [rdi]; void *
0x18000c293  and     ebx, 0Ch
0x18000c296  mov     ecx, ebx; unsigned int
0x18000c298  call    ?ProtectACLs@@YAXKPEAX@Z; ProtectACLs(ulong,void *)
0x18000c29d  mov     eax, ebp
0x18000c29f  jmp     short loc_18000C2A6
0x18000c2a1  mov     eax, 80004003h
0x18000c2a6  add     rsp, 38h
0x18000c2aa  pop     rdi
0x18000c2ab  pop     rsi
0x18000c2ac  pop     rbp
0x18000c2ad  pop     rbx
0x18000c2ae  retn
```
