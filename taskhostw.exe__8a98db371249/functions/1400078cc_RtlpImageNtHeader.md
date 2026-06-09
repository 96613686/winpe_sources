# RtlpImageNtHeader

- ea: `0x1400078cc`
- end: `0x14000791d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140007924`

## callees

- `0x1400078cc`

## pseudocode

```c
__int64 __fastcall RtlpImageNtHeader(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax

  v1 = 0;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_WORD *)a1 == 23117 )
  {
    v2 = *(int *)(a1 + 60);
    if ( (unsigned int)v2 < 0x10000000 )
    {
      v1 = a1 + v2;
      if ( *(_DWORD *)(a1 + v2) != 17744 )
        return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400078cc  sub     rsp, 18h
0x1400078d0  xor     edx, edx
0x1400078d2  lea     rax, [rcx-1]
0x1400078d6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400078da  ja      short loc_140007915
0x1400078dc  mov     eax, 5A4Dh
0x1400078e1  cmp     [rcx], ax
0x1400078e4  jnz     short loc_14000790D
0x1400078e6  movsxd  rax, dword ptr [rcx+3Ch]
0x1400078ea  test    eax, eax
0x1400078ec  js      short loc_14000790D
0x1400078ee  cmp     eax, 10000000h
0x1400078f3  jnb     short loc_14000790D
0x1400078f5  lea     rdx, [rcx+rax]
0x1400078f9  mov     [rsp+18h+var_18], rdx
0x1400078fd  xor     eax, eax
0x1400078ff  cmp     dword ptr [rdx], 4550h
0x140007905  cmovnz  rdx, rax
0x140007909  mov     [rsp+18h+var_18], rdx
0x14000790d  jmp     short loc_140007915
0x14000790f  xor     edx, edx
0x140007911  mov     [rsp+18h+var_18], rdx
0x140007915  mov     rax, rdx
0x140007918  add     rsp, 18h
0x14000791c  retn
```
