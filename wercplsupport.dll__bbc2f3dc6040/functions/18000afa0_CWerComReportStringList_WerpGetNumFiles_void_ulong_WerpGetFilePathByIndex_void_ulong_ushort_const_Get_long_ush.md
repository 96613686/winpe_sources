# CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::Get(long,ushort * *)

- ea: `0x18000afa0`
- end: `0x18000afee`
- name: `?Get@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@UEAAJJPEAPEAG@Z`
- size: `78`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007d20`
- `0x180007fe0`
- `0x18000afa0`
- `0x18000f6c8`

## pseudocode

```c
__int64 __fastcall CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::Get(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  int v6; // ebx
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 2;
  v6 = CAutoImpersonate::ImpersonateUserHighestPrivs((CAutoImpersonate *)&v8);
  if ( v6 >= 0 )
    v6 = CWerComReportStringList<&long WerpGetNumFiles(void *,unsigned long *),&long WerpGetFilePathByIndex(void *,unsigned long,unsigned short const * *)>::_Get(
           a1 - 24,
           a2,
           a3);
  CAutoImpersonate::~CAutoImpersonate((CAutoImpersonate *)&v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000afa0  push    rbx
0x18000afa2  push    rbp
0x18000afa3  push    rsi
0x18000afa4  push    rdi
0x18000afa5  sub     rsp, 28h
0x18000afa9  mov     rbp, rcx
0x18000afac  mov     [rsp+48h+arg_18], 2
0x18000afb4  lea     rcx, [rsp+48h+arg_18]; this
0x18000afb9  mov     rdi, r8
0x18000afbc  mov     esi, edx
0x18000afbe  call    ?ImpersonateUserHighestPrivs@CAutoImpersonate@@QEAAJXZ; CAutoImpersonate::ImpersonateUserHighestPrivs(void)
0x18000afc3  mov     ebx, eax
0x18000afc5  test    eax, eax
0x18000afc7  js      short loc_18000AFD9
0x18000afc9  lea     rcx, [rbp-18h]
0x18000afcd  mov     r8, rdi
0x18000afd0  mov     edx, esi
0x18000afd2  call    ?_Get@?$CWerComReportStringList@$1?WerpGetNumFiles@@YAJPEAXPEAK@Z$1?WerpGetFilePathByIndex@@YAJ0KPEAPEBG@Z@@QEAAJJPEAPEAG@Z; CWerComReportStringList<&WerpGetNumFiles(void *,ulong *),&WerpGetFilePathByIndex(void *,ulong,ushort const * *)>::_Get(long,ushort * *)
0x18000afd7  mov     ebx, eax
0x18000afd9  lea     rcx, [rsp+48h+arg_18]; this
0x18000afde  call    ??1CAutoImpersonate@@QEAA@XZ; CAutoImpersonate::~CAutoImpersonate(void)
0x18000afe3  mov     eax, ebx
0x18000afe5  add     rsp, 28h
0x18000afe9  pop     rdi
0x18000afea  pop     rsi
0x18000afeb  pop     rbp
0x18000afec  pop     rbx
0x18000afed  retn
```
