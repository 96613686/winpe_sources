# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x180012230`
- end: `0x180012287`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `87`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800131b0`
- `0x180013290`
- `0x1800133f0`
- `0x180013990`
- `0x180013e30`
- `0x180013fa0`
- `0x1800140f0`
- `0x180014230`

## callees

- `0x180012230`
- `0x180012640`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180012280`
- `KERNEL32!RaiseException` at `0x180012280`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2)
{
  unsigned __int64 v3; // r9
  const WCHAR *v4; // rdx

  a1[1].Reserved.Reserved1 = 0;
  v3 = -1;
  v4 = *a2;
  do
    ++v3;
  while ( v4[v3] );
  if ( v3 > 0xFFFFFFFF || (int)v3 + 1 < (unsigned int)v3 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x180012286LL);
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(a1, v4, v3 + 1, v3);
  return a1;
}

```

## disassembly

```asm
0x180012230  push    rbx
0x180012232  sub     rsp, 20h
0x180012236  xor     eax, eax
0x180012238  mov     rbx, rcx
0x18001223b  mov     [rcx+18h], rax
0x18001223f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180012243  mov     rdx, [rdx]; sourceString
0x180012246  inc     r9; unsigned int
0x180012249  cmp     [rdx+r9*2], ax
0x18001224e  jnz     short loc_180012246
0x180012250  mov     eax, 0FFFFFFFFh
0x180012255  cmp     r9, rax
0x180012258  ja      short loc_180012271
0x18001225a  lea     r8d, [r9+1]; unsigned int
0x18001225e  cmp     r8d, r9d
0x180012261  jb      short loc_180012271
0x180012263  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180012268  mov     rax, rbx
0x18001226b  add     rsp, 20h
0x18001226f  pop     rbx
0x180012270  retn
0x180012271  xor     r9d, r9d; lpArguments
0x180012274  xor     r8d, r8d; nNumberOfArguments
0x180012277  mov     ecx, 80070216h; dwExceptionCode
0x18001227c  lea     edx, [r9+1]; dwExceptionFlags
0x180012280  call    cs:__imp_RaiseException
```
