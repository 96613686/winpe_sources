# CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::Get(long,ushort * *,ushort * *)

- ea: `0x18000ae20`
- end: `0x18000ae78`
- name: `?Get@?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@UEAAJJPEAPEAG0@Z`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000ae20`
- `0x18000f25c`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::Get(
        __int64 a1,
        unsigned int a2,
        BSTR *a3,
        BSTR *a4)
{
  int v8; // ebx
  _DWORD v10[14]; // [rsp+20h] [rbp-38h] BYREF

  v10[0] = 2;
  v8 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)v10);
  if ( v8 >= 0 )
    v8 = CWerComReportKeyValueList<&long WerComListConstCountFunc<54>(void *,unsigned long *),&long WerpGetDynamicParameter(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::_Get(
           a1 - 24,
           a2,
           a3,
           a4);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ae20  push    rbx
0x18000ae22  push    rbp
0x18000ae23  push    rsi
0x18000ae24  push    rdi
0x18000ae25  push    r14
0x18000ae27  sub     rsp, 30h
0x18000ae2b  mov     r14, rcx
0x18000ae2e  mov     [rsp+58h+var_38], 2
0x18000ae36  lea     rcx, [rsp+58h+var_38]; this
0x18000ae3b  mov     rdi, r9
0x18000ae3e  mov     rsi, r8
0x18000ae41  mov     ebp, edx
0x18000ae43  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000ae48  mov     ebx, eax
0x18000ae4a  test    eax, eax
0x18000ae4c  js      short loc_18000AE61
0x18000ae4e  lea     rcx, [r14-18h]
0x18000ae52  mov     r9, rdi
0x18000ae55  mov     r8, rsi
0x18000ae58  mov     edx, ebp
0x18000ae5a  call    ?_Get@?$CWerComReportKeyValueList@$1??$WerComListConstCountFunc@$0DG@@@YAJPEAXPEAK@Z$1?WerpGetDynamicParameter@@YAJ0KPEAPEBG2@Z@@QEAAJJPEAPEAG0@Z; CWerComReportKeyValueList<&WerComListConstCountFunc<54>(void *,ulong *),&WerpGetDynamicParameter(void *,ulong,ushort const * *,ushort const * *)>::_Get(long,ushort * *,ushort * *)
0x18000ae5f  mov     ebx, eax
0x18000ae61  lea     rcx, [rsp+58h+var_38]; this
0x18000ae66  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000ae6b  mov     eax, ebx
0x18000ae6d  add     rsp, 30h
0x18000ae71  pop     r14
0x18000ae73  pop     rdi
0x18000ae74  pop     rsi
0x18000ae75  pop     rbp
0x18000ae76  pop     rbx
0x18000ae77  retn
```
