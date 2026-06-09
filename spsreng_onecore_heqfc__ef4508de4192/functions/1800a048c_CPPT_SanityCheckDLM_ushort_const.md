# CPPT::SanityCheckDLM(ushort const *)

- ea: `0x1800a048c`
- end: `0x1800a0526`
- name: `?SanityCheckDLM@CPPT@@SA_NPEBG@Z`
- size: `154`
- prototype: `bool __fastcall(wchar_t *FileName)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b6a0`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x1800a048c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800a04d2`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800a04d2`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800a0505`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800a0505`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a04f5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a04f5`

## pseudocode

```c
bool __fastcall CPPT::SanityCheckDLM(wchar_t *FileName)
{
  errno_t v2; // eax
  FILE *v3; // rcx
  FILE *Stream; // [rsp+20h] [rbp-98h] BYREF
  _BYTE Buffer[112]; // [rsp+30h] [rbp-88h] BYREF

  memset_0(Buffer, 0, 0x68u);
  Stream = 0;
  v2 = _wfopen_s(&Stream, FileName, L"rb");
  v3 = Stream;
  if ( Stream )
  {
    if ( !v2 )
    {
      fread(Buffer, 0x68u, 1u, Stream);
      v3 = Stream;
    }
    if ( v3 )
      fclose(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a048c  push    rbx
0x1800a048e  sub     rsp, 0B0h
0x1800a0495  mov     rax, cs:__security_cookie
0x1800a049c  xor     rax, rsp
0x1800a049f  mov     [rsp+0B8h+var_18], rax
0x1800a04a7  xor     edx, edx; Val
0x1800a04a9  mov     rbx, rcx
0x1800a04ac  lea     rcx, [rsp+0B8h+Buffer]; void *
0x1800a04b1  lea     r8d, [rdx+68h]; Size
0x1800a04b5  call    memset_0
0x1800a04ba  lea     r8, aRb; "rb"
0x1800a04c1  mov     [rsp+0B8h+Stream], 0
0x1800a04ca  mov     rdx, rbx; FileName
0x1800a04cd  lea     rcx, [rsp+0B8h+Stream]; Stream
0x1800a04d2  call    cs:__imp__wfopen_s
0x1800a04d8  mov     rcx, [rsp+0B8h+Stream]
0x1800a04dd  test    rcx, rcx
0x1800a04e0  jz      short loc_1800A050B
0x1800a04e2  test    eax, eax
0x1800a04e4  jnz     short loc_1800A0500
0x1800a04e6  mov     r9, rcx; Stream
0x1800a04e9  lea     edx, [rax+68h]; ElementSize
0x1800a04ec  lea     rcx, [rsp+0B8h+Buffer]; Buffer
0x1800a04f1  lea     r8d, [rax+1]; ElementCount
0x1800a04f5  call    cs:__imp_fread
0x1800a04fb  mov     rcx, [rsp+0B8h+Stream]; Stream
0x1800a0500  test    rcx, rcx
0x1800a0503  jz      short loc_1800A050B
0x1800a0505  call    cs:__imp_fclose
0x1800a050b  xor     al, al
0x1800a050d  mov     rcx, [rsp+0B8h+var_18]
0x1800a0515  xor     rcx, rsp; StackCookie
0x1800a0518  call    __security_check_cookie
0x1800a051d  add     rsp, 0B0h
0x1800a0524  pop     rbx
0x1800a0525  retn
```
