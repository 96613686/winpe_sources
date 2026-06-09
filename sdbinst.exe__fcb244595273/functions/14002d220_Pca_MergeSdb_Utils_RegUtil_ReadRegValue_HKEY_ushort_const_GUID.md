# Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,_GUID &)

- ea: `0x14002d220`
- end: `0x14002d26f`
- name: `?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAU_GUID@@@Z`
- size: `79`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, struct _GUID *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140028714`
- `0x140029af0`
- `0x14002d660`

## callees

- `0x14002d220`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14002d253`
- `ADVAPI32!RegGetValueW` at `0x14002d253`

## pseudocode

```c
LSTATUS __fastcall Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY a1, const unsigned __int16 *a2, struct _GUID *a3)
{
  LSTATUS result; // eax
  DWORD v4; // [rsp+68h] [rbp+20h] BYREF

  v4 = 16;
  result = RegGetValueW(a1, &Format, a2, 8u, 0, a3, &v4);
  if ( !result && v4 != 16 )
    return 1462;
  return result;
}

```

## disassembly

```asm
0x14002d220  mov     r11, rsp
0x14002d223  sub     rsp, 48h
0x14002d227  lea     rax, [r11+20h]
0x14002d22b  mov     [rsp+48h+arg_18], 10h
0x14002d233  mov     [r11-18h], rax
0x14002d237  mov     r9d, 8; dwFlags
0x14002d23d  mov     [r11-20h], r8
0x14002d241  mov     r8, rdx; lpValue
0x14002d244  lea     rdx, Format; lpSubKey
0x14002d24b  mov     qword ptr [r11-28h], 0
0x14002d253  call    cs:__imp_RegGetValueW
0x14002d259  test    eax, eax
0x14002d25b  jnz     short loc_14002D26A
0x14002d25d  cmp     [rsp+48h+arg_18], 10h
0x14002d262  mov     ecx, 5B6h
0x14002d267  cmovnz  eax, ecx
0x14002d26a  add     rsp, 48h
0x14002d26e  retn
```
