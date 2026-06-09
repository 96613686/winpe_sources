# HandlePeerPollingThreadPeerListUpdated(void *,uchar)

- ea: `0x1800164f0`
- end: `0x180016591`
- name: `?HandlePeerPollingThreadPeerListUpdated@@YAXPEAXE@Z`
- size: `161`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800164f0`
- `0x1800165a0`
- `0x180016960`
- `0x180017240`
- `0x180018138`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180016570`
- `ntdll!RtlReleaseResource` at `0x180016570`
- `ntdll!RtlAcquireResourceShared` at `0x180016533`
- `ntdll!RtlAcquireResourceShared` at `0x180016533`

## string_xrefs

- `0x180016580`: `PeerPollingThread: PeerListUpdated\n`

## pseudocode

```c
void __fastcall HandlePeerPollingThreadPeerListUpdated(void *a1)
{
  char v1; // bl
  __int64 i; // rdx

  if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
    && _pflstate
    && *((_BYTE *)_pflstate + 315)
    && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
  {
    v1 = 0;
    for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x33u; i = *(_QWORD *)(i + 8) )
    {
      if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x33 )
      {
        v1 = 1;
        break;
      }
    }
    RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
    if ( v1 )
      FileLogAdd(L"PeerPollingThread: PeerListUpdated\n");
  }
  UpdatePeerListTimes();
  UpdatePeerPollingThreadTimerQueue2();
  UpdatePeerPollingThreadTimerQueue1();
}

```

## disassembly

```asm
0x1800164f0  push    rbx
0x1800164f2  sub     rsp, 20h
0x1800164f6  xor     ecx, ecx
0x1800164f8  xor     eax, eax
0x1800164fa  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x180016502  jnz     short loc_180016518
0x180016504  call    ?UpdatePeerListTimes@@YAXXZ; UpdatePeerListTimes(void)
0x180016509  call    ?UpdatePeerPollingThreadTimerQueue2@@YAJXZ; UpdatePeerPollingThreadTimerQueue2(void)
0x18001650e  add     rsp, 20h
0x180016512  pop     rbx
0x180016513  jmp     ?UpdatePeerPollingThreadTimerQueue1@@YAJXZ; UpdatePeerPollingThreadTimerQueue1(void)
0x180016518  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18001651f  test    rcx, rcx
0x180016522  jz      short loc_180016504
0x180016524  cmp     byte ptr [rcx+13Bh], 0
0x18001652b  jz      short loc_180016504
0x18001652d  add     rcx, 50h ; 'P'; Resource
0x180016531  mov     dl, 1; Wait
0x180016533  call    cs:__imp_RtlAcquireResourceShared
0x18001653a  nop     dword ptr [rax+rax+00h]
0x18001653f  test    al, al
0x180016541  jz      short loc_180016504
0x180016543  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x18001654a  xor     bl, bl
0x18001654c  mov     rdx, [r8+18h]
0x180016550  test    rdx, rdx
0x180016553  jz      short loc_18001656C
0x180016555  mov     ecx, [rdx]
0x180016557  cmp     ecx, 33h ; '3'
0x18001655a  ja      short loc_18001656C
0x18001655c  add     ecx, [rdx+4]
0x18001655f  cmp     ecx, 33h ; '3'
0x180016562  ja      short loc_18001656A
0x180016564  mov     rdx, [rdx+8]
0x180016568  jmp     short loc_180016550
0x18001656a  mov     bl, 1
0x18001656c  lea     rcx, [r8+50h]; Resource
0x180016570  call    cs:__imp_RtlReleaseResource
0x180016577  nop     dword ptr [rax+rax+00h]
0x18001657c  test    bl, bl
0x18001657e  jz      short loc_180016504
0x180016580  lea     rcx, aPeerpollingthr_3; "PeerPollingThread: PeerListUpdated\n"
0x180016587  call    FileLogAdd
0x18001658c  jmp     loc_180016504
```
