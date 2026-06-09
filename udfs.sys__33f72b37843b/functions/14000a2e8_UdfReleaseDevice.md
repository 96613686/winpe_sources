# UdfReleaseDevice

- ea: `0x14000a2e8`
- end: `0x14000a31b`
- name: `UdfReleaseDevice`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x140008cac`
- `0x140009a60`
- `0x140009e80`
- `0x14000a0ec`
- `0x14000c728`
- `0x140011ea0`
- `0x140017fa8`
- `0x140019f5c`
- `0x14001a234`
- `0x14001a478`
- `0x14001acf8`
- `0x14002c330`
- `0x14003b79c`
- `0x140046750`
- `0x140054830`
- `0x140058114`

## callees

- `0x14000a2e8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000a2f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000a2f8`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000a30d`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14000a30d`

## pseudocode

```c
void __fastcall UdfReleaseDevice(__int64 a1, __int64 a2, ERESOURCE_THREAD a3)
{
  struct _ERESOURCE *v3; // rcx

  v3 = (struct _ERESOURCE *)(a2 + 136);
  if ( a3 )
    ExReleaseResourceForThreadLite(v3, a3);
  else
    ExReleaseResourceLite(v3);
}

```

## disassembly

```asm
0x14000a2e8  sub     rsp, 28h
0x14000a2ec  lea     rcx, [rdx+88h]; Resource
0x14000a2f3  test    r8, r8
0x14000a2f6  jnz     short loc_14000A30A
0x14000a2f8  call    cs:__imp_ExReleaseResourceLite
0x14000a2ff  nop     dword ptr [rax+rax+00h]
0x14000a304  add     rsp, 28h
0x14000a308  retn
0x14000a30a  mov     rdx, r8; ResourceThreadId
0x14000a30d  call    cs:__imp_ExReleaseResourceForThreadLite
0x14000a314  nop     dword ptr [rax+rax+00h]
0x14000a319  jmp     short loc_14000A304
```
