# CWordParsingFSM::BuildFromBin(ushort const *,IMSASRLocaleHandler *)

- ea: `0x1800f5340`
- end: `0x1800f5423`
- name: `?BuildFromBin@CWordParsingFSM@@UEAAJPEBGPEAUIMSASRLocaleHandler@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(CWordParsingFSM *__hidden this, const unsigned __int16 *, struct IMSASRLocaleHandler *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800f5340`
- `0x1800f6cbc`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800f536c`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800f536c`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800f540b`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800f540b`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x1800f53b3`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x1800f53b3`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f53a8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f53a8`

## string_xrefs

- `0x1800f53f0`: `Failed to open binary file: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWordParsingFSM::BuildFromBin(
        CWordParsingFSM *this,
        const unsigned __int16 *a2,
        struct IMSASRLocaleHandler *a3)
{
  errno_t v6; // eax
  int v7; // eax
  int v8; // ebx
  FILE *Stream; // [rsp+20h] [rbp-18h] BYREF
  char Buffer; // [rsp+58h] [rbp+20h] BYREF

  Stream = 0;
  v6 = _wfopen_s(&Stream, a2, L"rb");
  if ( !Stream || v6 )
  {
    WPFsmError(L"Failed to open binary file: %s", a2);
    v8 = -2147467259;
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(CWordParsingFSM *))(*(_QWORD *)this + 80LL))(this);
    Buffer = 0;
    v8 = v7;
    fread(&Buffer, 1u, 1u, Stream);
    if ( feof(Stream) )
    {
      if ( v8 >= 0 )
        v8 = (*(__int64 (__fastcall **)(CWordParsingFSM *, struct IMSASRLocaleHandler *))(*(_QWORD *)this + 128LL))(
               this,
               a3);
    }
    else
    {
      WPFsmError(L"Failed to load binary file. Expected EOF");
      v8 = -2147024809;
    }
  }
  if ( Stream )
    fclose(Stream);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800f5340  mov     rax, rsp
0x1800f5343  mov     [rax+8], rbx
0x1800f5347  mov     [rax+10h], rsi
0x1800f534b  push    rdi
0x1800f534c  sub     rsp, 30h
0x1800f5350  mov     rsi, r8
0x1800f5353  mov     qword ptr [rax-18h], 0
0x1800f535b  mov     rdi, rcx
0x1800f535e  lea     r8, aRb; "rb"
0x1800f5365  lea     rcx, [rax-18h]; Stream
0x1800f5369  mov     rbx, rdx
0x1800f536c  call    cs:__imp__wfopen_s
0x1800f5372  mov     rdx, [rsp+38h+Stream]
0x1800f5377  test    rdx, rdx
0x1800f537a  jz      short loc_1800F53ED
0x1800f537c  test    eax, eax
0x1800f537e  jnz     short loc_1800F53ED
0x1800f5380  mov     rax, [rdi]
0x1800f5383  mov     rcx, rdi
0x1800f5386  mov     rax, [rax+50h]
0x1800f538a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f538f  mov     r9, [rsp+38h+Stream]; Stream
0x1800f5394  lea     rcx, [rsp+38h+Buffer]; Buffer
0x1800f5399  mov     edx, 1; ElementSize
0x1800f539e  mov     [rsp+38h+Buffer], 0
0x1800f53a3  mov     r8d, edx; ElementCount
0x1800f53a6  mov     ebx, eax
0x1800f53a8  call    cs:__imp_fread
0x1800f53ae  mov     rcx, [rsp+38h+Stream]; Stream
0x1800f53b3  call    cs:__imp_feof
0x1800f53b9  test    eax, eax
0x1800f53bb  jnz     short loc_1800F53D0
0x1800f53bd  lea     rcx, aFailedToLoadBi; "Failed to load binary file. Expected EO"...
0x1800f53c4  call    ?WPFsmError@@YAXPEBGZZ; WPFsmError(ushort const *,...)
0x1800f53c9  mov     ebx, 80070057h
0x1800f53ce  jmp     short loc_1800F5401
0x1800f53d0  test    ebx, ebx
0x1800f53d2  js      short loc_1800F5401
0x1800f53d4  mov     rax, [rdi]
0x1800f53d7  mov     rdx, rsi
0x1800f53da  mov     rcx, rdi
0x1800f53dd  mov     rax, [rax+80h]
0x1800f53e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f53e9  mov     ebx, eax
0x1800f53eb  jmp     short loc_1800F5401
0x1800f53ed  mov     rdx, rbx
0x1800f53f0  lea     rcx, aFailedToOpenBi; "Failed to open binary file: %s"
0x1800f53f7  call    ?WPFsmError@@YAXPEBGZZ; WPFsmError(ushort const *,...)
0x1800f53fc  mov     ebx, 80004005h
0x1800f5401  mov     rcx, [rsp+38h+Stream]; Stream
0x1800f5406  test    rcx, rcx
0x1800f5409  jz      short loc_1800F5411
0x1800f540b  call    cs:__imp_fclose
0x1800f5411  mov     rsi, [rsp+38h+arg_8]
0x1800f5416  mov     eax, ebx
0x1800f5418  mov     rbx, [rsp+38h+arg_0]
0x1800f541d  add     rsp, 30h
0x1800f5421  pop     rdi
0x1800f5422  retn
```
