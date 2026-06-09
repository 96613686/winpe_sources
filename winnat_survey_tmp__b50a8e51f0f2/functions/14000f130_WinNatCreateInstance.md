# WinNatCreateInstance

- ea: `0x14000f130`
- end: `0x14000f281`
- name: `WinNatCreateInstance`
- size: `337`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400110d0`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x14000d4e4`
- `0x14000d634`
- `0x14000e488`
- `0x14000e8a4`
- `0x14000e8c4`
- `0x14000f130`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f162`
- `ntoskrnl!ExAllocatePool2` at `0x14000f162`

## pseudocode

```c
__int64 __fastcall WinNatCreateInstance(STRSAFE_LPCWSTR pszSrc)
{
  __int64 Pool2; // rax
  size_t v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  const wchar_t *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 AddressPool; // rax
  _QWORD *v12; // rcx

  if ( !(unsigned __int8)RoReferenceEx(&dword_140026A84) )
    return 0;
  Pool2 = ExAllocatePool2(64, 960, 1852395095);
  v4 = Pool2;
  if ( !Pool2 )
  {
    WinNatDereferenceGlobal();
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v5, v6, L"Instance allocation failed");
    return 0;
  }
  v8 = (const wchar_t *)(Pool2 + 344);
  if ( StringCchCopyW((STRSAFE_LPWSTR)(Pool2 + 344), v3, pszSrc) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9);
  RtlInitializeScalableMrswLock(v4);
  *(_QWORD *)(v4 + 904) = v4 + 896;
  *(_QWORD *)(v4 + 896) = v4 + 896;
  AddressPool = WinNatLibCreateAddressPool((__int64)qword_140026AE0, v8, 0);
  *(_QWORD *)(v4 + 888) = AddressPool;
  if ( !AddressPool )
  {
    WinNatDereferenceGlobal();
    return 0;
  }
  *(_QWORD *)(v4 + 320) = 1;
  *(_QWORD *)(v4 + 880) = v4 + 872;
  *(_QWORD *)(v4 + 872) = v4 + 872;
  *(_BYTE *)(v4 + 866) = 1;
  v12 = (_QWORD *)qword_140026AA8;
  if ( *(__int64 **)qword_140026AA8 != &qword_140026AA0 )
    __fastfail(3u);
  *(_QWORD *)(v4 + 328) = &qword_140026AA0;
  *(_QWORD *)(v4 + 336) = v12;
  *v12 = v4 + 328;
  qword_140026AA8 = v4 + 328;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 320)) <= 1 )
    __fastfail(0xEu);
  return v4;
}

```

## disassembly

```asm
0x14000f130  mov     [rsp+arg_0], rbx
0x14000f135  mov     [rsp+arg_8], rsi
0x14000f13a  push    rdi
0x14000f13b  sub     rsp, 20h
0x14000f13f  mov     rsi, rcx
0x14000f142  lea     rcx, dword_140026A84
0x14000f149  call    RoReferenceEx
0x14000f14e  test    al, al
0x14000f150  jz      short loc_14000F1A0
0x14000f152  mov     edx, 3C0h
0x14000f157  mov     ecx, 40h ; '@'
0x14000f15c  mov     r8d, 6E694E57h
0x14000f162  call    cs:__imp_ExAllocatePool2
0x14000f169  nop     dword ptr [rax+rax+00h]
0x14000f16e  mov     rbx, rax
0x14000f171  test    rax, rax
0x14000f174  jnz     short loc_14000F1B3
0x14000f176  call    WinNatDereferenceGlobal
0x14000f17b  cmp     cs:dword_140026104, 1
0x14000f182  jnz     short loc_14000F1A0
0x14000f184  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000f18b  jz      short loc_14000F1A0
0x14000f18d  lea     r9, aInstanceAlloca; "Instance allocation failed"
0x14000f194  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f19b  call    McTemplateK0z_EtwWriteTransfer
0x14000f1a0  xor     eax, eax
0x14000f1a2  mov     rbx, [rsp+28h+arg_0]
0x14000f1a7  mov     rsi, [rsp+28h+arg_8]
0x14000f1ac  add     rsp, 20h
0x14000f1b0  pop     rdi
0x14000f1b1  retn
0x14000f1b3  lea     rdi, [rax+158h]
0x14000f1ba  mov     r8, rsi; pszSrc
0x14000f1bd  mov     rcx, rdi; pszDest
0x14000f1c0  call    StringCchCopyW
0x14000f1c5  test    eax, eax
0x14000f1c7  jns     short loc_14000F1CE
0x14000f1c9  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000f1ce  mov     rcx, rbx
0x14000f1d1  call    RtlInitializeScalableMrswLock
0x14000f1d6  lea     rax, [rbx+380h]
0x14000f1dd  xor     r8d, r8d
0x14000f1e0  mov     [rax+8], rax
0x14000f1e4  mov     rdx, rdi
0x14000f1e7  mov     [rax], rax
0x14000f1ea  mov     rcx, cs:qword_140026AE0
0x14000f1f1  call    WinNatLibCreateAddressPool
0x14000f1f6  mov     [rbx+378h], rax
0x14000f1fd  test    rax, rax
0x14000f200  jnz     short loc_14000F209
0x14000f202  call    WinNatDereferenceGlobal
0x14000f207  jmp     short loc_14000F1A0
0x14000f209  lea     rax, [rbx+368h]
0x14000f210  mov     qword ptr [rbx+140h], 1
0x14000f21b  mov     [rax+8], rax
0x14000f21f  lea     rdx, qword_140026AA0
0x14000f226  mov     [rax], rax
0x14000f229  mov     byte ptr [rbx+362h], 1
0x14000f230  mov     rcx, cs:qword_140026AA8
0x14000f237  cmp     [rcx], rdx
0x14000f23a  jz      short loc_14000F243
0x14000f23c  mov     ecx, 3
0x14000f241  int     29h; Win8: RtlFailFast(ecx)
0x14000f243  lea     rax, [rbx+148h]
0x14000f24a  mov     [rax], rdx
0x14000f24d  mov     [rax+8], rcx
0x14000f251  mov     [rcx], rax
0x14000f254  mov     cs:qword_140026AA8, rax
0x14000f25b  mov     eax, 1
0x14000f260  lock xadd [rbx+140h], rax
0x14000f269  inc     rax
0x14000f26c  cmp     rax, 1
0x14000f270  jg      short loc_14000F279
0x14000f272  mov     ecx, 0Eh
0x14000f277  int     29h; Win8: RtlFailFast(ecx)
0x14000f279  mov     rax, rbx
0x14000f27c  jmp     loc_14000F1A2
```
