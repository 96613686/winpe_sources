# RtlpImageNtHeader

- ea: `0x1400027fc`
- end: `0x14000284d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140002854`

## callees

- `0x1400027fc`

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
0x1400027fc  sub     rsp, 18h
0x140002800  xor     edx, edx
0x140002802  lea     rax, [rcx-1]
0x140002806  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000280a  ja      short loc_140002845
0x14000280c  mov     eax, 5A4Dh
0x140002811  cmp     [rcx], ax
0x140002814  jnz     short loc_14000283D
0x140002816  movsxd  rax, dword ptr [rcx+3Ch]
0x14000281a  test    eax, eax
0x14000281c  js      short loc_14000283D
0x14000281e  cmp     eax, 10000000h
0x140002823  jnb     short loc_14000283D
0x140002825  lea     rdx, [rcx+rax]
0x140002829  mov     [rsp+18h+var_18], rdx
0x14000282d  xor     eax, eax
0x14000282f  cmp     dword ptr [rdx], 4550h
0x140002835  cmovnz  rdx, rax
0x140002839  mov     [rsp+18h+var_18], rdx
0x14000283d  jmp     short loc_140002845
0x14000283f  xor     edx, edx
0x140002841  mov     [rsp+18h+var_18], rdx
0x140002845  mov     rax, rdx
0x140002848  add     rsp, 18h
0x14000284c  retn
```
