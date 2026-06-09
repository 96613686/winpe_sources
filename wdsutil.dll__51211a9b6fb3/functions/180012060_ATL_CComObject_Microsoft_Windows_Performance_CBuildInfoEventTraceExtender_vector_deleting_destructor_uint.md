# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180012060`
- end: `0x180012097`
- name: `??_E?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180011f68`
- `0x180012060`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001207c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001207c`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(
        void *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180012060  mov     [rsp+arg_0], rbx
0x180012065  push    rdi
0x180012066  sub     rsp, 20h
0x18001206a  mov     ebx, edx
0x18001206c  mov     rdi, rcx
0x18001206f  call    ??1?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(void)
0x180012074  test    bl, 1
0x180012077  jz      short loc_180012088
0x180012079  mov     rcx, rdi
0x18001207c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012083  nop     dword ptr [rax+rax+00h]
0x180012088  mov     rbx, [rsp+28h+arg_0]
0x18001208d  mov     rax, rdi
0x180012090  add     rsp, 20h
0x180012094  pop     rdi
0x180012095  retn
```
