# CUwfStaticConfiguration::DeleteOverlayFile(void)

- ea: `0x180007250`
- end: `0x1800072a9`
- name: `?DeleteOverlayFile@CUwfStaticConfiguration@@QEAAJXZ`
- size: `89`
- prototype: `__int64 __fastcall(CUwfConfiguration **this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000c300`
- `0x1800169c4`

## callees

- `0x180007180`
- `0x180007250`
- `0x180007ad0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000728b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000728b`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::DeleteOverlayFile(CUwfConfiguration **this)
{
  int OverlayFileName; // edi
  unsigned __int16 *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  OverlayFileName = CUwfStaticConfiguration::GetOverlayFileName((CUwfStaticConfiguration *)this, &v4);
  if ( OverlayFileName >= 0 )
    OverlayFileName = CUwfConfiguration::DeleteFileW(this[4], v4);
  operator delete[](v4);
  if ( OverlayFileName < 0 )
    *((_DWORD *)this[4] + 4) = OverlayFileName;
  return (unsigned int)OverlayFileName;
}

```

## disassembly

```asm
0x180007250  mov     [rsp+arg_0], rbx
0x180007255  push    rdi
0x180007256  sub     rsp, 20h
0x18000725a  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 **
0x18000725f  mov     [rsp+28h+arg_8], 0
0x180007268  mov     rbx, rcx
0x18000726b  call    ?GetOverlayFileName@CUwfStaticConfiguration@@QEAAJPEAPEAG@Z; CUwfStaticConfiguration::GetOverlayFileName(ushort * *)
0x180007270  mov     edi, eax
0x180007272  test    eax, eax
0x180007274  js      short loc_180007286
0x180007276  mov     rdx, [rsp+28h+arg_8]; unsigned __int16 *
0x18000727b  mov     rcx, [rbx+20h]; this
0x18000727f  call    ?DeleteFileW@CUwfConfiguration@@QEAAJPEBG@Z; CUwfConfiguration::DeleteFileW(ushort const *)
0x180007284  mov     edi, eax
0x180007286  mov     rcx, [rsp+28h+arg_8]
0x18000728b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007291  test    edi, edi
0x180007293  jns     short loc_18000729C
0x180007295  mov     rax, [rbx+20h]
0x180007299  mov     [rax+10h], edi
0x18000729c  mov     rbx, [rsp+28h+arg_0]
0x1800072a1  mov     eax, edi
0x1800072a3  add     rsp, 20h
0x1800072a7  pop     rdi
0x1800072a8  retn
```
