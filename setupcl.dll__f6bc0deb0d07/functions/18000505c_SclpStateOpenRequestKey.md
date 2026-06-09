# SclpStateOpenRequestKey

- ea: `0x18000505c`
- end: `0x18000513d`
- name: `SclpStateOpenRequestKey`
- size: `225`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180001de0`
- `0x180002010`
- `0x180002640`

## callees

- `0x1800014e8`
- `0x18000505c`
- `0x18000a524`

## import_xrefs

- `ntdll!NtClose` at `0x18000512c`
- `ntdll!NtClose` at `0x18000512c`

## string_xrefs

- `0x1800050d6`: `\REGISTRY\MACHINE\SYSTEM\SETUP\SETUPCL`
- `0x180005084`: `Manipulating a pended request in offline mode requires access to the offline SYSTEM hive.`
- `0x18000509d`: `SclpStateOpenRequestKey`
- `0x180005104`: `\REGISTRY\MACHINE\SYSTEM\SETUP\SETUPCL\PendingRequest`

## pseudocode

```c
__int64 __fastcall SclpStateOpenRequestKey(__int64 a1, __int64 a2)
{
  int v3; // ebx
  int Key; // edi
  __int64 v5; // rsi
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rdx
  HANDLE Handle; // [rsp+70h] [rbp+18h] BYREF

  Handle = 0;
  if ( !a1 )
  {
    v3 = 1;
    goto LABEL_8;
  }
  v3 = *(_DWORD *)a1;
  if ( *(_DWORD *)a1 == 2 )
  {
    if ( !*(_QWORD *)(a1 + 56) )
    {
      SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 1427, (__int64)"SclpStateOpenRequestKey");
      Key = -1073741811;
      goto LABEL_15;
    }
    goto LABEL_6;
  }
  if ( v3 == 1 )
  {
LABEL_8:
    v5 = 0;
    goto LABEL_9;
  }
LABEL_6:
  v5 = *(_QWORD *)(a1 + 56);
LABEL_9:
  v6 = L"\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SETUPCL";
  if ( v3 != 1 )
    v6 = L"SETUP\\SETUPCL";
  Key = SclCreateKey(v5, v6, 983103, &Handle);
  if ( Key >= 0 )
  {
    v7 = L"\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SETUPCL\\PendingRequest";
    if ( v3 != 1 )
      v7 = L"SETUP\\SETUPCL\\PendingRequest";
    Key = SclCreateKey(v5, v7, 983103, a2);
  }
LABEL_15:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18000505c  push    rbx
0x18000505e  push    rbp
0x18000505f  push    rsi
0x180005060  push    rdi
0x180005061  sub     rsp, 38h
0x180005065  mov     [rsp+58h+Handle], 0
0x18000506e  mov     rbp, rdx
0x180005071  test    rcx, rcx
0x180005074  jz      short loc_1800050C5
0x180005076  mov     ebx, [rcx]
0x180005078  cmp     ebx, 2
0x18000507b  jnz     short loc_1800050BA
0x18000507d  cmp     qword ptr [rcx+38h], 0
0x180005082  jnz     short loc_1800050BF
0x180005084  lea     rax, aManipulatingAP; "Manipulating a pended request in offlin"...
0x18000508b  mov     r9d, 593h
0x180005091  mov     [rsp+58h+var_30], rax
0x180005096  lea     r8, SclEvent_Generic_Error
0x18000509d  lea     rax, aSclpstateopenr; "SclpStateOpenRequestKey"
0x1800050a4  xor     ecx, ecx
0x1800050a6  lea     edx, [rbx+1]
0x1800050a9  mov     [rsp+58h+var_38], rax
0x1800050ae  call    SclLogGenericMessage
0x1800050b3  mov     edi, 0C000000Dh
0x1800050b8  jmp     short loc_180005122
0x1800050ba  cmp     ebx, 1
0x1800050bd  jz      short loc_1800050CA
0x1800050bf  mov     rsi, [rcx+38h]
0x1800050c3  jmp     short loc_1800050CC
0x1800050c5  mov     ebx, 1
0x1800050ca  xor     esi, esi
0x1800050cc  lea     rax, aSetupSetupcl; "SETUP\\SETUPCL"
0x1800050d3  cmp     ebx, 1
0x1800050d6  lea     rdx, aRegistryMachin_2; "\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SET"...
0x1800050dd  mov     r8d, 0F003Fh
0x1800050e3  cmovnz  rdx, rax
0x1800050e7  lea     r9, [rsp+58h+Handle]
0x1800050ec  mov     rcx, rsi
0x1800050ef  call    SclCreateKey
0x1800050f4  mov     edi, eax
0x1800050f6  test    eax, eax
0x1800050f8  js      short loc_180005122
0x1800050fa  cmp     ebx, 1
0x1800050fd  lea     rax, aSetupSetupclPe; "SETUP\\SETUPCL\\PendingRequest"
0x180005104  lea     rdx, aRegistryMachin_8; "\\REGISTRY\\MACHINE\\SYSTEM\\SETUP\\SET"...
0x18000510b  mov     r9, rbp
0x18000510e  cmovnz  rdx, rax
0x180005112  mov     r8d, 0F003Fh
0x180005118  mov     rcx, rsi
0x18000511b  call    SclCreateKey
0x180005120  mov     edi, eax
0x180005122  mov     rcx, [rsp+58h+Handle]; Handle
0x180005127  test    rcx, rcx
0x18000512a  jz      short loc_180005132
0x18000512c  call    cs:__imp_NtClose
0x180005132  mov     eax, edi
0x180005134  add     rsp, 38h
0x180005138  pop     rdi
0x180005139  pop     rsi
0x18000513a  pop     rbp
0x18000513b  pop     rbx
0x18000513c  retn
```
