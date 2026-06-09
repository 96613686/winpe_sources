# CPxeProviderHandler::RemoveBannedDeviceIdFromPacket(void *,ulong)

- ea: `0x180006430`
- end: `0x1800065ae`
- name: `?RemoveBannedDeviceIdFromPacket@CPxeProviderHandler@@AEAAKPEAXK@Z`
- size: `382`
- prototype: `__int64 __fastcall(CPxeProviderHandler *this, void *, ULONG)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005aa4`

## callees

- `0x180002994`
- `0x180006430`
- `0x1800070c8`
- `0x180007980`
- `0x180011a62`
- `0x180011a90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000652a`
- `msvcrt!memcpy_s` at `0x18000652a`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180006469`
- `WdsCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x180006469`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000657c`
- `WdsCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x18000657c`
- `WdsCommonLib!DhcpBytesToGuid` at `0x1800064fb`
- `WdsCommonLib!DhcpBytesToGuid` at `0x1800064fb`
- `WdsCommonLib!?IsBanned@CBannedDeviceIds@@QEAAHPEBU_WDS_DEVICE_ID@@@Z` at `0x180006549`
- `WdsCommonLib!?IsBanned@CBannedDeviceIds@@QEAAHPEBU_WDS_DEVICE_ID@@@Z` at `0x180006549`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::RemoveBannedDeviceIdFromPacket(CPxeProviderHandler *this, void *a2, ULONG a3)
{
  CMRSWLock *v3; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  BYTE pbOptionLen[8]; // [rsp+30h] [rbp-89h] BYREF
  PVOID ppOptionValue; // [rsp+38h] [rbp-81h] BYREF
  __int128 Source; // [rsp+40h] [rbp-79h] BYREF
  _BYTE Destination[128]; // [rsp+50h] [rbp-69h] BYREF
  __int64 v17; // [rsp+D0h] [rbp+17h]

  v3 = (CPxeProviderHandler *)((char *)this + 200);
  CMRSWLock::ReaderLock((CPxeProviderHandler *)((char *)this + 200));
  ppOptionValue = 0;
  pbOptionLen[0] = 0;
  Source = 0;
  memset_0(Destination, 0, 0x88u);
  if ( *((_DWORD *)this + 81) )
  {
    v9 = ElValidateWin32_2(5023, v7, v8, 452);
  }
  else if ( PxeDhcpGetOptionValue(a2, a3, 1u, 0x61u, pbOptionLen, &ppOptionValue) == 2 )
  {
    v9 = 0;
  }
  else
  {
    v9 = DhcpBytesToGuid(ppOptionValue, pbOptionLen[0], &Source);
    if ( !(unsigned int)ElValidateWin32_2(v9, v10, v11, 479) )
    {
      memcpy_s(Destination, 0x80u, &Source, 0x10u);
      v17 = 16;
      if ( CBannedDeviceIds::IsBanned(
             (CPxeProviderHandler *)((char *)this + 136),
             (const struct _WDS_DEVICE_ID *)Destination) )
      {
        memmove_0(
          (char *)ppOptionValue - 2,
          (char *)ppOptionValue + pbOptionLen[0],
          a3 + (_DWORD)a2 - ((_DWORD)ppOptionValue + pbOptionLen[0]));
      }
    }
  }
  CMRSWLock::ReaderRelease(v3);
  return v9;
}

```

## disassembly

```asm
0x180006430  mov     [rsp-8+arg_18], rbx
0x180006435  push    rbp
0x180006436  push    rsi
0x180006437  push    rdi
0x180006438  push    r14
0x18000643a  push    r15
0x18000643c  lea     rbp, [rsp-37h]
0x180006441  sub     rsp, 0F0h
0x180006448  mov     rax, cs:__security_cookie
0x18000644f  xor     rax, rsp
0x180006452  mov     [rbp+57h+var_30], rax
0x180006456  lea     rsi, [rcx+0C8h]
0x18000645d  mov     r15, rcx
0x180006460  mov     rcx, rsi
0x180006463  mov     r14d, r8d
0x180006466  mov     rdi, rdx
0x180006469  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x180006470  nop     dword ptr [rax+rax+00h]
0x180006475  and     [rsp+110h+var_D8], 0
0x18000647b  lea     rcx, [rbp+57h+Destination]; void *
0x18000647f  xorps   xmm0, xmm0
0x180006482  mov     [rsp+110h+var_E0], 0
0x180006487  xor     edx, edx; Val
0x180006489  mov     r8d, 88h; Size
0x18000648f  movups  [rbp+57h+Source], xmm0
0x180006493  call    memset_0
0x180006498  cmp     dword ptr [r15+144h], 0
0x1800064a0  jz      short loc_1800064B9
0x1800064a2  mov     ecx, 139Fh
0x1800064a7  mov     r9d, 1C4h
0x1800064ad  call    ElValidateWin32_2
0x1800064b2  mov     ebx, eax
0x1800064b4  jmp     loc_180006579
0x1800064b9  lea     rax, [rsp+110h+var_D8]
0x1800064be  mov     r9b, 61h ; 'a'; bOption
0x1800064c1  mov     [rsp+110h+ppOptionValue], rax; ppOptionValue
0x1800064c6  mov     r8d, 1; uInstance
0x1800064cc  lea     rax, [rsp+110h+var_E0]
0x1800064d1  mov     edx, r14d; uPacketLen
0x1800064d4  mov     rcx, rdi; pPacket
0x1800064d7  mov     [rsp+110h+pbOptionLen], rax; pbOptionLen
0x1800064dc  call    PxeDhcpGetOptionValue
0x1800064e1  cmp     eax, 2
0x1800064e4  jnz     short loc_1800064ED
0x1800064e6  xor     ebx, ebx
0x1800064e8  jmp     loc_180006579
0x1800064ed  movzx   edx, [rsp+110h+var_E0]
0x1800064f2  lea     r8, [rbp+57h+Source]
0x1800064f6  mov     rcx, [rsp+110h+var_D8]
0x1800064fb  call    cs:__imp_DhcpBytesToGuid
0x180006502  nop     dword ptr [rax+rax+00h]
0x180006507  mov     ecx, eax
0x180006509  mov     r9d, 1DFh
0x18000650f  mov     ebx, eax
0x180006511  call    ElValidateWin32_2
0x180006516  test    eax, eax
0x180006518  jnz     short loc_180006579
0x18000651a  lea     r9d, [rax+10h]; SourceSize
0x18000651e  lea     edx, [r9+70h]; DestinationSize
0x180006522  lea     r8, [rbp+57h+Source]; Source
0x180006526  lea     rcx, [rbp+57h+Destination]; Destination
0x18000652a  call    cs:__imp_memcpy_s
0x180006531  nop     dword ptr [rax+rax+00h]
0x180006536  lea     rcx, [r15+88h]
0x18000653d  mov     [rbp+57h+var_40], 10h
0x180006545  lea     rdx, [rbp+57h+Destination]
0x180006549  call    cs:__imp_?IsBanned@CBannedDeviceIds@@QEAAHPEBU_WDS_DEVICE_ID@@@Z; CBannedDeviceIds::IsBanned(_WDS_DEVICE_ID const *)
0x180006550  nop     dword ptr [rax+rax+00h]
0x180006555  test    eax, eax
0x180006557  jz      short loc_180006579
0x180006559  mov     rcx, [rsp+110h+var_D8]
0x18000655e  movzx   edx, [rsp+110h+var_E0]
0x180006563  add     rcx, 0FFFFFFFFFFFFFFFEh; void *
0x180006567  add     rdx, 2
0x18000656b  add     rdx, rcx; Src
0x18000656e  sub     edi, edx
0x180006570  lea     r8d, [r14+rdi]; Size
0x180006574  call    memmove_0
0x180006579  mov     rcx, rsi
0x18000657c  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180006583  nop     dword ptr [rax+rax+00h]
0x180006588  mov     eax, ebx
0x18000658a  mov     rcx, [rbp+57h+var_30]
0x18000658e  xor     rcx, rsp; StackCookie
0x180006591  call    __security_check_cookie
0x180006596  mov     rbx, [rsp+110h+arg_18]
0x18000659e  add     rsp, 0F0h
0x1800065a5  pop     r15
0x1800065a7  pop     r14
0x1800065a9  pop     rdi
0x1800065aa  pop     rsi
0x1800065ab  pop     rbp
0x1800065ac  retn
```
