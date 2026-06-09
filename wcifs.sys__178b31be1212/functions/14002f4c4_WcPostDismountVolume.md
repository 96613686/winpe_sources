# WcPostDismountVolume

- ea: `0x14002f4c4`
- end: `0x14002f5d0`
- name: `WcPostDismountVolume`
- size: `268`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a110`

## callees

- `0x14002f4c4`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002f580`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002f580`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f50e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f540`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f50e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f540`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002f5ad`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002f5ad`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14002f555`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14002f555`
- `FLTMGR!FltReleaseResource` at `0x14002f59a`
- `FLTMGR!FltReleaseResource` at `0x14002f59a`
- `FLTMGR!FltReleaseContext` at `0x14002f5be`
- `FLTMGR!FltReleaseContext` at `0x14002f5be`
- `FLTMGR!FltGetInstanceContext` at `0x14002f4e7`
- `FLTMGR!FltGetInstanceContext` at `0x14002f4e7`

## pseudocode

```c
void __fastcall WcPostDismountVolume(__int64 a1, __int64 a2)
{
  bool v2; // sf
  PFLT_CONTEXT v3; // rcx
  BOOLEAN i; // dl
  PVOID v5; // rax
  PFLT_CONTEXT Context; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(int *)(a1 + 24) < 0;
  Context = 0;
  if ( !v2 && FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &Context) >= 0 )
  {
    v3 = Context;
    if ( *((_QWORD *)Context + 7) )
    {
      ExAcquireFastMutex(&FastMutex);
      --dword_14000E244;
      *(_DWORD *)(*((_QWORD *)Context + 7) + 32LL) &= ~1u;
    }
    else
    {
      if ( !*((_DWORD *)Context + 16) )
      {
LABEL_11:
        FltReleaseContext(v3);
        return;
      }
      ExAcquireFastMutex(&FastMutex);
      FltAcquireResourceExclusive((PERESOURCE)((char *)Context + 72));
      for ( i = 1; ; i = 0 )
      {
        v5 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)((char *)Context + 176), i);
        if ( !v5 )
          break;
        --dword_14000E244;
        *(_DWORD *)(*(_QWORD *)v5 + 32LL) &= ~1u;
      }
      FltReleaseResource((PERESOURCE)((char *)Context + 72));
    }
    ExReleaseFastMutex(&FastMutex);
    v3 = Context;
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x14002f4c4  sub     rsp, 28h
0x14002f4c8  cmp     dword ptr [rcx+18h], 0
0x14002f4cc  mov     rax, rdx
0x14002f4cf  mov     [rsp+28h+Context], 0
0x14002f4d8  jl      loc_14002F5CA
0x14002f4de  mov     rcx, [rax+18h]; Instance
0x14002f4e2  lea     rdx, [rsp+28h+Context]; Context
0x14002f4e7  call    cs:__imp_FltGetInstanceContext
0x14002f4ee  nop     dword ptr [rax+rax+00h]
0x14002f4f3  test    eax, eax
0x14002f4f5  js      loc_14002F5CA
0x14002f4fb  mov     rcx, [rsp+28h+Context]
0x14002f500  cmp     qword ptr [rcx+38h], 0
0x14002f505  jz      short loc_14002F52F
0x14002f507  lea     rcx, FastMutex; FastMutex
0x14002f50e  call    cs:__imp_ExAcquireFastMutex
0x14002f515  nop     dword ptr [rax+rax+00h]
0x14002f51a  mov     rax, [rsp+28h+Context]
0x14002f51f  dec     cs:dword_14000E244
0x14002f525  mov     rdx, [rax+38h]
0x14002f529  and     dword ptr [rdx+20h], 0FFFFFFFEh
0x14002f52d  jmp     short loc_14002F5A6
0x14002f52f  cmp     dword ptr [rcx+40h], 0
0x14002f533  jbe     loc_14002F5BE
0x14002f539  lea     rcx, FastMutex; FastMutex
0x14002f540  call    cs:__imp_ExAcquireFastMutex
0x14002f547  nop     dword ptr [rax+rax+00h]
0x14002f54c  mov     rcx, [rsp+28h+Context]
0x14002f551  add     rcx, 48h ; 'H'; Resource
0x14002f555  call    cs:__imp_FltAcquireResourceExclusive
0x14002f55c  nop     dword ptr [rax+rax+00h]
0x14002f561  mov     dl, 1
0x14002f563  jmp     short loc_14002F574
0x14002f565  dec     cs:dword_14000E244
0x14002f56b  mov     rax, [rax]
0x14002f56e  and     dword ptr [rax+20h], 0FFFFFFFEh
0x14002f572  xor     edx, edx; Restart
0x14002f574  mov     rcx, [rsp+28h+Context]
0x14002f579  add     rcx, 0B0h; Table
0x14002f580  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002f587  nop     dword ptr [rax+rax+00h]
0x14002f58c  test    rax, rax
0x14002f58f  jnz     short loc_14002F565
0x14002f591  mov     rcx, [rsp+28h+Context]
0x14002f596  add     rcx, 48h ; 'H'; Resource
0x14002f59a  call    cs:__imp_FltReleaseResource
0x14002f5a1  nop     dword ptr [rax+rax+00h]
0x14002f5a6  lea     rcx, FastMutex; FastMutex
0x14002f5ad  call    cs:__imp_ExReleaseFastMutex
0x14002f5b4  nop     dword ptr [rax+rax+00h]
0x14002f5b9  mov     rcx, [rsp+28h+Context]; Context
0x14002f5be  call    cs:__imp_FltReleaseContext
0x14002f5c5  nop     dword ptr [rax+rax+00h]
0x14002f5ca  add     rsp, 28h
0x14002f5ce  retn
```
