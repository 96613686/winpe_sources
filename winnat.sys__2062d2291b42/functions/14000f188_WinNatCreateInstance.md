# WinNatCreateInstance

- ea: `0x14000f188`
- end: `0x14000f2d9`
- name: `WinNatCreateInstance`
- size: `337`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140011130`

## callees

- `0x14000c440`
- `0x14000caa0`
- `0x14000d4b4`
- `0x14000d604`
- `0x14000e4b0`
- `0x14000e8cc`
- `0x14000e8ec`
- `0x14000f188`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f1ba`
- `ntoskrnl!ExAllocatePool2` at `0x14000f1ba`

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
  __int64 v11; // r8
  __int64 AddressPool; // rax
  _QWORD *v13; // rcx

  if ( !(unsigned __int8)RoReferenceEx(&dword_140027A84) )
    return 0;
  Pool2 = ExAllocatePool2(64, 960, 1852395095);
  v4 = Pool2;
  if ( !Pool2 )
  {
    WinNatDereferenceGlobal();
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v5, v6, L"Instance allocation failed");
    return 0;
  }
  v8 = (const wchar_t *)(Pool2 + 344);
  if ( StringCchCopyW((STRSAFE_LPWSTR)(Pool2 + 344), v3, pszSrc) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9, v11);
  RtlInitializeScalableMrswLock(v4);
  *(_QWORD *)(v4 + 904) = v4 + 896;
  *(_QWORD *)(v4 + 896) = v4 + 896;
  AddressPool = WinNatLibCreateAddressPool((__int64)qword_140027AE0, v8, 0);
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
  v13 = (_QWORD *)qword_140027AA8;
  if ( *(__int64 **)qword_140027AA8 != &qword_140027AA0 )
    __fastfail(3u);
  *(_QWORD *)(v4 + 328) = &qword_140027AA0;
  *(_QWORD *)(v4 + 336) = v13;
  *v13 = v4 + 328;
  qword_140027AA8 = v4 + 328;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v4 + 320)) <= 1 )
    __fastfail(0xEu);
  return v4;
}

```

## disassembly

```asm
0x14000f188  mov     [rsp+arg_0], rbx
0x14000f18d  mov     [rsp+arg_8], rsi
0x14000f192  push    rdi
0x14000f193  sub     rsp, 20h
0x14000f197  mov     rsi, rcx
0x14000f19a  lea     rcx, dword_140027A84
0x14000f1a1  call    RoReferenceEx
0x14000f1a6  test    al, al
0x14000f1a8  jz      short loc_14000F1F8
0x14000f1aa  mov     edx, 3C0h
0x14000f1af  mov     ecx, 40h ; '@'
0x14000f1b4  mov     r8d, 6E694E57h
0x14000f1ba  call    cs:__imp_ExAllocatePool2
0x14000f1c1  nop     dword ptr [rax+rax+00h]
0x14000f1c6  mov     rbx, rax
0x14000f1c9  test    rax, rax
0x14000f1cc  jnz     short loc_14000F20B
0x14000f1ce  call    WinNatDereferenceGlobal
0x14000f1d3  cmp     cs:dword_140027104, 1
0x14000f1da  jnz     short loc_14000F1F8
0x14000f1dc  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000f1e3  jz      short loc_14000F1F8
0x14000f1e5  lea     r9, aInstanceAlloca; "Instance allocation failed"
0x14000f1ec  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f1f3  call    McTemplateK0z_EtwWriteTransfer
0x14000f1f8  xor     eax, eax
0x14000f1fa  mov     rbx, [rsp+28h+arg_0]
0x14000f1ff  mov     rsi, [rsp+28h+arg_8]
0x14000f204  add     rsp, 20h
0x14000f208  pop     rdi
0x14000f209  retn
0x14000f20b  lea     rdi, [rax+158h]
0x14000f212  mov     r8, rsi; pszSrc
0x14000f215  mov     rcx, rdi; pszDest
0x14000f218  call    StringCchCopyW
0x14000f21d  test    eax, eax
0x14000f21f  jns     short loc_14000F226
0x14000f221  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000f226  mov     rcx, rbx
0x14000f229  call    RtlInitializeScalableMrswLock
0x14000f22e  lea     rax, [rbx+380h]
0x14000f235  xor     r8d, r8d
0x14000f238  mov     [rax+8], rax
0x14000f23c  mov     rdx, rdi
0x14000f23f  mov     [rax], rax
0x14000f242  mov     rcx, cs:qword_140027AE0
0x14000f249  call    WinNatLibCreateAddressPool
0x14000f24e  mov     [rbx+378h], rax
0x14000f255  test    rax, rax
0x14000f258  jnz     short loc_14000F261
0x14000f25a  call    WinNatDereferenceGlobal
0x14000f25f  jmp     short loc_14000F1F8
0x14000f261  lea     rax, [rbx+368h]
0x14000f268  mov     qword ptr [rbx+140h], 1
0x14000f273  mov     [rax+8], rax
0x14000f277  lea     rdx, qword_140027AA0
0x14000f27e  mov     [rax], rax
0x14000f281  mov     byte ptr [rbx+362h], 1
0x14000f288  mov     rcx, cs:qword_140027AA8
0x14000f28f  cmp     [rcx], rdx
0x14000f292  jz      short loc_14000F29B
0x14000f294  mov     ecx, 3
0x14000f299  int     29h; Win8: RtlFailFast(ecx)
0x14000f29b  lea     rax, [rbx+148h]
0x14000f2a2  mov     [rax], rdx
0x14000f2a5  mov     [rax+8], rcx
0x14000f2a9  mov     [rcx], rax
0x14000f2ac  mov     cs:qword_140027AA8, rax
0x14000f2b3  mov     eax, 1
0x14000f2b8  lock xadd [rbx+140h], rax
0x14000f2c1  inc     rax
0x14000f2c4  cmp     rax, 1
0x14000f2c8  jg      short loc_14000F2D1
0x14000f2ca  mov     ecx, 0Eh
0x14000f2cf  int     29h; Win8: RtlFailFast(ecx)
0x14000f2d1  mov     rax, rbx
0x14000f2d4  jmp     loc_14000F1FA
```
