# TpmRegistry::DeleteKeyValue(TpmRegistry::KEY_VALUES,ushort const *)

- ea: `0x1400055dc`
- end: `0x140005690`
- name: `?DeleteKeyValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBG@Z`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005370`
- `0x14002f0b0`

## callees

- `0x1400055dc`
- `0x140005a88`
- `0x14000c4e8`
- `0x14001a37c`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x140005631`
- `ntoskrnl!ZwDeleteValueKey` at `0x140005631`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005604`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005604`

## pseudocode

```c
__int64 __fastcall TpmRegistry::DeleteKeyValue(unsigned int a1, const WCHAR *a2)
{
  NTSTATUS v4; // ebx
  int v5; // r8d
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+60h] [rbp+18h] BYREF

  KeyHandle = 0;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v4 = TpmRegistry::OpenKey(a1, 2, &KeyHandle);
  if ( v4 >= 0 )
    v4 = ZwDeleteValueKey(KeyHandle, &ValueName);
  TpmRegistry::CloseKey(KeyHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_dSD(WPP_GLOBAL_Control->AttachedDevice, 27, v5, a1, (__int64)a2, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400055dc  mov     rax, rsp
0x1400055df  mov     [rax+8], rbx
0x1400055e3  mov     [rax+10h], rsi
0x1400055e7  push    rdi
0x1400055e8  sub     rsp, 40h
0x1400055ec  mov     esi, ecx
0x1400055ee  mov     qword ptr [rax+18h], 0
0x1400055f6  xorps   xmm0, xmm0
0x1400055f9  lea     rcx, [rax-18h]; DestinationString
0x1400055fd  movups  xmmword ptr [rax-18h], xmm0
0x140005601  mov     rdi, rdx
0x140005604  call    cs:__imp_RtlInitUnicodeString
0x14000560b  nop     dword ptr [rax+rax+00h]
0x140005610  lea     r8, [rsp+48h+KeyHandle]
0x140005615  mov     edx, 2
0x14000561a  mov     ecx, esi
0x14000561c  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAX@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,void * *)
0x140005621  mov     ebx, eax
0x140005623  test    eax, eax
0x140005625  js      short loc_14000563F
0x140005627  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14000562c  lea     rdx, [rsp+48h+ValueName]; ValueName
0x140005631  call    cs:__imp_ZwDeleteValueKey
0x140005638  nop     dword ptr [rax+rax+00h]
0x14000563d  mov     ebx, eax
0x14000563f  mov     rcx, [rsp+48h+KeyHandle]; void *
0x140005644  call    ?CloseKey@TpmRegistry@@CAXPEAX@Z; TpmRegistry::CloseKey(void *)
0x140005649  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140005650  lea     rax, WPP_GLOBAL_Control
0x140005657  cmp     rcx, rax
0x14000565a  jz      short loc_14000567D
0x14000565c  mov     eax, [rcx+2Ch]
0x14000565f  test    al, 4
0x140005661  jz      short loc_14000567D
0x140005663  mov     rcx, [rcx+18h]
0x140005667  mov     edx, 1Bh
0x14000566c  mov     [rsp+48h+var_20], ebx
0x140005670  mov     r9d, esi
0x140005673  mov     [rsp+48h+var_28], rdi
0x140005678  call    WPP_SF_dSD
0x14000567d  mov     rsi, [rsp+48h+arg_8]
0x140005682  mov     eax, ebx
0x140005684  mov     rbx, [rsp+48h+arg_0]
0x140005689  add     rsp, 40h
0x14000568d  pop     rdi
0x14000568e  retn
```
