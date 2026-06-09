# GetPid4FromRegistryInternal

- ea: `0x18003b294`
- end: `0x18003b34b`
- name: `GetPid4FromRegistryInternal`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b878`

## callees

- `0x180003520`
- `0x180004288`
- `0x18003b294`
- `0x18003b570`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b32c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b32c`

## pseudocode

```c
__int64 __fastcall GetPid4FromRegistryInternal(HLOCAL *a1)
{
  int Value; // eax
  unsigned int v3; // edi
  __int64 v4; // rcx
  HLOCAL v5; // rbx
  DWORD v7; // [rsp+48h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+18h] BYREF

  hMem = 0;
  v7 = 0;
  Value = CRegUtilT<void *,CRegType,0,1>::GetValue(
            (__int64)a1,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\",
            L"DigitalProductId4",
            (BYTE **)&hMem,
            &v7);
  v3 = Value;
  if ( Value < 0 )
  {
    v4 = (unsigned int)Value;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    v5 = hMem;
    goto LABEL_9;
  }
  if ( v7 < 0x4F8 )
  {
    v4 = 2147942413LL;
    v3 = -2147024883;
    goto LABEL_3;
  }
  v5 = hMem;
  if ( v7 == *(_DWORD *)hMem )
  {
    v5 = 0;
    *a1 = hMem;
  }
  else
  {
    v3 = -2147024883;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942413LL);
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v5 )
    LocalFree(v5);
  return v3;
}

```

## disassembly

```asm
0x18003b294  mov     r11, rsp
0x18003b297  mov     [r11+8], rbx
0x18003b29b  mov     [r11+20h], rsi
0x18003b29f  push    rdi
0x18003b2a0  sub     rsp, 30h
0x18003b2a4  lea     rax, [r11+10h]
0x18003b2a8  mov     qword ptr [r11+18h], 0
0x18003b2b0  lea     r9, [r11+18h]
0x18003b2b4  mov     [r11-18h], rax
0x18003b2b8  lea     r8, aDigitalproduct; "DigitalProductId4"
0x18003b2bf  mov     [rsp+38h+arg_8], 0
0x18003b2c7  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003b2ce  mov     rsi, rcx
0x18003b2d1  call    ?GetValue@?$CRegUtilT@PEAXUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAXPEAK@Z; CRegUtilT<void *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,void * *,ulong *)
0x18003b2d6  mov     edi, eax
0x18003b2d8  test    eax, eax
0x18003b2da  jns     short loc_18003B2EA
0x18003b2dc  mov     ecx, eax
0x18003b2de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b2e3  mov     rbx, [rsp+38h+hMem]
0x18003b2e8  jmp     short loc_18003B31D
0x18003b2ea  mov     eax, [rsp+38h+arg_8]
0x18003b2ee  cmp     eax, 4F8h
0x18003b2f3  jnb     short loc_18003B2FE
0x18003b2f5  mov     ecx, 8007000Dh
0x18003b2fa  mov     edi, ecx
0x18003b2fc  jmp     short loc_18003B2DE
0x18003b2fe  mov     rbx, [rsp+38h+hMem]
0x18003b303  cmp     eax, [rbx]
0x18003b305  jz      short loc_18003B315
0x18003b307  mov     ecx, 8007000Dh
0x18003b30c  mov     edi, ecx
0x18003b30e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b313  jmp     short loc_18003B31D
0x18003b315  mov     rax, rbx
0x18003b318  xor     ebx, ebx
0x18003b31a  mov     [rsi], rax
0x18003b31d  mov     ecx, edi
0x18003b31f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b324  test    rbx, rbx
0x18003b327  jz      short loc_18003B338
0x18003b329  mov     rcx, rbx; hMem
0x18003b32c  call    cs:__imp_LocalFree
0x18003b333  nop     dword ptr [rax+rax+00h]
0x18003b338  mov     rbx, [rsp+38h+arg_0]
0x18003b33d  mov     eax, edi
0x18003b33f  mov     rsi, [rsp+38h+arg_18]
0x18003b344  add     rsp, 30h
0x18003b348  pop     rdi
0x18003b349  retn
```
