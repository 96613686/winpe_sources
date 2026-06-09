# ReasonCodeToString

- ea: `0x18001181c`
- end: `0x1800118db`
- name: `ReasonCodeToString`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800117b0`

## callees

- `0x18001181c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011896`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011896`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800118d3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800118d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011864`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118a0`
- `OneX!OneXReasonCodeToString` at `0x1800118c7`
- `OneX!OneXReasonCodeToString` at `0x1800118c7`

## string_xrefs

- `0x18001185d`: `wlanapi.dll`

## pseudocode

```c
__int64 __fastcall ReasonCodeToString(__int64 a1, unsigned int a2, unsigned int a3, WCHAR *a4)
{
  unsigned int v7; // ebx
  __int64 i; // rax
  DWORD LastError; // eax
  HMODULE phModule; // [rsp+50h] [rbp+8h] BYREF

  phModule = 0;
  v7 = 87;
  if ( !a3 || !a4 )
    return v7;
  if ( a2 - 327680 <= 0xFFFF )
  {
    LastError = OneXReasonCodeToString(a2, a3, a4, 0);
  }
  else
  {
    if ( GetModuleHandleExW(0, L"wlanapi.dll", &phModule) )
    {
      for ( i = 0; (unsigned int)i < 0x85; i = (unsigned int)(i + 1) )
      {
        if ( LODWORD(qword_180070710[i]) == a2 )
        {
          if ( !LoadStringW(phModule, HIDWORD(qword_180070710[i]), a4, a3) )
            goto LABEL_10;
          v7 = 0;
          goto LABEL_12;
        }
      }
      goto LABEL_12;
    }
LABEL_10:
    LastError = GetLastError();
  }
  v7 = LastError;
LABEL_12:
  if ( phModule )
    FreeLibrary(phModule);
  return v7;
}

```

## disassembly

```asm
0x18001181c  mov     [rsp+phModule], rcx
0x180011821  push    rbx
0x180011822  push    rbp
0x180011823  push    rsi
0x180011824  push    rdi
0x180011825  sub     rsp, 28h
0x180011829  mov     [rsp+48h+phModule], 0
0x180011832  mov     rsi, r9
0x180011835  mov     ebp, r8d
0x180011838  mov     edi, edx
0x18001183a  mov     ebx, 57h ; 'W'
0x18001183f  test    r8d, r8d
0x180011842  jz      short loc_1800118B2
0x180011844  test    r9, r9
0x180011847  jz      short loc_1800118B2
0x180011849  lea     eax, [rdx-50000h]
0x18001184f  cmp     eax, 0FFFFh
0x180011854  jbe     short loc_1800118BD
0x180011856  lea     r8, [rsp+48h+phModule]; phModule
0x18001185b  xor     ecx, ecx; dwFlags
0x18001185d  lea     rdx, ModuleName; "wlanapi.dll"
0x180011864  call    cs:__imp_GetModuleHandleExW
0x18001186a  test    eax, eax
0x18001186c  jz      short loc_1800118A0
0x18001186e  xor     eax, eax
0x180011870  lea     rcx, qword_180070710
0x180011877  cmp     eax, 85h
0x18001187c  jnb     short loc_1800118A8
0x18001187e  cmp     [rcx+rax*8], edi
0x180011881  jz      short loc_180011887
0x180011883  inc     eax
0x180011885  jmp     short loc_180011877
0x180011887  mov     edx, [rcx+rax*8+4]; uID
0x18001188b  mov     r9d, ebp; cchBufferMax
0x18001188e  mov     rcx, [rsp+48h+phModule]; hInstance
0x180011893  mov     r8, rsi; lpBuffer
0x180011896  call    cs:__imp_LoadStringW
0x18001189c  test    eax, eax
0x18001189e  jnz     short loc_1800118CF
0x1800118a0  call    cs:__imp_GetLastError
0x1800118a6  mov     ebx, eax
0x1800118a8  mov     rcx, [rsp+48h+phModule]; hLibModule
0x1800118ad  test    rcx, rcx
0x1800118b0  jnz     short loc_1800118D3
0x1800118b2  mov     eax, ebx
0x1800118b4  add     rsp, 28h
0x1800118b8  pop     rdi
0x1800118b9  pop     rsi
0x1800118ba  pop     rbp
0x1800118bb  pop     rbx
0x1800118bc  retn
0x1800118bd  xor     r9d, r9d
0x1800118c0  mov     r8, rsi
0x1800118c3  mov     edx, ebp
0x1800118c5  mov     ecx, edi
0x1800118c7  call    cs:__imp_OneXReasonCodeToString
0x1800118cd  jmp     short loc_1800118A6
0x1800118cf  xor     ebx, ebx
0x1800118d1  jmp     short loc_1800118A8
0x1800118d3  call    cs:__imp_FreeLibrary
0x1800118d9  jmp     short loc_1800118B2
```
