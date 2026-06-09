# CTokenActivation::DetectSmartCard(int *)

- ea: `0x180037c68`
- end: `0x180037d39`
- name: `?DetectSmartCard@CTokenActivation@@IEAAJPEAH@Z`
- size: `209`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003a800`

## callees

- `0x180003520`
- `0x180004288`
- `0x180036ed8`
- `0x180037c68`
- `0x180038090`

## import_xrefs

- `WinSCard!SCardEstablishContext` at `0x180037c9d`
- `WinSCard!SCardEstablishContext` at `0x180037c9d`
- `WinSCard!SCardReleaseContext` at `0x180037d1f`
- `WinSCard!SCardReleaseContext` at `0x180037d1f`

## pseudocode

```c
__int64 __fastcall CTokenActivation::DetectSmartCard(CTokenActivation *this, int *a2)
{
  int SmartCardReaderStates; // eax
  unsigned int v4; // ebx
  int v5; // r8d
  __int64 v6; // rdx
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF
  int v9; // [rsp+34h] [rbp+Ch]
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF
  SCARDCONTEXT hContext; // [rsp+48h] [rbp+20h] BYREF

  v9 = HIDWORD(this);
  hContext = 0;
  v8 = 0;
  v10 = 0;
  SmartCardReaderStates = SCardEstablishContext(0, 0, 0, &hContext);
  v4 = SmartCardReaderStates;
  if ( SmartCardReaderStates < 0
    || (SmartCardReaderStates = CCryptoHelperT<CEmptyType>::GetSmartCardReaderStates(hContext, &v10, &v8),
        v4 = SmartCardReaderStates,
        SmartCardReaderStates < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)SmartCardReaderStates);
  }
  else
  {
    v5 = 0;
    v6 = 0;
    if ( v8 )
    {
      while ( (*(_BYTE *)(v10 + 72 * v6 + 20) & 0x20) == 0 )
      {
        v6 = (unsigned int)(v6 + 1);
        if ( (unsigned int)v6 >= v8 )
          goto LABEL_9;
      }
      v5 = 1;
    }
LABEL_9:
    *a2 = v5;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>::~SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>(&v10);
  if ( hContext )
    SCardReleaseContext(hContext);
  return v4;
}

```

## disassembly

```asm
0x180037c68  mov     rax, rsp
0x180037c6b  mov     [rax+10h], rbx
0x180037c6f  mov     [rax+8], rcx
0x180037c73  push    rdi
0x180037c74  sub     rsp, 20h
0x180037c78  mov     rdi, rdx
0x180037c7b  mov     qword ptr [rax+20h], 0
0x180037c83  xor     edx, edx; pvReserved1
0x180037c85  mov     dword ptr [rax+8], 0
0x180037c8c  lea     r9, [rax+20h]; phContext
0x180037c90  mov     qword ptr [rax+18h], 0
0x180037c98  xor     r8d, r8d; pvReserved2
0x180037c9b  xor     ecx, ecx; dwScope
0x180037c9d  call    cs:__imp_SCardEstablishContext
0x180037ca4  nop     dword ptr [rax+rax+00h]
0x180037ca9  mov     ebx, eax
0x180037cab  test    eax, eax
0x180037cad  jns     short loc_180037CB8
0x180037caf  mov     ecx, eax
0x180037cb1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037cb6  jmp     short loc_180037D04
0x180037cb8  mov     rcx, [rsp+28h+hContext]; hContext
0x180037cbd  lea     r8, [rsp+28h+arg_0]
0x180037cc2  lea     rdx, [rsp+28h+arg_10]
0x180037cc7  call    ?GetSmartCardReaderStates@?$CCryptoHelperT@VCEmptyType@@@@SAJ_KPEAPEAU_tag_TOKEN_SCARD_READERSTATE@@PEAK@Z; CCryptoHelperT<CEmptyType>::GetSmartCardReaderStates(unsigned __int64,_tag_TOKEN_SCARD_READERSTATE * *,ulong *)
0x180037ccc  mov     ebx, eax
0x180037cce  test    eax, eax
0x180037cd0  js      short loc_180037CAF
0x180037cd2  mov     r9d, [rsp+28h+arg_0]
0x180037cd7  xor     r8d, r8d
0x180037cda  xor     edx, edx
0x180037cdc  test    r9d, r9d
0x180037cdf  jz      short loc_180037D01
0x180037ce1  mov     r10, [rsp+28h+arg_10]
0x180037ce6  lea     rcx, [rdx+rdx*8]
0x180037cea  test    byte ptr [r10+rcx*8+14h], 20h
0x180037cf0  jnz     short loc_180037CFB
0x180037cf2  inc     edx
0x180037cf4  cmp     edx, r9d
0x180037cf7  jb      short loc_180037CE6
0x180037cf9  jmp     short loc_180037D01
0x180037cfb  mov     r8d, 1
0x180037d01  mov     [rdi], r8d
0x180037d04  mov     ecx, ebx
0x180037d06  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037d0b  lea     rcx, [rsp+28h+arg_10]
0x180037d10  call    ??1?$SP@U_tag_TOKEN_SCARD_READERSTATE@@V?$SP_CPP_ARRAY@U_tag_TOKEN_SCARD_READERSTATE@@@@@@QEAA@XZ; SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>::~SP<_tag_TOKEN_SCARD_READERSTATE,SP_CPP_ARRAY<_tag_TOKEN_SCARD_READERSTATE>>(void)
0x180037d15  mov     rcx, [rsp+28h+hContext]; hContext
0x180037d1a  test    rcx, rcx
0x180037d1d  jz      short loc_180037D2B
0x180037d1f  call    cs:__imp_SCardReleaseContext
0x180037d26  nop     dword ptr [rax+rax+00h]
0x180037d2b  mov     eax, ebx
0x180037d2d  mov     rbx, [rsp+28h+arg_8]
0x180037d32  add     rsp, 20h
0x180037d36  pop     rdi
0x180037d37  retn
```
