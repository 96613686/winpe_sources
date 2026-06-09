# WMCommListGet

- ea: `0x14000b938`
- end: `0x14000b9b4`
- name: `WMCommListGet`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009aa0`
- `0x14000a994`

## callees

- `0x140002a78`
- `0x140002a94`
- `0x14000b8b0`
- `0x14000b938`

## import_xrefs

- `FLTMGR!FltReleaseResource` at `0x14000b99a`
- `FLTMGR!FltReleaseResource` at `0x14000b99a`
- `FLTMGR!FltAcquireResourceShared` at `0x14000b94f`
- `FLTMGR!FltAcquireResourceShared` at `0x14000b94f`

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
0x14000b938  mov     [rsp+arg_0], rbx
0x14000b93d  push    rdi
0x14000b93e  sub     rsp, 20h
0x14000b942  mov     rbx, rcx
0x14000b945  mov     rdi, rdx
0x14000b948  lea     rcx, stru_1400061E0; Resource
0x14000b94f  call    cs:__imp_FltAcquireResourceShared
0x14000b956  nop     dword ptr [rax+rax+00h]
0x14000b95b  mov     rdx, rbx
0x14000b95e  lea     rcx, MatchByGuid
0x14000b965  call    PriGetEntry
0x14000b96a  mov     rcx, rax
0x14000b96d  test    rax, rax
0x14000b970  jnz     short loc_14000B979
0x14000b972  mov     ebx, 0C0000225h
0x14000b977  jmp     short loc_14000B993
0x14000b979  call    WMCommListEntryAddRef
0x14000b97e  test    al, al
0x14000b980  jz      short loc_14000B989
0x14000b982  xor     ebx, ebx
0x14000b984  mov     [rdi], rcx
0x14000b987  jmp     short loc_14000B993
0x14000b989  call    WMCommListEntryRelease
0x14000b98e  mov     ebx, 0C0000095h
0x14000b993  lea     rcx, stru_1400061E0; Resource
0x14000b99a  call    cs:__imp_FltReleaseResource
0x14000b9a1  nop     dword ptr [rax+rax+00h]
0x14000b9a6  mov     eax, ebx
0x14000b9a8  mov     rbx, [rsp+28h+arg_0]
0x14000b9ad  add     rsp, 20h
0x14000b9b1  pop     rdi
0x14000b9b2  retn
```
