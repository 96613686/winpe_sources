# WcPostDismountVolume

- ea: `0x14002f474`
- end: `0x14002f580`
- name: `WcPostDismountVolume`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a110`

## callees

- `0x14002f474`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002f530`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002f530`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f4be`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f4f0`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f4be`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002f4f0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002f55d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002f55d`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14002f505`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14002f505`
- `FLTMGR!FltReleaseResource` at `0x14002f54a`
- `FLTMGR!FltReleaseResource` at `0x14002f54a`
- `FLTMGR!FltReleaseContext` at `0x14002f56e`
- `FLTMGR!FltReleaseContext` at `0x14002f56e`
- `FLTMGR!FltGetInstanceContext` at `0x14002f497`
- `FLTMGR!FltGetInstanceContext` at `0x14002f497`

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
0x14002f474  sub     rsp, 28h
0x14002f478  cmp     dword ptr [rcx+18h], 0
0x14002f47c  mov     rax, rdx
0x14002f47f  mov     [rsp+28h+Context], 0
0x14002f488  jl      loc_14002F57A
0x14002f48e  mov     rcx, [rax+18h]; Instance
0x14002f492  lea     rdx, [rsp+28h+Context]; Context
0x14002f497  call    cs:__imp_FltGetInstanceContext
0x14002f49e  nop     dword ptr [rax+rax+00h]
0x14002f4a3  test    eax, eax
0x14002f4a5  js      loc_14002F57A
0x14002f4ab  mov     rcx, [rsp+28h+Context]
0x14002f4b0  cmp     qword ptr [rcx+38h], 0
0x14002f4b5  jz      short loc_14002F4DF
0x14002f4b7  lea     rcx, FastMutex; FastMutex
0x14002f4be  call    cs:__imp_ExAcquireFastMutex
0x14002f4c5  nop     dword ptr [rax+rax+00h]
0x14002f4ca  mov     rax, [rsp+28h+Context]
0x14002f4cf  dec     cs:dword_14000E244
0x14002f4d5  mov     rdx, [rax+38h]
0x14002f4d9  and     dword ptr [rdx+20h], 0FFFFFFFEh
0x14002f4dd  jmp     short loc_14002F556
0x14002f4df  cmp     dword ptr [rcx+40h], 0
0x14002f4e3  jbe     loc_14002F56E
0x14002f4e9  lea     rcx, FastMutex; FastMutex
0x14002f4f0  call    cs:__imp_ExAcquireFastMutex
0x14002f4f7  nop     dword ptr [rax+rax+00h]
0x14002f4fc  mov     rcx, [rsp+28h+Context]
0x14002f501  add     rcx, 48h ; 'H'; Resource
0x14002f505  call    cs:__imp_FltAcquireResourceExclusive
0x14002f50c  nop     dword ptr [rax+rax+00h]
0x14002f511  mov     dl, 1
0x14002f513  jmp     short loc_14002F524
0x14002f515  dec     cs:dword_14000E244
0x14002f51b  mov     rax, [rax]
0x14002f51e  and     dword ptr [rax+20h], 0FFFFFFFEh
0x14002f522  xor     edx, edx; Restart
0x14002f524  mov     rcx, [rsp+28h+Context]
0x14002f529  add     rcx, 0B0h; Table
0x14002f530  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002f537  nop     dword ptr [rax+rax+00h]
0x14002f53c  test    rax, rax
0x14002f53f  jnz     short loc_14002F515
0x14002f541  mov     rcx, [rsp+28h+Context]
0x14002f546  add     rcx, 48h ; 'H'; Resource
0x14002f54a  call    cs:__imp_FltReleaseResource
0x14002f551  nop     dword ptr [rax+rax+00h]
0x14002f556  lea     rcx, FastMutex; FastMutex
0x14002f55d  call    cs:__imp_ExReleaseFastMutex
0x14002f564  nop     dword ptr [rax+rax+00h]
0x14002f569  mov     rcx, [rsp+28h+Context]; Context
0x14002f56e  call    cs:__imp_FltReleaseContext
0x14002f575  nop     dword ptr [rax+rax+00h]
0x14002f57a  add     rsp, 28h
0x14002f57e  retn
```
