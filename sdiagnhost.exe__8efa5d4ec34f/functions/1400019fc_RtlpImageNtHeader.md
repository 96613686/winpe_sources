# RtlpImageNtHeader

- ea: `0x1400019fc`
- end: `0x140001a4d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001a54`

## callees

- `0x1400019fc`

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
0x1400019fc  sub     rsp, 18h
0x140001a00  xor     edx, edx
0x140001a02  lea     rax, [rcx-1]
0x140001a06  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140001a0a  ja      short loc_140001A45
0x140001a0c  mov     eax, 5A4Dh
0x140001a11  cmp     [rcx], ax
0x140001a14  jnz     short loc_140001A3D
0x140001a16  movsxd  rax, dword ptr [rcx+3Ch]
0x140001a1a  test    eax, eax
0x140001a1c  js      short loc_140001A3D
0x140001a1e  cmp     eax, 10000000h
0x140001a23  jnb     short loc_140001A3D
0x140001a25  lea     rdx, [rcx+rax]
0x140001a29  mov     [rsp+18h+var_18], rdx
0x140001a2d  xor     eax, eax
0x140001a2f  cmp     dword ptr [rdx], 4550h
0x140001a35  cmovnz  rdx, rax
0x140001a39  mov     [rsp+18h+var_18], rdx
0x140001a3d  jmp     short loc_140001A45
0x140001a3f  xor     edx, edx
0x140001a41  mov     [rsp+18h+var_18], rdx
0x140001a45  mov     rax, rdx
0x140001a48  add     rsp, 18h
0x140001a4c  retn
```
