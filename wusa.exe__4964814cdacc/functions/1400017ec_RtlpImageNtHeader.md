# RtlpImageNtHeader

- ea: `0x1400017ec`
- end: `0x14000183d`
- name: `RtlpImageNtHeader`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001844`

## callees

- `0x1400017ec`

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
0x1400017ec  sub     rsp, 18h
0x1400017f0  xor     edx, edx
0x1400017f2  lea     rax, [rcx-1]
0x1400017f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400017fa  ja      short loc_140001835
0x1400017fc  mov     eax, 5A4Dh
0x140001801  cmp     [rcx], ax
0x140001804  jnz     short loc_14000182D
0x140001806  movsxd  rax, dword ptr [rcx+3Ch]
0x14000180a  test    eax, eax
0x14000180c  js      short loc_14000182D
0x14000180e  cmp     eax, 10000000h
0x140001813  jnb     short loc_14000182D
0x140001815  lea     rdx, [rcx+rax]
0x140001819  mov     [rsp+18h+var_18], rdx
0x14000181d  xor     eax, eax
0x14000181f  cmp     dword ptr [rdx], 4550h
0x140001825  cmovnz  rdx, rax
0x140001829  mov     [rsp+18h+var_18], rdx
0x14000182d  jmp     short loc_140001835
0x14000182f  xor     edx, edx
0x140001831  mov     [rsp+18h+var_18], rdx
0x140001835  mov     rax, rdx
0x140001838  add     rsp, 18h
0x14000183c  retn
```
