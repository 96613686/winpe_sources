# SclpUefiRefreshDiskBootConfig

- ea: `0x18000f4e4`
- end: `0x18000f667`
- name: `SclpUefiRefreshDiskBootConfig`
- size: `387`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f110`

## callees

- `0x18000a524`
- `0x18000e834`
- `0x18000ec38`
- `0x18000f4e4`
- `0x180012ce8`
- `0x180012d0c`
- `0x18001378c`
- `0x180018010`

## string_xrefs

- `0x18000f507`: `SclpUefiRefreshDiskBootConfig`

## pseudocode

```c
__int64 __fastcall SclpUefiRefreshDiskBootConfig(__int64 a1)
{
  __int64 v1; // r14
  int v3; // ecx
  __int64 v4; // rax
  __int64 v5; // rdi
  unsigned int v6; // esi
  __int64 v7; // rax
  __int64 v8; // rbx
  int v10; // [rsp+70h] [rbp+8h] BYREF

  v1 = a1 + 1152;
  if ( !a1 )
    v1 = 0;
  SclLogGenericMessage(
    v1,
    1,
    (int)SclEvent_Generic_Info,
    463,
    (__int64)"SclpUefiRefreshDiskBootConfig",
    "Updating boot entries to use new GUIDs.");
  AllocRoutine = (__int64 (__fastcall *)(_QWORD))SclExeMalloc;
  FreeRoutine = SclExeFree;
  v4 = EFIOSBOCreateEx(v3);
  v5 = v4;
  if ( v4 )
  {
    v10 = 0;
    v7 = OSBOGetFirstBootEntry(v4, &v10);
LABEL_6:
    v8 = v7;
    while ( 1 )
    {
      v6 = 0;
      if ( !v7 )
        break;
      if ( (*(_BYTE *)(v7 + 3128) & 4) != 0 )
      {
        if ( OSBESetFriendlyName(v7, v7 + 8) )
        {
          (*(void (__fastcall **)(__int64))(v8 + 3160))(v8);
          SclpGetAndWriteBootEntry(a1, v8);
          v7 = OSBOGetNextBootEntry(v5, &v10);
          goto LABEL_6;
        }
        v6 = -1073741823;
        SclLogGenericMessage(
          v1,
          3,
          (int)SclEvent_Generic_Error,
          509,
          (__int64)"SclpUefiRefreshDiskBootConfig",
          "Failed to reset the friendly name for boot entry [%ws]",
          v8 + 8);
        break;
      }
    }
    (*(void (__fastcall **)(__int64))(v5 + 104))(v5);
    (*(void (__fastcall **)(__int64))(v5 + 96))(v5);
  }
  else
  {
    v6 = -1073741823;
    SclLogGenericMessage(
      v1,
      3,
      (int)SclEvent_Generic_Error,
      481,
      (__int64)"SclpUefiRefreshDiskBootConfig",
      "Failed to initialize the boot options library.");
  }
  return v6;
}

```

## disassembly

```asm
0x18000f4e4  mov     r11, rsp
0x18000f4e7  mov     [r11+10h], rbx
0x18000f4eb  mov     [r11+18h], rbp
0x18000f4ef  push    rsi
0x18000f4f0  push    rdi
0x18000f4f1  push    r12
0x18000f4f3  push    r14
0x18000f4f5  push    r15
0x18000f4f7  sub     rsp, 40h
0x18000f4fb  xor     eax, eax
0x18000f4fd  lea     r14, [rcx+480h]
0x18000f504  test    rcx, rcx
0x18000f507  lea     r12, aSclpuefirefres; "SclpUefiRefreshDiskBootConfig"
0x18000f50e  mov     r15, rcx
0x18000f511  lea     r8, SclEvent_Generic_Info
0x18000f518  cmovz   r14, rax
0x18000f51c  mov     r9d, 1CFh
0x18000f522  lea     rax, aUpdatingBootEn; "Updating boot entries to use new GUIDs."
0x18000f529  mov     edx, 1
0x18000f52e  mov     [r11-40h], rax
0x18000f532  mov     rcx, r14
0x18000f535  mov     [r11-48h], r12
0x18000f539  call    SclLogGenericMessage
0x18000f53e  lea     rax, SclExeMalloc
0x18000f545  mov     cs:AllocRoutine, rax
0x18000f54c  lea     rax, SclExeFree
0x18000f553  mov     cs:FreeRoutine, rax
0x18000f55a  call    EFIOSBOCreateEx
0x18000f55f  mov     rdi, rax
0x18000f562  test    rax, rax
0x18000f565  jnz     short loc_18000F59A
0x18000f567  lea     rax, aFailedToInitia; "Failed to initialize the boot options l"...
0x18000f56e  mov     r9d, 1E1h
0x18000f574  mov     [rsp+68h+var_40], rax
0x18000f579  lea     r8, SclEvent_Generic_Error
0x18000f580  lea     edx, [rdi+3]
0x18000f583  mov     [rsp+68h+var_48], r12
0x18000f588  mov     rcx, r14
0x18000f58b  mov     esi, 0C0000001h
0x18000f590  call    SclLogGenericMessage
0x18000f595  jmp     loc_18000F64C
0x18000f59a  lea     rdx, [rsp+68h+arg_0]
0x18000f59f  mov     [rsp+68h+arg_0], 0
0x18000f5a7  mov     rcx, rdi
0x18000f5aa  call    OSBOGetFirstBootEntry
0x18000f5af  mov     rbx, rax
0x18000f5b2  xor     esi, esi
0x18000f5b4  test    rbx, rbx
0x18000f5b7  jz      short loc_18000F634
0x18000f5b9  test    byte ptr [rbx+0C38h], 4
0x18000f5c0  jz      short loc_18000F5B2
0x18000f5c2  lea     rbp, [rbx+8]
0x18000f5c6  mov     rcx, rbx
0x18000f5c9  mov     rdx, rbp
0x18000f5cc  call    OSBESetFriendlyName
0x18000f5d1  test    rax, rax
0x18000f5d4  jz      short loc_18000F5FF
0x18000f5d6  mov     rax, [rbx+0C58h]
0x18000f5dd  mov     rcx, rbx
0x18000f5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5e5  mov     rdx, rbx
0x18000f5e8  mov     rcx, r15
0x18000f5eb  call    SclpGetAndWriteBootEntry
0x18000f5f0  lea     rdx, [rsp+68h+arg_0]
0x18000f5f5  mov     rcx, rdi
0x18000f5f8  call    OSBOGetNextBootEntry
0x18000f5fd  jmp     short loc_18000F5AF
0x18000f5ff  lea     rax, aFailedToResetT; "Failed to reset the friendly name for b"...
0x18000f606  mov     [rsp+68h+var_38], rbp
0x18000f60b  mov     [rsp+68h+var_40], rax
0x18000f610  lea     r8, SclEvent_Generic_Error
0x18000f617  mov     r9d, 1FDh
0x18000f61d  mov     [rsp+68h+var_48], r12
0x18000f622  mov     edx, 3
0x18000f627  mov     rcx, r14
0x18000f62a  mov     esi, 0C0000001h
0x18000f62f  call    SclLogGenericMessage
0x18000f634  mov     rax, [rdi+68h]
0x18000f638  mov     rcx, rdi
0x18000f63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f640  mov     rax, [rdi+60h]
0x18000f644  mov     rcx, rdi
0x18000f647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64c  lea     r11, [rsp+68h+var_28]
0x18000f651  mov     eax, esi
0x18000f653  mov     rbx, [r11+38h]
0x18000f657  mov     rbp, [r11+40h]
0x18000f65b  mov     rsp, r11
0x18000f65e  pop     r15
0x18000f660  pop     r14
0x18000f662  pop     r12
0x18000f664  pop     rdi
0x18000f665  pop     rsi
0x18000f666  retn
```
