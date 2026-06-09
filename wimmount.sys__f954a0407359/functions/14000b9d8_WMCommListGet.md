# WMCommListGet

- ea: `0x14000b9d8`
- end: `0x14000ba54`
- name: `WMCommListGet`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009aa0`
- `0x14000aa34`

## callees

- `0x140002a78`
- `0x140002a94`
- `0x14000b950`
- `0x14000b9d8`

## import_xrefs

- `FLTMGR!FltReleaseResource` at `0x14000ba3a`
- `FLTMGR!FltReleaseResource` at `0x14000ba3a`
- `FLTMGR!FltAcquireResourceShared` at `0x14000b9ef`
- `FLTMGR!FltAcquireResourceShared` at `0x14000b9ef`

## pseudocode

```c
__int64 __fastcall WMCommListGet(__int64 a1, _QWORD *a2)
{
  __int64 Entry; // rcx
  unsigned int v5; // ebx
  void *v6; // rcx

  FltAcquireResourceShared(&stru_1400061E0);
  Entry = PriGetEntry(MatchByGuid, a1);
  if ( Entry )
  {
    if ( (unsigned __int8)WMCommListEntryAddRef(Entry) )
    {
      v5 = 0;
      *a2 = v6;
    }
    else
    {
      WMCommListEntryRelease(v6);
      v5 = -1073741675;
    }
  }
  else
  {
    v5 = -1073741275;
  }
  FltReleaseResource(&stru_1400061E0);
  return v5;
}

```

## disassembly

```asm
0x14000b9d8  mov     [rsp+arg_0], rbx
0x14000b9dd  push    rdi
0x14000b9de  sub     rsp, 20h
0x14000b9e2  mov     rbx, rcx
0x14000b9e5  mov     rdi, rdx
0x14000b9e8  lea     rcx, stru_1400061E0; Resource
0x14000b9ef  call    cs:__imp_FltAcquireResourceShared
0x14000b9f6  nop     dword ptr [rax+rax+00h]
0x14000b9fb  mov     rdx, rbx
0x14000b9fe  lea     rcx, MatchByGuid
0x14000ba05  call    PriGetEntry
0x14000ba0a  mov     rcx, rax
0x14000ba0d  test    rax, rax
0x14000ba10  jnz     short loc_14000BA19
0x14000ba12  mov     ebx, 0C0000225h
0x14000ba17  jmp     short loc_14000BA33
0x14000ba19  call    WMCommListEntryAddRef
0x14000ba1e  test    al, al
0x14000ba20  jz      short loc_14000BA29
0x14000ba22  xor     ebx, ebx
0x14000ba24  mov     [rdi], rcx
0x14000ba27  jmp     short loc_14000BA33
0x14000ba29  call    WMCommListEntryRelease
0x14000ba2e  mov     ebx, 0C0000095h
0x14000ba33  lea     rcx, stru_1400061E0; Resource
0x14000ba3a  call    cs:__imp_FltReleaseResource
0x14000ba41  nop     dword ptr [rax+rax+00h]
0x14000ba46  mov     eax, ebx
0x14000ba48  mov     rbx, [rsp+28h+arg_0]
0x14000ba4d  add     rsp, 20h
0x14000ba51  pop     rdi
0x14000ba52  retn
```
