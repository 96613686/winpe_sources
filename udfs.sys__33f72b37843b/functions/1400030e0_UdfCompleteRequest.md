# UdfCompleteRequest

- ea: `0x1400030e0`
- end: `0x140003140`
- name: `UdfCompleteRequest`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010f0`
- `0x140003148`
- `0x1400077f0`
- `0x1400094c0`
- `0x140009b94`
- `0x14000dc18`
- `0x14000feb4`
- `0x140010f38`
- `0x140012e94`
- `0x140015a34`
- `0x14002d25c`
- `0x14002e198`
- `0x14002e280`
- `0x14002e31c`
- `0x14002f034`
- `0x1400318f4`
- `0x1400319f8`
- `0x140031f84`
- `0x140035794`
- `0x140035c3c`
- `0x140035ca4`
- `0x14003604c`
- `0x1400361d8`
- `0x1400362e0`
- `0x140036494`
- `0x140036578`
- `0x140036790`
- `0x140036888`
- `0x1400369d4`
- `0x140036b0c`
- `0x140036c38`
- `0x140037544`
- `0x1400375d8`
- `0x140037770`
- `0x14003787c`
- `0x14003a188`
- `0x14003a700`
- `0x14003a7a4`
- `0x14003f440`
- `0x14003f4c8`
- `0x140042c40`
- `0x140044f90`
- `0x140047a10`
- `0x140049f20`
- `0x140049f80`
- `0x14004b594`
- `0x140053260`
- `0x1400541a8`
- `0x140054830`
- `0x140055060`

## callees

- `0x1400030e0`
- `0x140044860`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140003117`
- `ntoskrnl!IofCompleteRequest` at `0x140003117`

## pseudocode

```c
void __fastcall UdfCompleteRequest(void *a1, IRP *a2, NTSTATUS a3)
{
  if ( a1 )
    UdfCleanupIrpContext(a1);
  if ( a2 )
  {
    if ( (a3 & 0xC0000000) == 0xC0000000 && (a2->Flags & 0x40) != 0 )
      a2->IoStatus.Information = 0;
    a2->IoStatus.Status = a3;
    IofCompleteRequest(a2, 1);
  }
}

```

## disassembly

```asm
0x1400030e0  mov     [rsp+arg_0], rbx
0x1400030e5  push    rdi
0x1400030e6  sub     rsp, 20h
0x1400030ea  mov     edi, r8d
0x1400030ed  mov     rbx, rdx
0x1400030f0  test    rcx, rcx
0x1400030f3  jz      short loc_1400030FC
0x1400030f5  xor     edx, edx
0x1400030f7  call    UdfCleanupIrpContext
0x1400030fc  test    rbx, rbx
0x1400030ff  jz      short loc_140003123
0x140003101  mov     eax, edi
0x140003103  and     eax, 0C0000000h
0x140003108  cmp     eax, 0C0000000h
0x14000310d  jz      short loc_14000312F
0x14000310f  mov     dl, 1; PriorityBoost
0x140003111  mov     [rbx+30h], edi
0x140003114  mov     rcx, rbx; Irp
0x140003117  call    cs:__imp_IofCompleteRequest
0x14000311e  nop     dword ptr [rax+rax+00h]
0x140003123  mov     rbx, [rsp+28h+arg_0]
0x140003128  add     rsp, 20h
0x14000312c  pop     rdi
0x14000312d  retn
0x14000312f  mov     eax, [rbx+10h]
0x140003132  test    al, 40h
0x140003134  jz      short loc_14000310F
0x140003136  mov     qword ptr [rbx+38h], 0
0x14000313e  jmp     short loc_14000310F
```
