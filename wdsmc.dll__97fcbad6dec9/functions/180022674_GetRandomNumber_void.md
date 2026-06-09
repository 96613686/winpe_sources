# GetRandomNumber(void)

- ea: `0x180022674`
- end: `0x1800226db`
- name: `?GetRandomNumber@@YAKXZ`
- size: `103`
- prototype: `unsigned int(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x1800010b0`
- `0x1800010d0`
- `0x1800010f0`

## callees

- `0x180022674`
- `0x180026670`

## import_xrefs

- `msvcrt!srand` at `0x1800226b8`
- `msvcrt!srand` at `0x1800226b8`
- `msvcrt!rand` at `0x1800226be`
- `msvcrt!rand` at `0x1800226be`
- `KERNEL32!GetTickCount` at `0x1800226b0`
- `KERNEL32!GetTickCount` at `0x1800226b0`
- `RPCRT4!UuidCreate` at `0x180022690`
- `RPCRT4!UuidCreate` at `0x180022690`

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
0x180022674  push    rbx
0x180022676  sub     rsp, 40h
0x18002267a  mov     rax, cs:__security_cookie
0x180022681  xor     rax, rsp
0x180022684  mov     [rsp+48h+var_18], rax
0x180022689  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18002268e  xor     ebx, ebx
0x180022690  call    cs:__imp_UuidCreate
0x180022696  test    eax, eax
0x180022698  jnz     short loc_1800226B0
0x18002269a  lea     rax, [rsp+48h+Uuid]
0x18002269f  lea     ecx, [rbx+4]
0x1800226a2  xor     ebx, [rax]
0x1800226a4  lea     rax, [rax+4]
0x1800226a8  sub     rcx, 1
0x1800226ac  jnz     short loc_1800226A2
0x1800226ae  jmp     short loc_1800226C6
0x1800226b0  call    cs:__imp_GetTickCount
0x1800226b6  mov     ecx, eax; Seed
0x1800226b8  call    cs:__imp_srand
0x1800226be  call    cs:__imp_rand
0x1800226c4  mov     ebx, eax
0x1800226c6  mov     eax, ebx
0x1800226c8  mov     rcx, [rsp+48h+var_18]
0x1800226cd  xor     rcx, rsp; StackCookie
0x1800226d0  call    __security_check_cookie
0x1800226d5  add     rsp, 40h
0x1800226d9  pop     rbx
0x1800226da  retn
```
