# Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,ulong &)

- ea: `0x14002d1dc`
- end: `0x14002d21a`
- name: `?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAK@Z`
- size: `62`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14002285c`
- `0x140024958`
- `0x14002d660`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14002d20f`
- `ADVAPI32!RegGetValueW` at `0x14002d20f`

## pseudocode

```c
LSTATUS __fastcall Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY a1, const unsigned __int16 *a2, unsigned int *a3)
{
  DWORD v4; // [rsp+68h] [rbp+20h] BYREF

  v4 = 4;
  return RegGetValueW(a1, &Format, a2, 0x18u, 0, a3, &v4);
}

```

## disassembly

```asm
0x14002d1dc  mov     r11, rsp
0x14002d1df  sub     rsp, 48h
0x14002d1e3  lea     rax, [r11+20h]
0x14002d1e7  mov     [rsp+48h+arg_18], 4
0x14002d1ef  mov     [r11-18h], rax
0x14002d1f3  mov     r9d, 18h; dwFlags
0x14002d1f9  mov     [r11-20h], r8
0x14002d1fd  mov     r8, rdx; lpValue
0x14002d200  lea     rdx, Format; lpSubKey
0x14002d207  mov     qword ptr [r11-28h], 0
0x14002d20f  call    cs:__imp_RegGetValueW
0x14002d215  add     rsp, 48h
0x14002d219  retn
```
