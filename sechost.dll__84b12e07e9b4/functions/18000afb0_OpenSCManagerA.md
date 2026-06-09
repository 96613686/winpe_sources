# OpenSCManagerA

- ea: `0x18000afb0`
- end: `0x18000b120`
- name: `OpenSCManagerA`
- size: `368`
- prototype: `SC_HANDLE __stdcall(LPCSTR lpMachineName, LPCSTR lpDatabaseName, DWORD dwDesiredAccess)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a1f0`
- `0x18000a4f0`
- `0x18000a780`
- `0x18000ae80`
- `0x180039710`
- `0x1800397c0`
- `0x180039870`
- `0x180039910`
- `0x18003aa70`

## callees

- `0x18000afb0`
- `0x18000b9a0`
- `0x1800198d8`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x18000b098`
- `ntdll!RtlInitAnsiString` at `0x18000b098`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000b0bc`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000b0bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b008`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b064`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b064`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b07e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b07e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b0cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b107`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b115`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b0cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b107`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b115`

## pseudocode

```c
SC_HANDLE __stdcall OpenSCManagerA(LPCSTR lpMachineName, LPCSTR lpDatabaseName, DWORD dwDesiredAccess)
{
  unsigned __int16 *v3; // rbp
  WCHAR *v4; // rsi
  unsigned __int64 v8; // rax
  DWORD LastError; // ebx
  SC_HANDLE v11; // rdi
  USHORT v12; // di
  int v13; // eax
  struct _UNICODE_STRING v14; // [rsp+20h] [rbp-58h] BYREF
  _STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v16; // [rsp+80h] [rbp+8h] BYREF

  v3 = 0;
  v4 = 0;
  v16 = 0;
  if ( lpMachineName )
  {
    v14 = 0;
    v8 = -1;
    DestinationString = 0;
    do
      ++v8;
    while ( lpMachineName[v8] );
    if ( v8 > 0x7FFE )
      goto LABEL_5;
    v12 = 2 * (v8 + 1);
    v4 = (WCHAR *)LocalAlloc(0x40u, v12);
    if ( !v4 )
      goto LABEL_5;
    RtlInitAnsiString(&DestinationString, lpMachineName);
    v14.Buffer = v4;
    v14.Length = 0;
    v14.MaximumLength = v12;
    if ( RtlAnsiStringToUnicodeString(&v14, &DestinationString, 0) < 0 )
    {
      LocalFree(v4);
LABEL_5:
      LastError = 8;
LABEL_6:
      SetLastError(LastError);
      return 0;
    }
  }
  if ( !lpDatabaseName || (v13 = ScConvertToUnicode(&v16, lpDatabaseName), v3 = v16, v13) )
  {
    v11 = OpenSCManagerW(v4, v3, dwDesiredAccess);
    if ( v11 )
      LastError = 0;
    else
      LastError = GetLastError();
  }
  else
  {
    v11 = 0;
    LastError = 8;
  }
  if ( v4 )
    LocalFree(v4);
  if ( v3 )
    LocalFree(v3);
  if ( LastError )
    goto LABEL_6;
  return v11;
}

```

## disassembly

```asm
0x18000afb0  push    rbx
0x18000afb2  push    rbp
0x18000afb3  push    rsi
0x18000afb4  push    rdi
0x18000afb5  push    r14
0x18000afb7  push    r15
0x18000afb9  sub     rsp, 48h
0x18000afbd  xor     ebp, ebp
0x18000afbf  xor     esi, esi
0x18000afc1  mov     [rsp+78h+arg_0], rbp
0x18000afc9  mov     r15d, r8d
0x18000afcc  mov     r14, rdx
0x18000afcf  mov     rbx, rcx
0x18000afd2  test    rcx, rcx
0x18000afd5  jz      short loc_18000B01D
0x18000afd7  xorps   xmm0, xmm0
0x18000afda  xorps   xmm1, xmm1
0x18000afdd  movups  xmmword ptr [rsp+78h+var_58.Length], xmm0
0x18000afe2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000afe9  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x18000afee  xchg    ax, ax
0x18000aff0  inc     rax
0x18000aff3  cmp     [rcx+rax], sil
0x18000aff7  jnz     short loc_18000AFF0
0x18000aff9  cmp     rax, 7FFEh
0x18000afff  jbe     short loc_18000B06E
0x18000b001  mov     ebx, 8
0x18000b006  mov     ecx, ebx; dwErrCode
0x18000b008  call    cs:__imp_SetLastError
0x18000b00e  xor     eax, eax
0x18000b010  add     rsp, 48h
0x18000b014  pop     r15
0x18000b016  pop     r14
0x18000b018  pop     rdi
0x18000b019  pop     rsi
0x18000b01a  pop     rbp
0x18000b01b  pop     rbx
0x18000b01c  retn
0x18000b01d  test    r14, r14
0x18000b020  jnz     loc_18000B0D8
0x18000b026  mov     r8d, r15d; dwDesiredAccess
0x18000b029  mov     rdx, rbp; lpDatabaseName
0x18000b02c  mov     rcx, rsi; lpMachineName
0x18000b02f  call    OpenSCManagerW
0x18000b034  mov     rdi, rax
0x18000b037  test    rax, rax
0x18000b03a  jz      short loc_18000B064
0x18000b03c  xor     ebx, ebx
0x18000b03e  test    rsi, rsi
0x18000b041  jnz     loc_18000B104
0x18000b047  test    rbp, rbp
0x18000b04a  jnz     loc_18000B112
0x18000b050  test    ebx, ebx
0x18000b052  jnz     short loc_18000B006
0x18000b054  mov     rax, rdi
0x18000b057  add     rsp, 48h
0x18000b05b  pop     r15
0x18000b05d  pop     r14
0x18000b05f  pop     rdi
0x18000b060  pop     rsi
0x18000b061  pop     rbp
0x18000b062  pop     rbx
0x18000b063  retn
0x18000b064  call    cs:__imp_GetLastError
0x18000b06a  mov     ebx, eax
0x18000b06c  jmp     short loc_18000B03E
0x18000b06e  inc     ax
0x18000b071  mov     ecx, 40h ; '@'; uFlags
0x18000b076  add     ax, ax
0x18000b079  movzx   edi, ax
0x18000b07c  mov     edx, edi; uBytes
0x18000b07e  call    cs:__imp_LocalAlloc
0x18000b084  mov     rsi, rax
0x18000b087  test    rax, rax
0x18000b08a  jz      loc_18000B001
0x18000b090  mov     rdx, rbx; SourceString
0x18000b093  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18000b098  call    cs:__imp_RtlInitAnsiString
0x18000b09e  xor     ecx, ecx
0x18000b0a0  mov     [rsp+78h+var_58.Buffer], rsi
0x18000b0a5  mov     [rsp+78h+var_58.Length], cx
0x18000b0aa  lea     rdx, [rsp+78h+DestinationString]; SourceString
0x18000b0af  lea     rcx, [rsp+78h+var_58]; DestinationString
0x18000b0b4  mov     [rsp+78h+var_58.MaximumLength], di
0x18000b0b9  xor     r8d, r8d; AllocateDestinationString
0x18000b0bc  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000b0c2  test    eax, eax
0x18000b0c4  jns     loc_18000B01D
0x18000b0ca  mov     rcx, rsi; hMem
0x18000b0cd  call    cs:__imp_LocalFree
0x18000b0d3  jmp     loc_18000B001
0x18000b0d8  mov     rdx, r14; char *
0x18000b0db  lea     rcx, [rsp+78h+arg_0]; unsigned __int16 **
0x18000b0e3  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x18000b0e8  mov     rbp, [rsp+78h+arg_0]
0x18000b0f0  test    eax, eax
0x18000b0f2  jnz     loc_18000B026
0x18000b0f8  xor     edi, edi
0x18000b0fa  mov     ebx, 8
0x18000b0ff  jmp     loc_18000B03E
0x18000b104  mov     rcx, rsi; hMem
0x18000b107  call    cs:__imp_LocalFree
0x18000b10d  jmp     loc_18000B047
0x18000b112  mov     rcx, rbp; hMem
0x18000b115  call    cs:__imp_LocalFree
0x18000b11b  jmp     loc_18000B050
```
