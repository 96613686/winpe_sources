# RtlpImageNtHeader

- ea: `0x14000176c`
- end: `0x1400017bd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400017c4`

## callees

- `0x14000176c`

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
0x14000176c  sub     rsp, 18h
0x140001770  xor     edx, edx
0x140001772  lea     rax, [rcx-1]
0x140001776  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000177a  ja      short loc_1400017B5
0x14000177c  mov     eax, 5A4Dh
0x140001781  cmp     [rcx], ax
0x140001784  jnz     short loc_1400017AD
0x140001786  movsxd  rax, dword ptr [rcx+3Ch]
0x14000178a  test    eax, eax
0x14000178c  js      short loc_1400017AD
0x14000178e  cmp     eax, 10000000h
0x140001793  jnb     short loc_1400017AD
0x140001795  lea     rdx, [rcx+rax]
0x140001799  mov     [rsp+18h+var_18], rdx
0x14000179d  xor     eax, eax
0x14000179f  cmp     dword ptr [rdx], 4550h
0x1400017a5  cmovnz  rdx, rax
0x1400017a9  mov     [rsp+18h+var_18], rdx
0x1400017ad  jmp     short loc_1400017B5
0x1400017af  xor     edx, edx
0x1400017b1  mov     [rsp+18h+var_18], rdx
0x1400017b5  mov     rax, rdx
0x1400017b8  add     rsp, 18h
0x1400017bc  retn
```
