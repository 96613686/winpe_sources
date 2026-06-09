# InitImageInformation(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x140017650`
- end: `0x140017693`
- name: `?InitImageInformation@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `67`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ntoskrnl!RtlImageNtHeader` at `0x140017662`
- `ntoskrnl!RtlImageNtHeader` at `0x140017662`

## pseudocode

```c
__int64 __fastcall InitImageInformation(PRTL_RUN_ONCE a1, PVOID a2, PVOID *a3)
{
  PIMAGE_NT_HEADERS v3; // rax

  qword_14001E0A8 = 0x140000000uLL;
  v3 = RtlImageNtHeader((PVOID)0x140000000LL);
  qword_14001E0B8 = qword_14001E0A8 + v3->OptionalHeader.AddressOfEntryPoint;
  dword_14001E0C0 = v3->OptionalHeader.SizeOfImage;
  return 1;
}

```

## disassembly

```asm
0x140017650  sub     rsp, 28h
0x140017654  lea     rcx, cs:140000000h; BaseAddress
0x14001765b  mov     cs:qword_14001E0A8, rcx
0x140017662  call    cs:__imp_RtlImageNtHeader
0x140017669  nop     dword ptr [rax+rax+00h]
0x14001766e  mov     ecx, [rax+28h]
0x140017671  add     rcx, cs:qword_14001E0A8
0x140017678  mov     cs:qword_14001E0B8, rcx
0x14001767f  mov     eax, [rax+50h]
0x140017682  mov     cs:dword_14001E0C0, eax
0x140017688  mov     eax, 1
0x14001768d  add     rsp, 28h
0x140017691  retn
```
