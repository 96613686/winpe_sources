# W3WP_HOST::W3WP_HOST(APPHOST_CONFIG *)

- ea: `0x180002b68`
- end: `0x180002d38`
- name: `??0W3WP_HOST@@QEAA@PEAUAPPHOST_CONFIG@@@Z`
- size: `464`
- prototype: `W3WP_HOST *__fastcall(W3WP_HOST *__hidden this, struct APPHOST_CONFIG *)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003540`
- `0x180004b20`

## import_xrefs

- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002bfb`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002bfb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002c21`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002c21`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002c5e`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002c93`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002c5e`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002c93`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cc3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002ce0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002cc3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002ce0`

## pseudocode

```c
W3WP_HOST *__fastcall W3WP_HOST::W3WP_HOST(W3WP_HOST *this, struct APPHOST_CONFIG *a2)
{
  const unsigned __int16 *v4; // rdx
  W3WP_HOST *result; // rax

  *((_DWORD *)this + 19) = 1;
  *(_QWORD *)this = &W3WP_HOST::`vftable'{for `IWorkerProcessFramework'};
  v4 = L"HostableWebCore";
  *((_QWORD *)this + 1) = &W3WP_HOST::`vftable'{for `IWpfApplicationInfoUtil'};
  *((_QWORD *)this + 2) = &W3WP_HOST::`vftable'{for `IWpfSettings'};
  *((_QWORD *)this + 3) = &W3WP_HOST::`vftable'{for `IWpfActions'};
  *((_QWORD *)this + 4) = &W3WP_HOST::`vftable'{for `IWpfExposeProtocolManagerCustomInterface'};
  *((_QWORD *)this + 5) = &W3WP_HOST::`vftable'{for `IIisCoreReportCounters'};
  *((_QWORD *)this + 6) = &W3WP_HOST::`vftable'{for `IWPInstanceCountersManager'};
  *((_QWORD *)this + 7) = &W3WP_HOST::`vftable'{for `IWpfApplicationPreloadUtil'};
  *((_QWORD *)this + 8) = &W3WP_HOST::`vftable'{for `IWPInstanceSendData'};
  if ( a2 )
    v4 = L"W3SVC-WP";
  EVENT_LOG::EVENT_LOG((W3WP_HOST *)((char *)this + 80), v4);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  STRU::STRU((W3WP_HOST *)((char *)this + 128));
  *((_DWORD *)this + 46) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 50) = 0;
  *((_DWORD *)this + 62) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  CReaderWriterLock3::CReaderWriterLock3((W3WP_HOST *)((char *)this + 320));
  *((_QWORD *)this + 42) = (char *)this + 328;
  *((_QWORD *)this + 41) = (char *)this + 328;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 90) = 0;
  CReaderWriterLock3::CReaderWriterLock3((W3WP_HOST *)((char *)this + 368));
  *((_DWORD *)this + 98) = 0;
  *((_QWORD *)this + 48) = (char *)this + 376;
  *((_QWORD *)this + 47) = (char *)this + 376;
  STRU::STRU((W3WP_HOST *)((char *)this + 400), (unsigned __int16 *)this + 228, 0x104u);
  STRU::STRU((W3WP_HOST *)((char *)this + 976), (unsigned __int16 *)this + 516, 0x104u);
  *((_QWORD *)this + 194) = 0;
  result = this;
  *((_QWORD *)this + 195) = 0;
  *((_QWORD *)this + 196) = 0;
  *((_QWORD *)this + 197) = 0;
  *((_QWORD *)this + 198) = 0;
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 39) = a2;
  *((_DWORD *)this + 18) = 1414017879;
  return result;
}

```

## disassembly

```asm
0x180002b68  push    rbx
0x180002b6a  push    rbp
0x180002b6b  push    rsi
0x180002b6c  push    rdi
0x180002b6d  sub     rsp, 28h
0x180002b71  mov     rdi, rdx
0x180002b74  mov     dword ptr [rcx+4Ch], 1
0x180002b7b  lea     rax, ??_7W3WP_HOST@@6BIWorkerProcessFramework@@@; const W3WP_HOST::`vftable'{for `IWorkerProcessFramework'}
0x180002b82  mov     rsi, rcx
0x180002b85  mov     [rcx], rax
0x180002b88  lea     rdx, aHostablewebcor; "HostableWebCore"
0x180002b8f  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationInfoUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationInfoUtil'}
0x180002b96  xor     ebp, ebp
0x180002b98  mov     [rcx+8], rax
0x180002b9c  test    rdi, rdi
0x180002b9f  lea     rax, ??_7W3WP_HOST@@6BIWpfSettings@@@; const W3WP_HOST::`vftable'{for `IWpfSettings'}
0x180002ba6  mov     [rcx+10h], rax
0x180002baa  lea     rax, ??_7W3WP_HOST@@6BIWpfActions@@@; const W3WP_HOST::`vftable'{for `IWpfActions'}
0x180002bb1  mov     [rcx+18h], rax
0x180002bb5  lea     rax, ??_7W3WP_HOST@@6BIWpfExposeProtocolManagerCustomInterface@@@; const W3WP_HOST::`vftable'{for `IWpfExposeProtocolManagerCustomInterface'}
0x180002bbc  mov     [rcx+20h], rax
0x180002bc0  lea     rax, ??_7W3WP_HOST@@6BIIisCoreReportCounters@@@; const W3WP_HOST::`vftable'{for `IIisCoreReportCounters'}
0x180002bc7  mov     [rcx+28h], rax
0x180002bcb  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceCountersManager@@@; const W3WP_HOST::`vftable'{for `IWPInstanceCountersManager'}
0x180002bd2  mov     [rcx+30h], rax
0x180002bd6  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationPreloadUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationPreloadUtil'}
0x180002bdd  mov     [rcx+38h], rax
0x180002be1  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceSendData@@@; const W3WP_HOST::`vftable'{for `IWPInstanceSendData'}
0x180002be8  mov     [rcx+40h], rax
0x180002bec  lea     rax, aW3svcWp; "W3SVC-WP"
0x180002bf3  cmovnz  rdx, rax
0x180002bf7  add     rcx, 50h ; 'P'
0x180002bfb  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180002c02  nop     dword ptr [rax+rax+00h]
0x180002c07  lea     rcx, [rsi+80h]
0x180002c0e  mov     [rsi+58h], rbp
0x180002c12  mov     [rsi+60h], rbp
0x180002c16  mov     [rsi+68h], rbp
0x180002c1a  mov     [rsi+70h], rbp
0x180002c1e  mov     [rsi+78h], ebp
0x180002c21  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002c28  nop     dword ptr [rax+rax+00h]
0x180002c2d  lea     rbx, [rsi+140h]
0x180002c34  mov     [rsi+0B8h], ebp
0x180002c3a  mov     rcx, rbx
0x180002c3d  mov     [rsi+0C0h], rbp
0x180002c44  mov     [rsi+0C8h], ebp
0x180002c4a  mov     [rsi+0F8h], ebp
0x180002c50  mov     [rsi+128h], rbp
0x180002c57  mov     [rsi+130h], rbp
0x180002c5e  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002c65  nop     dword ptr [rax+rax+00h]
0x180002c6a  lea     rax, [rbx+8]
0x180002c6e  mov     [rax+8], rax
0x180002c72  lea     rbx, [rsi+170h]
0x180002c79  mov     [rax], rax
0x180002c7c  mov     rcx, rbx
0x180002c7f  mov     [rsi+158h], rbp
0x180002c86  mov     [rsi+160h], rbp
0x180002c8d  mov     [rsi+168h], ebp
0x180002c93  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002c9a  nop     dword ptr [rax+rax+00h]
0x180002c9f  lea     rax, [rbx+8]
0x180002ca3  mov     [rbx+18h], ebp
0x180002ca6  mov     ebx, 104h
0x180002cab  mov     [rax+8], rax
0x180002caf  mov     r8d, ebx
0x180002cb2  mov     [rax], rax
0x180002cb5  lea     rdx, [rsi+1C8h]
0x180002cbc  lea     rcx, [rsi+190h]
0x180002cc3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002cca  nop     dword ptr [rax+rax+00h]
0x180002ccf  lea     rdx, [rsi+408h]
0x180002cd6  mov     r8d, ebx
0x180002cd9  lea     rcx, [rsi+3D0h]
0x180002ce0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002ce7  nop     dword ptr [rax+rax+00h]
0x180002cec  mov     [rsi+610h], rbp
0x180002cf3  mov     rax, rsi
0x180002cf6  mov     [rsi+618h], rbp
0x180002cfd  mov     [rsi+620h], rbp
0x180002d04  mov     [rsi+628h], rbp
0x180002d0b  mov     [rsi+630h], rbp
0x180002d12  mov     [rsi+638h], rbp
0x180002d19  mov     [rsi+640h], rbp
0x180002d20  mov     [rsi+138h], rdi
0x180002d27  mov     dword ptr [rsi+48h], 54483357h
0x180002d2e  add     rsp, 28h
0x180002d32  pop     rdi
0x180002d33  pop     rsi
0x180002d34  pop     rbp
0x180002d35  pop     rbx
0x180002d36  retn
```
