# CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::Initialize(CBufferedFileWriterConnector *,ushort const *)

- ea: `0x1800274c0`
- end: `0x180027570`
- name: `?Initialize@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAKPEAVCBufferedFileWriterConnector@@PEBG@Z`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800282b0`

## callees

- `0x180015830`
- `0x1800274c0`
- `0x1800284e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180027525`
- `KERNEL32!CreateFileW` at `0x180027525`
- `KERNEL32!GetLastError` at `0x18002753b`
- `KERNEL32!GetLastError` at `0x18002753b`

## string_xrefs

- `0x1800274ed`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`
- `0x18002754d`: `onecore\base\Eco\WDS\wdslib\common\inc\BufferedFileWriter.h`

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
0x1800274c0  mov     [rsp+arg_0], rbx
0x1800274c5  mov     [rsp+arg_8], rsi
0x1800274ca  push    rdi
0x1800274cb  sub     rsp, 40h
0x1800274cf  mov     rsi, r8
0x1800274d2  mov     [rcx+28h], rdx
0x1800274d6  lea     r8, [rcx+50h]; unsigned __int16 **
0x1800274da  mov     rdi, rcx
0x1800274dd  mov     rcx, rsi; unsigned __int16 *
0x1800274e0  xor     edx, edx; int
0x1800274e2  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x1800274e7  mov     r9d, 12Bh
0x1800274ed  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800274f4  mov     ecx, eax
0x1800274f6  mov     ebx, eax
0x1800274f8  call    ElValidateWin32_14
0x1800274fd  test    eax, eax
0x1800274ff  jnz     short loc_18002755D
0x180027501  and     [rsp+48h+var_18], 0
0x180027507  xor     r9d, r9d; lpSecurityAttributes
0x18002750a  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180027512  xor     r8d, r8d; dwShareMode
0x180027515  mov     edx, 40000000h; dwDesiredAccess
0x18002751a  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x180027522  mov     rcx, rsi; lpFileName
0x180027525  call    cs:__imp_CreateFileW
0x18002752c  nop     dword ptr [rax+rax+00h]
0x180027531  mov     [rdi+30h], rax
0x180027535  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027539  jnz     short loc_18002755D
0x18002753b  call    cs:__imp_GetLastError
0x180027542  nop     dword ptr [rax+rax+00h]
0x180027547  mov     r9d, 13Ah
0x18002754d  lea     r8, aOnecoreBaseEco_26; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180027554  mov     ecx, eax
0x180027556  call    ElValidateWin32_14
0x18002755b  mov     ebx, eax
0x18002755d  mov     rsi, [rsp+48h+arg_8]
0x180027562  mov     eax, ebx
0x180027564  mov     rbx, [rsp+48h+arg_0]
0x180027569  add     rsp, 40h
0x18002756d  pop     rdi
0x18002756e  retn
```
