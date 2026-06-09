# CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::get_Count(long *)

- ea: `0x180011180`
- end: `0x1800111c4`
- name: `?get_Count@?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@UEAAJPEAJ@Z`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x180011180`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::get_Count(
        __int64 a1,
        _DWORD *a2)
{
  int v3; // ebx
  int v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 2;
  v3 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v5);
  if ( v3 >= 0 )
  {
    *a2 = 54;
    v3 = 0;
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011180  mov     [rsp+arg_0], rbx
0x180011185  push    rdi
0x180011186  sub     rsp, 20h
0x18001118a  lea     rcx, [rsp+28h+arg_10]; this
0x18001118f  mov     [rsp+28h+arg_10], 2
0x180011197  mov     rdi, rdx
0x18001119a  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18001119f  lea     rcx, [rsp+28h+arg_10]; this
0x1800111a4  mov     ebx, eax
0x1800111a6  test    eax, eax
0x1800111a8  js      short loc_1800111B2
0x1800111aa  mov     dword ptr [rdi], 36h ; '6'
0x1800111b0  xor     ebx, ebx
0x1800111b2  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x1800111b7  mov     eax, ebx
0x1800111b9  mov     rbx, [rsp+28h+arg_0]
0x1800111be  add     rsp, 20h
0x1800111c2  pop     rdi
0x1800111c3  retn
```
