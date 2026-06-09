# pSetupOpenPredefinedKey

- ea: `0x18000c944`
- end: `0x18000c9bb`
- name: `pSetupOpenPredefinedKey`
- size: `119`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bb04`
- `0x18000c650`

## callees

- `0x18000c650`
- `0x18000c944`
- `0x180018290`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000c99e`
- `ntdll!RtlFreeUnicodeString` at `0x18000c99e`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000c963`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18000c963`
- `ntdll!RtlNtStatusToDosError` at `0x18000c96f`
- `ntdll!RtlNtStatusToDosError` at `0x18000c96f`

## pseudocode

```c
__int64 __fastcall pSetupOpenPredefinedKey(__int64 a1, _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  const WCHAR *Buffer; // rax
  unsigned int v6; // ebx
  struct _UNICODE_STRING KeyPath; // [rsp+20h] [rbp-18h] BYREF

  KeyPath = 0;
  if ( a1 == -2147483647 )
  {
    v3 = RtlFormatCurrentUserKeyPath(&KeyPath);
    if ( v3 < 0 )
    {
      v4 = RtlNtStatusToDosError(v3);
LABEL_6:
      v6 = v4;
      goto LABEL_7;
    }
    Buffer = KeyPath.Buffer;
LABEL_5:
    v4 = pSetupOpenKeyEx(0, Buffer, 0x2000000u, a2);
    goto LABEL_6;
  }
  Buffer = pSetupGetPredefinedKeyPath(a1);
  if ( Buffer )
    goto LABEL_5;
  v6 = 50;
LABEL_7:
  if ( KeyPath.Buffer )
    RtlFreeUnicodeString(&KeyPath);
  return v6;
}

```

## disassembly

```asm
0x18000c944  push    rbx
0x18000c946  sub     rsp, 30h
0x18000c94a  xorps   xmm0, xmm0
0x18000c94d  mov     rbx, rdx
0x18000c950  movups  xmmword ptr [rsp+38h+KeyPath.Length], xmm0
0x18000c955  cmp     rcx, 0FFFFFFFF80000001h
0x18000c95c  jnz     short loc_18000C9AC
0x18000c95e  lea     rcx, [rsp+38h+KeyPath]; KeyPath
0x18000c963  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18000c969  test    eax, eax
0x18000c96b  jns     short loc_18000C977
0x18000c96d  mov     ecx, eax; Status
0x18000c96f  call    cs:__imp_RtlNtStatusToDosError
0x18000c975  jmp     short loc_18000C98F
0x18000c977  mov     rax, [rsp+38h+KeyPath.Buffer]
0x18000c97c  mov     r9, rbx
0x18000c97f  mov     r8d, 2000000h
0x18000c985  mov     rdx, rax
0x18000c988  xor     ecx, ecx
0x18000c98a  call    pSetupOpenKeyEx
0x18000c98f  mov     ebx, eax
0x18000c991  cmp     [rsp+38h+KeyPath.Buffer], 0
0x18000c997  jz      short loc_18000C9A4
0x18000c999  lea     rcx, [rsp+38h+KeyPath]; UnicodeString
0x18000c99e  call    cs:__imp_RtlFreeUnicodeString
0x18000c9a4  mov     eax, ebx
0x18000c9a6  add     rsp, 30h
0x18000c9aa  pop     rbx
0x18000c9ab  retn
0x18000c9ac  call    pSetupGetPredefinedKeyPath
0x18000c9b1  test    rax, rax
0x18000c9b4  jnz     short loc_18000C97C
0x18000c9b6  lea     ebx, [rax+32h]
0x18000c9b9  jmp     short loc_18000C991
```
