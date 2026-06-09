# CCabDecompressor::CabDecompressorFileOpen(char const *,int,int)

- ea: `0x180015670`
- end: `0x1800157d4`
- name: `?CabDecompressorFileOpen@CCabDecompressor@@CA_JPEBDHH@Z`
- size: `356`
- prototype: `INT_PTR __cdecl(LPSTR pszFile, int oflag, int pmode)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015158`

## callees

- `0x180005f64`
- `0x18000956c`
- `0x18000a60c`
- `0x18000deec`
- `0x180015670`
- `0x1800165cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001572e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001572e`

## string_xrefs

- `0x18001576b`: `CreateFile(%ws)`
- `0x180015743`: `CCabDecompressor::CabDecompressorFileOpen`
- `0x1800157b2`: `CCabDecompressor::CabDecompressorFileOpen`

## pseudocode

```c
INT_PTR __fastcall CCabDecompressor::CabDecompressorFileOpen(const CHAR *pszFile, int oflag, int pmode)
{
  char *v4; // rax
  _QWORD *v5; // rbx
  struct CCabDecompressor *Node; // rax
  struct _SECURITY_ATTRIBUTES *v7; // r9
  struct CCabDecompressor *v8; // rdi
  int v9; // eax
  void *FileRetryIfSharingViolation; // rax
  void *v12; // [rsp+30h] [rbp-38h]
  unsigned int v13; // [rsp+38h] [rbp-30h]
  void *v14; // [rsp+40h] [rbp-28h]

  v4 = (char *)SusAlloc(0x20u);
  v5 = v4;
  if ( v4 )
  {
    *(_DWORD *)v4 = 0;
    *(_QWORD *)(v4 + 20) = 0;
    Node = CCabDecompressorList::FindNode(pszFile);
    v8 = Node;
    if ( !Node )
      return (INT_PTR)v5;
    v9 = *((_DWORD *)Node + 34);
    if ( !v9 )
    {
      v5[1] = *((_QWORD *)v8 + 7);
      *((_DWORD *)v5 + 4) = 0;
      return (INT_PTR)v5;
    }
    if ( v9 == 1 )
    {
      FileRetryIfSharingViolation = SusCreateFileRetryIfSharingViolation(
                                      *((LPCWSTR *)v8 + 15),
                                      0x80000000,
                                      1u,
                                      v7,
                                      3u,
                                      0x80u,
                                      v12,
                                      v13,
                                      v14,
                                      1,
                                      *((_DWORD *)v8 + 38));
      v5[1] = FileRetryIfSharingViolation;
      if ( FileRetryIfSharingViolation != (void *)-1LL )
      {
        *((_DWORD *)v5 + 4) = 1;
        *((_DWORD *)v5 + 6) = *((_DWORD *)v8 + 39);
        return (INT_PTR)v5;
      }
      GetLastError();
      WUTrace("CCabDecompressor::CabDecompressorFileOpen", 733, 32, 3);
    }
    CSusBaseAllocTag<942762101>::operator delete(v5);
  }
  WUTrace("CCabDecompressor::CabDecompressorFileOpen", 756, 32, 3);
  return -1;
}

```

## disassembly

```asm
0x180015670  mov     [rsp+arg_0], rbx
0x180015675  mov     [rsp+arg_8], rsi
0x18001567a  push    rdi
0x18001567b  sub     rsp, 60h
0x18001567f  mov     rdi, rcx
0x180015682  mov     ecx, 20h ; ' '; unsigned __int64
0x180015687  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18001568c  mov     rbx, rax
0x18001568f  test    rax, rax
0x180015692  jnz     short loc_18001569E
0x180015694  mov     esi, 8007000Eh
0x180015699  jmp     loc_1800157A0
0x18001569e  mov     rcx, rdi; lpString1
0x1800156a1  mov     dword ptr [rax], 0
0x1800156a7  mov     qword ptr [rax+14h], 0
0x1800156af  call    ?FindNode@CCabDecompressorList@@SAPEAVCCabDecompressor@@PEBD@Z; CCabDecompressorList::FindNode(char const *)
0x1800156b4  mov     rdi, rax
0x1800156b7  test    rax, rax
0x1800156ba  jz      short loc_1800156D5
0x1800156bc  mov     eax, [rax+88h]
0x1800156c2  test    eax, eax
0x1800156c4  jnz     short loc_1800156E8
0x1800156c6  mov     rax, [rdi+38h]
0x1800156ca  mov     [rbx+8], rax
0x1800156ce  mov     dword ptr [rbx+10h], 0
0x1800156d5  mov     rax, rbx
0x1800156d8  mov     rbx, [rsp+68h+arg_0]
0x1800156dd  mov     rsi, [rsp+68h+arg_8]
0x1800156e2  add     rsp, 60h
0x1800156e6  pop     rdi
0x1800156e7  retn
0x1800156e8  mov     esi, 1
0x1800156ed  cmp     eax, esi
0x1800156ef  jnz     loc_180015793
0x1800156f5  mov     eax, [rdi+98h]
0x1800156fb  mov     r8d, esi; dwShareMode
0x1800156fe  mov     rcx, [rdi+78h]; lpFileName
0x180015702  mov     edx, 80000000h; dwDesiredAccess
0x180015707  mov     [rsp+68h+var_18], eax; unsigned int
0x18001570b  mov     [rsp+68h+var_20], esi; int
0x18001570f  mov     [rsp+68h+var_40], 80h; DWORD
0x180015717  mov     [rsp+68h+var_48], 3; DWORD
0x18001571f  call    ?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z; SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)
0x180015724  mov     [rbx+8], rax
0x180015728  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001572c  jnz     short loc_180015782
0x18001572e  call    cs:__imp_GetLastError
0x180015734  movzx   esi, ax
0x180015737  mov     r9d, 3
0x18001573d  or      esi, 80070000h
0x180015743  lea     rcx, aCcabdecompress; "CCabDecompressor::CabDecompressorFileOp"...
0x18001574a  test    eax, eax
0x18001574c  mov     edx, 2DDh
0x180015751  cmovle  esi, eax
0x180015754  lea     r8d, [r9+1Dh]
0x180015758  test    esi, esi
0x18001575a  mov     eax, 8000FFFFh
0x18001575f  cmovns  esi, eax
0x180015762  mov     rax, [rdi+78h]
0x180015766  mov     [rsp+68h+var_38], rax
0x18001576b  lea     rax, aCreatefileWs; "CreateFile(%ws)"
0x180015772  mov     qword ptr [rsp+68h+var_40], rax
0x180015777  mov     [rsp+68h+var_48], esi
0x18001577b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180015780  jmp     short loc_180015798
0x180015782  mov     [rbx+10h], esi
0x180015785  mov     eax, [rdi+9Ch]
0x18001578b  mov     [rbx+18h], eax
0x18001578e  jmp     loc_1800156D5
0x180015793  mov     esi, 80240FFFh
0x180015798  mov     rcx, rbx; lpMem
0x18001579b  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800157a0  lea     rdx, aMethodFailed; "Method failed"
0x1800157a7  mov     r9d, 3
0x1800157ad  mov     qword ptr [rsp+68h+var_40], rdx
0x1800157b2  lea     rcx, aCcabdecompress; "CCabDecompressor::CabDecompressorFileOp"...
0x1800157b9  mov     edx, 2F4h
0x1800157be  mov     [rsp+68h+var_48], esi
0x1800157c2  lea     r8d, [r9+1Dh]
0x1800157c6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800157cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800157cf  jmp     loc_1800156D8
```
