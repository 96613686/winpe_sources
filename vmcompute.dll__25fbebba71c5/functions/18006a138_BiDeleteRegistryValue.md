# BiDeleteRegistryValue

- ea: `0x18006a138`
- end: `0x18006a209`
- name: `BiDeleteRegistryValue`
- size: `209`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180065404`
- `0x1800656c0`
- `0x1800658a0`
- `0x180065aa8`

## callees

- `0x18006a138`
- `0x18006a2d4`
- `0x18006b024`
- `0x18006fbc0`
- `0x180070e28`

## import_xrefs

- `ntdll!ZwClose` at `0x18006a1ea`
- `ntdll!ZwClose` at `0x18006a1ea`
- `ntdll!ZwDeleteValueKey` at `0x18006a1bc`
- `ntdll!ZwDeleteValueKey` at `0x18006a1bc`
- `ntdll!RtlInitUnicodeString` at `0x18006a15a`
- `ntdll!RtlInitUnicodeString` at `0x18006a15a`

## pseudocode

```c
__int64 __fastcall BiDeleteRegistryValue(__int64 a1, const WCHAR *a2, void *a3)
{
  unsigned __int64 v4; // rsi
  int v5; // eax
  unsigned __int64 v6; // rbx
  unsigned int v7; // edi
  unsigned int v8; // eax
  NTSTATUS v9; // eax
  struct _UNICODE_STRING ValueName; // [rsp+20h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp+18h] BYREF

  KeyHandle = a3;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v4 = a1 & 0xFFFFFFFFFFFFFFFDuLL;
  KeyHandle = 0;
  v5 = BiOpenKey(v4, L"Description", 131103, &KeyHandle);
  v6 = (unsigned __int64)KeyHandle;
  v7 = v5;
  if ( v5 >= 0 )
  {
    if ( ((unsigned __int8)KeyHandle & 1) != 0 )
    {
      v8 = ORDeleteValue((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL, ValueName.Buffer);
      v9 = BiDosErrorToNtStatus(v8);
    }
    else
    {
      v9 = ZwDeleteValueKey(KeyHandle, &ValueName);
    }
    v7 = v9;
  }
  if ( v6 != v4 && v6 )
  {
    if ( (v6 & 1) != 0 )
      ORCloseKey(v6 & 0xFFFFFFFFFFFFFFFEuLL);
    else
      ZwClose((HANDLE)v6);
  }
  return v7;
}

```

## disassembly

```asm
0x18006a138  mov     rax, rsp
0x18006a13b  mov     [rax+8], rbx
0x18006a13f  mov     [rax+10h], rsi
0x18006a143  mov     [rax+18h], r8
0x18006a147  push    rdi
0x18006a148  sub     rsp, 30h
0x18006a14c  mov     rsi, rcx
0x18006a14f  xorps   xmm0, xmm0
0x18006a152  lea     rcx, [rax-18h]; DestinationString
0x18006a156  movups  xmmword ptr [rax-18h], xmm0
0x18006a15a  call    cs:__imp_RtlInitUnicodeString
0x18006a161  nop     dword ptr [rax+rax+00h]
0x18006a166  and     rsi, 0FFFFFFFFFFFFFFFDh
0x18006a16a  mov     [rsp+38h+KeyHandle], 0
0x18006a173  mov     rcx, rsi
0x18006a176  lea     r9, [rsp+38h+KeyHandle]
0x18006a17b  mov     r8d, 2001Fh
0x18006a181  lea     rdx, aDescription; "Description"
0x18006a188  call    BiOpenKey
0x18006a18d  mov     rbx, [rsp+38h+KeyHandle]
0x18006a192  mov     edi, eax
0x18006a194  test    eax, eax
0x18006a196  js      short loc_18006A1CA
0x18006a198  mov     rcx, rbx; KeyHandle
0x18006a19b  test    bl, 1
0x18006a19e  jz      short loc_18006A1B7
0x18006a1a0  mov     rdx, [rsp+38h+ValueName.Buffer]
0x18006a1a5  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18006a1a9  call    ORDeleteValue
0x18006a1ae  mov     ecx, eax
0x18006a1b0  call    BiDosErrorToNtStatus
0x18006a1b5  jmp     short loc_18006A1C8
0x18006a1b7  lea     rdx, [rsp+38h+ValueName]; ValueName
0x18006a1bc  call    cs:__imp_ZwDeleteValueKey
0x18006a1c3  nop     dword ptr [rax+rax+00h]
0x18006a1c8  mov     edi, eax
0x18006a1ca  cmp     rbx, rsi
0x18006a1cd  jz      short loc_18006A1F6
0x18006a1cf  test    rbx, rbx
0x18006a1d2  jz      short loc_18006A1F6
0x18006a1d4  test    bl, 1
0x18006a1d7  jz      short loc_18006A1E7
0x18006a1d9  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006a1dd  mov     rcx, rbx
0x18006a1e0  call    ORCloseKey
0x18006a1e5  jmp     short loc_18006A1F6
0x18006a1e7  mov     rcx, rbx; Handle
0x18006a1ea  call    cs:__imp_ZwClose
0x18006a1f1  nop     dword ptr [rax+rax+00h]
0x18006a1f6  mov     rbx, [rsp+38h+arg_0]
0x18006a1fb  mov     eax, edi
0x18006a1fd  mov     rsi, [rsp+38h+arg_8]
0x18006a202  add     rsp, 30h
0x18006a206  pop     rdi
0x18006a207  retn
```
