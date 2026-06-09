# Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,Pca::MergeSdb::Utils::TimeValue &)

- ea: `0x14002d61c`
- end: `0x14002d65a`
- name: `?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAVTimeValue@234@@Z`
- size: `62`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, struct Pca::MergeSdb::Utils::TimeValue *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140028714`
- `0x14002955c`
- `0x14002d660`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14002d64f`
- `ADVAPI32!RegGetValueW` at `0x14002d64f`

## pseudocode

```c
LSTATUS __fastcall Pca::MergeSdb::Utils::RegUtil::ReadRegValue(
        HKEY a1,
        const unsigned __int16 *a2,
        struct Pca::MergeSdb::Utils::TimeValue *a3)
{
  DWORD v4; // [rsp+68h] [rbp+20h] BYREF

  v4 = 8;
  return RegGetValueW(a1, &Format, a2, 0x48u, 0, a3, &v4);
}

```

## disassembly

```asm
0x14002d61c  mov     r11, rsp
0x14002d61f  sub     rsp, 48h
0x14002d623  lea     rax, [r11+20h]
0x14002d627  mov     [rsp+48h+arg_18], 8
0x14002d62f  mov     [r11-18h], rax
0x14002d633  mov     r9d, 48h ; 'H'; dwFlags
0x14002d639  mov     [r11-20h], r8
0x14002d63d  mov     r8, rdx; lpValue
0x14002d640  lea     rdx, Format; lpSubKey
0x14002d647  mov     qword ptr [r11-28h], 0
0x14002d64f  call    cs:__imp_RegGetValueW
0x14002d655  add     rsp, 48h
0x14002d659  retn
```
