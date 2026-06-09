# CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::Get(long,ushort * *,ushort * *)

- ea: `0x18000ae80`
- end: `0x18000aed8`
- name: `?Get@?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@UEAAJJPEAPEAG0@Z`
- size: `88`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000ae80`
- `0x18000f364`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::Get(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  int v8; // ebx
  _DWORD v10[14]; // [rsp+20h] [rbp-38h] BYREF

  v10[0] = 2;
  v8 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)v10);
  if ( v8 >= 0 )
    v8 = CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::_Get(
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
0x18000ae80  push    rbx
0x18000ae82  push    rbp
0x18000ae83  push    rsi
0x18000ae84  push    rdi
0x18000ae85  push    r14
0x18000ae87  sub     rsp, 30h
0x18000ae8b  mov     r14, rcx
0x18000ae8e  mov     [rsp+58h+var_38], 2
0x18000ae96  lea     rcx, [rsp+58h+var_38]; this
0x18000ae9b  mov     rdi, r9
0x18000ae9e  mov     rsi, r8
0x18000aea1  mov     ebp, edx
0x18000aea3  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000aea8  mov     ebx, eax
0x18000aeaa  test    eax, eax
0x18000aeac  js      short loc_18000AEC1
0x18000aeae  lea     rcx, [r14-18h]
0x18000aeb2  mov     r9, rdi
0x18000aeb5  mov     r8, rsi
0x18000aeb8  mov     edx, ebp
0x18000aeba  call    ?_Get@?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@QEAAJJPEAPEAG0@Z; CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::_Get(long,ushort * *,ushort * *)
0x18000aebf  mov     ebx, eax
0x18000aec1  lea     rcx, [rsp+58h+var_38]; this
0x18000aec6  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000aecb  mov     eax, ebx
0x18000aecd  add     rsp, 30h
0x18000aed1  pop     r14
0x18000aed3  pop     rdi
0x18000aed4  pop     rsi
0x18000aed5  pop     rbp
0x18000aed6  pop     rbx
0x18000aed7  retn
```
