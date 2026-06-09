# CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)

- ea: `0x180010ac8`
- end: `0x180010b2f`
- name: `?MoveNext@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z`
- size: `103`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f5cc`
- `0x1800102ac`
- `0x18001038c`
- `0x18001050c`
- `0x180010884`

## callees

- `0x180010ac8`

## pseudocode

```c
void __fastcall CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(__int64 a1, __int64 a2)
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
    if ( !v3 || (v4 = *(_QWORD *)(v3 + 3224), (*(_QWORD *)(a2 + 8) = v4) == 0) )
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
0x180010ac8  cmp     dword ptr [rdx], 0
0x180010acb  mov     r8, rdx
0x180010ace  mov     r10, rcx
0x180010ad1  jnz     short locret_180010B2E
0x180010ad3  mov     rax, [rdx+8]
0x180010ad7  test    rax, rax
0x180010ada  jz      short loc_180010AEC
0x180010adc  mov     rax, [rax+0C98h]
0x180010ae3  mov     [rdx+8], rax
0x180010ae7  test    rax, rax
0x180010aea  jnz     short locret_180010B2E
0x180010aec  mov     edx, [rdx+4]
0x180010aef  inc     edx
0x180010af1  mov     [r8+4], edx
0x180010af5  cmp     edx, 71h ; 'q'
0x180010af8  jnb     short loc_180010B25
0x180010afa  mov     r9d, edx
0x180010afd  mov     eax, r9d
0x180010b00  lea     rcx, [rax+rax*2]
0x180010b04  mov     rax, [r10+rcx*8+8]
0x180010b09  mov     [r8+8], rax
0x180010b0d  test    rax, rax
0x180010b10  jnz     short loc_180010B22
0x180010b12  lea     edx, [r9+1]
0x180010b16  mov     [r8+4], edx
0x180010b1a  mov     r9d, edx
0x180010b1d  cmp     edx, 71h ; 'q'
0x180010b20  jb      short loc_180010AFD
0x180010b22  cmp     edx, 71h ; 'q'
0x180010b25  jnz     short locret_180010B2E
0x180010b27  mov     dword ptr [r8], 1
0x180010b2e  retn
```
