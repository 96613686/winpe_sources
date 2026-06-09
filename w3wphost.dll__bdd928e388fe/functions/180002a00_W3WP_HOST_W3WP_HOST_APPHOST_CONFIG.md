# W3WP_HOST::W3WP_HOST(APPHOST_CONFIG *)

- ea: `0x180002a00`
- end: `0x180002bab`
- name: `??0W3WP_HOST@@QEAA@PEAUAPPHOST_CONFIG@@@Z`
- size: `427`
- prototype: `W3WP_HOST *__fastcall(W3WP_HOST *__hidden this, struct APPHOST_CONFIG *)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003340`
- `0x180004750`

## import_xrefs

- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002a93`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002a93`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002ab3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002ab3`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002aea`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002b19`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002aea`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002b19`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002b43`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002b5a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002b43`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002b5a`

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
0x180002a00  push    rbx
0x180002a02  push    rbp
0x180002a03  push    rsi
0x180002a04  push    rdi
0x180002a05  sub     rsp, 28h
0x180002a09  mov     rdi, rdx
0x180002a0c  mov     dword ptr [rcx+4Ch], 1
0x180002a13  lea     rax, ??_7W3WP_HOST@@6BIWorkerProcessFramework@@@; const W3WP_HOST::`vftable'{for `IWorkerProcessFramework'}
0x180002a1a  mov     rsi, rcx
0x180002a1d  mov     [rcx], rax
0x180002a20  lea     rdx, aHostablewebcor; "HostableWebCore"
0x180002a27  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationInfoUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationInfoUtil'}
0x180002a2e  xor     ebp, ebp
0x180002a30  mov     [rcx+8], rax
0x180002a34  test    rdi, rdi
0x180002a37  lea     rax, ??_7W3WP_HOST@@6BIWpfSettings@@@; const W3WP_HOST::`vftable'{for `IWpfSettings'}
0x180002a3e  mov     [rcx+10h], rax
0x180002a42  lea     rax, ??_7W3WP_HOST@@6BIWpfActions@@@; const W3WP_HOST::`vftable'{for `IWpfActions'}
0x180002a49  mov     [rcx+18h], rax
0x180002a4d  lea     rax, ??_7W3WP_HOST@@6BIWpfExposeProtocolManagerCustomInterface@@@; const W3WP_HOST::`vftable'{for `IWpfExposeProtocolManagerCustomInterface'}
0x180002a54  mov     [rcx+20h], rax
0x180002a58  lea     rax, ??_7W3WP_HOST@@6BIIisCoreReportCounters@@@; const W3WP_HOST::`vftable'{for `IIisCoreReportCounters'}
0x180002a5f  mov     [rcx+28h], rax
0x180002a63  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceCountersManager@@@; const W3WP_HOST::`vftable'{for `IWPInstanceCountersManager'}
0x180002a6a  mov     [rcx+30h], rax
0x180002a6e  lea     rax, ??_7W3WP_HOST@@6BIWpfApplicationPreloadUtil@@@; const W3WP_HOST::`vftable'{for `IWpfApplicationPreloadUtil'}
0x180002a75  mov     [rcx+38h], rax
0x180002a79  lea     rax, ??_7W3WP_HOST@@6BIWPInstanceSendData@@@; const W3WP_HOST::`vftable'{for `IWPInstanceSendData'}
0x180002a80  mov     [rcx+40h], rax
0x180002a84  lea     rax, aW3svcWp; "W3SVC-WP"
0x180002a8b  cmovnz  rdx, rax
0x180002a8f  add     rcx, 50h ; 'P'
0x180002a93  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180002a99  lea     rcx, [rsi+80h]
0x180002aa0  mov     [rsi+58h], rbp
0x180002aa4  mov     [rsi+60h], rbp
0x180002aa8  mov     [rsi+68h], rbp
0x180002aac  mov     [rsi+70h], rbp
0x180002ab0  mov     [rsi+78h], ebp
0x180002ab3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002ab9  lea     rbx, [rsi+140h]
0x180002ac0  mov     [rsi+0B8h], ebp
0x180002ac6  mov     rcx, rbx
0x180002ac9  mov     [rsi+0C0h], rbp
0x180002ad0  mov     [rsi+0C8h], ebp
0x180002ad6  mov     [rsi+0F8h], ebp
0x180002adc  mov     [rsi+128h], rbp
0x180002ae3  mov     [rsi+130h], rbp
0x180002aea  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002af0  lea     rax, [rbx+8]
0x180002af4  mov     [rax+8], rax
0x180002af8  lea     rbx, [rsi+170h]
0x180002aff  mov     [rax], rax
0x180002b02  mov     rcx, rbx
0x180002b05  mov     [rsi+158h], rbp
0x180002b0c  mov     [rsi+160h], rbp
0x180002b13  mov     [rsi+168h], ebp
0x180002b19  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002b1f  lea     rax, [rbx+8]
0x180002b23  mov     [rbx+18h], ebp
0x180002b26  mov     ebx, 104h
0x180002b2b  mov     [rax+8], rax
0x180002b2f  mov     r8d, ebx
0x180002b32  mov     [rax], rax
0x180002b35  lea     rdx, [rsi+1C8h]
0x180002b3c  lea     rcx, [rsi+190h]
0x180002b43  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002b49  lea     rdx, [rsi+408h]
0x180002b50  mov     r8d, ebx
0x180002b53  lea     rcx, [rsi+3D0h]
0x180002b5a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002b60  mov     [rsi+610h], rbp
0x180002b67  mov     rax, rsi
0x180002b6a  mov     [rsi+618h], rbp
0x180002b71  mov     [rsi+620h], rbp
0x180002b78  mov     [rsi+628h], rbp
0x180002b7f  mov     [rsi+630h], rbp
0x180002b86  mov     [rsi+638h], rbp
0x180002b8d  mov     [rsi+640h], rbp
0x180002b94  mov     [rsi+138h], rdi
0x180002b9b  mov     dword ptr [rsi+48h], 54483357h
0x180002ba2  add     rsp, 28h
0x180002ba6  pop     rdi
0x180002ba7  pop     rsi
0x180002ba8  pop     rbp
0x180002ba9  pop     rbx
0x180002baa  retn
```
