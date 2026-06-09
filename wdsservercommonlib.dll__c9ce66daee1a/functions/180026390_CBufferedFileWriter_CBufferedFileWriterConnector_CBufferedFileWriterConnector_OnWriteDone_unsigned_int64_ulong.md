# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::Initialize(CBufferedFileWriterConnector *,ushort const *)

- ea: `0x180026390`
- end: `0x180026440`
- name: `?Initialize@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAKPEAVCBufferedFileWriterConnector@@PEBG@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027160`

## callees

- `0x180014b10`
- `0x180026390`
- `0x180027390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002640b`
- `KERNEL32!GetLastError` at `0x18002640b`
- `KERNEL32!CreateFileW` at `0x1800263f5`
- `KERNEL32!CreateFileW` at `0x1800263f5`

## string_xrefs

- `0x1800263bd`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x18002641d`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

## pseudocode

```c
__int64 __fastcall CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::Initialize(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 v9; // rdx

  *(_QWORD *)(a1 + 40) = a2;
  v5 = DuplicateStringWBom(a3, 0, (unsigned __int16 **)(a1 + 80));
  if ( !(unsigned int)ElValidateWin32_14(
                        v5,
                        v6,
                        "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                        299) )
  {
    FileW = CreateFileW(a3, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    *(_QWORD *)(a1 + 48) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      return (unsigned int)ElValidateWin32_14(
                             LastError,
                             v9,
                             "onecore\\base\\Eco\\WDS\\wdslib\\common\\inc\\BufferedFileWriter.h",
                             314);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180026390  mov     [rsp+arg_0], rbx
0x180026395  mov     [rsp+arg_8], rsi
0x18002639a  push    rdi
0x18002639b  sub     rsp, 40h
0x18002639f  mov     rsi, r8
0x1800263a2  mov     [rcx+28h], rdx
0x1800263a6  lea     r8, [rcx+50h]; unsigned __int16 **
0x1800263aa  mov     rdi, rcx
0x1800263ad  mov     rcx, rsi; unsigned __int16 *
0x1800263b0  xor     edx, edx; int
0x1800263b2  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x1800263b7  mov     r9d, 12Bh
0x1800263bd  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800263c4  mov     ecx, eax
0x1800263c6  mov     ebx, eax
0x1800263c8  call    ElValidateWin32_14
0x1800263cd  test    eax, eax
0x1800263cf  jnz     short loc_18002642D
0x1800263d1  and     [rsp+48h+var_18], 0
0x1800263d7  xor     r9d, r9d; lpSecurityAttributes
0x1800263da  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800263e2  xor     r8d, r8d; dwShareMode
0x1800263e5  mov     edx, 40000000h; dwDesiredAccess
0x1800263ea  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x1800263f2  mov     rcx, rsi; lpFileName
0x1800263f5  call    cs:__imp_CreateFileW
0x1800263fc  nop     dword ptr [rax+rax+00h]
0x180026401  mov     [rdi+30h], rax
0x180026405  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026409  jnz     short loc_18002642D
0x18002640b  call    cs:__imp_GetLastError
0x180026412  nop     dword ptr [rax+rax+00h]
0x180026417  mov     r9d, 13Ah
0x18002641d  lea     r8, aOnecoreBaseEco_27; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180026424  mov     ecx, eax
0x180026426  call    ElValidateWin32_14
0x18002642b  mov     ebx, eax
0x18002642d  mov     rsi, [rsp+48h+arg_8]
0x180026432  mov     eax, ebx
0x180026434  mov     rbx, [rsp+48h+arg_0]
0x180026439  add     rsp, 40h
0x18002643d  pop     rdi
0x18002643e  retn
```
