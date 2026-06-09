# Vml::VmComFileStream::Write(void const *,ulong,ulong *)

- ea: `0x1400cc9c0`
- end: `0x1400ccae3`
- name: `?Write@VmComFileStream@Vml@@UEAAJPEBXKPEAK@Z`
- size: `291`
- prototype: `__int64 __fastcall(Vml::VmComFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140005360`
- `0x14000ddac`
- `0x14000ea60`
- `0x1400341ac`
- `0x1400cc9c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cca46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400cca46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400cca3c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400cca3c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400cca66`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400cca66`

## string_xrefs

- `0x1400ccabf`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400ccad0`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400ccaa6`: `onecore\vm\common\vml\VmComStorage.h`

## pseudocode

```c
__int64 __fastcall Vml::VmComFileStream::Write(Vml::VmComFileStream *this, const void *a2, DWORD a3, unsigned int *a4)
{
  DWORD LastError; // eax
  const char *v7; // r9
  DWORD v8; // ecx
  __int64 result; // rax
  unsigned int v10; // eax
  int v11; // edx
  int lpOverlapped; // [rsp+20h] [rbp-58h]
  unsigned int lpOverlappeda; // [rsp+20h] [rbp-58h]
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x546,
      (unsigned int)"onecore\\vm\\common\\vml\\VmComStorage.h",
      (const char *)0x80004003LL,
      lpOverlapped);
  NumberOfBytesWritten = a3;
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  Overlapped.hEvent = 0;
  Overlapped.Offset = *((_DWORD *)this + 4);
  Overlapped.OffsetHigh = HIDWORD(*((_QWORD *)this + 2));
  if ( WriteFile(*((HANDLE *)this + 1), a2, a3, &NumberOfBytesWritten, &Overlapped) )
  {
    if ( !GetOverlappedResult(*((HANDLE *)this + 1), &Overlapped, &NumberOfBytesWritten, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x9DA,
        (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
        v7);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 997 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x9CF,
        (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
        (const char *)LastError,
        lpOverlappeda);
  }
  v8 = NumberOfBytesWritten;
  *((_QWORD *)this + 2) += NumberOfBytesWritten;
  if ( a4 )
    *a4 = v8;
  result = 0;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v10 = wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x559,
              (unsigned int)"onecore\\vm\\common\\vml\\VmComStorage.h",
              v7);
      NumberOfBytesWritten = Vml::VmlStgResultFromHResult((Vml *)v10, v11);
      result = NumberOfBytesWritten;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1400cc9c0  push    rbx
0x1400cc9c2  push    rdi
0x1400cc9c3  sub     rsp, 68h
0x1400cc9c7  mov     rax, cs:__security_cookie
0x1400cc9ce  xor     rax, rsp
0x1400cc9d1  mov     [rsp+78h+var_20], rax
0x1400cc9d6  mov     rbx, r9
0x1400cc9d9  mov     rdi, rcx
0x1400cc9dc  test    rbx, rbx
0x1400cc9df  jz      short loc_1400CC9E8
0x1400cc9e1  mov     dword ptr [r9], 0
0x1400cc9e8  mov     rcx, [rsp+78h]; this
0x1400cc9ed  test    rdx, rdx
0x1400cc9f0  jz      loc_1400CCAA0
0x1400cc9f6  mov     [rsp+78h+NumberOfBytesWritten], r8d
0x1400cc9fb  mov     [rsp+78h+Overlapped.Internal], 0
0x1400cca04  mov     [rsp+78h+Overlapped.InternalHigh], 0
0x1400cca0d  mov     [rsp+78h+Overlapped.hEvent], 0
0x1400cca16  mov     eax, [rdi+10h]
0x1400cca19  mov     dword ptr [rsp+78h+Overlapped.10h], eax
0x1400cca1d  mov     rax, [rdi+10h]
0x1400cca21  shr     rax, 20h
0x1400cca25  mov     dword ptr [rsp+78h+Overlapped.10h+4], eax
0x1400cca29  lea     rax, [rsp+78h+Overlapped]
0x1400cca2e  mov     qword ptr [rsp+78h+lpOverlapped], rax; unsigned int
0x1400cca33  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400cca38  mov     rcx, [rdi+8]; hFile
0x1400cca3c  call    cs:__imp_WriteFile
0x1400cca42  test    eax, eax
0x1400cca44  jnz     short loc_1400CCA55
0x1400cca46  call    cs:__imp_GetLastError
0x1400cca4c  cmp     eax, 3E5h
0x1400cca51  jnz     short loc_1400CCAB7
0x1400cca53  jmp     short loc_1400CCA75
0x1400cca55  xor     r9d, r9d; bWait
0x1400cca58  lea     r8, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesTransferred
0x1400cca5d  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x1400cca62  mov     rcx, [rdi+8]; hFile
0x1400cca66  call    cs:__imp_GetOverlappedResult
0x1400cca6c  mov     rcx, [rsp+78h]; this
0x1400cca71  test    eax, eax
0x1400cca73  jz      short loc_1400CCAD0
0x1400cca75  mov     ecx, [rsp+78h+NumberOfBytesWritten]
0x1400cca79  add     [rdi+10h], rcx
0x1400cca7d  test    rbx, rbx
0x1400cca80  jz      short loc_1400CCA84
0x1400cca82  mov     [rbx], ecx
0x1400cca84  xor     eax, eax
0x1400cca86  jmp     short loc_1400CCA8C
0x1400cca88  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x1400cca8c  mov     rcx, [rsp+78h+var_20]
0x1400cca91  xor     rcx, rsp; StackCookie
0x1400cca94  call    __security_check_cookie
0x1400cca99  add     rsp, 68h
0x1400cca9d  pop     rdi
0x1400cca9e  pop     rbx
0x1400cca9f  retn
0x1400ccaa0  mov     r9d, 80004003h; char *
0x1400ccaa6  lea     r8, aOnecoreVmCommo_1; "onecore\\vm\\common\\vml\\VmComStorage."...
0x1400ccaad  mov     edx, 546h; void *
0x1400ccab2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400ccab7  mov     rcx, [rsp+78h]; this
0x1400ccabc  mov     r9d, eax; char *
0x1400ccabf  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400ccac6  mov     edx, 9CFh; void *
0x1400ccacb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ccad0  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400ccad7  mov     edx, 9DAh; void *
0x1400ccadc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
