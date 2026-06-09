# CUwfStaticConfiguration::set_OverlayFlags(ulong)

- ea: `0x18000c190`
- end: `0x18000c1f8`
- name: `?set_OverlayFlags@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `104`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000c300`
- `0x180017550`

## callees

- `0x18000a150`
- `0x18000c190`
- `0x18000cf40`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_OverlayFlags(CUwfStaticConfiguration *this, char a2)
{
  CUwfConfiguration **v2; // rbx
  int updated; // edx

  v2 = (CUwfConfiguration **)((char *)this + 32);
  if ( *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
LABEL_5:
    *((_DWORD *)*v2 + 4) = updated;
    return (unsigned int)updated;
  }
  updated = CUwfConfiguration::UpdateDWORDValue(
              *v2,
              (CUwfStaticConfiguration *)((char *)this + 16),
              L"OverlayFlags",
              a2,
              1);
  if ( updated < 0 )
    goto LABEL_5;
  updated = CUwfConfiguration::set_UwfBootPersistenceEnabled(*v2, (a2 & 2) != 0);
  if ( updated < 0 )
    goto LABEL_5;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000c190  mov     [rsp+arg_0], rbx
0x18000c195  push    rdi
0x18000c196  sub     rsp, 30h
0x18000c19a  cmp     byte ptr [rcx+9], 0
0x18000c19e  lea     rbx, [rcx+20h]
0x18000c1a2  mov     edi, edx
0x18000c1a4  jz      short loc_18000C1AD
0x18000c1a6  mov     edx, 80070005h
0x18000c1ab  jmp     short loc_18000C1E5
0x18000c1ad  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000c1b1  mov     [rsp+38h+var_18], 1; bool
0x18000c1b6  mov     rcx, [rbx]; this
0x18000c1b9  lea     r8, aOverlayflags; "OverlayFlags"
0x18000c1c0  mov     r9d, edi; unsigned int
0x18000c1c3  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000c1c8  mov     edx, eax
0x18000c1ca  test    eax, eax
0x18000c1cc  js      short loc_18000C1E5
0x18000c1ce  mov     rcx, [rbx]; this
0x18000c1d1  shr     edi, 1
0x18000c1d3  and     dil, 1
0x18000c1d7  mov     dl, dil; bool
0x18000c1da  call    ?set_UwfBootPersistenceEnabled@CUwfConfiguration@@QEAAJ_N@Z; CUwfConfiguration::set_UwfBootPersistenceEnabled(bool)
0x18000c1df  mov     edx, eax
0x18000c1e1  test    eax, eax
0x18000c1e3  jns     short loc_18000C1EB
0x18000c1e5  mov     rax, [rbx]
0x18000c1e8  mov     [rax+10h], edx
0x18000c1eb  mov     rbx, [rsp+38h+arg_0]
0x18000c1f0  mov     eax, edx
0x18000c1f2  add     rsp, 30h
0x18000c1f6  pop     rdi
0x18000c1f7  retn
```
