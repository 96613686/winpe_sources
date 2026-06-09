# CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::Get(long,ushort * *)

- ea: `0x18000aee0`
- end: `0x18000af2e`
- name: `?Get@?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@UEAAJJPEAPEAG@Z`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000aee0`
- `0x18000f46c`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::Get(
        __int64 a1,
        unsigned int a2,
        BSTR *a3)
{
  int v6; // ebx
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 2;
  v6 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( v6 >= 0 )
    v6 = CWerComReportStringList<&long WerComListConstCountFunc<11>(void *,unsigned long *),&long WerpGetUIParamByIndex(void *,unsigned long,unsigned short const * *)>::_Get(
           a1 - 24,
           a2,
           a3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000aee0  push    rbx
0x18000aee2  push    rbp
0x18000aee3  push    rsi
0x18000aee4  push    rdi
0x18000aee5  sub     rsp, 28h
0x18000aee9  mov     rbp, rcx
0x18000aeec  mov     [rsp+48h+arg_18], 2
0x18000aef4  lea     rcx, [rsp+48h+arg_18]; this
0x18000aef9  mov     rdi, r8
0x18000aefc  mov     esi, edx
0x18000aefe  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000af03  mov     ebx, eax
0x18000af05  test    eax, eax
0x18000af07  js      short loc_18000AF19
0x18000af09  lea     rcx, [rbp-18h]
0x18000af0d  mov     r8, rdi
0x18000af10  mov     edx, esi
0x18000af12  call    ?_Get@?$CWerComReportStringList@$1??$WerComListConstCountFunc@$0L@@@YAJPEAXPEAK@Z$1?WerpGetUIParamByIndex@@YAJ0KPEAPEBG@Z@@QEAAJJPEAPEAG@Z; CWerComReportStringList<&WerComListConstCountFunc<11>(void *,ulong *),&WerpGetUIParamByIndex(void *,ulong,ushort const * *)>::_Get(long,ushort * *)
0x18000af17  mov     ebx, eax
0x18000af19  lea     rcx, [rsp+48h+arg_18]; this
0x18000af1e  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000af23  mov     eax, ebx
0x18000af25  add     rsp, 28h
0x18000af29  pop     rdi
0x18000af2a  pop     rsi
0x18000af2b  pop     rbp
0x18000af2c  pop     rbx
0x18000af2d  retn
```
