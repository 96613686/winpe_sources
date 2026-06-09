# BufferedFileWriterCreate

- ea: `0x1800282b0`
- end: `0x180028369`
- name: `BufferedFileWriterCreate`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002158`
- `0x1800271f0`
- `0x180027260`
- `0x1800274c0`
- `0x1800282b0`
- `0x1800284e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180028338`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028338`

## string_xrefs

- `0x180028313`: `onecore\base\eco\wds\wdslib\common\src\bufferedfilewriter.cpp`

## pseudocode

```c
__int64 __fastcall BufferedFileWriterCreate(const unsigned __int16 *a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  char *v8; // rax
  char *v9; // rbx
  unsigned int v10; // edi
  __int64 v11; // rdx

  v8 = (char *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>(v8 + 16);
    *(_QWORD *)v9 = a2;
    *((_QWORD *)v9 + 1) = a3;
    v10 = CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::Initialize(
            (__int64)(v9 + 16),
            (__int64)v9,
            a1);
    if ( (unsigned int)ElValidateWin32_14(
                         v10,
                         v11,
                         "onecore\\base\\eco\\wds\\wdslib\\common\\src\\bufferedfilewriter.cpp",
                         134) )
    {
      CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>::~CBufferedFileWriter<CBufferedFileWriterConnector,&public: void CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,unsigned long),&public: void CBufferedFileWriterConnector::OnError(unsigned __int64,unsigned long,unsigned long)>((struct _RTL_CRITICAL_SECTION *)(v9 + 16));
      operator delete(v9);
    }
    else
    {
      *a4 = v9;
    }
  }
  else
  {
    return 8;
  }
  return v10;
}

```

## disassembly

```asm
0x1800282b0  mov     rax, rsp
0x1800282b3  mov     [rax+8], rbx
0x1800282b7  mov     [rax+10h], rbp
0x1800282bb  mov     [rax+18h], rsi
0x1800282bf  mov     [rax+20h], rdi
0x1800282c3  push    r14
0x1800282c5  sub     rsp, 20h
0x1800282c9  mov     rbp, rdx
0x1800282cc  mov     r14, rcx
0x1800282cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800282d6  mov     ecx, 88h; unsigned __int64
0x1800282db  mov     rsi, r9
0x1800282de  mov     rdi, r8
0x1800282e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800282e6  mov     rbx, rax
0x1800282e9  test    rax, rax
0x1800282ec  jz      short loc_180028346
0x1800282ee  lea     rcx, [rax+10h]
0x1800282f2  call    ??0?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAA@XZ; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>(void)
0x1800282f7  lea     rcx, [rbx+10h]
0x1800282fb  mov     [rbx], rbp
0x1800282fe  mov     r8, r14
0x180028301  mov     [rbx+8], rdi
0x180028305  mov     rdx, rbx
0x180028308  call    ?Initialize@?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAAKPEAVCBufferedFileWriterConnector@@PEBG@Z; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::Initialize(CBufferedFileWriterConnector *,ushort const *)
0x18002830d  mov     r9d, 86h
0x180028313  lea     r8, aOnecoreBaseEco_18; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002831a  mov     ecx, eax
0x18002831c  mov     edi, eax
0x18002831e  call    ElValidateWin32_14
0x180028323  test    eax, eax
0x180028325  jnz     short loc_18002832C
0x180028327  mov     [rsi], rbx
0x18002832a  jmp     short loc_18002834B
0x18002832c  lea     rcx, [rbx+10h]
0x180028330  call    ??1?$CBufferedFileWriter@VCBufferedFileWriterConnector@@$1?OnWriteDone@1@QEAAX_KK@Z$1?ReleaseBuffer@1@QEAAXPEAX0K@Z$1?OnError@1@QEAAX0KK@Z@@QEAA@XZ; CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>::~CBufferedFileWriter<CBufferedFileWriterConnector,&CBufferedFileWriterConnector::OnWriteDone(unsigned __int64,ulong),&CBufferedFileWriterConnector::ReleaseBuffer(void *,unsigned __int64,ulong),&CBufferedFileWriterConnector::OnError(unsigned __int64,ulong,ulong)>(void)
0x180028335  mov     rcx, rbx
0x180028338  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002833f  nop     dword ptr [rax+rax+00h]
0x180028344  jmp     short loc_18002834B
0x180028346  mov     edi, 8
0x18002834b  mov     rbx, [rsp+28h+arg_0]
0x180028350  mov     eax, edi
0x180028352  mov     rdi, [rsp+28h+arg_18]
0x180028357  mov     rbp, [rsp+28h+arg_8]
0x18002835c  mov     rsi, [rsp+28h+arg_10]
0x180028361  add     rsp, 20h
0x180028365  pop     r14
0x180028367  retn
```
