# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::Get(long,ushort * *)

- ea: `0x18000af40`
- end: `0x18000af8e`
- name: `?Get@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@UEAAJJPEAPEAG@Z`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000af40`
- `0x18000f59c`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::Get(
        __int64 a1,
        unsigned int a2,
        BSTR *a3)
{
  int v6; // ebx
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 2;
  v6 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( v6 >= 0 )
    v6 = CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long GetFileNameByIndex(void *,unsigned long,unsigned short const * *)>::_Get(
           a1 - 24,
           a2,
           a3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000af40  push    rbx
0x18000af42  push    rbp
0x18000af43  push    rsi
0x18000af44  push    rdi
0x18000af45  sub     rsp, 28h
0x18000af49  mov     rbp, rcx
0x18000af4c  mov     [rsp+48h+arg_18], 2
0x18000af54  lea     rcx, [rsp+48h+arg_18]; this
0x18000af59  mov     rdi, r8
0x18000af5c  mov     esi, edx
0x18000af5e  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000af63  mov     ebx, eax
0x18000af65  test    eax, eax
0x18000af67  js      short loc_18000AF79
0x18000af69  lea     rcx, [rbp-18h]
0x18000af6d  mov     r8, rdi
0x18000af70  mov     edx, esi
0x18000af72  call    ?_Get@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?GetFileNameByIndex@@YAJ0KPEAPEBG@Z@@QEAAJJPEAPEAG@Z; CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&GetFileNameByIndex(void *,ulong,ushort const * *)>::_Get(long,ushort * *)
0x18000af77  mov     ebx, eax
0x18000af79  lea     rcx, [rsp+48h+arg_18]; this
0x18000af7e  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000af83  mov     eax, ebx
0x18000af85  add     rsp, 28h
0x18000af89  pop     rdi
0x18000af8a  pop     rsi
0x18000af8b  pop     rbp
0x18000af8c  pop     rbx
0x18000af8d  retn
```
