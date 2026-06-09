# CSLLUAComInstance::SLLUADepositOfflineConfirmationId(_GUID const *,ushort *,ushort *)

- ea: `0x18001d590`
- end: `0x18001d62a`
- name: `?SLLUADepositOfflineConfirmationId@CSLLUAComInstance@@UEAAJPEBU_GUID@@PEAG1@Z`
- size: `154`
- prototype: `int(CSLLUAComInstance *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001d590`

## import_xrefs

- `SLC!SLDepositOfflineConfirmationId` at `0x18001d5e8`
- `SLC!SLDepositOfflineConfirmationId` at `0x18001d5e8`
- `SLC!SLOpen` at `0x18001d5c8`
- `SLC!SLOpen` at `0x18001d5c8`
- `SLC!SLClose` at `0x18001d612`
- `SLC!SLClose` at `0x18001d612`

## pseudocode

```c
__int64 __fastcall CSLLUAComInstance::SLLUADepositOfflineConfirmationId(
        CSLLUAComInstance *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v7; // rcx
  unsigned int v8; // ebx
  HRESULT v9; // eax
  HSLC phSLC; // [rsp+58h] [rbp+10h] BYREF

  phSLC = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v7 = 2147942487LL;
    v8 = -2147024809;
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_9;
  }
  v9 = SLOpen(&phSLC);
  v8 = v9;
  if ( v9 < 0 || (v9 = SLDepositOfflineConfirmationId(phSLC, a2, a3, a4), v8 = v9, v9 < 0) )
  {
    v7 = (unsigned int)v9;
    goto LABEL_8;
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( phSLC )
    SLClose(phSLC);
  return v8;
}

```

## disassembly

```asm
0x18001d590  push    rbx
0x18001d592  push    rbp
0x18001d593  push    rsi
0x18001d594  push    rdi
0x18001d595  sub     rsp, 28h
0x18001d599  mov     [rsp+48h+phSLC], 0
0x18001d5a2  mov     rdi, r9
0x18001d5a5  mov     rsi, r8
0x18001d5a8  mov     rbp, rdx
0x18001d5ab  test    rdx, rdx
0x18001d5ae  jnz     short loc_18001D5B9
0x18001d5b0  mov     ecx, 80070057h
0x18001d5b5  mov     ebx, ecx
0x18001d5b7  jmp     short loc_18001D5FC
0x18001d5b9  test    rsi, rsi
0x18001d5bc  jz      short loc_18001D5B0
0x18001d5be  test    rdi, rdi
0x18001d5c1  jz      short loc_18001D5B0
0x18001d5c3  lea     rcx, [rsp+48h+phSLC]; phSLC
0x18001d5c8  call    cs:__imp_SLOpen
0x18001d5cf  nop     dword ptr [rax+rax+00h]
0x18001d5d4  mov     ebx, eax
0x18001d5d6  test    eax, eax
0x18001d5d8  js      short loc_18001D5FA
0x18001d5da  mov     rcx, [rsp+48h+phSLC]; hSLC
0x18001d5df  mov     r9, rdi; pwszConfirmationId
0x18001d5e2  mov     r8, rsi; pwszInstallationId
0x18001d5e5  mov     rdx, rbp; pProductSkuId
0x18001d5e8  call    cs:__imp_SLDepositOfflineConfirmationId
0x18001d5ef  nop     dword ptr [rax+rax+00h]
0x18001d5f4  mov     ebx, eax
0x18001d5f6  test    eax, eax
0x18001d5f8  jns     short loc_18001D601
0x18001d5fa  mov     ecx, eax
0x18001d5fc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d601  mov     ecx, ebx
0x18001d603  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d608  mov     rcx, [rsp+48h+phSLC]; hSLC
0x18001d60d  test    rcx, rcx
0x18001d610  jz      short loc_18001D61E
0x18001d612  call    cs:__imp_SLClose
0x18001d619  nop     dword ptr [rax+rax+00h]
0x18001d61e  mov     eax, ebx
0x18001d620  add     rsp, 28h
0x18001d624  pop     rdi
0x18001d625  pop     rsi
0x18001d626  pop     rbp
0x18001d627  pop     rbx
0x18001d628  retn
```
