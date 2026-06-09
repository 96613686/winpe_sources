# CPxeProviderHandler::UpdateSettings(void)

- ea: `0x180006f24`
- end: `0x180007051`
- name: `?UpdateSettings@CPxeProviderHandler@@QEAAKXZ`
- size: `301`
- prototype: `unsigned int __fastcall(CPxeProviderHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180003050`
- `0x1800069c4`

## callees

- `0x180006f24`

## import_xrefs

- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006fb2`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006ffd`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180007023`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006fb2`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180006ffd`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180007023`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180006f40`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180006f40`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180007032`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x180007032`
- `WdsCommonLib!?Initialize@CBannedDeviceIds@@QEAAKPEBGPEAUHKEY__@@00@Z` at `0x180006f6f`
- `WdsCommonLib!?Initialize@CBannedDeviceIds@@QEAAKPEBGPEAUHKEY__@@00@Z` at `0x180006f6f`

## string_xrefs

- `0x180006f61`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::UpdateSettings(CPxeProviderHandler *this)
{
  CMRSWLock *v1; // rsi
  unsigned int v3; // edi
  int v4; // eax
  int v5; // eax
  int v6; // edx
  __int64 v8; // [rsp+20h] [rbp-18h]

  v1 = (CPxeProviderHandler *)((char *)this + 200);
  CMRSWLock::ReaderLock((CPxeProviderHandler *)((char *)this + 200));
  v3 = CBannedDeviceIds::Initialize(
         (CPxeProviderHandler *)((char *)this + 136),
         0,
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE",
         L"BannedGuids");
  if ( v3 )
  {
    v4 = *((_DWORD *)this + 80);
    if ( v4 != 1 )
    {
      *((_DWORD *)this + 80) = 1;
      if ( !v4 )
      {
        LODWORD(v8) = v3;
        CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070200, 1, 5, v8);
      }
    }
  }
  v5 = v3 != 0;
  *((_DWORD *)this + 81) = v5;
  v6 = *((_DWORD *)this + 82);
  if ( v6 != v5 )
  {
    if ( v6 || !v3 )
    {
      *((_DWORD *)this + 82) = v5;
      CEventLog::Log((CEventLog *)qword_18001CC40, 0x41070202u, 0, 0);
    }
    else
    {
      *((_DWORD *)this + 82) = v5;
      CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070201, 1);
    }
  }
  CMRSWLock::ReaderRelease(v1);
  return v3;
}

```

## disassembly

```asm
0x180006f24  mov     [rsp+arg_0], rbx
0x180006f29  mov     [rsp+arg_8], rsi
0x180006f2e  push    rdi
0x180006f2f  sub     rsp, 30h
0x180006f33  lea     rsi, [rcx+0C8h]
0x180006f3a  mov     rbx, rcx
0x180006f3d  mov     rcx, rsi
0x180006f40  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180006f47  nop     dword ptr [rax+rax+00h]
0x180006f4c  lea     rax, aBannedguids; "BannedGuids"
0x180006f53  xor     edx, edx
0x180006f55  lea     rcx, [rbx+88h]
0x180006f5c  mov     [rsp+38h+var_18], rax
0x180006f61  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x180006f68  mov     r8, 0FFFFFFFF80000002h
0x180006f6f  call    cs:__imp_?Initialize@CBannedDeviceIds@@QEAAKPEBGPEAUHKEY__@@00@Z; CBannedDeviceIds::Initialize(ushort const *,HKEY__ *,ushort const *,ushort const *)
0x180006f76  nop     dword ptr [rax+rax+00h]
0x180006f7b  mov     edi, eax
0x180006f7d  test    eax, eax
0x180006f7f  jz      short loc_180006FBE
0x180006f81  mov     eax, [rbx+140h]
0x180006f87  cmp     eax, 1
0x180006f8a  jz      short loc_180006FBE
0x180006f8c  mov     dword ptr [rbx+140h], 1
0x180006f96  test    eax, eax
0x180006f98  jnz     short loc_180006FBE
0x180006f9a  mov     edx, 0C1070200h
0x180006f9f  mov     dword ptr [rsp+38h+var_18], edi
0x180006fa3  lea     r9d, [rax+5]
0x180006fa7  lea     r8d, [rax+1]
0x180006fab  lea     rcx, qword_18001CC40
0x180006fb2  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180006fb9  nop     dword ptr [rax+rax+00h]
0x180006fbe  xor     eax, eax
0x180006fc0  test    edi, edi
0x180006fc2  setnz   al
0x180006fc5  mov     [rbx+144h], eax
0x180006fcb  mov     edx, [rbx+148h]
0x180006fd1  cmp     edx, eax
0x180006fd3  jz      short loc_18000702F
0x180006fd5  test    edx, edx
0x180006fd7  jnz     short loc_18000700B
0x180006fd9  test    edi, edi
0x180006fdb  jz      short loc_18000700B
0x180006fdd  mov     r9d, 5
0x180006fe3  mov     [rbx+148h], eax
0x180006fe9  mov     edx, 0C1070201h
0x180006fee  mov     dword ptr [rsp+38h+var_18], edi
0x180006ff2  lea     rcx, qword_18001CC40
0x180006ff9  lea     r8d, [r9-4]
0x180006ffd  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180007004  nop     dword ptr [rax+rax+00h]
0x180007009  jmp     short loc_18000702F
0x18000700b  xor     r9d, r9d
0x18000700e  mov     [rbx+148h], eax
0x180007014  xor     r8d, r8d
0x180007017  lea     rcx, qword_18001CC40
0x18000701e  mov     edx, 41070202h
0x180007023  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000702a  nop     dword ptr [rax+rax+00h]
0x18000702f  mov     rcx, rsi
0x180007032  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180007039  nop     dword ptr [rax+rax+00h]
0x18000703e  mov     rbx, [rsp+38h+arg_0]
0x180007043  mov     eax, edi
0x180007045  mov     rsi, [rsp+38h+arg_8]
0x18000704a  add     rsp, 30h
0x18000704e  pop     rdi
0x18000704f  retn
```
