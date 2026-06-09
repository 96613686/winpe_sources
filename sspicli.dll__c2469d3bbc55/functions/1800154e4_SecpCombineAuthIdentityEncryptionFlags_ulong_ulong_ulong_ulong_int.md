# SecpCombineAuthIdentityEncryptionFlags(ulong,ulong,ulong *,ulong *,int *)

- ea: `0x1800154e4`
- end: `0x1800155ac`
- name: `?SecpCombineAuthIdentityEncryptionFlags@@YAJKKPEAK0PEAH@Z`
- size: `200`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800137a0`

## callees

- `0x18000a170`
- `0x1800154e4`

## pseudocode

```c
__int64 __fastcall SecpCombineAuthIdentityEncryptionFlags(
        int a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        int *a5)
{
  int *v5; // rdi
  __int64 result; // rax
  int v10; // ecx
  int v11; // [rsp+58h] [rbp+10h] BYREF

  v5 = a5;
  v11 = 0;
  *a3 = a2;
  *v5 = 0;
  if ( (a2 & 0x10000) == 0 )
    return 3221225485LL;
  if ( a1 != 1 )
  {
    result = 0;
    if ( a1 == 2 )
    {
      v10 = 16;
      if ( (a2 & 0x10) == 0 )
        *v5 = 1;
      *a4 = 0;
LABEL_19:
      *a3 |= v10;
      return result;
    }
    if ( a1 == 4 )
    {
      v10 = 128;
      if ( (a2 & 0x80) == 0 )
        *v5 = 1;
      *a4 = 4;
      goto LABEL_19;
    }
    return 3221225485LL;
  }
  if ( (a2 & 0x10) != 0 )
    return 3221225659LL;
  result = SecpGetThreadLogonContext(&v11);
  if ( (int)result >= 0 )
  {
    v10 = v11 != 0 ? 32 : 64;
    if ( (a2 & 0x60) != 0 )
    {
      if ( (v10 & a2) == 0 )
        return 3221225659LL;
    }
    else
    {
      *v5 = 1;
    }
    *a4 = 2;
    goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x1800154e4  push    rbx
0x1800154e6  push    rsi
0x1800154e7  push    rdi
0x1800154e8  push    r14
0x1800154ea  sub     rsp, 28h
0x1800154ee  mov     rdi, [rsp+48h+arg_20]
0x1800154f3  mov     rsi, r9
0x1800154f6  mov     [rsp+48h+arg_8], 0
0x1800154fe  mov     r14, r8
0x180015501  mov     [r8], edx
0x180015504  mov     ebx, edx
0x180015506  mov     dword ptr [rdi], 0
0x18001550c  bt      edx, 10h
0x180015510  jnb     loc_18001559D
0x180015516  cmp     ecx, 1
0x180015519  jnz     short loc_180015560
0x18001551b  mov     ecx, 10h
0x180015520  test    cl, bl
0x180015522  jz      short loc_18001552B
0x180015524  mov     eax, 0C00000BBh
0x180015529  jmp     short loc_1800155A2
0x18001552b  lea     rcx, [rsp+48h+arg_8]; int *
0x180015530  call    ?SecpGetThreadLogonContext@@YAJPEAH@Z; SecpGetThreadLogonContext(int *)
0x180015535  test    eax, eax
0x180015537  js      short loc_1800155A2
0x180015539  mov     ecx, [rsp+48h+arg_8]
0x18001553d  neg     ecx
0x18001553f  sbb     ecx, ecx
0x180015541  and     ecx, 0FFFFFFE0h
0x180015544  add     ecx, 40h ; '@'
0x180015547  test    bl, 60h
0x18001554a  jz      short loc_180015552
0x18001554c  test    ebx, ecx
0x18001554e  jnz     short loc_180015558
0x180015550  jmp     short loc_180015524
0x180015552  mov     dword ptr [rdi], 1
0x180015558  mov     dword ptr [rsi], 2
0x18001555e  jmp     short loc_180015598
0x180015560  xor     eax, eax
0x180015562  cmp     ecx, 2
0x180015565  jnz     short loc_18001557B
0x180015567  lea     ecx, [rax+10h]
0x18001556a  and     ebx, ecx
0x18001556c  test    bl, bl
0x18001556e  jnz     short loc_180015576
0x180015570  mov     dword ptr [rdi], 1
0x180015576  mov     [r9], eax
0x180015579  jmp     short loc_180015598
0x18001557b  cmp     ecx, 4
0x18001557e  jnz     short loc_18001559D
0x180015580  mov     ecx, 80h
0x180015585  and     ebx, ecx
0x180015587  test    bl, bl
0x180015589  jnz     short loc_180015591
0x18001558b  mov     dword ptr [rdi], 1
0x180015591  mov     dword ptr [r9], 4
0x180015598  or      [r14], ecx
0x18001559b  jmp     short loc_1800155A2
0x18001559d  mov     eax, 0C000000Dh
0x1800155a2  add     rsp, 28h
0x1800155a6  pop     r14
0x1800155a8  pop     rdi
0x1800155a9  pop     rsi
0x1800155aa  pop     rbx
0x1800155ab  retn
```
