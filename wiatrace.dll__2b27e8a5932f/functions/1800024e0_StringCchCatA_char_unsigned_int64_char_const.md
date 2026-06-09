# StringCchCatA(char *,unsigned __int64,char const *)

- ea: `0x1800024e0`
- end: `0x180002577`
- name: `?StringCchCatA@@YAJPEAD_KPEBD@Z`
- size: `151`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001300`

## callees

- `0x1800024e0`

## pseudocode

```c
__int64 __fastcall StringCchCatA(char *a1, __int64 a2, char *a3)
{
  __int64 v3; // rbx
  __int64 v5; // r9
  char *v6; // rax
  int v7; // edx
  __int64 v8; // rax
  char *v9; // rdx
  __int64 i; // r10
  char *v11; // rax
  __int64 result; // rax

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    return (unsigned int)-2147024809;
  v5 = a2;
  v6 = a1;
  while ( *v6 )
  {
    ++v6;
    if ( !--v5 )
    {
      v7 = -2147024809;
      v8 = 0;
      goto LABEL_7;
    }
  }
  v8 = a2 - v5;
  v7 = 0;
LABEL_7:
  if ( v7 < 0 )
    return (unsigned int)v7;
  v9 = &a1[v8];
  for ( i = a2 - v8; i; --i )
  {
    if ( !v3 )
      break;
    if ( !*a3 )
      break;
    *v9++ = *a3++;
    --v3;
  }
  v11 = v9 - 1;
  if ( i )
    v11 = v9;
  *v11 = 0;
  result = 2147942522LL;
  if ( i )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800024e0  mov     [rsp+arg_0], rbx
0x1800024e5  lea     rax, [rdx-1]
0x1800024e9  mov     ebx, 7FFFFFFEh
0x1800024ee  mov     r10, rdx
0x1800024f1  mov     r11, rcx
0x1800024f4  cmp     rax, rbx
0x1800024f7  ja      short loc_18000256A
0x1800024f9  mov     r9, rdx
0x1800024fc  mov     rax, rcx
0x1800024ff  nop
0x180002500  cmp     byte ptr [rax], 0
0x180002503  jz      short loc_180002519
0x180002505  inc     rax
0x180002508  sub     r9, 1
0x18000250c  jnz     short loc_180002500
0x18000250e  xor     ecx, ecx
0x180002510  mov     edx, 80070057h
0x180002515  mov     eax, ecx
0x180002517  jmp     short loc_180002523
0x180002519  mov     rax, r10
0x18000251c  sub     rax, r9
0x18000251f  xor     ecx, ecx
0x180002521  mov     edx, ecx
0x180002523  test    edx, edx
0x180002525  js      short loc_18000256F
0x180002527  lea     rdx, [rax+r11]
0x18000252b  sub     r10, rax
0x18000252e  jz      short loc_18000254E
0x180002530  test    rbx, rbx
0x180002533  jz      short loc_18000254E
0x180002535  movzx   eax, byte ptr [r8]
0x180002539  test    al, al
0x18000253b  jz      short loc_18000254E
0x18000253d  mov     [rdx], al
0x18000253f  inc     r8
0x180002542  inc     rdx
0x180002545  dec     rbx
0x180002548  sub     r10, 1
0x18000254c  jnz     short loc_180002530
0x18000254e  test    r10, r10
0x180002551  lea     rax, [rdx-1]
0x180002555  cmovnz  rax, rdx
0x180002559  mov     byte ptr [rax], 0
0x18000255c  mov     eax, 8007007Ah
0x180002561  cmovnz  eax, ecx
0x180002564  mov     rbx, [rsp+arg_0]
0x180002569  retn
0x18000256a  mov     edx, 80070057h
0x18000256f  mov     rbx, [rsp+arg_0]
0x180002574  mov     eax, edx
0x180002576  retn
```
