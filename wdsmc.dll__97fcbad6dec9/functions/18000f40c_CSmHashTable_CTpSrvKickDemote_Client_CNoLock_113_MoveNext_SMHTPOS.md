# CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::MoveNext(_SMHTPOS &)

- ea: `0x18000f40c`
- end: `0x18000f470`
- name: `?MoveNext@?$CSmHashTable@UClient@CTpSrvKickDemote@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z`
- size: `100`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ea7c`
- `0x18000ec74`
- `0x18000ef44`

## callees

- `0x18000f40c`

## pseudocode

```c
void __fastcall CSmHashTable<CTpSrvKickDemote::Client,CNoLock,113>::MoveNext(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  unsigned int v5; // edx
  bool v6; // zf
  unsigned int i; // r9d
  __int64 v8; // rax

  if ( !*(_DWORD *)a2 )
  {
    v3 = *(_QWORD *)(a2 + 8);
    if ( !v3 || (v4 = *(_QWORD *)(v3 + 16), (*(_QWORD *)(a2 + 8) = v4) == 0) )
    {
      v5 = *(_DWORD *)(a2 + 4) + 1;
      *(_DWORD *)(a2 + 4) = v5;
      v6 = v5 == 113;
      if ( v5 < 0x71 )
      {
        for ( i = v5; i < 0x71; v5 = i )
        {
          v8 = *(_QWORD *)(a1 + 24LL * i + 8);
          *(_QWORD *)(a2 + 8) = v8;
          if ( v8 )
            break;
          *(_DWORD *)(a2 + 4) = ++i;
        }
        v6 = v5 == 113;
      }
      if ( v6 )
        *(_DWORD *)a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x18000f40c  cmp     dword ptr [rdx], 0
0x18000f40f  mov     r8, rdx
0x18000f412  mov     r10, rcx
0x18000f415  jnz     short locret_18000F46F
0x18000f417  mov     rax, [rdx+8]
0x18000f41b  test    rax, rax
0x18000f41e  jz      short loc_18000F42D
0x18000f420  mov     rax, [rax+10h]
0x18000f424  mov     [rdx+8], rax
0x18000f428  test    rax, rax
0x18000f42b  jnz     short locret_18000F46F
0x18000f42d  mov     edx, [rdx+4]
0x18000f430  inc     edx
0x18000f432  mov     [r8+4], edx
0x18000f436  cmp     edx, 71h ; 'q'
0x18000f439  jnb     short loc_18000F466
0x18000f43b  mov     r9d, edx
0x18000f43e  mov     eax, r9d
0x18000f441  lea     rcx, [rax+rax*2]
0x18000f445  mov     rax, [r10+rcx*8+8]
0x18000f44a  mov     [r8+8], rax
0x18000f44e  test    rax, rax
0x18000f451  jnz     short loc_18000F463
0x18000f453  lea     edx, [r9+1]
0x18000f457  mov     [r8+4], edx
0x18000f45b  mov     r9d, edx
0x18000f45e  cmp     edx, 71h ; 'q'
0x18000f461  jb      short loc_18000F43E
0x18000f463  cmp     edx, 71h ; 'q'
0x18000f466  jnz     short locret_18000F46F
0x18000f468  mov     dword ptr [r8], 1
0x18000f46f  retn
```
