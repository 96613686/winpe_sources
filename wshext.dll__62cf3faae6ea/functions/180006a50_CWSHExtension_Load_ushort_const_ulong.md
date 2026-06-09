# CWSHExtension::Load(ushort const *,ulong)

- ea: `0x180006a50`
- end: `0x180006a8e`
- name: `?Load@CWSHExtension@@UEAAJPEBGK@Z`
- size: `62`
- prototype: `int(CWSHExtension *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180006a81`
- `KERNEL32!WideCharToMultiByte` at `0x180006a81`

## pseudocode

```c
__int64 __fastcall CWSHExtension::Load(CHAR *this, const unsigned __int16 *a2)
{
  WideCharToMultiByte(0, 0, a2, -1, this + 56, 260, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180006a50  mov     rax, rsp
0x180006a53  sub     rsp, 48h
0x180006a57  mov     qword ptr [rax-10h], 0
0x180006a5f  add     rcx, 38h ; '8'
0x180006a63  mov     qword ptr [rax-18h], 0
0x180006a6b  mov     r8, rdx; lpWideCharStr
0x180006a6e  mov     dword ptr [rax-20h], 104h
0x180006a75  or      r9d, 0FFFFFFFFh; cchWideChar
0x180006a79  mov     [rax-28h], rcx
0x180006a7d  xor     edx, edx; dwFlags
0x180006a7f  xor     ecx, ecx; CodePage
0x180006a81  call    cs:__imp_WideCharToMultiByte
0x180006a87  xor     eax, eax
0x180006a89  add     rsp, 48h
0x180006a8d  retn
```
