# CModelDownloadComponent::ValidateModelFilesList(ushort const *)

- ea: `0x180100f44`
- end: `0x180101110`
- name: `?ValidateModelFilesList@CModelDownloadComponent@@CAJPEBG@Z`
- size: `460`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f310`

## callees

- `0x180013ec0`
- `0x180079e30`
- `0x18007aae4`
- `0x180100f44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x180100fb3`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x180100fb3`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x180101050`
- `api-ms-win-crt-private-l1-1-0!_o__wstat64i32` at `0x180101050`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1801010de`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1801010de`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x180101026`
- `api-ms-win-crt-private-l1-1-0!_o_feof` at `0x180101026`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010100a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010107b`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010100a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010107b`

## string_xrefs

- `0x180100fce`: `CModelDownloadComponent::ValidateModelFilesList`
- `0x18010109f`: `CModelDownloadComponent::ValidateModelFilesList`
- `0x1801010ba`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2178)`
- `0x18010108e`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2200)`
- `0x180100fbf`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2185)`
- `0x180101016`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2190)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::ValidateModelFilesList(wchar_t *FileName)
{
  errno_t v2; // edi
  const wchar_t *v3; // rax
  int v4; // ebx
  FILE *Stream; // [rsp+30h] [rbp-D0h] BYREF
  struct _stat64i32 Stat; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v9; // [rsp+280h] [rbp+180h]

  memset_0(Buffer, 0, 0x218u);
  Stream = 0;
  if ( !FileName || !*FileName )
  {
    v4 = -2147024809;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::ValidateModelFilesList",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2178)",
      -2147024809);
    v2 = (int)Stream;
    goto LABEL_16;
  }
  v2 = _wfopen_s(&Stream, FileName, L"rb");
  if ( v2 )
  {
    v3 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2185)";
LABEL_5:
    v4 = -2147024891;
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      (const wchar_t *)&NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::ValidateModelFilesList",
      v3,
      -2147024891);
    goto LABEL_16;
  }
  if ( fread(Buffer, 0x218u, 1u, Stream) != 1 )
  {
    v3 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2190)";
    goto LABEL_5;
  }
  v4 = 0;
  while ( !feof(Stream) )
  {
    memset(&Stat, 0, sizeof(Stat));
    v2 = _wstat64i32(Buffer, &Stat);
    if ( v2 || Stat.st_mtime != v9 )
    {
      v4 = -2147024809;
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        (const wchar_t *)&NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::ValidateModelFilesList",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2200)",
        -2147024809);
      break;
    }
    fread(Buffer, 0x218u, (unsigned int)(v2 + 1), Stream);
  }
LABEL_16:
  if ( Stream )
    fclose(Stream);
  if ( v2 || v4 < 0 )
    return (unsigned int)-2147024891;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180100f44  push    rbp
0x180100f46  push    rbx
0x180100f47  push    rsi
0x180100f48  push    rdi
0x180100f49  push    r14
0x180100f4b  push    r15
0x180100f4d  lea     rbp, [rsp-1A8h]
0x180100f55  sub     rsp, 2A8h
0x180100f5c  mov     rax, cs:__security_cookie
0x180100f63  xor     rax, rsp
0x180100f66  mov     [rbp+1D0h+var_40], rax
0x180100f6d  mov     rbx, rcx
0x180100f70  mov     r15d, 218h
0x180100f76  mov     r8d, r15d; Size
0x180100f79  lea     rcx, [rsp+2D0h+Buffer]; void *
0x180100f7e  xor     edx, edx; Val
0x180100f80  call    memset_0
0x180100f85  xor     esi, esi
0x180100f87  mov     r14d, 80070005h
0x180100f8d  mov     [rsp+2D0h+Stream], rsi
0x180100f92  test    rbx, rbx
0x180100f95  jz      loc_18010109A
0x180100f9b  cmp     [rbx], si
0x180100f9e  jz      loc_18010109A
0x180100fa4  lea     r8, aRb; "rb"
0x180100fab  mov     rdx, rbx; FileName
0x180100fae  lea     rcx, [rsp+2D0h+Stream]; Stream
0x180100fb3  call    cs:__imp__wfopen_s
0x180100fb9  mov     edi, eax
0x180100fbb  test    eax, eax
0x180100fbd  jz      short loc_180100FF7
0x180100fbf  lea     rax, aOnecoreuapEndu_115; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180100fc6  mov     [rsp+2D0h+var_2A8], r14d
0x180100fcb  mov     ebx, r14d
0x180100fce  lea     r9, aCmodeldownload; "CModelDownloadComponent::ValidateModelF"...
0x180100fd5  mov     [rsp+2D0h+var_2B0], rax
0x180100fda  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x180100fe1  mov     ecx, 2; int
0x180100fe6  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x180100fed  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x180100ff2  jmp     loc_1801010D4
0x180100ff7  mov     r9, [rsp+2D0h+Stream]; Stream
0x180100ffc  lea     rcx, [rsp+2D0h+Buffer]; Buffer
0x180101001  mov     r8d, 1; ElementCount
0x180101007  mov     rdx, r15; ElementSize
0x18010100a  call    cs:__imp_fread
0x180101010  cmp     rax, 1
0x180101014  jz      short loc_18010101F
0x180101016  lea     rax, aOnecoreuapEndu_73; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18010101d  jmp     short loc_180100FC6
0x18010101f  mov     ebx, esi
0x180101021  mov     rcx, [rsp+2D0h+Stream]; Stream
0x180101026  call    cs:__imp_feof
0x18010102c  test    eax, eax
0x18010102e  jnz     loc_1801010D4
0x180101034  xorps   xmm0, xmm0
0x180101037  lea     rdx, [rsp+2D0h+Stat]; Stat
0x18010103c  lea     rcx, [rsp+2D0h+Buffer]; FileName
0x180101041  movups  xmmword ptr [rsp+2D0h+Stat.st_dev], xmm0
0x180101046  movups  xmmword ptr [rsp+2D0h+Stat.st_rdev], xmm0
0x18010104b  movups  xmmword ptr [rsp+2D0h+Stat.st_mtime], xmm0
0x180101050  call    cs:__imp__wstat64i32
0x180101056  mov     edi, eax
0x180101058  test    eax, eax
0x18010105a  jnz     short loc_180101083
0x18010105c  mov     rax, [rbp+1D0h+var_50]
0x180101063  cmp     [rsp+2D0h+Stat.st_mtime], rax
0x180101068  jnz     short loc_180101083
0x18010106a  mov     r9, [rsp+2D0h+Stream]; Stream
0x18010106f  lea     r8d, [rdi+1]; ElementCount
0x180101073  mov     rdx, r15; ElementSize
0x180101076  lea     rcx, [rsp+2D0h+Buffer]; Buffer
0x18010107b  call    cs:__imp_fread
0x180101081  jmp     short loc_180101021
0x180101083  mov     eax, 80070057h
0x180101088  mov     ebx, eax
0x18010108a  mov     [rsp+2D0h+var_2A8], eax
0x18010108e  lea     rax, aOnecoreuapEndu_341; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180101095  jmp     loc_180100FCE
0x18010109a  mov     eax, 80070057h
0x18010109f  lea     r9, aCmodeldownload; "CModelDownloadComponent::ValidateModelF"...
0x1801010a6  mov     [rsp+2D0h+var_2A8], eax
0x1801010aa  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1801010b1  mov     ebx, eax
0x1801010b3  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1801010ba  lea     rax, aOnecoreuapEndu_137; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1801010c1  mov     ecx, 2; int
0x1801010c6  mov     [rsp+2D0h+var_2B0], rax
0x1801010cb  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x1801010d0  mov     edi, dword ptr [rsp+2D0h+Stream]
0x1801010d4  mov     rcx, [rsp+2D0h+Stream]; Stream
0x1801010d9  test    rcx, rcx
0x1801010dc  jz      short loc_1801010E4
0x1801010de  call    cs:__imp_fclose
0x1801010e4  test    edi, edi
0x1801010e6  jnz     short loc_1801010EC
0x1801010e8  test    ebx, ebx
0x1801010ea  jns     short loc_1801010EF
0x1801010ec  mov     ebx, r14d
0x1801010ef  mov     eax, ebx
0x1801010f1  mov     rcx, [rbp+1D0h+var_40]
0x1801010f8  xor     rcx, rsp; StackCookie
0x1801010fb  call    __security_check_cookie
0x180101100  add     rsp, 2A8h
0x180101107  pop     r15
0x180101109  pop     r14
0x18010110b  pop     rdi
0x18010110c  pop     rsi
0x18010110d  pop     rbx
0x18010110e  pop     rbp
0x18010110f  retn
```
