# CUwfStaticConfiguration::set_ResetPersistentStateSavedMode(ulong)

- ea: `0x18000cd70`
- end: `0x18000cdd5`
- name: `?set_ResetPersistentStateSavedMode@CUwfStaticConfiguration@@QEAAJK@Z`
- size: `101`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1800179f0`

## callees

- `0x18000a150`
- `0x18000cd70`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_ResetPersistentStateSavedMode(
        CUwfStaticConfiguration *this,
        unsigned int a2)
{
  unsigned int v3; // edx
  int updated; // eax

  if ( *((_BYTE *)this + 9) )
  {
    v3 = -2147024891;
LABEL_3:
    *(_DWORD *)(*((_QWORD *)this + 4) + 16LL) = v3;
    return v3;
  }
  if ( a2 >= 2 )
  {
    v3 = -2147024809;
    goto LABEL_3;
  }
  updated = CUwfConfiguration::UpdateDWORDValue(
              *((CUwfConfiguration **)this + 4),
              (CUwfStaticConfiguration *)((char *)this + 16),
              L"ResetPersistentStateSavedMode",
              a2,
              1);
  v3 = updated;
  if ( updated < 0 )
    goto LABEL_3;
  if ( updated == 1 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x18000cd70  push    rbx
0x18000cd72  sub     rsp, 30h
0x18000cd76  cmp     byte ptr [rcx+9], 0
0x18000cd7a  mov     r9d, edx; unsigned int
0x18000cd7d  mov     rbx, rcx
0x18000cd80  jz      short loc_18000CD96
0x18000cd82  mov     edx, 80070005h
0x18000cd87  mov     rax, [rbx+20h]
0x18000cd8b  mov     [rax+10h], edx
0x18000cd8e  mov     eax, edx
0x18000cd90  add     rsp, 30h
0x18000cd94  pop     rbx
0x18000cd95  retn
0x18000cd96  mov     eax, r9d
0x18000cd99  test    r9d, r9d
0x18000cd9c  jz      short loc_18000CDAD
0x18000cd9e  sub     eax, 1
0x18000cda1  jz      short loc_18000CDAD
0x18000cda3  sub     eax, 1
0x18000cda6  mov     edx, 80070057h
0x18000cdab  jmp     short loc_18000CD87
0x18000cdad  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000cdb1  mov     [rsp+38h+var_18], 1; bool
0x18000cdb6  mov     rcx, [rcx+20h]; this
0x18000cdba  lea     r8, aResetpersisten; "ResetPersistentStateSavedMode"
0x18000cdc1  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000cdc6  mov     edx, eax
0x18000cdc8  test    eax, eax
0x18000cdca  js      short loc_18000CD87
0x18000cdcc  cmp     eax, 1
0x18000cdcf  jnz     short loc_18000CD8E
0x18000cdd1  xor     edx, edx
0x18000cdd3  jmp     short loc_18000CD8E
```
