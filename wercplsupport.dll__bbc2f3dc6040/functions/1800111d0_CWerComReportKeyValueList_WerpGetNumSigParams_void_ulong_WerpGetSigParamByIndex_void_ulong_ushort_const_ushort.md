# CWerComReportKeyValueList<&WerpGetNumSigParams(void *,ulong *),&WerpGetSigParamByIndex(void *,ulong,ushort const * *,ushort const * *)>::get_Count(long *)

- ea: `0x1800111d0`
- end: `0x180011237`
- name: `?get_Count@?$CWerComReportKeyValueList@$1?WerpGetNumSigParams@@YAJPEAXPEAK@Z$1?WerpGetSigParamByIndex@@YAJ0KPEAPEBG2@Z@@UEAAJPEAJ@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x1800111d0`

## import_xrefs

- `wer!WerpGetNumSigParams` at `0x18001120d`
- `wer!WerpGetNumSigParams` at `0x18001120d`

## pseudocode

```c
__int64 __fastcall CWerComReportKeyValueList<&long WerpGetNumSigParams(void *,unsigned long *),&long WerpGetSigParamByIndex(void *,unsigned long,unsigned short const * *,unsigned short const * *)>::get_Count(
        __int64 a1,
        _DWORD *a2)
{
  int NumSigParams; // ebx
  __int64 v5; // rcx
  int v7; // [rsp+40h] [rbp+18h] BYREF
  int v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 2;
  NumSigParams = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( NumSigParams >= 0 )
  {
    v5 = *(_QWORD *)(a1 + 8);
    v7 = 0;
    NumSigParams = WerpGetNumSigParams(v5, &v7);
    *a2 = v7;
  }
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)NumSigParams;
}

```

## disassembly

```asm
0x1800111d0  mov     rax, rsp
0x1800111d3  mov     [rax+8], rbx
0x1800111d7  mov     [rax+10h], rsi
0x1800111db  push    rdi
0x1800111dc  sub     rsp, 20h
0x1800111e0  mov     rsi, rcx
0x1800111e3  mov     dword ptr [rax+20h], 2
0x1800111ea  lea     rcx, [rax+20h]; this
0x1800111ee  mov     rdi, rdx
0x1800111f1  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x1800111f6  mov     ebx, eax
0x1800111f8  test    eax, eax
0x1800111fa  js      short loc_18001121B
0x1800111fc  mov     rcx, [rsi+8]
0x180011200  lea     rdx, [rsp+28h+arg_10]
0x180011205  mov     [rsp+28h+arg_10], 0
0x18001120d  call    cs:__imp_WerpGetNumSigParams
0x180011213  mov     ecx, [rsp+28h+arg_10]
0x180011217  mov     ebx, eax
0x180011219  mov     [rdi], ecx
0x18001121b  lea     rcx, [rsp+28h+arg_18]; this
0x180011220  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x180011225  mov     rsi, [rsp+28h+arg_8]
0x18001122a  mov     eax, ebx
0x18001122c  mov     rbx, [rsp+28h+arg_0]
0x180011231  add     rsp, 20h
0x180011235  pop     rdi
0x180011236  retn
```
