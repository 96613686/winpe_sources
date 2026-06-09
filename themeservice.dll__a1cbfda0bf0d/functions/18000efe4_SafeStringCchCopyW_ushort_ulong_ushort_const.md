# SafeStringCchCopyW(ushort *,ulong,ushort const *)

- ea: `0x18000efe4`
- end: `0x18000f003`
- name: `?SafeStringCchCopyW@@YAJPEAGKPEBG@Z`
- size: `31`
- prototype: `int __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f0bc`

## callees

- `0x180006a08`
- `0x18000efe4`

## pseudocode

```c
int __fastcall SafeStringCchCopyW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  int result; // eax

  result = -2147024809;
  if ( a1 )
  {
    if ( a3 )
    {
      return StringCchCopyW(a1, 0x104u, a3);
    }
    else
    {
      result = 0;
      *a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000efe4  mov     eax, 80070057h
0x18000efe9  test    rcx, rcx
0x18000efec  jz      short locret_18000F002
0x18000efee  test    r8, r8
0x18000eff1  jz      short loc_18000EFFD
0x18000eff3  mov     edx, 104h; unsigned __int64
0x18000eff8  jmp     ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000effd  xor     eax, eax
0x18000efff  mov     [rcx], ax
0x18000f002  retn
```
