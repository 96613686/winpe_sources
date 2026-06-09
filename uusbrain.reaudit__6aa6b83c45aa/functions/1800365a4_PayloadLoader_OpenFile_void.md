# PayloadLoader::OpenFile(void * *)

- ea: `0x1800365a4`
- end: `0x18003666c`
- name: `?OpenFile@PayloadLoader@@QEAAJPEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(PayloadLoader *__hidden this, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180039190`

## callees

- `0x180026a00`
- `0x180026cd8`
- `0x1800365a4`
- `0x180036948`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036606`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036606`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PayloadLoader::OpenFile(PayloadLoader *this, void **a2)
{
  int v4; // eax
  const WCHAR *v5; // rcx
  char *FileW; // rax
  const char *v7; // r9
  wil *v8; // rcx
  __int64 result; // rax
  int v10; // edi
  unsigned int v11; // esi
  __int64 FileVerString; // rax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-68h]
  unsigned int Failure; // [rsp+50h] [rbp-38h]
  _BYTE v17[40]; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    if ( (*((_BYTE *)this + 64) & 3) != 0 )
    {
      v4 = PayloadLoader::ValidateBinaryIfEnabled(this);
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x47,
          (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\PayloadLoader.hpp",
          (const char *)(unsigned int)v4,
          dwCreationDisposition);
    }
    v5 = (const WCHAR *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) > 7u )
      v5 = *(const WCHAR **)v5;
    FileW = (char *)CreateFileW(v5, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v8 = retaddr;
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x54,
        (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\PayloadLoader.hpp",
        v7);
    *a2 = FileW;
    result = 0;
  }
  catch ( ... )
  {
    v10 = wil::ResultFromCaughtException(v8);
    v11 = *((_DWORD *)this + 16);
    FileVerString = PayloadLoader::GetFileVerString(this, v17);
    if ( *(_QWORD *)(FileVerString + 24) > 7u )
      FileVerString = *(_QWORD *)FileVerString;
    Failure = PayloadLoader::ReportLoadFailure(
                *(const wchar_t **)this,
                *((_BYTE *)this + 8),
                (PayloadLoader *)((char *)this + 16),
                (PayloadLoader *)((char *)this + 32),
                (PayloadLoader *)((char *)this + 72),
                (const wchar_t *)FileVerString,
                v11,
                0,
                v10);
    std::wstring::_Tidy_deallocate(v17);
    return Failure;
  }
  return result;
}

```

## disassembly

```asm
0x1800365a4  mov     [rsp+arg_10], rbx
0x1800365a9  push    rdi
0x1800365aa  sub     rsp, 80h
0x1800365b1  mov     rdi, rdx
0x1800365b4  mov     rbx, rcx
0x1800365b7  mov     [rsp+88h+var_38], rcx
0x1800365bc  test    byte ptr [rcx+40h], 3
0x1800365c0  jz      short loc_1800365D3
0x1800365c2  call    ?ValidateBinaryIfEnabled@PayloadLoader@@AEAAJXZ; PayloadLoader::ValidateBinaryIfEnabled(void)
0x1800365c7  mov     rcx, [rsp+88h]; this
0x1800365cf  test    eax, eax
0x1800365d1  js      short loc_180036644
0x1800365d3  lea     rcx, [rbx+48h]
0x1800365d7  cmp     qword ptr [rcx+18h], 7
0x1800365dc  jbe     short loc_1800365E1
0x1800365de  mov     rcx, [rcx]; lpFileName
0x1800365e1  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x1800365ea  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800365f2  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1800365fa  xor     r9d, r9d; lpSecurityAttributes
0x1800365fd  mov     edx, 80000000h; dwDesiredAccess
0x180036602  lea     r8d, [r9+1]; dwShareMode
0x180036606  call    cs:__imp_CreateFileW
0x18003660c  mov     [rsp+88h+var_30], rax
0x180036611  lea     rcx, [rax-1]
0x180036615  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180036619  setnbe  dl
0x18003661c  mov     rcx, [rsp+88h]; this
0x180036624  test    dl, dl
0x180036626  jnz     short loc_180036659
0x180036628  mov     [rdi], rax
0x18003662b  xor     eax, eax
0x18003662d  jmp     short loc_180036633
0x18003662f  mov     eax, dword ptr [rsp+88h+var_38]
0x180036633  mov     rbx, [rsp+88h+arg_10]
0x18003663b  add     rsp, 80h
0x180036642  pop     rdi
0x180036643  retn
0x180036644  mov     r9d, eax; char *
0x180036647  lea     r8, aCW1SSrcBrainLi_9; "C:\\__w\\1\\s\\src\\brain\\lib\\Payload"...
0x18003664e  mov     edx, 47h ; 'G'; void *
0x180036653  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180036659  lea     r8, aCW1SSrcBrainLi_9; "C:\\__w\\1\\s\\src\\brain\\lib\\Payload"...
0x180036660  mov     edx, 54h ; 'T'; void *
0x180036665  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
