# VmpQueryRegistryRevertEntries(VM_GPT_ATTRIBUTES_REVERT_ENTRY * *,ulong *)

- ea: `0x1400131f0`
- end: `0x1400132f0`
- name: `?VmpQueryRegistryRevertEntries@@YAJPEAPEAVVM_GPT_ATTRIBUTES_REVERT_ENTRY@@PEAK@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct VM_GPT_ATTRIBUTES_REVERT_ENTRY **, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140011bd8`
- `0x1400143a0`
- `0x1400184b0`

## callees

- `0x140005540`
- `0x1400131f0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400132ac`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400132ac`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140013280`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140013280`
- `ntoskrnl!ZwClose` at `0x1400132be`
- `ntoskrnl!ZwClose` at `0x1400132be`

## pseudocode

```c
__int64 __fastcall VmpQueryRegistryRevertEntries(struct VM_GPT_ATTRIBUTES_REVERT_ENTRY **a1, unsigned int *a2)
{
  struct VM_ROOT_EXTENSION *v4; // rcx
  __int64 v5; // rcx
  int v6; // ebx
  _QWORD v8[16]; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v9; // [rsp+C0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+6Fh]
  struct VM_GPT_ATTRIBUTES_REVERT_ENTRY *v11; // [rsp+D0h] [rbp+77h] BYREF

  v9 = 0;
  Handle = 0;
  memset(&v8[1], 0, 0x68u);
  v4 = VmRootExtension;
  v8[0] = &VmpQueryRegistryRevertEntriesCallback;
  *a1 = 0;
  v8[2] = L"GptAttributeRevertEntries";
  v8[3] = &v9;
  *a2 = 0;
  v5 = *((_QWORD *)v4 + 4);
  v11 = 0;
  LODWORD(v8[1]) = 4;
  v6 = IoOpenDriverRegistryKey(v5, 1, 1);
  if ( v6 >= 0 )
  {
    v6 = RtlQueryRegistryValuesEx(0x40000000, Handle, v8, &v11, 0);
    ZwClose(Handle);
    if ( v6 >= 0 )
    {
      *a1 = v11;
      *a2 = v9;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400131f0  mov     [rsp-8+arg_18], rbx
0x1400131f5  push    rbp
0x1400131f6  push    rsi
0x1400131f7  push    rdi
0x1400131f8  lea     rbp, [rsp-47h]
0x1400131fd  sub     rsp, 0A0h
0x140013204  mov     rdi, rdx
0x140013207  mov     [rbp+57h+arg_0], 0
0x14001320e  xor     edx, edx; Val
0x140013210  mov     [rbp+57h+Handle], 0
0x140013218  mov     rsi, rcx
0x14001321b  lea     rcx, [rbp+57h+var_78]; void *
0x14001321f  lea     r8d, [rdx+68h]; Size
0x140013223  call    memset
0x140013228  mov     rcx, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14001322f  lea     rax, VmpQueryRegistryRevertEntriesCallback
0x140013236  mov     [rbp+57h+var_80], rax
0x14001323a  xor     r9d, r9d
0x14001323d  mov     qword ptr [rsi], 0
0x140013244  lea     rax, ValueName; "GptAttributeRevertEntries"
0x14001324b  mov     [rbp+57h+var_70], rax
0x14001324f  lea     rax, [rbp+57h+arg_0]
0x140013253  mov     [rbp+57h+var_68], rax
0x140013257  lea     rax, [rbp+57h+Handle]
0x14001325b  lea     edx, [r9+1]
0x14001325f  mov     dword ptr [rdi], 0
0x140013265  mov     rcx, [rcx+20h]
0x140013269  mov     r8d, edx
0x14001326c  mov     [rsp+0B0h+var_90], rax
0x140013271  mov     [rbp+57h+arg_10], 0
0x140013279  mov     [rbp+57h+var_78], 4
0x140013280  call    cs:__imp_IoOpenDriverRegistryKey
0x140013287  nop     dword ptr [rax+rax+00h]
0x14001328c  mov     ebx, eax
0x14001328e  test    eax, eax
0x140013290  js      short loc_1400132DA
0x140013292  mov     rdx, [rbp+57h+Handle]
0x140013296  lea     r9, [rbp+57h+arg_10]
0x14001329a  lea     r8, [rbp+57h+var_80]
0x14001329e  mov     [rsp+0B0h+var_90], 0
0x1400132a7  mov     ecx, 40000000h
0x1400132ac  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400132b3  nop     dword ptr [rax+rax+00h]
0x1400132b8  mov     rcx, [rbp+57h+Handle]; Handle
0x1400132bc  mov     ebx, eax
0x1400132be  call    cs:__imp_ZwClose
0x1400132c5  nop     dword ptr [rax+rax+00h]
0x1400132ca  test    ebx, ebx
0x1400132cc  js      short loc_1400132DA
0x1400132ce  mov     rax, [rbp+57h+arg_10]
0x1400132d2  mov     [rsi], rax
0x1400132d5  mov     eax, [rbp+57h+arg_0]
0x1400132d8  mov     [rdi], eax
0x1400132da  mov     eax, ebx
0x1400132dc  mov     rbx, [rsp+0B0h+arg_18]
0x1400132e4  add     rsp, 0A0h
0x1400132eb  pop     rdi
0x1400132ec  pop     rsi
0x1400132ed  pop     rbp
0x1400132ee  retn
```
