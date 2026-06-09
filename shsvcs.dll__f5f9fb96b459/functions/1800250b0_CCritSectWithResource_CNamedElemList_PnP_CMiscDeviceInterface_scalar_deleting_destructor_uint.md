# CCritSectWithResource<CNamedElemList<PnP::CMiscDeviceInterface>>::`scalar deleting destructor'(uint)

- ea: `0x1800250b0`
- end: `0x1800250fc`
- name: `??_G?$CCritSectWithResource@V?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@@@UEAAPEAXI@Z`
- size: `76`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001b3f8`
- `0x1800250b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800250da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800250da`

## pseudocode

```c
char *__fastcall CCritSectWithResource<CNamedElemList<PnP::CMiscDeviceInterface>>::`scalar deleting destructor'(
        char *Block,
        char a2)
{
  bool v2; // zf

  v2 = *((_DWORD *)Block + 12) == 0;
  *(_QWORD *)Block = &CCritSectWithResource<CNamedElemList<PnP::CMiscDeviceInterface>>::`vftable';
  if ( !v2 )
  {
    *((_DWORD *)Block + 12) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 8));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800250b0  mov     [rsp+arg_0], rbx
0x1800250b5  push    rdi
0x1800250b6  sub     rsp, 20h
0x1800250ba  cmp     dword ptr [rcx+30h], 0
0x1800250be  lea     rax, ??_7?$CCritSectWithResource@V?$CNamedElemList@VCMiscDeviceInterface@PnP@@@@@@6B@; const CCritSectWithResource<CNamedElemList<PnP::CMiscDeviceInterface>>::`vftable'
0x1800250c5  mov     [rcx], rax
0x1800250c8  mov     edi, edx
0x1800250ca  mov     rbx, rcx
0x1800250cd  jz      short loc_1800250E0
0x1800250cf  mov     dword ptr [rcx+30h], 0
0x1800250d6  add     rcx, 8; lpCriticalSection
0x1800250da  call    cs:__imp_DeleteCriticalSection
0x1800250e0  test    dil, 1
0x1800250e4  jz      short loc_1800250EE
0x1800250e6  mov     rcx, rbx; Block
0x1800250e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800250ee  mov     rax, rbx
0x1800250f1  mov     rbx, [rsp+28h+arg_0]
0x1800250f6  add     rsp, 20h
0x1800250fa  pop     rdi
0x1800250fb  retn
```
