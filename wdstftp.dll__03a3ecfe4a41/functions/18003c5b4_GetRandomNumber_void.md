# GetRandomNumber(void)

- ea: `0x18003c5b4`
- end: `0x18003c633`
- name: `?GetRandomNumber@@YAKXZ`
- size: `127`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004428`

## callees

- `0x18003c5b4`
- `0x1800607b0`

## import_xrefs

- `msvcrt!srand` at `0x18003c604`
- `msvcrt!srand` at `0x18003c604`
- `msvcrt!rand` at `0x18003c610`
- `msvcrt!rand` at `0x18003c610`
- `KERNEL32!GetTickCount` at `0x18003c5f6`
- `KERNEL32!GetTickCount` at `0x18003c5f6`
- `RPCRT4!UuidCreate` at `0x18003c5d0`
- `RPCRT4!UuidCreate` at `0x18003c5d0`

## pseudocode

```c
__int64 GetRandomNumber(void)
{
  unsigned int v0; // ebx
  UUID *p_Uuid; // rax
  __int64 v2; // rcx
  DWORD TickCount; // eax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  v0 = 0;
  if ( UuidCreate(&Uuid) )
  {
    TickCount = GetTickCount();
    srand(TickCount);
    return (unsigned int)rand();
  }
  else
  {
    p_Uuid = &Uuid;
    v2 = 4;
    do
    {
      v0 ^= p_Uuid->Data1;
      p_Uuid = (UUID *)((char *)p_Uuid + 4);
      --v2;
    }
    while ( v2 );
  }
  return v0;
}

```

## disassembly

```asm
0x18003c5b4  push    rbx
0x18003c5b6  sub     rsp, 40h
0x18003c5ba  mov     rax, cs:__security_cookie
0x18003c5c1  xor     rax, rsp
0x18003c5c4  mov     [rsp+48h+var_18], rax
0x18003c5c9  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18003c5ce  xor     ebx, ebx
0x18003c5d0  call    cs:__imp_UuidCreate
0x18003c5d7  nop     dword ptr [rax+rax+00h]
0x18003c5dc  test    eax, eax
0x18003c5de  jnz     short loc_18003C5F6
0x18003c5e0  lea     rax, [rsp+48h+Uuid]
0x18003c5e5  lea     ecx, [rbx+4]
0x18003c5e8  xor     ebx, [rax]
0x18003c5ea  lea     rax, [rax+4]
0x18003c5ee  sub     rcx, 1
0x18003c5f2  jnz     short loc_18003C5E8
0x18003c5f4  jmp     short loc_18003C61E
0x18003c5f6  call    cs:__imp_GetTickCount
0x18003c5fd  nop     dword ptr [rax+rax+00h]
0x18003c602  mov     ecx, eax; Seed
0x18003c604  call    cs:__imp_srand
0x18003c60b  nop     dword ptr [rax+rax+00h]
0x18003c610  call    cs:__imp_rand
0x18003c617  nop     dword ptr [rax+rax+00h]
0x18003c61c  mov     ebx, eax
0x18003c61e  mov     eax, ebx
0x18003c620  mov     rcx, [rsp+48h+var_18]
0x18003c625  xor     rcx, rsp; StackCookie
0x18003c628  call    __security_check_cookie
0x18003c62d  add     rsp, 40h
0x18003c631  pop     rbx
0x18003c632  retn
```
