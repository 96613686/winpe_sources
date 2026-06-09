# ServiceStatus(ulong)

- ea: `0x180002728`
- end: `0x180002748`
- name: `?ServiceStatus@@YAKK@Z`
- size: `32`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `25`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180002390`
- `0x180002550`
- `0x180005f40`
- `0x180006604`
- `0x1800112e0`
- `0x180011480`
- `0x180011690`
- `0x180011970`
- `0x180011b10`
- `0x180011de0`
- `0x180011f80`
- `0x180012130`
- `0x180012400`
- `0x180012670`
- `0x180012b10`
- `0x180012ee0`
- `0x1800130e0`
- `0x1800133d0`
- `0x180013580`
- `0x1800136c0`
- `0x180013990`
- `0x180013bf0`
- `0x180013db0`
- `0x18001c25c`
- `0x18001c410`

## callees

- `0x180002728`

## pseudocode

```c
__int64 __fastcall ServiceStatus(unsigned int a1)
{
  if ( a1 == 1702 || a1 == 1717 || a1 == 1726 || a1 == 1753 )
    return 1062;
  return a1;
}

```

## disassembly

```asm
0x180002728  mov     eax, ecx
0x18000272a  sub     eax, 6A6h
0x18000272f  jz      short loc_180002740
0x180002731  sub     eax, 0Fh
0x180002734  jz      short loc_180002740
0x180002736  sub     eax, 9
0x180002739  jz      short loc_180002740
0x18000273b  cmp     eax, 1Bh
0x18000273e  jnz     short loc_180002745
0x180002740  mov     ecx, 426h
0x180002745  mov     eax, ecx
0x180002747  retn
```
