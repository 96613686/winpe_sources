# RtlpImageNtHeader

- ea: `0x14000157c`
- end: `0x1400015cd`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400015d4`

## callees

- `0x14000157c`

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
0x14000157c  sub     rsp, 18h
0x140001580  xor     edx, edx
0x140001582  lea     rax, [rcx-1]
0x140001586  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000158a  ja      short loc_1400015C5
0x14000158c  mov     eax, 5A4Dh
0x140001591  cmp     [rcx], ax
0x140001594  jnz     short loc_1400015BD
0x140001596  movsxd  rax, dword ptr [rcx+3Ch]
0x14000159a  test    eax, eax
0x14000159c  js      short loc_1400015BD
0x14000159e  cmp     eax, 10000000h
0x1400015a3  jnb     short loc_1400015BD
0x1400015a5  lea     rdx, [rcx+rax]
0x1400015a9  mov     [rsp+18h+var_18], rdx
0x1400015ad  xor     eax, eax
0x1400015af  cmp     dword ptr [rdx], 4550h
0x1400015b5  cmovnz  rdx, rax
0x1400015b9  mov     [rsp+18h+var_18], rdx
0x1400015bd  jmp     short loc_1400015C5
0x1400015bf  xor     edx, edx
0x1400015c1  mov     [rsp+18h+var_18], rdx
0x1400015c5  mov     rax, rdx
0x1400015c8  add     rsp, 18h
0x1400015cc  retn
```
