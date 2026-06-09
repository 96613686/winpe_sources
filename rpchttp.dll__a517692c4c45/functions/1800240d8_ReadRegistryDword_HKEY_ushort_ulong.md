# ReadRegistryDword(HKEY__ *,ushort *,ulong *)

- ea: `0x1800240d8`
- end: `0x18002413b`
- name: `?ReadRegistryDword@@YAJPEAUHKEY__@@PEAGPEAK@Z`
- size: `99`
- prototype: `LSTATUS __fastcall(HKEY, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180022770`

## callees

- `0x1800240d8`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180024116`
- `ADVAPI32!RegGetValueW` at `0x180024116`

## pseudocode

```c
LSTATUS __fastcall ReadRegistryDword(HKEY a1, unsigned __int16 *a2, unsigned int *a3)
{
  LSTATUS result; // eax
  DWORD v5[6]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v6; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  v5[0] = 4;
  result = RegGetValueW(a1, 0, a2, 0x18u, 0, &v6, v5);
  if ( result )
  {
    if ( result != 2 )
      return 14;
  }
  else
  {
    *a3 = v6;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800240d8  mov     r11, rsp
0x1800240db  push    rbx
0x1800240dc  sub     rsp, 50h
0x1800240e0  lea     rax, [r11-18h]
0x1800240e4  mov     [rsp+58h+arg_18], 0
0x1800240ec  mov     [r11-28h], rax
0x1800240f0  mov     rbx, r8
0x1800240f3  lea     rax, [r11+20h]
0x1800240f7  mov     [rsp+58h+var_18], 4
0x1800240ff  mov     r8, rdx; lpValue
0x180024102  mov     [r11-30h], rax
0x180024106  mov     r9d, 18h; dwFlags
0x18002410c  mov     qword ptr [r11-38h], 0
0x180024114  xor     edx, edx; lpSubKey
0x180024116  call    cs:__imp_RegGetValueW
0x18002411c  test    eax, eax
0x18002411e  jnz     short loc_18002412A
0x180024120  mov     eax, [rsp+58h+arg_18]
0x180024124  mov     [rbx], eax
0x180024126  xor     eax, eax
0x180024128  jmp     short loc_180024135
0x18002412a  cmp     eax, 2
0x18002412d  mov     ecx, 0Eh
0x180024132  cmovnz  eax, ecx
0x180024135  add     rsp, 50h
0x180024139  pop     rbx
0x18002413a  retn
```
