# DavQueryAndParseResponseEx

- ea: `0x1800134d8`
- end: `0x1800135ae`
- name: `DavQueryAndParseResponseEx`
- size: `214`
- prototype: ``
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049bc`
- `0x180007e10`
- `0x18000d9e4`
- `0x18001507c`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x18001c6e8`
- `0x18001dcb4`
- `0x180020c1c`
- `0x180021008`
- `0x180021628`
- `0x1800229b0`
- `0x180023cd4`

## callees

- `0x18000b7dc`
- `0x18000b89c`
- `0x1800131e8`
- `0x1800134d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013519`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001350f`
- `WINHTTP!WinHttpQueryHeaders` at `0x18001350f`

## pseudocode

```c
__int64 __fastcall DavQueryAndParseResponseEx(void *a1, unsigned int *a2)
{
  DWORD LastError; // ebx
  __int64 v4; // rcx
  unsigned int Buffer; // [rsp+50h] [rbp+18h] BYREF
  DWORD lpdwBufferLength; // [rsp+58h] [rbp+20h] BYREF

  Buffer = 0;
  lpdwBufferLength = 4;
  if ( WinHttpQueryHeaders(a1, 0x20000013u, 0, &Buffer, &lpdwBufferLength, 0) )
  {
    v4 = Buffer;
    if ( a2 )
      *a2 = Buffer;
    LastError = DavMapHttpErrorToDosError(v4);
    if ( (LastError & 0xFFFFFFFD) != 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xABu,
        (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
        LastError);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xAAu,
        (__int64)WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
        LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800134d8  mov     rax, rsp
0x1800134db  push    rbx
0x1800134dc  sub     rsp, 30h
0x1800134e0  mov     qword ptr [rax-10h], 0
0x1800134e8  mov     rbx, rdx
0x1800134eb  mov     dword ptr [rax+18h], 0
0x1800134f2  lea     r9, [rsp+38h+Buffer]; lpBuffer
0x1800134f7  mov     dword ptr [rax+20h], 4
0x1800134fe  lea     rax, [rax+20h]
0x180013502  xor     r8d, r8d; pwszName
0x180013505  mov     [rsp+38h+lpdwBufferLength], rax; lpdwBufferLength
0x18001350a  mov     edx, 20000013h; dwInfoLevel
0x18001350f  call    cs:__imp_WinHttpQueryHeaders
0x180013515  test    eax, eax
0x180013517  jnz     short loc_180013554
0x180013519  call    cs:__imp_GetLastError
0x18001351f  mov     ebx, eax
0x180013521  mov     rcx, cs:WPP_GLOBAL_Control
0x180013528  lea     rax, WPP_GLOBAL_Control
0x18001352f  cmp     rcx, rax
0x180013532  jz      short loc_1800135A6
0x180013534  test    byte ptr [rcx+1Ch], 1
0x180013538  jz      short loc_1800135A6
0x18001353a  mov     rcx, [rcx+10h]
0x18001353e  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013545  mov     edx, 0AAh
0x18001354a  mov     r9d, ebx
0x18001354d  call    WPP_SF_d
0x180013552  jmp     short loc_1800135A6
0x180013554  mov     ecx, [rsp+38h+Buffer]
0x180013558  test    rbx, rbx
0x18001355b  jz      short loc_18001355F
0x18001355d  mov     [rbx], ecx
0x18001355f  call    DavMapHttpErrorToDosError
0x180013564  mov     ebx, eax
0x180013566  test    eax, 0FFFFFFFDh
0x18001356b  jz      short loc_1800135A6
0x18001356d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013574  lea     rax, WPP_GLOBAL_Control
0x18001357b  cmp     rcx, rax
0x18001357e  jz      short loc_1800135A6
0x180013580  test    byte ptr [rcx+1Ch], 1
0x180013584  jz      short loc_1800135A6
0x180013586  mov     eax, [rsp+38h+Buffer]
0x18001358a  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x180013591  mov     rcx, [rcx+10h]
0x180013595  mov     edx, 0ABh
0x18001359a  mov     r9d, ebx
0x18001359d  mov     dword ptr [rsp+38h+lpdwBufferLength], eax
0x1800135a1  call    WPP_SF_Dd
0x1800135a6  mov     eax, ebx
0x1800135a8  add     rsp, 30h
0x1800135ac  pop     rbx
0x1800135ad  retn
```
