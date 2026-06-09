# CTpSrvKickDemote::Initialize(void)

- ea: `0x18000e340`
- end: `0x18000e44c`
- name: `?Initialize@CTpSrvKickDemote@@QEAAKXZ`
- size: `268`
- prototype: `unsigned int __fastcall(CTpSrvKickDemote *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800148b4`

## callees

- `0x18000e340`
- `0x18000f068`
- `0x1800248d4`
- `0x180025850`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18000e3be`
- `KERNEL32!CreateEventW` at `0x18000e3be`
- `KERNEL32!GetLastError` at `0x18000e3d0`
- `KERNEL32!GetLastError` at `0x18000e3d0`

## pseudocode

```c
__int64 __fastcall CTpSrvKickDemote::Initialize(CTpSrvKickDemote *this)
{
  unsigned int v2; // ebx
  const char *v3; // rdx
  const char *v4; // rdx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  const char *v7; // rdx
  const char *v8; // rdx
  const char *v9; // rdx
  const char *v10; // rdx

  v2 = CTimer<CTpSrvKickDemote>::Initialize((char *)this + 5480, (__int64)this);
  if ( !ElValidateWin32(v2, v3, "base\\eco\\wds\\transport\\server\\mc\\tpsrvkickdemote.cpp", 0x42u) )
  {
    v2 = CTimer<CTpSrvKickDemote>::Initialize((char *)this + 5536, (__int64)this);
    if ( !ElValidateWin32(v2, v4, "base\\eco\\wds\\transport\\server\\mc\\tpsrvkickdemote.cpp", 0x46u) )
    {
      *((_DWORD *)this + 1930) = 0;
      *((_QWORD *)this + 964) = this;
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 967) = EventW;
      if ( EventW )
      {
        v2 = CMRSWLock::Initialize((CTpSrvKickDemote *)((char *)this + 7744));
        ElValidateWin32(v2, v9, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD9u);
      }
      else
      {
        LastError = GetLastError();
        v2 = ElValidateWin32(LastError, v7, "internal\\onecorebase\\private\\inc\\eco\\wds\\ChildCount.h", 0xD5u);
        if ( !v2 )
          v2 = 31;
      }
      ElValidateWin32(v2, v8, "internal\\onecorebase\\private\\inc\\eco\\wds\\UserWorkItemConnector.h", 0x51u);
      ElValidateWin32(v2, v10, "base\\eco\\wds\\transport\\server\\mc\\tpsrvkickdemote.cpp", 0x4Du);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000e340  mov     [rsp+arg_0], rbx
0x18000e345  push    rdi
0x18000e346  sub     rsp, 40h
0x18000e34a  mov     rdi, rcx
0x18000e34d  add     rcx, 1568h; Parameter
0x18000e354  mov     rdx, rdi
0x18000e357  call    ?Initialize@?$CTimer@VCTpSrvKickDemote@@@@QEAAKPEAVCTpSrvKickDemote@@PEAXKK1K@Z; CTimer<CTpSrvKickDemote>::Initialize(CTpSrvKickDemote *,void *,ulong,ulong,void *,ulong)
0x18000e35c  mov     r9d, 42h ; 'B'; unsigned int
0x18000e362  lea     r8, aBaseEcoWdsTran_18; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000e369  mov     ecx, eax; unsigned int
0x18000e36b  mov     ebx, eax
0x18000e36d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e372  test    eax, eax
0x18000e374  jnz     loc_18000E43F
0x18000e37a  lea     rcx, [rdi+15A0h]; Parameter
0x18000e381  mov     rdx, rdi
0x18000e384  call    ?Initialize@?$CTimer@VCTpSrvKickDemote@@@@QEAAKPEAVCTpSrvKickDemote@@PEAXKK1K@Z; CTimer<CTpSrvKickDemote>::Initialize(CTpSrvKickDemote *,void *,ulong,ulong,void *,ulong)
0x18000e389  mov     r9d, 46h ; 'F'; unsigned int
0x18000e38f  lea     r8, aBaseEcoWdsTran_18; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000e396  mov     ecx, eax; unsigned int
0x18000e398  mov     ebx, eax
0x18000e39a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e39f  test    eax, eax
0x18000e3a1  jnz     loc_18000E43F
0x18000e3a7  and     [rdi+1E28h], eax
0x18000e3ad  xor     r9d, r9d; lpName
0x18000e3b0  xor     r8d, r8d; bInitialState
0x18000e3b3  mov     [rdi+1E20h], rdi
0x18000e3ba  xor     edx, edx; bManualReset
0x18000e3bc  xor     ecx, ecx; lpEventAttributes
0x18000e3be  call    cs:__imp_CreateEventW
0x18000e3c4  mov     [rdi+1E38h], rax
0x18000e3cb  test    rax, rax
0x18000e3ce  jnz     short loc_18000E3F5
0x18000e3d0  call    cs:__imp_GetLastError
0x18000e3d6  mov     r9d, 0D5h; unsigned int
0x18000e3dc  lea     r8, aInternalOnecor; "internal\\onecorebase\\private\\inc\\ec"...
0x18000e3e3  mov     ecx, eax; unsigned int
0x18000e3e5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e3ea  mov     ebx, eax
0x18000e3ec  test    eax, eax
0x18000e3ee  jnz     short loc_18000E417
0x18000e3f0  lea     ebx, [rax+1Fh]
0x18000e3f3  jmp     short loc_18000E417
0x18000e3f5  lea     rcx, [rdi+1E40h]; this
0x18000e3fc  call    ?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x18000e401  mov     r9d, 0D9h; unsigned int
0x18000e407  lea     r8, aInternalOnecor; "internal\\onecorebase\\private\\inc\\ec"...
0x18000e40e  mov     ecx, eax; unsigned int
0x18000e410  mov     ebx, eax
0x18000e412  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e417  mov     r9d, 51h ; 'Q'; unsigned int
0x18000e41d  lea     r8, aInternalOnecor_3; "internal\\onecorebase\\private\\inc\\ec"...
0x18000e424  mov     ecx, ebx; unsigned int
0x18000e426  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e42b  mov     r9d, 4Dh ; 'M'; unsigned int
0x18000e431  lea     r8, aBaseEcoWdsTran_18; "base\\eco\\wds\\transport\\server\\mc\\"...
0x18000e438  mov     ecx, ebx; unsigned int
0x18000e43a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e43f  mov     eax, ebx
0x18000e441  mov     rbx, [rsp+48h+arg_0]
0x18000e446  add     rsp, 40h
0x18000e44a  pop     rdi
0x18000e44b  retn
```
