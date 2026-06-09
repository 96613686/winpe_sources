# CMulticastServer::ReadParameters(void)

- ea: `0x180005e28`
- end: `0x180005f12`
- name: `?ReadParameters@CMulticastServer@@AEAAKXZ`
- size: `234`
- prototype: `unsigned int __fastcall(CMulticastServer *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800053a0`
- `0x180008650`

## callees

- `0x180001110`
- `0x180005e28`
- `0x180008dcc`
- `0x180018174`
- `0x180024b0c`
- `0x180024dec`
- `0x180025850`

## pseudocode

```c
__int64 __fastcall CMulticastServer::ReadParameters(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned int updated; // ebx
  const char *v3; // rdx
  const char *v4; // rdx
  int v5; // eax
  int DebugInfo; // ecx
  CMRSWLock *v8; // [rsp+30h] [rbp-18h] BYREF
  int v9; // [rsp+38h] [rbp-10h]

  v9 = 0;
  v8 = (CMRSWLock *)this;
  CAutoWriterLock::Lock((LPCRITICAL_SECTION *)&v8);
  updated = CMulticastProfile::Initialize((CMulticastProfile *)&this[8]);
  if ( !ElValidateWin32(updated, v3, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x1D7u) )
  {
    updated = CBandwidthManager::UpdateSettings(this + 14);
    ElValidateWin32(updated, v4, "base\\eco\\wds\\transport\\server\\mc\\mcserver.cpp", 0x1DEu);
  }
  v5 = updated != 0;
  HIDWORD(this[7].DebugInfo) = v5;
  DebugInfo = (int)this[7].DebugInfo;
  if ( DebugInfo != v5 )
  {
    if ( DebugInfo || !updated )
    {
      LODWORD(this[7].DebugInfo) = v5;
      CEventLog::Log((CEventLog *)&hEventLog, 0x41210200u, 0);
    }
    else
    {
      LODWORD(this[7].DebugInfo) = v5;
      CEventLog::Log((CEventLog *)&hEventLog, 0xC1210201, 1, 5, updated);
    }
  }
  if ( v9 == 1 )
    CMRSWLock::WriterRelease(v8);
  return updated;
}

```

## disassembly

```asm
0x180005e28  mov     rax, rsp
0x180005e2b  mov     [rax+8], rbx
0x180005e2f  push    rdi
0x180005e30  sub     rsp, 40h
0x180005e34  and     dword ptr [rax-10h], 0
0x180005e38  mov     rdi, rcx
0x180005e3b  mov     [rax-18h], rcx
0x180005e3f  lea     rcx, [rax-18h]; this
0x180005e43  call    ?Lock@CAutoWriterLock@@QEAAXXZ; CAutoWriterLock::Lock(void)
0x180005e48  lea     rcx, [rdi+140h]; this
0x180005e4f  call    ?Initialize@CMulticastProfile@@QEAAKXZ; CMulticastProfile::Initialize(void)
0x180005e54  mov     r9d, 1D7h; unsigned int
0x180005e5a  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005e61  mov     ecx, eax; unsigned int
0x180005e63  mov     ebx, eax
0x180005e65  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005e6a  test    eax, eax
0x180005e6c  jnz     short loc_180005E90
0x180005e6e  lea     rcx, [rdi+230h]; lpCriticalSection
0x180005e75  call    ?UpdateSettings@CBandwidthManager@@QEAAKXZ; CBandwidthManager::UpdateSettings(void)
0x180005e7a  mov     r9d, 1DEh; unsigned int
0x180005e80  lea     r8, aBaseEcoWdsTran_11; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180005e87  mov     ecx, eax; unsigned int
0x180005e89  mov     ebx, eax
0x180005e8b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180005e90  xor     eax, eax
0x180005e92  test    ebx, ebx
0x180005e94  setnz   al
0x180005e97  mov     [rdi+11Ch], eax
0x180005e9d  mov     ecx, [rdi+118h]
0x180005ea3  cmp     ecx, eax
0x180005ea5  jz      short loc_180005EEE
0x180005ea7  test    ecx, ecx
0x180005ea9  jnz     short loc_180005ED4
0x180005eab  test    ebx, ebx
0x180005ead  jz      short loc_180005ED4
0x180005eaf  lea     r9d, [rcx+5]
0x180005eb3  mov     [rdi+118h], eax
0x180005eb9  lea     r8d, [rcx+1]; int
0x180005ebd  mov     [rsp+48h+var_28], ebx
0x180005ec1  lea     rcx, hEventLog; this
0x180005ec8  mov     edx, 0C1210201h; unsigned int
0x180005ecd  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180005ed2  jmp     short loc_180005EEE
0x180005ed4  xor     r8d, r8d; int
0x180005ed7  mov     [rdi+118h], eax
0x180005edd  mov     edx, 41210200h; unsigned int
0x180005ee2  lea     rcx, hEventLog; this
0x180005ee9  call    ?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180005eee  mov     eax, [rsp+48h+var_10]
0x180005ef2  test    eax, eax
0x180005ef4  jz      short loc_180005F05
0x180005ef6  cmp     eax, 1
0x180005ef9  jnz     short loc_180005F05
0x180005efb  mov     rcx, [rsp+48h+var_18]; this
0x180005f00  call    ?WriterRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::WriterRelease(void)
0x180005f05  mov     eax, ebx
0x180005f07  mov     rbx, [rsp+48h+arg_0]
0x180005f0c  add     rsp, 40h
0x180005f10  pop     rdi
0x180005f11  retn
```
