# IsFidoDWFrontEndSession(void)

- ea: `0x100435ef0`
- end: `0x100435fc6`
- name: `?IsFidoDWFrontEndSession@@YA_NXZ`
- size: `214`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x100435fd0`
- `0x1004361a0`

## callees

- `0x100435ef0`

## import_xrefs

- `sqlmin!GetXdbServerGlobals` at `0x100435ef4`
- `sqlmin!GetXdbServerGlobals` at `0x100435ef4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100435f60`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100435f60`
- `sqldk!SystemThread_TlsOffset` at `0x100435f39`
- `sqldk!SystemThread_TlsOffset` at `0x100435f73`
- `sqldk!SystemThread_TlsIndex` at `0x100435f30`
- `sqldk!SystemThread_TlsIndex` at `0x100435f6a`

## pseudocode

```c
bool __fastcall IsFidoDWFrontEndSession(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  struct CSessionTraceFlags *v3; // rcx

  return *(_BYTE *)(GetXdbServerGlobals(a1, a2) + 12004)
      && (*((_DWORD *)qword_10049F360 + 3626)
       || *(char *)(qword_10049F340 + 1533) < 0
       || (v2 = *(_QWORD *)(SystemThread_TlsOffset
                          + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))) != 0
       && (v3 = **(struct CSessionTraceFlags ***)(v2 + 56)) != 0
       && CSessionTraceFlags::CheckSessionTraceInternal(v3, 0x2FEFu))
      && *(_QWORD *)(SystemThread_TlsOffset
                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))
      && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + SystemThread_TlsIndex)
                                           + SystemThread_TlsOffset)
                               + 72LL)
                   + 270LL)
        & 8) != 0;
}

```

## disassembly

```asm
0x100435ef0  sub     rsp, 28h
0x100435ef4  call    cs:__imp_GetXdbServerGlobals
0x100435efa  cmp     byte ptr [rax+2EE4h], 0
0x100435f01  jz      loc_100435FBF
0x100435f07  mov     rax, cs:qword_10049F360
0x100435f0e  cmp     dword ptr [rax+38A8h], 0
0x100435f15  jnz     short loc_100435F6A
0x100435f17  mov     rax, cs:qword_10049F340
0x100435f1e  cmp     byte ptr [rax+5FDh], 0
0x100435f25  jl      short loc_100435F6A
0x100435f27  mov     r8, gs:58h
0x100435f30  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100435f37  mov     edx, [rax]
0x100435f39  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100435f40  mov     ecx, [rax]
0x100435f42  mov     rax, [r8+rdx*8]
0x100435f46  mov     rax, [rcx+rax]
0x100435f4a  test    rax, rax
0x100435f4d  jz      short loc_100435FBF
0x100435f4f  mov     rax, [rax+38h]
0x100435f53  mov     rcx, [rax]
0x100435f56  test    rcx, rcx
0x100435f59  jz      short loc_100435FBF
0x100435f5b  mov     edx, 2FEFh
0x100435f60  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100435f66  test    eax, eax
0x100435f68  jz      short loc_100435FBF
0x100435f6a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100435f71  mov     ecx, [rax]
0x100435f73  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100435f7a  lea     rdx, ds:0[rcx*8]
0x100435f82  mov     r8d, [rax]
0x100435f85  mov     rax, gs:58h
0x100435f8e  mov     rcx, [rax+rdx]
0x100435f92  cmp     qword ptr [r8+rcx], 0
0x100435f97  jz      short loc_100435FBF
0x100435f99  mov     rax, gs:58h
0x100435fa2  mov     rcx, [rax+rdx]
0x100435fa6  mov     rax, [rcx+r8]
0x100435faa  mov     rcx, [rax+48h]
0x100435fae  movzx   eax, byte ptr [rcx+10Eh]
0x100435fb5  shr     al, 3
0x100435fb8  and     al, 1
0x100435fba  add     rsp, 28h
0x100435fbe  retn
0x100435fbf  xor     al, al
0x100435fc1  add     rsp, 28h
0x100435fc5  retn
```
