# SAL2::CSBE2FileScan::RepairFile(ushort const *)

- ea: `0x18007e950`
- end: `0x18007eac0`
- name: `?RepairFile@CSBE2FileScan@SAL2@@UEAAJPEBG@Z`
- size: `368`
- prototype: `int(SAL2::CSBE2FileScan *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x1800089b8`
- `0x18002573c`
- `0x1800627f0`
- `0x18007e7ec`
- `0x18007e950`
- `0x18008530c`
- `0x180087064`
- `0x180088ca0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007e9d4`
- `KERNEL32!GetLastError` at `0x18007e9d4`
- `KERNEL32!CreateFileW` at `0x18007e9c0`
- `KERNEL32!CreateFileW` at `0x18007e9c0`

## string_xrefs

- `0x18007ea88`: `multimedia\dshow\filters\sbe\sal\sallogrepair.cpp`

## pseudocode

```c
__int64 __fastcall SAL2::CSBE2FileScan::RepairFile(SAL2::CSBE2FileScan *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  struct CEhEventTracer *v4; // rcx
  unsigned int v5; // r9d
  unsigned int v6; // r8d
  void *v7; // rsi
  signed int LastError; // eax
  int v9; // eax
  void *v10; // r8
  struct SAL2::CSALLog *v12; // [rsp+68h] [rbp+10h] BYREF
  struct SAL2::ISALSyncIo *v13; // [rsp+70h] [rbp+18h] BYREF
  __int64 FileW; // [rsp+78h] [rbp+20h] BYREF

  FileW = -1;
  v12 = 0;
  v13 = 0;
  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = (SAL2::CSBE2FileScan *)((char *)this + 96);
    v5 = -2147467261;
    v6 = 198;
LABEL_14:
    SBEBasicTracers::EtwTraceError(v4, "multimedia\\dshow\\filters\\sbe\\sal\\sallogrepair.cpp", v6, v5);
    goto LABEL_15;
  }
  FileW = (__int64)CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x40000080u, 0);
  v7 = (void *)FileW;
  if ( FileW == -1 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = (SAL2::CSBE2FileScan *)((char *)this + 176);
    v5 = v3;
    v6 = 215;
    goto LABEL_14;
  }
  v9 = SAL2::CSALLog::CreateInstance(
         (struct SBEBasicTracers *)(((unsigned __int64)this + 8) & -(__int64)(this != (SAL2::CSBE2FileScan *)24)),
         0,
         0x1000u,
         0x40000u,
         &v12);
  v3 = v9;
  if ( v9 < 0 )
  {
    v6 = 225;
LABEL_13:
    v4 = (SAL2::CSBE2FileScan *)((char *)this + 96);
    v5 = v9;
    goto LABEL_14;
  }
  v9 = SAL2::CSALSyncFileIo::CreateInstance(v7, &v13);
  v3 = v9;
  if ( v9 < 0 )
  {
    v6 = 231;
    goto LABEL_13;
  }
  v9 = SAL2::CSALLog::Load(v12, v13, 0x80000000, 0, 0);
  v3 = v9;
  if ( v9 < 0 )
  {
    v6 = 234;
    goto LABEL_13;
  }
LABEL_15:
  SAL2::CloseHandle((SAL2 *)&FileW, (void **)0xFFFFFFFFFFFFFFFFLL, v10);
  SAL2::Release<SAL2::CSALResidentNVP *>(&v12);
  EhEtw::TPtr<IEhTraceSpan>::Release(&v13);
  return v3;
}

```

## disassembly

```asm
0x18007e950  push    rbx
0x18007e952  push    rsi
0x18007e953  push    rdi
0x18007e954  sub     rsp, 40h
0x18007e958  mov     [rsp+58h+arg_18], 0FFFFFFFFFFFFFFFFh
0x18007e961  mov     rax, rdx
0x18007e964  mov     [rsp+58h+arg_8], 0
0x18007e96d  mov     rdi, rcx
0x18007e970  mov     [rsp+58h+arg_10], 0
0x18007e979  test    rdx, rdx
0x18007e97c  jnz     short loc_18007E998
0x18007e97e  mov     ebx, 80004003h
0x18007e983  add     rcx, 60h ; '`'
0x18007e987  mov     r9d, 80004003h
0x18007e98d  mov     r8d, 0C6h
0x18007e993  jmp     loc_18007EA88
0x18007e998  xor     r9d, r9d; lpSecurityAttributes
0x18007e99b  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18007e9a4  mov     [rsp+58h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18007e9ac  mov     edx, 80000000h; dwDesiredAccess
0x18007e9b1  mov     rcx, rax; lpFileName
0x18007e9b4  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18007e9bc  lea     r8d, [r9+7]; dwShareMode
0x18007e9c0  call    cs:__imp_CreateFileW
0x18007e9c6  mov     [rsp+58h+arg_18], rax
0x18007e9cb  mov     rsi, rax
0x18007e9ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007e9d2  jnz     short loc_18007E9FE
0x18007e9d4  call    cs:__imp_GetLastError
0x18007e9da  mov     ebx, eax
0x18007e9dc  test    eax, eax
0x18007e9de  jle     short loc_18007E9E9
0x18007e9e0  movzx   ebx, ax
0x18007e9e3  or      ebx, 80070000h
0x18007e9e9  lea     rcx, [rdi+0B0h]
0x18007e9f0  mov     r9d, ebx
0x18007e9f3  mov     r8d, 0D7h
0x18007e9f9  jmp     loc_18007EA88
0x18007e9fe  lea     rdx, [rdi+8]
0x18007ea02  mov     r9d, 40000h; unsigned int
0x18007ea08  lea     rax, [rdi-18h]
0x18007ea0c  mov     r8d, 1000h; unsigned int
0x18007ea12  neg     rax
0x18007ea15  lea     rax, [rsp+58h+arg_8]
0x18007ea1a  sbb     rcx, rcx
0x18007ea1d  mov     qword ptr [rsp+58h+dwCreationDisposition], rax; struct SAL2::CSALLog **
0x18007ea22  and     rcx, rdx; struct SBEBasicTracers *
0x18007ea25  xor     edx, edx; struct SAL2::CSALPoolGrow *
0x18007ea27  call    ?CreateInstance@CSALLog@SAL2@@SAJPEAVSBEBasicTracers@@PEAVCSALPoolGrow@2@KKPEAPEAV12@@Z; SAL2::CSALLog::CreateInstance(SBEBasicTracers *,SAL2::CSALPoolGrow *,ulong,ulong,SAL2::CSALLog * *)
0x18007ea2c  mov     ebx, eax
0x18007ea2e  test    eax, eax
0x18007ea30  jns     short loc_18007EA3A
0x18007ea32  mov     r8d, 0E1h
0x18007ea38  jmp     short loc_18007EA81
0x18007ea3a  lea     rdx, [rsp+58h+arg_10]; struct SAL2::ISALSyncIo **
0x18007ea3f  mov     rcx, rsi; void *
0x18007ea42  call    ?CreateInstance@CSALSyncFileIo@SAL2@@SAJPEAXPEAPEAVISALSyncIo@2@@Z; SAL2::CSALSyncFileIo::CreateInstance(void *,SAL2::ISALSyncIo * *)
0x18007ea47  mov     ebx, eax
0x18007ea49  test    eax, eax
0x18007ea4b  jns     short loc_18007EA55
0x18007ea4d  mov     r8d, 0E7h
0x18007ea53  jmp     short loc_18007EA81
0x18007ea55  mov     rdx, [rsp+58h+arg_10]; struct SAL2::ISALSyncIo *
0x18007ea5a  xor     r9d, r9d; int
0x18007ea5d  mov     rcx, [rsp+58h+arg_8]; this
0x18007ea62  mov     r8d, 80000000h; unsigned int
0x18007ea68  mov     [rsp+58h+dwCreationDisposition], 0; int
0x18007ea70  call    ?Load@CSALLog@SAL2@@QEAAJPEAVISALSyncIo@2@KHH@Z; SAL2::CSALLog::Load(SAL2::ISALSyncIo *,ulong,int,int)
0x18007ea75  mov     ebx, eax
0x18007ea77  test    eax, eax
0x18007ea79  jns     short loc_18007EA94
0x18007ea7b  mov     r8d, 0EAh; unsigned int
0x18007ea81  lea     rcx, [rdi+60h]; struct CEhEventTracer *
0x18007ea85  mov     r9d, eax; unsigned int
0x18007ea88  lea     rdx, aMultimediaDsho_14; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x18007ea8f  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x18007ea94  or      rdx, 0FFFFFFFFFFFFFFFFh; void **
0x18007ea98  lea     rcx, [rsp+58h+arg_18]; this
0x18007ea9d  call    ?CloseHandle@SAL2@@YAXAEAPEAXPEAX@Z; SAL2::CloseHandle(void * &,void *)
0x18007eaa2  lea     rcx, [rsp+58h+arg_8]
0x18007eaa7  call    ??$Release@PEAVCSALResidentNVP@SAL2@@@SAL2@@YAXAEAPEAVCSALResidentNVP@0@@Z; SAL2::Release<SAL2::CSALResidentNVP *>(SAL2::CSALResidentNVP * &)
0x18007eaac  lea     rcx, [rsp+58h+arg_10]
0x18007eab1  call    ?Release@?$TPtr@UIEhTraceSpan@@@EhEtw@@QEAAXXZ; EhEtw::TPtr<IEhTraceSpan>::Release(void)
0x18007eab6  mov     eax, ebx
0x18007eab8  add     rsp, 40h
0x18007eabc  pop     rdi
0x18007eabd  pop     rsi
0x18007eabe  pop     rbx
0x18007eabf  retn
```
