# WdcCreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)

- ea: `0x18002aa2c`
- end: `0x18002ac7b`
- name: `?WdcCreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(HINSTANCE hModule, const unsigned __int16 *, const unsigned __int16 *, struct IStream **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002e740`
- `0x1800511e8`

## callees

- `0x18000b854`
- `0x18002aa2c`
- `0x180084e1c`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18002ac62`
- `KERNEL32!GlobalFree` at `0x18002ac62`
- `KERNEL32!GlobalUnlock` at `0x18002ac50`
- `KERNEL32!GlobalUnlock` at `0x18002ac50`
- `KERNEL32!GlobalLock` at `0x18002abc7`
- `KERNEL32!GlobalLock` at `0x18002abc7`
- `KERNEL32!GlobalAlloc` at `0x18002ab8c`
- `KERNEL32!GlobalAlloc` at `0x18002ab8c`
- `KERNEL32!GetLastError` at `0x18002aa5d`
- `KERNEL32!GetLastError` at `0x18002aa96`
- `KERNEL32!GetLastError` at `0x18002aafe`
- `KERNEL32!GetLastError` at `0x18002ab55`
- `KERNEL32!GetLastError` at `0x18002ab9a`
- `KERNEL32!GetLastError` at `0x18002abd5`
- `KERNEL32!GetLastError` at `0x18002aa5d`
- `KERNEL32!GetLastError` at `0x18002aa96`
- `KERNEL32!GetLastError` at `0x18002aafe`
- `KERNEL32!GetLastError` at `0x18002ab55`
- `KERNEL32!GetLastError` at `0x18002ab9a`
- `KERNEL32!GetLastError` at `0x18002abd5`
- `KERNEL32!FindResourceW` at `0x18002aa49`
- `KERNEL32!FindResourceW` at `0x18002aa49`
- `KERNEL32!LoadResource` at `0x18002aa88`
- `KERNEL32!LoadResource` at `0x18002aa88`
- `KERNEL32!LockResource` at `0x18002aab1`
- `KERNEL32!LockResource` at `0x18002aab1`
- `KERNEL32!SizeofResource` at `0x18002ab49`
- `KERNEL32!SizeofResource` at `0x18002ab49`
- `KERNEL32!FreeResource` at `0x18002ac42`
- `KERNEL32!FreeResource` at `0x18002ac42`
- `ole32!CreateStreamOnHGlobal` at `0x18002ac0d`
- `ole32!CreateStreamOnHGlobal` at `0x18002ac0d`

## string_xrefs

- `0x18002aae0`: `WdcCreateStreamFromResource`
- `0x18002ab2b`: `WdcCreateStreamFromResource`
- `0x18002ac27`: `WdcCreateStreamFromResource`

## pseudocode

```c
__int64 __fastcall WdcCreateStreamFromResource(
        HINSTANCE hModule,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IStream **a4)
{
  HRSRC ResourceW; // rax
  HRSRC v7; // rdi
  signed int LastError; // eax
  signed int v9; // ebx
  void *v10; // r14
  void *v11; // rsi
  HGLOBAL Resource; // rax
  void *v13; // r15
  signed int v14; // eax
  const void *v15; // r12
  signed int v16; // eax
  DWORD v17; // eax
  SIZE_T v18; // rdi
  signed int v19; // eax
  HRESULT StreamOnHGlobal; // eax
  HGLOBAL v21; // rax
  signed int v22; // eax
  LPVOID v23; // rax
  signed int v24; // eax
  HRESULT v26; // [rsp+20h] [rbp-58h]

  ResourceW = FindResourceW(hModule, a2, (LPCWSTR)0x17);
  v7 = ResourceW;
  if ( !ResourceW || ResourceW == (HRSRC)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( !LastError )
      goto LABEL_15;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_16;
  }
  v10 = 0;
  v11 = 0;
  Resource = LoadResource(hModule, v7);
  v13 = Resource;
  if ( !Resource )
  {
    v14 = GetLastError();
    v9 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v9 = (unsigned __int16)v14 | 0x80070000;
      if ( v9 >= 0 )
        goto LABEL_13;
LABEL_16:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
        "WdcCreateStreamFromResource",
        0,
        L"FAILURE: 0x%08x",
        v9);
      return (unsigned int)v9;
    }
LABEL_15:
    v9 = -2147467259;
    goto LABEL_16;
  }
  if ( Resource != (HGLOBAL)-1LL )
    goto LABEL_13;
  v16 = GetLastError();
  v9 = v16;
  if ( !v16 )
  {
    v9 = -2147467259;
LABEL_24:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
      "WdcCreateStreamFromResource",
      0,
      L"FAILURE: 0x%08x",
      v9);
LABEL_53:
    FreeResource(v13);
    goto LABEL_54;
  }
  if ( v16 > 0 )
    v9 = (unsigned __int16)v16 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_24;
LABEL_13:
  v15 = LockResource(v13);
  if ( !v15 )
  {
    v9 = -2147467259;
    goto LABEL_52;
  }
  v17 = SizeofResource(hModule, v7);
  v18 = v17;
  if ( !v17 )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( !v19 )
    {
      v9 = -2147467259;
LABEL_32:
      StreamOnHGlobal = v9;
LABEL_50:
      v26 = StreamOnHGlobal;
      goto LABEL_51;
    }
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_32;
  }
  v21 = GlobalAlloc(2u, v18);
  v11 = v21;
  if ( !v21 || v21 == (HGLOBAL)-1LL )
  {
    v22 = GetLastError();
    v9 = v22;
    if ( !v22 )
    {
LABEL_39:
      v9 = -2147467259;
      goto LABEL_40;
    }
    if ( v22 > 0 )
      v9 = (unsigned __int16)v22 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_40;
  }
  v23 = GlobalLock(v11);
  v10 = v23;
  if ( v23 && v23 != (LPVOID)-1LL )
    goto LABEL_49;
  v24 = GetLastError();
  v9 = v24;
  if ( !v24 )
    goto LABEL_39;
  if ( v24 > 0 )
    v9 = (unsigned __int16)v24 | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_49:
    memcpy_0(v10, v15, v18);
    StreamOnHGlobal = CreateStreamOnHGlobal(v11, 1, a4);
    v9 = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
      goto LABEL_52;
    goto LABEL_50;
  }
LABEL_40:
  v26 = v9;
LABEL_51:
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
    "WdcCreateStreamFromResource",
    0,
    L"FAILURE: 0x%08x",
    v26);
LABEL_52:
  if ( v13 )
    goto LABEL_53;
LABEL_54:
  if ( v10 )
    GlobalUnlock(v10);
  if ( v9 < 0 && v11 )
    GlobalFree(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002aa2c  push    rbx
0x18002aa2e  push    rbp
0x18002aa2f  push    rsi
0x18002aa30  push    rdi
0x18002aa31  push    r12
0x18002aa33  push    r13
0x18002aa35  push    r14
0x18002aa37  push    r15
0x18002aa39  sub     rsp, 38h
0x18002aa3d  mov     r8d, 17h; lpType
0x18002aa43  mov     r13, r9
0x18002aa46  mov     rbp, rcx
0x18002aa49  call    cs:__imp_FindResourceW
0x18002aa4f  mov     rdi, rax
0x18002aa52  mov     r12d, 80070000h
0x18002aa58  test    rax, rax
0x18002aa5b  jnz     short loc_18002AA77
0x18002aa5d  call    cs:__imp_GetLastError
0x18002aa63  mov     ebx, eax
0x18002aa65  test    eax, eax
0x18002aa67  jz      short loc_18002AACD
0x18002aa69  jle     short loc_18002AA71
0x18002aa6b  movzx   ebx, ax
0x18002aa6e  or      ebx, r12d
0x18002aa71  test    ebx, ebx
0x18002aa73  jns     short loc_18002AA7D
0x18002aa75  jmp     short loc_18002AAD2
0x18002aa77  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002aa7b  jz      short loc_18002AA5D
0x18002aa7d  mov     rdx, rdi; hResInfo
0x18002aa80  mov     rcx, rbp; hModule
0x18002aa83  xor     r14d, r14d
0x18002aa86  xor     esi, esi
0x18002aa88  call    cs:__imp_LoadResource
0x18002aa8e  mov     r15, rax
0x18002aa91  test    rax, rax
0x18002aa94  jnz     short loc_18002AAF8
0x18002aa96  call    cs:__imp_GetLastError
0x18002aa9c  mov     ebx, eax
0x18002aa9e  test    eax, eax
0x18002aaa0  jz      short loc_18002AACD
0x18002aaa2  jle     short loc_18002AAAA
0x18002aaa4  movzx   ebx, ax
0x18002aaa7  or      ebx, r12d
0x18002aaaa  test    ebx, ebx
0x18002aaac  js      short loc_18002AAD2
0x18002aaae  mov     rcx, r15; hResData
0x18002aab1  call    cs:__imp_LockResource
0x18002aab7  mov     r12, rax
0x18002aaba  test    rax, rax
0x18002aabd  jnz     loc_18002AB43
0x18002aac3  mov     ebx, 80004005h
0x18002aac8  jmp     loc_18002AC3A
0x18002aacd  mov     ebx, 80004005h
0x18002aad2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002aad9  mov     [rsp+78h+var_58], ebx
0x18002aadd  xor     r8d, r8d; int
0x18002aae0  lea     rdx, aWdccreatestrea; "WdcCreateStreamFromResource"
0x18002aae7  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x18002aaee  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002aaf3  jmp     loc_18002AC68
0x18002aaf8  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18002aafc  jnz     short loc_18002AAAE
0x18002aafe  call    cs:__imp_GetLastError
0x18002ab04  mov     ebx, eax
0x18002ab06  test    eax, eax
0x18002ab08  jz      short loc_18002AB18
0x18002ab0a  jle     short loc_18002AB12
0x18002ab0c  movzx   ebx, ax
0x18002ab0f  or      ebx, r12d
0x18002ab12  test    ebx, ebx
0x18002ab14  jns     short loc_18002AAAE
0x18002ab16  jmp     short loc_18002AB1D
0x18002ab18  mov     ebx, 80004005h
0x18002ab1d  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002ab24  mov     [rsp+78h+var_58], ebx
0x18002ab28  xor     r8d, r8d; int
0x18002ab2b  lea     rdx, aWdccreatestrea; "WdcCreateStreamFromResource"
0x18002ab32  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x18002ab39  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002ab3e  jmp     loc_18002AC3F
0x18002ab43  mov     rdx, rdi; hResInfo
0x18002ab46  mov     rcx, rbp; hModule
0x18002ab49  call    cs:__imp_SizeofResource
0x18002ab4f  mov     edi, eax
0x18002ab51  test    eax, eax
0x18002ab53  jnz     short loc_18002AB7F
0x18002ab55  call    cs:__imp_GetLastError
0x18002ab5b  mov     ebx, eax
0x18002ab5d  test    eax, eax
0x18002ab5f  jz      short loc_18002AB73
0x18002ab61  mov     ebp, 80070000h
0x18002ab66  jle     short loc_18002AB6D
0x18002ab68  movzx   ebx, ax
0x18002ab6b  or      ebx, ebp
0x18002ab6d  test    ebx, ebx
0x18002ab6f  jns     short loc_18002AB84
0x18002ab71  jmp     short loc_18002AB78
0x18002ab73  mov     ebx, 80004005h
0x18002ab78  mov     eax, ebx
0x18002ab7a  jmp     loc_18002AC19
0x18002ab7f  mov     ebp, 80070000h
0x18002ab84  mov     rdx, rdi; dwBytes
0x18002ab87  mov     ecx, 2; uFlags
0x18002ab8c  call    cs:__imp_GlobalAlloc
0x18002ab92  mov     rsi, rax
0x18002ab95  test    rax, rax
0x18002ab98  jnz     short loc_18002ABBE
0x18002ab9a  call    cs:__imp_GetLastError
0x18002aba0  mov     ebx, eax
0x18002aba2  test    eax, eax
0x18002aba4  jz      short loc_18002ABB3
0x18002aba6  jle     short loc_18002ABAD
0x18002aba8  movzx   ebx, ax
0x18002abab  or      ebx, ebp
0x18002abad  test    ebx, ebx
0x18002abaf  jns     short loc_18002ABC4
0x18002abb1  jmp     short loc_18002ABB8
0x18002abb3  mov     ebx, 80004005h
0x18002abb8  mov     [rsp+78h+var_58], ebx
0x18002abbc  jmp     short loc_18002AC1D
0x18002abbe  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002abc2  jz      short loc_18002AB9A
0x18002abc4  mov     rcx, rsi; hMem
0x18002abc7  call    cs:__imp_GlobalLock
0x18002abcd  mov     r14, rax
0x18002abd0  test    rax, rax
0x18002abd3  jnz     short loc_18002ABEE
0x18002abd5  call    cs:__imp_GetLastError
0x18002abdb  mov     ebx, eax
0x18002abdd  test    eax, eax
0x18002abdf  jz      short loc_18002ABB3
0x18002abe1  jle     short loc_18002ABE8
0x18002abe3  movzx   ebx, ax
0x18002abe6  or      ebx, ebp
0x18002abe8  test    ebx, ebx
0x18002abea  jns     short loc_18002ABF4
0x18002abec  jmp     short loc_18002ABB8
0x18002abee  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18002abf2  jz      short loc_18002ABD5
0x18002abf4  mov     r8, rdi; Size
0x18002abf7  mov     rdx, r12; Src
0x18002abfa  mov     rcx, r14; void *
0x18002abfd  call    memcpy_0
0x18002ac02  mov     r8, r13; ppstm
0x18002ac05  mov     edx, 1; fDeleteOnRelease
0x18002ac0a  mov     rcx, rsi; hGlobal
0x18002ac0d  call    cs:__imp_CreateStreamOnHGlobal
0x18002ac13  mov     ebx, eax
0x18002ac15  test    eax, eax
0x18002ac17  jns     short loc_18002AC3A
0x18002ac19  mov     [rsp+78h+var_58], eax
0x18002ac1d  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002ac24  xor     r8d, r8d; int
0x18002ac27  lea     rdx, aWdccreatestrea; "WdcCreateStreamFromResource"
0x18002ac2e  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x18002ac35  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002ac3a  test    r15, r15
0x18002ac3d  jz      short loc_18002AC48
0x18002ac3f  mov     rcx, r15; hResData
0x18002ac42  call    cs:__imp_FreeResource
0x18002ac48  test    r14, r14
0x18002ac4b  jz      short loc_18002AC56
0x18002ac4d  mov     rcx, r14; hMem
0x18002ac50  call    cs:__imp_GlobalUnlock
0x18002ac56  test    ebx, ebx
0x18002ac58  jns     short loc_18002AC68
0x18002ac5a  test    rsi, rsi
0x18002ac5d  jz      short loc_18002AC68
0x18002ac5f  mov     rcx, rsi; hMem
0x18002ac62  call    cs:__imp_GlobalFree
0x18002ac68  mov     eax, ebx
0x18002ac6a  add     rsp, 38h
0x18002ac6e  pop     r15
0x18002ac70  pop     r14
0x18002ac72  pop     r13
0x18002ac74  pop     r12
0x18002ac76  pop     rdi
0x18002ac77  pop     rsi
0x18002ac78  pop     rbp
0x18002ac79  pop     rbx
0x18002ac7a  retn
```
