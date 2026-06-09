# CUwfStaticVolumeConfiguration::RemoveAllFileExclusions(void)

- ea: `0x180008d30`
- end: `0x180008d90`
- name: `?RemoveAllFileExclusions@CUwfStaticVolumeConfiguration@@QEAAJXZ`
- size: `96`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180008d30`
- `0x18000e480`
- `0x18000e4d0`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::RemoveAllFileExclusions(CUwfStaticVolumeConfiguration *this)
{
  int v2; // edx

  if ( *((_BYTE *)this + 9) )
  {
    v2 = -2147024891;
LABEL_5:
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = v2;
    return (unsigned int)v2;
  }
  v2 = CUwfRegKey::SetMultiSzValue(
         (CUwfStaticVolumeConfiguration *)((char *)this + 16),
         L"FileExceptionsUserDefined",
         0);
  if ( v2 < 0 )
    goto LABEL_5;
  v2 = CUwfRegKey::SetDWORDValue(
         (CUwfStaticVolumeConfiguration *)((char *)this + 16),
         L"NumFileExceptionsUserDefined",
         0);
  if ( v2 < 0 )
    goto LABEL_5;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180008d30  mov     [rsp+arg_0], rbx
0x180008d35  push    rdi
0x180008d36  sub     rsp, 20h
0x180008d3a  cmp     byte ptr [rcx+9], 0
0x180008d3e  mov     rbx, rcx
0x180008d41  jz      short loc_180008D4A
0x180008d43  mov     edx, 80070005h
0x180008d48  jmp     short loc_180008D7C
0x180008d4a  xor     r8d, r8d; struct _MULTISZ *
0x180008d4d  lea     rdx, Value; "FileExceptionsUserDefined"
0x180008d54  add     rcx, 10h; this
0x180008d58  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x180008d5d  mov     edx, eax
0x180008d5f  test    eax, eax
0x180008d61  js      short loc_180008D7C
0x180008d63  xor     r8d, r8d; unsigned int
0x180008d66  lea     rdx, aNumfileexcepti; "NumFileExceptionsUserDefined"
0x180008d6d  lea     rcx, [rbx+10h]; this
0x180008d71  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x180008d76  mov     edx, eax
0x180008d78  test    eax, eax
0x180008d7a  jns     short loc_180008D83
0x180008d7c  mov     rax, [rbx+18h]
0x180008d80  mov     [rax+10h], edx
0x180008d83  mov     rbx, [rsp+28h+arg_0]
0x180008d88  mov     eax, edx
0x180008d8a  add     rsp, 20h
0x180008d8e  pop     rdi
0x180008d8f  retn
```
