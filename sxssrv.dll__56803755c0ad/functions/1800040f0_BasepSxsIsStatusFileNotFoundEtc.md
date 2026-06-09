# BasepSxsIsStatusFileNotFoundEtc

- ea: `0x1800040f0`
- end: `0x180004142`
- name: `BasepSxsIsStatusFileNotFoundEtc`
- size: `82`
- prototype: `_BOOL8 __fastcall(NTSTATUS)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002800`
- `0x180002c50`
- `0x180003170`

## callees

- `0x1800040f0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180004122`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180004122`

## pseudocode

```c
_BOOL8 __fastcall BasepSxsIsStatusFileNotFoundEtc(NTSTATUS a1)
{
  _BOOL8 result; // rax
  unsigned __int64 v2; // rax
  __int64 v3; // rdx
  ULONG v4; // eax

  result = 0;
  if ( a1 < 0 )
  {
    v2 = (unsigned int)(a1 + 1073741809);
    if ( (unsigned int)v2 <= 0x2B )
    {
      v3 = 0x82000000001LL;
      if ( _bittest64(&v3, v2) )
        return 1;
    }
    v4 = RtlNtStatusToDosErrorNoTeb(a1);
    if ( v4 == 53 || v4 - 2 <= 1 || v4 == 67 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800040f0  sub     rsp, 28h
0x1800040f4  test    ecx, ecx
0x1800040f6  js      short loc_180004100
0x1800040f8  xor     eax, eax
0x1800040fa  add     rsp, 28h
0x1800040fe  retn
0x180004100  lea     eax, [rcx+3FFFFFF1h]
0x180004106  cmp     eax, 2Bh ; '+'
0x180004109  ja      short loc_180004122
0x18000410b  mov     rdx, 82000000001h
0x180004115  bt      rdx, rax
0x180004119  jnb     short loc_180004122
0x18000411b  mov     eax, 1
0x180004120  jmp     short loc_1800040FA
0x180004122  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180004129  nop     dword ptr [rax+rax+00h]
0x18000412e  cmp     eax, 35h ; '5'
0x180004131  jz      short loc_18000411B
0x180004133  lea     ecx, [rax-2]
0x180004136  cmp     ecx, 1
0x180004139  jbe     short loc_18000411B
0x18000413b  cmp     eax, 43h ; 'C'
0x18000413e  jnz     short loc_1800040F8
0x180004140  jmp     short loc_18000411B
```
